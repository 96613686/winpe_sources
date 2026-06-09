# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x1800072e0`
- end: `0x180007350`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800072e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000730a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000730a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000733a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000733a`

## string_xrefs

- `0x180007303`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  FormatMessageW(0x1A00u, ModuleHandleW, dwMessageId, 0x400u, lpBuffer, nSize, 0);
}

```

## disassembly

```asm
0x1800072e0  mov     [rsp+arg_0], rbx
0x1800072e5  mov     [rsp+arg_8], rsi
0x1800072ea  push    rdi
0x1800072eb  sub     rsp, 40h
0x1800072ef  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800072f6  mov     ebx, r8d
0x1800072f9  mov     rdi, rdx
0x1800072fc  mov     esi, ecx
0x1800072fe  test    rax, rax
0x180007301  jnz     short loc_180007317
0x180007303  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000730a  call    cs:__imp_GetModuleHandleW
0x180007310  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007317  mov     [rsp+48h+Arguments], 0; Arguments
0x180007320  mov     r9d, 400h; dwLanguageId
0x180007326  mov     [rsp+48h+nSize], ebx; nSize
0x18000732a  mov     r8d, esi; dwMessageId
0x18000732d  mov     rdx, rax; lpSource
0x180007330  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180007335  mov     ecx, 1A00h; dwFlags
0x18000733a  call    cs:__imp_FormatMessageW
0x180007340  mov     rbx, [rsp+48h+arg_0]
0x180007345  mov     rsi, [rsp+48h+arg_8]
0x18000734a  add     rsp, 40h
0x18000734e  pop     rdi
0x18000734f  retn
```
