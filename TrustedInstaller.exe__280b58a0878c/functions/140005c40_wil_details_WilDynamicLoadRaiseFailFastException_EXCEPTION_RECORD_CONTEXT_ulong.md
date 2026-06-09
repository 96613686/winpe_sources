# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140005c40`
- end: `0x140005c90`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400033e0`
- `0x140005c40`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140005c5f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140005c5f`

## string_xrefs

- `0x140005c55`: `kernelbase.dll`

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
0x140005c40  mov     [rsp+arg_0], rbx
0x140005c45  mov     [rsp+arg_8], rsi
0x140005c4a  push    rdi
0x140005c4b  sub     rsp, 20h
0x140005c4f  mov     rsi, rcx
0x140005c52  mov     ebx, r8d
0x140005c55  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140005c5c  mov     rdi, rdx
0x140005c5f  call    cs:__imp_GetModuleHandleW
0x140005c65  mov     rcx, rax
0x140005c68  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x140005c6d  test    rax, rax
0x140005c70  jz      short loc_140005C80
0x140005c72  mov     r8d, ebx
0x140005c75  mov     rdx, rdi
0x140005c78  mov     rcx, rsi
0x140005c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c80  mov     rbx, [rsp+28h+arg_0]
0x140005c85  mov     rsi, [rsp+28h+arg_8]
0x140005c8a  add     rsp, 20h
0x140005c8e  pop     rdi
0x140005c8f  retn
```
