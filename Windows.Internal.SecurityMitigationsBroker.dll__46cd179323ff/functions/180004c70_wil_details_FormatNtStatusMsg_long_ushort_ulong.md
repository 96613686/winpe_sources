# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004c70`
- end: `0x180004ce0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004c70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004c9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004c9a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004cca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004cca`

## string_xrefs

- `0x180004c93`: `ntdll.dll`

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
0x180004c70  mov     [rsp+arg_0], rbx
0x180004c75  mov     [rsp+arg_8], rsi
0x180004c7a  push    rdi
0x180004c7b  sub     rsp, 40h
0x180004c7f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004c86  mov     ebx, r8d
0x180004c89  mov     rdi, rdx
0x180004c8c  mov     esi, ecx
0x180004c8e  test    rax, rax
0x180004c91  jnz     short loc_180004CA7
0x180004c93  lea     rcx, ModuleName; "ntdll.dll"
0x180004c9a  call    cs:__imp_GetModuleHandleW
0x180004ca0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004ca7  mov     [rsp+48h+Arguments], 0; Arguments
0x180004cb0  mov     r9d, 400h; dwLanguageId
0x180004cb6  mov     [rsp+48h+nSize], ebx; nSize
0x180004cba  mov     r8d, esi; dwMessageId
0x180004cbd  mov     rdx, rax; lpSource
0x180004cc0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004cc5  mov     ecx, 1A00h; dwFlags
0x180004cca  call    cs:__imp_FormatMessageW
0x180004cd0  mov     rbx, [rsp+48h+arg_0]
0x180004cd5  mov     rsi, [rsp+48h+arg_8]
0x180004cda  add     rsp, 40h
0x180004cde  pop     rdi
0x180004cdf  retn
```
