# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18002a3c0`
- end: `0x18002a430`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002a3c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a3ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a3ea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002a41a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002a41a`

## string_xrefs

- `0x18002a3e3`: `ntdll.dll`

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
0x18002a3c0  mov     [rsp+arg_0], rbx
0x18002a3c5  mov     [rsp+arg_8], rsi
0x18002a3ca  push    rdi
0x18002a3cb  sub     rsp, 40h
0x18002a3cf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002a3d6  mov     ebx, r8d
0x18002a3d9  mov     rdi, rdx
0x18002a3dc  mov     esi, ecx
0x18002a3de  test    rax, rax
0x18002a3e1  jnz     short loc_18002A3F7
0x18002a3e3  lea     rcx, ModuleName; "ntdll.dll"
0x18002a3ea  call    cs:__imp_GetModuleHandleW
0x18002a3f0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002a3f7  mov     [rsp+48h+Arguments], 0; Arguments
0x18002a400  mov     r9d, 400h; dwLanguageId
0x18002a406  mov     [rsp+48h+nSize], ebx; nSize
0x18002a40a  mov     r8d, esi; dwMessageId
0x18002a40d  mov     rdx, rax; lpSource
0x18002a410  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18002a415  mov     ecx, 1A00h; dwFlags
0x18002a41a  call    cs:__imp_FormatMessageW
0x18002a420  mov     rbx, [rsp+48h+arg_0]
0x18002a425  mov     rsi, [rsp+48h+arg_8]
0x18002a42a  add     rsp, 40h
0x18002a42e  pop     rdi
0x18002a42f  retn
```
