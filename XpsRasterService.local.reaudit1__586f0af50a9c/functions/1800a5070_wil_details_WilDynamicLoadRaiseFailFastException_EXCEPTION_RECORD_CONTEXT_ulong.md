# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800a5070`
- end: `0x1800a50c0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800a1ac8`
- `0x1800a5070`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a508f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a508f`

## string_xrefs

- `0x1800a5085`: `kernelbase.dll`

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
0x1800a5070  mov     [rsp+arg_0], rbx
0x1800a5075  mov     [rsp+arg_8], rsi
0x1800a507a  push    rdi
0x1800a507b  sub     rsp, 20h
0x1800a507f  mov     rsi, rcx
0x1800a5082  mov     ebx, r8d
0x1800a5085  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800a508c  mov     rdi, rdx
0x1800a508f  call    cs:__imp_GetModuleHandleW
0x1800a5095  mov     rcx, rax
0x1800a5098  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800a509d  test    rax, rax
0x1800a50a0  jz      short loc_1800A50B0
0x1800a50a2  mov     r8d, ebx
0x1800a50a5  mov     rdx, rdi
0x1800a50a8  mov     rcx, rsi
0x1800a50ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a50b0  mov     rbx, [rsp+28h+arg_0]
0x1800a50b5  mov     rsi, [rsp+28h+arg_8]
0x1800a50ba  add     rsp, 20h
0x1800a50be  pop     rdi
0x1800a50bf  retn
```
