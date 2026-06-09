# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180003540`
- end: `0x1800035b0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003540`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000356a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000356a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000359a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000359a`

## string_xrefs

- `0x180003563`: `ntdll.dll`

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
0x180003540  mov     [rsp+arg_0], rbx
0x180003545  mov     [rsp+arg_8], rsi
0x18000354a  push    rdi
0x18000354b  sub     rsp, 40h
0x18000354f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003556  mov     ebx, r8d
0x180003559  mov     rdi, rdx
0x18000355c  mov     esi, ecx
0x18000355e  test    rax, rax
0x180003561  jnz     short loc_180003577
0x180003563  lea     rcx, ModuleName; "ntdll.dll"
0x18000356a  call    cs:__imp_GetModuleHandleW
0x180003570  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003577  mov     [rsp+48h+Arguments], 0; Arguments
0x180003580  mov     r9d, 400h; dwLanguageId
0x180003586  mov     [rsp+48h+nSize], ebx; nSize
0x18000358a  mov     r8d, esi; dwMessageId
0x18000358d  mov     rdx, rax; lpSource
0x180003590  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180003595  mov     ecx, 1A00h; dwFlags
0x18000359a  call    cs:__imp_FormatMessageW
0x1800035a0  mov     rbx, [rsp+48h+arg_0]
0x1800035a5  mov     rsi, [rsp+48h+arg_8]
0x1800035aa  add     rsp, 40h
0x1800035ae  pop     rdi
0x1800035af  retn
```
