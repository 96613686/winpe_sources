# std::vector<std::shared_ptr<Broker::BrokerEvent>,std::allocator<std::shared_ptr<Broker::BrokerEvent>>>::_Change_array(std::shared_ptr<Broker::BrokerEvent> * const,unsigned __int64,unsigned __int64)

- ea: `0x180004e78`
- end: `0x180004f64`
- name: `?_Change_array@?$vector@V?$shared_ptr@VBrokerEvent@Broker@@@std@@V?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@2@@std@@AEAAXQEAV?$shared_ptr@VBrokerEvent@Broker@@@2@_K1@Z`
- size: `236`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003db0`
- `0x180004140`
- `0x180011b9c`

## callees

- `0x180004e78`
- `0x180014898`
- `0x180015b58`
- `0x18001e010`

## pseudocode

```c
void __fastcall std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Change_array(
        void **a1,
        char *a2,
        __int64 a3,
        __int64 a4)
{
  char *v4; // rsi
  char *v9; // r12
  volatile signed __int32 *v10; // rbx
  char *v11; // rcx
  signed __int64 v12; // rdx
  void *v13; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 v14; // [rsp+58h] [rbp+10h] BYREF

  v4 = (char *)*a1;
  if ( *a1 )
  {
    v9 = (char *)a1[1];
    while ( v4 != v9 )
    {
      v10 = (volatile signed __int32 *)*((_QWORD *)v4 + 1);
      if ( v10 && _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
      v4 += 16;
    }
    v11 = (char *)*a1;
    v12 = (_BYTE *)a1[2] - (_BYTE *)*a1;
    v13 = *a1;
    v14 = v12 & 0xFFFFFFFFFFFFFFF0uLL;
    if ( (v12 & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v13, &v14);
      v11 = (char *)v13;
    }
    operator delete(v11);
  }
  *a1 = a2;
  a1[1] = &a2[16 * a3];
  a1[2] = &a2[16 * a4];
}

```

## disassembly

```asm
0x180004e78  mov     [rsp+arg_10], rbx
0x180004e7d  mov     [rsp+arg_18], rbp
0x180004e82  push    rsi
0x180004e83  push    rdi
0x180004e84  push    r12
0x180004e86  push    r14
0x180004e88  push    r15
0x180004e8a  sub     rsp, 20h
0x180004e8e  mov     rsi, [rcx]
0x180004e91  mov     rbp, r9
0x180004e94  mov     r14, r8
0x180004e97  mov     r15, rdx
0x180004e9a  mov     rdi, rcx
0x180004e9d  test    rsi, rsi
0x180004ea0  jz      short loc_180004F19
0x180004ea2  mov     r12, [rcx+8]
0x180004ea6  jmp     short loc_180004ED6
0x180004ea8  mov     rax, [rbx]
0x180004eab  mov     rcx, rbx
0x180004eae  mov     rax, [rax]
0x180004eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eb6  or      eax, 0FFFFFFFFh
0x180004eb9  lock xadd [rbx+0Ch], eax
0x180004ebe  cmp     eax, 1
0x180004ec1  jnz     short loc_180004ED2
0x180004ec3  mov     rax, [rbx]
0x180004ec6  mov     rcx, rbx
0x180004ec9  mov     rax, [rax+8]
0x180004ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed2  add     rsi, 10h
0x180004ed6  cmp     rsi, r12
0x180004ed9  jz      short loc_180004EF3
0x180004edb  mov     rbx, [rsi+8]
0x180004edf  test    rbx, rbx
0x180004ee2  jz      short loc_180004ED2
0x180004ee4  or      eax, 0FFFFFFFFh
0x180004ee7  lock xadd [rbx+8], eax
0x180004eec  cmp     eax, 1
0x180004eef  jz      short loc_180004EA8
0x180004ef1  jmp     short loc_180004ED2
0x180004ef3  mov     rcx, [rdi]; void *
0x180004ef6  mov     rdx, [rdi+10h]
0x180004efa  sub     rdx, rcx
0x180004efd  mov     [rsp+48h+arg_0], rcx
0x180004f02  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x180004f06  mov     [rsp+48h+arg_8], rdx
0x180004f0b  cmp     rdx, 1000h
0x180004f12  jnb     short loc_180004F49
0x180004f14  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004f19  mov     rbx, [rsp+48h+arg_10]
0x180004f1e  shl     r14, 4
0x180004f22  add     r14, r15
0x180004f25  shl     rbp, 4
0x180004f29  add     rbp, r15
0x180004f2c  mov     [rdi], r15
0x180004f2f  mov     [rdi+8], r14
0x180004f33  mov     [rdi+10h], rbp
0x180004f37  mov     rbp, [rsp+48h+arg_18]
0x180004f3c  add     rsp, 20h
0x180004f40  pop     r15
0x180004f42  pop     r14
0x180004f44  pop     r12
0x180004f46  pop     rdi
0x180004f47  pop     rsi
0x180004f48  retn
0x180004f49  lea     rdx, [rsp+48h+arg_8]; unsigned __int64 *
0x180004f4e  lea     rcx, [rsp+48h+arg_0]; void **
0x180004f53  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180004f58  mov     rcx, [rsp+48h+arg_0]
0x180004f5d  mov     rdx, [rsp+48h+arg_8]
0x180004f62  jmp     short loc_180004F14
```
