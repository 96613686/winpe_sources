# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180007b50`
- end: `0x180007bc0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180007b50`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007baa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007baa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007b7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007b7a`

## string_xrefs

- `0x180007b73`: `ntdll.dll`

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
0x180007b50  mov     [rsp+arg_0], rbx
0x180007b55  mov     [rsp+arg_8], rsi
0x180007b5a  push    rdi
0x180007b5b  sub     rsp, 40h
0x180007b5f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007b66  mov     ebx, r8d
0x180007b69  mov     rdi, rdx
0x180007b6c  mov     esi, ecx
0x180007b6e  test    rax, rax
0x180007b71  jnz     short loc_180007B87
0x180007b73  lea     rcx, ModuleName; "ntdll.dll"
0x180007b7a  call    cs:__imp_GetModuleHandleW
0x180007b80  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007b87  mov     [rsp+48h+Arguments], 0; Arguments
0x180007b90  mov     r9d, 400h; dwLanguageId
0x180007b96  mov     [rsp+48h+nSize], ebx; nSize
0x180007b9a  mov     r8d, esi; dwMessageId
0x180007b9d  mov     rdx, rax; lpSource
0x180007ba0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180007ba5  mov     ecx, 1A00h; dwFlags
0x180007baa  call    cs:__imp_FormatMessageW
0x180007bb0  mov     rbx, [rsp+48h+arg_0]
0x180007bb5  mov     rsi, [rsp+48h+arg_8]
0x180007bba  add     rsp, 40h
0x180007bbe  pop     rdi
0x180007bbf  retn
```
