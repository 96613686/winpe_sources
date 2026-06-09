# Kerb3961::CipherPolicyImpl::SelectChecksum(Kerb3961::KeyUsage,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)

- ea: `0x18000d960`
- end: `0x18000db87`
- name: `?SelectChecksum@CipherPolicyImpl@Kerb3961@@UEBA?AU?$ReturnType@U?$ResultAdapter@PEAUChecksumAlgorithm@Kerb3961@@@Kerb3961@@$1??$SingleGetter@U?$ResultAdapter@PEAUChecksumAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@U?$ResultAdapter@PEAUChecksumAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEAU32@AEAU12@@Z@2@W4KeyUsage@2@AEBUCipherPartnerHandle@2@1@Z`
- size: `551`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callees

- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x180003610`
- `0x180003da0`
- `0x18000aa04`
- `0x18000b024`
- `0x18000bfc8`
- `0x18000d960`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000db03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000db25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000db03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000db25`

## string_xrefs

- `0x18000db7a`: `Non test code is attempting to bypass policy`

## pseudocode

```c
__int64 __fastcall Kerb3961::CipherPolicyImpl::SelectChecksum(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v8; // r9
  const char *v9; // rdx
  RTL_SRWLOCK *v10; // rcx
  int v11; // r12d
  char v12; // r13
  _QWORD *i; // rbx
  __int64 v14; // r14
  const char *v15; // rdx
  unsigned __int64 v16; // rcx
  _QWORD *v17; // rax
  unsigned __int64 v18; // rax
  bool v19; // zf
  int v20; // r8d
  char v22; // [rsp+30h] [rbp-40h] BYREF
  int v23; // [rsp+40h] [rbp-30h] BYREF
  char v24; // [rsp+44h] [rbp-2Ch]
  int v25; // [rsp+50h] [rbp-20h] BYREF
  char v26; // [rsp+54h] [rbp-1Ch]
  char v27; // [rsp+55h] [rbp-1Bh]
  PSRWLOCK SRWLock[2]; // [rsp+60h] [rbp-10h] BYREF
  char v29; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v30; // [rsp+C8h] [rbp+58h]

  v30 = a4;
  if ( a3 == 0x8000000000000000uLL )
  {
    if ( !Kerb3961::g_allowPolicyBypass )
      Kerb3961::ConsistencyFail(
        (Kerb3961 *)L"Non test code is attempting to bypass policy",
        (const unsigned __int16 *)a2);
  }
  else if ( a3 == 0x8000000000000001uLL )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"keyUsage != KeyUsage::AlwaysBlocked",
      (const char *)a2);
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"CheckKeyUsage(keyUsage)",
      (const char *)0xC00002FDLL,
      v20);
    *(_QWORD *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -1073741059;
    return a2;
  }
  Kerb3961::CipherPolicyImpl::EnsureInitialization(a1, &v29, a3);
  LOBYTE(v8) = 8;
  Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(a1, &v25, a3, v8);
  if ( v27 )
  {
    v11 = v25;
    v12 = v26;
    wil::srwlock::lock_shared(a1 + 16, SRWLock);
    for ( i = *(_QWORD **)(a1 + 72); i != (_QWORD *)(a1 + 56); i = (_QWORD *)v16 )
    {
      v14 = i[4];
      v23 = v11;
      v24 = v12;
      if ( (*(unsigned __int8 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v14 + 56LL))(
             v14,
             &v23,
             Kerb3961::g_supportedEncryptionTypes) )
      {
        v25 = v11;
        v26 = v12;
        if ( *(int *)Kerb3961::CipherPolicyImpl::ChecksumEnabledForPartners(
                       a1,
                       (unsigned int)&v22,
                       v14,
                       (unsigned int)&v25,
                       v30,
                       a5) >= 0 )
        {
          v10 = SRWLock[0];
          *(_QWORD *)a2 = v14;
          *(_DWORD *)(a2 + 8) = 0;
          if ( v10 )
            ReleaseSRWLockShared(v10);
          v19 = v29 == 0;
          goto LABEL_30;
        }
      }
      else
      {
        Kerb3961::Logging::Verify::ConditionFailed(
          (Kerb3961::Logging::Verify *)"checksum->ChecksumEnabledForUsage(keyScenario, g_supportedEncryptionTypes)",
          v15);
      }
      v16 = i[2];
      if ( (void **)v16 == &utl::_TreeSentinel )
      {
        v17 = (_QWORD *)(*i & 0xFFFFFFFFFFFFFFFEuLL);
        v16 = (unsigned __int64)v17;
        if ( (_QWORD *)v17[2] == i && (_QWORD *)*v17 != i )
        {
          v16 = *v17 & 0xFFFFFFFFFFFFFFFEuLL;
          if ( *(_QWORD **)(v16 + 16) == v17 && *(_QWORD **)v16 != v17 )
          {
            do
            {
              v18 = v16;
              v16 = *(_QWORD *)v16 & 0xFFFFFFFFFFFFFFFEuLL;
            }
            while ( *(_QWORD *)(v16 + 16) == v18 );
          }
        }
      }
      else
      {
        if ( i == (_QWORD *)v16 )
          __int2c();
        for ( ; *(void ***)(v16 + 8) != &utl::_TreeSentinel; v16 = *(_QWORD *)(v16 + 8) )
          ;
      }
    }
    v10 = SRWLock[0];
    *(_QWORD *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -1073741059;
    if ( v10 )
      ReleaseSRWLockShared(v10);
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"scenarioOpt.has_value()", v9);
    *(_QWORD *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -1073741811;
  }
  v19 = v29 == 0;
LABEL_30:
  if ( !v19 )
    Kerb3961::UninitializeCiphers((Kerb3961 *)v10);
  return a2;
}

```

## disassembly

```asm
0x18000d960  mov     [rsp-38h+arg_0], rbx
0x18000d965  mov     [rsp-38h+arg_18], r9
0x18000d96a  push    rbp
0x18000d96b  push    rsi
0x18000d96c  push    rdi
0x18000d96d  push    r12
0x18000d96f  push    r13
0x18000d971  push    r14
0x18000d973  push    r15
0x18000d975  mov     rbp, rsp
0x18000d978  sub     rsp, 70h
0x18000d97c  mov     rax, 8000000000000000h
0x18000d986  xor     r14d, r14d
0x18000d989  mov     rbx, r8
0x18000d98c  mov     rdi, rdx
0x18000d98f  mov     rsi, rcx
0x18000d992  cmp     r8, rax
0x18000d995  jnz     short loc_18000D9A6
0x18000d997  cmp     cs:?g_allowPolicyBypass@Kerb3961@@3_NA, r14b; bool Kerb3961::g_allowPolicyBypass
0x18000d99e  jz      loc_18000DB7A
0x18000d9a4  jmp     short loc_18000D9B9
0x18000d9a6  mov     rax, 8000000000000001h
0x18000d9b0  cmp     rbx, rax
0x18000d9b3  jz      loc_18000DB38
0x18000d9b9  lea     rdx, [rbp+arg_10]
0x18000d9bd  call    ?EnsureInitialization@CipherPolicyImpl@Kerb3961@@QEBA?AUInitializationSentinel@12@W4KeyUsage@2@@Z; Kerb3961::CipherPolicyImpl::EnsureInitialization(Kerb3961::KeyUsage)
0x18000d9c2  mov     r9b, 8
0x18000d9c5  lea     rdx, [rbp+var_20]
0x18000d9c9  mov     r8, rbx
0x18000d9cc  mov     rcx, rsi
0x18000d9cf  call    ?GetOurPolicyScenarioForKeyUsage@CipherPolicyImpl@Kerb3961@@QEBA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@2@W4KeyPolicyQualifiers@2@@Z; Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(Kerb3961::KeyUsage,Kerb3961::KeyPolicyQualifiers)
0x18000d9d4  cmp     [rbp+var_1B], r14b
0x18000d9d8  jnz     short loc_18000D9F5
0x18000d9da  lea     rcx, aScenariooptHas; "scenarioOpt.has_value()"
0x18000d9e1  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d9e6  mov     [rdi], r14
0x18000d9e9  mov     dword ptr [rdi+8], 0C000000Dh
0x18000d9f0  jmp     loc_18000DB2B
0x18000d9f5  mov     r12d, [rbp+var_20]
0x18000d9f9  lea     rcx, [rsi+10h]
0x18000d9fd  mov     r13b, [rbp+var_1C]
0x18000da01  lea     rdx, [rbp+SRWLock]
0x18000da05  call    ?lock_shared@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_shared(void)
0x18000da0a  lea     r15, [rsi+38h]
0x18000da0e  mov     rbx, [r15+10h]
0x18000da12  cmp     rbx, r15
0x18000da15  jz      loc_18000DB0F
0x18000da1b  mov     r14, [rbx+20h]
0x18000da1f  lea     rdx, [rbp+var_30]
0x18000da23  mov     r8d, cs:?g_supportedEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A; Kerb3961::EncryptionTypeBitmask Kerb3961::g_supportedEncryptionTypes
0x18000da2a  mov     rcx, r14
0x18000da2d  mov     [rbp+var_30], r12d
0x18000da31  mov     [rbp+var_2C], r13b
0x18000da35  mov     rax, [r14]
0x18000da38  mov     rax, [rax+38h]
0x18000da3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da41  test    al, al
0x18000da43  jnz     short loc_18000DA53
0x18000da45  lea     rcx, aChecksumChecks_0; "checksum->ChecksumEnabledForUsage(keySc"...
0x18000da4c  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000da51  jmp     short loc_18000DA85
0x18000da53  mov     rax, [rbp+arg_20]
0x18000da57  lea     r9, [rbp+var_20]
0x18000da5b  mov     [rsp+70h+var_48], rax
0x18000da60  lea     rdx, [rbp+var_40]
0x18000da64  mov     rax, [rbp+arg_18]
0x18000da68  mov     r8, r14
0x18000da6b  mov     rcx, rsi
0x18000da6e  mov     [rsp+70h+var_50], rax
0x18000da73  mov     [rbp+var_20], r12d
0x18000da77  mov     [rbp+var_1C], r13b
0x18000da7b  call    ?ChecksumEnabledForPartners@CipherPolicyImpl@Kerb3961@@QEBA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@PEAUChecksumAlgorithm@2@UKeyPolicyScenario@2@AEBUCipherPartnerHandle@2@2@Z; Kerb3961::CipherPolicyImpl::ChecksumEnabledForPartners(Kerb3961::ChecksumAlgorithm *,Kerb3961::KeyPolicyScenario,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)
0x18000da80  cmp     dword ptr [rax], 0
0x18000da83  jge     short loc_18000DAF0
0x18000da85  mov     rcx, [rbx+10h]
0x18000da89  lea     rdx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000da90  cmp     rcx, rdx
0x18000da93  jz      short loc_18000DAB1
0x18000da95  cmp     rbx, rcx
0x18000da98  jnz     short loc_18000DA9C
0x18000da9a  int     2Ch; Windows NT - assertion failure
0x18000da9c  cmp     [rcx+8], rdx
0x18000daa0  jz      short loc_18000DAE8
0x18000daa2  mov     rax, [rcx+8]
0x18000daa6  mov     rcx, rax
0x18000daa9  cmp     [rax+8], rdx
0x18000daad  jnz     short loc_18000DAA2
0x18000daaf  jmp     short loc_18000DAE8
0x18000dab1  mov     rax, [rbx]
0x18000dab4  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000dab8  mov     rcx, rax
0x18000dabb  cmp     [rax+10h], rbx
0x18000dabf  jnz     short loc_18000DAE8
0x18000dac1  cmp     [rax], rbx
0x18000dac4  jz      short loc_18000DAE8
0x18000dac6  mov     rcx, [rax]
0x18000dac9  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000dacd  cmp     [rcx+10h], rax
0x18000dad1  jnz     short loc_18000DAE8
0x18000dad3  cmp     [rcx], rax
0x18000dad6  jz      short loc_18000DAE8
0x18000dad8  mov     rax, rcx
0x18000dadb  mov     rcx, [rcx]
0x18000dade  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000dae2  cmp     [rcx+10h], rax
0x18000dae6  jz      short loc_18000DAD8
0x18000dae8  mov     rbx, rcx
0x18000daeb  jmp     loc_18000DA12
0x18000daf0  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000daf4  mov     [rdi], r14
0x18000daf7  mov     dword ptr [rdi+8], 0
0x18000dafe  test    rcx, rcx
0x18000db01  jz      short loc_18000DB09
0x18000db03  call    cs:__imp_ReleaseSRWLockShared
0x18000db09  cmp     [rbp+arg_10], 0
0x18000db0d  jmp     short loc_18000DB2F
0x18000db0f  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000db13  xor     r14d, r14d
0x18000db16  mov     [rdi], r14
0x18000db19  mov     dword ptr [rdi+8], 0C00002FDh
0x18000db20  test    rcx, rcx
0x18000db23  jz      short loc_18000DB2B
0x18000db25  call    cs:__imp_ReleaseSRWLockShared
0x18000db2b  cmp     [rbp+arg_10], r14b
0x18000db2f  jz      short loc_18000DB5F
0x18000db31  call    ?UninitializeCiphers@Kerb3961@@YAXXZ; Kerb3961::UninitializeCiphers(void)
0x18000db36  jmp     short loc_18000DB5F
0x18000db38  lea     rcx, aKeyusageKeyusa; "keyUsage != KeyUsage::AlwaysBlocked"
0x18000db3f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000db44  mov     edx, 0C00002FDh; char *
0x18000db49  lea     rcx, aCheckkeyusageK; "CheckKeyUsage(keyUsage)"
0x18000db50  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000db55  mov     [rdi], r14
0x18000db58  mov     dword ptr [rdi+8], 0C00002FDh
0x18000db5f  mov     rbx, [rsp+70h+arg_0]
0x18000db67  mov     rax, rdi
0x18000db6a  add     rsp, 70h
0x18000db6e  pop     r15
0x18000db70  pop     r14
0x18000db72  pop     r13
0x18000db74  pop     r12
0x18000db76  pop     rdi
0x18000db77  pop     rsi
0x18000db78  pop     rbp
0x18000db79  retn
0x18000db7a  lea     rcx, aNonTestCodeIsA; "Non test code is attempting to bypass p"...
0x18000db81  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
