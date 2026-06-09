# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1400073f0`
- end: `0x140007440`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003138`
- `0x1400073f0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000740f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000740f`

## string_xrefs

- `0x140007405`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  void (__fastcall *Proc)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD); // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  Proc = (void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,unsigned long)>(ModuleHandleW);
  if ( Proc )
    Proc(this, a2, v4);
}

```

## disassembly

```asm
0x1400073f0  mov     [rsp+arg_0], rbx
0x1400073f5  mov     [rsp+arg_8], rsi
0x1400073fa  push    rdi
0x1400073fb  sub     rsp, 20h
0x1400073ff  mov     rsi, rcx
0x140007402  mov     ebx, r8d
0x140007405  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000740c  mov     rdi, rdx
0x14000740f  call    cs:__imp_GetModuleHandleW
0x140007415  mov     rcx, rax
0x140007418  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x14000741d  test    rax, rax
0x140007420  jz      short loc_140007430
0x140007422  mov     r8d, ebx
0x140007425  mov     rdx, rdi
0x140007428  mov     rcx, rsi
0x14000742b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007430  mov     rbx, [rsp+28h+arg_0]
0x140007435  mov     rsi, [rsp+28h+arg_8]
0x14000743a  add     rsp, 20h
0x14000743e  pop     rdi
0x14000743f  retn
```
