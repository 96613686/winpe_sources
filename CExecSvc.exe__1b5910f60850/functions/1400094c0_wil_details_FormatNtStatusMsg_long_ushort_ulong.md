# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1400094c0`
- end: `0x140009530`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1400094c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400094ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400094ea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000951a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000951a`

## string_xrefs

- `0x1400094e3`: `ntdll.dll`

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
0x1400094c0  mov     [rsp+arg_0], rbx
0x1400094c5  mov     [rsp+arg_8], rsi
0x1400094ca  push    rdi
0x1400094cb  sub     rsp, 40h
0x1400094cf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400094d6  mov     ebx, r8d
0x1400094d9  mov     rdi, rdx
0x1400094dc  mov     esi, ecx
0x1400094de  test    rax, rax
0x1400094e1  jnz     short loc_1400094F7
0x1400094e3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1400094ea  call    cs:__imp_GetModuleHandleW
0x1400094f0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400094f7  mov     [rsp+48h+Arguments], 0; Arguments
0x140009500  mov     r9d, 400h; dwLanguageId
0x140009506  mov     [rsp+48h+nSize], ebx; nSize
0x14000950a  mov     r8d, esi; dwMessageId
0x14000950d  mov     rdx, rax; lpSource
0x140009510  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140009515  mov     ecx, 1A00h; dwFlags
0x14000951a  call    cs:__imp_FormatMessageW
0x140009520  mov     rbx, [rsp+48h+arg_0]
0x140009525  mov     rsi, [rsp+48h+arg_8]
0x14000952a  add     rsp, 40h
0x14000952e  pop     rdi
0x14000952f  retn
```
