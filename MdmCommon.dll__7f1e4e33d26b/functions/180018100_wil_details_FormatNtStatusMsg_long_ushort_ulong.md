# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180018100`
- end: `0x180018170`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180018100`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001812a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001812a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001815a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001815a`

## string_xrefs

- `0x180018123`: `ntdll.dll`

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
0x180018100  mov     [rsp+arg_0], rbx
0x180018105  mov     [rsp+arg_8], rsi
0x18001810a  push    rdi
0x18001810b  sub     rsp, 40h
0x18001810f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180018116  mov     ebx, r8d
0x180018119  mov     rdi, rdx
0x18001811c  mov     esi, ecx
0x18001811e  test    rax, rax
0x180018121  jnz     short loc_180018137
0x180018123  lea     rcx, ModuleName; "ntdll.dll"
0x18001812a  call    cs:__imp_GetModuleHandleW
0x180018130  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180018137  mov     [rsp+48h+Arguments], 0; Arguments
0x180018140  mov     r9d, 400h; dwLanguageId
0x180018146  mov     [rsp+48h+nSize], ebx; nSize
0x18001814a  mov     r8d, esi; dwMessageId
0x18001814d  mov     rdx, rax; lpSource
0x180018150  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180018155  mov     ecx, 1A00h; dwFlags
0x18001815a  call    cs:__imp_FormatMessageW
0x180018160  mov     rbx, [rsp+48h+arg_0]
0x180018165  mov     rsi, [rsp+48h+arg_8]
0x18001816a  add     rsp, 40h
0x18001816e  pop     rdi
0x18001816f  retn
```
