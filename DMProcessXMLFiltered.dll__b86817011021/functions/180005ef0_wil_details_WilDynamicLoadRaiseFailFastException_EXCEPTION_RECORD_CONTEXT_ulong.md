# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005ef0`
- end: `0x180005f48`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005ef0`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f0f`

## string_xrefs

- `0x180005f05`: `kernelbase.dll`

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
0x180005ef0  mov     [rsp+arg_0], rbx
0x180005ef5  mov     [rsp+arg_8], rsi
0x180005efa  push    rdi
0x180005efb  sub     rsp, 20h
0x180005eff  mov     rsi, rcx
0x180005f02  mov     ebx, r8d
0x180005f05  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005f0c  mov     rdi, rdx
0x180005f0f  call    cs:__imp_GetModuleHandleW
0x180005f15  mov     rcx, rax; hModule
0x180005f18  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180005f1f  call    cs:__imp_GetProcAddress
0x180005f25  test    rax, rax
0x180005f28  jz      short loc_180005F38
0x180005f2a  mov     r8d, ebx
0x180005f2d  mov     rdx, rdi
0x180005f30  mov     rcx, rsi
0x180005f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f38  mov     rbx, [rsp+28h+arg_0]
0x180005f3d  mov     rsi, [rsp+28h+arg_8]
0x180005f42  add     rsp, 20h
0x180005f46  pop     rdi
0x180005f47  retn
```
