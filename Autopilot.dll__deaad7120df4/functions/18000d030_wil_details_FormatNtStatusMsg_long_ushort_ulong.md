# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18000d030`
- end: `0x18000d0ad`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d030`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d05a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d05a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000d090`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000d090`

## string_xrefs

- `0x18000d053`: `ntdll.dll`

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
0x18000d030  mov     [rsp+arg_0], rbx
0x18000d035  mov     [rsp+arg_8], rsi
0x18000d03a  push    rdi
0x18000d03b  sub     rsp, 40h
0x18000d03f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d046  mov     ebx, r8d
0x18000d049  mov     rdi, rdx
0x18000d04c  mov     esi, ecx
0x18000d04e  test    rax, rax
0x18000d051  jnz     short loc_18000D06D
0x18000d053  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000d05a  call    cs:__imp_GetModuleHandleW
0x18000d061  nop     dword ptr [rax+rax+00h]
0x18000d066  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d06d  mov     [rsp+48h+Arguments], 0; Arguments
0x18000d076  mov     r9d, 400h; dwLanguageId
0x18000d07c  mov     [rsp+48h+nSize], ebx; nSize
0x18000d080  mov     r8d, esi; dwMessageId
0x18000d083  mov     rdx, rax; lpSource
0x18000d086  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000d08b  mov     ecx, 1A00h; dwFlags
0x18000d090  call    cs:__imp_FormatMessageW
0x18000d097  nop     dword ptr [rax+rax+00h]
0x18000d09c  mov     rbx, [rsp+48h+arg_0]
0x18000d0a1  mov     rsi, [rsp+48h+arg_8]
0x18000d0a6  add     rsp, 40h
0x18000d0aa  pop     rdi
0x18000d0ab  retn
```
