# ?SendDuplexRepliesDuringAsyncSequence@VmMigrationTcpTransport@@IEAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@Z

- ea: `0x140095270`
- end: `0x1400958e7`
- name: `?SendDuplexRepliesDuringAsyncSequence@VmMigrationTcpTransport@@IEAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@Z`
- size: `1655`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *this)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14006af38`
- `0x14007e580`
- `0x14007f44c`
- `0x1400950c0`
- `0x140095190`
- `0x140095270`
- `0x140095d6c`
- `0x140096ab4`
- `0x1400988d0`
- `0x14009f9ec`
- `0x1400c5a1c`
- `0x140132940`
- `0x140184e70`
- `0x1401dd648`
- `0x1401dfdcc`
- `0x1401e1038`
- `0x1401e126c`
- `0x1402c2010`

## string_xrefs

- `0x1400952c4`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400952ef`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14009531d`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14009534b`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14009537e`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400953ac`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400954f8`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095560`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14009557f`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400955e5`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095613`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095648`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400956b5`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095747`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14009578b`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400957cc`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400957ec`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095832`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095851`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095870`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14009588f`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall VmMigrationTcpTransport::SendDuplexRepliesDuringAsyncSequence(
        VmMigrationTcpTransport *this,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4)
{
  wil::details::in1diag3 *v7; // r10
  wil::details::in1diag3 *v8; // r10
  __int64 v9; // r11
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 *v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rcx
  char v18; // r12
  bool v19; // di
  char v20; // r15
  VmMigrationSettings *v21; // rcx
  unsigned int MigrationMessageDefaultTimeout; // eax
  const char *v23; // rax
  struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *v24; // rax
  const char *IsSet; // rax
  const char *v26; // r9
  const char *v27; // rax
  int v28; // eax
  const char *v29; // r9
  __int64 result; // rax
  int v31; // [rsp+20h] [rbp-128h]
  int v32; // [rsp+20h] [rbp-128h]
  char *v33; // [rsp+30h] [rbp-118h]
  char *v34; // [rsp+30h] [rbp-118h]
  _QWORD v35[2]; // [rsp+60h] [rbp-E8h] BYREF
  _QWORD v36[2]; // [rsp+70h] [rbp-D8h] BYREF
  _QWORD v37[2]; // [rsp+80h] [rbp-C8h] BYREF
  struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *v38; // [rsp+90h] [rbp-B8h] BYREF
  void *v39; // [rsp+98h] [rbp-B0h]
  void *v40; // [rsp+A0h] [rbp-A8h]
  _QWORD v41[3]; // [rsp+A8h] [rbp-A0h] BYREF
  _QWORD v42[3]; // [rsp+C0h] [rbp-88h] BYREF
  _QWORD v43[4]; // [rsp+D8h] [rbp-70h] BYREF
  __int128 v44; // [rsp+F8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  try
  {
    v39 = a3;
    v40 = a4;
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x425,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x80070057LL,
        v31);
    if ( !(unsigned __int8)_is_valid___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEBA_NXZ(a3) )
      wil::details::in1diag3::Throw_Hr(
        v7,
        (void *)0x426,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x80070057LL,
        v31);
    if ( !(unsigned __int8)_is_valid___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEBA_NXZ(a4) )
      wil::details::in1diag3::Throw_Hr(
        v8,
        (void *)0x427,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x80070057LL,
        v31);
    v10 = *((_QWORD *)this + 91);
    if ( !v10 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x429,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x8007139FLL,
        v31);
    v11 = *((_QWORD *)this + 100);
    if ( !v11 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42A,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x8007139FLL,
        v31);
    v12 = *((_QWORD *)this + 81);
    if ( !v12 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42B,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x8007139FLL,
        v31);
    v43[0] = *((_QWORD *)this + 91);
    v13 = (__int64 *)*a4;
    if ( *a4 )
      v14 = *v13;
    else
      v14 = 0;
    v43[1] = v14;
    v15 = (_QWORD *)*a3;
    if ( *a3 )
      v15 = (_QWORD *)*v15;
    v43[2] = v15;
    v43[3] = v11;
    v41[0] = v10;
    if ( v13 )
      v16 = *v13;
    else
      v16 = 0;
    v41[1] = v16;
    v41[2] = v12;
    v42[0] = v10;
    if ( v13 )
      v17 = *v13;
    else
      v17 = 0;
    v42[1] = v17;
    v42[2] = v9;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v44 = 0;
    VmMigrationSettings::VmMigrationSettings((VmMigrationSettings *)&v44, v16);
    while ( 1 )
    {
      v38 = 0;
      if ( v18 )
      {
        v36[0] = 3;
        v36[1] = v41;
        IsSet = (const char *)WaitUntilAnObjectIsSet(v36, 30000);
        if ( !IsSet )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x489,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x80004004LL,
            v31);
        if ( IsSet == (const char *)1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x48E,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x80004005LL,
            v31);
        if ( IsSet != (const char *)2 )
          wil::details::in1diag3::FailFast_UnexpectedMsg(
            retaddr,
            (void *)0x498,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            "indexOfSetObject: %zu.",
            IsSet);
        if ( !(unsigned int)VmMigrationTcpTransport::LookupNextUnusedBuffer(this, &v38) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x494,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            v26);
        v24 = v38;
      }
      else
      {
        MigrationMessageDefaultTimeout = VmMigrationSettings::GetMigrationMessageDefaultTimeout(v21);
        v35[0] = 4;
        v35[1] = v43;
        v23 = (const char *)WaitUntilAnObjectIsSet(v35, MigrationMessageDefaultTimeout);
        if ( !v23 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x45F,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x80004004LL,
            v31);
        if ( v23 == (const char *)1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x464,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x80004005LL,
            v31);
        if ( v23 == (const char *)2 )
        {
          v18 = 1;
          VmMigrationTcpTransport::UnreserveTransportBufferForDuplexReplies(this);
          v20 = 1;
          if ( v38 )
            (*(void (__fastcall **)(VmMigrationTcpTransport *))(*(_QWORD *)this + 448LL))(this);
          goto LABEL_55;
        }
        if ( v23 != (const char *)3 )
          wil::details::in1diag3::FailFast_UnexpectedMsg(
            retaddr,
            (void *)0x47C,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            "indexOfSetObject: %zu.",
            v23);
        v24 = VmMigrationTcpTransport::TakeReservedDuplexReplyBufferOwnership(this);
        v38 = v24;
      }
      do
      {
        if ( !v24 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4A5,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x8007054FLL,
            v31);
        v37[0] = 3;
        v37[1] = v42;
        v27 = (const char *)WaitUntilAnObjectIsSet(v37, 0xFFFFFFFFLL);
        if ( !v27 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4AF,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x80004004LL,
            v31);
        if ( v27 == (const char *)1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4B4,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x80004005LL,
            v31);
        if ( v27 != (const char *)2 )
          wil::details::in1diag3::FailFast_UnexpectedMsg(
            retaddr,
            (void *)0x4BE,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            "indexOfSetObject: %zu.",
            v27);
        v19 = VmMigrationTcpTransport::OfferReplyBuffer(this, &v38);
        v24 = v38;
      }
      while ( v38 && !v19 );
      if ( v38 )
      {
        (*(void (__fastcall **)(VmMigrationTcpTransport *))(*(_QWORD *)this + 448LL))(this);
        v38 = 0;
      }
LABEL_55:
      if ( v19 )
      {
        if ( !v20 )
          VmMigrationTcpTransport::UnreserveTransportBufferForDuplexReplies(this);
        v28 = VmMigrationTcpTransport::FlushPendingSends(this, 0x7530u);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4CE,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)(unsigned int)v28,
            v31);
        if ( v28 )
        {
          LODWORD(v33) = v28;
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0x4D4,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x8007054FLL,
            v28 != 294977,
            (bool)"flushPendingSendsResult: 0x%08X.",
            v33);
          LODWORD(v34) = *((_DWORD *)this + 139);
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0x4D8,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x8007054FLL,
            (int)v34 >= 0,
            (bool)"m_OverlappedSendResult: 0x%08X.",
            v34);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4DA,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)*((unsigned int *)this + 139),
            v32);
        }
        Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)((char *)&v44 + 8));
        std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(a3);
        std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(a4);
        return 0;
      }
    }
  }
  catch ( ... )
  {
    LODWORD(v38) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x4DF,
                     (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
                     v29);
    std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(v39);
    std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(v40);
    return (unsigned int)v38;
  }
  return result;
}

```

## disassembly

```asm
0x140095270  push    rbx
0x140095272  push    rsi
0x140095273  push    rdi
0x140095274  push    r12
0x140095276  push    r13
0x140095278  push    r14
0x14009527a  push    r15
0x14009527c  sub     rsp, 110h
0x140095283  mov     rax, cs:__security_cookie
0x14009528a  xor     rax, rsp
0x14009528d  mov     [rsp+148h+var_40], rax
0x140095295  mov     rsi, r9
0x140095298  mov     r14, r8
0x14009529b  mov     r11, rdx
0x14009529e  mov     rbx, rcx
0x1400952a1  mov     [rsp+148h+var_B0], r8
0x1400952a9  mov     [rsp+148h+var_A8], r9
0x1400952b1  mov     rcx, [rsp+148h]; this
0x1400952b9  test    rdx, rdx
0x1400952bc  jnz     short loc_1400952D5
0x1400952be  mov     r9d, 80070057h; char *
0x1400952c4  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400952cb  mov     edx, 425h; void *
0x1400952d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400952d5  mov     r10, [rsp+148h]
0x1400952dd  mov     rcx, r14
0x1400952e0  call    ?is_valid@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEBA_NXZ
0x1400952e5  test    al, al
0x1400952e7  jnz     short loc_140095303
0x1400952e9  mov     r9d, 80070057h; char *
0x1400952ef  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400952f6  mov     edx, 426h; void *
0x1400952fb  mov     rcx, r10; this
0x1400952fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140095303  mov     r10, [rsp+148h]
0x14009530b  mov     rcx, rsi
0x14009530e  call    ?is_valid@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEBA_NXZ
0x140095313  test    al, al
0x140095315  jnz     short loc_140095331
0x140095317  mov     r9d, 80070057h; char *
0x14009531d  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140095324  mov     edx, 427h; void *
0x140095329  mov     rcx, r10; this
0x14009532c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140095331  mov     rcx, [rbx+2D8h]
0x140095338  mov     rax, [rsp+148h]
0x140095340  test    rcx, rcx
0x140095343  jnz     short loc_14009535F
0x140095345  mov     r9d, 8007139Fh; char *
0x14009534b  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140095352  mov     edx, 429h; void *
0x140095357  mov     rcx, rax; this
0x14009535a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009535f  mov     r8, [rbx+320h]
0x140095366  test    r8, r8
0x140095369  setz    al
0x14009536c  mov     r10, [rsp+148h]
0x140095374  test    al, al
0x140095376  jz      short loc_140095392
0x140095378  mov     r9d, 8007139Fh; char *
0x14009537e  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140095385  mov     edx, 42Ah; void *
0x14009538a  mov     rcx, r10; this
0x14009538d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140095392  mov     r9, [rbx+288h]
0x140095399  mov     rax, [rsp+148h]
0x1400953a1  test    r9, r9
0x1400953a4  jnz     short loc_1400953C0
0x1400953a6  mov     r9d, 8007139Fh; char *
0x1400953ac  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400953b3  mov     edx, 42Bh; void *
0x1400953b8  mov     rcx, rax; this
0x1400953bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400953c0  mov     [rsp+148h+var_70], rcx
0x1400953c8  mov     rax, [rsi]
0x1400953cb  test    rax, rax
0x1400953ce  jz      short loc_1400953D5
0x1400953d0  mov     rdx, [rax]
0x1400953d3  jmp     short loc_1400953D7
0x1400953d5  xor     edx, edx
0x1400953d7  mov     [rsp+148h+var_68], rdx
0x1400953df  mov     rdx, [r14]
0x1400953e2  test    rdx, rdx
0x1400953e5  jz      short loc_1400953EA
0x1400953e7  mov     rdx, [rdx]
0x1400953ea  mov     [rsp+148h+var_60], rdx
0x1400953f2  mov     [rsp+148h+var_58], r8
0x1400953fa  mov     [rsp+148h+var_A0], rcx
0x140095402  test    rax, rax
0x140095405  jz      short loc_14009540C
0x140095407  mov     rdx, [rax]
0x14009540a  jmp     short loc_14009540E
0x14009540c  xor     edx, edx; bool
0x14009540e  mov     [rsp+148h+var_98], rdx
0x140095416  mov     [rsp+148h+var_90], r9
0x14009541e  mov     [rsp+148h+var_88], rcx
0x140095426  test    rax, rax
0x140095429  jz      short loc_140095430
0x14009542b  mov     rcx, [rax]
0x14009542e  jmp     short loc_140095432
0x140095430  xor     ecx, ecx
0x140095432  mov     [rsp+148h+var_80], rcx
0x14009543a  mov     [rsp+148h+var_78], r11
0x140095442  xor     r12b, r12b
0x140095445  xor     dil, dil
0x140095448  xor     r15b, r15b
0x14009544b  xorps   xmm0, xmm0
0x14009544e  movups  [rsp+148h+var_50], xmm0
0x140095456  lea     rcx, [rsp+148h+var_50]; this
0x14009545e  call    ??0VmMigrationSettings@@QEAA@_N@Z; VmMigrationSettings::VmMigrationSettings(bool)
0x140095463  nop
0x140095464  mov     [rsp+148h+var_B8], 0
0x140095470  xorps   xmm0, xmm0
0x140095473  xor     eax, eax
0x140095475  movups  [rsp+148h+var_108], xmm0
0x14009547a  mov     [rsp+148h+var_F8], rax
0x14009547f  mov     qword ptr [rsp+148h+var_108], rbx
0x140095484  lea     r13, [rsp+148h+var_B8]
0x14009548c  mov     qword ptr [rsp+148h+var_108+8], r13
0x140095491  mov     byte ptr [rsp+148h+var_F8], 1
0x140095496  test    r12b, r12b
0x140095499  jnz     loc_140095590
0x14009549f  call    ?GetMigrationMessageDefaultTimeout@VmMigrationSettings@@QEBAIXZ; VmMigrationSettings::GetMigrationMessageDefaultTimeout(void)
0x1400954a4  mov     [rsp+148h+var_E8], 4
0x1400954ad  lea     rcx, [rsp+148h+var_70]
0x1400954b5  mov     [rsp+148h+var_E0], rcx
0x1400954ba  mov     edx, eax
0x1400954bc  lea     rcx, [rsp+148h+var_E8]
0x1400954c1  call    WaitUntilAnObjectIsSet
0x1400954c6  mov     rcx, rax
0x1400954c9  test    rax, rax
0x1400954cc  jz      loc_140095571
0x1400954d2  sub     rcx, 1
0x1400954d6  jz      short loc_140095552
0x1400954d8  sub     rcx, 1
0x1400954dc  jz      short loc_14009551F
0x1400954de  cmp     rcx, 1
0x1400954e2  jz      short loc_14009550A
0x1400954e4  mov     rcx, [rsp+148h]; this
0x1400954ec  mov     [rsp+148h+var_128], rax; char *
0x1400954f1  lea     r9, aIndexofsetobje; "indexOfSetObject: %zu."
0x1400954f8  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400954ff  mov     edx, 47Ch; void *
0x140095504  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x14009550a  mov     rcx, rbx; this
0x14009550d  call    ?TakeReservedDuplexReplyBufferOwnership@VmMigrationTcpTransport@@IEAAPEAU_TRANSPORT_BUFFER@1@XZ; VmMigrationTcpTransport::TakeReservedDuplexReplyBufferOwnership(void)
0x140095512  mov     [rsp+148h+var_B8], rax
0x14009551a  jmp     loc_140095630
0x14009551f  mov     r12b, 1
0x140095522  mov     rcx, rbx; this
0x140095525  call    ?UnreserveTransportBufferForDuplexReplies@VmMigrationTcpTransport@@IEAAXXZ; VmMigrationTcpTransport::UnreserveTransportBufferForDuplexReplies(void)
0x14009552a  mov     r15b, r12b
0x14009552d  mov     rdx, [rsp+148h+var_B8]
0x140095535  test    rdx, rdx
0x140095538  jz      short loc_14009554D
0x14009553a  mov     rax, [rbx]
0x14009553d  mov     rcx, rbx
0x140095540  mov     rax, [rax+1C0h]
0x140095547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009554c  nop
0x14009554d  jmp     loc_140095713
0x140095552  mov     rcx, [rsp+148h]; this
0x14009555a  mov     r9d, 80004005h; char *
0x140095560  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140095567  mov     edx, 464h; void *
0x14009556c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140095571  mov     rcx, [rsp+148h]; this
0x140095579  mov     r9d, 80004004h; char *
0x14009557f  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140095586  mov     edx, 45Fh; void *
0x14009558b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140095590  mov     [rsp+148h+var_D8], 3
0x140095599  lea     rax, [rsp+148h+var_A0]
0x1400955a1  mov     [rsp+148h+var_D0], rax
0x1400955a6  mov     edx, 7530h
0x1400955ab  lea     rcx, [rsp+148h+var_D8]
0x1400955b0  call    WaitUntilAnObjectIsSet
0x1400955b5  mov     rcx, rax
0x1400955b8  test    rax, rax
0x1400955bb  jz      loc_140095881
0x1400955c1  sub     rcx, 1
0x1400955c5  jz      loc_140095862
0x1400955cb  cmp     rcx, 1
0x1400955cf  jz      short loc_1400955F7
0x1400955d1  mov     rcx, [rsp+148h]; this
0x1400955d9  mov     [rsp+148h+var_128], rax; char *
0x1400955de  lea     r9, aIndexofsetobje; "indexOfSetObject: %zu."
0x1400955e5  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400955ec  mov     edx, 498h; void *
0x1400955f1  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x1400955f7  mov     rdi, [rsp+148h]
0x1400955ff  lea     rdx, [rsp+148h+var_B8]; struct VmMigrationTcpTransport::_TRANSPORT_BUFFER **
0x140095607  mov     rcx, rbx; this
0x14009560a  call    ?LookupNextUnusedBuffer@VmMigrationTcpTransport@@IEAAHPEAPEAU_TRANSPORT_BUFFER@1@@Z; VmMigrationTcpTransport::LookupNextUnusedBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER * *)
0x14009560f  test    eax, eax
0x140095611  jnz     short loc_140095628
0x140095613  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14009561a  mov     edx, 494h; void *
0x14009561f  mov     rcx, rdi; this
0x140095622  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140095628  mov     rax, [rsp+148h+var_B8]
0x140095630  test    rax, rax
0x140095633  setz    al
0x140095636  mov     rcx, [rsp+148h]; this
0x14009563e  test    al, al
0x140095640  jz      short loc_140095659
0x140095642  mov     r9d, 8007054Fh; char *
0x140095648  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14009564f  mov     edx, 4A5h; void *
0x140095654  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140095659  mov     [rsp+148h+var_C8], 3
0x140095665  lea     rax, [rsp+148h+var_88]
0x14009566d  mov     [rsp+148h+var_C0], rax
0x140095675  or      edx, 0FFFFFFFFh
0x140095678  lea     rcx, [rsp+148h+var_C8]
0x140095680  call    WaitUntilAnObjectIsSet
0x140095685  mov     rcx, rax
0x140095688  test    rax, rax
0x14009568b  jz      loc_140095843
0x140095691  sub     rcx, 1
0x140095695  jz      loc_140095824
0x14009569b  cmp     rcx, 1
0x14009569f  jz      short loc_1400956C7
0x1400956a1  mov     rcx, [rsp+148h]; this
0x1400956a9  mov     [rsp+148h+var_128], rax; char *
0x1400956ae  lea     r9, aIndexofsetobje; "indexOfSetObject: %zu."
0x1400956b5  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400956bc  mov     edx, 4BEh; void *
0x1400956c1  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x1400956c7  lea     rdx, [rsp+148h+var_B8]; struct VmMigrationTcpTransport::_TRANSPORT_BUFFER **
0x1400956cf  mov     rcx, rbx; this
0x1400956d2  call    ?OfferReplyBuffer@VmMigrationTcpTransport@@IEAA_NPEAPEAU_TRANSPORT_BUFFER@1@@Z; VmMigrationTcpTransport::OfferReplyBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER * *)
0x1400956d7  mov     dil, al
0x1400956da  mov     rax, [rsp+148h+var_B8]
0x1400956e2  test    rax, rax
0x1400956e5  jz      short loc_1400956F0
0x1400956e7  test    dil, dil
0x1400956ea  jz      loc_140095630
0x1400956f0  mov     rdx, [r13+0]
0x1400956f4  test    rdx, rdx
0x1400956f7  jz      short loc_140095713
0x1400956f9  mov     rax, [rbx]
0x1400956fc  mov     rcx, rbx
0x1400956ff  mov     rax, [rax+1C0h]
0x140095706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009570b  mov     qword ptr [r13+0], 0
0x140095713  test    dil, dil
0x140095716  jz      loc_140095464
0x14009571c  test    r15b, r15b
0x14009571f  jnz     short loc_140095729
0x140095721  mov     rcx, rbx; this
0x140095724  call    ?UnreserveTransportBufferForDuplexReplies@VmMigrationTcpTransport@@IEAAXXZ; VmMigrationTcpTransport::UnreserveTransportBufferForDuplexReplies(void)
0x140095729  mov     edx, 7530h; unsigned int
0x14009572e  mov     rcx, rbx; this
0x140095731  call    ?FlushPendingSends@VmMigrationTcpTransport@@IEAAJK@Z; VmMigrationTcpTransport::FlushPendingSends(ulong)
0x140095736  mov     edx, eax
0x140095738  mov     rcx, [rsp+148h]; this
0x140095740  test    eax, eax
0x140095742  jns     short loc_140095758
0x140095744  mov     r9d, eax; char *
0x140095747  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14009574e  mov     edx, 4CEh; void *
0x140095753  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140095758  test    edx, edx
0x14009575a  jz      loc_1400957FE
0x140095760  cmp     edx, 48041h
0x140095766  setnz   al
0x140095769  mov     rcx, [rsp+148h]; this
0x140095771  mov     dword ptr [rsp+148h+var_118], edx; char *
0x140095775  lea     rdx, aFlushpendingse; "flushPendingSendsResult: 0x%08X."
0x14009577c  mov     qword ptr [rsp+148h+var_120], rdx; bool
0x140095781  mov     byte ptr [rsp+148h+var_128], al; char
0x140095785  mov     r9d, 8007054Fh; char *
0x14009578b  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140095792  mov     edx, 4D4h; void *
0x140095797  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14009579c  mov     eax, [rbx+22Ch]
0x1400957a2  mov     edx, eax
0x1400957a4  shr     edx, 1Fh
0x1400957a7  xor     dl, 1
0x1400957aa  mov     rcx, [rsp+148h]; this
0x1400957b2  mov     dword ptr [rsp+148h+var_118], eax; char *
0x1400957b6  lea     rax, aMOverlappedsen; "m_OverlappedSendResult: 0x%08X."
0x1400957bd  mov     qword ptr [rsp+148h+var_120], rax; bool
0x1400957c2  mov     byte ptr [rsp+148h+var_128], dl; int
0x1400957c6  mov     r9d, 8007054Fh; char *
0x1400957cc  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400957d3  mov     edx, 4D8h; void *
0x1400957d8  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1400957dd  mov     rcx, [rsp+148h]; this
0x1400957e5  mov     r9d, [rbx+22Ch]; char *
0x1400957ec  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400957f3  mov     edx, 4DAh; void *
0x1400957f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400957fe  lea     rcx, [rsp+148h+var_50+8]; this
0x140095806  call    ?Close@VmRegistryKey@Vml@@QEAAXXZ; Vml::VmRegistryKey::Close(void)
0x14009580b  nop
0x14009580c  mov     rcx, r14; void *
0x14009580f  call    ??1?$shared_ptr@VIMigrationTransferTransportAdapterSource@@@std@@QEAA@XZ; std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(void)
0x140095814  nop
  ... truncated ...
```
