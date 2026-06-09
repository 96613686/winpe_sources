# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004ac0`
- end: `0x180004b30`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004ac0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004aea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004aea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004b1a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004b1a`

## string_xrefs

- `0x180004ae3`: `ntdll.dll`

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
0x180004ac0  mov     [rsp+arg_0], rbx
0x180004ac5  mov     [rsp+arg_8], rsi
0x180004aca  push    rdi
0x180004acb  sub     rsp, 40h
0x180004acf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004ad6  mov     ebx, r8d
0x180004ad9  mov     rdi, rdx
0x180004adc  mov     esi, ecx
0x180004ade  test    rax, rax
0x180004ae1  jnz     short loc_180004AF7
0x180004ae3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180004aea  call    cs:__imp_GetModuleHandleW
0x180004af0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004af7  mov     [rsp+48h+Arguments], 0; Arguments
0x180004b00  mov     r9d, 400h; dwLanguageId
0x180004b06  mov     [rsp+48h+nSize], ebx; nSize
0x180004b0a  mov     r8d, esi; dwMessageId
0x180004b0d  mov     rdx, rax; lpSource
0x180004b10  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004b15  mov     ecx, 1A00h; dwFlags
0x180004b1a  call    cs:__imp_FormatMessageW
0x180004b20  mov     rbx, [rsp+48h+arg_0]
0x180004b25  mov     rsi, [rsp+48h+arg_8]
0x180004b2a  add     rsp, 40h
0x180004b2e  pop     rdi
0x180004b2f  retn
```
