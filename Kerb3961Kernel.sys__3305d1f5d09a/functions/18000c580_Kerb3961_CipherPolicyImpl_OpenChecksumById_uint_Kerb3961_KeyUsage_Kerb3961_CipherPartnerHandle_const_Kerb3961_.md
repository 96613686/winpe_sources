# Kerb3961::CipherPolicyImpl::OpenChecksumById(uint,Kerb3961::KeyUsage,Kerb3961::CipherPartnerHandle const &,Kerb3961::CipherPartnerHandle const &)

- ea: `0x18000c580`
- end: `0x18000c6fb`
- name: `?OpenChecksumById@CipherPolicyImpl@Kerb3961@@UEBA?AU?$ReturnType@U?$ResultAdapter@PEAUChecksumAlgorithm@Kerb3961@@@Kerb3961@@$1??$SingleGetter@U?$ResultAdapter@PEAUChecksumAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@U?$ResultAdapter@PEAUChecksumAlgorithm@Kerb3961@@@Kerb3961@@$07@2@YAAEAU32@AEAU12@@Z@2@IW4KeyUsage@2@AEBUCipherPartnerHandle@2@1@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000bc30`

## callees

- `0x180006c80`
- `0x18000a798`
- `0x18000ba20`
- `0x18000bb20`
- `0x18000c580`
- `0x180010e6c`
- `0x180011760`
- `0x1800118cc`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18000c6c1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18000c6c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000c6cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000c6cd`

## pseudocode

```c
__int64 Kerb3961::CipherPolicyImpl::OpenChecksumById(__int64 a1, __int64 a2, unsigned int a3, ...)
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
    if ( (_UNKNOWN **)qword_18001A3E0 == &Kerb3961::g_checksums )
      goto LABEL_16;
    v8 = (char *)Kerb3961::g_checksums;
    v9 = &Kerb3961::g_checksums;
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
    if ( v9 == &Kerb3961::g_checksums || a3 < *((_DWORD *)v9 + 6) )
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
          (Kerb3961::Logging::Verify *)"ChecksumEnabledForUs(checksum, keyScenario)",
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
0x18000c580  mov     [rsp-18h+arg_0], rbx
0x18000c585  mov     [rsp-18h+arg_8], rsi
0x18000c58a  mov     [rsp-18h+arg_18], r9
0x18000c58f  push    rbp
0x18000c590  push    rdi
0x18000c591  push    r14
0x18000c593  mov     rbp, rsp
0x18000c596  sub     rsp, 40h
0x18000c59a  mov     rbx, rdx
0x18000c59d  mov     r14, rcx
0x18000c5a0  lea     rdx, [rbp+arg_18]
0x18000c5a4  mov     esi, r8d
0x18000c5a7  lea     rcx, [rbp+var_1C]
0x18000c5ab  call    ?CheckKeyUsage@CipherPolicyImpl@Kerb3961@@SA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEAW4KeyUsage@2@@Z; Kerb3961::CipherPolicyImpl::CheckKeyUsage(Kerb3961::KeyUsage &)
0x18000c5b0  mov     edi, [rax]
0x18000c5b2  test    edi, edi
0x18000c5b4  jns     short loc_18000C5D3
0x18000c5b6  mov     edx, edi; char *
0x18000c5b8  lea     rcx, aCheckkeyusageK; "CheckKeyUsage(keyUsage)"
0x18000c5bf  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000c5c4  mov     qword ptr [rbx], 0
0x18000c5cb  mov     [rbx+8], edi
0x18000c5ce  jmp     loc_18000C6E4
0x18000c5d3  lea     rdx, [rbp+var_20]
0x18000c5d7  mov     rcx, r14
0x18000c5da  call    ?EnsureInitialization@CipherPolicyImpl@Kerb3961@@QEBA?AUInitializationSentinel@12@W4KeyUsage@2@@Z; Kerb3961::CipherPolicyImpl::EnsureInitialization(Kerb3961::KeyUsage)
0x18000c5df  lea     rdx, [rbp+var_10]
0x18000c5e3  lea     rcx, ?g_cipherLock@Kerb3961@@3UCommonLock@1@A; Kerb3961::CommonLock Kerb3961::g_cipherLock
0x18000c5ea  call    ?acquire_shared@push_lock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_KP6AXPEA_K@_E$1?release_push_lock_shared@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEA_KPEA_K$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x18000c5ef  lea     r8, ?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x18000c5f6  cmp     cs:qword_18001A3E0, r8
0x18000c5fd  jz      loc_18000C6A8
0x18000c603  mov     rax, cs:?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x18000c60a  mov     rcx, r8
0x18000c60d  cmp     [rax+18h], esi
0x18000c610  jnb     short loc_18000C619
0x18000c612  mov     edx, 10h
0x18000c617  jmp     short loc_18000C621
0x18000c619  mov     rcx, rax
0x18000c61c  mov     edx, 8
0x18000c621  mov     rax, [rdx+rax]
0x18000c625  lea     rdx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000c62c  cmp     rax, rdx
0x18000c62f  jnz     short loc_18000C60D
0x18000c631  cmp     rcx, r8
0x18000c634  jz      short loc_18000C6A8
0x18000c636  cmp     esi, [rcx+18h]
0x18000c639  jb      short loc_18000C6A8
0x18000c63b  mov     rdx, [rbp+arg_18]
0x18000c63f  mov     rax, 8000000000000000h
0x18000c649  cmp     rdx, rax
0x18000c64c  jz      short loc_18000C698
0x18000c64e  lea     rcx, [rbp+var_1C]
0x18000c652  call    ?GetScenarioForKeyUsage@Kerb3961@@YA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@1@@Z; Kerb3961::GetScenarioForKeyUsage(Kerb3961::KeyUsage)
0x18000c657  cmp     [rbp+var_17], 0
0x18000c65b  jz      short loc_18000C67C
0x18000c65d  mov     edi, 0C0000001h
0x18000c662  lea     rcx, aChecksumenable; "ChecksumEnabledForUs(checksum, keyScena"...
0x18000c669  mov     edx, edi; char *
0x18000c66b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000c670  mov     qword ptr [rbx], 0
0x18000c677  mov     [rbx+8], edi
0x18000c67a  jmp     short loc_18000C6B6
0x18000c67c  lea     rcx, aScenariooptHas; "scenarioOpt.has_value()"
0x18000c683  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000c688  mov     qword ptr [rbx], 0
0x18000c68f  mov     dword ptr [rbx+8], 0C000000Dh
0x18000c696  jmp     short loc_18000C6B6
0x18000c698  mov     rax, [rcx+20h]
0x18000c69c  mov     [rbx], rax
0x18000c69f  mov     dword ptr [rbx+8], 0
0x18000c6a6  jmp     short loc_18000C6B6
0x18000c6a8  mov     qword ptr [rbx], 0
0x18000c6af  mov     dword ptr [rbx+8], 0C00002FDh
0x18000c6b6  mov     rcx, [rbp+var_10]
0x18000c6ba  test    rcx, rcx
0x18000c6bd  jz      short loc_18000C6D9
0x18000c6bf  xor     edx, edx
0x18000c6c1  call    cs:__imp_ExReleasePushLockSharedEx
0x18000c6c8  nop     dword ptr [rax+rax+00h]
0x18000c6cd  call    cs:__imp_KeLeaveCriticalRegion
0x18000c6d4  nop     dword ptr [rax+rax+00h]
0x18000c6d9  cmp     [rbp+var_20], 0
0x18000c6dd  jz      short loc_18000C6E4
0x18000c6df  call    ?UninitializeCiphers@Kerb3961@@YAXXZ; Kerb3961::UninitializeCiphers(void)
0x18000c6e4  mov     rsi, [rsp+40h+arg_8]
0x18000c6e9  mov     rax, rbx
0x18000c6ec  mov     rbx, [rsp+40h+arg_0]
0x18000c6f1  add     rsp, 40h
0x18000c6f5  pop     r14
0x18000c6f7  pop     rdi
0x18000c6f8  pop     rbp
0x18000c6f9  retn
```
