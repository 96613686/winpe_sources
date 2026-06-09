# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180028ab0`
- end: `0x180028b15`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180028ab0`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180028acf`
- `KERNEL32!GetModuleHandleW` at `0x180028acf`
- `KERNEL32!GetProcAddress` at `0x180028ae5`
- `KERNEL32!GetProcAddress` at `0x180028ae5`

## string_xrefs

- `0x180028ac5`: `kernelbase.dll`

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
0x180028ab0  mov     [rsp+arg_0], rbx
0x180028ab5  mov     [rsp+arg_8], rsi
0x180028aba  push    rdi
0x180028abb  sub     rsp, 20h
0x180028abf  mov     rsi, rcx
0x180028ac2  mov     ebx, r8d
0x180028ac5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180028acc  mov     rdi, rdx
0x180028acf  call    cs:__imp_GetModuleHandleW
0x180028ad6  nop     dword ptr [rax+rax+00h]
0x180028adb  mov     rcx, rax; hModule
0x180028ade  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180028ae5  call    cs:__imp_GetProcAddress
0x180028aec  nop     dword ptr [rax+rax+00h]
0x180028af1  test    rax, rax
0x180028af4  jz      short loc_180028B04
0x180028af6  mov     r8d, ebx
0x180028af9  mov     rdx, rdi
0x180028afc  mov     rcx, rsi
0x180028aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b04  mov     rbx, [rsp+28h+arg_0]
0x180028b09  mov     rsi, [rsp+28h+arg_8]
0x180028b0e  add     rsp, 20h
0x180028b12  pop     rdi
0x180028b13  retn
```
