# Kerb3961::CipherPolicyImpl::OpenChecksumById(uint,Kerb3961::KeyUsage,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)

- ea: `0x18000cdb0`
- end: `0x18000cfc6`
- name: `?OpenChecksumById@CipherPolicyImpl@Kerb3961@@UEBA?AU?$ReturnType@U?$ResultAdapter@PEAUChecksumAlgorithm@Kerb3961@@@Kerb3961@@$1??$SingleGetter@U?$ResultAdapter@PEAUChecksumAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@U?$ResultAdapter@PEAUChecksumAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEAU32@AEAU12@@Z@2@IW4KeyUsage@2@AEBUCipherPartnerHandle@2@1@Z`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b360`

## callees

- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x180003610`
- `0x180003da0`
- `0x18000aa04`
- `0x18000b024`
- `0x18000bfc8`
- `0x18000cdb0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cf12`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cf12`

## string_xrefs

- `0x18000cfb9`: `Non test code is attempting to bypass policy`

## pseudocode

```c
__int64 __fastcall Kerb3961::CipherPolicyImpl::OpenChecksumById(
        Kerb3961::CipherPolicyImpl *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  void **v10; // rax
  void **v11; // rcx
  __int64 v12; // rdx
  void *v13; // rsi
  const char *v14; // rdx
  char v15; // r15
  int v16; // edi
  unsigned __int8 (__fastcall *v17)(void *, int *, _QWORD); // rax
  const char *v18; // rdx
  int v19; // r8d
  Kerb3961 *v20; // rcx
  int v21; // edi
  int v22; // r8d
  int v23; // r8d
  int v25; // [rsp+30h] [rbp-30h] BYREF
  char v26; // [rsp+34h] [rbp-2Ch]
  int v27; // [rsp+40h] [rbp-20h] BYREF
  char v28; // [rsp+44h] [rbp-1Ch]
  char v29; // [rsp+45h] [rbp-1Bh]
  PSRWLOCK SRWLock[2]; // [rsp+50h] [rbp-10h] BYREF
  char v31; // [rsp+A8h] [rbp+48h] BYREF

  if ( a4 == 0x8000000000000000uLL )
  {
    if ( !Kerb3961::g_allowPolicyBypass )
      Kerb3961::ConsistencyFail(
        (Kerb3961 *)L"Non test code is attempting to bypass policy",
        (const unsigned __int16 *)a2);
  }
  else if ( a4 == 0x8000000000000001uLL )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"keyUsage != KeyUsage::AlwaysBlocked",
      (const char *)a2);
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"CheckKeyUsage(keyUsage)",
      (const char *)0xC00002FDLL,
      v23);
    *(_QWORD *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -1073741059;
    return a2;
  }
  Kerb3961::CipherPolicyImpl::EnsureInitialization(a1, &v31, a4);
  wil::srwlock::lock_shared(&Kerb3961::g_cipherLock, SRWLock);
  if ( (void **)qword_180029068 == &Kerb3961::g_checksums )
    goto LABEL_18;
  v10 = (void **)Kerb3961::g_checksums;
  v11 = &Kerb3961::g_checksums;
  do
  {
    if ( *((_DWORD *)v10 + 6) >= a3 )
    {
      v11 = v10;
      v12 = 1;
    }
    else
    {
      v12 = 2;
    }
    v10 = (void **)v10[v12];
  }
  while ( v10 != &utl::_TreeSentinel );
  if ( v11 == &Kerb3961::g_checksums || a3 < *((_DWORD *)v11 + 6) )
    goto LABEL_18;
  v13 = v11[4];
  if ( a4 == 0x8000000000000000uLL )
    goto LABEL_25;
  Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(a1, &v27, a4, 0);
  if ( v29 )
  {
    v15 = v28;
    v16 = v27;
    v17 = *(unsigned __int8 (__fastcall **)(void *, int *, _QWORD))(*(_QWORD *)v13 + 56LL);
    v25 = v27;
    v26 = v28;
    if ( !v17(v13, &v25, Kerb3961::g_supportedEncryptionTypes) )
    {
      Kerb3961::Logging::Verify::ConditionFailed(
        (Kerb3961::Logging::Verify *)"checksum->ChecksumEnabledForUsage(keyScenario, g_supportedEncryptionTypes)",
        v18);
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"ChecksumEnabledForUs(checksum, keyScenario)",
        (const char *)0xC00002FDLL,
        v19);
LABEL_18:
      *(_QWORD *)a2 = 0;
      *(_DWORD *)(a2 + 8) = -1073741059;
      goto LABEL_19;
    }
    v27 = v16;
    v28 = v15;
    v21 = *(_DWORD *)Kerb3961::CipherPolicyImpl::ChecksumEnabledForPartners(
                       (_DWORD)a1,
                       (unsigned int)&v25,
                       (_DWORD)v13,
                       (unsigned int)&v27,
                       a5,
                       a6);
    if ( v21 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"ChecksumEnabledForPartners(checksum, keyScenario, partner1, partner2)",
        (const char *)(unsigned int)v21,
        v22);
      *(_QWORD *)a2 = 0;
      *(_DWORD *)(a2 + 8) = v21;
      goto LABEL_19;
    }
LABEL_25:
    *(_QWORD *)a2 = v13;
    *(_DWORD *)(a2 + 8) = 0;
    goto LABEL_19;
  }
  Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"scenarioOpt.has_value()", v14);
  *(_QWORD *)a2 = 0;
  *(_DWORD *)(a2 + 8) = -1073741811;
LABEL_19:
  v20 = (Kerb3961 *)SRWLock[0];
  if ( SRWLock[0] )
    ReleaseSRWLockShared(SRWLock[0]);
  if ( v31 )
    Kerb3961::UninitializeCiphers(v20);
  return a2;
}

```

## disassembly

```asm
0x18000cdb0  mov     [rsp-28h+arg_0], rbx
0x18000cdb5  mov     [rsp-28h+arg_8], rsi
0x18000cdba  push    rbp
0x18000cdbb  push    rdi
0x18000cdbc  push    r12
0x18000cdbe  push    r14
0x18000cdc0  push    r15
0x18000cdc2  mov     rbp, rsp
0x18000cdc5  sub     rsp, 60h
0x18000cdc9  mov     r15, 8000000000000000h
0x18000cdd3  xor     r12d, r12d
0x18000cdd6  mov     rdi, r9
0x18000cdd9  mov     esi, r8d
0x18000cddc  mov     rbx, rdx
0x18000cddf  mov     r14, rcx
0x18000cde2  cmp     r9, r15
0x18000cde5  jnz     short loc_18000CDF6
0x18000cde7  cmp     cs:?g_allowPolicyBypass@Kerb3961@@3_NA, r12b; bool Kerb3961::g_allowPolicyBypass
0x18000cdee  jz      loc_18000CFB9
0x18000cdf4  jmp     short loc_18000CE09
0x18000cdf6  mov     rax, 8000000000000001h
0x18000ce00  cmp     rdi, rax
0x18000ce03  jz      loc_18000CF76
0x18000ce09  mov     r8, rdi
0x18000ce0c  lea     rdx, [rbp+arg_18]
0x18000ce10  call    ?EnsureInitialization@CipherPolicyImpl@Kerb3961@@QEBA?AUInitializationSentinel@12@W4KeyUsage@2@@Z; Kerb3961::CipherPolicyImpl::EnsureInitialization(Kerb3961::KeyUsage)
0x18000ce15  lea     rdx, [rbp+SRWLock]
0x18000ce19  lea     rcx, ?g_cipherLock@Kerb3961@@3UCommonLock@1@A; Kerb3961::CommonLock Kerb3961::g_cipherLock
0x18000ce20  call    ?lock_shared@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_shared(void)
0x18000ce25  lea     r8, ?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x18000ce2c  cmp     cs:qword_180029068, r8
0x18000ce33  jz      loc_18000CEFF
0x18000ce39  mov     rax, cs:?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x18000ce40  mov     rcx, r8
0x18000ce43  cmp     [rax+18h], esi
0x18000ce46  jnb     short loc_18000CE4F
0x18000ce48  mov     edx, 10h
0x18000ce4d  jmp     short loc_18000CE57
0x18000ce4f  mov     rcx, rax
0x18000ce52  mov     edx, 8
0x18000ce57  mov     rax, [rdx+rax]
0x18000ce5b  lea     rdx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000ce62  cmp     rax, rdx
0x18000ce65  jnz     short loc_18000CE43
0x18000ce67  cmp     rcx, r8
0x18000ce6a  jz      loc_18000CEFF
0x18000ce70  cmp     esi, [rcx+18h]
0x18000ce73  jb      loc_18000CEFF
0x18000ce79  mov     rsi, [rcx+20h]
0x18000ce7d  cmp     rdi, r15
0x18000ce80  jz      loc_18000CF6D
0x18000ce86  xor     r9d, r9d
0x18000ce89  lea     rdx, [rbp+var_20]
0x18000ce8d  mov     r8, rdi
0x18000ce90  mov     rcx, r14
0x18000ce93  call    ?GetOurPolicyScenarioForKeyUsage@CipherPolicyImpl@Kerb3961@@QEBA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@2@W4KeyPolicyQualifiers@2@@Z; Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(Kerb3961::KeyUsage,Kerb3961::KeyPolicyQualifiers)
0x18000ce98  cmp     [rbp+var_1B], r12b
0x18000ce9c  jnz     short loc_18000CEB6
0x18000ce9e  lea     rcx, aScenariooptHas; "scenarioOpt.has_value()"
0x18000cea5  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000ceaa  mov     [rbx], r12
0x18000cead  mov     dword ptr [rbx+8], 0C000000Dh
0x18000ceb4  jmp     short loc_18000CF09
0x18000ceb6  mov     rax, [rsi]
0x18000ceb9  lea     rdx, [rbp+var_30]
0x18000cebd  mov     r15b, [rbp+var_1C]
0x18000cec1  mov     rcx, rsi
0x18000cec4  mov     edi, [rbp+var_20]
0x18000cec7  mov     r8d, cs:?g_supportedEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A; Kerb3961::EncryptionTypeBitmask Kerb3961::g_supportedEncryptionTypes
0x18000cece  mov     rax, [rax+38h]
0x18000ced2  mov     [rbp+var_30], edi
0x18000ced5  mov     [rbp+var_2C], r15b
0x18000ced9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cede  test    al, al
0x18000cee0  jnz     short loc_18000CF25
0x18000cee2  lea     rcx, aChecksumChecks_0; "checksum->ChecksumEnabledForUsage(keySc"...
0x18000cee9  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000ceee  mov     edx, 0C00002FDh; char *
0x18000cef3  lea     rcx, aChecksumenable_3; "ChecksumEnabledForUs(checksum, keyScena"...
0x18000cefa  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000ceff  mov     [rbx], r12
0x18000cf02  mov     dword ptr [rbx+8], 0C00002FDh
0x18000cf09  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000cf0d  test    rcx, rcx
0x18000cf10  jz      short loc_18000CF18
0x18000cf12  call    cs:__imp_ReleaseSRWLockShared
0x18000cf18  cmp     [rbp+arg_18], r12b
0x18000cf1c  jz      short loc_18000CF9D
0x18000cf1e  call    ?UninitializeCiphers@Kerb3961@@YAXXZ; Kerb3961::UninitializeCiphers(void)
0x18000cf23  jmp     short loc_18000CF9D
0x18000cf25  mov     rax, [rbp+arg_28]
0x18000cf29  lea     r9, [rbp+var_20]
0x18000cf2d  mov     [rsp+60h+var_38], rax
0x18000cf32  lea     rdx, [rbp+var_30]
0x18000cf36  mov     rax, [rbp+arg_20]
0x18000cf3a  mov     r8, rsi
0x18000cf3d  mov     rcx, r14
0x18000cf40  mov     [rsp+60h+var_40], rax
0x18000cf45  mov     [rbp+var_20], edi
0x18000cf48  mov     [rbp+var_1C], r15b
0x18000cf4c  call    ?ChecksumEnabledForPartners@CipherPolicyImpl@Kerb3961@@QEBA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@PEAUChecksumAlgorithm@2@UKeyPolicyScenario@2@AEBUCipherPartnerHandle@2@2@Z; Kerb3961::CipherPolicyImpl::ChecksumEnabledForPartners(Kerb3961::ChecksumAlgorithm *,Kerb3961::KeyPolicyScenario,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)
0x18000cf51  mov     edi, [rax]
0x18000cf53  test    edi, edi
0x18000cf55  jns     short loc_18000CF6D
0x18000cf57  mov     edx, edi; char *
0x18000cf59  lea     rcx, aChecksumenable_2; "ChecksumEnabledForPartners(checksum, ke"...
0x18000cf60  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000cf65  mov     [rbx], r12
0x18000cf68  mov     [rbx+8], edi
0x18000cf6b  jmp     short loc_18000CF09
0x18000cf6d  mov     [rbx], rsi
0x18000cf70  mov     [rbx+8], r12d
0x18000cf74  jmp     short loc_18000CF09
0x18000cf76  lea     rcx, aKeyusageKeyusa; "keyUsage != KeyUsage::AlwaysBlocked"
0x18000cf7d  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000cf82  mov     edx, 0C00002FDh; char *
0x18000cf87  lea     rcx, aCheckkeyusageK; "CheckKeyUsage(keyUsage)"
0x18000cf8e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000cf93  mov     [rbx], r12
0x18000cf96  mov     dword ptr [rbx+8], 0C00002FDh
0x18000cf9d  lea     r11, [rsp+60h+var_s0]
0x18000cfa2  mov     rax, rbx
0x18000cfa5  mov     rbx, [r11+30h]
0x18000cfa9  mov     rsi, [r11+38h]
0x18000cfad  mov     rsp, r11
0x18000cfb0  pop     r15
0x18000cfb2  pop     r14
0x18000cfb4  pop     r12
0x18000cfb6  pop     rdi
0x18000cfb7  pop     rbp
0x18000cfb8  retn
0x18000cfb9  lea     rcx, aNonTestCodeIsA; "Non test code is attempting to bypass p"...
0x18000cfc0  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
