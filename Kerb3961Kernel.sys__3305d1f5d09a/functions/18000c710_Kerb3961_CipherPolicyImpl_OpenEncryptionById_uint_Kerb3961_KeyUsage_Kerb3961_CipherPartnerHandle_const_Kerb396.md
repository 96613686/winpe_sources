# Kerb3961::CipherPolicyImpl::OpenEncryptionById(uint,Kerb3961::KeyUsage,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)

- ea: `0x18000c710`
- end: `0x18000c88b`
- name: `?OpenEncryptionById@CipherPolicyImpl@Kerb3961@@UEBA?AU?$ReturnType@U?$ResultAdapter@PEAUEncryptionAlgorithm@Kerb3961@@@Kerb3961@@$1??$SingleGetter@U?$ResultAdapter@PEAUEncryptionAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@U?$ResultAdapter@PEAUEncryptionAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEAU32@AEAU12@@Z@2@IW4KeyUsage@2@AEBUCipherPartnerHandle@2@1@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000c080`

## callees

- `0x180006c80`
- `0x18000a798`
- `0x18000ba20`
- `0x18000bb20`
- `0x18000c710`
- `0x180010e6c`
- `0x180011760`
- `0x1800118cc`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18000c851`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18000c851`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000c85d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000c85d`

## pseudocode

```c
__int64 Kerb3961::CipherPolicyImpl::OpenEncryptionById(__int64 a1, __int64 a2, unsigned int a3, ...)
{
  int v6; // edi
  int v7; // r8d
  char *v8; // rax
  _UNKNOWN **v9; // rcx
  __int64 v10; // rdx
  const char *v11; // rdx
  int v12; // r8d
  Kerb3961 *v13; // rcx
  _BYTE v15[4]; // [rsp+20h] [rbp-20h] BYREF
  int v16; // [rsp+24h] [rbp-1Ch] BYREF
  char v17; // [rsp+29h] [rbp-17h]
  Kerb3961 *v18; // [rsp+30h] [rbp-10h] BYREF
  __int64 v19; // [rsp+78h] [rbp+38h] BYREF
  va_list va; // [rsp+78h] [rbp+38h]
  va_list va1; // [rsp+80h] [rbp+40h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v19 = va_arg(va1, _QWORD);
  v6 = *Kerb3961::CipherPolicyImpl::CheckKeyUsage(&v16, (__int64 *)va);
  if ( v6 >= 0 )
  {
    Kerb3961::CipherPolicyImpl::EnsureInitialization(a1, v15);
    wil::push_lock::acquire_shared(&Kerb3961::g_cipherLock, &v18);
    if ( (_UNKNOWN **)qword_18001A3C0 == &Kerb3961::g_encryptions )
      goto LABEL_16;
    v8 = (char *)Kerb3961::g_encryptions;
    v9 = &Kerb3961::g_encryptions;
    do
    {
      if ( *((_DWORD *)v8 + 6) >= a3 )
      {
        v9 = (_UNKNOWN **)v8;
        v10 = 8;
      }
      else
      {
        v10 = 16;
      }
      v8 = *(char **)&v8[v10];
    }
    while ( v8 != (char *)&utl::_TreeSentinel );
    if ( v9 == &Kerb3961::g_encryptions || a3 < *((_DWORD *)v9 + 6) )
    {
LABEL_16:
      *(_QWORD *)a2 = 0;
      *(_DWORD *)(a2 + 8) = -1073741059;
    }
    else if ( v19 == 0x8000000000000000uLL )
    {
      *(_QWORD *)a2 = v9[4];
      *(_DWORD *)(a2 + 8) = 0;
    }
    else
    {
      Kerb3961::GetScenarioForKeyUsage(&v16);
      if ( v17 )
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"CipherEnabledForUs(encryption, keyScenario)",
          (const char *)0xC0000001LL,
          v12);
        *(_QWORD *)a2 = 0;
        *(_DWORD *)(a2 + 8) = -1073741823;
      }
      else
      {
        Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"scenarioOpt.has_value()", v11);
        *(_QWORD *)a2 = 0;
        *(_DWORD *)(a2 + 8) = -1073741811;
      }
    }
    v13 = v18;
    if ( v18 )
    {
      ExReleasePushLockSharedEx(v18, 0);
      KeLeaveCriticalRegion();
    }
    if ( v15[0] )
      Kerb3961::UninitializeCiphers(v13);
  }
  else
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"CheckKeyUsage(keyUsage)",
      (const char *)(unsigned int)v6,
      v7);
    *(_QWORD *)a2 = 0;
    *(_DWORD *)(a2 + 8) = v6;
  }
  return a2;
}

```

## disassembly

```asm
0x18000c710  mov     [rsp-18h+arg_0], rbx
0x18000c715  mov     [rsp-18h+arg_8], rsi
0x18000c71a  mov     [rsp-18h+arg_18], r9
0x18000c71f  push    rbp
0x18000c720  push    rdi
0x18000c721  push    r14
0x18000c723  mov     rbp, rsp
0x18000c726  sub     rsp, 40h
0x18000c72a  mov     rbx, rdx
0x18000c72d  mov     r14, rcx
0x18000c730  lea     rdx, [rbp+arg_18]
0x18000c734  mov     esi, r8d
0x18000c737  lea     rcx, [rbp+var_1C]
0x18000c73b  call    ?CheckKeyUsage@CipherPolicyImpl@Kerb3961@@SA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEAW4KeyUsage@2@@Z; Kerb3961::CipherPolicyImpl::CheckKeyUsage(Kerb3961::KeyUsage &)
0x18000c740  mov     edi, [rax]
0x18000c742  test    edi, edi
0x18000c744  jns     short loc_18000C763
0x18000c746  mov     edx, edi; char *
0x18000c748  lea     rcx, aCheckkeyusageK; "CheckKeyUsage(keyUsage)"
0x18000c74f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000c754  mov     qword ptr [rbx], 0
0x18000c75b  mov     [rbx+8], edi
0x18000c75e  jmp     loc_18000C874
0x18000c763  lea     rdx, [rbp+var_20]
0x18000c767  mov     rcx, r14
0x18000c76a  call    ?EnsureInitialization@CipherPolicyImpl@Kerb3961@@QEBA?AUInitializationSentinel@12@W4KeyUsage@2@@Z; Kerb3961::CipherPolicyImpl::EnsureInitialization(Kerb3961::KeyUsage)
0x18000c76f  lea     rdx, [rbp+var_10]
0x18000c773  lea     rcx, ?g_cipherLock@Kerb3961@@3UCommonLock@1@A; Kerb3961::CommonLock Kerb3961::g_cipherLock
0x18000c77a  call    ?acquire_shared@push_lock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_KP6AXPEA_K@_E$1?release_push_lock_shared@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEA_KPEA_K$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x18000c77f  lea     r8, ?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x18000c786  cmp     cs:qword_18001A3C0, r8
0x18000c78d  jz      loc_18000C838
0x18000c793  mov     rax, cs:?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x18000c79a  mov     rcx, r8
0x18000c79d  cmp     [rax+18h], esi
0x18000c7a0  jnb     short loc_18000C7A9
0x18000c7a2  mov     edx, 10h
0x18000c7a7  jmp     short loc_18000C7B1
0x18000c7a9  mov     rcx, rax
0x18000c7ac  mov     edx, 8
0x18000c7b1  mov     rax, [rdx+rax]
0x18000c7b5  lea     rdx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000c7bc  cmp     rax, rdx
0x18000c7bf  jnz     short loc_18000C79D
0x18000c7c1  cmp     rcx, r8
0x18000c7c4  jz      short loc_18000C838
0x18000c7c6  cmp     esi, [rcx+18h]
0x18000c7c9  jb      short loc_18000C838
0x18000c7cb  mov     rdx, [rbp+arg_18]
0x18000c7cf  mov     rax, 8000000000000000h
0x18000c7d9  cmp     rdx, rax
0x18000c7dc  jz      short loc_18000C828
0x18000c7de  lea     rcx, [rbp+var_1C]
0x18000c7e2  call    ?GetScenarioForKeyUsage@Kerb3961@@YA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@1@@Z; Kerb3961::GetScenarioForKeyUsage(Kerb3961::KeyUsage)
0x18000c7e7  cmp     [rbp+var_17], 0
0x18000c7eb  jz      short loc_18000C80C
0x18000c7ed  mov     edi, 0C0000001h
0x18000c7f2  lea     rcx, aCipherenabledf; "CipherEnabledForUs(encryption, keyScena"...
0x18000c7f9  mov     edx, edi; char *
0x18000c7fb  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000c800  mov     qword ptr [rbx], 0
0x18000c807  mov     [rbx+8], edi
0x18000c80a  jmp     short loc_18000C846
0x18000c80c  lea     rcx, aScenariooptHas; "scenarioOpt.has_value()"
0x18000c813  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000c818  mov     qword ptr [rbx], 0
0x18000c81f  mov     dword ptr [rbx+8], 0C000000Dh
0x18000c826  jmp     short loc_18000C846
0x18000c828  mov     rax, [rcx+20h]
0x18000c82c  mov     [rbx], rax
0x18000c82f  mov     dword ptr [rbx+8], 0
0x18000c836  jmp     short loc_18000C846
0x18000c838  mov     qword ptr [rbx], 0
0x18000c83f  mov     dword ptr [rbx+8], 0C00002FDh
0x18000c846  mov     rcx, [rbp+var_10]
0x18000c84a  test    rcx, rcx
0x18000c84d  jz      short loc_18000C869
0x18000c84f  xor     edx, edx
0x18000c851  call    cs:__imp_ExReleasePushLockSharedEx
0x18000c858  nop     dword ptr [rax+rax+00h]
0x18000c85d  call    cs:__imp_KeLeaveCriticalRegion
0x18000c864  nop     dword ptr [rax+rax+00h]
0x18000c869  cmp     [rbp+var_20], 0
0x18000c86d  jz      short loc_18000C874
0x18000c86f  call    ?UninitializeCiphers@Kerb3961@@YAXXZ; Kerb3961::UninitializeCiphers(void)
0x18000c874  mov     rsi, [rsp+40h+arg_8]
0x18000c879  mov     rax, rbx
0x18000c87c  mov     rbx, [rsp+40h+arg_0]
0x18000c881  add     rsp, 40h
0x18000c885  pop     r14
0x18000c887  pop     rdi
0x18000c888  pop     rbp
0x18000c889  retn
```
