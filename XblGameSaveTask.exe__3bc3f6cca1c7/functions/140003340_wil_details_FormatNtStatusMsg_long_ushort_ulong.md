# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140003340`
- end: `0x1400033b0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003340`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000336a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000336a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000339a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000339a`

## string_xrefs

- `0x140003363`: `ntdll.dll`

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
0x140003340  mov     [rsp+arg_0], rbx
0x140003345  mov     [rsp+arg_8], rsi
0x14000334a  push    rdi
0x14000334b  sub     rsp, 40h
0x14000334f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003356  mov     ebx, r8d
0x140003359  mov     rdi, rdx
0x14000335c  mov     esi, ecx
0x14000335e  test    rax, rax
0x140003361  jnz     short loc_140003377
0x140003363  lea     rcx, ModuleName; "ntdll.dll"
0x14000336a  call    cs:__imp_GetModuleHandleW
0x140003370  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003377  mov     [rsp+48h+Arguments], 0; Arguments
0x140003380  mov     r9d, 400h; dwLanguageId
0x140003386  mov     [rsp+48h+nSize], ebx; nSize
0x14000338a  mov     r8d, esi; dwMessageId
0x14000338d  mov     rdx, rax; lpSource
0x140003390  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140003395  mov     ecx, 1A00h; dwFlags
0x14000339a  call    cs:__imp_FormatMessageW
0x1400033a0  mov     rbx, [rsp+48h+arg_0]
0x1400033a5  mov     rsi, [rsp+48h+arg_8]
0x1400033aa  add     rsp, 40h
0x1400033ae  pop     rdi
0x1400033af  retn
```
