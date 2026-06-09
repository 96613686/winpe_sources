# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18003fe70`
- end: `0x18003fec0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003f058`
- `0x18003fe70`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003fe8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003fe8f`

## string_xrefs

- `0x18003fe85`: `kernelbase.dll`

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
0x18003fe70  mov     [rsp+arg_0], rbx
0x18003fe75  mov     [rsp+arg_8], rsi
0x18003fe7a  push    rdi
0x18003fe7b  sub     rsp, 20h
0x18003fe7f  mov     rsi, rcx
0x18003fe82  mov     ebx, r8d
0x18003fe85  lea     rcx, ModuleName; "kernelbase.dll"
0x18003fe8c  mov     rdi, rdx
0x18003fe8f  call    cs:__imp_GetModuleHandleW
0x18003fe95  mov     rcx, rax
0x18003fe98  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18003fe9d  test    rax, rax
0x18003fea0  jz      short loc_18003FEB0
0x18003fea2  mov     r8d, ebx
0x18003fea5  mov     rdx, rdi
0x18003fea8  mov     rcx, rsi
0x18003feab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003feb0  mov     rbx, [rsp+28h+arg_0]
0x18003feb5  mov     rsi, [rsp+28h+arg_8]
0x18003feba  add     rsp, 20h
0x18003febe  pop     rdi
0x18003febf  retn
```
