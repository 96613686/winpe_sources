# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004630`
- end: `0x1800046a0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000465a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000465a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000468a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000468a`

## string_xrefs

- `0x180004653`: `ntdll.dll`

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
0x180004630  mov     [rsp+arg_0], rbx
0x180004635  mov     [rsp+arg_8], rsi
0x18000463a  push    rdi
0x18000463b  sub     rsp, 40h
0x18000463f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004646  mov     ebx, r8d
0x180004649  mov     rdi, rdx
0x18000464c  mov     esi, ecx
0x18000464e  test    rax, rax
0x180004651  jnz     short loc_180004667
0x180004653  lea     rcx, ModuleName; "ntdll.dll"
0x18000465a  call    cs:__imp_GetModuleHandleW
0x180004660  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004667  mov     [rsp+48h+Arguments], 0; Arguments
0x180004670  mov     r9d, 400h; dwLanguageId
0x180004676  mov     [rsp+48h+nSize], ebx; nSize
0x18000467a  mov     r8d, esi; dwMessageId
0x18000467d  mov     rdx, rax; lpSource
0x180004680  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004685  mov     ecx, 1A00h; dwFlags
0x18000468a  call    cs:__imp_FormatMessageW
0x180004690  mov     rbx, [rsp+48h+arg_0]
0x180004695  mov     rsi, [rsp+48h+arg_8]
0x18000469a  add     rsp, 40h
0x18000469e  pop     rdi
0x18000469f  retn
```
