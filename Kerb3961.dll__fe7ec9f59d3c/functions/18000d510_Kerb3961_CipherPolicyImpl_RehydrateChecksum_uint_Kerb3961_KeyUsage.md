# Kerb3961::CipherPolicyImpl::RehydrateChecksum(uint,Kerb3961::KeyUsage)

- ea: `0x18000d510`
- end: `0x18000d6d8`
- name: `?RehydrateChecksum@CipherPolicyImpl@Kerb3961@@UEBA?AU?$ReturnType@U?$ResultAdapter@PEAUChecksumAlgorithm@Kerb3961@@@Kerb3961@@$1??$SingleGetter@U?$ResultAdapter@PEAUChecksumAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@U?$ResultAdapter@PEAUChecksumAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEAU32@AEAU12@@Z@2@IW4KeyUsage@2@@Z`
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
- `0x18000d510`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d671`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d671`

## string_xrefs

- `0x18000d6cb`: `Non test code is attempting to bypass policy`

## pseudocode

```c
__int64 __fastcall Kerb3961::CipherPolicyImpl::RehydrateChecksum(
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
  if ( (void **)qword_180029068 == &Kerb3961::g_checksums )
    goto LABEL_19;
  v9 = (void **)Kerb3961::g_checksums;
  v10 = &Kerb3961::g_checksums;
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
  if ( v10 == &Kerb3961::g_checksums || a3 < *((_DWORD *)v10 + 6) )
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
      && !(*(unsigned __int8 (__fastcall **)(void *, int *, _QWORD))(*(_QWORD *)v12 + 56LL))(
            v12,
            &v19,
            Kerb3961::g_supportedEncryptionTypes) )
    {
      Kerb3961::Logging::Verify::ConditionFailed(
        (Kerb3961::Logging::Verify *)"checksum->ChecksumEnabledForUsage(keyScenario, g_supportedEncryptionTypes)",
        v14);
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"ChecksumEnabledForUs(checksum, keyScenario)",
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
0x18000d510  push    rbp
0x18000d512  push    rbx
0x18000d513  push    rsi
0x18000d514  push    rdi
0x18000d515  push    r12
0x18000d517  push    r14
0x18000d519  mov     rbp, rsp
0x18000d51c  sub     rsp, 48h
0x18000d520  mov     r12, 8000000000000000h
0x18000d52a  mov     rdi, r9
0x18000d52d  mov     esi, r8d
0x18000d530  mov     rbx, rdx
0x18000d533  mov     r14, rcx
0x18000d536  cmp     r9, r12
0x18000d539  jnz     short loc_18000D54A
0x18000d53b  cmp     cs:?g_allowPolicyBypass@Kerb3961@@3_NA, 0; bool Kerb3961::g_allowPolicyBypass
0x18000d542  jz      loc_18000D6CB
0x18000d548  jmp     short loc_18000D55D
0x18000d54a  mov     rax, 8000000000000001h
0x18000d554  cmp     rdi, rax
0x18000d557  jz      loc_18000D690
0x18000d55d  mov     r8, rdi
0x18000d560  lea     rdx, [rbp+arg_18]
0x18000d564  call    ?EnsureInitialization@CipherPolicyImpl@Kerb3961@@QEBA?AUInitializationSentinel@12@W4KeyUsage@2@@Z; Kerb3961::CipherPolicyImpl::EnsureInitialization(Kerb3961::KeyUsage)
0x18000d569  lea     rdx, [rbp+SRWLock]
0x18000d56d  lea     rcx, ?g_cipherLock@Kerb3961@@3UCommonLock@1@A; Kerb3961::CommonLock Kerb3961::g_cipherLock
0x18000d574  call    ?lock_shared@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_shared(void)
0x18000d579  lea     r8, ?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x18000d580  cmp     cs:qword_180029068, r8
0x18000d587  jz      loc_18000D65A
0x18000d58d  mov     rax, cs:?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x18000d594  mov     rcx, r8
0x18000d597  cmp     [rax+18h], esi
0x18000d59a  jnb     short loc_18000D5A3
0x18000d59c  mov     edx, 10h
0x18000d5a1  jmp     short loc_18000D5AB
0x18000d5a3  mov     rcx, rax
0x18000d5a6  mov     edx, 8
0x18000d5ab  mov     rax, [rdx+rax]
0x18000d5af  lea     rdx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000d5b6  cmp     rax, rdx
0x18000d5b9  jnz     short loc_18000D597
0x18000d5bb  cmp     rcx, r8
0x18000d5be  jz      loc_18000D65A
0x18000d5c4  cmp     esi, [rcx+18h]
0x18000d5c7  jb      loc_18000D65A
0x18000d5cd  mov     rsi, [rcx+20h]
0x18000d5d1  cmp     rdi, r12
0x18000d5d4  jz      loc_18000D684
0x18000d5da  mov     r9b, 10h
0x18000d5dd  lea     rdx, [rbp+var_28]
0x18000d5e1  mov     r8, rdi
0x18000d5e4  mov     rcx, r14
0x18000d5e7  call    ?GetOurPolicyScenarioForKeyUsage@CipherPolicyImpl@Kerb3961@@QEBA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@2@W4KeyPolicyQualifiers@2@@Z; Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(Kerb3961::KeyUsage,Kerb3961::KeyPolicyQualifiers)
0x18000d5ec  cmp     [rbp+var_23], 0
0x18000d5f0  jnz     short loc_18000D60E
0x18000d5f2  lea     rcx, aScenariooptHas; "scenarioOpt.has_value()"
0x18000d5f9  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d5fe  mov     qword ptr [rbx], 0
0x18000d605  mov     dword ptr [rbx+8], 0C000000Dh
0x18000d60c  jmp     short loc_18000D668
0x18000d60e  mov     cl, [rbp+var_24]
0x18000d611  test    cl, 4
0x18000d614  jz      short loc_18000D684
0x18000d616  mov     eax, [rbp+var_28]
0x18000d619  lea     rdx, [rbp+var_28]
0x18000d61d  mov     r8d, cs:?g_supportedEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A; Kerb3961::EncryptionTypeBitmask Kerb3961::g_supportedEncryptionTypes
0x18000d624  mov     [rbp+var_28], eax
0x18000d627  mov     rax, [rsi]
0x18000d62a  mov     [rbp+var_24], cl
0x18000d62d  mov     rcx, rsi
0x18000d630  mov     rax, [rax+38h]
0x18000d634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d639  test    al, al
0x18000d63b  jnz     short loc_18000D684
0x18000d63d  lea     rcx, aChecksumChecks_0; "checksum->ChecksumEnabledForUsage(keySc"...
0x18000d644  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d649  mov     edx, 0C00002FDh; char *
0x18000d64e  lea     rcx, aChecksumenable_3; "ChecksumEnabledForUs(checksum, keyScena"...
0x18000d655  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d65a  mov     qword ptr [rbx], 0
0x18000d661  mov     dword ptr [rbx+8], 0C00002FDh
0x18000d668  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000d66c  test    rcx, rcx
0x18000d66f  jz      short loc_18000D677
0x18000d671  call    cs:__imp_ReleaseSRWLockShared
0x18000d677  cmp     [rbp+arg_18], 0
0x18000d67b  jz      short loc_18000D6BB
0x18000d67d  call    ?UninitializeCiphers@Kerb3961@@YAXXZ; Kerb3961::UninitializeCiphers(void)
0x18000d682  jmp     short loc_18000D6BB
0x18000d684  mov     [rbx], rsi
0x18000d687  mov     dword ptr [rbx+8], 0
0x18000d68e  jmp     short loc_18000D668
0x18000d690  lea     rcx, aKeyusageKeyusa; "keyUsage != KeyUsage::AlwaysBlocked"
0x18000d697  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d69c  mov     edx, 0C00002FDh; char *
0x18000d6a1  lea     rcx, aCheckkeyusageK; "CheckKeyUsage(keyUsage)"
0x18000d6a8  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d6ad  mov     qword ptr [rbx], 0
0x18000d6b4  mov     dword ptr [rbx+8], 0C00002FDh
0x18000d6bb  mov     rax, rbx
0x18000d6be  add     rsp, 48h
0x18000d6c2  pop     r14
0x18000d6c4  pop     r12
0x18000d6c6  pop     rdi
0x18000d6c7  pop     rsi
0x18000d6c8  pop     rbx
0x18000d6c9  pop     rbp
0x18000d6ca  retn
0x18000d6cb  lea     rcx, aNonTestCodeIsA; "Non test code is attempting to bypass p"...
0x18000d6d2  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
