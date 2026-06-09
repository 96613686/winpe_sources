# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x180005f40`
- end: `0x180005fb0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005f40`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180005f9a`
- `KERNEL32!FormatMessageW` at `0x180005f9a`
- `KERNEL32!GetModuleHandleW` at `0x180005f6a`
- `KERNEL32!GetModuleHandleW` at `0x180005f6a`

## string_xrefs

- `0x180005f63`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180005f40  mov     [rsp+arg_0], rbx
0x180005f45  mov     [rsp+arg_8], rsi
0x180005f4a  push    rdi
0x180005f4b  sub     rsp, 40h
0x180005f4f  mov     ebx, r8d
0x180005f52  mov     rdi, rdx
0x180005f55  mov     esi, ecx
0x180005f57  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005f5e  test    rax, rax
0x180005f61  jnz     short loc_180005F77
0x180005f63  lea     rcx, ModuleName; "ntdll.dll"
0x180005f6a  call    cs:__imp_GetModuleHandleW
0x180005f70  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005f77  mov     [rsp+48h+Arguments], 0; Arguments
0x180005f80  mov     [rsp+48h+nSize], ebx; nSize
0x180005f84  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180005f89  mov     r9d, 400h; dwLanguageId
0x180005f8f  mov     r8d, esi; dwMessageId
0x180005f92  mov     rdx, rax; lpSource
0x180005f95  mov     ecx, 1A00h; dwFlags
0x180005f9a  call    cs:__imp_FormatMessageW
0x180005fa0  mov     rbx, [rsp+48h+arg_0]
0x180005fa5  mov     rsi, [rsp+48h+arg_8]
0x180005faa  add     rsp, 40h
0x180005fae  pop     rdi
0x180005faf  retn
```
