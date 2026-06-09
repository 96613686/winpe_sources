# Kerb3961::CipherPolicyImpl::RehydrateEncryption(uint,Kerb3961::KeyUsage)

- ea: `0x18000d6e0`
- end: `0x18000d8a8`
- name: `?RehydrateEncryption@CipherPolicyImpl@Kerb3961@@UEBA?AU?$ReturnType@U?$ResultAdapter@PEAUEncryptionAlgorithm@Kerb3961@@@Kerb3961@@$1??$SingleGetter@U?$ResultAdapter@PEAUEncryptionAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@U?$ResultAdapter@PEAUEncryptionAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEAU32@AEAU12@@Z@2@IW4KeyUsage@2@@Z`
- size: `456`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x180003610`
- `0x180003da0`
- `0x18000b024`
- `0x18000bfc8`
- `0x18000d6e0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d841`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d841`

## string_xrefs

- `0x18000d89b`: `Non test code is attempting to bypass policy`

## pseudocode

```c
__int64 __fastcall Kerb3961::CipherPolicyImpl::RehydrateEncryption(
        Kerb3961::CipherPolicyImpl *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 v8; // r9
  void **v9; // rax
  void **v10; // rcx
  __int64 v11; // rdx
  void *v12; // rsi
  const char *v13; // rdx
  const char *v14; // rdx
  int v15; // r8d
  Kerb3961 *v16; // rcx
  int v17; // r8d
  int v19; // [rsp+20h] [rbp-28h] BYREF
  char v20; // [rsp+24h] [rbp-24h]
  char v21; // [rsp+25h] [rbp-23h]
  PSRWLOCK SRWLock[3]; // [rsp+30h] [rbp-18h] BYREF
  char v23; // [rsp+98h] [rbp+50h] BYREF

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
      v17);
    *(_QWORD *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -1073741059;
    return a2;
  }
  Kerb3961::CipherPolicyImpl::EnsureInitialization(a1, &v23, a4);
  wil::srwlock::lock_shared(&Kerb3961::g_cipherLock, SRWLock);
  if ( (void **)qword_180029048 == &Kerb3961::g_encryptions )
    goto LABEL_19;
  v9 = (void **)Kerb3961::g_encryptions;
  v10 = &Kerb3961::g_encryptions;
  do
  {
    if ( *((_DWORD *)v9 + 6) >= a3 )
    {
      v10 = v9;
      v11 = 1;
    }
    else
    {
      v11 = 2;
    }
    v9 = (void **)v9[v11];
  }
  while ( v9 != &utl::_TreeSentinel );
  if ( v10 == &Kerb3961::g_encryptions || a3 < *((_DWORD *)v10 + 6) )
    goto LABEL_19;
  v12 = v10[4];
  if ( a4 == 0x8000000000000000uLL )
  {
LABEL_24:
    *(_QWORD *)a2 = v12;
    *(_DWORD *)(a2 + 8) = 0;
    goto LABEL_20;
  }
  LOBYTE(v8) = 16;
  Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(a1, &v19, a4, v8);
  if ( v21 )
  {
    if ( (v20 & 4) != 0
      && !(*(unsigned __int8 (__fastcall **)(void *, int *, _QWORD))(*(_QWORD *)v12 + 80LL))(
            v12,
            &v19,
            Kerb3961::g_supportedEncryptionTypes) )
    {
      Kerb3961::Logging::Verify::ConditionFailed(
        (Kerb3961::Logging::Verify *)"cipher->CipherEnabledForUsage(keyScenario, g_supportedEncryptionTypes)",
        v14);
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"CipherEnabledForUs(encryption, keyScenario)",
        (const char *)0xC00002FDLL,
        v15);
LABEL_19:
      *(_QWORD *)a2 = 0;
      *(_DWORD *)(a2 + 8) = -1073741059;
      goto LABEL_20;
    }
    goto LABEL_24;
  }
  Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"scenarioOpt.has_value()", v13);
  *(_QWORD *)a2 = 0;
  *(_DWORD *)(a2 + 8) = -1073741811;
LABEL_20:
  v16 = (Kerb3961 *)SRWLock[0];
  if ( SRWLock[0] )
    ReleaseSRWLockShared(SRWLock[0]);
  if ( v23 )
    Kerb3961::UninitializeCiphers(v16);
  return a2;
}

```

## disassembly

```asm
0x18000d6e0  push    rbp
0x18000d6e2  push    rbx
0x18000d6e3  push    rsi
0x18000d6e4  push    rdi
0x18000d6e5  push    r12
0x18000d6e7  push    r14
0x18000d6e9  mov     rbp, rsp
0x18000d6ec  sub     rsp, 48h
0x18000d6f0  mov     r12, 8000000000000000h
0x18000d6fa  mov     rdi, r9
0x18000d6fd  mov     esi, r8d
0x18000d700  mov     rbx, rdx
0x18000d703  mov     r14, rcx
0x18000d706  cmp     r9, r12
0x18000d709  jnz     short loc_18000D71A
0x18000d70b  cmp     cs:?g_allowPolicyBypass@Kerb3961@@3_NA, 0; bool Kerb3961::g_allowPolicyBypass
0x18000d712  jz      loc_18000D89B
0x18000d718  jmp     short loc_18000D72D
0x18000d71a  mov     rax, 8000000000000001h
0x18000d724  cmp     rdi, rax
0x18000d727  jz      loc_18000D860
0x18000d72d  mov     r8, rdi
0x18000d730  lea     rdx, [rbp+arg_18]
0x18000d734  call    ?EnsureInitialization@CipherPolicyImpl@Kerb3961@@QEBA?AUInitializationSentinel@12@W4KeyUsage@2@@Z; Kerb3961::CipherPolicyImpl::EnsureInitialization(Kerb3961::KeyUsage)
0x18000d739  lea     rdx, [rbp+SRWLock]
0x18000d73d  lea     rcx, ?g_cipherLock@Kerb3961@@3UCommonLock@1@A; Kerb3961::CommonLock Kerb3961::g_cipherLock
0x18000d744  call    ?lock_shared@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_shared(void)
0x18000d749  lea     r8, ?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x18000d750  cmp     cs:qword_180029048, r8
0x18000d757  jz      loc_18000D82A
0x18000d75d  mov     rax, cs:?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x18000d764  mov     rcx, r8
0x18000d767  cmp     [rax+18h], esi
0x18000d76a  jnb     short loc_18000D773
0x18000d76c  mov     edx, 10h
0x18000d771  jmp     short loc_18000D77B
0x18000d773  mov     rcx, rax
0x18000d776  mov     edx, 8
0x18000d77b  mov     rax, [rdx+rax]
0x18000d77f  lea     rdx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000d786  cmp     rax, rdx
0x18000d789  jnz     short loc_18000D767
0x18000d78b  cmp     rcx, r8
0x18000d78e  jz      loc_18000D82A
0x18000d794  cmp     esi, [rcx+18h]
0x18000d797  jb      loc_18000D82A
0x18000d79d  mov     rsi, [rcx+20h]
0x18000d7a1  cmp     rdi, r12
0x18000d7a4  jz      loc_18000D854
0x18000d7aa  mov     r9b, 10h
0x18000d7ad  lea     rdx, [rbp+var_28]
0x18000d7b1  mov     r8, rdi
0x18000d7b4  mov     rcx, r14
0x18000d7b7  call    ?GetOurPolicyScenarioForKeyUsage@CipherPolicyImpl@Kerb3961@@QEBA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@2@W4KeyPolicyQualifiers@2@@Z; Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(Kerb3961::KeyUsage,Kerb3961::KeyPolicyQualifiers)
0x18000d7bc  cmp     [rbp+var_23], 0
0x18000d7c0  jnz     short loc_18000D7DE
0x18000d7c2  lea     rcx, aScenariooptHas; "scenarioOpt.has_value()"
0x18000d7c9  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d7ce  mov     qword ptr [rbx], 0
0x18000d7d5  mov     dword ptr [rbx+8], 0C000000Dh
0x18000d7dc  jmp     short loc_18000D838
0x18000d7de  mov     cl, [rbp+var_24]
0x18000d7e1  test    cl, 4
0x18000d7e4  jz      short loc_18000D854
0x18000d7e6  mov     eax, [rbp+var_28]
0x18000d7e9  lea     rdx, [rbp+var_28]
0x18000d7ed  mov     r8d, cs:?g_supportedEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A; Kerb3961::EncryptionTypeBitmask Kerb3961::g_supportedEncryptionTypes
0x18000d7f4  mov     [rbp+var_28], eax
0x18000d7f7  mov     rax, [rsi]
0x18000d7fa  mov     [rbp+var_24], cl
0x18000d7fd  mov     rcx, rsi
0x18000d800  mov     rax, [rax+50h]
0x18000d804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d809  test    al, al
0x18000d80b  jnz     short loc_18000D854
0x18000d80d  lea     rcx, aCipherCipheren; "cipher->CipherEnabledForUsage(keyScenar"...
0x18000d814  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d819  mov     edx, 0C00002FDh; char *
0x18000d81e  lea     rcx, aCipherenabledf; "CipherEnabledForUs(encryption, keyScena"...
0x18000d825  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d82a  mov     qword ptr [rbx], 0
0x18000d831  mov     dword ptr [rbx+8], 0C00002FDh
0x18000d838  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000d83c  test    rcx, rcx
0x18000d83f  jz      short loc_18000D847
0x18000d841  call    cs:__imp_ReleaseSRWLockShared
0x18000d847  cmp     [rbp+arg_18], 0
0x18000d84b  jz      short loc_18000D88B
0x18000d84d  call    ?UninitializeCiphers@Kerb3961@@YAXXZ; Kerb3961::UninitializeCiphers(void)
0x18000d852  jmp     short loc_18000D88B
0x18000d854  mov     [rbx], rsi
0x18000d857  mov     dword ptr [rbx+8], 0
0x18000d85e  jmp     short loc_18000D838
0x18000d860  lea     rcx, aKeyusageKeyusa; "keyUsage != KeyUsage::AlwaysBlocked"
0x18000d867  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d86c  mov     edx, 0C00002FDh; char *
0x18000d871  lea     rcx, aCheckkeyusageK; "CheckKeyUsage(keyUsage)"
0x18000d878  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d87d  mov     qword ptr [rbx], 0
0x18000d884  mov     dword ptr [rbx+8], 0C00002FDh
0x18000d88b  mov     rax, rbx
0x18000d88e  add     rsp, 48h
0x18000d892  pop     r14
0x18000d894  pop     r12
0x18000d896  pop     rdi
0x18000d897  pop     rsi
0x18000d898  pop     rbx
0x18000d899  pop     rbp
0x18000d89a  retn
0x18000d89b  lea     rcx, aNonTestCodeIsA; "Non test code is attempting to bypass p"...
0x18000d8a2  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
