# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005530`
- end: `0x1800055a0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005530`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000555a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000555a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000558a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000558a`

## string_xrefs

- `0x180005553`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180005530  mov     [rsp+arg_0], rbx
0x180005535  mov     [rsp+arg_8], rsi
0x18000553a  push    rdi
0x18000553b  sub     rsp, 40h
0x18000553f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005546  mov     ebx, r8d
0x180005549  mov     rdi, rdx
0x18000554c  mov     esi, ecx
0x18000554e  test    rax, rax
0x180005551  jnz     short loc_180005567
0x180005553  lea     rcx, ModuleName; "ntdll.dll"
0x18000555a  call    cs:__imp_GetModuleHandleW
0x180005560  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005567  mov     [rsp+48h+Arguments], 0; Arguments
0x180005570  mov     r9d, 400h; dwLanguageId
0x180005576  mov     [rsp+48h+nSize], ebx; nSize
0x18000557a  mov     r8d, esi; dwMessageId
0x18000557d  mov     rdx, rax; lpSource
0x180005580  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180005585  mov     ecx, 1A00h; dwFlags
0x18000558a  call    cs:__imp_FormatMessageW
0x180005590  mov     rbx, [rsp+48h+arg_0]
0x180005595  mov     rsi, [rsp+48h+arg_8]
0x18000559a  add     rsp, 40h
0x18000559e  pop     rdi
0x18000559f  retn
```
