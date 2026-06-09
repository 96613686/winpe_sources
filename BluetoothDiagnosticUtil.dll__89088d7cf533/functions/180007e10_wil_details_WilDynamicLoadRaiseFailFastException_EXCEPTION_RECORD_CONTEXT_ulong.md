# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180007e10`
- end: `0x180007e75`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007e10`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180007e45`
- `KERNEL32!GetProcAddress` at `0x180007e45`
- `KERNEL32!GetModuleHandleW` at `0x180007e2f`
- `KERNEL32!GetModuleHandleW` at `0x180007e2f`

## string_xrefs

- `0x180007e25`: `kernelbase.dll`

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
0x180007e10  mov     [rsp+arg_0], rbx
0x180007e15  mov     [rsp+arg_8], rsi
0x180007e1a  push    rdi
0x180007e1b  sub     rsp, 20h
0x180007e1f  mov     rsi, rcx
0x180007e22  mov     ebx, r8d
0x180007e25  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007e2c  mov     rdi, rdx
0x180007e2f  call    cs:__imp_GetModuleHandleW
0x180007e36  nop     dword ptr [rax+rax+00h]
0x180007e3b  mov     rcx, rax; hModule
0x180007e3e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180007e45  call    cs:__imp_GetProcAddress
0x180007e4c  nop     dword ptr [rax+rax+00h]
0x180007e51  test    rax, rax
0x180007e54  jz      short loc_180007E64
0x180007e56  mov     r8d, ebx
0x180007e59  mov     rdx, rdi
0x180007e5c  mov     rcx, rsi
0x180007e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e64  mov     rbx, [rsp+28h+arg_0]
0x180007e69  mov     rsi, [rsp+28h+arg_8]
0x180007e6e  add     rsp, 20h
0x180007e72  pop     rdi
0x180007e73  retn
```
