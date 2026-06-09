# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004bd0`
- end: `0x180004c40`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004bd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004bfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004bfa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004c2a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004c2a`

## string_xrefs

- `0x180004bf3`: `ntdll.dll`

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
0x180004bd0  mov     [rsp+arg_0], rbx
0x180004bd5  mov     [rsp+arg_8], rsi
0x180004bda  push    rdi
0x180004bdb  sub     rsp, 40h
0x180004bdf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004be6  mov     ebx, r8d
0x180004be9  mov     rdi, rdx
0x180004bec  mov     esi, ecx
0x180004bee  test    rax, rax
0x180004bf1  jnz     short loc_180004C07
0x180004bf3  lea     rcx, ModuleName; "ntdll.dll"
0x180004bfa  call    cs:__imp_GetModuleHandleW
0x180004c00  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004c07  mov     [rsp+48h+Arguments], 0; Arguments
0x180004c10  mov     r9d, 400h; dwLanguageId
0x180004c16  mov     [rsp+48h+nSize], ebx; nSize
0x180004c1a  mov     r8d, esi; dwMessageId
0x180004c1d  mov     rdx, rax; lpSource
0x180004c20  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004c25  mov     ecx, 1A00h; dwFlags
0x180004c2a  call    cs:__imp_FormatMessageW
0x180004c30  mov     rbx, [rsp+48h+arg_0]
0x180004c35  mov     rsi, [rsp+48h+arg_8]
0x180004c3a  add     rsp, 40h
0x180004c3e  pop     rdi
0x180004c3f  retn
```
