# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180009910`
- end: `0x180009967`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003778`
- `0x180009910`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000992f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000992f`

## string_xrefs

- `0x180009925`: `kernelbase.dll`

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
0x180009910  mov     [rsp+arg_0], rbx
0x180009915  mov     [rsp+arg_8], rsi
0x18000991a  push    rdi
0x18000991b  sub     rsp, 20h
0x18000991f  mov     rsi, rcx
0x180009922  mov     ebx, r8d
0x180009925  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000992c  mov     rdi, rdx
0x18000992f  call    cs:__imp_GetModuleHandleW
0x180009936  nop     dword ptr [rax+rax+00h]
0x18000993b  mov     rcx, rax
0x18000993e  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180009943  test    rax, rax
0x180009946  jz      short loc_180009956
0x180009948  mov     r8d, ebx
0x18000994b  mov     rdx, rdi
0x18000994e  mov     rcx, rsi
0x180009951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009956  mov     rbx, [rsp+28h+arg_0]
0x18000995b  mov     rsi, [rsp+28h+arg_8]
0x180009960  add     rsp, 20h
0x180009964  pop     rdi
0x180009965  retn
```
