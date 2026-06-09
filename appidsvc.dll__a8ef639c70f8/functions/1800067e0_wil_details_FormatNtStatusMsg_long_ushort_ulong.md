# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800067e0`
- end: `0x180006850`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800067e0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000683a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000683a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000680a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000680a`

## string_xrefs

- `0x180006803`: `ntdll.dll`

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
0x1800067e0  mov     [rsp+arg_0], rbx
0x1800067e5  mov     [rsp+arg_8], rsi
0x1800067ea  push    rdi
0x1800067eb  sub     rsp, 40h
0x1800067ef  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800067f6  mov     ebx, r8d
0x1800067f9  mov     rdi, rdx
0x1800067fc  mov     esi, ecx
0x1800067fe  test    rax, rax
0x180006801  jnz     short loc_180006817
0x180006803  lea     rcx, ModuleName; "ntdll.dll"
0x18000680a  call    cs:__imp_GetModuleHandleW
0x180006810  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006817  mov     [rsp+48h+Arguments], 0; Arguments
0x180006820  mov     r9d, 400h; dwLanguageId
0x180006826  mov     [rsp+48h+nSize], ebx; nSize
0x18000682a  mov     r8d, esi; dwMessageId
0x18000682d  mov     rdx, rax; lpSource
0x180006830  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180006835  mov     ecx, 1A00h; dwFlags
0x18000683a  call    cs:__imp_FormatMessageW
0x180006840  mov     rbx, [rsp+48h+arg_0]
0x180006845  mov     rsi, [rsp+48h+arg_8]
0x18000684a  add     rsp, 40h
0x18000684e  pop     rdi
0x18000684f  retn
```
