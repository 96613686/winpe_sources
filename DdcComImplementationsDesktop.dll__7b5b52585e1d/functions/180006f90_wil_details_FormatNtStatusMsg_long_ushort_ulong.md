# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180006f90`
- end: `0x180007000`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006f90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006fba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006fba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006fea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006fea`

## string_xrefs

- `0x180006fb3`: `ntdll.dll`

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
0x180006f90  mov     [rsp+arg_0], rbx
0x180006f95  mov     [rsp+arg_8], rsi
0x180006f9a  push    rdi
0x180006f9b  sub     rsp, 40h
0x180006f9f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006fa6  mov     ebx, r8d
0x180006fa9  mov     rdi, rdx
0x180006fac  mov     esi, ecx
0x180006fae  test    rax, rax
0x180006fb1  jnz     short loc_180006FC7
0x180006fb3  lea     rcx, ModuleName; "ntdll.dll"
0x180006fba  call    cs:__imp_GetModuleHandleW
0x180006fc0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006fc7  mov     [rsp+48h+Arguments], 0; Arguments
0x180006fd0  mov     r9d, 400h; dwLanguageId
0x180006fd6  mov     [rsp+48h+nSize], ebx; nSize
0x180006fda  mov     r8d, esi; dwMessageId
0x180006fdd  mov     rdx, rax; lpSource
0x180006fe0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180006fe5  mov     ecx, 1A00h; dwFlags
0x180006fea  call    cs:__imp_FormatMessageW
0x180006ff0  mov     rbx, [rsp+48h+arg_0]
0x180006ff5  mov     rsi, [rsp+48h+arg_8]
0x180006ffa  add     rsp, 40h
0x180006ffe  pop     rdi
0x180006fff  retn
```
