# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180001db0`
- end: `0x180001e20`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001db0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001dda`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001dda`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180001e0a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180001e0a`

## string_xrefs

- `0x180001dd3`: `ntdll.dll`

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
0x180001db0  mov     [rsp+arg_0], rbx
0x180001db5  mov     [rsp+arg_8], rsi
0x180001dba  push    rdi
0x180001dbb  sub     rsp, 40h
0x180001dbf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180001dc6  mov     ebx, r8d
0x180001dc9  mov     rdi, rdx
0x180001dcc  mov     esi, ecx
0x180001dce  test    rax, rax
0x180001dd1  jnz     short loc_180001DE7
0x180001dd3  lea     rcx, ModuleName; "ntdll.dll"
0x180001dda  call    cs:__imp_GetModuleHandleW
0x180001de0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180001de7  mov     [rsp+48h+Arguments], 0; Arguments
0x180001df0  mov     r9d, 400h; dwLanguageId
0x180001df6  mov     [rsp+48h+nSize], ebx; nSize
0x180001dfa  mov     r8d, esi; dwMessageId
0x180001dfd  mov     rdx, rax; lpSource
0x180001e00  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180001e05  mov     ecx, 1A00h; dwFlags
0x180001e0a  call    cs:__imp_FormatMessageW
0x180001e10  mov     rbx, [rsp+48h+arg_0]
0x180001e15  mov     rsi, [rsp+48h+arg_8]
0x180001e1a  add     rsp, 40h
0x180001e1e  pop     rdi
0x180001e1f  retn
```
