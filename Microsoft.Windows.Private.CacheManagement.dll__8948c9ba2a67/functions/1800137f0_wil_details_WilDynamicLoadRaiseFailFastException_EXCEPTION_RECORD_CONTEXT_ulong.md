# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800137f0`
- end: `0x180013849`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `89`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800137f0`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001381f`
- `KERNEL32!GetProcAddress` at `0x18001381f`
- `KERNEL32!GetModuleHandleW` at `0x18001380f`
- `KERNEL32!GetModuleHandleW` at `0x18001380f`

## string_xrefs

- `0x180013805`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v4);
}

```

## disassembly

```asm
0x1800137f0  mov     [rsp+arg_0], rbx
0x1800137f5  mov     [rsp+arg_8], rsi
0x1800137fa  push    rdi
0x1800137fb  sub     rsp, 20h
0x1800137ff  mov     rsi, rcx
0x180013802  mov     ebx, r8d
0x180013805  lea     rcx, ModuleName; "kernelbase.dll"
0x18001380c  mov     rdi, rdx
0x18001380f  call    cs:__imp_GetModuleHandleW
0x180013815  mov     rcx, rax; hModule
0x180013818  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18001381f  call    cs:__imp_GetProcAddress
0x180013825  test    rax, rax
0x180013828  jz      short loc_180013839
0x18001382a  mov     r8d, ebx
0x18001382d  mov     rdx, rdi
0x180013830  mov     rcx, rsi
0x180013833  call    cs:__guard_dispatch_icall_fptr
0x180013839  mov     rbx, [rsp+28h+arg_0]
0x18001383e  mov     rsi, [rsp+28h+arg_8]
0x180013843  add     rsp, 20h
0x180013847  pop     rdi
0x180013848  retn
```
