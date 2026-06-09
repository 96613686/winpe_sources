# Kerb3961::CipherPolicyImpl::GetCiphers(Kerb3961::KeyUsage,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)

- ea: `0x18000ba20`
- end: `0x18000bc7b`
- name: `?GetCiphers@CipherPolicyImpl@Kerb3961@@UEBA?AU?$ReturnType@U?$ResultAdapter@UEncryptionTypeArray@Kerb3961@@@Kerb3961@@$1??$SingleGetter@U?$ResultAdapter@UEncryptionTypeArray@Kerb3961@@@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@U?$ResultAdapter@UEncryptionTypeArray@Kerb3961@@@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@W4KeyUsage@2@AEBUCipherPartnerHandle@2@1@Z`
- size: `603`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002dcc`
- `0x180002fc0`
- `0x180003380`
- `0x1800033f4`
- `0x180003610`
- `0x180003da0`
- `0x18000a1a4`
- `0x18000ae18`
- `0x18000b024`
- `0x18000ba20`
- `0x18000bfc8`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000bc17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000bc17`

## string_xrefs

- `0x18000bc6e`: `Non test code is attempting to bypass policy`

## pseudocode

```c
__int64 __fastcall Kerb3961::CipherPolicyImpl::GetCiphers(
        Kerb3961::CipherPolicyImpl *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5)
{
  __int64 v6; // rbx
  __int64 v8; // r9
  const char *v9; // rdx
  Kerb3961 *v10; // rcx
  const char *v11; // rdx
  _DWORD *v12; // rdi
  int v13; // ebx
  _QWORD *v14; // rax
  __int64 v15; // r15
  char v16; // r14
  __int64 v17; // r12
  const char *v18; // rdx
  const struct std::nothrow_t *v19; // rdx
  int v20; // r8d
  _BYTE v22[4]; // [rsp+30h] [rbp-40h] BYREF
  int v23[3]; // [rsp+34h] [rbp-3Ch] BYREF
  int v24; // [rsp+40h] [rbp-30h] BYREF
  char v25; // [rsp+44h] [rbp-2Ch]
  int v26; // [rsp+50h] [rbp-20h] BYREF
  char v27; // [rsp+54h] [rbp-1Ch]
  char v28; // [rsp+55h] [rbp-1Bh]
  PSRWLOCK SRWLock; // [rsp+60h] [rbp-10h] BYREF
  void *v30; // [rsp+68h] [rbp-8h] BYREF

  v6 = a2;
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
    *(_QWORD *)v6 = 0;
    *(_QWORD *)(v6 + 8) = 0;
    *(_DWORD *)(v6 + 16) = -1073741059;
    return v6;
  }
  Kerb3961::CipherPolicyImpl::EnsureInitialization(a1, v22, a3);
  LOBYTE(v8) = 8;
  Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(a1, &v26, a3, v8);
  if ( v28 )
  {
    wil::srwlock::lock_shared((char *)a1 + 16, &SRWLock);
    utl::make_unique<unsigned int [0],0>(&v30, *((_QWORD *)a1 + 6));
    v12 = v30;
    if ( v30 )
    {
      v13 = v26;
      v14 = (_QWORD *)*((_QWORD *)a1 + 5);
      v15 = 0;
      v16 = v27;
      v30 = v14;
      while ( v14 != (_QWORD *)((char *)a1 + 24) )
      {
        v17 = v14[4];
        v24 = v13;
        v25 = v16;
        if ( (*(unsigned __int8 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v17 + 80LL))(
               v17,
               &v24,
               Kerb3961::g_supportedEncryptionTypes) )
        {
          v26 = v13;
          v27 = v16;
          if ( *Kerb3961::CipherPolicyImpl::CipherEnabledForPartners((__int64)a1, v23, v17, &v26, a4, a5) >= 0 )
            v12[v15++] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 216LL))(v17);
        }
        else
        {
          Kerb3961::Logging::Verify::ConditionFailed(
            (Kerb3961::Logging::Verify *)"cipher->CipherEnabledForUsage(keyScenario, g_supportedEncryptionTypes)",
            v18);
        }
        utl::_TreeConstIt<utl::pair<unsigned int const,Kerb3961::EncryptionAlgorithm *>>::operator++(&v30);
        v14 = v30;
      }
      v6 = a2;
      if ( v15 )
      {
        Kerb3961::Logging::Policy::GetCiphers(a3, v12, v15, 0);
        *(_QWORD *)a2 = v15;
        *(_QWORD *)(a2 + 8) = v12;
        *(_DWORD *)(a2 + 16) = 0;
      }
      else
      {
        Kerb3961::Logging::Policy::GetCiphers(a3, v12, 0, 3221226237LL);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = -1073741059;
        if ( v12 )
          operator delete(v12, v19);
      }
    }
    else
    {
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"array != nullptr", v11);
      *(_QWORD *)v6 = 0;
      *(_QWORD *)(v6 + 8) = 0;
      *(_DWORD *)(v6 + 16) = -1073741801;
    }
    v10 = (Kerb3961 *)SRWLock;
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"scenarioOpt.has_value()", v9);
    *(_QWORD *)v6 = 0;
    *(_QWORD *)(v6 + 8) = 0;
    *(_DWORD *)(v6 + 16) = -1073741811;
  }
  if ( v22[0] )
    Kerb3961::UninitializeCiphers(v10);
  return v6;
}

```

## disassembly

```asm
0x18000ba20  mov     rax, rsp
0x18000ba23  mov     [rax+8], rbx
0x18000ba27  mov     [rax+20h], r9
0x18000ba2b  mov     [rax+18h], r8
0x18000ba2f  mov     [rax+10h], rdx
0x18000ba33  push    rbp
0x18000ba34  push    rsi
0x18000ba35  push    rdi
0x18000ba36  push    r12
0x18000ba38  push    r13
0x18000ba3a  push    r14
0x18000ba3c  push    r15
0x18000ba3e  mov     rbp, rsp
0x18000ba41  sub     rsp, 70h
0x18000ba45  mov     rax, 8000000000000000h
0x18000ba4f  xor     r12d, r12d
0x18000ba52  mov     r14, r8
0x18000ba55  mov     rbx, rdx
0x18000ba58  mov     rsi, rcx
0x18000ba5b  cmp     r8, rax
0x18000ba5e  jnz     short loc_18000BA6F
0x18000ba60  cmp     cs:?g_allowPolicyBypass@Kerb3961@@3_NA, r12b; bool Kerb3961::g_allowPolicyBypass
0x18000ba67  jz      loc_18000BC6E
0x18000ba6d  jmp     short loc_18000BA82
0x18000ba6f  mov     rax, 8000000000000001h
0x18000ba79  cmp     r14, rax
0x18000ba7c  jz      loc_18000BC2A
0x18000ba82  lea     rdx, [rbp+var_40]
0x18000ba86  call    ?EnsureInitialization@CipherPolicyImpl@Kerb3961@@QEBA?AUInitializationSentinel@12@W4KeyUsage@2@@Z; Kerb3961::CipherPolicyImpl::EnsureInitialization(Kerb3961::KeyUsage)
0x18000ba8b  mov     r9b, 8
0x18000ba8e  lea     rdx, [rbp+var_20]
0x18000ba92  mov     r8, r14
0x18000ba95  mov     rcx, rsi
0x18000ba98  call    ?GetOurPolicyScenarioForKeyUsage@CipherPolicyImpl@Kerb3961@@QEBA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@2@W4KeyPolicyQualifiers@2@@Z; Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(Kerb3961::KeyUsage,Kerb3961::KeyPolicyQualifiers)
0x18000ba9d  cmp     [rbp+var_1B], r12b
0x18000baa1  jnz     short loc_18000BAC2
0x18000baa3  lea     rcx, aScenariooptHas; "scenarioOpt.has_value()"
0x18000baaa  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000baaf  mov     [rbx], r12
0x18000bab2  mov     [rbx+8], r12
0x18000bab6  mov     dword ptr [rbx+10h], 0C000000Dh
0x18000babd  jmp     loc_18000BC1D
0x18000bac2  lea     rcx, [rsi+10h]
0x18000bac6  lea     rdx, [rbp+SRWLock]
0x18000baca  call    ?lock_shared@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_shared(void)
0x18000bacf  mov     rdx, [rsi+30h]
0x18000bad3  lea     rcx, [rbp+var_8]
0x18000bad7  call    ??$make_unique@$$BY0A@I$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@IU?$default_delete@$$BY0A@I@utl@@@0@_K@Z; utl::make_unique<uint [0],0>(unsigned __int64)
0x18000badc  mov     rdi, [rbp+var_8]
0x18000bae0  test    rdi, rdi
0x18000bae3  jz      loc_18000BBF4
0x18000bae9  mov     ebx, [rbp+var_20]
0x18000baec  lea     r13, [rsi+18h]
0x18000baf0  mov     rax, [r13+10h]
0x18000baf4  mov     r15, r12
0x18000baf7  mov     r14b, [rbp+var_1C]
0x18000bafb  mov     [rbp+var_8], rax
0x18000baff  cmp     rax, r13
0x18000bb02  jz      loc_18000BB9D
0x18000bb08  mov     r12, [rax+20h]
0x18000bb0c  lea     rdx, [rbp+var_30]
0x18000bb10  mov     r8d, cs:?g_supportedEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A; Kerb3961::EncryptionTypeBitmask Kerb3961::g_supportedEncryptionTypes
0x18000bb17  mov     rcx, r12
0x18000bb1a  mov     [rbp+var_30], ebx
0x18000bb1d  mov     [rbp+var_2C], r14b
0x18000bb21  mov     rax, [r12]
0x18000bb25  mov     rax, [rax+50h]
0x18000bb29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb2e  test    al, al
0x18000bb30  jnz     short loc_18000BB40
0x18000bb32  lea     rcx, aCipherCipheren; "cipher->CipherEnabledForUsage(keyScenar"...
0x18000bb39  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000bb3e  jmp     short loc_18000BB8B
0x18000bb40  mov     rax, [rbp+arg_20]
0x18000bb44  lea     r9, [rbp+var_20]
0x18000bb48  mov     [rsp+70h+var_48], rax
0x18000bb4d  lea     rdx, [rbp+var_3C]
0x18000bb51  mov     rax, [rbp+arg_18]
0x18000bb55  mov     r8, r12
0x18000bb58  mov     rcx, rsi
0x18000bb5b  mov     [rsp+70h+var_50], rax
0x18000bb60  mov     [rbp+var_20], ebx
0x18000bb63  mov     [rbp+var_1C], r14b
0x18000bb67  call    ?CipherEnabledForPartners@CipherPolicyImpl@Kerb3961@@QEBA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@PEAUEncryptionAlgorithm@2@UKeyPolicyScenario@2@AEBUCipherPartnerHandle@2@2@Z; Kerb3961::CipherPolicyImpl::CipherEnabledForPartners(Kerb3961::EncryptionAlgorithm *,Kerb3961::KeyPolicyScenario,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)
0x18000bb6c  cmp     dword ptr [rax], 0
0x18000bb6f  jl      short loc_18000BB8B
0x18000bb71  mov     rax, [r12]
0x18000bb75  mov     rcx, r12
0x18000bb78  mov     rax, [rax+0D8h]
0x18000bb7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb84  mov     [rdi+r15*4], eax
0x18000bb88  inc     r15
0x18000bb8b  lea     rcx, [rbp+var_8]
0x18000bb8f  call    ??E?$_TreeConstIt@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>::operator++(void)
0x18000bb94  mov     rax, [rbp+var_8]
0x18000bb98  jmp     loc_18000BAFF
0x18000bb9d  mov     r14, [rbp+arg_10]
0x18000bba1  xor     r12d, r12d
0x18000bba4  mov     rbx, [rbp+arg_8]
0x18000bba8  mov     rdx, rdi
0x18000bbab  mov     rcx, r14
0x18000bbae  test    r15, r15
0x18000bbb1  jnz     short loc_18000BBDC
0x18000bbb3  mov     esi, 0C00002FDh
0x18000bbb8  xor     r8d, r8d
0x18000bbbb  mov     r9d, esi
0x18000bbbe  call    ?GetCiphers@Policy@Logging@Kerb3961@@YAXW4KeyUsage@3@QEAI_KJ@Z; Kerb3961::Logging::Policy::GetCiphers(Kerb3961::KeyUsage,uint * const,unsigned __int64,long)
0x18000bbc3  mov     [rbx], r12
0x18000bbc6  mov     [rbx+8], r12
0x18000bbca  mov     [rbx+10h], esi
0x18000bbcd  test    rdi, rdi
0x18000bbd0  jz      short loc_18000BC0E
0x18000bbd2  mov     rcx, rdi; void *
0x18000bbd5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bbda  jmp     short loc_18000BC0E
0x18000bbdc  xor     r9d, r9d
0x18000bbdf  mov     r8, r15
0x18000bbe2  call    ?GetCiphers@Policy@Logging@Kerb3961@@YAXW4KeyUsage@3@QEAI_KJ@Z; Kerb3961::Logging::Policy::GetCiphers(Kerb3961::KeyUsage,uint * const,unsigned __int64,long)
0x18000bbe7  mov     [rbx], r15
0x18000bbea  mov     [rbx+8], rdi
0x18000bbee  mov     [rbx+10h], r12d
0x18000bbf2  jmp     short loc_18000BC0E
0x18000bbf4  lea     rcx, aArrayNullptr; "array != nullptr"
0x18000bbfb  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000bc00  mov     [rbx], r12
0x18000bc03  mov     [rbx+8], r12
0x18000bc07  mov     dword ptr [rbx+10h], 0C0000017h
0x18000bc0e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000bc12  test    rcx, rcx
0x18000bc15  jz      short loc_18000BC1D
0x18000bc17  call    cs:__imp_ReleaseSRWLockShared
0x18000bc1d  cmp     [rbp+var_40], r12b
0x18000bc21  jz      short loc_18000BC53
0x18000bc23  call    ?UninitializeCiphers@Kerb3961@@YAXXZ; Kerb3961::UninitializeCiphers(void)
0x18000bc28  jmp     short loc_18000BC53
0x18000bc2a  lea     rcx, aKeyusageKeyusa; "keyUsage != KeyUsage::AlwaysBlocked"
0x18000bc31  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000bc36  mov     esi, 0C00002FDh
0x18000bc3b  lea     rcx, aCheckkeyusageK; "CheckKeyUsage(keyUsage)"
0x18000bc42  mov     edx, esi; char *
0x18000bc44  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000bc49  mov     [rbx], r12
0x18000bc4c  mov     [rbx+8], r12
0x18000bc50  mov     [rbx+10h], esi
0x18000bc53  mov     rax, rbx
0x18000bc56  mov     rbx, [rsp+70h+arg_0]
0x18000bc5e  add     rsp, 70h
0x18000bc62  pop     r15
0x18000bc64  pop     r14
0x18000bc66  pop     r13
0x18000bc68  pop     r12
0x18000bc6a  pop     rdi
0x18000bc6b  pop     rsi
0x18000bc6c  pop     rbp
0x18000bc6d  retn
0x18000bc6e  lea     rcx, aNonTestCodeIsA; "Non test code is attempting to bypass p"...
0x18000bc75  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
