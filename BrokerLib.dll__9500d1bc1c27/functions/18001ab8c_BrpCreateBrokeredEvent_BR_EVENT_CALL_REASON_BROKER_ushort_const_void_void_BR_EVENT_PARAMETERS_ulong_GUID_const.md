# BrpCreateBrokeredEvent(_BR_EVENT_CALL_REASON,_BROKER *,ushort const *,void *,void *,_BR_EVENT_PARAMETERS *,ulong,_GUID const *,_BROKERED_EVENT * *,_BR_NEW_EVENT_INFORMATION *,_CBROKERED_EVENT_ID *)

- ea: `0x18001ab8c`
- end: `0x18001addb`
- name: `?BrpCreateBrokeredEvent@@YAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEBGPEAX3PEAU_BR_EVENT_PARAMETERS@@KPEBU_GUID@@PEAPEAU_BROKERED_EVENT@@PEAU_BR_NEW_EVENT_INFORMATION@@PEAU_CBROKERED_EVENT_ID@@@Z`
- size: `591`
- prototype: `unsigned int __high(enum _BR_EVENT_CALL_REASON, struct _BROKER *, const unsigned __int16 *, void *, void *, struct _BR_EVENT_PARAMETERS *, unsigned int, const struct _GUID *, struct _BROKERED_EVENT **, struct _BR_NEW_EVENT_INFORMATION *, struct _CBROKERED_EVENT_ID *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180010080`

## callees

- `0x180004ae0`
- `0x180004d70`
- `0x1800058e0`
- `0x180006b30`
- `0x180007350`
- `0x180009e94`
- `0x18000a0d0`
- `0x18000b3a4`
- `0x18000e628`
- `0x18000f330`
- `0x18000fb84`
- `0x180015af0`
- `0x180017a9c`
- `0x18001ab8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall BrpCreateBrokeredEvent(
        unsigned int a1,
        const void *a2,
        const unsigned __int16 *a3,
        void *a4,
        __int64 a5,
        Broker::BrokerBase *a6,
        int a7,
        _OWORD *a8,
        struct _BROKERED_EVENT **a9,
        _OWORD *a10,
        _QWORD *a11)
{
  Broker::BrokerBase *v15; // rbx
  unsigned int v16; // edi
  __int64 AppId; // rax
  bool v18; // bl
  __int64 v20; // [rsp+20h] [rbp-188h]
  HANDLE v21[2]; // [rsp+68h] [rbp-140h] BYREF
  Broker::BrokerBase *v22; // [rsp+78h] [rbp-130h] BYREF
  std::_Ref_count_base *v23; // [rsp+80h] [rbp-128h]
  _QWORD *v24; // [rsp+88h] [rbp-120h]
  _OWORD *v25; // [rsp+90h] [rbp-118h]
  _BYTE v26[96]; // [rsp+A0h] [rbp-108h] BYREF
  _BYTE v27[96]; // [rsp+100h] [rbp-A8h] BYREF

  v15 = a6;
  v22 = a6;
  v25 = a10;
  v24 = a11;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_aedb1da3e26b324cbac6301bae0d271e_Traceguids);
  if ( !a2 || (v16 = 0, !a9) )
  {
    v16 = 87;
    goto LABEL_17;
  }
  Broker::RpcClientToken::RpcClientToken((Broker::RpcClientToken *)v21);
  if ( Broker::RpcClientToken::IsAppContainer(v21) )
  {
    if ( !a3 || !a4 )
    {
      v16 = 5;
      Broker::RpcClientToken::~RpcClientToken((Broker::RpcClientToken *)v21);
      goto LABEL_17;
    }
    Broker::ApplicationIdentity::ApplicationIdentity((Broker::ApplicationIdentity *)v26, a4, a3);
    AppId = Broker::RpcClientToken::GetAppId(v21, v27);
    v18 = Broker::ApplicationIdentity::operator!=((__int64)v26, AppId);
    Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v27);
    if ( v18 )
    {
      v16 = 5;
      Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v26);
      Broker::RpcClientToken::~RpcClientToken((Broker::RpcClientToken *)v21);
LABEL_17:
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_aedb1da3e26b324cbac6301bae0d271e_Traceguids, v16);
      return v16;
    }
    Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v26);
    v15 = v22;
  }
  Broker::BrokerBase::GetInstance(&v22, a2);
  Broker::BrokerBase::CreateBrokeredEventEA(v22, a1, a3, a4, v20, (__int64)v15, a7, a8, a9, v25, v24);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  Broker::RpcClientToken::~RpcClientToken((Broker::RpcClientToken *)v21);
  return v16;
}

```

## disassembly

```asm
0x18001ab8c  push    rbx
0x18001ab8e  push    rsi
0x18001ab8f  push    rdi
0x18001ab90  push    r12
0x18001ab92  push    r13
0x18001ab94  push    r14
0x18001ab96  push    r15
0x18001ab98  sub     rsp, 170h
0x18001ab9f  mov     rax, cs:__security_cookie
0x18001aba6  xor     rax, rsp
0x18001aba9  mov     [rsp+1A8h+var_48], rax
0x18001abb1  mov     r15, r9
0x18001abb4  mov     r14, r8
0x18001abb7  mov     rsi, rdx
0x18001abba  mov     r13d, ecx
0x18001abbd  mov     rbx, [rsp+1A8h+arg_28]
0x18001abc5  mov     [rsp+1A8h+var_130], rbx
0x18001abca  mov     r12, [rsp+1A8h+arg_40]
0x18001abd2  mov     rax, [rsp+1A8h+arg_48]
0x18001abda  mov     [rsp+1A8h+var_118], rax
0x18001abe2  mov     rax, [rsp+1A8h+arg_50]
0x18001abea  mov     [rsp+1A8h+var_120], rax
0x18001abf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abf9  test    dword ptr [rcx+1Ch], 800h
0x18001ac00  jz      short loc_18001AC1D
0x18001ac02  cmp     byte ptr [rcx+19h], 5
0x18001ac06  jb      short loc_18001AC1D
0x18001ac08  mov     edx, 0Ch
0x18001ac0d  lea     r8, WPP_aedb1da3e26b324cbac6301bae0d271e_Traceguids
0x18001ac14  mov     rcx, [rcx+10h]
0x18001ac18  call    WPP_SF_
0x18001ac1d  test    rsi, rsi
0x18001ac20  jz      loc_18001AD83
0x18001ac26  xor     edi, edi
0x18001ac28  test    r12, r12
0x18001ac2b  jz      loc_18001AD83
0x18001ac31  lea     rcx, [rsp+1A8h+var_140]; this
0x18001ac36  call    ??0RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::RpcClientToken(void)
0x18001ac3b  nop
0x18001ac3c  lea     rcx, [rsp+1A8h+var_140]; this
0x18001ac41  call    ?IsAppContainer@RpcClientToken@Broker@@QEAA_NXZ; Broker::RpcClientToken::IsAppContainer(void)
0x18001ac46  test    al, al
0x18001ac48  jz      loc_18001ACF5
0x18001ac4e  test    r14, r14
0x18001ac51  jz      loc_18001ACE0
0x18001ac57  test    r15, r15
0x18001ac5a  jz      loc_18001ACE0
0x18001ac60  mov     r8, r14; unsigned __int16 *
0x18001ac63  mov     rdx, r15; void *
0x18001ac66  lea     rcx, [rsp+1A8h+var_108]; this
0x18001ac6e  call    ??0ApplicationIdentity@Broker@@QEAA@PEAXQEBG@Z; Broker::ApplicationIdentity::ApplicationIdentity(void *,ushort const * const)
0x18001ac73  nop
0x18001ac74  lea     rdx, [rsp+1A8h+var_A8]
0x18001ac7c  lea     rcx, [rsp+1A8h+var_140]
0x18001ac81  call    ?GetAppId@RpcClientToken@Broker@@QEAA?AUApplicationIdentity@2@PEBG_N@Z; Broker::RpcClientToken::GetAppId(ushort const *,bool)
0x18001ac86  mov     rdx, rax
0x18001ac89  lea     rcx, [rsp+1A8h+var_108]
0x18001ac91  call    ??9ApplicationIdentity@Broker@@QEBA_NAEBU01@@Z; Broker::ApplicationIdentity::operator!=(Broker::ApplicationIdentity const &)
0x18001ac96  mov     bl, al
0x18001ac98  lea     rcx, [rsp+1A8h+var_A8]; this
0x18001aca0  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x18001aca5  test    bl, bl
0x18001aca7  jz      short loc_18001ACCC
0x18001aca9  mov     edi, 5
0x18001acae  lea     rcx, [rsp+1A8h+var_108]; this
0x18001acb6  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x18001acbb  nop
0x18001acbc  lea     rcx, [rsp+1A8h+var_140]; this
0x18001acc1  call    ??1RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::~RpcClientToken(void)
0x18001acc6  nop
0x18001acc7  jmp     loc_18001AD88
0x18001accc  lea     rcx, [rsp+1A8h+var_108]; this
0x18001acd4  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x18001acd9  mov     rbx, [rsp+1A8h+var_130]
0x18001acde  jmp     short loc_18001ACF5
0x18001ace0  mov     edi, 5
0x18001ace5  lea     rcx, [rsp+1A8h+var_140]; this
0x18001acea  call    ??1RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::~RpcClientToken(void)
0x18001acef  nop
0x18001acf0  jmp     loc_18001AD88
0x18001acf5  mov     rdx, rsi
0x18001acf8  lea     rcx, [rsp+1A8h+var_130]
0x18001acfd  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x18001ad02  nop
0x18001ad03  mov     rax, [rsp+1A8h+var_120]
0x18001ad0b  mov     [rsp+1A8h+var_158], rax
0x18001ad10  mov     rax, [rsp+1A8h+var_118]
0x18001ad18  mov     [rsp+1A8h+var_160], rax
0x18001ad1d  mov     [rsp+1A8h+var_168], r12
0x18001ad22  mov     rax, [rsp+1A8h+arg_38]
0x18001ad2a  mov     [rsp+1A8h+var_170], rax
0x18001ad2f  mov     eax, [rsp+1A8h+arg_30]
0x18001ad36  mov     [rsp+1A8h+var_178], eax
0x18001ad3a  mov     [rsp+1A8h+var_180], rbx
0x18001ad3f  mov     r9, r15
0x18001ad42  mov     r8, r14
0x18001ad45  mov     edx, r13d
0x18001ad48  mov     rcx, [rsp+1A8h+var_130]
0x18001ad4d  call    ?CreateBrokeredEventEA@BrokerBase@Broker@@QEAAXW4_BR_EVENT_CALL_REASON@@PEBGPEAX2PEAU_BR_EVENT_PARAMETERS@@KPEBU_GUID@@PEAPEAU_BROKERED_EVENT@@PEAU_BR_NEW_EVENT_INFORMATION@@PEAU_CBROKERED_EVENT_ID@@@Z; Broker::BrokerBase::CreateBrokeredEventEA(_BR_EVENT_CALL_REASON,ushort const *,void *,void *,_BR_EVENT_PARAMETERS *,ulong,_GUID const *,_BROKERED_EVENT * *,_BR_NEW_EVENT_INFORMATION *,_CBROKERED_EVENT_ID *)
0x18001ad52  nop
0x18001ad53  mov     rcx, [rsp+1A8h+var_128]; this
0x18001ad5b  test    rcx, rcx
0x18001ad5e  jz      short loc_18001AD66
0x18001ad60  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ad65  nop
0x18001ad66  lea     rcx, [rsp+1A8h+var_140]; this
0x18001ad6b  call    ??1RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::~RpcClientToken(void)
0x18001ad70  nop
0x18001ad71  jmp     short loc_18001ADB6
0x18001ad73  mov     edi, [rsp+1A8h+var_148]
0x18001ad77  jmp     short loc_18001AD88
0x18001ad79  mov     edi, [rsp+1A8h+var_148]
0x18001ad7d  test    edi, edi
0x18001ad7f  jz      short loc_18001ADB6
0x18001ad81  jmp     short loc_18001AD88
0x18001ad83  mov     edi, 57h ; 'W'
0x18001ad88  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad8f  test    dword ptr [rcx+1Ch], 800h
0x18001ad96  jz      short loc_18001ADB6
0x18001ad98  cmp     byte ptr [rcx+19h], 2
0x18001ad9c  jb      short loc_18001ADB6
0x18001ad9e  mov     edx, 0Dh
0x18001ada3  mov     r9d, edi
0x18001ada6  lea     r8, WPP_aedb1da3e26b324cbac6301bae0d271e_Traceguids
0x18001adad  mov     rcx, [rcx+10h]
0x18001adb1  call    WPP_SF_d
0x18001adb6  mov     eax, edi
0x18001adb8  mov     rcx, [rsp+1A8h+var_48]
0x18001adc0  xor     rcx, rsp; StackCookie
0x18001adc3  call    __security_check_cookie
0x18001adc8  add     rsp, 170h
0x18001adcf  pop     r15
0x18001add1  pop     r14
0x18001add3  pop     r13
0x18001add5  pop     r12
0x18001add7  pop     rdi
0x18001add8  pop     rsi
0x18001add9  pop     rbx
0x18001adda  retn
```
