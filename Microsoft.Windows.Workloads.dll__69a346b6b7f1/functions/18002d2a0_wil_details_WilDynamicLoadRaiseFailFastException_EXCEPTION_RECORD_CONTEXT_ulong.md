# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18002d2a0`
- end: `0x18002d2f9`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `89`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002d2a0`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002d2bf`
- `KERNEL32!GetModuleHandleW` at `0x18002d2bf`
- `KERNEL32!GetProcAddress` at `0x18002d2cf`
- `KERNEL32!GetProcAddress` at `0x18002d2cf`

## string_xrefs

- `0x18002d2b5`: `kernelbase.dll`

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
0x18002d2a0  mov     [rsp+arg_0], rbx
0x18002d2a5  mov     [rsp+arg_8], rsi
0x18002d2aa  push    rdi
0x18002d2ab  sub     rsp, 20h
0x18002d2af  mov     rsi, rcx
0x18002d2b2  mov     ebx, r8d
0x18002d2b5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002d2bc  mov     rdi, rdx
0x18002d2bf  call    cs:__imp_GetModuleHandleW
0x18002d2c5  mov     rcx, rax; hModule
0x18002d2c8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18002d2cf  call    cs:__imp_GetProcAddress
0x18002d2d5  test    rax, rax
0x18002d2d8  jz      short loc_18002D2E9
0x18002d2da  mov     r8d, ebx
0x18002d2dd  mov     rdx, rdi
0x18002d2e0  mov     rcx, rsi
0x18002d2e3  call    cs:__guard_dispatch_icall_fptr
0x18002d2e9  mov     rbx, [rsp+28h+arg_0]
0x18002d2ee  mov     rsi, [rsp+28h+arg_8]
0x18002d2f3  add     rsp, 20h
0x18002d2f7  pop     rdi
0x18002d2f8  retn
```
