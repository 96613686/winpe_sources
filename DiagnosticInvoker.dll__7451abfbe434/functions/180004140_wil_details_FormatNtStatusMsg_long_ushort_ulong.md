# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004140`
- end: `0x1800041b0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004140`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000416a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000416a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000419a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000419a`

## string_xrefs

- `0x180004163`: `ntdll.dll`

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
0x180004140  mov     [rsp+arg_0], rbx
0x180004145  mov     [rsp+arg_8], rsi
0x18000414a  push    rdi
0x18000414b  sub     rsp, 40h
0x18000414f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004156  mov     ebx, r8d
0x180004159  mov     rdi, rdx
0x18000415c  mov     esi, ecx
0x18000415e  test    rax, rax
0x180004161  jnz     short loc_180004177
0x180004163  lea     rcx, ModuleName; "ntdll.dll"
0x18000416a  call    cs:__imp_GetModuleHandleW
0x180004170  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004177  mov     [rsp+48h+Arguments], 0; Arguments
0x180004180  mov     r9d, 400h; dwLanguageId
0x180004186  mov     [rsp+48h+nSize], ebx; nSize
0x18000418a  mov     r8d, esi; dwMessageId
0x18000418d  mov     rdx, rax; lpSource
0x180004190  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004195  mov     ecx, 1A00h; dwFlags
0x18000419a  call    cs:__imp_FormatMessageW
0x1800041a0  mov     rbx, [rsp+48h+arg_0]
0x1800041a5  mov     rsi, [rsp+48h+arg_8]
0x1800041aa  add     rsp, 40h
0x1800041ae  pop     rdi
0x1800041af  retn
```
