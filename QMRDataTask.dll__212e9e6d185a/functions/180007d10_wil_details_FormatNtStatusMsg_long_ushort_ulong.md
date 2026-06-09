# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180007d10`
- end: `0x180007d80`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180007d10`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180007d3a`
- `KERNEL32!GetModuleHandleW` at `0x180007d3a`
- `KERNEL32!FormatMessageW` at `0x180007d6a`
- `KERNEL32!FormatMessageW` at `0x180007d6a`

## string_xrefs

- `0x180007d33`: `ntdll.dll`

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
0x180007d10  mov     [rsp+arg_0], rbx
0x180007d15  mov     [rsp+arg_8], rsi
0x180007d1a  push    rdi
0x180007d1b  sub     rsp, 40h
0x180007d1f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007d26  mov     ebx, r8d
0x180007d29  mov     rdi, rdx
0x180007d2c  mov     esi, ecx
0x180007d2e  test    rax, rax
0x180007d31  jnz     short loc_180007D47
0x180007d33  lea     rcx, ModuleName; "ntdll.dll"
0x180007d3a  call    cs:__imp_GetModuleHandleW
0x180007d40  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007d47  mov     [rsp+48h+Arguments], 0; Arguments
0x180007d50  mov     r9d, 400h; dwLanguageId
0x180007d56  mov     [rsp+48h+nSize], ebx; nSize
0x180007d5a  mov     r8d, esi; dwMessageId
0x180007d5d  mov     rdx, rax; lpSource
0x180007d60  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180007d65  mov     ecx, 1A00h; dwFlags
0x180007d6a  call    cs:__imp_FormatMessageW
0x180007d70  mov     rbx, [rsp+48h+arg_0]
0x180007d75  mov     rsi, [rsp+48h+arg_8]
0x180007d7a  add     rsp, 40h
0x180007d7e  pop     rdi
0x180007d7f  retn
```
