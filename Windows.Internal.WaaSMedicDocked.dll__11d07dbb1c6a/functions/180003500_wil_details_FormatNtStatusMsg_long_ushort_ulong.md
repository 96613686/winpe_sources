# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180003500`
- end: `0x180003570`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003500`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000352a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000352a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000355a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000355a`

## string_xrefs

- `0x180003523`: `ntdll.dll`

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
0x180003500  mov     [rsp+arg_0], rbx
0x180003505  mov     [rsp+arg_8], rsi
0x18000350a  push    rdi
0x18000350b  sub     rsp, 40h
0x18000350f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003516  mov     ebx, r8d
0x180003519  mov     rdi, rdx
0x18000351c  mov     esi, ecx
0x18000351e  test    rax, rax
0x180003521  jnz     short loc_180003537
0x180003523  lea     rcx, ModuleName; "ntdll.dll"
0x18000352a  call    cs:__imp_GetModuleHandleW
0x180003530  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003537  mov     [rsp+48h+Arguments], 0; Arguments
0x180003540  mov     r9d, 400h; dwLanguageId
0x180003546  mov     [rsp+48h+nSize], ebx; nSize
0x18000354a  mov     r8d, esi; dwMessageId
0x18000354d  mov     rdx, rax; lpSource
0x180003550  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180003555  mov     ecx, 1A00h; dwFlags
0x18000355a  call    cs:__imp_FormatMessageW
0x180003560  mov     rbx, [rsp+48h+arg_0]
0x180003565  mov     rsi, [rsp+48h+arg_8]
0x18000356a  add     rsp, 40h
0x18000356e  pop     rdi
0x18000356f  retn
```
