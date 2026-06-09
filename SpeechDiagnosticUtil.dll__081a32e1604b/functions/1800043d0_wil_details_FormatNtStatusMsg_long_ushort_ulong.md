# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800043d0`
- end: `0x18000444d`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800043d0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800043fa`
- `KERNEL32!GetModuleHandleW` at `0x1800043fa`
- `KERNEL32!FormatMessageW` at `0x180004430`
- `KERNEL32!FormatMessageW` at `0x180004430`

## string_xrefs

- `0x1800043f3`: `ntdll.dll`

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
0x1800043d0  mov     [rsp+arg_0], rbx
0x1800043d5  mov     [rsp+arg_8], rsi
0x1800043da  push    rdi
0x1800043db  sub     rsp, 40h
0x1800043df  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800043e6  mov     ebx, r8d
0x1800043e9  mov     rdi, rdx
0x1800043ec  mov     esi, ecx
0x1800043ee  test    rax, rax
0x1800043f1  jnz     short loc_18000440D
0x1800043f3  lea     rcx, ModuleName; "ntdll.dll"
0x1800043fa  call    cs:__imp_GetModuleHandleW
0x180004401  nop     dword ptr [rax+rax+00h]
0x180004406  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000440d  mov     [rsp+48h+Arguments], 0; Arguments
0x180004416  mov     r9d, 400h; dwLanguageId
0x18000441c  mov     [rsp+48h+nSize], ebx; nSize
0x180004420  mov     r8d, esi; dwMessageId
0x180004423  mov     rdx, rax; lpSource
0x180004426  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000442b  mov     ecx, 1A00h; dwFlags
0x180004430  call    cs:__imp_FormatMessageW
0x180004437  nop     dword ptr [rax+rax+00h]
0x18000443c  mov     rbx, [rsp+48h+arg_0]
0x180004441  mov     rsi, [rsp+48h+arg_8]
0x180004446  add     rsp, 40h
0x18000444a  pop     rdi
0x18000444b  retn
```
