# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005d30`
- end: `0x180005d87`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800021e8`
- `0x180005d30`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180005d4f`
- `KERNEL32!GetModuleHandleW` at `0x180005d4f`

## string_xrefs

- `0x180005d45`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  void (__fastcall *Proc)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD); // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  Proc = (void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,unsigned long)>(ModuleHandleW);
  if ( Proc )
    Proc(this, a2, v4);
}

```

## disassembly

```asm
0x180005d30  mov     [rsp+arg_0], rbx
0x180005d35  mov     [rsp+arg_8], rsi
0x180005d3a  push    rdi
0x180005d3b  sub     rsp, 20h
0x180005d3f  mov     rsi, rcx
0x180005d42  mov     ebx, r8d
0x180005d45  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005d4c  mov     rdi, rdx
0x180005d4f  call    cs:__imp_GetModuleHandleW
0x180005d56  nop     dword ptr [rax+rax+00h]
0x180005d5b  mov     rcx, rax
0x180005d5e  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180005d63  test    rax, rax
0x180005d66  jz      short loc_180005D76
0x180005d68  mov     r8d, ebx
0x180005d6b  mov     rdx, rdi
0x180005d6e  mov     rcx, rsi
0x180005d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d76  mov     rbx, [rsp+28h+arg_0]
0x180005d7b  mov     rsi, [rsp+28h+arg_8]
0x180005d80  add     rsp, 20h
0x180005d84  pop     rdi
0x180005d85  retn
```
