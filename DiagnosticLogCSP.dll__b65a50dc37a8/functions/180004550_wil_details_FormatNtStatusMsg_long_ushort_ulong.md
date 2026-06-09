# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004550`
- end: `0x1800045cd`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004550`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000457a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000457a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800045b0`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800045b0`

## string_xrefs

- `0x180004573`: `ntdll.dll`

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
0x180004550  mov     [rsp+arg_0], rbx
0x180004555  mov     [rsp+arg_8], rsi
0x18000455a  push    rdi
0x18000455b  sub     rsp, 40h
0x18000455f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004566  mov     ebx, r8d
0x180004569  mov     rdi, rdx
0x18000456c  mov     esi, ecx
0x18000456e  test    rax, rax
0x180004571  jnz     short loc_18000458D
0x180004573  lea     rcx, ModuleName; "ntdll.dll"
0x18000457a  call    cs:__imp_GetModuleHandleW
0x180004581  nop     dword ptr [rax+rax+00h]
0x180004586  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000458d  mov     [rsp+48h+Arguments], 0; Arguments
0x180004596  mov     r9d, 400h; dwLanguageId
0x18000459c  mov     [rsp+48h+nSize], ebx; nSize
0x1800045a0  mov     r8d, esi; dwMessageId
0x1800045a3  mov     rdx, rax; lpSource
0x1800045a6  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800045ab  mov     ecx, 1A00h; dwFlags
0x1800045b0  call    cs:__imp_FormatMessageW
0x1800045b7  nop     dword ptr [rax+rax+00h]
0x1800045bc  mov     rbx, [rsp+48h+arg_0]
0x1800045c1  mov     rsi, [rsp+48h+arg_8]
0x1800045c6  add     rsp, 40h
0x1800045ca  pop     rdi
0x1800045cb  retn
```
