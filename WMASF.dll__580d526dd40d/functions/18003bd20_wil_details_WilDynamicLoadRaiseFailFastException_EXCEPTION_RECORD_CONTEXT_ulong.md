# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18003bd20`
- end: `0x18003bd78`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003bd20`
- `0x180040010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003bd4f`
- `KERNEL32!GetProcAddress` at `0x18003bd4f`
- `KERNEL32!GetModuleHandleW` at `0x18003bd3f`
- `KERNEL32!GetModuleHandleW` at `0x18003bd3f`

## string_xrefs

- `0x18003bd35`: `kernelbase.dll`

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
0x18003bd20  mov     [rsp+arg_0], rbx
0x18003bd25  mov     [rsp+arg_8], rsi
0x18003bd2a  push    rdi
0x18003bd2b  sub     rsp, 20h
0x18003bd2f  mov     rsi, rcx
0x18003bd32  mov     ebx, r8d
0x18003bd35  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003bd3c  mov     rdi, rdx
0x18003bd3f  call    cs:__imp_GetModuleHandleW
0x18003bd45  mov     rcx, rax; hModule
0x18003bd48  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18003bd4f  call    cs:__imp_GetProcAddress
0x18003bd55  test    rax, rax
0x18003bd58  jz      short loc_18003BD68
0x18003bd5a  mov     r8d, ebx
0x18003bd5d  mov     rdx, rdi
0x18003bd60  mov     rcx, rsi
0x18003bd63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd68  mov     rbx, [rsp+28h+arg_0]
0x18003bd6d  mov     rsi, [rsp+28h+arg_8]
0x18003bd72  add     rsp, 20h
0x18003bd76  pop     rdi
0x18003bd77  retn
```
