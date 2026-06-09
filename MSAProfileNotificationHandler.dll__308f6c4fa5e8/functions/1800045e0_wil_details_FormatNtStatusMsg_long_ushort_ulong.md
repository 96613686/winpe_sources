# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800045e0`
- end: `0x180004650`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800045e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000460a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000460a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000463a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000463a`

## string_xrefs

- `0x180004603`: `ntdll.dll`

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
0x1800045e0  mov     [rsp+arg_0], rbx
0x1800045e5  mov     [rsp+arg_8], rsi
0x1800045ea  push    rdi
0x1800045eb  sub     rsp, 40h
0x1800045ef  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800045f6  mov     ebx, r8d
0x1800045f9  mov     rdi, rdx
0x1800045fc  mov     esi, ecx
0x1800045fe  test    rax, rax
0x180004601  jnz     short loc_180004617
0x180004603  lea     rcx, ModuleName; "ntdll.dll"
0x18000460a  call    cs:__imp_GetModuleHandleW
0x180004610  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004617  mov     [rsp+48h+Arguments], 0; Arguments
0x180004620  mov     r9d, 400h; dwLanguageId
0x180004626  mov     [rsp+48h+nSize], ebx; nSize
0x18000462a  mov     r8d, esi; dwMessageId
0x18000462d  mov     rdx, rax; lpSource
0x180004630  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004635  mov     ecx, 1A00h; dwFlags
0x18000463a  call    cs:__imp_FormatMessageW
0x180004640  mov     rbx, [rsp+48h+arg_0]
0x180004645  mov     rsi, [rsp+48h+arg_8]
0x18000464a  add     rsp, 40h
0x18000464e  pop     rdi
0x18000464f  retn
```
