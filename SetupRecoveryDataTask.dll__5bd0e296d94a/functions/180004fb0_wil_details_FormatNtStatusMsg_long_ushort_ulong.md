# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004fb0`
- end: `0x180005020`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004fb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004fda`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004fda`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000500a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000500a`

## string_xrefs

- `0x180004fd3`: `ntdll.dll`

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
0x180004fb0  mov     [rsp+arg_0], rbx
0x180004fb5  mov     [rsp+arg_8], rsi
0x180004fba  push    rdi
0x180004fbb  sub     rsp, 40h
0x180004fbf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004fc6  mov     ebx, r8d
0x180004fc9  mov     rdi, rdx
0x180004fcc  mov     esi, ecx
0x180004fce  test    rax, rax
0x180004fd1  jnz     short loc_180004FE7
0x180004fd3  lea     rcx, ModuleName; "ntdll.dll"
0x180004fda  call    cs:__imp_GetModuleHandleW
0x180004fe0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004fe7  mov     [rsp+48h+Arguments], 0; Arguments
0x180004ff0  mov     r9d, 400h; dwLanguageId
0x180004ff6  mov     [rsp+48h+nSize], ebx; nSize
0x180004ffa  mov     r8d, esi; dwMessageId
0x180004ffd  mov     rdx, rax; lpSource
0x180005000  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180005005  mov     ecx, 1A00h; dwFlags
0x18000500a  call    cs:__imp_FormatMessageW
0x180005010  mov     rbx, [rsp+48h+arg_0]
0x180005015  mov     rsi, [rsp+48h+arg_8]
0x18000501a  add     rsp, 40h
0x18000501e  pop     rdi
0x18000501f  retn
```
