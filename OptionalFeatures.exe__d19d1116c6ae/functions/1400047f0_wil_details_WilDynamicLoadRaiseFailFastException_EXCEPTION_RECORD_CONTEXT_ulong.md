# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1400047f0`
- end: `0x140004848`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400047f0`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000481f`
- `KERNEL32!GetProcAddress` at `0x14000481f`
- `KERNEL32!GetModuleHandleW` at `0x14000480f`
- `KERNEL32!GetModuleHandleW` at `0x14000480f`

## string_xrefs

- `0x140004805`: `kernelbase.dll`

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
0x1400047f0  mov     [rsp+arg_0], rbx
0x1400047f5  mov     [rsp+arg_8], rsi
0x1400047fa  push    rdi
0x1400047fb  sub     rsp, 20h
0x1400047ff  mov     rsi, rcx
0x140004802  mov     ebx, r8d
0x140004805  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000480c  mov     rdi, rdx
0x14000480f  call    cs:__imp_GetModuleHandleW
0x140004815  mov     rcx, rax; hModule
0x140004818  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000481f  call    cs:__imp_GetProcAddress
0x140004825  test    rax, rax
0x140004828  jz      short loc_140004838
0x14000482a  mov     r8d, ebx
0x14000482d  mov     rdx, rdi
0x140004830  mov     rcx, rsi
0x140004833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004838  mov     rbx, [rsp+28h+arg_0]
0x14000483d  mov     rsi, [rsp+28h+arg_8]
0x140004842  add     rsp, 20h
0x140004846  pop     rdi
0x140004847  retn
```
