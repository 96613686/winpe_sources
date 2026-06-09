# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1400040b0`
- end: `0x140004120`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1400040b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400040da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400040da`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000410a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000410a`

## string_xrefs

- `0x1400040d3`: `ntdll.dll`

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
0x1400040b0  mov     [rsp+arg_0], rbx
0x1400040b5  mov     [rsp+arg_8], rsi
0x1400040ba  push    rdi
0x1400040bb  sub     rsp, 40h
0x1400040bf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400040c6  mov     ebx, r8d
0x1400040c9  mov     rdi, rdx
0x1400040cc  mov     esi, ecx
0x1400040ce  test    rax, rax
0x1400040d1  jnz     short loc_1400040E7
0x1400040d3  lea     rcx, ModuleName; "ntdll.dll"
0x1400040da  call    cs:__imp_GetModuleHandleW
0x1400040e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400040e7  mov     [rsp+48h+Arguments], 0; Arguments
0x1400040f0  mov     r9d, 400h; dwLanguageId
0x1400040f6  mov     [rsp+48h+nSize], ebx; nSize
0x1400040fa  mov     r8d, esi; dwMessageId
0x1400040fd  mov     rdx, rax; lpSource
0x140004100  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140004105  mov     ecx, 1A00h; dwFlags
0x14000410a  call    cs:__imp_FormatMessageW
0x140004110  mov     rbx, [rsp+48h+arg_0]
0x140004115  mov     rsi, [rsp+48h+arg_8]
0x14000411a  add     rsp, 40h
0x14000411e  pop     rdi
0x14000411f  retn
```
