# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140004e80`
- end: `0x140004ef0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140004e80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004eaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004eaa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004eda`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004eda`

## string_xrefs

- `0x140004ea3`: `ntdll.dll`

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
0x140004e80  mov     [rsp+arg_0], rbx
0x140004e85  mov     [rsp+arg_8], rsi
0x140004e8a  push    rdi
0x140004e8b  sub     rsp, 40h
0x140004e8f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004e96  mov     ebx, r8d
0x140004e99  mov     rdi, rdx
0x140004e9c  mov     esi, ecx
0x140004e9e  test    rax, rax
0x140004ea1  jnz     short loc_140004EB7
0x140004ea3  lea     rcx, ModuleName; "ntdll.dll"
0x140004eaa  call    cs:__imp_GetModuleHandleW
0x140004eb0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004eb7  mov     [rsp+48h+Arguments], 0; Arguments
0x140004ec0  mov     r9d, 400h; dwLanguageId
0x140004ec6  mov     [rsp+48h+nSize], ebx; nSize
0x140004eca  mov     r8d, esi; dwMessageId
0x140004ecd  mov     rdx, rax; lpSource
0x140004ed0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140004ed5  mov     ecx, 1A00h; dwFlags
0x140004eda  call    cs:__imp_FormatMessageW
0x140004ee0  mov     rbx, [rsp+48h+arg_0]
0x140004ee5  mov     rsi, [rsp+48h+arg_8]
0x140004eea  add     rsp, 40h
0x140004eee  pop     rdi
0x140004eef  retn
```
