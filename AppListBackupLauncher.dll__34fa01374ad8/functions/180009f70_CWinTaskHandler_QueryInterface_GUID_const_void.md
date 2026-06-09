# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180009f70`
- end: `0x180009fd6`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180009f70`
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
0x180009f70  sub     rsp, 28h
0x180009f74  test    r8, r8
0x180009f77  jnz     short loc_180009F80
0x180009f79  mov     eax, 80070057h
0x180009f7e  jmp     short loc_180009FD1
0x180009f80  mov     rax, [rdx]
0x180009f83  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x180009f8a  jnz     short loc_180009F99
0x180009f8c  mov     rax, [rdx+8]
0x180009f90  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180009f97  jz      short loc_180009FB2
0x180009f99  mov     rax, [rdx]
0x180009f9c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180009fa3  jnz     short loc_180009FC5
0x180009fa5  mov     rax, [rdx+8]
0x180009fa9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180009fb0  jnz     short loc_180009FC5
0x180009fb2  mov     [r8], rcx
0x180009fb5  mov     rax, [rcx]
0x180009fb8  mov     rax, [rax+8]
0x180009fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fc1  xor     eax, eax
0x180009fc3  jmp     short loc_180009FD1
0x180009fc5  mov     qword ptr [r8], 0
0x180009fcc  mov     eax, 80004002h
0x180009fd1  add     rsp, 28h
0x180009fd5  retn
```
