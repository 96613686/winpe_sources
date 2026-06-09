# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18001b650`
- end: `0x18001b6c0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001b650`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b67a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b67a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001b6aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001b6aa`

## string_xrefs

- `0x18001b673`: `ntdll.dll`

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
0x18001b650  mov     [rsp+arg_0], rbx
0x18001b655  mov     [rsp+arg_8], rsi
0x18001b65a  push    rdi
0x18001b65b  sub     rsp, 40h
0x18001b65f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001b666  mov     ebx, r8d
0x18001b669  mov     rdi, rdx
0x18001b66c  mov     esi, ecx
0x18001b66e  test    rax, rax
0x18001b671  jnz     short loc_18001B687
0x18001b673  lea     rcx, LibFileName; "ntdll.dll"
0x18001b67a  call    cs:__imp_GetModuleHandleW
0x18001b680  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001b687  mov     [rsp+48h+Arguments], 0; Arguments
0x18001b690  mov     r9d, 400h; dwLanguageId
0x18001b696  mov     [rsp+48h+nSize], ebx; nSize
0x18001b69a  mov     r8d, esi; dwMessageId
0x18001b69d  mov     rdx, rax; lpSource
0x18001b6a0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18001b6a5  mov     ecx, 1A00h; dwFlags
0x18001b6aa  call    cs:__imp_FormatMessageW
0x18001b6b0  mov     rbx, [rsp+48h+arg_0]
0x18001b6b5  mov     rsi, [rsp+48h+arg_8]
0x18001b6ba  add     rsp, 40h
0x18001b6be  pop     rdi
0x18001b6bf  retn
```
