# std::vector<Broker::ApplicationIdentity,std::allocator<Broker::ApplicationIdentity>>::_Change_array(Broker::ApplicationIdentity * const,unsigned __int64,unsigned __int64)

- ea: `0x180004ca8`
- end: `0x180004d60`
- name: `?_Change_array@?$vector@UApplicationIdentity@Broker@@V?$allocator@UApplicationIdentity@Broker@@@std@@@std@@AEAAXQEAUApplicationIdentity@Broker@@_K1@Z`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180019d48`

## callees

- `0x180004ca8`
- `0x180004d70`
- `0x180014898`
- `0x180015b58`

## pseudocode

```c
__int64 __fastcall std::vector<Broker::ApplicationIdentity>::_Change_array(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  Broker::ApplicationIdentity *v4; // rbx
  Broker::ApplicationIdentity *v9; // rbp
  void *v10; // rcx
  __int64 v11; // rax
  __int64 result; // rax
  void *v13; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 v14; // [rsp+58h] [rbp+10h] BYREF

  v4 = *(Broker::ApplicationIdentity **)a1;
  if ( *(_QWORD *)a1 )
  {
    v9 = *(Broker::ApplicationIdentity **)(a1 + 8);
    while ( v4 != v9 )
    {
      Broker::ApplicationIdentity::~ApplicationIdentity(v4);
      v4 = (Broker::ApplicationIdentity *)((char *)v4 + 88);
    }
    v10 = *(void **)a1;
    v11 = *(_QWORD *)(a1 + 16) - *(_QWORD *)a1;
    v13 = *(void **)a1;
    v14 = 8 * (v11 >> 3);
    if ( v14 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v13, &v14);
      v10 = v13;
    }
    operator delete(v10);
  }
  *(_QWORD *)a1 = a2;
  *(_QWORD *)(a1 + 8) = a2 + 88 * a3;
  result = a2 + 88 * a4;
  *(_QWORD *)(a1 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x180004ca8  mov     [rsp+arg_10], rbx
0x180004cad  push    rbp
0x180004cae  push    rsi
0x180004caf  push    rdi
0x180004cb0  push    r14
0x180004cb2  push    r15
0x180004cb4  sub     rsp, 20h
0x180004cb8  mov     rbx, [rcx]
0x180004cbb  mov     r14, r9
0x180004cbe  mov     r15, r8
0x180004cc1  mov     rsi, rdx
0x180004cc4  mov     rdi, rcx
0x180004cc7  test    rbx, rbx
0x180004cca  jz      short loc_180004D1B
0x180004ccc  mov     rbp, [rcx+8]
0x180004cd0  jmp     short loc_180004CDE
0x180004cd2  mov     rcx, rbx; this
0x180004cd5  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180004cda  add     rbx, 58h ; 'X'
0x180004cde  cmp     rbx, rbp
0x180004ce1  jnz     short loc_180004CD2
0x180004ce3  mov     rcx, [rdi]; void *
0x180004ce6  mov     rdx, 2E8BA2E8BA2E8BA3h
0x180004cf0  mov     rax, [rdi+10h]
0x180004cf4  sub     rax, rcx
0x180004cf7  mov     [rsp+48h+arg_0], rcx
0x180004cfc  sar     rax, 3
0x180004d00  imul    rax, rdx
0x180004d04  imul    rdx, rax, 58h ; 'X'; unsigned __int64
0x180004d08  mov     [rsp+48h+arg_8], rdx
0x180004d0d  cmp     rdx, 1000h
0x180004d14  jnb     short loc_180004D45
0x180004d16  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004d1b  mov     rbx, [rsp+48h+arg_10]
0x180004d20  imul    rax, r15, 58h ; 'X'
0x180004d24  mov     [rdi], rsi
0x180004d27  add     rax, rsi
0x180004d2a  mov     [rdi+8], rax
0x180004d2e  imul    rax, r14, 58h ; 'X'
0x180004d32  add     rax, rsi
0x180004d35  mov     [rdi+10h], rax
0x180004d39  add     rsp, 20h
0x180004d3d  pop     r15
0x180004d3f  pop     r14
0x180004d41  pop     rdi
0x180004d42  pop     rsi
0x180004d43  pop     rbp
0x180004d44  retn
0x180004d45  lea     rdx, [rsp+48h+arg_8]; unsigned __int64 *
0x180004d4a  lea     rcx, [rsp+48h+arg_0]; void **
0x180004d4f  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180004d54  mov     rcx, [rsp+48h+arg_0]
0x180004d59  mov     rdx, [rsp+48h+arg_8]
0x180004d5e  jmp     short loc_180004D16
```
