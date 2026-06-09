# Broker::SebBroker::EnumerateEvents(Broker::ApplicationIdentity const &,_SebiEventType,ulong,ulong)

- ea: `0x18000dc40`
- end: `0x18000df2f`
- name: `?EnumerateEvents@SebBroker@Broker@@QEAA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEBUApplicationIdentity@2@W4_SebiEventType@@KK@Z`
- size: `751`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, unsigned int, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cc40`
- `0x18001e150`

## callees

- `0x1800030e0`
- `0x1800076a0`
- `0x18000b168`
- `0x18000dc40`
- `0x18000e79c`
- `0x180011590`
- `0x1800171bc`
- `0x18001b1f4`

## import_xrefs

- `BrokerLib!BrGetBrokeredEventInfo2` at `0x18000ddcc`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x18000ddcc`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x18000dd42`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x18000dd42`
- `BrokerLib!BrBufferFree` at `0x18000deb4`
- `BrokerLib!BrBufferFree` at `0x18000deb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Broker::SebBroker::EnumerateEvents(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        int a6)
{
  _QWORD *v10; // rbx
  PSID v11; // rdi
  __int64 v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  unsigned int BrokeredEventInfo2; // eax
  __int64 *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdx
  std::_Ref_count_base *v19; // rdi
  _QWORD *v20; // r8
  __int64 v21; // rax
  _OWORD *v22; // rdx
  __int64 v24; // [rsp+38h] [rbp-60h] BYREF
  __int64 *v25; // [rsp+40h] [rbp-58h] BYREF
  __int64 v26; // [rsp+48h] [rbp-50h] BYREF
  __int64 v27; // [rsp+50h] [rbp-48h]
  __int128 v28; // [rsp+58h] [rbp-40h]
  unsigned int v29; // [rsp+A0h] [rbp+8h] BYREF
  _QWORD *v30; // [rsp+A8h] [rbp+10h]

  v30 = a2;
  std::vector<_GUID>::vector<_GUID>(a2);
  v29 = 0;
  v24 = 0;
  v10 = 0;
  v11 = 0;
  v26 = *(_QWORD *)(a1 + 136);
  v27 = 1;
  Broker::BrokerLock::Acquire((Broker::BrokerLock *)&v26);
  v12 = *(_QWORD *)(a1 + 136);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), *(PSID *)a3);
    v12 = *(_QWORD *)(a1 + 136);
  }
  if ( !a5 )
  {
    v10 = (_QWORD *)(a3 + 56);
    if ( *(_QWORD *)(a3 + 80) > 7u )
      v10 = (_QWORD *)*v10;
  }
  if ( !a6 )
    v11 = *(PSID *)a3;
  v13 = BrQueryBrokeredEvents2(v12, v11, v10, a4, &v29, &v24);
  if ( !v13 )
  {
    v14 = 0;
    if ( !v29 )
      goto LABEL_35;
    while ( 1 )
    {
      v25 = 0;
      v28 = 0;
      BrokeredEventInfo2 = BrGetBrokeredEventInfo2(*(_QWORD *)(a1 + 136), *(_QWORD *)(v24 + 8LL * v14), 0, 0, &v25);
      if ( BrokeredEventInfo2 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
            BrokeredEventInfo2);
        goto LABEL_34;
      }
      v16 = v25;
      v17 = v25[1];
      if ( v17 )
        _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
      v18 = *v16;
      v19 = (std::_Ref_count_base *)v16[1];
      *(_QWORD *)&v28 = v18;
      *((_QWORD *)&v28 + 1) = v19;
      if ( dword_180035124[12 * *(int *)(v18 + 96)] )
      {
        if ( v19 )
          goto LABEL_33;
      }
      else
      {
        v20 = *(_QWORD **)(v18 + 224);
        v21 = *v20 - *(_QWORD *)&GUID_NULL.Data1;
        if ( *v20 == *(_QWORD *)&GUID_NULL.Data1 )
          v21 = v20[1] - *(_QWORD *)GUID_NULL.Data4;
        if ( v21 )
        {
          v22 = (_OWORD *)a2[1];
          if ( v22 == (_OWORD *)a2[2] )
          {
            std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(a2);
          }
          else
          {
            *v22 = *(_OWORD *)v20;
            a2[1] += 16LL;
          }
          if ( !v19 )
            goto LABEL_34;
LABEL_33:
          std::_Ref_count_base::_Decref(v19);
          goto LABEL_34;
        }
        if ( v19 )
          goto LABEL_33;
      }
LABEL_34:
      if ( ++v14 >= v29 )
        goto LABEL_35;
    }
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v13);
LABEL_35:
  if ( v24 )
    BrBufferFree();
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), *(PSID *)a3);
  if ( HIDWORD(v27) )
    Broker::BrokerLock::Release((Broker::BrokerLock *)&v26);
  return a2;
}

```

## disassembly

```asm
0x18000dc40  mov     [rsp+arg_10], rbx
0x18000dc45  mov     [rsp+arg_18], rbp
0x18000dc4a  mov     [rsp+arg_8], rdx
0x18000dc4f  push    rsi
0x18000dc50  push    rdi
0x18000dc51  push    r12
0x18000dc53  push    r14
0x18000dc55  push    r15
0x18000dc57  sub     rsp, 70h
0x18000dc5b  mov     ebp, r9d
0x18000dc5e  mov     r15, r8
0x18000dc61  mov     rsi, rdx
0x18000dc64  mov     r14, rcx
0x18000dc67  xor     r12d, r12d
0x18000dc6a  mov     [rsp+98h+var_68], r12d
0x18000dc6f  mov     rcx, rdx
0x18000dc72  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18000dc77  mov     [rsp+98h+var_68], 1
0x18000dc7f  mov     [rsp+98h+arg_0], r12d
0x18000dc87  mov     [rsp+98h+var_60], r12
0x18000dc8c  mov     ebx, r12d
0x18000dc8f  mov     edi, r12d
0x18000dc92  mov     rax, [r14+88h]
0x18000dc99  mov     [rsp+98h+var_50], rax
0x18000dc9e  mov     [rsp+98h+var_48], 1
0x18000dca7  lea     rcx, [rsp+98h+var_50]; this
0x18000dcac  call    ?Acquire@BrokerLock@Broker@@QEAAXXZ; Broker::BrokerLock::Acquire(void)
0x18000dcb1  mov     rcx, [r14+88h]
0x18000dcb8  mov     rax, cs:WPP_GLOBAL_Control
0x18000dcbf  test    byte ptr [rax+1Ch], 1
0x18000dcc3  jz      short loc_18000DCFD
0x18000dcc5  cmp     byte ptr [rax+19h], 4
0x18000dcc9  jb      short loc_18000DCFD
0x18000dccb  mov     rcx, [r15]
0x18000dcce  lea     r9, [r15+38h]
0x18000dcd2  cmp     qword ptr [r9+18h], 7
0x18000dcd7  jbe     short loc_18000DCDC
0x18000dcd9  mov     r9, [r9]
0x18000dcdc  mov     edx, 15h
0x18000dce1  mov     [rsp+98h+pSid], rcx; pSid
0x18000dce6  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000dced  mov     rcx, [rax+10h]; LoggerHandle
0x18000dcf1  call    WPP_SF_S_sid_
0x18000dcf6  mov     rcx, [r14+88h]
0x18000dcfd  cmp     [rsp+98h+arg_20], 0
0x18000dd05  jnz     short loc_18000DD15
0x18000dd07  lea     rbx, [r15+38h]
0x18000dd0b  cmp     qword ptr [rbx+18h], 7
0x18000dd10  jbe     short loc_18000DD15
0x18000dd12  mov     rbx, [rbx]
0x18000dd15  cmp     [rsp+98h+arg_28], 0
0x18000dd1d  jnz     short loc_18000DD22
0x18000dd1f  mov     rdi, [r15]
0x18000dd22  lea     rax, [rsp+98h+var_60]
0x18000dd27  mov     [rsp+98h+var_70], rax
0x18000dd2c  lea     rax, [rsp+98h+arg_0]
0x18000dd34  mov     [rsp+98h+pSid], rax
0x18000dd39  mov     r9d, ebp
0x18000dd3c  mov     r8, rbx
0x18000dd3f  mov     rdx, rdi
0x18000dd42  call    cs:__imp_BrQueryBrokeredEvents2
0x18000dd48  test    eax, eax
0x18000dd4a  jz      short loc_18000DD84
0x18000dd4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd53  test    byte ptr [rcx+1Ch], 1
0x18000dd57  jz      loc_18000DEAA
0x18000dd5d  cmp     byte ptr [rcx+19h], 2
0x18000dd61  jb      loc_18000DEAA
0x18000dd67  mov     edx, 16h
0x18000dd6c  mov     r9d, eax
0x18000dd6f  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000dd76  mov     rcx, [rcx+10h]
0x18000dd7a  call    WPP_SF_d
0x18000dd7f  jmp     loc_18000DEAA
0x18000dd84  mov     ebx, r12d
0x18000dd87  cmp     [rsp+98h+arg_0], r12d
0x18000dd8f  jbe     loc_18000DEAA
0x18000dd95  lea     rbp, dword_180035124
0x18000dd9c  mov     [rsp+98h+var_58], r12
0x18000dda1  xorps   xmm0, xmm0
0x18000dda4  movdqu  [rsp+98h+var_40], xmm0
0x18000ddaa  mov     eax, ebx
0x18000ddac  lea     rcx, [rsp+98h+var_58]
0x18000ddb1  mov     [rsp+98h+pSid], rcx
0x18000ddb6  xor     r9d, r9d
0x18000ddb9  xor     r8d, r8d
0x18000ddbc  mov     rdx, [rsp+98h+var_60]
0x18000ddc1  mov     rdx, [rdx+rax*8]
0x18000ddc5  mov     rcx, [r14+88h]
0x18000ddcc  call    cs:__imp_BrGetBrokeredEventInfo2
0x18000ddd2  test    eax, eax
0x18000ddd4  jz      short loc_18000DE07
0x18000ddd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dddd  test    byte ptr [rcx+1Ch], 1
0x18000dde1  jz      short loc_18000DE02
0x18000dde3  cmp     byte ptr [rcx+19h], 2
0x18000dde7  jb      short loc_18000DE02
0x18000dde9  mov     edx, 17h
0x18000ddee  mov     r9d, eax
0x18000ddf1  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000ddf8  mov     rcx, [rcx+10h]
0x18000ddfc  call    WPP_SF_d
0x18000de01  nop
0x18000de02  jmp     loc_18000DE9B
0x18000de07  mov     rcx, [rsp+98h+var_58]
0x18000de0c  mov     rax, [rcx+8]
0x18000de10  test    rax, rax
0x18000de13  jz      short loc_18000DE19
0x18000de15  lock inc dword ptr [rax+8]
0x18000de19  mov     rdx, [rcx]
0x18000de1c  mov     rdi, [rcx+8]
0x18000de20  mov     qword ptr [rsp+98h+var_40], rdx
0x18000de25  mov     qword ptr [rsp+98h+var_40+8], rdi
0x18000de2a  movsxd  rax, dword ptr [rdx+60h]
0x18000de2e  lea     rcx, [rax+rax*2]
0x18000de32  add     rcx, rcx
0x18000de35  cmp     dword ptr [rbp+rcx*8+0], 0
0x18000de3a  jz      short loc_18000DE43
0x18000de3c  test    rdi, rdi
0x18000de3f  jz      short loc_18000DE9B
0x18000de41  jmp     short loc_18000DE93
0x18000de43  mov     r8, [rdx+0E0h]
0x18000de4a  mov     rax, [r8]
0x18000de4d  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18000de54  jnz     short loc_18000DE61
0x18000de56  mov     rax, [r8+8]
0x18000de5a  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18000de61  test    rax, rax
0x18000de64  jnz     short loc_18000DE6D
0x18000de66  test    rdi, rdi
0x18000de69  jz      short loc_18000DE9B
0x18000de6b  jmp     short loc_18000DE93
0x18000de6d  mov     rdx, [rsi+8]
0x18000de71  cmp     rdx, [rsi+10h]
0x18000de75  jz      short loc_18000DE85
0x18000de77  movups  xmm0, xmmword ptr [r8]
0x18000de7b  movups  xmmword ptr [rdx], xmm0
0x18000de7e  add     qword ptr [rsi+8], 10h
0x18000de83  jmp     short loc_18000DE8E
0x18000de85  mov     rcx, rsi
0x18000de88  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x18000de8d  nop
0x18000de8e  test    rdi, rdi
0x18000de91  jz      short loc_18000DE9B
0x18000de93  mov     rcx, rdi; this
0x18000de96  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000de9b  inc     ebx
0x18000de9d  cmp     ebx, [rsp+98h+arg_0]
0x18000dea4  jb      loc_18000DD9C
0x18000deaa  mov     rcx, [rsp+98h+var_60]
0x18000deaf  test    rcx, rcx
0x18000deb2  jz      short loc_18000DEBA
0x18000deb4  call    cs:__imp_BrBufferFree
0x18000deba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dec1  test    byte ptr [rcx+1Ch], 1
0x18000dec5  jz      short loc_18000DF00
0x18000dec7  cmp     byte ptr [rcx+19h], 4
0x18000decb  jb      short loc_18000DF00
0x18000decd  mov     rax, [r15]
0x18000ded0  lea     r9, [r15+38h]
0x18000ded4  cmp     qword ptr [r9+18h], 7
0x18000ded9  jbe     short loc_18000DEDE
0x18000dedb  mov     r9, [r9]
0x18000dede  mov     edx, 18h
0x18000dee3  mov     [rsp+98h+pSid], rax; pSid
0x18000dee8  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000deef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000def6  mov     rcx, [rcx+10h]; LoggerHandle
0x18000defa  call    WPP_SF_S_sid_
0x18000deff  nop
0x18000df00  cmp     dword ptr [rsp+98h+var_48+4], 0
0x18000df05  jz      short loc_18000DF12
0x18000df07  lea     rcx, [rsp+98h+var_50]; this
0x18000df0c  call    ?Release@BrokerLock@Broker@@QEAAXXZ; Broker::BrokerLock::Release(void)
0x18000df11  nop
0x18000df12  mov     rax, rsi
0x18000df15  lea     r11, [rsp+98h+var_28]
0x18000df1a  mov     rbx, [r11+40h]
0x18000df1e  mov     rbp, [r11+48h]
0x18000df22  mov     rsp, r11
0x18000df25  pop     r15
0x18000df27  pop     r14
0x18000df29  pop     r12
0x18000df2b  pop     rdi
0x18000df2c  pop     rsi
0x18000df2d  retn
```
