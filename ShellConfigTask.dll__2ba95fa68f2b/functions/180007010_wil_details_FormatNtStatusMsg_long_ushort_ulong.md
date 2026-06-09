# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180007010`
- end: `0x180007080`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180007010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000706a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000706a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000703a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000703a`

## string_xrefs

- `0x180007033`: `ntdll.dll`

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
0x180007010  mov     [rsp+arg_0], rbx
0x180007015  mov     [rsp+arg_8], rsi
0x18000701a  push    rdi
0x18000701b  sub     rsp, 40h
0x18000701f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007026  mov     ebx, r8d
0x180007029  mov     rdi, rdx
0x18000702c  mov     esi, ecx
0x18000702e  test    rax, rax
0x180007031  jnz     short loc_180007047
0x180007033  lea     rcx, ModuleName; "ntdll.dll"
0x18000703a  call    cs:__imp_GetModuleHandleW
0x180007040  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007047  mov     [rsp+48h+Arguments], 0; Arguments
0x180007050  mov     r9d, 400h; dwLanguageId
0x180007056  mov     [rsp+48h+nSize], ebx; nSize
0x18000705a  mov     r8d, esi; dwMessageId
0x18000705d  mov     rdx, rax; lpSource
0x180007060  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180007065  mov     ecx, 1A00h; dwFlags
0x18000706a  call    cs:__imp_FormatMessageW
0x180007070  mov     rbx, [rsp+48h+arg_0]
0x180007075  mov     rsi, [rsp+48h+arg_8]
0x18000707a  add     rsp, 40h
0x18000707e  pop     rdi
0x18000707f  retn
```
