# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008700`
- end: `0x180008758`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008700`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000871f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000871f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000872f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000872f`

## string_xrefs

- `0x180008715`: `kernelbase.dll`

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
0x180008700  mov     [rsp+arg_0], rbx
0x180008705  mov     [rsp+arg_8], rsi
0x18000870a  push    rdi
0x18000870b  sub     rsp, 20h
0x18000870f  mov     rsi, rcx
0x180008712  mov     ebx, r8d
0x180008715  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000871c  mov     rdi, rdx
0x18000871f  call    cs:__imp_GetModuleHandleW
0x180008725  mov     rcx, rax; hModule
0x180008728  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000872f  call    cs:__imp_GetProcAddress
0x180008735  test    rax, rax
0x180008738  jz      short loc_180008748
0x18000873a  mov     r8d, ebx
0x18000873d  mov     rdx, rdi
0x180008740  mov     rcx, rsi
0x180008743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008748  mov     rbx, [rsp+28h+arg_0]
0x18000874d  mov     rsi, [rsp+28h+arg_8]
0x180008752  add     rsp, 20h
0x180008756  pop     rdi
0x180008757  retn
```
