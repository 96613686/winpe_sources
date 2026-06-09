# Broker::SebBroker::SignalSyncEvent(Broker::ApplicationIdentity const &,Broker::RpcClientToken *,_GUID &,uchar *,uchar const *,ulong,_GUID const *,_BI_ACTIVATION_STATUS *)

- ea: `0x1800026d0`
- end: `0x1800029b6`
- name: `?SignalSyncEvent@SebBroker@Broker@@QEAAXAEBUApplicationIdentity@2@PEAVRpcClientToken@2@AEAU_GUID@@PEAEPEBEKPEBU5@PEAW4_BI_ACTIVATION_STATUS@@@Z`
- size: `742`
- prototype: `void(Broker::SebBroker *__hidden this, const struct Broker::ApplicationIdentity *, struct Broker::RpcClientToken *, struct _GUID *, unsigned __int8 *, const unsigned __int8 *, unsigned int, const struct _GUID *, enum _BI_ACTIVATION_STATUS *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800029c0`

## callees

- `0x1800016c4`
- `0x180001730`
- `0x180001b50`
- `0x180001b78`
- `0x180001dc0`
- `0x180001e40`
- `0x1800026d0`
- `0x1800030e0`
- `0x180005a50`
- `0x1800076a0`
- `0x18000e79c`
- `0x180011590`
- `0x18001d9ac`
- `0x18001f260`

## import_xrefs

- `BrokerLib!BrGetBrokeredEventInfo2` at `0x1800027cf`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x1800027cf`
- `BrokerLib!BrFindBrokeredEvent` at `0x18000277e`
- `BrokerLib!BrFindBrokeredEvent` at `0x18000277e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Broker::SebBroker::SignalSyncEvent(
        Broker::SebBroker *this,
        const struct Broker::ApplicationIdentity *a2,
        struct Broker::RpcClientToken *a3,
        struct _GUID *a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        const struct _GUID *a8,
        enum _BI_ACTIVATION_STATUS *a9)
{
  Broker::SebEvent *v13; // rbx
  __int64 v14; // r9
  Broker::ApplicationIdentity *v15; // rax
  _QWORD *v16; // r9
  int v17; // eax
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-91h] BYREF
  int v19; // [rsp+48h] [rbp-79h]
  int v20; // [rsp+50h] [rbp-71h]
  __int64 v21; // [rsp+60h] [rbp-61h] BYREF
  __int64 v22; // [rsp+68h] [rbp-59h]
  Broker::SebEvent *v23[2]; // [rsp+70h] [rbp-51h] BYREF
  _BYTE v24[96]; // [rsp+80h] [rbp-41h] BYREF
  __int64 v25; // [rsp+100h] [rbp+3Fh] BYREF
  _QWORD *v26; // [rsp+118h] [rbp+57h] BYREF

  v25 = 0;
  v26 = 0;
  *(_OWORD *)v23 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a4);
  v21 = *((_QWORD *)this + 17);
  v22 = 1;
  Broker::BrokerLock::Acquire((Broker::BrokerLock *)&v21);
  *(struct _GUID *)pExceptionObject = *a4;
  if ( (unsigned int)BrFindBrokeredEvent(*((_QWORD *)this + 17), pExceptionObject, 0, 0, &v25) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v19 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  if ( (unsigned int)BrGetBrokeredEventInfo2(*((_QWORD *)this + 17), v25, 0, 0, &v26) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v19 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>::operator=(v23, v26);
  v13 = v23[0];
  if ( !Broker::SebEvent::IsSyncEvent(*((_DWORD *)v23[0] + 24)) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v14);
    *(_OWORD *)&pExceptionObject[8] = 0;
    v19 = 4;
    *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
    throw (Broker::InvalidParameter *)pExceptionObject;
  }
  v15 = Broker::ApplicationIdentity::ApplicationIdentity((Broker::ApplicationIdentity *)v24, a2);
  if ( !Broker::SebEvent::CheckSignalPermissions((__int64)v13, (__int64)v15, a3) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = (_QWORD *)((char *)v13 + 64);
      if ( *((_QWORD *)v13 + 11) > 7u )
        v16 = (_QWORD *)*v16;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v16);
    }
    *(_OWORD *)&pExceptionObject[8] = 0;
    v19 = 5;
    *(_QWORD *)pExceptionObject = &Broker::AccessDenied::`vftable';
    throw (Broker::AccessDenied *)pExceptionObject;
  }
  v17 = Broker::SebEvent::SignalSyncEvent(v13, a5, a6, a7, a8, a9);
  if ( v17 )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v19 = 1;
    *(_QWORD *)pExceptionObject = &Broker::Win32Error::`vftable';
    v20 = v17;
    throw (Broker::Win32Error *)pExceptionObject;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  if ( HIDWORD(v22) )
    Broker::BrokerLock::Release((Broker::BrokerLock *)&v21);
  if ( v23[1] )
    std::_Ref_count_base::_Decref(v23[1]);
}

```

## disassembly

```asm
0x1800026d0  mov     [rsp-8+arg_8], rbx
0x1800026d5  mov     [rsp-8+arg_10], rsi
0x1800026da  push    rbp
0x1800026db  push    rdi
0x1800026dc  push    r14
0x1800026de  lea     rbp, [rsp-1Fh]
0x1800026e3  sub     rsp, 0E0h
0x1800026ea  mov     rdi, r9
0x1800026ed  mov     r14, r8
0x1800026f0  mov     rsi, rdx
0x1800026f3  mov     rbx, rcx
0x1800026f6  mov     [rbp+2Fh+arg_0], 0
0x1800026fe  mov     [rbp+2Fh+arg_18], 0
0x180002706  xorps   xmm0, xmm0
0x180002709  movdqu  xmmword ptr [rbp+2Fh+var_80], xmm0
0x18000270e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002715  test    byte ptr [rcx+1Ch], 1
0x180002719  jz      short loc_18000273D
0x18000271b  cmp     byte ptr [rcx+19h], 4
0x18000271f  jb      short loc_18000273D
0x180002721  lea     r9, [rdx+38h]
0x180002725  cmp     qword ptr [r9+18h], 7
0x18000272a  jbe     short loc_18000272F
0x18000272c  mov     r9, [r9]
0x18000272f  mov     [rsp+0F0h+var_D0], rdi; __int64
0x180002734  mov     rcx, [rcx+10h]; LoggerHandle
0x180002738  call    WPP_SF_S_guid_
0x18000273d  mov     rax, [rbx+88h]
0x180002744  mov     [rbp+2Fh+var_90], rax
0x180002748  mov     [rbp+2Fh+var_88], 1
0x180002750  lea     rcx, [rbp+2Fh+var_90]; this
0x180002754  call    ?Acquire@BrokerLock@Broker@@QEAAXXZ; Broker::BrokerLock::Acquire(void)
0x180002759  nop
0x18000275a  movups  xmm0, xmmword ptr [rdi]
0x18000275d  movdqu  xmmword ptr [rsp+0F0h+pExceptionObject], xmm0
0x180002763  lea     rax, [rbp+2Fh+arg_0]
0x180002767  mov     [rsp+0F0h+var_D0], rax
0x18000276c  xor     r9d, r9d
0x18000276f  xor     r8d, r8d
0x180002772  lea     rdx, [rsp+0F0h+pExceptionObject]
0x180002777  mov     rcx, [rbx+88h]
0x18000277e  call    cs:__imp_BrFindBrokeredEvent
0x180002784  test    eax, eax
0x180002786  jz      short loc_1800027B5
0x180002788  xorps   xmm0, xmm0
0x18000278b  movups  xmmword ptr [rsp+0F0h+pExceptionObject+8], xmm0
0x180002790  mov     [rbp+2Fh+var_A8], 3
0x180002797  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18000279e  mov     qword ptr [rsp+0F0h+pExceptionObject], rax
0x1800027a3  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x1800027aa  lea     rcx, [rsp+0F0h+pExceptionObject]; pExceptionObject
0x1800027af  call    _CxxThrowException_0
0x1800027b5  lea     rax, [rbp+2Fh+arg_18]
0x1800027b9  mov     [rsp+0F0h+var_D0], rax
0x1800027be  xor     r9d, r9d
0x1800027c1  xor     r8d, r8d
0x1800027c4  mov     rdx, [rbp+2Fh+arg_0]
0x1800027c8  mov     rcx, [rbx+88h]
0x1800027cf  call    cs:__imp_BrGetBrokeredEventInfo2
0x1800027d5  test    eax, eax
0x1800027d7  jz      short loc_180002806
0x1800027d9  xorps   xmm0, xmm0
0x1800027dc  movups  xmmword ptr [rsp+0F0h+pExceptionObject+8], xmm0
0x1800027e1  mov     [rbp+2Fh+var_A8], 3
0x1800027e8  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x1800027ef  mov     qword ptr [rsp+0F0h+pExceptionObject], rax
0x1800027f4  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x1800027fb  lea     rcx, [rsp+0F0h+pExceptionObject]; pExceptionObject
0x180002800  call    _CxxThrowException_0
0x180002806  mov     rdx, [rbp+2Fh+arg_18]
0x18000280a  lea     rcx, [rbp+2Fh+var_80]
0x18000280e  call    ??4?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>::operator=(std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>> const &)
0x180002813  mov     rbx, [rbp+2Fh+var_80]
0x180002817  mov     r9d, [rbx+60h]
0x18000281b  mov     ecx, r9d
0x18000281e  call    ?IsSyncEvent@SebEvent@Broker@@SA_NW4_SebiEventType@@@Z; Broker::SebEvent::IsSyncEvent(_SebiEventType)
0x180002823  test    al, al
0x180002825  jnz     short loc_18000287C
0x180002827  mov     rcx, cs:WPP_GLOBAL_Control
0x18000282e  test    byte ptr [rcx+1Ch], 1
0x180002832  jz      short loc_18000284F
0x180002834  cmp     byte ptr [rcx+19h], 2
0x180002838  jb      short loc_18000284F
0x18000283a  mov     edx, 66h ; 'f'
0x18000283f  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180002846  mov     rcx, [rcx+10h]
0x18000284a  call    WPP_SF_d
0x18000284f  xorps   xmm0, xmm0
0x180002852  movups  xmmword ptr [rsp+0F0h+pExceptionObject+8], xmm0
0x180002857  mov     [rbp+2Fh+var_A8], 4
0x18000285e  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180002865  mov     qword ptr [rsp+0F0h+pExceptionObject], rax
0x18000286a  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180002871  lea     rcx, [rsp+0F0h+pExceptionObject]; pExceptionObject
0x180002876  call    _CxxThrowException_0
0x18000287c  mov     rdx, rsi; struct Broker::ApplicationIdentity *
0x18000287f  lea     rcx, [rbp+2Fh+var_70]; this
0x180002883  call    ??0ApplicationIdentity@Broker@@QEAA@AEBU01@@Z; Broker::ApplicationIdentity::ApplicationIdentity(Broker::ApplicationIdentity const &)
0x180002888  mov     r8, r14
0x18000288b  mov     rdx, rax
0x18000288e  mov     rcx, rbx
0x180002891  call    ?CheckSignalPermissions@SebEvent@Broker@@QEAA_NUApplicationIdentity@2@PEAVRpcClientToken@2@@Z; Broker::SebEvent::CheckSignalPermissions(Broker::ApplicationIdentity,Broker::RpcClientToken *)
0x180002896  test    al, al
0x180002898  jnz     short loc_1800028FD
0x18000289a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028a1  test    byte ptr [rcx+1Ch], 1
0x1800028a5  jz      short loc_1800028D0
0x1800028a7  cmp     byte ptr [rcx+19h], 2
0x1800028ab  jb      short loc_1800028D0
0x1800028ad  lea     r9, [rbx+40h]
0x1800028b1  cmp     qword ptr [r9+18h], 7
0x1800028b6  jbe     short loc_1800028BB
0x1800028b8  mov     r9, [r9]
0x1800028bb  mov     edx, 67h ; 'g'
0x1800028c0  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x1800028c7  mov     rcx, [rcx+10h]
0x1800028cb  call    WPP_SF_S
0x1800028d0  xorps   xmm0, xmm0
0x1800028d3  movups  xmmword ptr [rsp+0F0h+pExceptionObject+8], xmm0
0x1800028d8  mov     [rbp+2Fh+var_A8], 5
0x1800028df  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x1800028e6  mov     qword ptr [rsp+0F0h+pExceptionObject], rax
0x1800028eb  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x1800028f2  lea     rcx, [rsp+0F0h+pExceptionObject]; pExceptionObject
0x1800028f7  call    _CxxThrowException_0
0x1800028fd  mov     rax, [rbp+2Fh+arg_40]
0x180002901  mov     [rsp+0F0h+var_C8], rax; enum _BI_ACTIVATION_STATUS *
0x180002906  mov     rax, [rbp+2Fh+arg_38]
0x18000290a  mov     [rsp+0F0h+var_D0], rax; struct _GUID *
0x18000290f  mov     r9d, [rbp+2Fh+arg_30]; unsigned int
0x180002913  mov     r8, [rbp+2Fh+arg_28]; unsigned __int8 *
0x180002917  mov     rdx, [rbp+2Fh+arg_20]; unsigned __int8 *
0x18000291b  mov     rcx, rbx; this
0x18000291e  call    ?SignalSyncEvent@SebEvent@Broker@@QEAAKPEAEPEBEKPEBU_GUID@@PEAW4_BI_ACTIVATION_STATUS@@@Z; Broker::SebEvent::SignalSyncEvent(uchar *,uchar const *,ulong,_GUID const *,_BI_ACTIVATION_STATUS *)
0x180002923  test    eax, eax
0x180002925  jz      short loc_180002957
0x180002927  xorps   xmm0, xmm0
0x18000292a  movups  xmmword ptr [rsp+0F0h+pExceptionObject+8], xmm0
0x18000292f  mov     [rbp+2Fh+var_A8], 1
0x180002936  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000293d  mov     qword ptr [rsp+0F0h+pExceptionObject], rcx
0x180002942  mov     [rbp+2Fh+var_A0], eax
0x180002945  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000294c  lea     rcx, [rsp+0F0h+pExceptionObject]; pExceptionObject
0x180002951  call    _CxxThrowException_0
0x180002957  mov     rcx, cs:WPP_GLOBAL_Control
0x18000295e  test    byte ptr [rcx+1Ch], 1
0x180002962  jz      short loc_180002980
0x180002964  cmp     byte ptr [rcx+19h], 4
0x180002968  jb      short loc_180002980
0x18000296a  mov     edx, 68h ; 'h'
0x18000296f  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180002976  mov     rcx, [rcx+10h]
0x18000297a  call    WPP_SF_
0x18000297f  nop
0x180002980  cmp     dword ptr [rbp+2Fh+var_88+4], 0
0x180002984  jz      short loc_180002990
0x180002986  lea     rcx, [rbp+2Fh+var_90]; this
0x18000298a  call    ?Release@BrokerLock@Broker@@QEAAXXZ; Broker::BrokerLock::Release(void)
0x18000298f  nop
0x180002990  mov     rcx, [rbp+2Fh+var_80+8]; this
0x180002994  test    rcx, rcx
0x180002997  jz      short loc_18000299E
0x180002999  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000299e  lea     r11, [rsp+0F0h+var_10]
0x1800029a6  mov     rbx, [r11+28h]
0x1800029aa  mov     rsi, [r11+30h]
0x1800029ae  mov     rsp, r11
0x1800029b1  pop     r14
0x1800029b3  pop     rdi
0x1800029b4  pop     rbp
0x1800029b5  retn
```
