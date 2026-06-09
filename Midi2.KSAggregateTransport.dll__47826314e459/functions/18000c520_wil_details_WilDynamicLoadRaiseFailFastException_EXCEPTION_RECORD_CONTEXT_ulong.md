# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000c520`
- end: `0x18000c578`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c520`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c53f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c53f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c54f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c54f`

## string_xrefs

- `0x18000c535`: `kernelbase.dll`

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
0x18000c520  mov     [rsp+arg_0], rbx
0x18000c525  mov     [rsp+arg_8], rsi
0x18000c52a  push    rdi
0x18000c52b  sub     rsp, 20h
0x18000c52f  mov     rsi, rcx
0x18000c532  mov     ebx, r8d
0x18000c535  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c53c  mov     rdi, rdx
0x18000c53f  call    cs:__imp_GetModuleHandleW
0x18000c545  mov     rcx, rax; hModule
0x18000c548  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000c54f  call    cs:__imp_GetProcAddress
0x18000c555  test    rax, rax
0x18000c558  jz      short loc_18000C568
0x18000c55a  mov     r8d, ebx
0x18000c55d  mov     rdx, rdi
0x18000c560  mov     rcx, rsi
0x18000c563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c568  mov     rbx, [rsp+28h+arg_0]
0x18000c56d  mov     rsi, [rsp+28h+arg_8]
0x18000c572  add     rsp, 20h
0x18000c576  pop     rdi
0x18000c577  retn
```
