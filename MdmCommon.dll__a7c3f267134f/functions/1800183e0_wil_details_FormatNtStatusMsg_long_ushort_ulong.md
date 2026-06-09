# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800183e0`
- end: `0x18001845d`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800183e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001840a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001840a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180018440`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180018440`

## string_xrefs

- `0x180018403`: `ntdll.dll`

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
0x1800183e0  mov     [rsp+arg_0], rbx
0x1800183e5  mov     [rsp+arg_8], rsi
0x1800183ea  push    rdi
0x1800183eb  sub     rsp, 40h
0x1800183ef  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800183f6  mov     ebx, r8d
0x1800183f9  mov     rdi, rdx
0x1800183fc  mov     esi, ecx
0x1800183fe  test    rax, rax
0x180018401  jnz     short loc_18001841D
0x180018403  lea     rcx, ModuleName; "ntdll.dll"
0x18001840a  call    cs:__imp_GetModuleHandleW
0x180018411  nop     dword ptr [rax+rax+00h]
0x180018416  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001841d  mov     [rsp+48h+Arguments], 0; Arguments
0x180018426  mov     r9d, 400h; dwLanguageId
0x18001842c  mov     [rsp+48h+nSize], ebx; nSize
0x180018430  mov     r8d, esi; dwMessageId
0x180018433  mov     rdx, rax; lpSource
0x180018436  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18001843b  mov     ecx, 1A00h; dwFlags
0x180018440  call    cs:__imp_FormatMessageW
0x180018447  nop     dword ptr [rax+rax+00h]
0x18001844c  mov     rbx, [rsp+48h+arg_0]
0x180018451  mov     rsi, [rsp+48h+arg_8]
0x180018456  add     rsp, 40h
0x18001845a  pop     rdi
0x18001845b  retn
```
