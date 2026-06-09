# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x18000ddb0`
- end: `0x18000de16`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000ddb0`
- `0x18000f010`

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
0x18000ddb0  sub     rsp, 28h
0x18000ddb4  test    r8, r8
0x18000ddb7  jnz     short loc_18000DDC0
0x18000ddb9  mov     eax, 80070057h
0x18000ddbe  jmp     short loc_18000DE11
0x18000ddc0  mov     rax, [rdx]
0x18000ddc3  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x18000ddca  jnz     short loc_18000DDD9
0x18000ddcc  mov     rax, [rdx+8]
0x18000ddd0  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x18000ddd7  jz      short loc_18000DDF2
0x18000ddd9  mov     rax, [rdx]
0x18000dddc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000dde3  jnz     short loc_18000DE05
0x18000dde5  mov     rax, [rdx+8]
0x18000dde9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000ddf0  jnz     short loc_18000DE05
0x18000ddf2  mov     [r8], rcx
0x18000ddf5  mov     rax, [rcx]
0x18000ddf8  mov     rax, [rax+8]
0x18000ddfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de01  xor     eax, eax
0x18000de03  jmp     short loc_18000DE11
0x18000de05  mov     qword ptr [r8], 0
0x18000de0c  mov     eax, 80004002h
0x18000de11  add     rsp, 28h
0x18000de15  retn
```
