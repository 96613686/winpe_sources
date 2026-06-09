# Kerb3961::CipherPolicyImpl::EnsureInitialization(Kerb3961::KeyUsage)

- ea: `0x18000b024`
- end: `0x18000b0e4`
- name: `?EnsureInitialization@CipherPolicyImpl@Kerb3961@@QEBA?AUInitializationSentinel@12@W4KeyUsage@2@@Z`
- size: `192`
- prototype: `_BYTE *__fastcall(Kerb3961::CipherPolicyImpl *, _BYTE *, __int64)`
- caller_count: `12`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b3d0`
- `0x18000b660`
- `0x18000b750`
- `0x18000b920`
- `0x18000ba20`
- `0x18000c060`
- `0x18000cdb0`
- `0x18000cfd0`
- `0x18000d510`
- `0x18000d6e0`
- `0x18000d960`
- `0x18000db90`

## callees

- `0x1800033f4`
- `0x180003d70`
- `0x18000b024`
- `0x18000bfc8`
- `0x18000c400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b09c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b0ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b09c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b0ae`

## string_xrefs

- `0x18000b0ca`: `Only key usages of compute && store are eligible for last-resort initialization`

## pseudocode

```c
_BYTE *__fastcall Kerb3961::CipherPolicyImpl::EnsureInitialization(
        Kerb3961::CipherPolicyImpl *a1,
        _BYTE *a2,
        __int64 a3)
{
  const unsigned __int16 *v6; // rdx
  char v7; // r9
  const unsigned __int16 *v8; // rdx
  RTL_SRWLOCK *v9; // rcx
  char v11; // [rsp+30h] [rbp+8h] BYREF
  char v12; // [rsp+31h] [rbp+9h]
  char v13; // [rsp+35h] [rbp+Dh]
  PSRWLOCK SRWLock; // [rsp+48h] [rbp+20h] BYREF

  if ( *((_DWORD *)a1 + 2) )
  {
LABEL_10:
    *a2 = 0;
    return a2;
  }
  wil::srwlock::lock_exclusive((char *)a1 + 16, &SRWLock);
  if ( *((_DWORD *)a1 + 2) )
  {
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    goto LABEL_10;
  }
  Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(a1, &v11, a3, 0);
  if ( v13 == v7 || (unsigned __int8)(v12 - 1) > 1u )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"Only key usages of compute && store are eligible for last-resort initialization",
      v6);
  if ( *(int *)Kerb3961::CipherPolicyImpl::InitializeCiphersNoLock(a1) < 0 )
    Kerb3961::ConsistencyFail((Kerb3961 *)L"Last-resort initialization failed", v8);
  v9 = SRWLock;
  *a2 = 1;
  if ( v9 )
    ReleaseSRWLockExclusive(v9);
  return a2;
}

```

## disassembly

```asm
0x18000b024  mov     [rsp+arg_8], rbx
0x18000b029  mov     [rsp+arg_10], rsi
0x18000b02e  push    rdi
0x18000b02f  sub     rsp, 20h
0x18000b033  cmp     dword ptr [rcx+8], 0
0x18000b037  mov     rsi, r8
0x18000b03a  mov     rbx, rdx
0x18000b03d  mov     rdi, rcx
0x18000b040  jnz     short loc_18000B0B4
0x18000b042  add     rcx, 10h
0x18000b046  lea     rdx, [rsp+28h+SRWLock]
0x18000b04b  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x18000b050  cmp     dword ptr [rdi+8], 0
0x18000b054  jnz     short loc_18000B0A4
0x18000b056  xor     r9d, r9d
0x18000b059  lea     rdx, [rsp+28h+arg_0]
0x18000b05e  mov     r8, rsi
0x18000b061  mov     rcx, rdi
0x18000b064  call    ?GetOurPolicyScenarioForKeyUsage@CipherPolicyImpl@Kerb3961@@QEBA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@2@W4KeyPolicyQualifiers@2@@Z; Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(Kerb3961::KeyUsage,Kerb3961::KeyPolicyQualifiers)
0x18000b069  cmp     [rsp+28h+arg_5], r9b
0x18000b06e  jz      short loc_18000B0CA
0x18000b070  mov     al, [rsp+28h+arg_1]
0x18000b074  dec     al
0x18000b076  cmp     al, 1
0x18000b078  ja      short loc_18000B0CA
0x18000b07a  xor     r8d, r8d
0x18000b07d  lea     rdx, [rsp+28h+arg_0]
0x18000b082  mov     rcx, rdi; this
0x18000b085  call    ?InitializeCiphersNoLock@CipherPolicyImpl@Kerb3961@@QEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@PEAUHKEY__@@@Z; Kerb3961::CipherPolicyImpl::InitializeCiphersNoLock(HKEY__ *)
0x18000b08a  cmp     dword ptr [rax], 0
0x18000b08d  jl      short loc_18000B0D7
0x18000b08f  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x18000b094  mov     byte ptr [rbx], 1
0x18000b097  test    rcx, rcx
0x18000b09a  jz      short loc_18000B0B7
0x18000b09c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b0a2  jmp     short loc_18000B0B7
0x18000b0a4  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x18000b0a9  test    rcx, rcx
0x18000b0ac  jz      short loc_18000B0B4
0x18000b0ae  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b0b4  mov     byte ptr [rbx], 0
0x18000b0b7  mov     rsi, [rsp+28h+arg_10]
0x18000b0bc  mov     rax, rbx
0x18000b0bf  mov     rbx, [rsp+28h+arg_8]
0x18000b0c4  add     rsp, 20h
0x18000b0c8  pop     rdi
0x18000b0c9  retn
0x18000b0ca  lea     rcx, aOnlyKeyUsagesO; "Only key usages of compute && store are"...
0x18000b0d1  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
0x18000b0d7  lea     rcx, aLastResortInit; "Last-resort initialization failed"
0x18000b0de  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
