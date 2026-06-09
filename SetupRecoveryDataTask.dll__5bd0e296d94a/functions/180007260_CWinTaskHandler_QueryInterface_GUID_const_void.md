# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180007260`
- end: `0x1800072c6`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180007260`
- `0x18000d010`

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
0x180007260  sub     rsp, 28h
0x180007264  test    r8, r8
0x180007267  jnz     short loc_180007270
0x180007269  mov     eax, 80070057h
0x18000726e  jmp     short loc_1800072C1
0x180007270  mov     rax, [rdx]
0x180007273  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x18000727a  jnz     short loc_180007289
0x18000727c  mov     rax, [rdx+8]
0x180007280  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180007287  jz      short loc_1800072A2
0x180007289  mov     rax, [rdx]
0x18000728c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180007293  jnz     short loc_1800072B5
0x180007295  mov     rax, [rdx+8]
0x180007299  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800072a0  jnz     short loc_1800072B5
0x1800072a2  mov     [r8], rcx
0x1800072a5  mov     rax, [rcx]
0x1800072a8  mov     rax, [rax+8]
0x1800072ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072b1  xor     eax, eax
0x1800072b3  jmp     short loc_1800072C1
0x1800072b5  mov     qword ptr [r8], 0
0x1800072bc  mov     eax, 80004002h
0x1800072c1  add     rsp, 28h
0x1800072c5  retn
```
