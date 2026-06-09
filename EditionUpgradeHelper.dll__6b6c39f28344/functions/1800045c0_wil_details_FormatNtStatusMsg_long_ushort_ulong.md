# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800045c0`
- end: `0x180004630`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800045c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800045ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800045ea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000461a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000461a`

## string_xrefs

- `0x1800045e3`: `ntdll.dll`

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
0x1800045c0  mov     [rsp+arg_0], rbx
0x1800045c5  mov     [rsp+arg_8], rsi
0x1800045ca  push    rdi
0x1800045cb  sub     rsp, 40h
0x1800045cf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800045d6  mov     ebx, r8d
0x1800045d9  mov     rdi, rdx
0x1800045dc  mov     esi, ecx
0x1800045de  test    rax, rax
0x1800045e1  jnz     short loc_1800045F7
0x1800045e3  lea     rcx, ModuleName; "ntdll.dll"
0x1800045ea  call    cs:__imp_GetModuleHandleW
0x1800045f0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800045f7  mov     [rsp+48h+Arguments], 0; Arguments
0x180004600  mov     r9d, 400h; dwLanguageId
0x180004606  mov     [rsp+48h+nSize], ebx; nSize
0x18000460a  mov     r8d, esi; dwMessageId
0x18000460d  mov     rdx, rax; lpSource
0x180004610  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004615  mov     ecx, 1A00h; dwFlags
0x18000461a  call    cs:__imp_FormatMessageW
0x180004620  mov     rbx, [rsp+48h+arg_0]
0x180004625  mov     rsi, [rsp+48h+arg_8]
0x18000462a  add     rsp, 40h
0x18000462e  pop     rdi
0x18000462f  retn
```
