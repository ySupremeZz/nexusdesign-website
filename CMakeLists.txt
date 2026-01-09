cmake_minimum_required(VERSION 3.10)
project(NexusDesignAutomation)

# Define a custom target named 'git_setup'
add_custom_target(git_setup
    # 1. Initialize repository
    COMMAND git init
    # 2. Add all files
    COMMAND git add .
    # 3. Initial commit with message "#"
    COMMAND git commit -m "#"
    # 4. Rename current branch to main
    COMMAND git branch -M main
    # 5. Add remote origin
    COMMAND git remote add origin https://github.com/ySupremeZz/nexusdesign-website.git
    # 6. Amend the commit message (as requested in your sequence)
    COMMAND git commit --amend -m "#"
    # 7. Push to origin main
    COMMAND git push -u origin main
    
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
    COMMENT "Executing initial Git setup and push..."
    VERBATIM
)
