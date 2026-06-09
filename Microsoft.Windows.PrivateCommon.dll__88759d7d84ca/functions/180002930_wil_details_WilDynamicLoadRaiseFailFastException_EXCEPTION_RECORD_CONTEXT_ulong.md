# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180002930`
- end: `0x180002989`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `89`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002930`
- `0x18000b930`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000295f`
- `KERNEL32!GetProcAddress` at `0x18000295f`
- `KERNEL32!GetModuleHandleW` at `0x18000294f`
- `KERNEL32!GetModuleHandleW` at `0x18000294f`

## string_xrefs

- `0x180002945`: `kernelbase.dll`

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
0x180002930  mov     [rsp+arg_0], rbx
0x180002935  mov     [rsp+arg_8], rsi
0x18000293a  push    rdi
0x18000293b  sub     rsp, 20h
0x18000293f  mov     rsi, rcx
0x180002942  mov     ebx, r8d
0x180002945  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000294c  mov     rdi, rdx
0x18000294f  call    cs:__imp_GetModuleHandleW
0x180002955  mov     rcx, rax; hModule
0x180002958  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000295f  call    cs:__imp_GetProcAddress
0x180002965  test    rax, rax
0x180002968  jz      short loc_180002979
0x18000296a  mov     r8d, ebx
0x18000296d  mov     rdx, rdi
0x180002970  mov     rcx, rsi
0x180002973  call    cs:__guard_dispatch_icall_fptr
0x180002979  mov     rbx, [rsp+28h+arg_0]
0x18000297e  mov     rsi, [rsp+28h+arg_8]
0x180002983  add     rsp, 20h
0x180002987  pop     rdi
0x180002988  retn
```
