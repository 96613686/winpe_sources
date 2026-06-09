# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180002b90`
- end: `0x180002bf6`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002b90`
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
0x180002b90  sub     rsp, 28h
0x180002b94  test    r8, r8
0x180002b97  jnz     short loc_180002BA0
0x180002b99  mov     eax, 80070057h
0x180002b9e  jmp     short loc_180002BF1
0x180002ba0  mov     rax, [rdx]
0x180002ba3  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x180002baa  jnz     short loc_180002BB9
0x180002bac  mov     rax, [rdx+8]
0x180002bb0  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180002bb7  jz      short loc_180002BD2
0x180002bb9  mov     rax, [rdx]
0x180002bbc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180002bc3  jnz     short loc_180002BE5
0x180002bc5  mov     rax, [rdx+8]
0x180002bc9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180002bd0  jnz     short loc_180002BE5
0x180002bd2  mov     [r8], rcx
0x180002bd5  mov     rax, [rcx]
0x180002bd8  mov     rax, [rax+8]
0x180002bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be1  xor     eax, eax
0x180002be3  jmp     short loc_180002BF1
0x180002be5  mov     qword ptr [r8], 0
0x180002bec  mov     eax, 80004002h
0x180002bf1  add     rsp, 28h
0x180002bf5  retn
```
