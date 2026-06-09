# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x140002ca0`
- end: `0x140002d10`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002ca0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140002cfa`
- `KERNEL32!FormatMessageW` at `0x140002cfa`
- `KERNEL32!GetModuleHandleW` at `0x140002cca`
- `KERNEL32!GetModuleHandleW` at `0x140002cca`

## string_xrefs

- `0x140002cc3`: `ntdll.dll`

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
0x140002ca0  mov     [rsp+arg_0], rbx
0x140002ca5  mov     [rsp+arg_8], rsi
0x140002caa  push    rdi
0x140002cab  sub     rsp, 40h
0x140002caf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140002cb6  mov     ebx, r8d
0x140002cb9  mov     rdi, rdx
0x140002cbc  mov     esi, ecx
0x140002cbe  test    rax, rax
0x140002cc1  jnz     short loc_140002CD7
0x140002cc3  lea     rcx, ModuleName; "ntdll.dll"
0x140002cca  call    cs:__imp_GetModuleHandleW
0x140002cd0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140002cd7  mov     [rsp+48h+Arguments], 0; Arguments
0x140002ce0  mov     r9d, 400h; dwLanguageId
0x140002ce6  mov     [rsp+48h+nSize], ebx; nSize
0x140002cea  mov     r8d, esi; dwMessageId
0x140002ced  mov     rdx, rax; lpSource
0x140002cf0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140002cf5  mov     ecx, 1A00h; dwFlags
0x140002cfa  call    cs:__imp_FormatMessageW
0x140002d00  mov     rbx, [rsp+48h+arg_0]
0x140002d05  mov     rsi, [rsp+48h+arg_8]
0x140002d0a  add     rsp, 40h
0x140002d0e  pop     rdi
0x140002d0f  retn
```
