# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800054c0`
- end: `0x180005517`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003614`
- `0x1800054c0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800054df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800054df`

## string_xrefs

- `0x1800054d5`: `kernelbase.dll`

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
0x1800054c0  mov     [rsp+arg_0], rbx
0x1800054c5  mov     [rsp+arg_8], rsi
0x1800054ca  push    rdi
0x1800054cb  sub     rsp, 20h
0x1800054cf  mov     rsi, rcx
0x1800054d2  mov     ebx, r8d
0x1800054d5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800054dc  mov     rdi, rdx
0x1800054df  call    cs:__imp_GetModuleHandleW
0x1800054e6  nop     dword ptr [rax+rax+00h]
0x1800054eb  mov     rcx, rax
0x1800054ee  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800054f3  test    rax, rax
0x1800054f6  jz      short loc_180005506
0x1800054f8  mov     r8d, ebx
0x1800054fb  mov     rdx, rdi
0x1800054fe  mov     rcx, rsi
0x180005501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005506  mov     rbx, [rsp+28h+arg_0]
0x18000550b  mov     rsi, [rsp+28h+arg_8]
0x180005510  add     rsp, 20h
0x180005514  pop     rdi
0x180005515  retn
```
