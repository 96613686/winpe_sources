# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18000cf80`
- end: `0x18000cff0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000cf80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cfaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cfaa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000cfda`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000cfda`

## string_xrefs

- `0x18000cfa3`: `ntdll.dll`

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
0x18000cf80  mov     [rsp+arg_0], rbx
0x18000cf85  mov     [rsp+arg_8], rsi
0x18000cf8a  push    rdi
0x18000cf8b  sub     rsp, 40h
0x18000cf8f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cf96  mov     ebx, r8d
0x18000cf99  mov     rdi, rdx
0x18000cf9c  mov     esi, ecx
0x18000cf9e  test    rax, rax
0x18000cfa1  jnz     short loc_18000CFB7
0x18000cfa3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000cfaa  call    cs:__imp_GetModuleHandleW
0x18000cfb0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cfb7  mov     [rsp+48h+Arguments], 0; Arguments
0x18000cfc0  mov     r9d, 400h; dwLanguageId
0x18000cfc6  mov     [rsp+48h+nSize], ebx; nSize
0x18000cfca  mov     r8d, esi; dwMessageId
0x18000cfcd  mov     rdx, rax; lpSource
0x18000cfd0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000cfd5  mov     ecx, 1A00h; dwFlags
0x18000cfda  call    cs:__imp_FormatMessageW
0x18000cfe0  mov     rbx, [rsp+48h+arg_0]
0x18000cfe5  mov     rsi, [rsp+48h+arg_8]
0x18000cfea  add     rsp, 40h
0x18000cfee  pop     rdi
0x18000cfef  retn
```
