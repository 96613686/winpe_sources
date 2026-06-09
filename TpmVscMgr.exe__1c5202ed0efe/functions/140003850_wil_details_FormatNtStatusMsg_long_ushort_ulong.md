# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140003850`
- end: `0x1400038c0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003850`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1400038aa`
- `KERNEL32!FormatMessageW` at `0x1400038aa`
- `KERNEL32!GetModuleHandleW` at `0x14000387a`
- `KERNEL32!GetModuleHandleW` at `0x14000387a`

## string_xrefs

- `0x140003873`: `ntdll.dll`

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
0x140003850  mov     [rsp+arg_0], rbx
0x140003855  mov     [rsp+arg_8], rsi
0x14000385a  push    rdi
0x14000385b  sub     rsp, 40h
0x14000385f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003866  mov     ebx, r8d
0x140003869  mov     rdi, rdx
0x14000386c  mov     esi, ecx
0x14000386e  test    rax, rax
0x140003871  jnz     short loc_140003887
0x140003873  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000387a  call    cs:__imp_GetModuleHandleW
0x140003880  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003887  mov     [rsp+48h+Arguments], 0; Arguments
0x140003890  mov     r9d, 400h; dwLanguageId
0x140003896  mov     [rsp+48h+nSize], ebx; nSize
0x14000389a  mov     r8d, esi; dwMessageId
0x14000389d  mov     rdx, rax; lpSource
0x1400038a0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1400038a5  mov     ecx, 1A00h; dwFlags
0x1400038aa  call    cs:__imp_FormatMessageW
0x1400038b0  mov     rbx, [rsp+48h+arg_0]
0x1400038b5  mov     rsi, [rsp+48h+arg_8]
0x1400038ba  add     rsp, 40h
0x1400038be  pop     rdi
0x1400038bf  retn
```
