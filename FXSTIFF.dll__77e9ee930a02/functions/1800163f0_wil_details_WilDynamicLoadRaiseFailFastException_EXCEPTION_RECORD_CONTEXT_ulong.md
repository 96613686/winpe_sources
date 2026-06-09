# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800163f0`
- end: `0x180016457`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `103`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800163f0`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001640f`
- `KERNEL32!GetModuleHandleW` at `0x18001640f`
- `KERNEL32!GetProcAddress` at `0x180016426`
- `KERNEL32!GetProcAddress` at `0x180016426`

## string_xrefs

- `0x180016408`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v3; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v3 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v3);
}

```

## disassembly

```asm
0x1800163f0  mov     [rsp+arg_0], rbx
0x1800163f5  mov     [rsp+arg_8], rsi
0x1800163fa  push    rdi
0x1800163fb  sub     rsp, 20h
0x1800163ff  mov     ebx, r8d
0x180016402  mov     rdi, rdx
0x180016405  mov     rsi, rcx
0x180016408  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001640f  call    cs:__imp_GetModuleHandleW
0x180016416  nop     dword ptr [rax+rax+00h]
0x18001641b  nop
0x18001641c  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180016423  mov     rcx, rax; hModule
0x180016426  call    cs:__imp_GetProcAddress
0x18001642d  nop     dword ptr [rax+rax+00h]
0x180016432  nop
0x180016433  test    rax, rax
0x180016436  jz      short loc_180016446
0x180016438  mov     r8d, ebx
0x18001643b  mov     rdx, rdi
0x18001643e  mov     rcx, rsi
0x180016441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016446  mov     rbx, [rsp+28h+arg_0]
0x18001644b  mov     rsi, [rsp+28h+arg_8]
0x180016450  add     rsp, 20h
0x180016454  pop     rdi
0x180016455  retn
```
