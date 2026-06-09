# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180013a00`
- end: `0x180013a70`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180013a00`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180013a5a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180013a5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013a2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013a2a`

## string_xrefs

- `0x180013a23`: `ntdll.dll`

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
0x180013a00  mov     [rsp+arg_0], rbx
0x180013a05  mov     [rsp+arg_8], rsi
0x180013a0a  push    rdi
0x180013a0b  sub     rsp, 40h
0x180013a0f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013a16  mov     ebx, r8d
0x180013a19  mov     rdi, rdx
0x180013a1c  mov     esi, ecx
0x180013a1e  test    rax, rax
0x180013a21  jnz     short loc_180013A37
0x180013a23  lea     rcx, ModuleName; "ntdll.dll"
0x180013a2a  call    cs:__imp_GetModuleHandleW
0x180013a30  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013a37  mov     [rsp+48h+Arguments], 0; Arguments
0x180013a40  mov     r9d, 400h; dwLanguageId
0x180013a46  mov     [rsp+48h+nSize], ebx; nSize
0x180013a4a  mov     r8d, esi; dwMessageId
0x180013a4d  mov     rdx, rax; lpSource
0x180013a50  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180013a55  mov     ecx, 1A00h; dwFlags
0x180013a5a  call    cs:__imp_FormatMessageW
0x180013a60  mov     rbx, [rsp+48h+arg_0]
0x180013a65  mov     rsi, [rsp+48h+arg_8]
0x180013a6a  add     rsp, 40h
0x180013a6e  pop     rdi
0x180013a6f  retn
```
