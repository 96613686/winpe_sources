# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180028200`
- end: `0x180028265`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180028200`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002821f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002821f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028235`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028235`

## string_xrefs

- `0x180028215`: `kernelbase.dll`

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
0x180028200  mov     [rsp+arg_0], rbx
0x180028205  mov     [rsp+arg_8], rsi
0x18002820a  push    rdi
0x18002820b  sub     rsp, 20h
0x18002820f  mov     rsi, rcx
0x180028212  mov     ebx, r8d
0x180028215  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002821c  mov     rdi, rdx
0x18002821f  call    cs:__imp_GetModuleHandleW
0x180028226  nop     dword ptr [rax+rax+00h]
0x18002822b  mov     rcx, rax; hModule
0x18002822e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180028235  call    cs:__imp_GetProcAddress
0x18002823c  nop     dword ptr [rax+rax+00h]
0x180028241  test    rax, rax
0x180028244  jz      short loc_180028254
0x180028246  mov     r8d, ebx
0x180028249  mov     rdx, rdi
0x18002824c  mov     rcx, rsi
0x18002824f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028254  mov     rbx, [rsp+28h+arg_0]
0x180028259  mov     rsi, [rsp+28h+arg_8]
0x18002825e  add     rsp, 20h
0x180028262  pop     rdi
0x180028263  retn
```
