# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140005a70`
- end: `0x140005ac8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005a70`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140005a9f`
- `KERNEL32!GetProcAddress` at `0x140005a9f`
- `KERNEL32!GetModuleHandleW` at `0x140005a8f`
- `KERNEL32!GetModuleHandleW` at `0x140005a8f`

## string_xrefs

- `0x140005a85`: `kernelbase.dll`

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
0x140005a70  mov     [rsp+arg_0], rbx
0x140005a75  mov     [rsp+arg_8], rsi
0x140005a7a  push    rdi
0x140005a7b  sub     rsp, 20h
0x140005a7f  mov     rsi, rcx
0x140005a82  mov     ebx, r8d
0x140005a85  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140005a8c  mov     rdi, rdx
0x140005a8f  call    cs:__imp_GetModuleHandleW
0x140005a95  mov     rcx, rax; hModule
0x140005a98  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x140005a9f  call    cs:__imp_GetProcAddress
0x140005aa5  test    rax, rax
0x140005aa8  jz      short loc_140005AB8
0x140005aaa  mov     r8d, ebx
0x140005aad  mov     rdx, rdi
0x140005ab0  mov     rcx, rsi
0x140005ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ab8  mov     rbx, [rsp+28h+arg_0]
0x140005abd  mov     rsi, [rsp+28h+arg_8]
0x140005ac2  add     rsp, 20h
0x140005ac6  pop     rdi
0x140005ac7  retn
```
