# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140009650`
- end: `0x1400096c0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140009650`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000967a`
- `KERNEL32!GetModuleHandleW` at `0x14000967a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400096aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400096aa`

## string_xrefs

- `0x140009673`: `ntdll.dll`

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
0x140009650  mov     [rsp+arg_0], rbx
0x140009655  mov     [rsp+arg_8], rsi
0x14000965a  push    rdi
0x14000965b  sub     rsp, 40h
0x14000965f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009666  mov     ebx, r8d
0x140009669  mov     rdi, rdx
0x14000966c  mov     esi, ecx
0x14000966e  test    rax, rax
0x140009671  jnz     short loc_140009687
0x140009673  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000967a  call    cs:__imp_GetModuleHandleW
0x140009680  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009687  mov     [rsp+48h+Arguments], 0; Arguments
0x140009690  mov     r9d, 400h; dwLanguageId
0x140009696  mov     [rsp+48h+nSize], ebx; nSize
0x14000969a  mov     r8d, esi; dwMessageId
0x14000969d  mov     rdx, rax; lpSource
0x1400096a0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1400096a5  mov     ecx, 1A00h; dwFlags
0x1400096aa  call    cs:__imp_FormatMessageW
0x1400096b0  mov     rbx, [rsp+48h+arg_0]
0x1400096b5  mov     rsi, [rsp+48h+arg_8]
0x1400096ba  add     rsp, 40h
0x1400096be  pop     rdi
0x1400096bf  retn
```
