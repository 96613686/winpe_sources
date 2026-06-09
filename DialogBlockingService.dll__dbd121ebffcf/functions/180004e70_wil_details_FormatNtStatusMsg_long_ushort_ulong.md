# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004e70`
- end: `0x180004ee0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004e70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e9a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004eca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004eca`

## string_xrefs

- `0x180004e93`: `ntdll.dll`

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
0x180004e70  mov     [rsp+arg_0], rbx
0x180004e75  mov     [rsp+arg_8], rsi
0x180004e7a  push    rdi
0x180004e7b  sub     rsp, 40h
0x180004e7f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004e86  mov     ebx, r8d
0x180004e89  mov     rdi, rdx
0x180004e8c  mov     esi, ecx
0x180004e8e  test    rax, rax
0x180004e91  jnz     short loc_180004EA7
0x180004e93  lea     rcx, ModuleName; "ntdll.dll"
0x180004e9a  call    cs:__imp_GetModuleHandleW
0x180004ea0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004ea7  mov     [rsp+48h+Arguments], 0; Arguments
0x180004eb0  mov     r9d, 400h; dwLanguageId
0x180004eb6  mov     [rsp+48h+nSize], ebx; nSize
0x180004eba  mov     r8d, esi; dwMessageId
0x180004ebd  mov     rdx, rax; lpSource
0x180004ec0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004ec5  mov     ecx, 1A00h; dwFlags
0x180004eca  call    cs:__imp_FormatMessageW
0x180004ed0  mov     rbx, [rsp+48h+arg_0]
0x180004ed5  mov     rsi, [rsp+48h+arg_8]
0x180004eda  add     rsp, 40h
0x180004ede  pop     rdi
0x180004edf  retn
```
