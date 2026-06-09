# Kerb3961::CipherPolicyImpl::GetCheckums(Kerb3961::KeyUsage,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)

- ea: `0x18000b3d0`
- end: `0x18000b65a`
- name: `?GetCheckums@CipherPolicyImpl@Kerb3961@@UEBA?AU?$ReturnType@U?$ResultAdapter@UEncryptionTypeArray@Kerb3961@@@Kerb3961@@$1??$SingleGetter@U?$ResultAdapter@UEncryptionTypeArray@Kerb3961@@@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@U?$ResultAdapter@UEncryptionTypeArray@Kerb3961@@@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@W4KeyUsage@2@AEBUCipherPartnerHandle@2@1@Z`
- size: `650`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x180003610`
- `0x180003da0`
- `0x18000a1a4`
- `0x18000aa04`
- `0x18000b024`
- `0x18000b3d0`
- `0x18000bfc8`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b5f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b5f4`

## string_xrefs

- `0x18000b64d`: `Non test code is attempting to bypass policy`

## pseudocode

```c
__int64 __fastcall Kerb3961::CipherPolicyImpl::GetCheckums(
        Kerb3961::CipherPolicyImpl *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v6; // rdi
  __int64 v8; // r9
  const char *v9; // rdx
  Kerb3961 *v10; // rcx
  const struct std::nothrow_t *v11; // rdx
  _DWORD *v12; // rsi
  int v13; // edi
  _QWORD *v14; // rbx
  __int64 v15; // r15
  __int64 *v16; // r12
  __int64 v17; // rax
  const char *v18; // rdx
  unsigned __int64 v19; // rcx
  _QWORD *v20; // rax
  unsigned __int64 v21; // rax
  int v22; // r8d
  char v24; // [rsp+30h] [rbp-40h] BYREF
  int v25; // [rsp+40h] [rbp-30h] BYREF
  char v26; // [rsp+44h] [rbp-2Ch]
  void *v27[2]; // [rsp+50h] [rbp-20h] BYREF
  int v28; // [rsp+60h] [rbp-10h] BYREF
  char v29; // [rsp+64h] [rbp-Ch]
  char v30; // [rsp+65h] [rbp-Bh]
  PSRWLOCK SRWLock; // [rsp+68h] [rbp-8h] BYREF
  char v33; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v34; // [rsp+C8h] [rbp+58h]

  v34 = a4;
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
      v22);
    *(_QWORD *)v6 = 0;
    *(_QWORD *)(v6 + 8) = 0;
    *(_DWORD *)(v6 + 16) = -1073741059;
    return v6;
  }
  Kerb3961::CipherPolicyImpl::EnsureInitialization(a1, &v33, a3);
  LOBYTE(v8) = 8;
  Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(a1, &v28, a3, v8);
  if ( v30 )
  {
    wil::srwlock::lock_shared((char *)a1 + 16, &SRWLock);
    utl::make_unique<unsigned int [0],0>(v27, *((_QWORD *)a1 + 10));
    v12 = v27[0];
    if ( v27[0] )
    {
      v13 = v28;
      v14 = (_QWORD *)*((_QWORD *)a1 + 9);
      v15 = 0;
      while ( v14 != (_QWORD *)((char *)a1 + 56) )
      {
        v16 = (__int64 *)v14[4];
        v26 = v29;
        v17 = *v16;
        v25 = v13;
        if ( (*(unsigned __int8 (__fastcall **)(__int64 *, int *, _QWORD))(v17 + 56))(
               v16,
               &v25,
               Kerb3961::g_supportedEncryptionTypes) )
        {
          BYTE4(v27[0]) = v29;
          LODWORD(v27[0]) = v13;
          if ( *(int *)Kerb3961::CipherPolicyImpl::ChecksumEnabledForPartners(
                         (_DWORD)a1,
                         (unsigned int)&v24,
                         (_DWORD)v16,
                         (unsigned int)v27,
                         v34,
                         a5) >= 0 )
            v12[v15++] = (*(__int64 (__fastcall **)(__int64 *))(*v16 + 104))(v16);
        }
        else
        {
          Kerb3961::Logging::Verify::ConditionFailed(
            (Kerb3961::Logging::Verify *)"checksum->ChecksumEnabledForUsage(keyScenario, g_supportedEncryptionTypes)",
            v18);
        }
        v19 = v14[2];
        v11 = (const struct std::nothrow_t *)&utl::_TreeSentinel;
        if ( (void **)v19 == &utl::_TreeSentinel )
        {
          v20 = (_QWORD *)(*v14 & 0xFFFFFFFFFFFFFFFEuLL);
          v19 = (unsigned __int64)v20;
          if ( (_QWORD *)v20[2] == v14 && (_QWORD *)*v20 != v14 )
          {
            v19 = *v20 & 0xFFFFFFFFFFFFFFFEuLL;
            if ( *(_QWORD **)(v19 + 16) == v20 && *(_QWORD **)v19 != v20 )
            {
              do
              {
                v21 = v19;
                v19 = *(_QWORD *)v19 & 0xFFFFFFFFFFFFFFFEuLL;
              }
              while ( *(_QWORD *)(v19 + 16) == v21 );
            }
          }
        }
        else
        {
          if ( v14 == (_QWORD *)v19 )
            __int2c();
          for ( ; *(void ***)(v19 + 8) != &utl::_TreeSentinel; v19 = *(_QWORD *)(v19 + 8) )
            ;
        }
        v14 = (_QWORD *)v19;
      }
      v6 = a2;
      if ( v15 )
      {
        *(_QWORD *)a2 = v15;
        *(_QWORD *)(a2 + 8) = v12;
        *(_DWORD *)(a2 + 16) = 0;
      }
      else
      {
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = -1073741059;
        if ( v12 )
          operator delete(v12, v11);
      }
    }
    else
    {
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"array", (const char *)v11);
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
  if ( v33 )
    Kerb3961::UninitializeCiphers(v10);
  return v6;
}

```

## disassembly

```asm
0x18000b3d0  mov     [rsp-38h+arg_0], rbx
0x18000b3d5  mov     [rsp-38h+arg_18], r9
0x18000b3da  mov     [rsp-38h+arg_8], rdx
0x18000b3df  push    rbp
0x18000b3e0  push    rsi
0x18000b3e1  push    rdi
0x18000b3e2  push    r12
0x18000b3e4  push    r13
0x18000b3e6  push    r14
0x18000b3e8  push    r15
0x18000b3ea  mov     rbp, rsp
0x18000b3ed  sub     rsp, 70h
0x18000b3f1  mov     rax, 8000000000000000h
0x18000b3fb  xor     r12d, r12d
0x18000b3fe  mov     rbx, r8
0x18000b401  mov     rdi, rdx
0x18000b404  mov     r14, rcx
0x18000b407  cmp     r8, rax
0x18000b40a  jnz     short loc_18000B41B
0x18000b40c  cmp     cs:?g_allowPolicyBypass@Kerb3961@@3_NA, r12b; bool Kerb3961::g_allowPolicyBypass
0x18000b413  jz      loc_18000B64D
0x18000b419  jmp     short loc_18000B42E
0x18000b41b  mov     rax, 8000000000000001h
0x18000b425  cmp     rbx, rax
0x18000b428  jz      loc_18000B607
0x18000b42e  lea     rdx, [rbp+arg_10]
0x18000b432  call    ?EnsureInitialization@CipherPolicyImpl@Kerb3961@@QEBA?AUInitializationSentinel@12@W4KeyUsage@2@@Z; Kerb3961::CipherPolicyImpl::EnsureInitialization(Kerb3961::KeyUsage)
0x18000b437  mov     r9b, 8
0x18000b43a  lea     rdx, [rbp+var_10]
0x18000b43e  mov     r8, rbx
0x18000b441  mov     rcx, r14
0x18000b444  call    ?GetOurPolicyScenarioForKeyUsage@CipherPolicyImpl@Kerb3961@@QEBA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@2@W4KeyPolicyQualifiers@2@@Z; Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(Kerb3961::KeyUsage,Kerb3961::KeyPolicyQualifiers)
0x18000b449  cmp     [rbp+var_B], r12b
0x18000b44d  jnz     short loc_18000B46E
0x18000b44f  lea     rcx, aScenariooptHas; "scenarioOpt.has_value()"
0x18000b456  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000b45b  mov     [rdi], r12
0x18000b45e  mov     [rdi+8], r12
0x18000b462  mov     dword ptr [rdi+10h], 0C000000Dh
0x18000b469  jmp     loc_18000B5FA
0x18000b46e  lea     rcx, [r14+10h]
0x18000b472  lea     rdx, [rbp+SRWLock]
0x18000b476  call    ?lock_shared@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_shared(void)
0x18000b47b  mov     rdx, [r14+50h]
0x18000b47f  lea     rcx, [rbp+var_20]
0x18000b483  call    ??$make_unique@$$BY0A@I$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@IU?$default_delete@$$BY0A@I@utl@@@0@_K@Z; utl::make_unique<uint [0],0>(unsigned __int64)
0x18000b488  mov     rsi, [rbp+var_20]
0x18000b48c  test    rsi, rsi
0x18000b48f  jz      loc_18000B5D1
0x18000b495  mov     edi, [rbp+var_10]
0x18000b498  lea     r13, [r14+38h]
0x18000b49c  mov     rbx, [r13+10h]
0x18000b4a0  mov     r15, r12
0x18000b4a3  cmp     rbx, r13
0x18000b4a6  jz      loc_18000B59B
0x18000b4ac  mov     r12, [rbx+20h]
0x18000b4b0  lea     rdx, [rbp+var_30]
0x18000b4b4  mov     al, [rbp+var_C]
0x18000b4b7  mov     rcx, r12
0x18000b4ba  mov     r8d, cs:?g_supportedEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A; Kerb3961::EncryptionTypeBitmask Kerb3961::g_supportedEncryptionTypes
0x18000b4c1  mov     [rbp+var_2C], al
0x18000b4c4  mov     rax, [r12]
0x18000b4c8  mov     [rbp+var_30], edi
0x18000b4cb  mov     rax, [rax+38h]
0x18000b4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4d4  test    al, al
0x18000b4d6  jnz     short loc_18000B4E6
0x18000b4d8  lea     rcx, aChecksumChecks_0; "checksum->ChecksumEnabledForUsage(keySc"...
0x18000b4df  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000b4e4  jmp     short loc_18000B530
0x18000b4e6  mov     al, [rbp+var_C]
0x18000b4e9  lea     r9, [rbp+var_20]
0x18000b4ed  mov     byte ptr [rbp+var_20+4], al
0x18000b4f0  lea     rdx, [rbp+var_40]
0x18000b4f4  mov     rax, [rbp+arg_20]
0x18000b4f8  mov     r8, r12
0x18000b4fb  mov     [rsp+70h+var_48], rax
0x18000b500  mov     rcx, r14
0x18000b503  mov     rax, [rbp+arg_18]
0x18000b507  mov     [rsp+70h+var_50], rax
0x18000b50c  mov     dword ptr [rbp+var_20], edi
0x18000b50f  call    ?ChecksumEnabledForPartners@CipherPolicyImpl@Kerb3961@@QEBA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@PEAUChecksumAlgorithm@2@UKeyPolicyScenario@2@AEBUCipherPartnerHandle@2@2@Z; Kerb3961::CipherPolicyImpl::ChecksumEnabledForPartners(Kerb3961::ChecksumAlgorithm *,Kerb3961::KeyPolicyScenario,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)
0x18000b514  cmp     dword ptr [rax], 0
0x18000b517  jl      short loc_18000B530
0x18000b519  mov     rax, [r12]
0x18000b51d  mov     rcx, r12
0x18000b520  mov     rax, [rax+68h]
0x18000b524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b529  mov     [rsi+r15*4], eax
0x18000b52d  inc     r15
0x18000b530  mov     rcx, [rbx+10h]
0x18000b534  lea     rdx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000b53b  cmp     rcx, rdx
0x18000b53e  jz      short loc_18000B55C
0x18000b540  cmp     rbx, rcx
0x18000b543  jnz     short loc_18000B547
0x18000b545  int     2Ch; Windows NT - assertion failure
0x18000b547  cmp     [rcx+8], rdx
0x18000b54b  jz      short loc_18000B593
0x18000b54d  mov     rax, [rcx+8]
0x18000b551  mov     rcx, rax
0x18000b554  cmp     [rax+8], rdx
0x18000b558  jnz     short loc_18000B54D
0x18000b55a  jmp     short loc_18000B593
0x18000b55c  mov     rax, [rbx]
0x18000b55f  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000b563  mov     rcx, rax
0x18000b566  cmp     [rax+10h], rbx
0x18000b56a  jnz     short loc_18000B593
0x18000b56c  cmp     [rax], rbx
0x18000b56f  jz      short loc_18000B593
0x18000b571  mov     rcx, [rax]
0x18000b574  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000b578  cmp     [rcx+10h], rax
0x18000b57c  jnz     short loc_18000B593
0x18000b57e  cmp     [rcx], rax
0x18000b581  jz      short loc_18000B593
0x18000b583  mov     rax, rcx
0x18000b586  mov     rcx, [rcx]
0x18000b589  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000b58d  cmp     [rcx+10h], rax
0x18000b591  jz      short loc_18000B583
0x18000b593  mov     rbx, rcx
0x18000b596  jmp     loc_18000B4A3
0x18000b59b  mov     rdi, [rbp+arg_8]
0x18000b59f  xor     r12d, r12d
0x18000b5a2  test    r15, r15
0x18000b5a5  jnz     short loc_18000B5C4
0x18000b5a7  mov     [rdi], r12
0x18000b5aa  mov     [rdi+8], r12
0x18000b5ae  mov     dword ptr [rdi+10h], 0C00002FDh
0x18000b5b5  test    rsi, rsi
0x18000b5b8  jz      short loc_18000B5EB
0x18000b5ba  mov     rcx, rsi; void *
0x18000b5bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b5c2  jmp     short loc_18000B5EB
0x18000b5c4  mov     [rdi], r15
0x18000b5c7  mov     [rdi+8], rsi
0x18000b5cb  mov     [rdi+10h], r12d
0x18000b5cf  jmp     short loc_18000B5EB
0x18000b5d1  lea     rcx, aArray; "array"
0x18000b5d8  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000b5dd  mov     [rdi], r12
0x18000b5e0  mov     [rdi+8], r12
0x18000b5e4  mov     dword ptr [rdi+10h], 0C0000017h
0x18000b5eb  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000b5ef  test    rcx, rcx
0x18000b5f2  jz      short loc_18000B5FA
0x18000b5f4  call    cs:__imp_ReleaseSRWLockShared
0x18000b5fa  cmp     [rbp+arg_10], r12b
0x18000b5fe  jz      short loc_18000B632
0x18000b600  call    ?UninitializeCiphers@Kerb3961@@YAXXZ; Kerb3961::UninitializeCiphers(void)
0x18000b605  jmp     short loc_18000B632
0x18000b607  lea     rcx, aKeyusageKeyusa; "keyUsage != KeyUsage::AlwaysBlocked"
0x18000b60e  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000b613  mov     edx, 0C00002FDh; char *
0x18000b618  lea     rcx, aCheckkeyusageK; "CheckKeyUsage(keyUsage)"
0x18000b61f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000b624  mov     [rdi], r12
0x18000b627  mov     [rdi+8], r12
0x18000b62b  mov     dword ptr [rdi+10h], 0C00002FDh
0x18000b632  mov     rbx, [rsp+70h+arg_0]
0x18000b63a  mov     rax, rdi
0x18000b63d  add     rsp, 70h
0x18000b641  pop     r15
0x18000b643  pop     r14
0x18000b645  pop     r13
0x18000b647  pop     r12
0x18000b649  pop     rdi
0x18000b64a  pop     rsi
0x18000b64b  pop     rbp
0x18000b64c  retn
0x18000b64d  lea     rcx, aNonTestCodeIsA; "Non test code is attempting to bypass p"...
0x18000b654  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
