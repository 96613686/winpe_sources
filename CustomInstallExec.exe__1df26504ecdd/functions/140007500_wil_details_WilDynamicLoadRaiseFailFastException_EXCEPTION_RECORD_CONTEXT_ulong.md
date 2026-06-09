# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140007500`
- end: `0x140007550`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004890`
- `0x140007500`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000751f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000751f`

## string_xrefs

- `0x140007515`: `kernelbase.dll`

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
0x140007500  mov     [rsp+arg_0], rbx
0x140007505  mov     [rsp+arg_8], rsi
0x14000750a  push    rdi
0x14000750b  sub     rsp, 20h
0x14000750f  mov     rsi, rcx
0x140007512  mov     ebx, r8d
0x140007515  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000751c  mov     rdi, rdx
0x14000751f  call    cs:__imp_GetModuleHandleW
0x140007525  mov     rcx, rax
0x140007528  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x14000752d  test    rax, rax
0x140007530  jz      short loc_140007540
0x140007532  mov     r8d, ebx
0x140007535  mov     rdx, rdi
0x140007538  mov     rcx, rsi
0x14000753b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007540  mov     rbx, [rsp+28h+arg_0]
0x140007545  mov     rsi, [rsp+28h+arg_8]
0x14000754a  add     rsp, 20h
0x14000754e  pop     rdi
0x14000754f  retn
```
