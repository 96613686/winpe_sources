# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x180005da0`
- end: `0x180005e10`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005da0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180005dca`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180005dca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005dfa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005dfa`

## string_xrefs

- `0x180005dc3`: `ntdll.dll`

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
0x180005da0  mov     [rsp+arg_0], rbx
0x180005da5  mov     [rsp+arg_8], rsi
0x180005daa  push    rdi
0x180005dab  sub     rsp, 40h
0x180005daf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005db6  mov     ebx, r8d
0x180005db9  mov     rdi, rdx
0x180005dbc  mov     esi, ecx
0x180005dbe  test    rax, rax
0x180005dc1  jnz     short loc_180005DD7
0x180005dc3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180005dca  call    cs:__imp_GetModuleHandleW
0x180005dd0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005dd7  mov     [rsp+48h+Arguments], 0; Arguments
0x180005de0  mov     r9d, 400h; dwLanguageId
0x180005de6  mov     [rsp+48h+nSize], ebx; nSize
0x180005dea  mov     r8d, esi; dwMessageId
0x180005ded  mov     rdx, rax; lpSource
0x180005df0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180005df5  mov     ecx, 1A00h; dwFlags
0x180005dfa  call    cs:__imp_FormatMessageW
0x180005e00  mov     rbx, [rsp+48h+arg_0]
0x180005e05  mov     rsi, [rsp+48h+arg_8]
0x180005e0a  add     rsp, 40h
0x180005e0e  pop     rdi
0x180005e0f  retn
```
