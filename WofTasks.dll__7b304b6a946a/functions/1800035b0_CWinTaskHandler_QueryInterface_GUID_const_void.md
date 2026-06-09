# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x1800035b0`
- end: `0x180003616`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800035b0`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::QueryInterface(CWinTaskHandler *this, const struct _GUID *a2, void **a3)
{
  if ( !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITaskHandler.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ITaskHandler.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(CWinTaskHandler *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x1800035b0  sub     rsp, 28h
0x1800035b4  test    r8, r8
0x1800035b7  jnz     short loc_1800035C0
0x1800035b9  mov     eax, 80070057h
0x1800035be  jmp     short loc_180003611
0x1800035c0  mov     rax, [rdx]
0x1800035c3  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x1800035ca  jnz     short loc_1800035D9
0x1800035cc  mov     rax, [rdx+8]
0x1800035d0  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x1800035d7  jz      short loc_1800035F2
0x1800035d9  mov     rax, [rdx]
0x1800035dc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800035e3  jnz     short loc_180003605
0x1800035e5  mov     rax, [rdx+8]
0x1800035e9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800035f0  jnz     short loc_180003605
0x1800035f2  mov     [r8], rcx
0x1800035f5  mov     rax, [rcx]
0x1800035f8  mov     rax, [rax+8]
0x1800035fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003601  xor     eax, eax
0x180003603  jmp     short loc_180003611
0x180003605  mov     qword ptr [r8], 0
0x18000360c  mov     eax, 80004002h
0x180003611  add     rsp, 28h
0x180003615  retn
```
