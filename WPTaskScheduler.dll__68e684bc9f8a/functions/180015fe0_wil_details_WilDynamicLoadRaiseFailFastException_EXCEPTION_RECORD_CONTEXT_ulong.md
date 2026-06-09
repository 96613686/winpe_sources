# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180015fe0`
- end: `0x180016038`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180015fe0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001600f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001600f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015fff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015fff`

## string_xrefs

- `0x180015ff5`: `kernelbase.dll`

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
0x180015fe0  mov     [rsp+arg_0], rbx
0x180015fe5  mov     [rsp+arg_8], rsi
0x180015fea  push    rdi
0x180015feb  sub     rsp, 20h
0x180015fef  mov     rsi, rcx
0x180015ff2  mov     ebx, r8d
0x180015ff5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180015ffc  mov     rdi, rdx
0x180015fff  call    cs:__imp_GetModuleHandleW
0x180016005  mov     rcx, rax; hModule
0x180016008  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18001600f  call    cs:__imp_GetProcAddress
0x180016015  test    rax, rax
0x180016018  jz      short loc_180016028
0x18001601a  mov     r8d, ebx
0x18001601d  mov     rdx, rdi
0x180016020  mov     rcx, rsi
0x180016023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016028  mov     rbx, [rsp+28h+arg_0]
0x18001602d  mov     rsi, [rsp+28h+arg_8]
0x180016032  add     rsp, 20h
0x180016036  pop     rdi
0x180016037  retn
```
