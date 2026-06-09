# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180002eb0`
- end: `0x180002f20`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002eb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002eda`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002eda`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002f0a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002f0a`

## string_xrefs

- `0x180002ed3`: `ntdll.dll`

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
0x180002eb0  mov     [rsp+arg_0], rbx
0x180002eb5  mov     [rsp+arg_8], rsi
0x180002eba  push    rdi
0x180002ebb  sub     rsp, 40h
0x180002ebf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002ec6  mov     ebx, r8d
0x180002ec9  mov     rdi, rdx
0x180002ecc  mov     esi, ecx
0x180002ece  test    rax, rax
0x180002ed1  jnz     short loc_180002EE7
0x180002ed3  lea     rcx, ModuleName; "ntdll.dll"
0x180002eda  call    cs:__imp_GetModuleHandleW
0x180002ee0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002ee7  mov     [rsp+48h+Arguments], 0; Arguments
0x180002ef0  mov     r9d, 400h; dwLanguageId
0x180002ef6  mov     [rsp+48h+nSize], ebx; nSize
0x180002efa  mov     r8d, esi; dwMessageId
0x180002efd  mov     rdx, rax; lpSource
0x180002f00  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180002f05  mov     ecx, 1A00h; dwFlags
0x180002f0a  call    cs:__imp_FormatMessageW
0x180002f10  mov     rbx, [rsp+48h+arg_0]
0x180002f15  mov     rsi, [rsp+48h+arg_8]
0x180002f1a  add     rsp, 40h
0x180002f1e  pop     rdi
0x180002f1f  retn
```
