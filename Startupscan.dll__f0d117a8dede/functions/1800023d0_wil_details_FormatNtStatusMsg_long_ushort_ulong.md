# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800023d0`
- end: `0x180002440`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800023d0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000242a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000242a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800023fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800023fa`

## string_xrefs

- `0x1800023f3`: `ntdll.dll`

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
0x1800023d0  mov     [rsp+arg_0], rbx
0x1800023d5  mov     [rsp+arg_8], rsi
0x1800023da  push    rdi
0x1800023db  sub     rsp, 40h
0x1800023df  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800023e6  mov     ebx, r8d
0x1800023e9  mov     rdi, rdx
0x1800023ec  mov     esi, ecx
0x1800023ee  test    rax, rax
0x1800023f1  jnz     short loc_180002407
0x1800023f3  lea     rcx, ModuleName; "ntdll.dll"
0x1800023fa  call    cs:__imp_GetModuleHandleW
0x180002400  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002407  mov     [rsp+48h+Arguments], 0; Arguments
0x180002410  mov     r9d, 400h; dwLanguageId
0x180002416  mov     [rsp+48h+nSize], ebx; nSize
0x18000241a  mov     r8d, esi; dwMessageId
0x18000241d  mov     rdx, rax; lpSource
0x180002420  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180002425  mov     ecx, 1A00h; dwFlags
0x18000242a  call    cs:__imp_FormatMessageW
0x180002430  mov     rbx, [rsp+48h+arg_0]
0x180002435  mov     rsi, [rsp+48h+arg_8]
0x18000243a  add     rsp, 40h
0x18000243e  pop     rdi
0x18000243f  retn
```
