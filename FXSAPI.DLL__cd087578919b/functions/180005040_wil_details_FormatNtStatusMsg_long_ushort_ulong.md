# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005040`
- end: `0x1800050bd`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005040`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800050a0`
- `KERNEL32!FormatMessageW` at `0x1800050a0`
- `KERNEL32!GetModuleHandleW` at `0x18000506a`
- `KERNEL32!GetModuleHandleW` at `0x18000506a`

## string_xrefs

- `0x180005063`: `ntdll.dll`

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
0x180005040  mov     [rsp+arg_0], rbx
0x180005045  mov     [rsp+arg_8], rsi
0x18000504a  push    rdi
0x18000504b  sub     rsp, 40h
0x18000504f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005056  mov     ebx, r8d
0x180005059  mov     rdi, rdx
0x18000505c  mov     esi, ecx
0x18000505e  test    rax, rax
0x180005061  jnz     short loc_18000507D
0x180005063  lea     rcx, ModuleName; "ntdll.dll"
0x18000506a  call    cs:__imp_GetModuleHandleW
0x180005071  nop     dword ptr [rax+rax+00h]
0x180005076  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000507d  mov     [rsp+48h+Arguments], 0; Arguments
0x180005086  mov     r9d, 400h; dwLanguageId
0x18000508c  mov     [rsp+48h+nSize], ebx; nSize
0x180005090  mov     r8d, esi; dwMessageId
0x180005093  mov     rdx, rax; lpSource
0x180005096  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000509b  mov     ecx, 1A00h; dwFlags
0x1800050a0  call    cs:__imp_FormatMessageW
0x1800050a7  nop     dword ptr [rax+rax+00h]
0x1800050ac  mov     rbx, [rsp+48h+arg_0]
0x1800050b1  mov     rsi, [rsp+48h+arg_8]
0x1800050b6  add     rsp, 40h
0x1800050ba  pop     rdi
0x1800050bb  retn
```
