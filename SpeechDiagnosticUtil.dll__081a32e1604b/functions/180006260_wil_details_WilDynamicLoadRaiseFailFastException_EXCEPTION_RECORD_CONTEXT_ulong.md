# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006260`
- end: `0x1800062c5`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006260`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000627f`
- `KERNEL32!GetModuleHandleW` at `0x18000627f`
- `KERNEL32!GetProcAddress` at `0x180006295`
- `KERNEL32!GetProcAddress` at `0x180006295`

## string_xrefs

- `0x180006275`: `kernelbase.dll`

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
0x180006260  mov     [rsp+arg_0], rbx
0x180006265  mov     [rsp+arg_8], rsi
0x18000626a  push    rdi
0x18000626b  sub     rsp, 20h
0x18000626f  mov     rsi, rcx
0x180006272  mov     ebx, r8d
0x180006275  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000627c  mov     rdi, rdx
0x18000627f  call    cs:__imp_GetModuleHandleW
0x180006286  nop     dword ptr [rax+rax+00h]
0x18000628b  mov     rcx, rax; hModule
0x18000628e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180006295  call    cs:__imp_GetProcAddress
0x18000629c  nop     dword ptr [rax+rax+00h]
0x1800062a1  test    rax, rax
0x1800062a4  jz      short loc_1800062B4
0x1800062a6  mov     r8d, ebx
0x1800062a9  mov     rdx, rdi
0x1800062ac  mov     rcx, rsi
0x1800062af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062b4  mov     rbx, [rsp+28h+arg_0]
0x1800062b9  mov     rsi, [rsp+28h+arg_8]
0x1800062be  add     rsp, 20h
0x1800062c2  pop     rdi
0x1800062c3  retn
```
