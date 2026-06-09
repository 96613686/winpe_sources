# InstallPBHook

- ea: `0x1801021e8`
- end: `0x180102345`
- name: `InstallPBHook`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180101504`

## callees

- `0x180024478`
- `0x1801013b8`
- `0x1801021e8`
- `0x180102a4c`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x18010221a`
- `KERNEL32!GetModuleHandleA` at `0x180102238`
- `KERNEL32!GetModuleHandleA` at `0x18010221a`
- `KERNEL32!GetModuleHandleA` at `0x180102238`
- `KERNEL32!FreeLibrary` at `0x180102304`
- `KERNEL32!FreeLibrary` at `0x180102304`
- `KERNEL32!GetProcAddress` at `0x1801022c7`
- `KERNEL32!GetProcAddress` at `0x1801022e2`
- `KERNEL32!GetProcAddress` at `0x1801022c7`
- `KERNEL32!GetProcAddress` at `0x1801022e2`
- `USER32!SetWindowsHookExW` at `0x18010224f`
- `USER32!SetWindowsHookExW` at `0x18010224f`
- `USER32!SetWindowsHookExA` at `0x180102230`
- `USER32!SetWindowsHookExA` at `0x180102230`

## string_xrefs

- `0x180102296`: `user32.dll`

## pseudocode

```c

```
