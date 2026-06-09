# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180003d40`
- end: `0x180003db0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003d40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003d6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003d6a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003d9a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003d9a`

## string_xrefs

- `0x180003d63`: `ntdll.dll`

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
0x180003d40  mov     [rsp+arg_0], rbx
0x180003d45  mov     [rsp+arg_8], rsi
0x180003d4a  push    rdi
0x180003d4b  sub     rsp, 40h
0x180003d4f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003d56  mov     ebx, r8d
0x180003d59  mov     rdi, rdx
0x180003d5c  mov     esi, ecx
0x180003d5e  test    rax, rax
0x180003d61  jnz     short loc_180003D77
0x180003d63  lea     rcx, ModuleName; "ntdll.dll"
0x180003d6a  call    cs:__imp_GetModuleHandleW
0x180003d70  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003d77  mov     [rsp+48h+Arguments], 0; Arguments
0x180003d80  mov     r9d, 400h; dwLanguageId
0x180003d86  mov     [rsp+48h+nSize], ebx; nSize
0x180003d8a  mov     r8d, esi; dwMessageId
0x180003d8d  mov     rdx, rax; lpSource
0x180003d90  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180003d95  mov     ecx, 1A00h; dwFlags
0x180003d9a  call    cs:__imp_FormatMessageW
0x180003da0  mov     rbx, [rsp+48h+arg_0]
0x180003da5  mov     rsi, [rsp+48h+arg_8]
0x180003daa  add     rsp, 40h
0x180003dae  pop     rdi
0x180003daf  retn
```
