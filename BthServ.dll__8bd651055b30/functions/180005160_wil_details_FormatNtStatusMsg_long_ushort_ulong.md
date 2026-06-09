# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005160`
- end: `0x1800051d0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005160`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000518a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000518a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800051ba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800051ba`

## string_xrefs

- `0x180005183`: `ntdll.dll`

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
0x180005160  mov     [rsp+arg_0], rbx
0x180005165  mov     [rsp+arg_8], rsi
0x18000516a  push    rdi
0x18000516b  sub     rsp, 40h
0x18000516f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005176  mov     ebx, r8d
0x180005179  mov     rdi, rdx
0x18000517c  mov     esi, ecx
0x18000517e  test    rax, rax
0x180005181  jnz     short loc_180005197
0x180005183  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000518a  call    cs:__imp_GetModuleHandleW
0x180005190  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005197  mov     [rsp+48h+Arguments], 0; Arguments
0x1800051a0  mov     r9d, 400h; dwLanguageId
0x1800051a6  mov     [rsp+48h+nSize], ebx; nSize
0x1800051aa  mov     r8d, esi; dwMessageId
0x1800051ad  mov     rdx, rax; lpSource
0x1800051b0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800051b5  mov     ecx, 1A00h; dwFlags
0x1800051ba  call    cs:__imp_FormatMessageW
0x1800051c0  mov     rbx, [rsp+48h+arg_0]
0x1800051c5  mov     rsi, [rsp+48h+arg_8]
0x1800051ca  add     rsp, 40h
0x1800051ce  pop     rdi
0x1800051cf  retn
```
