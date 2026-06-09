# Broker::SebBroker::GetSessionID(void * const)

- ea: `0x180006c50`
- end: `0x180006d7b`
- name: `?GetSessionID@SebBroker@Broker@@AEAAKQEAX@Z`
- size: `299`
- prototype: `__int64 __fastcall(Broker::SebBroker *this, void *const)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800022b0`
- `0x180016590`

## callees

- `0x180006c50`
- `0x180006d90`
- `0x180027010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180006ce1`
- `ntdll!RtlEqualSid` at `0x180006ce1`

## pseudocode

```c
__int64 __fastcall Broker::SebBroker::GetSessionID(Broker::SebBroker *this, void *const a2)
{
  unsigned int v4; // ebp
  __int64 *v5; // rbx
  __int64 v6; // rax
  __int64 **v7; // rcx
  __int64 *j; // rcx
  __int64 v9; // rcx
  __int64 v10; // rsi
  volatile signed __int32 *v11; // rdi
  __int64 *i; // rax
  __int64 v14; // [rsp+58h] [rbp+10h] BYREF

  v4 = -1;
  v5 = (__int64 *)**((_QWORD **)this + 2);
  while ( v5 != *((__int64 **)this + 2) )
  {
    v6 = **(_QWORD **)v5[5];
    v14 = v6;
    while ( v6 != *(_QWORD *)v5[5] )
    {
      if ( *(_QWORD *)(v6 + 40) )
      {
        v9 = *(_QWORD *)(v6 + 48);
        if ( v9 )
          _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
        v10 = *(_QWORD *)(v6 + 40);
        v11 = *(volatile signed __int32 **)(v6 + 48);
        if ( RtlEqualSid(*(PSID *)v10, a2) )
          v4 = *(_DWORD *)(v10 + 40);
        if ( v11 )
        {
          if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
          }
        }
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(&v14);
      v6 = v14;
    }
    v7 = (__int64 **)v5[2];
    if ( *((_BYTE *)v7 + 25) )
    {
      for ( i = (__int64 *)v5[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
      {
        if ( v5 != (__int64 *)i[2] )
          break;
        v5 = i;
      }
      v5 = i;
    }
    else
    {
      v5 = (__int64 *)v5[2];
      for ( j = *v7; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v5 = j;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180006c50  mov     [rsp+arg_10], rbx
0x180006c55  push    rbp
0x180006c56  push    rsi
0x180006c57  push    rdi
0x180006c58  push    r14
0x180006c5a  push    r15
0x180006c5c  sub     rsp, 20h
0x180006c60  mov     rbx, [rcx+10h]
0x180006c64  mov     r15, rdx
0x180006c67  mov     r14, rcx
0x180006c6a  mov     ebp, 0FFFFFFFFh
0x180006c6f  mov     rbx, [rbx]
0x180006c72  cmp     rbx, [r14+10h]
0x180006c76  jz      loc_180006D42
0x180006c7c  mov     rax, [rbx+28h]
0x180006c80  mov     rax, [rax]
0x180006c83  mov     rax, [rax]
0x180006c86  mov     [rsp+48h+arg_8], rax
0x180006c8b  mov     rcx, [rbx+28h]
0x180006c8f  cmp     rax, [rcx]
0x180006c92  jnz     short loc_180006CBF
0x180006c94  mov     rcx, [rbx+10h]
0x180006c98  cmp     byte ptr [rcx+19h], 0
0x180006c9c  jnz     loc_180006D55
0x180006ca2  mov     rbx, rcx
0x180006ca5  mov     rcx, [rcx]
0x180006ca8  cmp     byte ptr [rcx+19h], 0
0x180006cac  jnz     short loc_180006C72
0x180006cae  mov     rax, [rcx]
0x180006cb1  mov     rbx, rcx
0x180006cb4  mov     rcx, rax
0x180006cb7  cmp     byte ptr [rax+19h], 0
0x180006cbb  jz      short loc_180006CAE
0x180006cbd  jmp     short loc_180006C72
0x180006cbf  cmp     qword ptr [rax+28h], 0
0x180006cc4  jz      short loc_180006D2E
0x180006cc6  mov     rcx, [rax+30h]
0x180006cca  test    rcx, rcx
0x180006ccd  jz      short loc_180006CD3
0x180006ccf  lock inc dword ptr [rcx+8]
0x180006cd3  mov     rsi, [rax+28h]
0x180006cd7  mov     rdx, r15; Sid2
0x180006cda  mov     rdi, [rax+30h]
0x180006cde  mov     rcx, [rsi]; Sid1
0x180006ce1  call    cs:__imp_RtlEqualSid
0x180006ce7  test    al, al
0x180006ce9  jz      short loc_180006CEE
0x180006ceb  mov     ebp, [rsi+28h]
0x180006cee  test    rdi, rdi
0x180006cf1  jz      short loc_180006D2E
0x180006cf3  mov     eax, 0FFFFFFFFh
0x180006cf8  lock xadd [rdi+8], eax
0x180006cfd  cmp     eax, 1
0x180006d00  jnz     short loc_180006D2E
0x180006d02  mov     rax, [rdi]
0x180006d05  mov     rcx, rdi
0x180006d08  mov     rax, [rax]
0x180006d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d10  mov     eax, 0FFFFFFFFh
0x180006d15  lock xadd [rdi+0Ch], eax
0x180006d1a  cmp     eax, 1
0x180006d1d  jnz     short loc_180006D2E
0x180006d1f  mov     rax, [rdi]
0x180006d22  mov     rcx, rdi
0x180006d25  mov     rax, [rax+8]
0x180006d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d2e  lea     rcx, [rsp+48h+arg_8]
0x180006d33  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)
0x180006d38  mov     rax, [rsp+48h+arg_8]
0x180006d3d  jmp     loc_180006C8B
0x180006d42  mov     rbx, [rsp+48h+arg_10]
0x180006d47  mov     eax, ebp
0x180006d49  add     rsp, 20h
0x180006d4d  pop     r15
0x180006d4f  pop     r14
0x180006d51  pop     rdi
0x180006d52  pop     rsi
0x180006d53  pop     rbp
0x180006d54  retn
0x180006d55  mov     rax, [rbx+8]
0x180006d59  cmp     byte ptr [rax+19h], 0
0x180006d5d  jnz     short loc_180006D73
0x180006d5f  nop
0x180006d60  cmp     rbx, [rax+10h]
0x180006d64  jnz     short loc_180006D73
0x180006d66  mov     rbx, rax
0x180006d69  mov     rax, [rax+8]
0x180006d6d  cmp     byte ptr [rax+19h], 0
0x180006d71  jz      short loc_180006D60
0x180006d73  mov     rbx, rax
0x180006d76  jmp     loc_180006C72
```
