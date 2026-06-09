# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140007460`
- end: `0x1400074b8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140007460`
- `0x14000a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000747f`
- `KERNEL32!GetModuleHandleW` at `0x14000747f`
- `KERNEL32!GetProcAddress` at `0x14000748f`
- `KERNEL32!GetProcAddress` at `0x14000748f`

## string_xrefs

- `0x140007475`: `kernelbase.dll`

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
0x140007460  mov     [rsp+arg_0], rbx
0x140007465  mov     [rsp+arg_8], rsi
0x14000746a  push    rdi
0x14000746b  sub     rsp, 20h
0x14000746f  mov     rsi, rcx
0x140007472  mov     ebx, r8d
0x140007475  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000747c  mov     rdi, rdx
0x14000747f  call    cs:__imp_GetModuleHandleW
0x140007485  mov     rcx, rax; hModule
0x140007488  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000748f  call    cs:__imp_GetProcAddress
0x140007495  test    rax, rax
0x140007498  jz      short loc_1400074A8
0x14000749a  mov     r8d, ebx
0x14000749d  mov     rdx, rdi
0x1400074a0  mov     rcx, rsi
0x1400074a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074a8  mov     rbx, [rsp+28h+arg_0]
0x1400074ad  mov     rsi, [rsp+28h+arg_8]
0x1400074b2  add     rsp, 20h
0x1400074b6  pop     rdi
0x1400074b7  retn
```
