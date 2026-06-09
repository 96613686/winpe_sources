# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180001f40`
- end: `0x180001fa6`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001f40`
- `0x180003010`

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
0x180001f40  sub     rsp, 28h
0x180001f44  test    r8, r8
0x180001f47  jnz     short loc_180001F50
0x180001f49  mov     eax, 80070057h
0x180001f4e  jmp     short loc_180001FA1
0x180001f50  mov     rax, [rdx]
0x180001f53  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x180001f5a  jnz     short loc_180001F69
0x180001f5c  mov     rax, [rdx+8]
0x180001f60  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180001f67  jz      short loc_180001F82
0x180001f69  mov     rax, [rdx]
0x180001f6c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180001f73  jnz     short loc_180001F95
0x180001f75  mov     rax, [rdx+8]
0x180001f79  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180001f80  jnz     short loc_180001F95
0x180001f82  mov     [r8], rcx
0x180001f85  mov     rax, [rcx]
0x180001f88  mov     rax, [rax+8]
0x180001f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f91  xor     eax, eax
0x180001f93  jmp     short loc_180001FA1
0x180001f95  mov     qword ptr [r8], 0
0x180001f9c  mov     eax, 80004002h
0x180001fa1  add     rsp, 28h
0x180001fa5  retn
```
