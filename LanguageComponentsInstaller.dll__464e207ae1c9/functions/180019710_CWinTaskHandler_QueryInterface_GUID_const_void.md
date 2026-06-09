# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180019710`
- end: `0x180019776`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180019710`
- `0x18002a010`

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
0x180019710  sub     rsp, 28h
0x180019714  test    r8, r8
0x180019717  jnz     short loc_180019720
0x180019719  mov     eax, 80070057h
0x18001971e  jmp     short loc_180019771
0x180019720  mov     rax, [rdx]
0x180019723  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x18001972a  jnz     short loc_180019739
0x18001972c  mov     rax, [rdx+8]
0x180019730  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180019737  jz      short loc_180019752
0x180019739  mov     rax, [rdx]
0x18001973c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180019743  jnz     short loc_180019765
0x180019745  mov     rax, [rdx+8]
0x180019749  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180019750  jnz     short loc_180019765
0x180019752  mov     [r8], rcx
0x180019755  mov     rax, [rcx]
0x180019758  mov     rax, [rax+8]
0x18001975c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019761  xor     eax, eax
0x180019763  jmp     short loc_180019771
0x180019765  mov     qword ptr [r8], 0
0x18001976c  mov     eax, 80004002h
0x180019771  add     rsp, 28h
0x180019775  retn
```
