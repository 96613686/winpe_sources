# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004b90`
- end: `0x180004c00`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004b90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004bba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004bba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004bea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004bea`

## string_xrefs

- `0x180004bb3`: `ntdll.dll`

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
0x180004b90  mov     [rsp+arg_0], rbx
0x180004b95  mov     [rsp+arg_8], rsi
0x180004b9a  push    rdi
0x180004b9b  sub     rsp, 40h
0x180004b9f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004ba6  mov     ebx, r8d
0x180004ba9  mov     rdi, rdx
0x180004bac  mov     esi, ecx
0x180004bae  test    rax, rax
0x180004bb1  jnz     short loc_180004BC7
0x180004bb3  lea     rcx, ModuleName; "ntdll.dll"
0x180004bba  call    cs:__imp_GetModuleHandleW
0x180004bc0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004bc7  mov     [rsp+48h+Arguments], 0; Arguments
0x180004bd0  mov     r9d, 400h; dwLanguageId
0x180004bd6  mov     [rsp+48h+nSize], ebx; nSize
0x180004bda  mov     r8d, esi; dwMessageId
0x180004bdd  mov     rdx, rax; lpSource
0x180004be0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004be5  mov     ecx, 1A00h; dwFlags
0x180004bea  call    cs:__imp_FormatMessageW
0x180004bf0  mov     rbx, [rsp+48h+arg_0]
0x180004bf5  mov     rsi, [rsp+48h+arg_8]
0x180004bfa  add     rsp, 40h
0x180004bfe  pop     rdi
0x180004bff  retn
```
