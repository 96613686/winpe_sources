# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140008830`
- end: `0x1400088a0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140008830`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000885a`
- `KERNEL32!GetModuleHandleW` at `0x14000885a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000888a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000888a`

## string_xrefs

- `0x140008853`: `ntdll.dll`

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
0x140008830  mov     [rsp+arg_0], rbx
0x140008835  mov     [rsp+arg_8], rsi
0x14000883a  push    rdi
0x14000883b  sub     rsp, 40h
0x14000883f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008846  mov     ebx, r8d
0x140008849  mov     rdi, rdx
0x14000884c  mov     esi, ecx
0x14000884e  test    rax, rax
0x140008851  jnz     short loc_140008867
0x140008853  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000885a  call    cs:__imp_GetModuleHandleW
0x140008860  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008867  mov     [rsp+48h+Arguments], 0; Arguments
0x140008870  mov     r9d, 400h; dwLanguageId
0x140008876  mov     [rsp+48h+nSize], ebx; nSize
0x14000887a  mov     r8d, esi; dwMessageId
0x14000887d  mov     rdx, rax; lpSource
0x140008880  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140008885  mov     ecx, 1A00h; dwFlags
0x14000888a  call    cs:__imp_FormatMessageW
0x140008890  mov     rbx, [rsp+48h+arg_0]
0x140008895  mov     rsi, [rsp+48h+arg_8]
0x14000889a  add     rsp, 40h
0x14000889e  pop     rdi
0x14000889f  retn
```
