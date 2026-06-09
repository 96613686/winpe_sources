# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180003800`
- end: `0x180003870`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003800`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000382a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000382a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000385a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000385a`

## string_xrefs

- `0x180003823`: `ntdll.dll`

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
0x180003800  mov     [rsp+arg_0], rbx
0x180003805  mov     [rsp+arg_8], rsi
0x18000380a  push    rdi
0x18000380b  sub     rsp, 40h
0x18000380f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003816  mov     ebx, r8d
0x180003819  mov     rdi, rdx
0x18000381c  mov     esi, ecx
0x18000381e  test    rax, rax
0x180003821  jnz     short loc_180003837
0x180003823  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000382a  call    cs:__imp_GetModuleHandleW
0x180003830  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003837  mov     [rsp+48h+Arguments], 0; Arguments
0x180003840  mov     r9d, 400h; dwLanguageId
0x180003846  mov     [rsp+48h+nSize], ebx; nSize
0x18000384a  mov     r8d, esi; dwMessageId
0x18000384d  mov     rdx, rax; lpSource
0x180003850  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180003855  mov     ecx, 1A00h; dwFlags
0x18000385a  call    cs:__imp_FormatMessageW
0x180003860  mov     rbx, [rsp+48h+arg_0]
0x180003865  mov     rsi, [rsp+48h+arg_8]
0x18000386a  add     rsp, 40h
0x18000386e  pop     rdi
0x18000386f  retn
```
