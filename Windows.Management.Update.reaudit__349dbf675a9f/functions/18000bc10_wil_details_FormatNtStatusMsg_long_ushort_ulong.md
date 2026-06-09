# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18000bc10`
- end: `0x18000bc8a`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `122`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000bc10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bc3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bc3a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bc6d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bc6d`

## string_xrefs

- `0x18000bc33`: `ntdll.dll`

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
0x18000bc10  mov     [rsp+arg_0], rbx
0x18000bc15  mov     [rsp+arg_8], rsi
0x18000bc1a  push    rdi
0x18000bc1b  sub     rsp, 40h
0x18000bc1f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bc26  mov     ebx, r8d
0x18000bc29  mov     rdi, rdx
0x18000bc2c  mov     esi, ecx
0x18000bc2e  test    rax, rax
0x18000bc31  jnz     short loc_18000BC4D
0x18000bc33  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000bc3a  call    cs:__imp_GetModuleHandleW
0x18000bc41  nop     dword ptr [rax+rax+00h]
0x18000bc46  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bc4d  and     [rsp+48h+var_18], 0
0x18000bc53  mov     r9d, 400h; dwLanguageId
0x18000bc59  mov     [rsp+48h+nSize], ebx; nSize
0x18000bc5d  mov     r8d, esi; dwMessageId
0x18000bc60  mov     rdx, rax; lpSource
0x18000bc63  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000bc68  mov     ecx, 1A00h; dwFlags
0x18000bc6d  call    cs:__imp_FormatMessageW
0x18000bc74  nop     dword ptr [rax+rax+00h]
0x18000bc79  mov     rbx, [rsp+48h+arg_0]
0x18000bc7e  mov     rsi, [rsp+48h+arg_8]
0x18000bc83  add     rsp, 40h
0x18000bc87  pop     rdi
0x18000bc88  retn
```
