# DdcCommandHandlerDesktop::QueryInterface(_GUID const &,void * *)

- ea: `0x1800030e0`
- end: `0x180003146`
- name: `?QueryInterface@DdcCommandHandlerDesktop@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(DdcCommandHandlerDesktop *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall DdcCommandHandlerDesktop::QueryInterface(
        DdcCommandHandlerDesktop *this,
        const struct _GUID *a2,
        void **a3)
{
  if ( !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ICommandHandler.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ICommandHandler.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(DdcCommandHandlerDesktop *))(*(_QWORD *)this + 8LL))(this);
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
0x1800030e0  sub     rsp, 28h
0x1800030e4  test    r8, r8
0x1800030e7  jnz     short loc_1800030F0
0x1800030e9  mov     eax, 80070057h
0x1800030ee  jmp     short loc_180003141
0x1800030f0  mov     rax, [rdx]
0x1800030f3  cmp     rax, qword ptr cs:IID_ICommandHandler.Data1
0x1800030fa  jnz     short loc_180003109
0x1800030fc  mov     rax, [rdx+8]
0x180003100  cmp     rax, qword ptr cs:IID_ICommandHandler.Data4
0x180003107  jz      short loc_180003122
0x180003109  mov     rax, [rdx]
0x18000310c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180003113  jnz     short loc_180003135
0x180003115  mov     rax, [rdx+8]
0x180003119  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180003120  jnz     short loc_180003135
0x180003122  mov     [r8], rcx
0x180003125  mov     rax, [rcx]
0x180003128  mov     rax, [rax+8]
0x18000312c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003131  xor     eax, eax
0x180003133  jmp     short loc_180003141
0x180003135  mov     qword ptr [r8], 0
0x18000313c  mov     eax, 80004002h
0x180003141  add     rsp, 28h
0x180003145  retn
```
