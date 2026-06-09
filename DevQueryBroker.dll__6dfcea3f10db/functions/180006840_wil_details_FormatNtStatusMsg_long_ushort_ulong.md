# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180006840`
- end: `0x1800068b0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006840`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000686a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000686a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000689a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000689a`

## string_xrefs

- `0x180006863`: `ntdll.dll`

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
0x180006840  mov     [rsp+arg_0], rbx
0x180006845  mov     [rsp+arg_8], rsi
0x18000684a  push    rdi
0x18000684b  sub     rsp, 40h
0x18000684f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006856  mov     ebx, r8d
0x180006859  mov     rdi, rdx
0x18000685c  mov     esi, ecx
0x18000685e  test    rax, rax
0x180006861  jnz     short loc_180006877
0x180006863  lea     rcx, ModuleName; "ntdll.dll"
0x18000686a  call    cs:__imp_GetModuleHandleW
0x180006870  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006877  mov     [rsp+48h+Arguments], 0; Arguments
0x180006880  mov     r9d, 400h; dwLanguageId
0x180006886  mov     [rsp+48h+nSize], ebx; nSize
0x18000688a  mov     r8d, esi; dwMessageId
0x18000688d  mov     rdx, rax; lpSource
0x180006890  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180006895  mov     ecx, 1A00h; dwFlags
0x18000689a  call    cs:__imp_FormatMessageW
0x1800068a0  mov     rbx, [rsp+48h+arg_0]
0x1800068a5  mov     rsi, [rsp+48h+arg_8]
0x1800068aa  add     rsp, 40h
0x1800068ae  pop     rdi
0x1800068af  retn
```
