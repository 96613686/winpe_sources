# Kerb3961::CipherPolicyImpl::SelectCipher(Kerb3961::KeyUsage,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)

- ea: `0x18000db90`
- end: `0x18000dd51`
- name: `?SelectCipher@CipherPolicyImpl@Kerb3961@@UEBA?AU?$ReturnType@U?$ResultAdapter@PEAUEncryptionAlgorithm@Kerb3961@@@Kerb3961@@$1??$SingleGetter@U?$ResultAdapter@PEAUEncryptionAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@U?$ResultAdapter@PEAUEncryptionAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEAU32@AEAU12@@Z@2@W4KeyUsage@2@AEBUCipherPartnerHandle@2@1@Z`
- size: `449`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callees

- `0x180002c64`
- `0x180002fc0`
- `0x180003380`
- `0x1800033f4`
- `0x180003610`
- `0x180003da0`
- `0x18000ae18`
- `0x18000b024`
- `0x18000bfc8`
- `0x18000db90`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000dcef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000dcef`

## string_xrefs

- `0x18000dd44`: `Non test code is attempting to bypass policy`

## pseudocode

```c
__int64 __fastcall Kerb3961::CipherPolicyImpl::SelectCipher(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v8; // r9
  const char *v9; // rdx
  Kerb3961 *v10; // rcx
  bool v11; // zf
  int v12; // r15d
  char v13; // r12
  __int64 v14; // r13
  __int64 v15; // rax
  __int64 v16; // rdi
  const char *v17; // rdx
  int v18; // r8d
  char v20; // [rsp+30h] [rbp-40h] BYREF
  int v21; // [rsp+40h] [rbp-30h] BYREF
  char v22; // [rsp+44h] [rbp-2Ch]
  int v23; // [rsp+50h] [rbp-20h] BYREF
  char v24; // [rsp+54h] [rbp-1Ch]
  char v25; // [rsp+55h] [rbp-1Bh]
  __int64 v26; // [rsp+60h] [rbp-10h] BYREF
  PSRWLOCK SRWLock; // [rsp+68h] [rbp-8h] BYREF
  char v28; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v29; // [rsp+C8h] [rbp+58h]

  v29 = a4;
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
      v18);
    *(_QWORD *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -1073741059;
    return a2;
  }
  Kerb3961::CipherPolicyImpl::EnsureInitialization(a1, &v28, a3);
  LOBYTE(v8) = 8;
  Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(a1, &v23, a3, v8);
  if ( v25 )
  {
    v12 = v23;
    v13 = v24;
    wil::srwlock::lock_shared(a1 + 16, &SRWLock);
    v14 = a5;
    v15 = *(_QWORD *)(a1 + 40);
    v26 = v15;
    while ( v15 != a1 + 24 )
    {
      v16 = *(_QWORD *)(v15 + 32);
      v21 = v12;
      v22 = v13;
      if ( (*(unsigned __int8 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v16 + 80LL))(
             v16,
             &v21,
             Kerb3961::g_supportedEncryptionTypes) )
      {
        v23 = v12;
        v24 = v13;
        if ( *(int *)Kerb3961::CipherPolicyImpl::CipherEnabledForPartners(
                       a1,
                       (unsigned int)&v20,
                       v16,
                       (unsigned int)&v23,
                       v29,
                       v14) >= 0 )
        {
          *(_QWORD *)a2 = v16;
          *(_DWORD *)(a2 + 8) = 0;
          goto LABEL_15;
        }
      }
      else
      {
        Kerb3961::Logging::Verify::ConditionFailed(
          (Kerb3961::Logging::Verify *)"cipher->CipherEnabledForUsage(keyScenario, g_supportedEncryptionTypes)",
          v17);
      }
      utl::_TreeConstIt<utl::pair<unsigned int const,Kerb3961::EncryptionAlgorithm *>>::operator++(&v26);
      v15 = v26;
    }
    *(_QWORD *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -1073741059;
LABEL_15:
    v10 = (Kerb3961 *)SRWLock;
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    v11 = v28 == 0;
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"scenarioOpt.has_value()", v9);
    v11 = v28 == 0;
    *(_QWORD *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -1073741811;
  }
  if ( !v11 )
    Kerb3961::UninitializeCiphers(v10);
  return a2;
}

```

## disassembly

```asm
0x18000db90  mov     [rsp-38h+arg_0], rbx
0x18000db95  mov     [rsp-38h+arg_18], r9
0x18000db9a  push    rbp
0x18000db9b  push    rsi
0x18000db9c  push    rdi
0x18000db9d  push    r12
0x18000db9f  push    r13
0x18000dba1  push    r14
0x18000dba3  push    r15
0x18000dba5  mov     rbp, rsp
0x18000dba8  sub     rsp, 70h
0x18000dbac  mov     rax, 8000000000000000h
0x18000dbb6  xor     r14d, r14d
0x18000dbb9  mov     rdi, r8
0x18000dbbc  mov     rbx, rdx
0x18000dbbf  mov     rsi, rcx
0x18000dbc2  cmp     r8, rax
0x18000dbc5  jnz     short loc_18000DBD6
0x18000dbc7  cmp     cs:?g_allowPolicyBypass@Kerb3961@@3_NA, r14b; bool Kerb3961::g_allowPolicyBypass
0x18000dbce  jz      loc_18000DD44
0x18000dbd4  jmp     short loc_18000DBE9
0x18000dbd6  mov     rax, 8000000000000001h
0x18000dbe0  cmp     rdi, rax
0x18000dbe3  jz      loc_18000DD02
0x18000dbe9  lea     rdx, [rbp+arg_10]
0x18000dbed  call    ?EnsureInitialization@CipherPolicyImpl@Kerb3961@@QEBA?AUInitializationSentinel@12@W4KeyUsage@2@@Z; Kerb3961::CipherPolicyImpl::EnsureInitialization(Kerb3961::KeyUsage)
0x18000dbf2  mov     r9b, 8
0x18000dbf5  lea     rdx, [rbp+var_20]
0x18000dbf9  mov     r8, rdi
0x18000dbfc  mov     rcx, rsi
0x18000dbff  call    ?GetOurPolicyScenarioForKeyUsage@CipherPolicyImpl@Kerb3961@@QEBA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@2@W4KeyPolicyQualifiers@2@@Z; Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(Kerb3961::KeyUsage,Kerb3961::KeyPolicyQualifiers)
0x18000dc04  cmp     [rbp+var_1B], r14b
0x18000dc08  jnz     short loc_18000DC29
0x18000dc0a  lea     rcx, aScenariooptHas; "scenarioOpt.has_value()"
0x18000dc11  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000dc16  cmp     [rbp+arg_10], r14b
0x18000dc1a  mov     [rbx], r14
0x18000dc1d  mov     dword ptr [rbx+8], 0C000000Dh
0x18000dc24  jmp     loc_18000DCF9
0x18000dc29  mov     r15d, [rbp+var_20]
0x18000dc2d  lea     rcx, [rsi+10h]
0x18000dc31  mov     r12b, [rbp+var_1C]
0x18000dc35  lea     rdx, [rbp+SRWLock]
0x18000dc39  call    ?lock_shared@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_shared(void)
0x18000dc3e  mov     r13, [rbp+arg_20]
0x18000dc42  lea     r14, [rsi+18h]
0x18000dc46  mov     rax, [r14+10h]
0x18000dc4a  mov     [rbp+var_10], rax
0x18000dc4e  cmp     rax, r14
0x18000dc51  jz      loc_18000DCD8
0x18000dc57  mov     rdi, [rax+20h]
0x18000dc5b  lea     rdx, [rbp+var_30]
0x18000dc5f  mov     r8d, cs:?g_supportedEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A; Kerb3961::EncryptionTypeBitmask Kerb3961::g_supportedEncryptionTypes
0x18000dc66  mov     rcx, rdi
0x18000dc69  mov     [rbp+var_30], r15d
0x18000dc6d  mov     [rbp+var_2C], r12b
0x18000dc71  mov     rax, [rdi]
0x18000dc74  mov     rax, [rax+50h]
0x18000dc78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc7d  test    al, al
0x18000dc7f  jnz     short loc_18000DC8F
0x18000dc81  lea     rcx, aCipherCipheren; "cipher->CipherEnabledForUsage(keyScenar"...
0x18000dc88  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000dc8d  jmp     short loc_18000DCBD
0x18000dc8f  mov     rax, [rbp+arg_18]
0x18000dc93  lea     r9, [rbp+var_20]
0x18000dc97  mov     [rsp+70h+var_48], r13
0x18000dc9c  lea     rdx, [rbp+var_40]
0x18000dca0  mov     r8, rdi
0x18000dca3  mov     [rsp+70h+var_50], rax
0x18000dca8  mov     rcx, rsi
0x18000dcab  mov     [rbp+var_20], r15d
0x18000dcaf  mov     [rbp+var_1C], r12b
0x18000dcb3  call    ?CipherEnabledForPartners@CipherPolicyImpl@Kerb3961@@QEBA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@PEAUEncryptionAlgorithm@2@UKeyPolicyScenario@2@AEBUCipherPartnerHandle@2@2@Z; Kerb3961::CipherPolicyImpl::CipherEnabledForPartners(Kerb3961::EncryptionAlgorithm *,Kerb3961::KeyPolicyScenario,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)
0x18000dcb8  cmp     dword ptr [rax], 0
0x18000dcbb  jge     short loc_18000DCCC
0x18000dcbd  lea     rcx, [rbp+var_10]
0x18000dcc1  call    ??E?$_TreeConstIt@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>::operator++(void)
0x18000dcc6  mov     rax, [rbp+var_10]
0x18000dcca  jmp     short loc_18000DC4E
0x18000dccc  mov     [rbx], rdi
0x18000dccf  mov     dword ptr [rbx+8], 0
0x18000dcd6  jmp     short loc_18000DCE6
0x18000dcd8  mov     qword ptr [rbx], 0
0x18000dcdf  mov     dword ptr [rbx+8], 0C00002FDh
0x18000dce6  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000dcea  test    rcx, rcx
0x18000dced  jz      short loc_18000DCF5
0x18000dcef  call    cs:__imp_ReleaseSRWLockShared
0x18000dcf5  cmp     [rbp+arg_10], 0
0x18000dcf9  jz      short loc_18000DD29
0x18000dcfb  call    ?UninitializeCiphers@Kerb3961@@YAXXZ; Kerb3961::UninitializeCiphers(void)
0x18000dd00  jmp     short loc_18000DD29
0x18000dd02  lea     rcx, aKeyusageKeyusa; "keyUsage != KeyUsage::AlwaysBlocked"
0x18000dd09  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000dd0e  mov     edx, 0C00002FDh; char *
0x18000dd13  lea     rcx, aCheckkeyusageK; "CheckKeyUsage(keyUsage)"
0x18000dd1a  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000dd1f  mov     [rbx], r14
0x18000dd22  mov     dword ptr [rbx+8], 0C00002FDh
0x18000dd29  mov     rax, rbx
0x18000dd2c  mov     rbx, [rsp+70h+arg_0]
0x18000dd34  add     rsp, 70h
0x18000dd38  pop     r15
0x18000dd3a  pop     r14
0x18000dd3c  pop     r13
0x18000dd3e  pop     r12
0x18000dd40  pop     rdi
0x18000dd41  pop     rsi
0x18000dd42  pop     rbp
0x18000dd43  retn
0x18000dd44  lea     rcx, aNonTestCodeIsA; "Non test code is attempting to bypass p"...
0x18000dd4b  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
