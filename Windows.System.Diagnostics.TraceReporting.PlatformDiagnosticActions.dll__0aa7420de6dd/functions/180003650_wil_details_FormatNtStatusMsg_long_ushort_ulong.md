# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180003650`
- end: `0x1800036c0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003650`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000367a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000367a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800036aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800036aa`

## string_xrefs

- `0x180003673`: `ntdll.dll`

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
0x180003650  mov     [rsp+arg_0], rbx
0x180003655  mov     [rsp+arg_8], rsi
0x18000365a  push    rdi
0x18000365b  sub     rsp, 40h
0x18000365f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003666  mov     ebx, r8d
0x180003669  mov     rdi, rdx
0x18000366c  mov     esi, ecx
0x18000366e  test    rax, rax
0x180003671  jnz     short loc_180003687
0x180003673  lea     rcx, ModuleName; "ntdll.dll"
0x18000367a  call    cs:__imp_GetModuleHandleW
0x180003680  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003687  mov     [rsp+48h+Arguments], 0; Arguments
0x180003690  mov     r9d, 400h; dwLanguageId
0x180003696  mov     [rsp+48h+nSize], ebx; nSize
0x18000369a  mov     r8d, esi; dwMessageId
0x18000369d  mov     rdx, rax; lpSource
0x1800036a0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800036a5  mov     ecx, 1A00h; dwFlags
0x1800036aa  call    cs:__imp_FormatMessageW
0x1800036b0  mov     rbx, [rsp+48h+arg_0]
0x1800036b5  mov     rsi, [rsp+48h+arg_8]
0x1800036ba  add     rsp, 40h
0x1800036be  pop     rdi
0x1800036bf  retn
```
