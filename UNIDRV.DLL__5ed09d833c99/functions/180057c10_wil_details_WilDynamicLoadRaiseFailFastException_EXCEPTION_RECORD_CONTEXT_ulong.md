# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180057c10`
- end: `0x180057c67`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180051e18`
- `0x180057c10`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180057c2f`
- `KERNEL32!GetModuleHandleW` at `0x180057c2f`

## string_xrefs

- `0x180057c25`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC Proc; // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  Proc = wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,unsigned long)>(ModuleHandleW);
  if ( Proc )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))Proc)(this, a2, v4);
}

```

## disassembly

```asm
0x180057c10  mov     [rsp+arg_0], rbx
0x180057c15  mov     [rsp+arg_8], rsi
0x180057c1a  push    rdi
0x180057c1b  sub     rsp, 20h
0x180057c1f  mov     rsi, rcx
0x180057c22  mov     ebx, r8d
0x180057c25  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180057c2c  mov     rdi, rdx
0x180057c2f  call    cs:__imp_GetModuleHandleW
0x180057c36  nop     dword ptr [rax+rax+00h]
0x180057c3b  mov     rcx, rax
0x180057c3e  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180057c43  test    rax, rax
0x180057c46  jz      short loc_180057C56
0x180057c48  mov     r8d, ebx
0x180057c4b  mov     rdx, rdi
0x180057c4e  mov     rcx, rsi
0x180057c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c56  mov     rbx, [rsp+28h+arg_0]
0x180057c5b  mov     rsi, [rsp+28h+arg_8]
0x180057c60  add     rsp, 20h
0x180057c64  pop     rdi
0x180057c65  retn
```
