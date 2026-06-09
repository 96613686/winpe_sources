# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800048d0`
- end: `0x180004940`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800048d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800048fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800048fa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000492a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000492a`

## string_xrefs

- `0x1800048f3`: `ntdll.dll`

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
0x1800048d0  mov     [rsp+arg_0], rbx
0x1800048d5  mov     [rsp+arg_8], rsi
0x1800048da  push    rdi
0x1800048db  sub     rsp, 40h
0x1800048df  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800048e6  mov     ebx, r8d
0x1800048e9  mov     rdi, rdx
0x1800048ec  mov     esi, ecx
0x1800048ee  test    rax, rax
0x1800048f1  jnz     short loc_180004907
0x1800048f3  lea     rcx, ModuleName; "ntdll.dll"
0x1800048fa  call    cs:__imp_GetModuleHandleW
0x180004900  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004907  mov     [rsp+48h+Arguments], 0; Arguments
0x180004910  mov     r9d, 400h; dwLanguageId
0x180004916  mov     [rsp+48h+nSize], ebx; nSize
0x18000491a  mov     r8d, esi; dwMessageId
0x18000491d  mov     rdx, rax; lpSource
0x180004920  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004925  mov     ecx, 1A00h; dwFlags
0x18000492a  call    cs:__imp_FormatMessageW
0x180004930  mov     rbx, [rsp+48h+arg_0]
0x180004935  mov     rsi, [rsp+48h+arg_8]
0x18000493a  add     rsp, 40h
0x18000493e  pop     rdi
0x18000493f  retn
```
