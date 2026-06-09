# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800048f0`
- end: `0x180004960`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800048f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000491a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000491a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000494a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000494a`

## string_xrefs

- `0x180004913`: `ntdll.dll`

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
0x1800048f0  mov     [rsp+arg_0], rbx
0x1800048f5  mov     [rsp+arg_8], rsi
0x1800048fa  push    rdi
0x1800048fb  sub     rsp, 40h
0x1800048ff  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004906  mov     ebx, r8d
0x180004909  mov     rdi, rdx
0x18000490c  mov     esi, ecx
0x18000490e  test    rax, rax
0x180004911  jnz     short loc_180004927
0x180004913  lea     rcx, ModuleName; "ntdll.dll"
0x18000491a  call    cs:__imp_GetModuleHandleW
0x180004920  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004927  mov     [rsp+48h+Arguments], 0; Arguments
0x180004930  mov     r9d, 400h; dwLanguageId
0x180004936  mov     [rsp+48h+nSize], ebx; nSize
0x18000493a  mov     r8d, esi; dwMessageId
0x18000493d  mov     rdx, rax; lpSource
0x180004940  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004945  mov     ecx, 1A00h; dwFlags
0x18000494a  call    cs:__imp_FormatMessageW
0x180004950  mov     rbx, [rsp+48h+arg_0]
0x180004955  mov     rsi, [rsp+48h+arg_8]
0x18000495a  add     rsp, 40h
0x18000495e  pop     rdi
0x18000495f  retn
```
