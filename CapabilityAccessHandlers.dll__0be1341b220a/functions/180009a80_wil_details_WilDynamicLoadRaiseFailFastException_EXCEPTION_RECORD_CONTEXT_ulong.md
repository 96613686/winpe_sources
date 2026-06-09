# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180009a80`
- end: `0x180009ad0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005e3c`
- `0x180009a80`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009a9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009a9f`

## string_xrefs

- `0x180009a95`: `kernelbase.dll`

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
0x180009a80  mov     [rsp+arg_0], rbx
0x180009a85  mov     [rsp+arg_8], rsi
0x180009a8a  push    rdi
0x180009a8b  sub     rsp, 20h
0x180009a8f  mov     rsi, rcx
0x180009a92  mov     ebx, r8d
0x180009a95  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009a9c  mov     rdi, rdx
0x180009a9f  call    cs:__imp_GetModuleHandleW
0x180009aa5  mov     rcx, rax
0x180009aa8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180009aad  test    rax, rax
0x180009ab0  jz      short loc_180009AC0
0x180009ab2  mov     r8d, ebx
0x180009ab5  mov     rdx, rdi
0x180009ab8  mov     rcx, rsi
0x180009abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ac0  mov     rbx, [rsp+28h+arg_0]
0x180009ac5  mov     rsi, [rsp+28h+arg_8]
0x180009aca  add     rsp, 20h
0x180009ace  pop     rdi
0x180009acf  retn
```
