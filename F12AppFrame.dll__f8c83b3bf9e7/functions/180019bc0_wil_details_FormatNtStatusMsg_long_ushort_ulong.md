# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180019bc0`
- end: `0x180019c30`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180019bc0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180019bea`
- `KERNEL32!GetModuleHandleW` at `0x180019bea`
- `KERNEL32!FormatMessageW` at `0x180019c1a`
- `KERNEL32!FormatMessageW` at `0x180019c1a`

## string_xrefs

- `0x180019be3`: `ntdll.dll`

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
0x180019bc0  mov     [rsp+arg_0], rbx
0x180019bc5  mov     [rsp+arg_8], rsi
0x180019bca  push    rdi
0x180019bcb  sub     rsp, 40h
0x180019bcf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180019bd6  mov     ebx, r8d
0x180019bd9  mov     rdi, rdx
0x180019bdc  mov     esi, ecx
0x180019bde  test    rax, rax
0x180019be1  jnz     short loc_180019BF7
0x180019be3  lea     rcx, aNtdllDll; "ntdll.dll"
0x180019bea  call    cs:__imp_GetModuleHandleW
0x180019bf0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180019bf7  mov     [rsp+48h+Arguments], 0; Arguments
0x180019c00  mov     r9d, 400h; dwLanguageId
0x180019c06  mov     [rsp+48h+nSize], ebx; nSize
0x180019c0a  mov     r8d, esi; dwMessageId
0x180019c0d  mov     rdx, rax; lpSource
0x180019c10  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180019c15  mov     ecx, 1A00h; dwFlags
0x180019c1a  call    cs:__imp_FormatMessageW
0x180019c20  mov     rbx, [rsp+48h+arg_0]
0x180019c25  mov     rsi, [rsp+48h+arg_8]
0x180019c2a  add     rsp, 40h
0x180019c2e  pop     rdi
0x180019c2f  retn
```
