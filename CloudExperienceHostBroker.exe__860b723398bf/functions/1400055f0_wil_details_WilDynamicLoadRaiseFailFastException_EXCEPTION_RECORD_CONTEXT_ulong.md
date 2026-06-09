# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1400055f0`
- end: `0x140005640`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000278c`
- `0x1400055f0`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000560f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000560f`

## string_xrefs

- `0x140005605`: `kernelbase.dll`

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
0x1400055f0  mov     [rsp+arg_0], rbx
0x1400055f5  mov     [rsp+arg_8], rsi
0x1400055fa  push    rdi
0x1400055fb  sub     rsp, 20h
0x1400055ff  mov     rsi, rcx
0x140005602  mov     ebx, r8d
0x140005605  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000560c  mov     rdi, rdx
0x14000560f  call    cs:__imp_GetModuleHandleW
0x140005615  mov     rcx, rax
0x140005618  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x14000561d  test    rax, rax
0x140005620  jz      short loc_140005630
0x140005622  mov     r8d, ebx
0x140005625  mov     rdx, rdi
0x140005628  mov     rcx, rsi
0x14000562b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005630  mov     rbx, [rsp+28h+arg_0]
0x140005635  mov     rsi, [rsp+28h+arg_8]
0x14000563a  add     rsp, 20h
0x14000563e  pop     rdi
0x14000563f  retn
```
