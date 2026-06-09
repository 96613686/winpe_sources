# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000bc70`
- end: `0x18000bcc8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000bc70`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000bc8f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000bc8f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000bc9f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000bc9f`

## string_xrefs

- `0x18000bc85`: `kernelbase.dll`

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
0x18000bc70  mov     [rsp+arg_0], rbx
0x18000bc75  mov     [rsp+arg_8], rsi
0x18000bc7a  push    rdi
0x18000bc7b  sub     rsp, 20h
0x18000bc7f  mov     rsi, rcx
0x18000bc82  mov     ebx, r8d
0x18000bc85  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000bc8c  mov     rdi, rdx
0x18000bc8f  call    cs:__imp_GetModuleHandleW
0x18000bc95  mov     rcx, rax; hModule
0x18000bc98  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000bc9f  call    cs:__imp_GetProcAddress
0x18000bca5  test    rax, rax
0x18000bca8  jz      short loc_18000BCB8
0x18000bcaa  mov     r8d, ebx
0x18000bcad  mov     rdx, rdi
0x18000bcb0  mov     rcx, rsi
0x18000bcb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcb8  mov     rbx, [rsp+28h+arg_0]
0x18000bcbd  mov     rsi, [rsp+28h+arg_8]
0x18000bcc2  add     rsp, 20h
0x18000bcc6  pop     rdi
0x18000bcc7  retn
```
