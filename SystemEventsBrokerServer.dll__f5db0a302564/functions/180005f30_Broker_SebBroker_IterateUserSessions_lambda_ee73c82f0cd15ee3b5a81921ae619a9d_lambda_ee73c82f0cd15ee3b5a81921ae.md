# Broker::SebBroker::IterateUserSessions<_lambda_ee73c82f0cd15ee3b5a81921ae619a9d_>(_lambda_ee73c82f0cd15ee3b5a81921ae619a9d_)

- ea: `0x180005f30`
- end: `0x18000608b`
- name: `??$IterateUserSessions@V_lambda_ee73c82f0cd15ee3b5a81921ae619a9d_@@@SebBroker@Broker@@AEAAXV_lambda_ee73c82f0cd15ee3b5a81921ae619a9d_@@@Z`
- size: `347`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008c40`

## callees

- `0x180005f30`
- `0x180006d90`
- `0x1800076a0`
- `0x180027010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180005fcd`
- `ntdll!RtlEqualSid` at `0x180005fcd`

## pseudocode

```c
void __fastcall Broker::SebBroker::IterateUserSessions<_lambda_ee73c82f0cd15ee3b5a81921ae619a9d_>(
        __int64 a1,
        __int64 a2)
{
  __int64 *v4; // rbx
  __int64 v5; // rax
  __int64 **v6; // rcx
  __int64 *j; // rcx
  __int64 v8; // rcx
  __int64 v9; // rsi
  volatile signed __int32 *v10; // rdi
  _QWORD *v11; // rax
  std::_Ref_count_base *v12; // rcx
  __int64 *i; // rax
  __int64 v14; // [rsp+40h] [rbp+8h] BYREF

  v4 = **(__int64 ***)(a1 + 16);
  while ( v4 != *(__int64 **)(a1 + 16) )
  {
    v5 = **(_QWORD **)v4[5];
    v14 = v5;
    while ( v5 != *(_QWORD *)v4[5] )
    {
      if ( *(_QWORD *)(v5 + 40) )
      {
        v8 = *(_QWORD *)(v5 + 48);
        if ( v8 )
          _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
        v9 = *(_QWORD *)(v5 + 40);
        v10 = *(volatile signed __int32 **)(v5 + 48);
        if ( *(_DWORD *)(v9 + 40) == *(_DWORD *)(a2 + 8) && RtlEqualSid(*(PSID *)v9, *(PSID *)(a2 + 16)) )
        {
          v11 = *(_QWORD **)a2;
          if ( v10 )
            _InterlockedIncrement(v10 + 2);
          *v11 = v9;
          v12 = (std::_Ref_count_base *)v11[1];
          v11[1] = v10;
          if ( v12 )
            std::_Ref_count_base::_Decref(v12);
        }
        if ( v10 )
        {
          if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
            if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
          }
        }
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(&v14);
      v5 = v14;
    }
    v6 = (__int64 **)v4[2];
    if ( *((_BYTE *)v6 + 25) )
    {
      for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
      {
        if ( v4 != (__int64 *)i[2] )
          break;
        v4 = i;
      }
      v4 = i;
    }
    else
    {
      v4 = (__int64 *)v4[2];
      for ( j = *v6; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v4 = j;
    }
  }
}

```

## disassembly

```asm
0x180005f30  mov     [rsp+arg_8], rbx
0x180005f35  mov     [rsp+arg_10], rbp
0x180005f3a  push    rsi
0x180005f3b  push    rdi
0x180005f3c  push    r14
0x180005f3e  sub     rsp, 20h
0x180005f42  mov     rbx, [rcx+10h]
0x180005f46  mov     r14, rdx
0x180005f49  mov     rbp, rcx
0x180005f4c  mov     rbx, [rbx]
0x180005f4f  nop
0x180005f50  cmp     rbx, [rbp+10h]
0x180005f54  jz      loc_18000604C
0x180005f5a  mov     rax, [rbx+28h]
0x180005f5e  mov     rax, [rax]
0x180005f61  mov     rax, [rax]
0x180005f64  mov     [rsp+38h+arg_0], rax
0x180005f69  mov     rcx, [rbx+28h]
0x180005f6d  cmp     rax, [rcx]
0x180005f70  jnz     short loc_180005F9D
0x180005f72  mov     rcx, [rbx+10h]
0x180005f76  cmp     byte ptr [rcx+19h], 0
0x180005f7a  jnz     loc_18000605F
0x180005f80  mov     rbx, rcx
0x180005f83  mov     rcx, [rcx]
0x180005f86  cmp     byte ptr [rcx+19h], 0
0x180005f8a  jnz     short loc_180005F50
0x180005f8c  mov     rax, [rcx]
0x180005f8f  mov     rbx, rcx
0x180005f92  mov     rcx, rax
0x180005f95  cmp     byte ptr [rax+19h], 0
0x180005f99  jz      short loc_180005F8C
0x180005f9b  jmp     short loc_180005F50
0x180005f9d  cmp     qword ptr [rax+28h], 0
0x180005fa2  jz      loc_180006038
0x180005fa8  mov     rcx, [rax+30h]
0x180005fac  test    rcx, rcx
0x180005faf  jz      short loc_180005FB5
0x180005fb1  lock inc dword ptr [rcx+8]
0x180005fb5  mov     rsi, [rax+28h]
0x180005fb9  mov     rdi, [rax+30h]
0x180005fbd  mov     eax, [r14+8]
0x180005fc1  cmp     [rsi+28h], eax
0x180005fc4  jnz     short loc_180005FF8
0x180005fc6  mov     rdx, [r14+10h]; Sid2
0x180005fca  mov     rcx, [rsi]; Sid1
0x180005fcd  call    cs:__imp_RtlEqualSid
0x180005fd3  test    al, al
0x180005fd5  jz      short loc_180005FF8
0x180005fd7  mov     rax, [r14]
0x180005fda  test    rdi, rdi
0x180005fdd  jz      short loc_180005FE3
0x180005fdf  lock inc dword ptr [rdi+8]
0x180005fe3  mov     [rax], rsi
0x180005fe6  mov     rcx, [rax+8]; this
0x180005fea  mov     [rax+8], rdi
0x180005fee  test    rcx, rcx
0x180005ff1  jz      short loc_180005FF8
0x180005ff3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180005ff8  test    rdi, rdi
0x180005ffb  jz      short loc_180006038
0x180005ffd  mov     eax, 0FFFFFFFFh
0x180006002  lock xadd [rdi+8], eax
0x180006007  cmp     eax, 1
0x18000600a  jnz     short loc_180006038
0x18000600c  mov     rax, [rdi]
0x18000600f  mov     rcx, rdi
0x180006012  mov     rax, [rax]
0x180006015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000601a  mov     eax, 0FFFFFFFFh
0x18000601f  lock xadd [rdi+0Ch], eax
0x180006024  cmp     eax, 1
0x180006027  jnz     short loc_180006038
0x180006029  mov     rax, [rdi]
0x18000602c  mov     rcx, rdi
0x18000602f  mov     rax, [rax+8]
0x180006033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006038  lea     rcx, [rsp+38h+arg_0]
0x18000603d  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)
0x180006042  mov     rax, [rsp+38h+arg_0]
0x180006047  jmp     loc_180005F69
0x18000604c  mov     rbx, [rsp+38h+arg_8]
0x180006051  mov     rbp, [rsp+38h+arg_10]
0x180006056  add     rsp, 20h
0x18000605a  pop     r14
0x18000605c  pop     rdi
0x18000605d  pop     rsi
0x18000605e  retn
0x18000605f  mov     rax, [rbx+8]
0x180006063  cmp     byte ptr [rax+19h], 0
0x180006067  jnz     short loc_180006083
0x180006069  nop     dword ptr [rax+00000000h]
0x180006070  cmp     rbx, [rax+10h]
0x180006074  jnz     short loc_180006083
0x180006076  mov     rbx, rax
0x180006079  mov     rax, [rax+8]
0x18000607d  cmp     byte ptr [rax+19h], 0
0x180006081  jz      short loc_180006070
0x180006083  mov     rbx, rax
0x180006086  jmp     loc_180005F50
```
