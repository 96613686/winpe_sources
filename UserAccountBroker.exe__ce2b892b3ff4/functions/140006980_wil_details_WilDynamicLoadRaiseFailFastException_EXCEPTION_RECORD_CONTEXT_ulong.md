# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140006980`
- end: `0x1400069d8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140006980`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000699f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000699f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400069af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400069af`

## string_xrefs

- `0x140006995`: `kernelbase.dll`

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
0x140006980  mov     [rsp+arg_0], rbx
0x140006985  mov     [rsp+arg_8], rsi
0x14000698a  push    rdi
0x14000698b  sub     rsp, 20h
0x14000698f  mov     rsi, rcx
0x140006992  mov     ebx, r8d
0x140006995  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000699c  mov     rdi, rdx
0x14000699f  call    cs:__imp_GetModuleHandleW
0x1400069a5  mov     rcx, rax; hModule
0x1400069a8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1400069af  call    cs:__imp_GetProcAddress
0x1400069b5  test    rax, rax
0x1400069b8  jz      short loc_1400069C8
0x1400069ba  mov     r8d, ebx
0x1400069bd  mov     rdx, rdi
0x1400069c0  mov     rcx, rsi
0x1400069c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400069c8  mov     rbx, [rsp+28h+arg_0]
0x1400069cd  mov     rsi, [rsp+28h+arg_8]
0x1400069d2  add     rsp, 20h
0x1400069d6  pop     rdi
0x1400069d7  retn
```
