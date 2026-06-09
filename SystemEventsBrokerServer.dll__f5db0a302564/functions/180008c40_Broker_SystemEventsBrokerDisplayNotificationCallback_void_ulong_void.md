# Broker::SystemEventsBrokerDisplayNotificationCallback(void *,ulong,void *)

- ea: `0x180008c40`
- end: `0x180009061`
- name: `?SystemEventsBrokerDisplayNotificationCallback@Broker@@YAKPEAXK0@Z`
- size: `1057`
- prototype: `unsigned int __fastcall(Broker *__hidden this, void *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180005a50`
- `0x180005f30`
- `0x1800076a0`
- `0x180008c40`
- `0x18001cf50`
- `0x1800223e0`
- `0x180027010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008d34`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008d34`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008e02`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008e02`
- `ntdll!RtlPublishWnfStateData` at `0x180008dd0`
- `ntdll!RtlPublishWnfStateData` at `0x180008dd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d3a`

## pseudocode

```c
__int64 __fastcall Broker::SystemEventsBrokerDisplayNotificationCallback(Broker *this, void *a2, __int64 a3, void *a4)
{
  _QWORD *v6; // rcx
  Broker::SebBroker *v7; // rdi
  volatile signed __int32 *v8; // rbx
  unsigned int v9; // r15d
  __int64 v10; // rax
  int v11; // eax
  unsigned __int8 v12; // r14
  __int64 v13; // rbp
  __int64 v14; // rcx
  __int64 v16; // rdx
  std::_Ref_count_base *v17[2]; // [rsp+30h] [rbp-1058h] BYREF
  std::_Ref_count_base **v18; // [rsp+40h] [rbp-1048h] BYREF
  unsigned int v19; // [rsp+48h] [rbp-1040h]
  __int64 v20; // [rsp+50h] [rbp-1038h]
  _DWORD v21[1024]; // [rsp+60h] [rbp-1028h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    v7 = Broker::SebBroker::Instance;
    if ( !Broker::SebBroker::Instance || !*(_BYTE *)Broker::SebBroker::Instance )
    {
      v8 = 0;
      goto LABEL_24;
    }
    v8 = (volatile signed __int32 *)*(&Broker::SebBroker::Instance + 1);
    v9 = *((_DWORD *)this + 10);
    if ( *(&Broker::SebBroker::Instance + 1) )
    {
      _InterlockedIncrement((volatile signed __int32 *)*(&Broker::SebBroker::Instance + 1) + 2);
      v6 = WPP_GLOBAL_Control;
      v8 = (volatile signed __int32 *)*(&Broker::SebBroker::Instance + 1);
      v7 = Broker::SebBroker::Instance;
    }
    if ( v7 )
    {
      v10 = *(_QWORD *)a3 - *(_QWORD *)&GUID_MONITOR_POWER_ON.Data1;
      if ( *(_QWORD *)a3 == *(_QWORD *)&GUID_MONITOR_POWER_ON.Data1 )
        v10 = *(_QWORD *)(a3 + 8) - *(_QWORD *)GUID_MONITOR_POWER_ON.Data4;
      if ( v10 )
      {
        v11 = *(_DWORD *)(a3 + 20);
        if ( !v11 )
        {
          if ( (*((_BYTE *)v6 + 28) & 0x10) != 0 && *((_BYTE *)v6 + 25) >= 4u )
            WPP_SF_d(v6[2], 40, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v9);
          goto LABEL_13;
        }
        if ( v11 == 2 )
        {
          if ( (*((_BYTE *)v6 + 28) & 0x10) == 0 || *((_BYTE *)v6 + 25) < 4u )
            goto LABEL_32;
          v16 = 41;
        }
        else
        {
          if ( (*((_BYTE *)v6 + 28) & 0x10) == 0 || *((_BYTE *)v6 + 25) < 4u )
            goto LABEL_32;
          v16 = 42;
        }
        WPP_SF_d(v6[2], v16, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v9);
      }
      else
      {
        if ( !*(_DWORD *)(a3 + 20) )
        {
          if ( (*((_BYTE *)v6 + 28) & 0x10) == 0 || *((_BYTE *)v6 + 25) < 4u )
          {
LABEL_13:
            v12 = 0;
            goto LABEL_14;
          }
          WPP_SF_(v6[2], 38, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
          v12 = 0;
LABEL_14:
          v13 = *(_QWORD *)this;
          RtlAcquireSRWLockExclusive((char *)v7 + 8);
          GetCurrentThreadId();
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v9);
          v19 = v9;
          v18 = v17;
          *(_OWORD *)v17 = 0;
          v20 = v13;
          Broker::SebBroker::IterateUserSessions<_lambda_ee73c82f0cd15ee3b5a81921ae619a9d_>((__int64)v7, (__int64)&v18);
          if ( v17[0] )
          {
            *((_BYTE *)v17[0] + 18) = v12;
            if ( *((_DWORD *)v17[0] + 14) || *((_DWORD *)v17[0] + 15) )
            {
              v14 = *((_QWORD *)v17[0] + 7);
              v21[1] = v9;
              v21[0] = (2 * v12) | 1;
              RtlPublishWnfStateData(v14, 0, v21, 8, 0);
            }
          }
          if ( v17[1] )
            std::_Ref_count_base::_Decref(v17[1]);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v9);
          RtlReleaseSRWLockExclusive((char *)v7 + 8);
          v6 = WPP_GLOBAL_Control;
          goto LABEL_24;
        }
        if ( (*((_BYTE *)v6 + 28) & 0x10) != 0 && *((_BYTE *)v6 + 25) >= 4u )
          WPP_SF_(v6[2], 39, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
      }
LABEL_32:
      v12 = 1;
      goto LABEL_14;
    }
  }
  else
  {
    v8 = 0;
    if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
    {
      WPP_SF_(v6[2], 37, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
LABEL_24:
  if ( (*((_BYTE *)v6 + 28) & 0x10) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_(v6[2], 43, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *, void *, __int64, void *))v8)(v8, a2, a3, a4);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008c40  push    rbx
0x180008c42  mov     eax, 1080h
0x180008c47  call    _alloca_probe
0x180008c4c  sub     rsp, rax
0x180008c4f  mov     rax, cs:__security_cookie
0x180008c56  xor     rax, rsp
0x180008c59  mov     [rsp+1088h+var_28], rax
0x180008c61  mov     [rsp+1088h+arg_8], rbp
0x180008c69  mov     rbp, rcx
0x180008c6c  mov     [rsp+1088h+arg_10], rsi
0x180008c74  mov     rsi, r8
0x180008c77  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c7e  test    byte ptr [rcx+1Ch], 10h
0x180008c82  jnz     loc_180008EB5
0x180008c88  mov     [rsp+1088h+arg_18], rdi
0x180008c90  mov     [rsp+1088h+var_18], r15
0x180008c98  test    rsi, rsi
0x180008c9b  jz      loc_180008F70
0x180008ca1  mov     rdi, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x180008ca8  test    rdi, rdi
0x180008cab  jz      loc_180008EAC
0x180008cb1  cmp     byte ptr [rdi], 0
0x180008cb4  jz      loc_180008EAC
0x180008cba  mov     rbx, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x180008cc1  mov     r15d, [rbp+28h]
0x180008cc5  test    rbx, rbx
0x180008cc8  jz      short loc_180008CE3
0x180008cca  lock inc dword ptr [rbx+8]
0x180008cce  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cd5  mov     rbx, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x180008cdc  mov     rdi, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x180008ce3  test    rdi, rdi
0x180008ce6  jz      loc_180008E0F
0x180008cec  mov     rax, [rsi]
0x180008cef  sub     rax, qword ptr cs:GUID_MONITOR_POWER_ON.Data1
0x180008cf6  jnz     short loc_180008D03
0x180008cf8  mov     rax, [rsi+8]
0x180008cfc  sub     rax, qword ptr cs:GUID_MONITOR_POWER_ON.Data4
0x180008d03  mov     [rsp+1088h+var_10], r14
0x180008d0b  test    rax, rax
0x180008d0e  jz      loc_180008FA9
0x180008d14  mov     eax, [rsi+14h]
0x180008d17  test    eax, eax
0x180008d19  jnz     loc_180008E91
0x180008d1f  test    byte ptr [rcx+1Ch], 10h
0x180008d23  jnz     loc_180008F49
0x180008d29  xor     r14b, r14b
0x180008d2c  mov     rbp, [rbp+0]
0x180008d30  lea     rcx, [rdi+8]
0x180008d34  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008d3a  call    cs:__imp_GetCurrentThreadId
0x180008d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d47  test    byte ptr [rcx+1Ch], 10h
0x180008d4b  jz      short loc_180008D57
0x180008d4d  cmp     byte ptr [rcx+19h], 4
0x180008d51  jnb     loc_180009035
0x180008d57  lea     rax, [rsp+1088h+var_1058]
0x180008d5c  mov     [rsp+1088h+var_1040], r15d
0x180008d61  mov     [rsp+1088h+var_1048], rax
0x180008d66  lea     rdx, [rsp+1088h+var_1048]
0x180008d6b  mov     eax, [rsp+1088h+var_103C]
0x180008d6f  xorps   xmm0, xmm0
0x180008d72  mov     rcx, rdi
0x180008d75  mov     [rsp+1088h+var_103C], eax
0x180008d79  movdqu  xmmword ptr [rsp+1088h+var_1058], xmm0
0x180008d7f  mov     [rsp+1088h+var_1038], rbp
0x180008d84  call    ??$IterateUserSessions@V_lambda_ee73c82f0cd15ee3b5a81921ae619a9d_@@@SebBroker@Broker@@AEAAXV_lambda_ee73c82f0cd15ee3b5a81921ae619a9d_@@@Z; Broker::SebBroker::IterateUserSessions<_lambda_ee73c82f0cd15ee3b5a81921ae619a9d_>(_lambda_ee73c82f0cd15ee3b5a81921ae619a9d_)
0x180008d89  mov     rax, [rsp+1088h+var_1058]
0x180008d8e  test    rax, rax
0x180008d91  jz      short loc_180008DD6
0x180008d93  mov     [rax+12h], r14b
0x180008d97  mov     rcx, [rsp+1088h+var_1058]
0x180008d9c  cmp     dword ptr [rcx+38h], 0
0x180008da0  jz      loc_180009052
0x180008da6  mov     rcx, [rcx+38h]
0x180008daa  lea     r8, [rsp+1088h+var_1028]
0x180008daf  movzx   eax, r14b
0x180008db3  mov     r9d, 8
0x180008db9  add     eax, eax
0x180008dbb  mov     [rsp+1088h+var_1024], r15d
0x180008dc0  or      eax, 1
0x180008dc3  xor     edx, edx
0x180008dc5  mov     [rsp+1088h+var_1028], eax
0x180008dc9  xor     eax, eax
0x180008dcb  mov     [rsp+1088h+var_1068], rax
0x180008dd0  call    cs:__imp_RtlPublishWnfStateData
0x180008dd6  mov     rcx, [rsp+1088h+var_1058+8]; this
0x180008ddb  mov     r14, [rsp+1088h+var_10]
0x180008de3  test    rcx, rcx
0x180008de6  jz      short loc_180008DED
0x180008de8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180008ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180008df4  test    byte ptr [rcx+1Ch], 10h
0x180008df8  jnz     loc_180008F04
0x180008dfe  lea     rcx, [rdi+8]
0x180008e02  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008e08  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e0f  mov     r15, [rsp+1088h+var_18]
0x180008e17  mov     rsi, [rsp+1088h+arg_10]
0x180008e1f  mov     rbp, [rsp+1088h+arg_8]
0x180008e27  test    byte ptr [rcx+1Ch], 10h
0x180008e2b  jnz     loc_180008EE0
0x180008e31  test    rbx, rbx
0x180008e34  jz      short loc_180008E6E
0x180008e36  mov     edi, 0FFFFFFFFh
0x180008e3b  mov     eax, edi
0x180008e3d  lock xadd [rbx+8], eax
0x180008e42  cmp     eax, 1
0x180008e45  jnz     short loc_180008E6E
0x180008e47  mov     rax, [rbx]
0x180008e4a  mov     rcx, rbx
0x180008e4d  mov     rax, [rax]
0x180008e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e55  lock xadd [rbx+0Ch], edi
0x180008e5a  cmp     edi, 1
0x180008e5d  jnz     short loc_180008E6E
0x180008e5f  mov     rax, [rbx]
0x180008e62  mov     rcx, rbx
0x180008e65  mov     rax, [rax+8]
0x180008e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e6e  mov     rdi, [rsp+1088h+arg_18]
0x180008e76  xor     eax, eax
0x180008e78  mov     rcx, [rsp+1088h+var_28]
0x180008e80  xor     rcx, rsp; StackCookie
0x180008e83  call    __security_check_cookie
0x180008e88  add     rsp, 1080h
0x180008e8f  pop     rbx
0x180008e90  retn
0x180008e91  cmp     eax, 2
0x180008e94  jz      loc_180008F2B
0x180008e9a  test    byte ptr [rcx+1Ch], 10h
0x180008e9e  jnz     loc_18000900E
0x180008ea4  mov     r14b, 1
0x180008ea7  jmp     loc_180008D2C
0x180008eac  xor     eax, eax
0x180008eae  mov     ebx, eax
0x180008eb0  jmp     loc_180008E0F
0x180008eb5  cmp     byte ptr [rcx+19h], 4
0x180008eb9  jb      loc_180008C88
0x180008ebf  mov     rcx, [rcx+10h]
0x180008ec3  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180008eca  mov     edx, 24h ; '$'
0x180008ecf  call    WPP_SF_
0x180008ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008edb  jmp     loc_180008C88
0x180008ee0  cmp     byte ptr [rcx+19h], 4
0x180008ee4  jb      loc_180008E31
0x180008eea  mov     rcx, [rcx+10h]
0x180008eee  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180008ef5  mov     edx, 2Bh ; '+'
0x180008efa  call    WPP_SF_
0x180008eff  jmp     loc_180008E31
0x180008f04  cmp     byte ptr [rcx+19h], 4
0x180008f08  jb      loc_180008DFE
0x180008f0e  mov     rcx, [rcx+10h]
0x180008f12  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180008f19  mov     edx, 23h ; '#'
0x180008f1e  mov     r9d, r15d
0x180008f21  call    WPP_SF_d
0x180008f26  jmp     loc_180008DFE
0x180008f2b  test    byte ptr [rcx+1Ch], 10h
0x180008f2f  jz      loc_180008EA4
0x180008f35  cmp     byte ptr [rcx+19h], 4
0x180008f39  jb      loc_180008EA4
0x180008f3f  mov     edx, 29h ; ')'
0x180008f44  jmp     loc_18000901D
0x180008f49  cmp     byte ptr [rcx+19h], 4
0x180008f4d  jb      loc_180008D29
0x180008f53  mov     rcx, [rcx+10h]
0x180008f57  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180008f5e  mov     edx, 28h ; '('
0x180008f63  mov     r9d, r15d
0x180008f66  call    WPP_SF_d
0x180008f6b  jmp     loc_180008D29
0x180008f70  xor     eax, eax
0x180008f72  mov     ebx, eax
0x180008f74  test    byte ptr [rcx+1Ch], 1
0x180008f78  jz      loc_180008E0F
0x180008f7e  cmp     byte ptr [rcx+19h], 2
0x180008f82  jb      loc_180008E0F
0x180008f88  mov     rcx, [rcx+10h]
0x180008f8c  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180008f93  mov     edx, 25h ; '%'
0x180008f98  call    WPP_SF_
0x180008f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fa4  jmp     loc_180008E0F
0x180008fa9  cmp     dword ptr [rsi+14h], 0
0x180008fad  jnz     short loc_180008FE0
0x180008faf  test    byte ptr [rcx+1Ch], 10h
0x180008fb3  jz      loc_180008D29
0x180008fb9  cmp     byte ptr [rcx+19h], 4
0x180008fbd  jb      loc_180008D29
0x180008fc3  mov     rcx, [rcx+10h]
0x180008fc7  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180008fce  mov     edx, 26h ; '&'
0x180008fd3  call    WPP_SF_
0x180008fd8  xor     r14b, r14b
0x180008fdb  jmp     loc_180008D2C
0x180008fe0  test    byte ptr [rcx+1Ch], 10h
0x180008fe4  jz      loc_180008EA4
0x180008fea  cmp     byte ptr [rcx+19h], 4
0x180008fee  jb      loc_180008EA4
0x180008ff4  mov     rcx, [rcx+10h]
0x180008ff8  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180008fff  mov     edx, 27h ; '''
0x180009004  call    WPP_SF_
0x180009009  jmp     loc_180008EA4
0x18000900e  cmp     byte ptr [rcx+19h], 4
0x180009012  jb      loc_180008EA4
0x180009018  mov     edx, 2Ah ; '*'
0x18000901d  mov     rcx, [rcx+10h]
0x180009021  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180009028  mov     r9d, r15d
0x18000902b  call    WPP_SF_d
0x180009030  jmp     loc_180008EA4
0x180009035  mov     rcx, [rcx+10h]
0x180009039  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180009040  mov     edx, 22h ; '"'
0x180009045  mov     r9d, r15d
0x180009048  call    WPP_SF_d
0x18000904d  jmp     loc_180008D57
0x180009052  cmp     dword ptr [rcx+3Ch], 0
0x180009056  jz      loc_180008DD6
0x18000905c  jmp     loc_180008DA6
```
