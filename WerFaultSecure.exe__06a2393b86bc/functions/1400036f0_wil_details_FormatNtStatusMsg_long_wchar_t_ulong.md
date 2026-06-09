# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x1400036f0`
- end: `0x140003760`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1400036f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000371a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000371a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000374a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000374a`

## string_xrefs

- `0x140003713`: `ntdll.dll`

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
0x1400036f0  mov     [rsp+arg_0], rbx
0x1400036f5  mov     [rsp+arg_8], rsi
0x1400036fa  push    rdi
0x1400036fb  sub     rsp, 40h
0x1400036ff  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003706  mov     ebx, r8d
0x140003709  mov     rdi, rdx
0x14000370c  mov     esi, ecx
0x14000370e  test    rax, rax
0x140003711  jnz     short loc_140003727
0x140003713  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000371a  call    cs:__imp_GetModuleHandleW
0x140003720  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003727  mov     [rsp+48h+Arguments], 0; Arguments
0x140003730  mov     r9d, 400h; dwLanguageId
0x140003736  mov     [rsp+48h+nSize], ebx; nSize
0x14000373a  mov     r8d, esi; dwMessageId
0x14000373d  mov     rdx, rax; lpSource
0x140003740  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140003745  mov     ecx, 1A00h; dwFlags
0x14000374a  call    cs:__imp_FormatMessageW
0x140003750  mov     rbx, [rsp+48h+arg_0]
0x140003755  mov     rsi, [rsp+48h+arg_8]
0x14000375a  add     rsp, 40h
0x14000375e  pop     rdi
0x14000375f  retn
```
