# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18000b670`
- end: `0x18000b6e0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b670`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b69a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b69a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b6ca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b6ca`

## string_xrefs

- `0x18000b693`: `ntdll.dll`

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
0x18000b670  mov     [rsp+arg_0], rbx
0x18000b675  mov     [rsp+arg_8], rsi
0x18000b67a  push    rdi
0x18000b67b  sub     rsp, 40h
0x18000b67f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b686  mov     ebx, r8d
0x18000b689  mov     rdi, rdx
0x18000b68c  mov     esi, ecx
0x18000b68e  test    rax, rax
0x18000b691  jnz     short loc_18000B6A7
0x18000b693  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000b69a  call    cs:__imp_GetModuleHandleW
0x18000b6a0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b6a7  mov     [rsp+48h+Arguments], 0; Arguments
0x18000b6b0  mov     r9d, 400h; dwLanguageId
0x18000b6b6  mov     [rsp+48h+nSize], ebx; nSize
0x18000b6ba  mov     r8d, esi; dwMessageId
0x18000b6bd  mov     rdx, rax; lpSource
0x18000b6c0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000b6c5  mov     ecx, 1A00h; dwFlags
0x18000b6ca  call    cs:__imp_FormatMessageW
0x18000b6d0  mov     rbx, [rsp+48h+arg_0]
0x18000b6d5  mov     rsi, [rsp+48h+arg_8]
0x18000b6da  add     rsp, 40h
0x18000b6de  pop     rdi
0x18000b6df  retn
```
