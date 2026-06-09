# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800068d0`
- end: `0x180006928`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800068d0`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800068ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800068ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068ff`

## string_xrefs

- `0x1800068e5`: `kernelbase.dll`

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
0x1800068d0  mov     [rsp+arg_0], rbx
0x1800068d5  mov     [rsp+arg_8], rsi
0x1800068da  push    rdi
0x1800068db  sub     rsp, 20h
0x1800068df  mov     rsi, rcx
0x1800068e2  mov     ebx, r8d
0x1800068e5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800068ec  mov     rdi, rdx
0x1800068ef  call    cs:__imp_GetModuleHandleW
0x1800068f5  mov     rcx, rax; hModule
0x1800068f8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800068ff  call    cs:__imp_GetProcAddress
0x180006905  test    rax, rax
0x180006908  jz      short loc_180006918
0x18000690a  mov     r8d, ebx
0x18000690d  mov     rdx, rdi
0x180006910  mov     rcx, rsi
0x180006913  call    _guard_dispatch_icall
0x180006918  mov     rbx, [rsp+28h+arg_0]
0x18000691d  mov     rsi, [rsp+28h+arg_8]
0x180006922  add     rsp, 20h
0x180006926  pop     rdi
0x180006927  retn
```
