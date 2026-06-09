# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004720`
- end: `0x180004790`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004720`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000474a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000474a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000477a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000477a`

## string_xrefs

- `0x180004743`: `ntdll.dll`

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
0x180004720  mov     [rsp+arg_0], rbx
0x180004725  mov     [rsp+arg_8], rsi
0x18000472a  push    rdi
0x18000472b  sub     rsp, 40h
0x18000472f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004736  mov     ebx, r8d
0x180004739  mov     rdi, rdx
0x18000473c  mov     esi, ecx
0x18000473e  test    rax, rax
0x180004741  jnz     short loc_180004757
0x180004743  lea     rcx, ModuleName; "ntdll.dll"
0x18000474a  call    cs:__imp_GetModuleHandleW
0x180004750  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004757  mov     [rsp+48h+Arguments], 0; Arguments
0x180004760  mov     r9d, 400h; dwLanguageId
0x180004766  mov     [rsp+48h+nSize], ebx; nSize
0x18000476a  mov     r8d, esi; dwMessageId
0x18000476d  mov     rdx, rax; lpSource
0x180004770  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004775  mov     ecx, 1A00h; dwFlags
0x18000477a  call    cs:__imp_FormatMessageW
0x180004780  mov     rbx, [rsp+48h+arg_0]
0x180004785  mov     rsi, [rsp+48h+arg_8]
0x18000478a  add     rsp, 40h
0x18000478e  pop     rdi
0x18000478f  retn
```
