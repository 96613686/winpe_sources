# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x180008c50`
- end: `0x180008cc0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008c50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c7a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008caa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008caa`

## string_xrefs

- `0x180008c73`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180008c50  mov     [rsp+arg_0], rbx
0x180008c55  mov     [rsp+arg_8], rsi
0x180008c5a  push    rdi
0x180008c5b  sub     rsp, 40h
0x180008c5f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008c66  mov     ebx, r8d
0x180008c69  mov     rdi, rdx
0x180008c6c  mov     esi, ecx
0x180008c6e  test    rax, rax
0x180008c71  jnz     short loc_180008C87
0x180008c73  lea     rcx, ModuleName; "ntdll.dll"
0x180008c7a  call    cs:__imp_GetModuleHandleW
0x180008c80  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008c87  mov     [rsp+48h+Arguments], 0; Arguments
0x180008c90  mov     r9d, 400h; dwLanguageId
0x180008c96  mov     [rsp+48h+nSize], ebx; nSize
0x180008c9a  mov     r8d, esi; dwMessageId
0x180008c9d  mov     rdx, rax; lpSource
0x180008ca0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180008ca5  mov     ecx, 1A00h; dwFlags
0x180008caa  call    cs:__imp_FormatMessageW
0x180008cb0  mov     rbx, [rsp+48h+arg_0]
0x180008cb5  mov     rsi, [rsp+48h+arg_8]
0x180008cba  add     rsp, 40h
0x180008cbe  pop     rdi
0x180008cbf  retn
```
