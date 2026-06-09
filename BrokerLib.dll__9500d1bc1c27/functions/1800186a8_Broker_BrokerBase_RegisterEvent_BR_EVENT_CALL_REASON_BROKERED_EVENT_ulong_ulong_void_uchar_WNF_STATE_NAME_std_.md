# Broker::BrokerBase::RegisterEvent(_BR_EVENT_CALL_REASON,_BROKERED_EVENT *,ulong,ulong,void *,uchar,_WNF_STATE_NAME *,std::shared_ptr<Broker::BrokerEvent> *)

- ea: `0x1800186a8`
- end: `0x1800187af`
- name: `?RegisterEvent@BrokerBase@Broker@@QEAAXW4_BR_EVENT_CALL_REASON@@PEAU_BROKERED_EVENT@@KKPEAXEPEAU_WNF_STATE_NAME@@PEAV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD, __int64, char)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180016d80`
- `0x180017a9c`
- `0x1800188c0`

## callees

- `0x180004500`
- `0x180004ae0`
- `0x180005b50`
- `0x1800165da`
- `0x180017460`
- `0x1800178fc`
- `0x1800186a8`

## pseudocode

```c
void __fastcall Broker::BrokerBase::RegisterEvent(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        char a7,
        __int64 a8,
        __int64 a9)
{
  __int64 *v13; // rax
  __int64 *v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  std::_Ref_count_base *v18; // rcx
  __int64 v19; // [rsp+50h] [rbp-58h] BYREF
  std::_Ref_count_base *v20; // [rsp+58h] [rbp-50h]
  std::_Ref_count_base *pExceptionObject[9]; // [rsp+60h] [rbp-48h] BYREF

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *(_QWORD *)(a1 + 8));
  if ( !a3 )
  {
    Broker::InvalidParameter::InvalidParameter((Broker::InvalidParameter *)pExceptionObject);
    throw (Broker::InvalidParameter *)pExceptionObject;
  }
  Broker::BrokerBase::ConstructEvent(a1, &v19, a2, a3, a4, a5, a6, a7);
  if ( a9 )
  {
    v13 = std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(pExceptionObject, &v19);
    v15 = *v13;
    *v13 = *v14;
    v16 = v14[1];
    *v14 = v15;
    v17 = v13[1];
    v13[1] = v16;
    v18 = pExceptionObject[1];
    v14[1] = v17;
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
  }
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
}

```

## disassembly

```asm
0x1800186a8  push    rbx
0x1800186aa  push    rbp
0x1800186ab  push    rsi
0x1800186ac  push    rdi
0x1800186ad  sub     rsp, 88h
0x1800186b4  mov     esi, r9d
0x1800186b7  mov     rbx, r8
0x1800186ba  mov     ebp, edx
0x1800186bc  mov     rdi, rcx
0x1800186bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186c6  test    dword ptr [rcx+1Ch], 800h
0x1800186cd  jz      short loc_1800186EE
0x1800186cf  cmp     byte ptr [rcx+19h], 5
0x1800186d3  jb      short loc_1800186EE
0x1800186d5  mov     r9, [rdi+8]
0x1800186d9  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x1800186e0  mov     rcx, [rcx+10h]
0x1800186e4  mov     edx, 21h ; '!'
0x1800186e9  call    WPP_SF__guid_
0x1800186ee  test    rbx, rbx
0x1800186f1  jz      loc_180018793
0x1800186f7  mov     al, [rsp+0A8h+arg_30]
0x1800186fe  lea     rdx, [rsp+0A8h+var_58]
0x180018703  mov     [rsp+0A8h+var_70], al
0x180018707  mov     r9, rbx
0x18001870a  mov     rax, [rsp+0A8h+arg_28]
0x180018712  mov     r8d, ebp
0x180018715  mov     [rsp+0A8h+var_78], rax
0x18001871a  mov     rcx, rdi
0x18001871d  mov     eax, [rsp+0A8h+arg_20]
0x180018724  mov     [rsp+0A8h+var_80], eax
0x180018728  mov     [rsp+0A8h+var_88], esi
0x18001872c  call    ?ConstructEvent@BrokerBase@Broker@@AEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@W4_BR_EVENT_CALL_REASON@@PEAU_BROKERED_EVENT@@KKPEAXEPEAU_WNF_STATE_NAME@@@Z; Broker::BrokerBase::ConstructEvent(_BR_EVENT_CALL_REASON,_BROKERED_EVENT *,ulong,ulong,void *,uchar,_WNF_STATE_NAME *)
0x180018731  mov     r8, [rsp+0A8h+arg_40]
0x180018739  test    r8, r8
0x18001873c  jz      short loc_180018778
0x18001873e  lea     rdx, [rsp+0A8h+var_58]
0x180018743  lea     rcx, [rsp+0A8h+pExceptionObject]
0x180018748  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x18001874d  mov     rcx, [r8]
0x180018750  mov     rdx, [rax]
0x180018753  mov     [rax], rcx
0x180018756  mov     rcx, [r8+8]
0x18001875a  mov     [r8], rdx
0x18001875d  mov     rdx, [rax+8]
0x180018761  mov     [rax+8], rcx
0x180018765  mov     rcx, [rsp+0A8h+var_40]; this
0x18001876a  mov     [r8+8], rdx
0x18001876e  test    rcx, rcx
0x180018771  jz      short loc_180018778
0x180018773  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018778  mov     rcx, [rsp+0A8h+var_50]; this
0x18001877d  test    rcx, rcx
0x180018780  jz      short loc_180018787
0x180018782  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018787  add     rsp, 88h
0x18001878e  pop     rdi
0x18001878f  pop     rsi
0x180018790  pop     rbp
0x180018791  pop     rbx
0x180018792  retn
0x180018793  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x180018798  call    ??0InvalidParameter@Broker@@QEAA@XZ; Broker::InvalidParameter::InvalidParameter(void)
0x18001879d  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800187a4  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1800187a9  call    _CxxThrowException_0
```
