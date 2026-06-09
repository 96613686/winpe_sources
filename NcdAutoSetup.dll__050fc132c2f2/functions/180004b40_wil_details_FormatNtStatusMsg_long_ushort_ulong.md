# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004b40`
- end: `0x180004bb0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004b40`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004b9a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004b9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004b6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004b6a`

## string_xrefs

- `0x180004b63`: `ntdll.dll`

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
0x180004b40  mov     [rsp+arg_0], rbx
0x180004b45  mov     [rsp+arg_8], rsi
0x180004b4a  push    rdi
0x180004b4b  sub     rsp, 40h
0x180004b4f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004b56  mov     ebx, r8d
0x180004b59  mov     rdi, rdx
0x180004b5c  mov     esi, ecx
0x180004b5e  test    rax, rax
0x180004b61  jnz     short loc_180004B77
0x180004b63  lea     rcx, ModuleName; "ntdll.dll"
0x180004b6a  call    cs:__imp_GetModuleHandleW
0x180004b70  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004b77  mov     [rsp+48h+Arguments], 0; Arguments
0x180004b80  mov     r9d, 400h; dwLanguageId
0x180004b86  mov     [rsp+48h+nSize], ebx; nSize
0x180004b8a  mov     r8d, esi; dwMessageId
0x180004b8d  mov     rdx, rax; lpSource
0x180004b90  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004b95  mov     ecx, 1A00h; dwFlags
0x180004b9a  call    cs:__imp_FormatMessageW
0x180004ba0  mov     rbx, [rsp+48h+arg_0]
0x180004ba5  mov     rsi, [rsp+48h+arg_8]
0x180004baa  add     rsp, 40h
0x180004bae  pop     rdi
0x180004baf  retn
```
