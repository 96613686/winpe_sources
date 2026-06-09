# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005450`
- end: `0x1800054a0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800035c4`
- `0x180005450`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000546f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000546f`

## string_xrefs

- `0x180005465`: `kernelbase.dll`

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
0x180005450  mov     [rsp+arg_0], rbx
0x180005455  mov     [rsp+arg_8], rsi
0x18000545a  push    rdi
0x18000545b  sub     rsp, 20h
0x18000545f  mov     rsi, rcx
0x180005462  mov     ebx, r8d
0x180005465  lea     rcx, ModuleName; "kernelbase.dll"
0x18000546c  mov     rdi, rdx
0x18000546f  call    cs:__imp_GetModuleHandleW
0x180005475  mov     rcx, rax
0x180005478  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000547d  test    rax, rax
0x180005480  jz      short loc_180005490
0x180005482  mov     r8d, ebx
0x180005485  mov     rdx, rdi
0x180005488  mov     rcx, rsi
0x18000548b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005490  mov     rbx, [rsp+28h+arg_0]
0x180005495  mov     rsi, [rsp+28h+arg_8]
0x18000549a  add     rsp, 20h
0x18000549e  pop     rdi
0x18000549f  retn
```
