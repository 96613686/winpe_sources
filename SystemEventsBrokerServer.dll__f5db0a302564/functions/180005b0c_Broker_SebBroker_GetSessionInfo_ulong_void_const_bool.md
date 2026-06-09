# Broker::SebBroker::GetSessionInfo(ulong,void * const,bool)

- ea: `0x180005b0c`
- end: `0x180005cb5`
- name: `?GetSessionInfo@SebBroker@Broker@@QEAA?AV?$shared_ptr@U_SessionInfo@Broker@@@std@@KQEAX_N@Z`
- size: `425`
- prototype: `_QWORD *(__int64, _QWORD *, int, ...)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001ef0`
- `0x1800022b0`
- `0x180017f40`

## callees

- `0x180005b0c`
- `0x180006d90`
- `0x1800076a0`
- `0x180027010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180005bc3`
- `ntdll!RtlEqualSid` at `0x180005bc3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005b56`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005b56`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005c97`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005c97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b5c`

## pseudocode

```c
_QWORD *Broker::SebBroker::GetSessionInfo(__int64 a1, _QWORD *a2, int a3, ...)
{
  char v3; // r15
  PSID v7; // rbp
  __int64 *v8; // rbx
  _QWORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rsi
  volatile signed __int32 *v12; // rdi
  std::_Ref_count_base *v13; // rcx
  __int64 **v14; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v18; // [rsp+60h] [rbp+8h]
  PSID Sid2; // [rsp+78h] [rbp+20h] BYREF
  va_list Sid2a; // [rsp+78h] [rbp+20h]
  __int64 v21; // [rsp+80h] [rbp+28h]
  va_list va1; // [rsp+88h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(Sid2a, a3);
  Sid2 = va_arg(va1, PSID);
  v21 = va_arg(va1, _QWORD);
  v3 = 0;
  *a2 = 0;
  a2[1] = 0;
  v18 = a1 + 8;
  if ( (_BYTE)v21 )
  {
    RtlAcquireSRWLockExclusive(a1 + 8);
    GetCurrentThreadId();
    v3 = 1;
  }
  v7 = Sid2;
  v8 = **(__int64 ***)(a1 + 16);
  while ( v8 != *(__int64 **)(a1 + 16) )
  {
    v9 = **(_QWORD ***)v8[5];
    Sid2 = v9;
    while ( v9 != *(_QWORD **)v8[5] )
    {
      if ( v9[5] )
      {
        v10 = v9[6];
        if ( v10 )
          _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
        v11 = v9[5];
        v12 = (volatile signed __int32 *)v9[6];
        if ( *(_DWORD *)(v11 + 40) == a3 && RtlEqualSid(*(PSID *)v11, v7) )
        {
          if ( v12 )
            _InterlockedIncrement(v12 + 2);
          *a2 = v11;
          v13 = (std::_Ref_count_base *)a2[1];
          a2[1] = v12;
          if ( v13 )
            std::_Ref_count_base::_Decref(v13);
        }
        if ( v12 && _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++((__int64 *)Sid2a);
      v9 = Sid2;
    }
    v14 = (__int64 **)v8[2];
    if ( *((_BYTE *)v14 + 25) )
    {
      for ( i = (__int64 *)v8[1]; !*((_BYTE *)i + 25) && v8 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v8 = i;
      v8 = i;
    }
    else
    {
      v8 = (__int64 *)v8[2];
      for ( j = *v14; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v8 = j;
    }
  }
  if ( v3 )
    RtlReleaseSRWLockExclusive(v18);
  return a2;
}

```

## disassembly

```asm
0x180005b0c  mov     [rsp+arg_8], rbx
0x180005b11  mov     [rsp+Sid2], r9
0x180005b16  push    rbp
0x180005b17  push    rsi
0x180005b18  push    rdi
0x180005b19  push    r12
0x180005b1b  push    r13
0x180005b1d  push    r14
0x180005b1f  push    r15
0x180005b21  sub     rsp, 20h
0x180005b25  xor     r15b, r15b
0x180005b28  mov     qword ptr [rdx], 0
0x180005b2f  lea     rbp, [rcx+8]
0x180005b33  mov     r12d, r8d
0x180005b36  mov     r14, rdx
0x180005b39  mov     r13, rcx
0x180005b3c  mov     qword ptr [rdx+8], 0
0x180005b44  mov     [rsp+58h+arg_0], rbp
0x180005b49  cmp     byte ptr [rsp+58h+arg_20], r15b
0x180005b51  jz      short loc_180005B65
0x180005b53  mov     rcx, rbp
0x180005b56  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180005b5c  call    cs:__imp_GetCurrentThreadId
0x180005b62  mov     r15b, 1
0x180005b65  mov     rbx, [r13+10h]
0x180005b69  mov     rbp, [rsp+58h+Sid2]
0x180005b6e  mov     rbx, [rbx]
0x180005b71  cmp     rbx, [r13+10h]
0x180005b75  jz      loc_180005C8A
0x180005b7b  mov     rax, [rbx+28h]
0x180005b7f  mov     rax, [rax]
0x180005b82  mov     rax, [rax]
0x180005b85  mov     [rsp+58h+Sid2], rax
0x180005b8a  mov     rcx, [rbx+28h]
0x180005b8e  cmp     rax, [rcx]
0x180005b91  jz      loc_180005C3B
0x180005b97  cmp     qword ptr [rax+28h], 0
0x180005b9c  jz      loc_180005C27
0x180005ba2  mov     rcx, [rax+30h]
0x180005ba6  test    rcx, rcx
0x180005ba9  jz      short loc_180005BAF
0x180005bab  lock inc dword ptr [rcx+8]
0x180005baf  mov     rsi, [rax+28h]
0x180005bb3  mov     rdi, [rax+30h]
0x180005bb7  cmp     [rsi+28h], r12d
0x180005bbb  jnz     short loc_180005BEB
0x180005bbd  mov     rcx, [rsi]; Sid1
0x180005bc0  mov     rdx, rbp; Sid2
0x180005bc3  call    cs:__imp_RtlEqualSid
0x180005bc9  test    al, al
0x180005bcb  jz      short loc_180005BEB
0x180005bcd  test    rdi, rdi
0x180005bd0  jz      short loc_180005BD6
0x180005bd2  lock inc dword ptr [rdi+8]
0x180005bd6  mov     [r14], rsi
0x180005bd9  mov     rcx, [r14+8]; this
0x180005bdd  mov     [r14+8], rdi
0x180005be1  test    rcx, rcx
0x180005be4  jz      short loc_180005BEB
0x180005be6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180005beb  test    rdi, rdi
0x180005bee  jz      short loc_180005C27
0x180005bf0  or      eax, 0FFFFFFFFh
0x180005bf3  lock xadd [rdi+8], eax
0x180005bf8  cmp     eax, 1
0x180005bfb  jnz     short loc_180005C27
0x180005bfd  mov     rax, [rdi]
0x180005c00  mov     rcx, rdi
0x180005c03  mov     rax, [rax]
0x180005c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c0b  or      eax, 0FFFFFFFFh
0x180005c0e  lock xadd [rdi+0Ch], eax
0x180005c13  cmp     eax, 1
0x180005c16  jnz     short loc_180005C27
0x180005c18  mov     rax, [rdi]
0x180005c1b  mov     rcx, rdi
0x180005c1e  mov     rax, [rax+8]
0x180005c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c27  lea     rcx, [rsp+58h+Sid2]
0x180005c2c  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)
0x180005c31  mov     rax, [rsp+58h+Sid2]
0x180005c36  jmp     loc_180005B8A
0x180005c3b  mov     rcx, [rbx+10h]
0x180005c3f  cmp     byte ptr [rcx+19h], 0
0x180005c43  jz      short loc_180005C66
0x180005c45  mov     rax, [rbx+8]
0x180005c49  jmp     short loc_180005C58
0x180005c4b  cmp     rbx, [rax+10h]
0x180005c4f  jnz     short loc_180005C5E
0x180005c51  mov     rbx, rax
0x180005c54  mov     rax, [rax+8]
0x180005c58  cmp     byte ptr [rax+19h], 0
0x180005c5c  jz      short loc_180005C4B
0x180005c5e  mov     rbx, rax
0x180005c61  jmp     loc_180005B71
0x180005c66  mov     rbx, rcx
0x180005c69  mov     rcx, [rcx]
0x180005c6c  cmp     byte ptr [rcx+19h], 0
0x180005c70  jnz     loc_180005B71
0x180005c76  mov     rax, [rcx]
0x180005c79  mov     rbx, rcx
0x180005c7c  mov     rcx, rax
0x180005c7f  cmp     byte ptr [rax+19h], 0
0x180005c83  jz      short loc_180005C76
0x180005c85  jmp     loc_180005B71
0x180005c8a  mov     rbp, [rsp+58h+arg_0]
0x180005c8f  test    r15b, r15b
0x180005c92  jz      short loc_180005C9D
0x180005c94  mov     rcx, rbp
0x180005c97  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180005c9d  mov     rbx, [rsp+58h+arg_8]
0x180005ca2  mov     rax, r14
0x180005ca5  add     rsp, 20h
0x180005ca9  pop     r15
0x180005cab  pop     r14
0x180005cad  pop     r13
0x180005caf  pop     r12
0x180005cb1  pop     rdi
0x180005cb2  pop     rsi
0x180005cb3  pop     rbp
0x180005cb4  retn
```
