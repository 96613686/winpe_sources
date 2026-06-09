# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004760`
- end: `0x1800047d0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004760`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000478a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000478a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800047ba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800047ba`

## string_xrefs

- `0x180004783`: `ntdll.dll`

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
0x180004760  mov     [rsp+arg_0], rbx
0x180004765  mov     [rsp+arg_8], rsi
0x18000476a  push    rdi
0x18000476b  sub     rsp, 40h
0x18000476f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004776  mov     ebx, r8d
0x180004779  mov     rdi, rdx
0x18000477c  mov     esi, ecx
0x18000477e  test    rax, rax
0x180004781  jnz     short loc_180004797
0x180004783  lea     rcx, ModuleName; "ntdll.dll"
0x18000478a  call    cs:__imp_GetModuleHandleW
0x180004790  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004797  mov     [rsp+48h+Arguments], 0; Arguments
0x1800047a0  mov     r9d, 400h; dwLanguageId
0x1800047a6  mov     [rsp+48h+nSize], ebx; nSize
0x1800047aa  mov     r8d, esi; dwMessageId
0x1800047ad  mov     rdx, rax; lpSource
0x1800047b0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800047b5  mov     ecx, 1A00h; dwFlags
0x1800047ba  call    cs:__imp_FormatMessageW
0x1800047c0  mov     rbx, [rsp+48h+arg_0]
0x1800047c5  mov     rsi, [rsp+48h+arg_8]
0x1800047ca  add     rsp, 40h
0x1800047ce  pop     rdi
0x1800047cf  retn
```
