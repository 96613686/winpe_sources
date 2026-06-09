# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x14000a260`
- end: `0x14000a2d0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14000a260`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a28a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a28a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000a2ba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000a2ba`

## string_xrefs

- `0x14000a283`: `ntdll.dll`

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
0x14000a260  mov     [rsp+arg_0], rbx
0x14000a265  mov     [rsp+arg_8], rsi
0x14000a26a  push    rdi
0x14000a26b  sub     rsp, 40h
0x14000a26f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a276  mov     ebx, r8d
0x14000a279  mov     rdi, rdx
0x14000a27c  mov     esi, ecx
0x14000a27e  test    rax, rax
0x14000a281  jnz     short loc_14000A297
0x14000a283  lea     rcx, aNtdllDll; "ntdll.dll"
0x14000a28a  call    cs:__imp_GetModuleHandleW
0x14000a290  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a297  mov     [rsp+48h+Arguments], 0; Arguments
0x14000a2a0  mov     r9d, 400h; dwLanguageId
0x14000a2a6  mov     [rsp+48h+nSize], ebx; nSize
0x14000a2aa  mov     r8d, esi; dwMessageId
0x14000a2ad  mov     rdx, rax; lpSource
0x14000a2b0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x14000a2b5  mov     ecx, 1A00h; dwFlags
0x14000a2ba  call    cs:__imp_FormatMessageW
0x14000a2c0  mov     rbx, [rsp+48h+arg_0]
0x14000a2c5  mov     rsi, [rsp+48h+arg_8]
0x14000a2ca  add     rsp, 40h
0x14000a2ce  pop     rdi
0x14000a2cf  retn
```
