# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180001c90`
- end: `0x180001d0d`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c90`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180001cf0`
- `KERNEL32!FormatMessageW` at `0x180001cf0`
- `KERNEL32!GetModuleHandleW` at `0x180001cba`
- `KERNEL32!GetModuleHandleW` at `0x180001cba`

## string_xrefs

- `0x180001cb3`: `ntdll.dll`

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
0x180001c90  mov     [rsp+arg_0], rbx
0x180001c95  mov     [rsp+arg_8], rsi
0x180001c9a  push    rdi
0x180001c9b  sub     rsp, 40h
0x180001c9f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180001ca6  mov     ebx, r8d
0x180001ca9  mov     rdi, rdx
0x180001cac  mov     esi, ecx
0x180001cae  test    rax, rax
0x180001cb1  jnz     short loc_180001CCD
0x180001cb3  lea     rcx, ModuleName; "ntdll.dll"
0x180001cba  call    cs:__imp_GetModuleHandleW
0x180001cc1  nop     dword ptr [rax+rax+00h]
0x180001cc6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180001ccd  mov     [rsp+48h+Arguments], 0; Arguments
0x180001cd6  mov     r9d, 400h; dwLanguageId
0x180001cdc  mov     [rsp+48h+nSize], ebx; nSize
0x180001ce0  mov     r8d, esi; dwMessageId
0x180001ce3  mov     rdx, rax; lpSource
0x180001ce6  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180001ceb  mov     ecx, 1A00h; dwFlags
0x180001cf0  call    cs:__imp_FormatMessageW
0x180001cf7  nop     dword ptr [rax+rax+00h]
0x180001cfc  mov     rbx, [rsp+48h+arg_0]
0x180001d01  mov     rsi, [rsp+48h+arg_8]
0x180001d06  add     rsp, 40h
0x180001d0a  pop     rdi
0x180001d0b  retn
```
