# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180022360`
- end: `0x1800223b0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001c2f0`
- `0x180022360`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002237f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002237f`

## string_xrefs

- `0x180022375`: `kernelbase.dll`

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
0x180022360  mov     [rsp+arg_0], rbx
0x180022365  mov     [rsp+arg_8], rsi
0x18002236a  push    rdi
0x18002236b  sub     rsp, 20h
0x18002236f  mov     rsi, rcx
0x180022372  mov     ebx, r8d
0x180022375  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002237c  mov     rdi, rdx
0x18002237f  call    cs:__imp_GetModuleHandleW
0x180022385  mov     rcx, rax
0x180022388  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18002238d  test    rax, rax
0x180022390  jz      short loc_1800223A0
0x180022392  mov     r8d, ebx
0x180022395  mov     rdx, rdi
0x180022398  mov     rcx, rsi
0x18002239b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223a0  mov     rbx, [rsp+28h+arg_0]
0x1800223a5  mov     rsi, [rsp+28h+arg_8]
0x1800223aa  add     rsp, 20h
0x1800223ae  pop     rdi
0x1800223af  retn
```
