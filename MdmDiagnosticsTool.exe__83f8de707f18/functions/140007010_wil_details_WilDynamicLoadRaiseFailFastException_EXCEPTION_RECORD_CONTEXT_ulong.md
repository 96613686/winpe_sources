# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140007010`
- end: `0x140007067`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400023b4`
- `0x140007010`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000702f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000702f`

## string_xrefs

- `0x140007025`: `kernelbase.dll`

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
0x140007010  mov     [rsp+arg_0], rbx
0x140007015  mov     [rsp+arg_8], rsi
0x14000701a  push    rdi
0x14000701b  sub     rsp, 20h
0x14000701f  mov     rsi, rcx
0x140007022  mov     ebx, r8d
0x140007025  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000702c  mov     rdi, rdx
0x14000702f  call    cs:__imp_GetModuleHandleW
0x140007036  nop     dword ptr [rax+rax+00h]
0x14000703b  mov     rcx, rax
0x14000703e  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x140007043  test    rax, rax
0x140007046  jz      short loc_140007056
0x140007048  mov     r8d, ebx
0x14000704b  mov     rdx, rdi
0x14000704e  mov     rcx, rsi
0x140007051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007056  mov     rbx, [rsp+28h+arg_0]
0x14000705b  mov     rsi, [rsp+28h+arg_8]
0x140007060  add     rsp, 20h
0x140007064  pop     rdi
0x140007065  retn
```
