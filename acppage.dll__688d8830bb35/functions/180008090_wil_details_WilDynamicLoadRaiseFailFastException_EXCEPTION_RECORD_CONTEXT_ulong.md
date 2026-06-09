# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008090`
- end: `0x1800080e8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008090`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800080af`
- `KERNEL32!GetModuleHandleW` at `0x1800080af`
- `KERNEL32!GetProcAddress` at `0x1800080bf`
- `KERNEL32!GetProcAddress` at `0x1800080bf`

## string_xrefs

- `0x1800080a5`: `kernelbase.dll`

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
0x180008090  mov     [rsp+arg_0], rbx
0x180008095  mov     [rsp+arg_8], rsi
0x18000809a  push    rdi
0x18000809b  sub     rsp, 20h
0x18000809f  mov     rsi, rcx
0x1800080a2  mov     ebx, r8d
0x1800080a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800080ac  mov     rdi, rdx
0x1800080af  call    cs:__imp_GetModuleHandleW
0x1800080b5  mov     rcx, rax; hModule
0x1800080b8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800080bf  call    cs:__imp_GetProcAddress
0x1800080c5  test    rax, rax
0x1800080c8  jz      short loc_1800080D8
0x1800080ca  mov     r8d, ebx
0x1800080cd  mov     rdx, rdi
0x1800080d0  mov     rcx, rsi
0x1800080d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080d8  mov     rbx, [rsp+28h+arg_0]
0x1800080dd  mov     rsi, [rsp+28h+arg_8]
0x1800080e2  add     rsp, 20h
0x1800080e6  pop     rdi
0x1800080e7  retn
```
