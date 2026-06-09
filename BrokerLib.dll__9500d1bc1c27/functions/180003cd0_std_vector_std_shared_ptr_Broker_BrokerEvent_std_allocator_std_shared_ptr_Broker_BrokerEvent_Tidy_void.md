# std::vector<std::shared_ptr<Broker::BrokerEvent>,std::allocator<std::shared_ptr<Broker::BrokerEvent>>>::_Tidy(void)

- ea: `0x180003cd0`
- end: `0x180003da1`
- name: `?_Tidy@?$vector@V?$shared_ptr@VBrokerEvent@Broker@@@std@@V?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@2@@std@@AEAAXXZ`
- size: `209`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800012cc`
- `0x18000220c`
- `0x180002e88`
- `0x180003760`
- `0x180003a60`
- `0x18000efc4`

## callees

- `0x180003cd0`
- `0x180014898`
- `0x180015b58`
- `0x18001e010`

## pseudocode

```c
void __fastcall std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Tidy(void **a1)
{
  char *v1; // rbx
  char *v3; // rbp
  volatile signed __int32 *v4; // rsi
  char *v5; // rcx
  signed __int64 v6; // rdx
  void *v7; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  v1 = (char *)*a1;
  if ( *a1 )
  {
    v3 = (char *)a1[1];
    while ( v1 != v3 )
    {
      v4 = (volatile signed __int32 *)*((_QWORD *)v1 + 1);
      if ( v4 && _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
        if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      }
      v1 += 16;
    }
    v5 = (char *)*a1;
    v6 = (_BYTE *)a1[2] - (_BYTE *)*a1;
    v7 = *a1;
    v8 = v6 & 0xFFFFFFFFFFFFFFF0uLL;
    if ( (v6 & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v7, &v8);
      v5 = (char *)v7;
    }
    operator delete(v5);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x180003cd0  mov     [rsp+arg_10], rbx
0x180003cd5  push    rbp
0x180003cd6  push    rsi
0x180003cd7  push    rdi
0x180003cd8  sub     rsp, 20h
0x180003cdc  mov     rbx, [rcx]
0x180003cdf  mov     rdi, rcx
0x180003ce2  test    rbx, rbx
0x180003ce5  jz      loc_180003D79
0x180003ceb  mov     rbp, [rcx+8]
0x180003cef  jmp     short loc_180003D1F
0x180003cf1  mov     rax, [rsi]
0x180003cf4  mov     rcx, rsi
0x180003cf7  mov     rax, [rax]
0x180003cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cff  or      eax, 0FFFFFFFFh
0x180003d02  lock xadd [rsi+0Ch], eax
0x180003d07  cmp     eax, 1
0x180003d0a  jnz     short loc_180003D1B
0x180003d0c  mov     rax, [rsi]
0x180003d0f  mov     rcx, rsi
0x180003d12  mov     rax, [rax+8]
0x180003d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d1b  add     rbx, 10h
0x180003d1f  cmp     rbx, rbp
0x180003d22  jz      short loc_180003D3C
0x180003d24  mov     rsi, [rbx+8]
0x180003d28  test    rsi, rsi
0x180003d2b  jz      short loc_180003D1B
0x180003d2d  or      eax, 0FFFFFFFFh
0x180003d30  lock xadd [rsi+8], eax
0x180003d35  cmp     eax, 1
0x180003d38  jz      short loc_180003CF1
0x180003d3a  jmp     short loc_180003D1B
0x180003d3c  mov     rcx, [rdi]; void *
0x180003d3f  mov     rdx, [rdi+10h]
0x180003d43  sub     rdx, rcx
0x180003d46  mov     [rsp+38h+arg_0], rcx
0x180003d4b  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x180003d4f  mov     [rsp+38h+arg_8], rdx
0x180003d54  cmp     rdx, 1000h
0x180003d5b  jnb     short loc_180003D86
0x180003d5d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003d62  mov     qword ptr [rdi], 0
0x180003d69  mov     qword ptr [rdi+8], 0
0x180003d71  mov     qword ptr [rdi+10h], 0
0x180003d79  mov     rbx, [rsp+38h+arg_10]
0x180003d7e  add     rsp, 20h
0x180003d82  pop     rdi
0x180003d83  pop     rsi
0x180003d84  pop     rbp
0x180003d85  retn
0x180003d86  lea     rdx, [rsp+38h+arg_8]; unsigned __int64 *
0x180003d8b  lea     rcx, [rsp+38h+arg_0]; void **
0x180003d90  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180003d95  mov     rcx, [rsp+38h+arg_0]
0x180003d9a  mov     rdx, [rsp+38h+arg_8]
0x180003d9f  jmp     short loc_180003D5D
```
