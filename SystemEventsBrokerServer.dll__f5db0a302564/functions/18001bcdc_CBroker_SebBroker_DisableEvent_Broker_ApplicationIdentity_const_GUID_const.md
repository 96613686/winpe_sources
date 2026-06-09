# CBroker::SebBroker::DisableEvent(Broker::ApplicationIdentity const &,_GUID const &)

- ea: `0x18001bcdc`
- end: `0x18001be2e`
- name: `?DisableEvent@SebBroker@CBroker@@QEAAXAEBUApplicationIdentity@Broker@@AEBU_GUID@@@Z`
- size: `338`
- prototype: `void __fastcall(struct _RTL_SRWLOCK *this, const struct Broker::ApplicationIdentity *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004610`

## callees

- `0x1800076a0`
- `0x180008c00`
- `0x18000c910`
- `0x18000cb50`
- `0x180013820`
- `0x180013860`
- `0x180013920`
- `0x18001bcdc`
- `0x18001c00c`
- `0x18001d9ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBroker::SebBroker::DisableEvent(
        struct _RTL_SRWLOCK *this,
        const struct Broker::ApplicationIdentity *a2,
        const struct _GUID *a3)
{
  CBroker::SebEvent *v6; // rsi
  _QWORD *v7; // rax
  CBroker::SebEvent *v8; // [rsp+30h] [rbp-48h] BYREF
  std::_Ref_count_base *v9; // [rsp+38h] [rbp-40h]
  _BYTE v10[16]; // [rsp+40h] [rbp-38h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-28h] BYREF
  __int128 v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+68h] [rbp-10h]

  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v10, this + 1, 1);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids, a3);
  Broker::BrokerEventTable<CBroker::SebEvent>::Find(&this[2], &v8, a3);
  v6 = v8;
  if ( Broker::ApplicationIdentity::operator!=((__int64)v8 + 8, (__int64)a2) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = (_QWORD *)((char *)a2 + 56);
      if ( *((_QWORD *)a2 + 10) > 7u )
        v7 = (_QWORD *)*v7;
      WPP_SF__guid__sid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), *(PSID *)a2, (__int64)v7);
    }
    v12 = 0;
    v13 = 5;
    pExceptionObject = &Broker::AccessDenied::`vftable';
    throw (Broker::AccessDenied *)&pExceptionObject;
  }
  CBroker::SebEvent::OnDisable(v6, 0);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids, a3);
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v10);
}

```

## disassembly

```asm
0x18001bcdc  mov     [rsp+arg_0], rbx
0x18001bce1  mov     [rsp+arg_8], rsi
0x18001bce6  push    rdi
0x18001bce7  sub     rsp, 70h
0x18001bceb  mov     rbx, r8
0x18001bcee  mov     rdi, rdx
0x18001bcf1  mov     rsi, rcx
0x18001bcf4  lea     rdx, [rcx+8]; struct _RTL_SRWLOCK *
0x18001bcf8  mov     r8b, 1; bool
0x18001bcfb  lea     rcx, [rsp+78h+var_38]; this
0x18001bd00  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x18001bd05  nop
0x18001bd06  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd0d  test    byte ptr [rcx+1Ch], 1
0x18001bd11  jz      short loc_18001BD31
0x18001bd13  cmp     byte ptr [rcx+19h], 4
0x18001bd17  jb      short loc_18001BD31
0x18001bd19  mov     edx, 20h ; ' '
0x18001bd1e  mov     r9, rbx
0x18001bd21  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001bd28  mov     rcx, [rcx+10h]
0x18001bd2c  call    WPP_SF__guid_
0x18001bd31  lea     rcx, [rsi+10h]
0x18001bd35  mov     r8, rbx
0x18001bd38  lea     rdx, [rsp+78h+var_48]
0x18001bd3d  call    ?Find@?$BrokerEventTable@VSebEvent@CBroker@@@Broker@@QEAA?AV?$shared_ptr@VSebEvent@CBroker@@@std@@AEBU_GUID@@@Z; Broker::BrokerEventTable<CBroker::SebEvent>::Find(_GUID const &)
0x18001bd42  nop
0x18001bd43  mov     rsi, [rsp+78h+var_48]
0x18001bd48  lea     rcx, [rsi+8]
0x18001bd4c  mov     rdx, rdi
0x18001bd4f  call    ??9ApplicationIdentity@Broker@@QEBA_NAEBU01@@Z; Broker::ApplicationIdentity::operator!=(Broker::ApplicationIdentity const &)
0x18001bd54  test    al, al
0x18001bd56  jz      short loc_18001BDCC
0x18001bd58  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd5f  test    byte ptr [rcx+1Ch], 20h
0x18001bd63  jz      short loc_18001BD9E
0x18001bd65  cmp     byte ptr [rcx+19h], 2
0x18001bd69  jb      short loc_18001BD9E
0x18001bd6b  lea     rax, [rdi+38h]
0x18001bd6f  cmp     qword ptr [rax+18h], 7
0x18001bd74  jbe     short loc_18001BD79
0x18001bd76  mov     rax, [rax]
0x18001bd79  mov     edx, 21h ; '!'
0x18001bd7e  mov     [rsp+78h+var_50], rax; __int64
0x18001bd83  mov     rax, [rdi]
0x18001bd86  mov     [rsp+78h+pSid], rax; pSid
0x18001bd8b  mov     r9, rbx
0x18001bd8e  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001bd95  mov     rcx, [rcx+10h]; LoggerHandle
0x18001bd99  call    WPP_SF__guid__sid_S
0x18001bd9e  xorps   xmm0, xmm0
0x18001bda1  movups  [rsp+78h+var_20], xmm0
0x18001bda6  mov     [rsp+78h+var_10], 5
0x18001bdae  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x18001bdb5  mov     [rsp+78h+pExceptionObject], rax
0x18001bdba  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x18001bdc1  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001bdc6  call    _CxxThrowException_0
0x18001bdcc  xor     edx, edx; bool
0x18001bdce  mov     rcx, rsi; this
0x18001bdd1  call    ?OnDisable@SebEvent@CBroker@@QEAAX_N@Z; CBroker::SebEvent::OnDisable(bool)
0x18001bdd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bddd  test    byte ptr [rcx+1Ch], 1
0x18001bde1  jz      short loc_18001BE02
0x18001bde3  cmp     byte ptr [rcx+19h], 4
0x18001bde7  jb      short loc_18001BE02
0x18001bde9  mov     edx, 22h ; '"'
0x18001bdee  mov     r9, rbx
0x18001bdf1  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001bdf8  mov     rcx, [rcx+10h]
0x18001bdfc  call    WPP_SF__guid_
0x18001be01  nop
0x18001be02  mov     rcx, [rsp+78h+var_40]; this
0x18001be07  test    rcx, rcx
0x18001be0a  jz      short loc_18001BE12
0x18001be0c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001be11  nop
0x18001be12  lea     rcx, [rsp+78h+var_38]; this
0x18001be17  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x18001be1c  lea     r11, [rsp+78h+var_8]
0x18001be21  mov     rbx, [r11+10h]
0x18001be25  mov     rsi, [r11+18h]
0x18001be29  mov     rsp, r11
0x18001be2c  pop     rdi
0x18001be2d  retn
```
