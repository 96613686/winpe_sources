# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14000c4d0`
- end: `0x14000c528`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000c4d0`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000c4ef`
- `KERNEL32!GetModuleHandleW` at `0x14000c4ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c4ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c4ff`

## string_xrefs

- `0x14000c4e5`: `kernelbase.dll`

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
0x14000c4d0  mov     [rsp+arg_0], rbx
0x14000c4d5  mov     [rsp+arg_8], rsi
0x14000c4da  push    rdi
0x14000c4db  sub     rsp, 20h
0x14000c4df  mov     rsi, rcx
0x14000c4e2  mov     ebx, r8d
0x14000c4e5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000c4ec  mov     rdi, rdx
0x14000c4ef  call    cs:__imp_GetModuleHandleW
0x14000c4f5  mov     rcx, rax; hModule
0x14000c4f8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000c4ff  call    cs:__imp_GetProcAddress
0x14000c505  test    rax, rax
0x14000c508  jz      short loc_14000C518
0x14000c50a  mov     r8d, ebx
0x14000c50d  mov     rdx, rdi
0x14000c510  mov     rcx, rsi
0x14000c513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c518  mov     rbx, [rsp+28h+arg_0]
0x14000c51d  mov     rsi, [rsp+28h+arg_8]
0x14000c522  add     rsp, 20h
0x14000c526  pop     rdi
0x14000c527  retn
```
