# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180003d00`
- end: `0x180003d7d`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003d00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003d2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003d2a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003d60`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003d60`

## string_xrefs

- `0x180003d23`: `ntdll.dll`

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
0x180003d00  mov     [rsp+arg_0], rbx
0x180003d05  mov     [rsp+arg_8], rsi
0x180003d0a  push    rdi
0x180003d0b  sub     rsp, 40h
0x180003d0f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003d16  mov     ebx, r8d
0x180003d19  mov     rdi, rdx
0x180003d1c  mov     esi, ecx
0x180003d1e  test    rax, rax
0x180003d21  jnz     short loc_180003D3D
0x180003d23  lea     rcx, ModuleName; "ntdll.dll"
0x180003d2a  call    cs:__imp_GetModuleHandleW
0x180003d31  nop     dword ptr [rax+rax+00h]
0x180003d36  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003d3d  mov     [rsp+48h+Arguments], 0; Arguments
0x180003d46  mov     r9d, 400h; dwLanguageId
0x180003d4c  mov     [rsp+48h+nSize], ebx; nSize
0x180003d50  mov     r8d, esi; dwMessageId
0x180003d53  mov     rdx, rax; lpSource
0x180003d56  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180003d5b  mov     ecx, 1A00h; dwFlags
0x180003d60  call    cs:__imp_FormatMessageW
0x180003d67  nop     dword ptr [rax+rax+00h]
0x180003d6c  mov     rbx, [rsp+48h+arg_0]
0x180003d71  mov     rsi, [rsp+48h+arg_8]
0x180003d76  add     rsp, 40h
0x180003d7a  pop     rdi
0x180003d7b  retn
```
