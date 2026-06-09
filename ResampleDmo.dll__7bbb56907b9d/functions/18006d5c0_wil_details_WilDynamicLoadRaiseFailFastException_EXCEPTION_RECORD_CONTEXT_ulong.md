# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18006d5c0`
- end: `0x18006d610`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18006c450`
- `0x18006d5c0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006d5df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006d5df`

## string_xrefs

- `0x18006d5d5`: `kernelbase.dll`

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
0x18006d5c0  mov     [rsp+arg_0], rbx
0x18006d5c5  mov     [rsp+arg_8], rsi
0x18006d5ca  push    rdi
0x18006d5cb  sub     rsp, 20h
0x18006d5cf  mov     rsi, rcx
0x18006d5d2  mov     ebx, r8d
0x18006d5d5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18006d5dc  mov     rdi, rdx
0x18006d5df  call    cs:__imp_GetModuleHandleW
0x18006d5e5  mov     rcx, rax
0x18006d5e8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18006d5ed  test    rax, rax
0x18006d5f0  jz      short loc_18006D600
0x18006d5f2  mov     r8d, ebx
0x18006d5f5  mov     rdx, rdi
0x18006d5f8  mov     rcx, rsi
0x18006d5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d600  mov     rbx, [rsp+28h+arg_0]
0x18006d605  mov     rsi, [rsp+28h+arg_8]
0x18006d60a  add     rsp, 20h
0x18006d60e  pop     rdi
0x18006d60f  retn
```
