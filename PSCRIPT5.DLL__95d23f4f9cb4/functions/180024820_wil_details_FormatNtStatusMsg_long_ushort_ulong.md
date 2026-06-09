# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180024820`
- end: `0x180024890`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180024820`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002484a`
- `KERNEL32!GetModuleHandleW` at `0x18002484a`
- `KERNEL32!FormatMessageW` at `0x18002487a`
- `KERNEL32!FormatMessageW` at `0x18002487a`

## string_xrefs

- `0x180024843`: `ntdll.dll`

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
0x180024820  mov     [rsp+arg_0], rbx
0x180024825  mov     [rsp+arg_8], rsi
0x18002482a  push    rdi
0x18002482b  sub     rsp, 40h
0x18002482f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180024836  mov     ebx, r8d
0x180024839  mov     rdi, rdx
0x18002483c  mov     esi, ecx
0x18002483e  test    rax, rax
0x180024841  jnz     short loc_180024857
0x180024843  lea     rcx, aNtdllDll; "ntdll.dll"
0x18002484a  call    cs:__imp_GetModuleHandleW
0x180024850  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180024857  mov     [rsp+48h+Arguments], 0; Arguments
0x180024860  mov     r9d, 400h; dwLanguageId
0x180024866  mov     [rsp+48h+nSize], ebx; nSize
0x18002486a  mov     r8d, esi; dwMessageId
0x18002486d  mov     rdx, rax; lpSource
0x180024870  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180024875  mov     ecx, 1A00h; dwFlags
0x18002487a  call    cs:__imp_FormatMessageW
0x180024880  mov     rbx, [rsp+48h+arg_0]
0x180024885  mov     rsi, [rsp+48h+arg_8]
0x18002488a  add     rsp, 40h
0x18002488e  pop     rdi
0x18002488f  retn
```
