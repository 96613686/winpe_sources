# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140001ad0`
- end: `0x140001b28`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001ad0`
- `0x14000f4d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140001aff`
- `KERNEL32!GetProcAddress` at `0x140001aff`
- `KERNEL32!GetModuleHandleW` at `0x140001aef`
- `KERNEL32!GetModuleHandleW` at `0x140001aef`

## string_xrefs

- `0x140001ae5`: `kernelbase.dll`

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
0x140001ad0  mov     [rsp+arg_0], rbx
0x140001ad5  mov     [rsp+arg_8], rsi
0x140001ada  push    rdi
0x140001adb  sub     rsp, 20h
0x140001adf  mov     rsi, rcx
0x140001ae2  mov     ebx, r8d
0x140001ae5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140001aec  mov     rdi, rdx
0x140001aef  call    cs:__imp_GetModuleHandleW
0x140001af5  mov     rcx, rax; hModule
0x140001af8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x140001aff  call    cs:__imp_GetProcAddress
0x140001b05  test    rax, rax
0x140001b08  jz      short loc_140001B18
0x140001b0a  mov     r8d, ebx
0x140001b0d  mov     rdx, rdi
0x140001b10  mov     rcx, rsi
0x140001b13  call    _guard_dispatch_icall
0x140001b18  mov     rbx, [rsp+28h+arg_0]
0x140001b1d  mov     rsi, [rsp+28h+arg_8]
0x140001b22  add     rsp, 20h
0x140001b26  pop     rdi
0x140001b27  retn
```
