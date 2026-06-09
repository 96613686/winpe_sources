# Concurrency::details::_TaskProcThunk::_Holder::~_Holder(void)

- ea: `0x18000fef4`
- end: `0x18000ff38`
- name: `??1_Holder@_TaskProcThunk@details@Concurrency@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(Concurrency::details::_TaskProcThunk::_Holder *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18001816f`

## callees

- `0x180002054`
- `0x18000fef4`
- `0x180019010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_TaskProcThunk::_Holder::~_Holder(
        Concurrency::details::_TaskProcThunk::_Holder *this,
        __int64 a2)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rcx

  v2 = *(_QWORD **)this;
  if ( *(_QWORD *)this )
  {
    v3 = (_QWORD *)v2[7];
    if ( v3 )
    {
      LOBYTE(a2) = v3 != v2;
      (*(void (__fastcall **)(_QWORD *, __int64))(*v3 + 32LL))(v3, a2);
      v2[7] = 0;
    }
    operator delete(v2, 0x40u);
  }
}

```

## disassembly

```asm
0x18000fef4  push    rbx
0x18000fef6  sub     rsp, 20h
0x18000fefa  mov     rbx, [rcx]
0x18000fefd  test    rbx, rbx
0x18000ff00  jz      short loc_18000FF32
0x18000ff02  mov     rcx, [rbx+38h]
0x18000ff06  test    rcx, rcx
0x18000ff09  jz      short loc_18000FF25
0x18000ff0b  mov     rax, [rcx]
0x18000ff0e  cmp     rcx, rbx
0x18000ff11  setnz   dl
0x18000ff14  mov     rax, [rax+20h]
0x18000ff18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff1d  mov     qword ptr [rbx+38h], 0
0x18000ff25  mov     edx, 40h ; '@'; unsigned __int64
0x18000ff2a  mov     rcx, rbx; void *
0x18000ff2d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ff32  add     rsp, 20h
0x18000ff36  pop     rbx
0x18000ff37  retn
```
