# Kerb3961::CipherPolicyImpl::OpenEncryptionById(uint,Kerb3961::KeyUsage,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)

- ea: `0x18000cfd0`
- end: `0x18000d1e6`
- name: `?OpenEncryptionById@CipherPolicyImpl@Kerb3961@@UEBA?AU?$ReturnType@U?$ResultAdapter@PEAUEncryptionAlgorithm@Kerb3961@@@Kerb3961@@$1??$SingleGetter@U?$ResultAdapter@PEAUEncryptionAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@U?$ResultAdapter@PEAUEncryptionAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEAU32@AEAU12@@Z@2@IW4KeyUsage@2@AEBUCipherPartnerHandle@2@1@Z`
- size: `534`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18000bf60`
- `0x18000c1c0`

## callees

- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x180003610`
- `0x180003da0`
- `0x18000ae18`
- `0x18000b024`
- `0x18000bfc8`
- `0x18000cfd0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d132`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d132`

## string_xrefs

- `0x18000d1d9`: `Non test code is attempting to bypass policy`

## pseudocode

```c
__int64 __fastcall Kerb3961::CipherPolicyImpl::OpenEncryptionById(
        __int64 a1,
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
  if ( (void **)qword_180029048 == &Kerb3961::g_encryptions )
    goto LABEL_18;
  v10 = (void **)Kerb3961::g_encryptions;
  v11 = &Kerb3961::g_encryptions;
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
  if ( v11 == &Kerb3961::g_encryptions || a3 < *((_DWORD *)v11 + 6) )
    goto LABEL_18;
  v13 = v11[4];
  if ( a4 == 0x8000000000000000uLL )
    goto LABEL_25;
  Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(a1, &v27, a4, 0);
  if ( v29 )
  {
    v15 = v28;
    v16 = v27;
    v17 = *(unsigned __int8 (__fastcall **)(void *, int *, _QWORD))(*(_QWORD *)v13 + 80LL);
    v25 = v27;
    v26 = v28;
    if ( !v17(v13, &v25, Kerb3961::g_supportedEncryptionTypes) )
    {
      Kerb3961::Logging::Verify::ConditionFailed(
        (Kerb3961::Logging::Verify *)"cipher->CipherEnabledForUsage(keyScenario, g_supportedEncryptionTypes)",
        v18);
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"CipherEnabledForUs(encryption, keyScenario)",
        (const char *)0xC00002FDLL,
        v19);
LABEL_18:
      *(_QWORD *)a2 = 0;
      *(_DWORD *)(a2 + 8) = -1073741059;
      goto LABEL_19;
    }
    v27 = v16;
    v28 = v15;
    v21 = *(_DWORD *)Kerb3961::CipherPolicyImpl::CipherEnabledForPartners(
                       a1,
                       (unsigned int)&v25,
                       (_DWORD)v13,
                       (unsigned int)&v27,
                       a5,
                       a6);
    if ( v21 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"CipherEnabledForPartners(encryption, keyScenario, partner1, partner2)",
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
0x18000cfd0  mov     [rsp-28h+arg_0], rbx
0x18000cfd5  mov     [rsp-28h+arg_8], rsi
0x18000cfda  push    rbp
0x18000cfdb  push    rdi
0x18000cfdc  push    r12
0x18000cfde  push    r14
0x18000cfe0  push    r15
0x18000cfe2  mov     rbp, rsp
0x18000cfe5  sub     rsp, 60h
0x18000cfe9  mov     r15, 8000000000000000h
0x18000cff3  xor     r12d, r12d
0x18000cff6  mov     rdi, r9
0x18000cff9  mov     esi, r8d
0x18000cffc  mov     rbx, rdx
0x18000cfff  mov     r14, rcx
0x18000d002  cmp     r9, r15
0x18000d005  jnz     short loc_18000D016
0x18000d007  cmp     cs:?g_allowPolicyBypass@Kerb3961@@3_NA, r12b; bool Kerb3961::g_allowPolicyBypass
0x18000d00e  jz      loc_18000D1D9
0x18000d014  jmp     short loc_18000D029
0x18000d016  mov     rax, 8000000000000001h
0x18000d020  cmp     rdi, rax
0x18000d023  jz      loc_18000D196
0x18000d029  mov     r8, rdi
0x18000d02c  lea     rdx, [rbp+arg_18]
0x18000d030  call    ?EnsureInitialization@CipherPolicyImpl@Kerb3961@@QEBA?AUInitializationSentinel@12@W4KeyUsage@2@@Z; Kerb3961::CipherPolicyImpl::EnsureInitialization(Kerb3961::KeyUsage)
0x18000d035  lea     rdx, [rbp+SRWLock]
0x18000d039  lea     rcx, ?g_cipherLock@Kerb3961@@3UCommonLock@1@A; Kerb3961::CommonLock Kerb3961::g_cipherLock
0x18000d040  call    ?lock_shared@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_shared(void)
0x18000d045  lea     r8, ?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x18000d04c  cmp     cs:qword_180029048, r8
0x18000d053  jz      loc_18000D11F
0x18000d059  mov     rax, cs:?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x18000d060  mov     rcx, r8
0x18000d063  cmp     [rax+18h], esi
0x18000d066  jnb     short loc_18000D06F
0x18000d068  mov     edx, 10h
0x18000d06d  jmp     short loc_18000D077
0x18000d06f  mov     rcx, rax
0x18000d072  mov     edx, 8
0x18000d077  mov     rax, [rdx+rax]
0x18000d07b  lea     rdx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000d082  cmp     rax, rdx
0x18000d085  jnz     short loc_18000D063
0x18000d087  cmp     rcx, r8
0x18000d08a  jz      loc_18000D11F
0x18000d090  cmp     esi, [rcx+18h]
0x18000d093  jb      loc_18000D11F
0x18000d099  mov     rsi, [rcx+20h]
0x18000d09d  cmp     rdi, r15
0x18000d0a0  jz      loc_18000D18D
0x18000d0a6  xor     r9d, r9d
0x18000d0a9  lea     rdx, [rbp+var_20]
0x18000d0ad  mov     r8, rdi
0x18000d0b0  mov     rcx, r14
0x18000d0b3  call    ?GetOurPolicyScenarioForKeyUsage@CipherPolicyImpl@Kerb3961@@QEBA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@2@W4KeyPolicyQualifiers@2@@Z; Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(Kerb3961::KeyUsage,Kerb3961::KeyPolicyQualifiers)
0x18000d0b8  cmp     [rbp+var_1B], r12b
0x18000d0bc  jnz     short loc_18000D0D6
0x18000d0be  lea     rcx, aScenariooptHas; "scenarioOpt.has_value()"
0x18000d0c5  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d0ca  mov     [rbx], r12
0x18000d0cd  mov     dword ptr [rbx+8], 0C000000Dh
0x18000d0d4  jmp     short loc_18000D129
0x18000d0d6  mov     rax, [rsi]
0x18000d0d9  lea     rdx, [rbp+var_30]
0x18000d0dd  mov     r15b, [rbp+var_1C]
0x18000d0e1  mov     rcx, rsi
0x18000d0e4  mov     edi, [rbp+var_20]
0x18000d0e7  mov     r8d, cs:?g_supportedEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A; Kerb3961::EncryptionTypeBitmask Kerb3961::g_supportedEncryptionTypes
0x18000d0ee  mov     rax, [rax+50h]
0x18000d0f2  mov     [rbp+var_30], edi
0x18000d0f5  mov     [rbp+var_2C], r15b
0x18000d0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0fe  test    al, al
0x18000d100  jnz     short loc_18000D145
0x18000d102  lea     rcx, aCipherCipheren; "cipher->CipherEnabledForUsage(keyScenar"...
0x18000d109  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d10e  mov     edx, 0C00002FDh; char *
0x18000d113  lea     rcx, aCipherenabledf; "CipherEnabledForUs(encryption, keyScena"...
0x18000d11a  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d11f  mov     [rbx], r12
0x18000d122  mov     dword ptr [rbx+8], 0C00002FDh
0x18000d129  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000d12d  test    rcx, rcx
0x18000d130  jz      short loc_18000D138
0x18000d132  call    cs:__imp_ReleaseSRWLockShared
0x18000d138  cmp     [rbp+arg_18], r12b
0x18000d13c  jz      short loc_18000D1BD
0x18000d13e  call    ?UninitializeCiphers@Kerb3961@@YAXXZ; Kerb3961::UninitializeCiphers(void)
0x18000d143  jmp     short loc_18000D1BD
0x18000d145  mov     rax, [rbp+arg_28]
0x18000d149  lea     r9, [rbp+var_20]
0x18000d14d  mov     [rsp+60h+var_38], rax
0x18000d152  lea     rdx, [rbp+var_30]
0x18000d156  mov     rax, [rbp+arg_20]
0x18000d15a  mov     r8, rsi
0x18000d15d  mov     rcx, r14
0x18000d160  mov     [rsp+60h+var_40], rax
0x18000d165  mov     [rbp+var_20], edi
0x18000d168  mov     [rbp+var_1C], r15b
0x18000d16c  call    ?CipherEnabledForPartners@CipherPolicyImpl@Kerb3961@@QEBA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@PEAUEncryptionAlgorithm@2@UKeyPolicyScenario@2@AEBUCipherPartnerHandle@2@2@Z; Kerb3961::CipherPolicyImpl::CipherEnabledForPartners(Kerb3961::EncryptionAlgorithm *,Kerb3961::KeyPolicyScenario,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)
0x18000d171  mov     edi, [rax]
0x18000d173  test    edi, edi
0x18000d175  jns     short loc_18000D18D
0x18000d177  mov     edx, edi; char *
0x18000d179  lea     rcx, aCipherenabledf_1; "CipherEnabledForPartners(encryption, ke"...
0x18000d180  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d185  mov     [rbx], r12
0x18000d188  mov     [rbx+8], edi
0x18000d18b  jmp     short loc_18000D129
0x18000d18d  mov     [rbx], rsi
0x18000d190  mov     [rbx+8], r12d
0x18000d194  jmp     short loc_18000D129
0x18000d196  lea     rcx, aKeyusageKeyusa; "keyUsage != KeyUsage::AlwaysBlocked"
0x18000d19d  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d1a2  mov     edx, 0C00002FDh; char *
0x18000d1a7  lea     rcx, aCheckkeyusageK; "CheckKeyUsage(keyUsage)"
0x18000d1ae  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d1b3  mov     [rbx], r12
0x18000d1b6  mov     dword ptr [rbx+8], 0C00002FDh
0x18000d1bd  lea     r11, [rsp+60h+var_s0]
0x18000d1c2  mov     rax, rbx
0x18000d1c5  mov     rbx, [r11+30h]
0x18000d1c9  mov     rsi, [r11+38h]
0x18000d1cd  mov     rsp, r11
0x18000d1d0  pop     r15
0x18000d1d2  pop     r14
0x18000d1d4  pop     r12
0x18000d1d6  pop     rdi
0x18000d1d7  pop     rbp
0x18000d1d8  retn
0x18000d1d9  lea     rcx, aNonTestCodeIsA; "Non test code is attempting to bypass p"...
0x18000d1e0  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
