# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140006150`
- end: `0x1400061c0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140006150`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000617a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000617a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400061aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400061aa`

## string_xrefs

- `0x140006173`: `ntdll.dll`

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
0x140006150  mov     [rsp+arg_0], rbx
0x140006155  mov     [rsp+arg_8], rsi
0x14000615a  push    rdi
0x14000615b  sub     rsp, 40h
0x14000615f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006166  mov     ebx, r8d
0x140006169  mov     rdi, rdx
0x14000616c  mov     esi, ecx
0x14000616e  test    rax, rax
0x140006171  jnz     short loc_140006187
0x140006173  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000617a  call    cs:__imp_GetModuleHandleW
0x140006180  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006187  mov     [rsp+48h+Arguments], 0; Arguments
0x140006190  mov     r9d, 400h; dwLanguageId
0x140006196  mov     [rsp+48h+nSize], ebx; nSize
0x14000619a  mov     r8d, esi; dwMessageId
0x14000619d  mov     rdx, rax; lpSource
0x1400061a0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1400061a5  mov     ecx, 1A00h; dwFlags
0x1400061aa  call    cs:__imp_FormatMessageW
0x1400061b0  mov     rbx, [rsp+48h+arg_0]
0x1400061b5  mov     rsi, [rsp+48h+arg_8]
0x1400061ba  add     rsp, 40h
0x1400061be  pop     rdi
0x1400061bf  retn
```
