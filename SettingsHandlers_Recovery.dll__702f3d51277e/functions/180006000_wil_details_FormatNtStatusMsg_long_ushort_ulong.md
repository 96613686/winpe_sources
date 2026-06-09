# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180006000`
- end: `0x180006070`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006000`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000602a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000602a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000605a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000605a`

## string_xrefs

- `0x180006023`: `ntdll.dll`

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
0x180006000  mov     [rsp+arg_0], rbx
0x180006005  mov     [rsp+arg_8], rsi
0x18000600a  push    rdi
0x18000600b  sub     rsp, 40h
0x18000600f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006016  mov     ebx, r8d
0x180006019  mov     rdi, rdx
0x18000601c  mov     esi, ecx
0x18000601e  test    rax, rax
0x180006021  jnz     short loc_180006037
0x180006023  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000602a  call    cs:__imp_GetModuleHandleW
0x180006030  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006037  mov     [rsp+48h+Arguments], 0; Arguments
0x180006040  mov     r9d, 400h; dwLanguageId
0x180006046  mov     [rsp+48h+nSize], ebx; nSize
0x18000604a  mov     r8d, esi; dwMessageId
0x18000604d  mov     rdx, rax; lpSource
0x180006050  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180006055  mov     ecx, 1A00h; dwFlags
0x18000605a  call    cs:__imp_FormatMessageW
0x180006060  mov     rbx, [rsp+48h+arg_0]
0x180006065  mov     rsi, [rsp+48h+arg_8]
0x18000606a  add     rsp, 40h
0x18000606e  pop     rdi
0x18000606f  retn
```
