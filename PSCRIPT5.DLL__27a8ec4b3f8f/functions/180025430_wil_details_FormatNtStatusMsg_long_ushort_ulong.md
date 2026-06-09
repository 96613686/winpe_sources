# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180025430`
- end: `0x1800254ad`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180025430`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002545a`
- `KERNEL32!GetModuleHandleW` at `0x18002545a`
- `KERNEL32!FormatMessageW` at `0x180025490`
- `KERNEL32!FormatMessageW` at `0x180025490`

## string_xrefs

- `0x180025453`: `ntdll.dll`

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
0x180025430  mov     [rsp+arg_0], rbx
0x180025435  mov     [rsp+arg_8], rsi
0x18002543a  push    rdi
0x18002543b  sub     rsp, 40h
0x18002543f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025446  mov     ebx, r8d
0x180025449  mov     rdi, rdx
0x18002544c  mov     esi, ecx
0x18002544e  test    rax, rax
0x180025451  jnz     short loc_18002546D
0x180025453  lea     rcx, aNtdllDll; "ntdll.dll"
0x18002545a  call    cs:__imp_GetModuleHandleW
0x180025461  nop     dword ptr [rax+rax+00h]
0x180025466  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002546d  mov     [rsp+48h+Arguments], 0; Arguments
0x180025476  mov     r9d, 400h; dwLanguageId
0x18002547c  mov     [rsp+48h+nSize], ebx; nSize
0x180025480  mov     r8d, esi; dwMessageId
0x180025483  mov     rdx, rax; lpSource
0x180025486  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18002548b  mov     ecx, 1A00h; dwFlags
0x180025490  call    cs:__imp_FormatMessageW
0x180025497  nop     dword ptr [rax+rax+00h]
0x18002549c  mov     rbx, [rsp+48h+arg_0]
0x1800254a1  mov     rsi, [rsp+48h+arg_8]
0x1800254a6  add     rsp, 40h
0x1800254aa  pop     rdi
0x1800254ab  retn
```
