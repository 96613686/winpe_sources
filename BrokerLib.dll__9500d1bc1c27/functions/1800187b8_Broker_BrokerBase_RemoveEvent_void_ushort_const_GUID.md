# Broker::BrokerBase::RemoveEvent(void *,ushort const *,_GUID)

- ea: `0x1800187b8`
- end: `0x1800188b8`
- name: `?RemoveEvent@BrokerBase@Broker@@QEAAXPEAXPEBGU_GUID@@@Z`
- size: `256`
- prototype: `void(Broker::BrokerBase *__hidden this, void *, const unsigned __int16 *, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016e80`

## callees

- `0x180004ae0`
- `0x180004d70`
- `0x180006b30`
- `0x180009d9c`
- `0x18000a0d0`
- `0x18000d5cc`
- `0x180015af0`
- `0x1800165da`
- `0x1800173f8`
- `0x1800183bc`
- `0x1800187b8`
- `0x18001a364`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800187f6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800187f6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018857`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018857`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Broker::BrokerBase::RemoveEvent(
        Broker::BrokerBase *this,
        void *a2,
        const unsigned __int16 *a3,
        struct _GUID *a4)
{
  __int64 v6; // rax
  __int64 v7; // r9
  const struct _GUID *v8; // rdx
  std::_Ref_count_base *v9[2]; // [rsp+20h] [rbp-D8h] BYREF
  Broker::BrokerBase *v10; // [rsp+30h] [rbp-C8h]
  Broker::BILayer::Failure *v11; // [rsp+38h] [rbp-C0h] BYREF
  _BYTE v12[8]; // [rsp+40h] [rbp-B8h] BYREF
  std::_Ref_count_base *v13; // [rsp+48h] [rbp-B0h]
  _BYTE pExceptionObject[32]; // [rsp+50h] [rbp-A8h] BYREF
  _BYTE v15[96]; // [rsp+70h] [rbp-88h] BYREF

  v10 = this;
  *(_OWORD *)v9 = 0;
  Broker::ApplicationIdentity::ApplicationIdentity((Broker::ApplicationIdentity *)v15, a2, a3);
  RtlAcquireSRWLockExclusive(this);
  try
  {
    v6 = Broker::BrokeredEventTable::Find((char *)this + 208, v12, a4);
    std::shared_ptr<Broker::BrokerEvent>::operator=(v9, v6);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( Broker::ApplicationIdentity::operator!=((__int64)v15, *((_QWORD *)v9[0] + 6)) )
    {
      Broker::AccessDenied::AccessDenied((Broker::AccessDenied *)pExceptionObject);
      throw (Broker::AccessDenied *)pExceptionObject;
    }
    Broker::BrokerBase::DestroyEvent((__int64)this, 0, v9, v7);
  }
  catch ( ... )
  {
    Broker::BrokerBase::UnlockInstance(v10, 0);
    throw;
  }
  RtlReleaseSRWLockExclusive(this);
  try
  {
    Broker::BILayer::DeleteEvent((Broker::BILayer *)a4, v8);
  }
  catch ( Broker::BILayer::Failure *v11 )
  {
    if ( *((_DWORD *)v11 + 8) != -1073741275 )
      throw;
  }
  Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v15);
  if ( v9[1] )
    std::_Ref_count_base::_Decref(v9[1]);
}

```

## disassembly

```asm
0x1800187b8  push    rbx
0x1800187ba  push    rdi
0x1800187bb  sub     rsp, 0E8h
0x1800187c2  mov     rax, cs:__security_cookie
0x1800187c9  xor     rax, rsp
0x1800187cc  mov     [rsp+0F8h+var_28], rax
0x1800187d4  mov     rdi, r9
0x1800187d7  mov     rbx, rcx
0x1800187da  mov     [rsp+0F8h+var_C8], rcx
0x1800187df  xorps   xmm0, xmm0
0x1800187e2  movdqu  xmmword ptr [rsp+0F8h+var_D8], xmm0
0x1800187e8  lea     rcx, [rsp+0F8h+var_88]; this
0x1800187ed  call    ??0ApplicationIdentity@Broker@@QEAA@PEAXQEBG@Z; Broker::ApplicationIdentity::ApplicationIdentity(void *,ushort const * const)
0x1800187f2  nop
0x1800187f3  mov     rcx, rbx
0x1800187f6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800187fc  nop
0x1800187fd  lea     rcx, [rbx+0D0h]
0x180018804  mov     r8, rdi
0x180018807  lea     rdx, [rsp+0F8h+var_B8]
0x18001880c  call    ?Find@BrokeredEventTable@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokeredEventTable::Find(_GUID const &)
0x180018811  mov     rdx, rax
0x180018814  lea     rcx, [rsp+0F8h+var_D8]
0x180018819  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x18001881e  mov     rcx, [rsp+0F8h+var_B0]; this
0x180018823  test    rcx, rcx
0x180018826  jz      short loc_18001882D
0x180018828  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001882d  mov     rdx, [rsp+0F8h+var_D8]
0x180018832  mov     rdx, [rdx+30h]
0x180018836  lea     rcx, [rsp+0F8h+var_88]
0x18001883b  call    ??9ApplicationIdentity@Broker@@QEBA_NAEBU01@@Z; Broker::ApplicationIdentity::operator!=(Broker::ApplicationIdentity const &)
0x180018840  test    al, al
0x180018842  jnz     short loc_18001889B
0x180018844  lea     r8, [rsp+0F8h+var_D8]
0x180018849  xor     edx, edx
0x18001884b  mov     rcx, rbx
0x18001884e  call    ?DestroyEvent@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEAV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::DestroyEvent(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> &)
0x180018853  nop
0x180018854  mov     rcx, rbx
0x180018857  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001885d  nop
0x18001885e  mov     rcx, rdi; this
0x180018861  call    ?DeleteEvent@BILayer@Broker@@YAXAEBU_GUID@@@Z; Broker::BILayer::DeleteEvent(_GUID const &)
0x180018866  nop
0x180018867  lea     rcx, [rsp+0F8h+var_88]; this
0x18001886c  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180018871  nop
0x180018872  mov     rcx, [rsp+0F8h+var_D8+8]; this
0x180018877  test    rcx, rcx
0x18001887a  jz      short loc_180018881
0x18001887c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018881  mov     rcx, [rsp+0F8h+var_28]
0x180018889  xor     rcx, rsp; StackCookie
0x18001888c  call    __security_check_cookie
0x180018891  add     rsp, 0E8h
0x180018898  pop     rdi
0x180018899  pop     rbx
0x18001889a  retn
0x18001889b  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x1800188a0  call    ??0AccessDenied@Broker@@QEAA@XZ; Broker::AccessDenied::AccessDenied(void)
0x1800188a5  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x1800188ac  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x1800188b1  call    _CxxThrowException_0
```
