# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180003230`
- end: `0x1800032a0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003230`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000325a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000325a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000328a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000328a`

## string_xrefs

- `0x180003253`: `ntdll.dll`

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
0x180003230  mov     [rsp+arg_0], rbx
0x180003235  mov     [rsp+arg_8], rsi
0x18000323a  push    rdi
0x18000323b  sub     rsp, 40h
0x18000323f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003246  mov     ebx, r8d
0x180003249  mov     rdi, rdx
0x18000324c  mov     esi, ecx
0x18000324e  test    rax, rax
0x180003251  jnz     short loc_180003267
0x180003253  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000325a  call    cs:__imp_GetModuleHandleW
0x180003260  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003267  mov     [rsp+48h+Arguments], 0; Arguments
0x180003270  mov     r9d, 400h; dwLanguageId
0x180003276  mov     [rsp+48h+nSize], ebx; nSize
0x18000327a  mov     r8d, esi; dwMessageId
0x18000327d  mov     rdx, rax; lpSource
0x180003280  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180003285  mov     ecx, 1A00h; dwFlags
0x18000328a  call    cs:__imp_FormatMessageW
0x180003290  mov     rbx, [rsp+48h+arg_0]
0x180003295  mov     rsi, [rsp+48h+arg_8]
0x18000329a  add     rsp, 40h
0x18000329e  pop     rdi
0x18000329f  retn
```
