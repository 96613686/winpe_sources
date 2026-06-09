# CShellBrowser::WndProcBS(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18004ec84`
- end: `0x18004f777`
- name: `?WndProcBS@CShellBrowser@@QEAA_JPEAUHWND__@@I_K_J@Z`
- size: `2803`
- prototype: `__int64 __usercall@<rax>(CShellBrowser *__hidden this@<rcx>, HWND hWnd@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64)`
- caller_count: `1`
- callee_count: `48`
- tags: `service_task`

## callers

- `0x18004eb20`

## callees

- `0x18002f35c`
- `0x180036ab8`
- `0x18003e194`
- `0x180047410`
- `0x18004d710`
- `0x18004e9cc`
- `0x18004ec84`
- `0x180050ad0`
- `0x180052a68`
- `0x180053a9c`
- `0x180053c10`
- `0x1800556f4`
- `0x180069adc`
- `0x18006bf34`
- `0x18008f198`
- `0x180090fd4`
- `0x180091268`
- `0x1800a8fa0`
- `0x1800bfbec`
- `0x1800c5e80`
- `0x1800ca9ac`
- `0x1800e3408`
- `0x1800f15c0`
- `0x1800f684c`
- `0x1800f6e64`
- `0x1800fb68c`
- `0x1800fbdf8`
- `0x1800ff034`
- `0x1801019f0`
- `0x180103480`
- `0x180108840`
- `0x1801143f8`
- `0x180127d8c`
- `0x18012efb4`
- `0x18012f3fc`
- `0x1801332dc`
- `0x18013f7d0`
- `0x18019b924`
- `0x1801d1c04`
- `0x1801d3020`
- `0x1801d3188`
- `0x1801d3774`
- `0x1801d397c`
- `0x1801d3ba0`
- `0x1801d3d1c`
- `0x1801d3e68`
- `0x1801d3ecc`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18004f1ff`
- `SHCORE!IUnknown_QueryService` at `0x18004f64a`
- `SHCORE!IUnknown_QueryService` at `0x18004f1ff`
- `SHCORE!IUnknown_QueryService` at `0x18004f64a`
- `SHCORE!__imp_SHAllocShared` at `0x18004f5c4`
- `SHCORE!__imp_SHAllocShared` at `0x18004f5c4`
- `SHELL32!__imp_ILGetSize` at `0x18004f5b2`
- `SHELL32!__imp_ILGetSize` at `0x18004f5b2`
- `SHLWAPI!__imp_StrCmpICW` at `0x18004f0c1`
- `SHLWAPI!__imp_StrCmpICW` at `0x18004f0c1`
- `SHLWAPI!__imp_SHDefWindowProc` at `0x18004f012`
- `SHLWAPI!__imp_SHDefWindowProc` at `0x18004f012`
- `SHLWAPI!__imp_IUnknown_CPContainerInvokeParam` at `0x18004f5e9`
- `SHLWAPI!__imp_IUnknown_CPContainerInvokeParam` at `0x18004f5e9`
- `USER32!SendMessageW` at `0x18004ef41`
- `USER32!SendMessageW` at `0x18004f4cb`
- `USER32!SendMessageW` at `0x18004ef41`
- `USER32!SendMessageW` at `0x18004f4cb`
- `USER32!KillTimer` at `0x18004f30c`
- `USER32!KillTimer` at `0x18004f30c`
- `USER32!SetWindowPos` at `0x18004f13d`
- `USER32!SetWindowPos` at `0x18004f13d`
- `USER32!IsWindowVisible` at `0x18004ed6d`
- `USER32!IsWindowVisible` at `0x18004ed6d`
- `USER32!RegisterWindowMessageW` at `0x18004efa9`
- `USER32!RegisterWindowMessageW` at `0x18004efa9`
- `USER32!GetWindowPlacement` at `0x18004edde`
- `USER32!GetWindowPlacement` at `0x18004edde`
- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x18004f03c`
- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x18004f03c`
- `UxTheme!__imp_IsDarkModeAllowedForApp` at `0x18004f046`
- `UxTheme!__imp_IsDarkModeAllowedForApp` at `0x18004f046`
- `OLEACC!LresultFromObject` at `0x18004f21b`
- `OLEACC!LresultFromObject` at `0x18004f21b`
- `DUI70!FlushThemeHandles` at `0x18004f05e`
- `DUI70!FlushThemeHandles` at `0x18004f05e`

## string_xrefs

- `0x18004efa2`: `ShellFileOpened`

## pseudocode

```c

```
