# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14000e730`
- end: `0x14000e788`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000e730`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e74f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e74f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e75f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e75f`

## string_xrefs

- `0x14000e745`: `kernelbase.dll`

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
0x14000e730  mov     [rsp+arg_0], rbx
0x14000e735  mov     [rsp+arg_8], rsi
0x14000e73a  push    rdi
0x14000e73b  sub     rsp, 20h
0x14000e73f  mov     rsi, rcx
0x14000e742  mov     ebx, r8d
0x14000e745  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000e74c  mov     rdi, rdx
0x14000e74f  call    cs:__imp_GetModuleHandleW
0x14000e755  mov     rcx, rax; hModule
0x14000e758  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000e75f  call    cs:__imp_GetProcAddress
0x14000e765  test    rax, rax
0x14000e768  jz      short loc_14000E778
0x14000e76a  mov     r8d, ebx
0x14000e76d  mov     rdx, rdi
0x14000e770  mov     rcx, rsi
0x14000e773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e778  mov     rbx, [rsp+28h+arg_0]
0x14000e77d  mov     rsi, [rsp+28h+arg_8]
0x14000e782  add     rsp, 20h
0x14000e786  pop     rdi
0x14000e787  retn
```
