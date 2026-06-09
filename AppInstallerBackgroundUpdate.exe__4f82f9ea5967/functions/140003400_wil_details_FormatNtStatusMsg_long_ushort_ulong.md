# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140003400`
- end: `0x140003470`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003400`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000342a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000342a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000345a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000345a`

## string_xrefs

- `0x140003423`: `ntdll.dll`

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
0x140003400  mov     [rsp+arg_0], rbx
0x140003405  mov     [rsp+arg_8], rsi
0x14000340a  push    rdi
0x14000340b  sub     rsp, 40h
0x14000340f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003416  mov     ebx, r8d
0x140003419  mov     rdi, rdx
0x14000341c  mov     esi, ecx
0x14000341e  test    rax, rax
0x140003421  jnz     short loc_140003437
0x140003423  lea     rcx, ModuleName; "ntdll.dll"
0x14000342a  call    cs:__imp_GetModuleHandleW
0x140003430  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003437  mov     [rsp+48h+Arguments], 0; Arguments
0x140003440  mov     r9d, 400h; dwLanguageId
0x140003446  mov     [rsp+48h+nSize], ebx; nSize
0x14000344a  mov     r8d, esi; dwMessageId
0x14000344d  mov     rdx, rax; lpSource
0x140003450  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140003455  mov     ecx, 1A00h; dwFlags
0x14000345a  call    cs:__imp_FormatMessageW
0x140003460  mov     rbx, [rsp+48h+arg_0]
0x140003465  mov     rsi, [rsp+48h+arg_8]
0x14000346a  add     rsp, 40h
0x14000346e  pop     rdi
0x14000346f  retn
```
