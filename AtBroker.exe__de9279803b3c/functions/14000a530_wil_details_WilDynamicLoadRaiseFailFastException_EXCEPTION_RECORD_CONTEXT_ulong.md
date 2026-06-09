# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14000a530`
- end: `0x14000a588`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a530`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000a55f`
- `KERNEL32!GetProcAddress` at `0x14000a55f`
- `KERNEL32!GetModuleHandleW` at `0x14000a54f`
- `KERNEL32!GetModuleHandleW` at `0x14000a54f`

## string_xrefs

- `0x14000a545`: `kernelbase.dll`

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
0x14000a530  mov     [rsp+arg_0], rbx
0x14000a535  mov     [rsp+arg_8], rsi
0x14000a53a  push    rdi
0x14000a53b  sub     rsp, 20h
0x14000a53f  mov     rsi, rcx
0x14000a542  mov     ebx, r8d
0x14000a545  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000a54c  mov     rdi, rdx
0x14000a54f  call    cs:__imp_GetModuleHandleW
0x14000a555  mov     rcx, rax; hModule
0x14000a558  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000a55f  call    cs:__imp_GetProcAddress
0x14000a565  test    rax, rax
0x14000a568  jz      short loc_14000A578
0x14000a56a  mov     r8d, ebx
0x14000a56d  mov     rdx, rdi
0x14000a570  mov     rcx, rsi
0x14000a573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a578  mov     rbx, [rsp+28h+arg_0]
0x14000a57d  mov     rsi, [rsp+28h+arg_8]
0x14000a582  add     rsp, 20h
0x14000a586  pop     rdi
0x14000a587  retn
```
