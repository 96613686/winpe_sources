# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000a260`
- end: `0x18000a2b8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a260`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a28f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a28f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a27f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a27f`

## string_xrefs

- `0x18000a275`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v4);
}

```

## disassembly

```asm
0x18000a260  mov     [rsp+arg_0], rbx
0x18000a265  mov     [rsp+arg_8], rsi
0x18000a26a  push    rdi
0x18000a26b  sub     rsp, 20h
0x18000a26f  mov     rsi, rcx
0x18000a272  mov     ebx, r8d
0x18000a275  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a27c  mov     rdi, rdx
0x18000a27f  call    cs:__imp_GetModuleHandleW
0x18000a285  mov     rcx, rax; hModule
0x18000a288  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000a28f  call    cs:__imp_GetProcAddress
0x18000a295  test    rax, rax
0x18000a298  jz      short loc_18000A2A8
0x18000a29a  mov     r8d, ebx
0x18000a29d  mov     rdx, rdi
0x18000a2a0  mov     rcx, rsi
0x18000a2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2a8  mov     rbx, [rsp+28h+arg_0]
0x18000a2ad  mov     rsi, [rsp+28h+arg_8]
0x18000a2b2  add     rsp, 20h
0x18000a2b6  pop     rdi
0x18000a2b7  retn
```
