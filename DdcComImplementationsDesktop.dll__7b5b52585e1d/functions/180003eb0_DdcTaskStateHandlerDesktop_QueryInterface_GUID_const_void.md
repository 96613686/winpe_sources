# DdcTaskStateHandlerDesktop::QueryInterface(_GUID const &,void * *)

- ea: `0x180003eb0`
- end: `0x180003f16`
- name: `?QueryInterface@DdcTaskStateHandlerDesktop@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(DdcTaskStateHandlerDesktop *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003eb0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall DdcTaskStateHandlerDesktop::QueryInterface(
        DdcTaskStateHandlerDesktop *this,
        const struct _GUID *a2,
        void **a3)
{
  if ( !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITaskStateHandler.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ITaskStateHandler.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(DdcTaskStateHandlerDesktop *))(*(_QWORD *)this + 8LL))(this);
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
0x180003eb0  sub     rsp, 28h
0x180003eb4  test    r8, r8
0x180003eb7  jnz     short loc_180003EC0
0x180003eb9  mov     eax, 80070057h
0x180003ebe  jmp     short loc_180003F11
0x180003ec0  mov     rax, [rdx]
0x180003ec3  cmp     rax, qword ptr cs:IID_ITaskStateHandler.Data1
0x180003eca  jnz     short loc_180003ED9
0x180003ecc  mov     rax, [rdx+8]
0x180003ed0  cmp     rax, qword ptr cs:IID_ITaskStateHandler.Data4
0x180003ed7  jz      short loc_180003EF2
0x180003ed9  mov     rax, [rdx]
0x180003edc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180003ee3  jnz     short loc_180003F05
0x180003ee5  mov     rax, [rdx+8]
0x180003ee9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180003ef0  jnz     short loc_180003F05
0x180003ef2  mov     [r8], rcx
0x180003ef5  mov     rax, [rcx]
0x180003ef8  mov     rax, [rax+8]
0x180003efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f01  xor     eax, eax
0x180003f03  jmp     short loc_180003F11
0x180003f05  mov     qword ptr [r8], 0
0x180003f0c  mov     eax, 80004002h
0x180003f11  add     rsp, 28h
0x180003f15  retn
```
