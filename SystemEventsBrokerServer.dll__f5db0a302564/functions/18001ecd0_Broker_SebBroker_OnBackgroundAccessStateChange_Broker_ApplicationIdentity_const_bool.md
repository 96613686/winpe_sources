# Broker::SebBroker::OnBackgroundAccessStateChange(Broker::ApplicationIdentity const &,bool)

- ea: `0x18001ecd0`
- end: `0x18001ef0a`
- name: `?OnBackgroundAccessStateChange@SebBroker@Broker@@AEAAXAEBUApplicationIdentity@2@_N@Z`
- size: `570`
- prototype: `void __fastcall(struct _BROKER **this, const struct Broker::ApplicationIdentity *, unsigned __int8)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001ea70`
- `0x18001eba0`

## callees

- `0x1800016c4`
- `0x180001730`
- `0x1800030e0`
- `0x1800076a0`
- `0x18000e770`
- `0x180011574`
- `0x1800133c0`
- `0x18001d9ac`
- `0x18001ecd0`

## import_xrefs

- `BrokerLib!BrGetBrokeredEventInfo2` at `0x18001ee1d`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x18001ee1d`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x18001ed81`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x18001ed81`
- `BrokerLib!BrBufferFree` at `0x18001eeb9`
- `BrokerLib!BrBufferFree` at `0x18001eeb9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Broker::SebBroker::OnBackgroundAccessStateChange(
        struct _BROKER **this,
        const struct Broker::ApplicationIdentity *a2,
        unsigned __int8 a3)
{
  int v3; // ebx
  _QWORD *v6; // r9
  __int64 v7; // r9
  char *v8; // rbx
  char *v9; // r8
  unsigned int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rdi
  unsigned int BrokeredEventInfo2; // eax
  _QWORD *v14; // rcx
  Broker::SebEvent *v15; // [rsp+30h] [rbp-19h] BYREF
  std::_Ref_count_base *v16; // [rsp+38h] [rbp-11h]
  _BYTE v17[16]; // [rsp+40h] [rbp-9h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp+7h] BYREF
  __int128 v19; // [rsp+58h] [rbp+Fh]
  int v20; // [rsp+68h] [rbp+1Fh]
  unsigned int v21; // [rsp+70h] [rbp+27h]
  int v22; // [rsp+B0h] [rbp+67h] BYREF
  __int64 v23; // [rsp+B8h] [rbp+6Fh] BYREF
  unsigned int v24; // [rsp+C0h] [rbp+77h] BYREF
  _QWORD *v25; // [rsp+C8h] [rbp+7Fh] BYREF

  v3 = a3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v6 = (_QWORD *)((char *)a2 + 56);
    if ( *((_QWORD *)a2 + 10) > 7u )
      v6 = (_QWORD *)*v6;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v6);
  }
  v24 = 0;
  v23 = 0;
  Broker::BrokerLock::BrokerLock((Broker::BrokerLock *)v17, this[17], 1);
  v7 = (v3 ^ 1u) + 17;
  v8 = (char *)a2 + 56;
  if ( *((_QWORD *)a2 + 10) <= 7u )
    v9 = (char *)a2 + 56;
  else
    v9 = *(char **)v8;
  v10 = BrQueryBrokeredEvents2(this[17], *(_QWORD *)a2, v9, v7, &v24, &v23);
  v11 = v10;
  if ( v10 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v10);
    v19 = 0;
    v20 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v21 = v11;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  v12 = 0;
  if ( v24 )
  {
    while ( 1 )
    {
      v25 = 0;
      v22 = 0;
      BrokeredEventInfo2 = BrGetBrokeredEventInfo2(this[17], *(_QWORD *)(v23 + 8 * v12), 0, 0, &v25);
      if ( BrokeredEventInfo2 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_22;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
          BrokeredEventInfo2);
      }
      else
      {
        std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(&v15, v25);
        Broker::SebEvent::SignalSyncEvent(v15, 0, 0, 0, 0, (enum _BI_ACTIVATION_STATUS *)&v22);
        if ( v16 )
          std::_Ref_count_base::_Decref(v16);
      }
      v14 = WPP_GLOBAL_Control;
LABEL_22:
      v12 = (unsigned int)(v12 + 1);
      if ( (unsigned int)v12 >= v24 )
        goto LABEL_25;
    }
  }
  v14 = WPP_GLOBAL_Control;
LABEL_25:
  if ( v23 )
  {
    BrBufferFree(v23);
    v14 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 4u )
  {
    if ( *((_QWORD *)v8 + 3) > 7u )
      v8 = *(char **)v8;
    WPP_SF_S(v14[2], 82, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v8);
  }
  Broker::BrokerLock::~BrokerLock((Broker::BrokerLock *)v17);
}

```

## disassembly

```asm
0x18001ecd0  push    rbp
0x18001ecd2  push    rbx
0x18001ecd3  push    rsi
0x18001ecd4  push    rdi
0x18001ecd5  lea     rbp, [rsp-3Fh]
0x18001ecda  sub     rsp, 88h
0x18001ece1  movzx   ebx, r8b
0x18001ece5  mov     rdi, rdx
0x18001ece8  mov     rsi, rcx
0x18001eceb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ecf2  test    byte ptr [rcx+1Ch], 1
0x18001ecf6  jz      short loc_18001ED21
0x18001ecf8  cmp     byte ptr [rcx+19h], 4
0x18001ecfc  jb      short loc_18001ED21
0x18001ecfe  lea     r9, [rdx+38h]
0x18001ed02  cmp     qword ptr [r9+18h], 7
0x18001ed07  jbe     short loc_18001ED0C
0x18001ed09  mov     r9, [r9]
0x18001ed0c  mov     edx, 4Fh ; 'O'
0x18001ed11  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001ed18  mov     rcx, [rcx+10h]
0x18001ed1c  call    WPP_SF_S
0x18001ed21  mov     [rbp+57h+arg_10], 0
0x18001ed28  mov     [rbp+57h+arg_8], 0
0x18001ed30  mov     r8d, 1; int
0x18001ed36  mov     rdx, [rsi+88h]; struct _BROKER *
0x18001ed3d  lea     rcx, [rbp+57h+var_60]; this
0x18001ed41  call    ??0BrokerLock@Broker@@QEAA@PEAU_BROKER@@HH@Z; Broker::BrokerLock::BrokerLock(_BROKER *,int,int)
0x18001ed46  nop
0x18001ed47  mov     r9d, ebx
0x18001ed4a  xor     r9d, 1
0x18001ed4e  add     r9d, 11h
0x18001ed52  lea     rbx, [rdi+38h]
0x18001ed56  cmp     qword ptr [rbx+18h], 7
0x18001ed5b  jbe     short loc_18001ED62
0x18001ed5d  mov     r8, [rbx]
0x18001ed60  jmp     short loc_18001ED65
0x18001ed62  mov     r8, rbx
0x18001ed65  lea     rax, [rbp+57h+arg_8]
0x18001ed69  mov     [rsp+0A0h+var_78], rax
0x18001ed6e  lea     rax, [rbp+57h+arg_10]
0x18001ed72  mov     [rsp+0A0h+var_80], rax
0x18001ed77  mov     rdx, [rdi]
0x18001ed7a  mov     rcx, [rsi+88h]
0x18001ed81  call    cs:__imp_BrQueryBrokeredEvents2
0x18001ed87  mov     edi, eax
0x18001ed89  test    eax, eax
0x18001ed8b  jz      short loc_18001EDE5
0x18001ed8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed94  test    byte ptr [rcx+1Ch], 1
0x18001ed98  jz      short loc_18001EDB8
0x18001ed9a  cmp     byte ptr [rcx+19h], 2
0x18001ed9e  jb      short loc_18001EDB8
0x18001eda0  mov     edx, 50h ; 'P'
0x18001eda5  mov     r9d, eax
0x18001eda8  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001edaf  mov     rcx, [rcx+10h]
0x18001edb3  call    WPP_SF_d
0x18001edb8  xorps   xmm0, xmm0
0x18001edbb  movups  [rbp+57h+var_48], xmm0
0x18001edbf  mov     [rbp+57h+var_38], 1
0x18001edc6  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001edcd  mov     [rbp+57h+pExceptionObject], rax
0x18001edd1  mov     [rbp+57h+var_30], edi
0x18001edd4  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001eddb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001eddf  call    _CxxThrowException_0
0x18001ede5  xor     edi, edi
0x18001ede7  cmp     [rbp+57h+arg_10], edi
0x18001edea  jbe     loc_18001EEA6
0x18001edf0  mov     [rbp+57h+arg_18], 0
0x18001edf8  mov     [rbp+57h+arg_0], 0
0x18001edff  lea     rcx, [rbp+57h+arg_18]
0x18001ee03  mov     [rsp+0A0h+var_80], rcx
0x18001ee08  xor     r9d, r9d
0x18001ee0b  xor     r8d, r8d
0x18001ee0e  mov     rdx, [rbp+57h+arg_8]
0x18001ee12  mov     rdx, [rdx+rdi*8]
0x18001ee16  mov     rcx, [rsi+88h]
0x18001ee1d  call    cs:__imp_BrGetBrokeredEventInfo2
0x18001ee23  test    eax, eax
0x18001ee25  jz      short loc_18001EE54
0x18001ee27  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee2e  test    byte ptr [rcx+1Ch], 1
0x18001ee32  jz      short loc_18001EE99
0x18001ee34  cmp     byte ptr [rcx+19h], 2
0x18001ee38  jb      short loc_18001EE99
0x18001ee3a  mov     edx, 51h ; 'Q'
0x18001ee3f  mov     r9d, eax
0x18001ee42  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001ee49  mov     rcx, [rcx+10h]
0x18001ee4d  call    WPP_SF_d
0x18001ee52  jmp     short loc_18001EE92
0x18001ee54  mov     rdx, [rbp+57h+arg_18]
0x18001ee58  lea     rcx, [rbp+57h+var_70]
0x18001ee5c  call    ??0?$shared_ptr@VSebEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(std::shared_ptr<Broker::SebEvent> const &)
0x18001ee61  lea     rcx, [rbp+57h+arg_0]
0x18001ee65  mov     [rsp+0A0h+var_78], rcx; enum _BI_ACTIVATION_STATUS *
0x18001ee6a  mov     [rsp+0A0h+var_80], 0; struct _GUID *
0x18001ee73  xor     r9d, r9d; unsigned int
0x18001ee76  xor     r8d, r8d; unsigned __int8 *
0x18001ee79  xor     edx, edx; unsigned __int8 *
0x18001ee7b  mov     rcx, [rbp+57h+var_70]; this
0x18001ee7f  call    ?SignalSyncEvent@SebEvent@Broker@@QEAAKPEAEPEBEKPEBU_GUID@@PEAW4_BI_ACTIVATION_STATUS@@@Z; Broker::SebEvent::SignalSyncEvent(uchar *,uchar const *,ulong,_GUID const *,_BI_ACTIVATION_STATUS *)
0x18001ee84  mov     rcx, [rbp+57h+var_68]; this
0x18001ee88  test    rcx, rcx
0x18001ee8b  jz      short loc_18001EE92
0x18001ee8d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ee92  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee99  inc     edi
0x18001ee9b  cmp     edi, [rbp+57h+arg_10]
0x18001ee9e  jb      loc_18001EDF0
0x18001eea4  jmp     short loc_18001EEAD
0x18001eea6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eead  mov     rax, [rbp+57h+arg_8]
0x18001eeb1  test    rax, rax
0x18001eeb4  jz      short loc_18001EEC6
0x18001eeb6  mov     rcx, rax
0x18001eeb9  call    cs:__imp_BrBufferFree
0x18001eebf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eec6  test    byte ptr [rcx+1Ch], 1
0x18001eeca  jz      short loc_18001EEF5
0x18001eecc  cmp     byte ptr [rcx+19h], 4
0x18001eed0  jb      short loc_18001EEF5
0x18001eed2  cmp     qword ptr [rbx+18h], 7
0x18001eed7  jbe     short loc_18001EEDC
0x18001eed9  mov     rbx, [rbx]
0x18001eedc  mov     edx, 52h ; 'R'
0x18001eee1  mov     r9, rbx
0x18001eee4  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001eeeb  mov     rcx, [rcx+10h]
0x18001eeef  call    WPP_SF_S
0x18001eef4  nop
0x18001eef5  lea     rcx, [rbp+57h+var_60]; this
0x18001eef9  call    ??1BrokerLock@Broker@@QEAA@XZ; Broker::BrokerLock::~BrokerLock(void)
0x18001eefe  add     rsp, 88h
0x18001ef05  pop     rdi
0x18001ef06  pop     rsi
0x18001ef07  pop     rbx
0x18001ef08  pop     rbp
0x18001ef09  retn
```
