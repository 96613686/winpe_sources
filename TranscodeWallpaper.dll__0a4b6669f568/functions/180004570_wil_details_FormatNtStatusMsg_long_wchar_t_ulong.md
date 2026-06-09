# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x180004570`
- end: `0x1800045e0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004570`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000459a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000459a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800045ca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800045ca`

## string_xrefs

- `0x180004593`: `ntdll.dll`

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
0x180004570  mov     [rsp+arg_0], rbx
0x180004575  mov     [rsp+arg_8], rsi
0x18000457a  push    rdi
0x18000457b  sub     rsp, 40h
0x18000457f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004586  mov     ebx, r8d
0x180004589  mov     rdi, rdx
0x18000458c  mov     esi, ecx
0x18000458e  test    rax, rax
0x180004591  jnz     short loc_1800045A7
0x180004593  lea     rcx, ModuleName; "ntdll.dll"
0x18000459a  call    cs:__imp_GetModuleHandleW
0x1800045a0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800045a7  mov     [rsp+48h+Arguments], 0; Arguments
0x1800045b0  mov     r9d, 400h; dwLanguageId
0x1800045b6  mov     [rsp+48h+nSize], ebx; nSize
0x1800045ba  mov     r8d, esi; dwMessageId
0x1800045bd  mov     rdx, rax; lpSource
0x1800045c0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800045c5  mov     ecx, 1A00h; dwFlags
0x1800045ca  call    cs:__imp_FormatMessageW
0x1800045d0  mov     rbx, [rsp+48h+arg_0]
0x1800045d5  mov     rsi, [rsp+48h+arg_8]
0x1800045da  add     rsp, 40h
0x1800045de  pop     rdi
0x1800045df  retn
```
