# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000ddf0`
- end: `0x18000de48`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ddf0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000de1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000de1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000de0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000de0f`

## string_xrefs

- `0x18000de05`: `kernelbase.dll`

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
0x18000ddf0  mov     [rsp+arg_0], rbx
0x18000ddf5  mov     [rsp+arg_8], rsi
0x18000ddfa  push    rdi
0x18000ddfb  sub     rsp, 20h
0x18000ddff  mov     rsi, rcx
0x18000de02  mov     ebx, r8d
0x18000de05  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000de0c  mov     rdi, rdx
0x18000de0f  call    cs:__imp_GetModuleHandleW
0x18000de15  mov     rcx, rax; hModule
0x18000de18  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000de1f  call    cs:__imp_GetProcAddress
0x18000de25  test    rax, rax
0x18000de28  jz      short loc_18000DE38
0x18000de2a  mov     r8d, ebx
0x18000de2d  mov     rdx, rdi
0x18000de30  mov     rcx, rsi
0x18000de33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de38  mov     rbx, [rsp+28h+arg_0]
0x18000de3d  mov     rsi, [rsp+28h+arg_8]
0x18000de42  add     rsp, 20h
0x18000de46  pop     rdi
0x18000de47  retn
```
