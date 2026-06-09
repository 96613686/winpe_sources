# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18007ac70`
- end: `0x18007acc8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18007ac70`
- `0x180092010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18007ac9f`
- `KERNEL32!GetProcAddress` at `0x18007ac9f`
- `KERNEL32!GetModuleHandleW` at `0x18007ac8f`
- `KERNEL32!GetModuleHandleW` at `0x18007ac8f`

## string_xrefs

- `0x18007ac85`: `kernelbase.dll`

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
0x18007ac70  mov     [rsp+arg_0], rbx
0x18007ac75  mov     [rsp+arg_8], rsi
0x18007ac7a  push    rdi
0x18007ac7b  sub     rsp, 20h
0x18007ac7f  mov     rsi, rcx
0x18007ac82  mov     ebx, r8d
0x18007ac85  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18007ac8c  mov     rdi, rdx
0x18007ac8f  call    cs:__imp_GetModuleHandleW
0x18007ac95  mov     rcx, rax; hModule
0x18007ac98  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18007ac9f  call    cs:__imp_GetProcAddress
0x18007aca5  test    rax, rax
0x18007aca8  jz      short loc_18007ACB8
0x18007acaa  mov     r8d, ebx
0x18007acad  mov     rdx, rdi
0x18007acb0  mov     rcx, rsi
0x18007acb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007acb8  mov     rbx, [rsp+28h+arg_0]
0x18007acbd  mov     rsi, [rsp+28h+arg_8]
0x18007acc2  add     rsp, 20h
0x18007acc6  pop     rdi
0x18007acc7  retn
```
