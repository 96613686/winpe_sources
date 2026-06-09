# Broker::SebBroker::OnDeleteEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)

- ea: `0x18000e4f0`
- end: `0x18000e75c`
- name: `?OnDeleteEvent@SebBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z`
- size: `620`
- prototype: `static unsigned int __high(enum _BR_EVENT_CALL_REASON, struct _BROKER *, struct _BROKERED_EVENT *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180005a50`
- `0x18000e4f0`
- `0x18000e79c`
- `0x18000e804`
- `0x180011590`
- `0x18001cf50`
- `0x180027010`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x18000e6f3`
- `ntdll!NtDeleteWnfStateName` at `0x18000e6f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Broker::SebBroker::OnDeleteEvent(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  _QWORD *v7; // rcx
  __int128 v8; // xmm0
  unsigned int v9; // esi
  volatile signed __int32 *v10; // rbx
  unsigned __int64 v12; // rax
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // [rsp+20h] [rbp-48h] BYREF
  __int64 v16; // [rsp+28h] [rbp-40h]
  __int128 v17; // [rsp+30h] [rbp-38h]
  __int64 v18; // [rsp+48h] [rbp-20h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( Broker::SebBroker::Instance && *(_BYTE *)Broker::SebBroker::Instance )
  {
    if ( *(&Broker::SebBroker::Instance + 1) )
    {
      _InterlockedIncrement((volatile signed __int32 *)*(&Broker::SebBroker::Instance + 1) + 2);
      v7 = WPP_GLOBAL_Control;
    }
    v8 = *(_OWORD *)&Broker::SebBroker::Instance;
  }
  else
  {
    v8 = 0;
  }
  v17 = v8;
  if ( a2 && a3 && a4 )
  {
    if ( (_QWORD)v8 )
    {
      v9 = 0;
      if ( *(_QWORD *)(v8 + 136) == a2 )
      {
        v15 = *(_QWORD *)(v8 + 136);
        v16 = 0;
        Broker::BrokerLock::Acquire((Broker::BrokerLock *)&v15);
        v12 = (unsigned int)(*(_DWORD *)(*a4 + 96LL) - 14);
        if ( (unsigned int)v12 <= 0x3D )
        {
          v13 = 0x3FD7D87934DC08D9LL;
          if ( _bittest64(&v13, v12) )
          {
            if ( *(_QWORD *)(*a4 + 124LL) )
            {
              v18 = *(_QWORD *)(*a4 + 124LL);
              v14 = NtDeleteWnfStateName(&v18);
              v9 = v14;
              if ( v14 < 0
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  125,
                  &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
                  (unsigned int)v14);
              }
            }
          }
        }
        std::shared_ptr<Broker::SebEvent>::`scalar deleting destructor'(a4);
        if ( HIDWORD(v16) )
          Broker::BrokerLock::Release((Broker::BrokerLock *)&v15);
        v7 = WPP_GLOBAL_Control;
      }
      else
      {
        v9 = 5;
      }
    }
    else
    {
      v9 = 21;
    }
  }
  else
  {
    v9 = 87;
  }
  if ( (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 4u )
    WPP_SF_d(v7[2], 127, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v9);
  v10 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
  if ( *((_QWORD *)&v17 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18000e4f0  mov     [rsp+arg_0], rbx
0x18000e4f5  mov     [rsp+arg_8], rsi
0x18000e4fa  push    rdi
0x18000e4fb  sub     rsp, 60h
0x18000e4ff  mov     rax, cs:__security_cookie
0x18000e506  xor     rax, rsp
0x18000e509  mov     [rsp+68h+var_18], rax
0x18000e50e  mov     rdi, r9
0x18000e511  mov     rsi, r8
0x18000e514  mov     rbx, rdx
0x18000e517  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e51e  test    byte ptr [rcx+1Ch], 1
0x18000e522  jz      short loc_18000E52E
0x18000e524  cmp     byte ptr [rcx+19h], 4
0x18000e528  jnb     loc_18000E676
0x18000e52e  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x18000e535  test    rax, rax
0x18000e538  jz      loc_18000E662
0x18000e53e  cmp     byte ptr [rax], 0
0x18000e541  jz      loc_18000E662
0x18000e547  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x18000e54e  test    rax, rax
0x18000e551  jz      short loc_18000E55E
0x18000e553  lock inc dword ptr [rax+8]
0x18000e557  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e55e  movups  xmm0, cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x18000e565  movdqu  [rsp+68h+var_38], xmm0
0x18000e56b  test    rbx, rbx
0x18000e56e  jnz     short loc_18000E5E0
0x18000e570  mov     esi, 57h ; 'W'
0x18000e575  test    byte ptr [rcx+1Ch], 1
0x18000e579  jnz     loc_18000E697
0x18000e57f  mov     rbx, qword ptr [rsp+68h+var_38+8]
0x18000e584  test    rbx, rbx
0x18000e587  jz      short loc_18000E5C1
0x18000e589  mov     edi, 0FFFFFFFFh
0x18000e58e  mov     eax, edi
0x18000e590  lock xadd [rbx+8], eax
0x18000e595  cmp     eax, 1
0x18000e598  jnz     short loc_18000E5C1
0x18000e59a  mov     rax, [rbx]
0x18000e59d  mov     rcx, rbx
0x18000e5a0  mov     rax, [rax]
0x18000e5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5a8  lock xadd [rbx+0Ch], edi
0x18000e5ad  cmp     edi, 1
0x18000e5b0  jnz     short loc_18000E5C1
0x18000e5b2  mov     rax, [rbx]
0x18000e5b5  mov     rcx, rbx
0x18000e5b8  mov     rax, [rax+8]
0x18000e5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5c1  mov     eax, esi
0x18000e5c3  mov     rcx, [rsp+68h+var_18]
0x18000e5c8  xor     rcx, rsp; StackCookie
0x18000e5cb  call    __security_check_cookie
0x18000e5d0  mov     rbx, [rsp+68h+arg_0]
0x18000e5d5  mov     rsi, [rsp+68h+arg_8]
0x18000e5da  add     rsp, 60h
0x18000e5de  pop     rdi
0x18000e5df  retn
0x18000e5e0  test    rsi, rsi
0x18000e5e3  jz      short loc_18000E570
0x18000e5e5  test    rdi, rdi
0x18000e5e8  jz      short loc_18000E570
0x18000e5ea  movq    rax, xmm0
0x18000e5ef  test    rax, rax
0x18000e5f2  jz      loc_18000E6BE
0x18000e5f8  xor     edx, edx
0x18000e5fa  mov     esi, edx
0x18000e5fc  cmp     [rax+88h], rbx
0x18000e603  jnz     loc_18000E6C8
0x18000e609  mov     rax, [rax+88h]
0x18000e610  mov     [rsp+68h+var_48], rax
0x18000e615  mov     [rsp+68h+var_40], rdx
0x18000e61a  lea     rcx, [rsp+68h+var_48]; this
0x18000e61f  call    ?Acquire@BrokerLock@Broker@@QEAAXXZ; Broker::BrokerLock::Acquire(void)
0x18000e624  mov     rcx, [rdi]
0x18000e627  mov     eax, [rcx+60h]
0x18000e62a  add     eax, 0FFFFFFF2h
0x18000e62d  cmp     eax, 3Dh ; '='
0x18000e630  ja      short loc_18000E646
0x18000e632  mov     rdx, 3FD7D87934DC08D9h
0x18000e63c  bt      rdx, rax
0x18000e640  jb      loc_18000E6D2
0x18000e646  mov     rcx, rdi; void *
0x18000e649  call    ??_G?$shared_ptr@VSebEvent@Broker@@@std@@QEAAPEAXI@Z; std::shared_ptr<Broker::SebEvent>::`scalar deleting destructor'(uint)
0x18000e64e  nop
0x18000e64f  cmp     dword ptr [rsp+68h+var_40+4], 0
0x18000e654  jnz     short loc_18000E66A
0x18000e656  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e65d  jmp     loc_18000E575
0x18000e662  xorps   xmm0, xmm0
0x18000e665  jmp     loc_18000E565
0x18000e66a  lea     rcx, [rsp+68h+var_48]; this
0x18000e66f  call    ?Release@BrokerLock@Broker@@QEAAXXZ; Broker::BrokerLock::Release(void)
0x18000e674  jmp     short loc_18000E656
0x18000e676  mov     edx, 7Ch ; '|'
0x18000e67b  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000e682  mov     rcx, [rcx+10h]
0x18000e686  call    WPP_SF_
0x18000e68b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e692  jmp     loc_18000E52E
0x18000e697  cmp     byte ptr [rcx+19h], 4
0x18000e69b  jb      loc_18000E57F
0x18000e6a1  mov     edx, 7Fh
0x18000e6a6  mov     r9d, esi
0x18000e6a9  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000e6b0  mov     rcx, [rcx+10h]
0x18000e6b4  call    WPP_SF_d
0x18000e6b9  jmp     loc_18000E57F
0x18000e6be  mov     esi, 15h
0x18000e6c3  jmp     loc_18000E575
0x18000e6c8  mov     esi, 5
0x18000e6cd  jmp     loc_18000E575
0x18000e6d2  mov     rdx, [rcx+7Ch]
0x18000e6d6  test    edx, edx
0x18000e6d8  jnz     short loc_18000E6E9
0x18000e6da  mov     rax, rdx
0x18000e6dd  shr     rax, 20h
0x18000e6e1  test    eax, eax
0x18000e6e3  jz      loc_18000E646
0x18000e6e9  mov     [rsp+68h+var_20], rdx
0x18000e6ee  lea     rcx, [rsp+68h+var_20]
0x18000e6f3  call    cs:__imp_NtDeleteWnfStateName
0x18000e6f9  mov     esi, eax
0x18000e6fb  test    eax, eax
0x18000e6fd  jns     loc_18000E646
0x18000e703  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e70a  test    byte ptr [rcx+1Ch], 20h
0x18000e70e  jz      loc_18000E646
0x18000e714  cmp     byte ptr [rcx+19h], 2
0x18000e718  jb      loc_18000E646
0x18000e71e  mov     edx, 7Dh ; '}'
0x18000e723  mov     r9d, eax
0x18000e726  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000e72d  mov     rcx, [rcx+10h]
0x18000e731  call    WPP_SF_d
0x18000e736  jmp     loc_18000E646
0x18000e73b  mov     esi, dword ptr [rsp+68h+var_20]
0x18000e73f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e746  jmp     loc_18000E575
0x18000e74b  mov     esi, dword ptr [rsp+68h+var_20]
0x18000e74f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e756  jmp     loc_18000E575
```
