# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140007750`
- end: `0x1400077a0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400038ec`
- `0x140007750`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000776f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000776f`

## string_xrefs

- `0x140007765`: `kernelbase.dll`

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
0x140007750  mov     [rsp+arg_0], rbx
0x140007755  mov     [rsp+arg_8], rsi
0x14000775a  push    rdi
0x14000775b  sub     rsp, 20h
0x14000775f  mov     rsi, rcx
0x140007762  mov     ebx, r8d
0x140007765  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000776c  mov     rdi, rdx
0x14000776f  call    cs:__imp_GetModuleHandleW
0x140007775  mov     rcx, rax
0x140007778  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x14000777d  test    rax, rax
0x140007780  jz      short loc_140007790
0x140007782  mov     r8d, ebx
0x140007785  mov     rdx, rdi
0x140007788  mov     rcx, rsi
0x14000778b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007790  mov     rbx, [rsp+28h+arg_0]
0x140007795  mov     rsi, [rsp+28h+arg_8]
0x14000779a  add     rsp, 20h
0x14000779e  pop     rdi
0x14000779f  retn
```
