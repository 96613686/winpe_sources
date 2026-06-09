# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140004ff0`
- end: `0x140005060`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140004ff0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000501a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000501a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000504a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000504a`

## string_xrefs

- `0x140005013`: `ntdll.dll`

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
0x140004ff0  mov     [rsp+arg_0], rbx
0x140004ff5  mov     [rsp+arg_8], rsi
0x140004ffa  push    rdi
0x140004ffb  sub     rsp, 40h
0x140004fff  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005006  mov     ebx, r8d
0x140005009  mov     rdi, rdx
0x14000500c  mov     esi, ecx
0x14000500e  test    rax, rax
0x140005011  jnz     short loc_140005027
0x140005013  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000501a  call    cs:__imp_GetModuleHandleW
0x140005020  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005027  mov     [rsp+48h+Arguments], 0; Arguments
0x140005030  mov     r9d, 400h; dwLanguageId
0x140005036  mov     [rsp+48h+nSize], ebx; nSize
0x14000503a  mov     r8d, esi; dwMessageId
0x14000503d  mov     rdx, rax; lpSource
0x140005040  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140005045  mov     ecx, 1A00h; dwFlags
0x14000504a  call    cs:__imp_FormatMessageW
0x140005050  mov     rbx, [rsp+48h+arg_0]
0x140005055  mov     rsi, [rsp+48h+arg_8]
0x14000505a  add     rsp, 40h
0x14000505e  pop     rdi
0x14000505f  retn
```
