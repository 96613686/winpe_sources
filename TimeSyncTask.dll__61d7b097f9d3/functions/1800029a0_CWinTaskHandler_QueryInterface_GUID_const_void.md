# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x1800029a0`
- end: `0x180002a06`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800029a0`
- `0x180004010`

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
0x1800029a0  sub     rsp, 28h
0x1800029a4  test    r8, r8
0x1800029a7  jnz     short loc_1800029B0
0x1800029a9  mov     eax, 80070057h
0x1800029ae  jmp     short loc_180002A01
0x1800029b0  mov     rax, [rdx]
0x1800029b3  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x1800029ba  jnz     short loc_1800029C9
0x1800029bc  mov     rax, [rdx+8]
0x1800029c0  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x1800029c7  jz      short loc_1800029E2
0x1800029c9  mov     rax, [rdx]
0x1800029cc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800029d3  jnz     short loc_1800029F5
0x1800029d5  mov     rax, [rdx+8]
0x1800029d9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800029e0  jnz     short loc_1800029F5
0x1800029e2  mov     [r8], rcx
0x1800029e5  mov     rax, [rcx]
0x1800029e8  mov     rax, [rax+8]
0x1800029ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029f1  xor     eax, eax
0x1800029f3  jmp     short loc_180002A01
0x1800029f5  mov     qword ptr [r8], 0
0x1800029fc  mov     eax, 80004002h
0x180002a01  add     rsp, 28h
0x180002a05  retn
```
