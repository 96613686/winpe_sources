# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140005780`
- end: `0x1400057f0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140005780`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1400057da`
- `KERNEL32!FormatMessageW` at `0x1400057da`
- `KERNEL32!GetModuleHandleW` at `0x1400057aa`
- `KERNEL32!GetModuleHandleW` at `0x1400057aa`

## string_xrefs

- `0x1400057a3`: `ntdll.dll`

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
0x140005780  mov     [rsp+arg_0], rbx
0x140005785  mov     [rsp+arg_8], rsi
0x14000578a  push    rdi
0x14000578b  sub     rsp, 40h
0x14000578f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005796  mov     ebx, r8d
0x140005799  mov     rdi, rdx
0x14000579c  mov     esi, ecx
0x14000579e  test    rax, rax
0x1400057a1  jnz     short loc_1400057B7
0x1400057a3  lea     rcx, ModuleName; "ntdll.dll"
0x1400057aa  call    cs:__imp_GetModuleHandleW
0x1400057b0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400057b7  mov     [rsp+48h+Arguments], 0; Arguments
0x1400057c0  mov     r9d, 400h; dwLanguageId
0x1400057c6  mov     [rsp+48h+nSize], ebx; nSize
0x1400057ca  mov     r8d, esi; dwMessageId
0x1400057cd  mov     rdx, rax; lpSource
0x1400057d0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1400057d5  mov     ecx, 1A00h; dwFlags
0x1400057da  call    cs:__imp_FormatMessageW
0x1400057e0  mov     rbx, [rsp+48h+arg_0]
0x1400057e5  mov     rsi, [rsp+48h+arg_8]
0x1400057ea  add     rsp, 40h
0x1400057ee  pop     rdi
0x1400057ef  retn
```
