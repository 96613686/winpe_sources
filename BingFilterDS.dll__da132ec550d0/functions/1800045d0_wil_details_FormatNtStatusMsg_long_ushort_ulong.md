# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800045d0`
- end: `0x180004640`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800045d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800045fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800045fa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000462a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000462a`

## string_xrefs

- `0x1800045f3`: `ntdll.dll`

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
0x1800045d0  mov     [rsp+arg_0], rbx
0x1800045d5  mov     [rsp+arg_8], rsi
0x1800045da  push    rdi
0x1800045db  sub     rsp, 40h
0x1800045df  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800045e6  mov     ebx, r8d
0x1800045e9  mov     rdi, rdx
0x1800045ec  mov     esi, ecx
0x1800045ee  test    rax, rax
0x1800045f1  jnz     short loc_180004607
0x1800045f3  lea     rcx, ModuleName; "ntdll.dll"
0x1800045fa  call    cs:__imp_GetModuleHandleW
0x180004600  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004607  mov     [rsp+48h+Arguments], 0; Arguments
0x180004610  mov     r9d, 400h; dwLanguageId
0x180004616  mov     [rsp+48h+nSize], ebx; nSize
0x18000461a  mov     r8d, esi; dwMessageId
0x18000461d  mov     rdx, rax; lpSource
0x180004620  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004625  mov     ecx, 1A00h; dwFlags
0x18000462a  call    cs:__imp_FormatMessageW
0x180004630  mov     rbx, [rsp+48h+arg_0]
0x180004635  mov     rsi, [rsp+48h+arg_8]
0x18000463a  add     rsp, 40h
0x18000463e  pop     rdi
0x18000463f  retn
```
