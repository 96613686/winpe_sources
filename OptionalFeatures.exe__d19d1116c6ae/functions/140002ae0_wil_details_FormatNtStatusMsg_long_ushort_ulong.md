# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140002ae0`
- end: `0x140002b50`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002ae0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140002b3a`
- `KERNEL32!FormatMessageW` at `0x140002b3a`
- `KERNEL32!GetModuleHandleW` at `0x140002b0a`
- `KERNEL32!GetModuleHandleW` at `0x140002b0a`

## string_xrefs

- `0x140002b03`: `ntdll.dll`

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
0x140002ae0  mov     [rsp+arg_0], rbx
0x140002ae5  mov     [rsp+arg_8], rsi
0x140002aea  push    rdi
0x140002aeb  sub     rsp, 40h
0x140002aef  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140002af6  mov     ebx, r8d
0x140002af9  mov     rdi, rdx
0x140002afc  mov     esi, ecx
0x140002afe  test    rax, rax
0x140002b01  jnz     short loc_140002B17
0x140002b03  lea     rcx, ModuleName; "ntdll.dll"
0x140002b0a  call    cs:__imp_GetModuleHandleW
0x140002b10  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140002b17  mov     [rsp+48h+Arguments], 0; Arguments
0x140002b20  mov     r9d, 400h; dwLanguageId
0x140002b26  mov     [rsp+48h+nSize], ebx; nSize
0x140002b2a  mov     r8d, esi; dwMessageId
0x140002b2d  mov     rdx, rax; lpSource
0x140002b30  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140002b35  mov     ecx, 1A00h; dwFlags
0x140002b3a  call    cs:__imp_FormatMessageW
0x140002b40  mov     rbx, [rsp+48h+arg_0]
0x140002b45  mov     rsi, [rsp+48h+arg_8]
0x140002b4a  add     rsp, 40h
0x140002b4e  pop     rdi
0x140002b4f  retn
```
