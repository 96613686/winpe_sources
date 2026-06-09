# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140006160`
- end: `0x1400061b8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140006160`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000617f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000617f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000618f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000618f`

## string_xrefs

- `0x140006175`: `kernelbase.dll`

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
0x140006160  mov     [rsp+arg_0], rbx
0x140006165  mov     [rsp+arg_8], rsi
0x14000616a  push    rdi
0x14000616b  sub     rsp, 20h
0x14000616f  mov     rsi, rcx
0x140006172  mov     ebx, r8d
0x140006175  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000617c  mov     rdi, rdx
0x14000617f  call    cs:__imp_GetModuleHandleW
0x140006185  mov     rcx, rax; hModule
0x140006188  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000618f  call    cs:__imp_GetProcAddress
0x140006195  test    rax, rax
0x140006198  jz      short loc_1400061A8
0x14000619a  mov     r8d, ebx
0x14000619d  mov     rdx, rdi
0x1400061a0  mov     rcx, rsi
0x1400061a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400061a8  mov     rbx, [rsp+28h+arg_0]
0x1400061ad  mov     rsi, [rsp+28h+arg_8]
0x1400061b2  add     rsp, 20h
0x1400061b6  pop     rdi
0x1400061b7  retn
```
