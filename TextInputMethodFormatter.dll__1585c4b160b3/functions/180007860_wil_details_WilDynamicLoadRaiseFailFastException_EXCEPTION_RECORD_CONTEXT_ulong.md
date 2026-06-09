# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180007860`
- end: `0x1800078b8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007860`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000788f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000788f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000787f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000787f`

## string_xrefs

- `0x180007875`: `kernelbase.dll`

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
0x180007860  mov     [rsp+arg_0], rbx
0x180007865  mov     [rsp+arg_8], rsi
0x18000786a  push    rdi
0x18000786b  sub     rsp, 20h
0x18000786f  mov     rsi, rcx
0x180007872  mov     ebx, r8d
0x180007875  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000787c  mov     rdi, rdx
0x18000787f  call    cs:__imp_GetModuleHandleW
0x180007885  mov     rcx, rax; hModule
0x180007888  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000788f  call    cs:__imp_GetProcAddress
0x180007895  test    rax, rax
0x180007898  jz      short loc_1800078A8
0x18000789a  mov     r8d, ebx
0x18000789d  mov     rdx, rdi
0x1800078a0  mov     rcx, rsi
0x1800078a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078a8  mov     rbx, [rsp+28h+arg_0]
0x1800078ad  mov     rsi, [rsp+28h+arg_8]
0x1800078b2  add     rsp, 20h
0x1800078b6  pop     rdi
0x1800078b7  retn
```
