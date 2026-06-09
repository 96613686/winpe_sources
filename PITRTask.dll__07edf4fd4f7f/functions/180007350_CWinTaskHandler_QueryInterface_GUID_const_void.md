# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180007350`
- end: `0x1800073b6`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180007350`
- `0x180012010`

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
0x180007350  sub     rsp, 28h
0x180007354  test    r8, r8
0x180007357  jnz     short loc_180007360
0x180007359  mov     eax, 80070057h
0x18000735e  jmp     short loc_1800073B1
0x180007360  mov     rax, [rdx]
0x180007363  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x18000736a  jnz     short loc_180007379
0x18000736c  mov     rax, [rdx+8]
0x180007370  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180007377  jz      short loc_180007392
0x180007379  mov     rax, [rdx]
0x18000737c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180007383  jnz     short loc_1800073A5
0x180007385  mov     rax, [rdx+8]
0x180007389  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180007390  jnz     short loc_1800073A5
0x180007392  mov     [r8], rcx
0x180007395  mov     rax, [rcx]
0x180007398  mov     rax, [rax+8]
0x18000739c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073a1  xor     eax, eax
0x1800073a3  jmp     short loc_1800073B1
0x1800073a5  mov     qword ptr [r8], 0
0x1800073ac  mov     eax, 80004002h
0x1800073b1  add     rsp, 28h
0x1800073b5  retn
```
