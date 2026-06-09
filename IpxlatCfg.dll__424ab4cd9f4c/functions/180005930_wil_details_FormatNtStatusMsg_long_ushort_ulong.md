# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005930`
- end: `0x1800059a0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005930`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000595a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000595a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000598a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000598a`

## string_xrefs

- `0x180005953`: `ntdll.dll`

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
0x180005930  mov     [rsp+arg_0], rbx
0x180005935  mov     [rsp+arg_8], rsi
0x18000593a  push    rdi
0x18000593b  sub     rsp, 40h
0x18000593f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005946  mov     ebx, r8d
0x180005949  mov     rdi, rdx
0x18000594c  mov     esi, ecx
0x18000594e  test    rax, rax
0x180005951  jnz     short loc_180005967
0x180005953  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000595a  call    cs:__imp_GetModuleHandleW
0x180005960  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005967  mov     [rsp+48h+Arguments], 0; Arguments
0x180005970  mov     r9d, 400h; dwLanguageId
0x180005976  mov     [rsp+48h+nSize], ebx; nSize
0x18000597a  mov     r8d, esi; dwMessageId
0x18000597d  mov     rdx, rax; lpSource
0x180005980  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180005985  mov     ecx, 1A00h; dwFlags
0x18000598a  call    cs:__imp_FormatMessageW
0x180005990  mov     rbx, [rsp+48h+arg_0]
0x180005995  mov     rsi, [rsp+48h+arg_8]
0x18000599a  add     rsp, 40h
0x18000599e  pop     rdi
0x18000599f  retn
```
