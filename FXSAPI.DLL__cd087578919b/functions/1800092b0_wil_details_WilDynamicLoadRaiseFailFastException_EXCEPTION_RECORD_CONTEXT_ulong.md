# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800092b0`
- end: `0x180009315`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800092b0`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800092e5`
- `KERNEL32!GetProcAddress` at `0x1800092e5`
- `KERNEL32!GetModuleHandleW` at `0x1800092cf`
- `KERNEL32!GetModuleHandleW` at `0x1800092cf`

## string_xrefs

- `0x1800092c5`: `kernelbase.dll`

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
0x1800092b0  mov     [rsp+arg_0], rbx
0x1800092b5  mov     [rsp+arg_8], rsi
0x1800092ba  push    rdi
0x1800092bb  sub     rsp, 20h
0x1800092bf  mov     rsi, rcx
0x1800092c2  mov     ebx, r8d
0x1800092c5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800092cc  mov     rdi, rdx
0x1800092cf  call    cs:__imp_GetModuleHandleW
0x1800092d6  nop     dword ptr [rax+rax+00h]
0x1800092db  mov     rcx, rax; hModule
0x1800092de  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800092e5  call    cs:__imp_GetProcAddress
0x1800092ec  nop     dword ptr [rax+rax+00h]
0x1800092f1  test    rax, rax
0x1800092f4  jz      short loc_180009304
0x1800092f6  mov     r8d, ebx
0x1800092f9  mov     rdx, rdi
0x1800092fc  mov     rcx, rsi
0x1800092ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009304  mov     rbx, [rsp+28h+arg_0]
0x180009309  mov     rsi, [rsp+28h+arg_8]
0x18000930e  add     rsp, 20h
0x180009312  pop     rdi
0x180009313  retn
```
