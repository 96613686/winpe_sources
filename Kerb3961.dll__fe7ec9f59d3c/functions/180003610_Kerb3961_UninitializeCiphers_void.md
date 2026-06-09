# Kerb3961::UninitializeCiphers(void)

- ea: `0x180003610`
- end: `0x1800036d2`
- name: `?UninitializeCiphers@Kerb3961@@YAXXZ`
- size: `194`
- prototype: `void __fastcall(Kerb3961 *__hidden this)`
- caller_count: `13`
- callee_count: `5`
- tags: ``

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
- `0x18000de8c`

## callees

- `0x180003380`
- `0x1800033f4`
- `0x180003610`
- `0x180003d70`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800036ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800036ba`

## pseudocode

```c
void __fastcall Kerb3961::UninitializeCiphers(Kerb3961 *this)
{
  const unsigned __int16 *v1; // rdx
  unsigned int v2; // eax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp+10h] BYREF

  wil::srwlock::lock_exclusive(&Kerb3961::g_cipherLock, &SRWLock);
  v2 = Kerb3961::g_ciphersInitialized;
  if ( !Kerb3961::g_ciphersInitialized )
    Kerb3961::ConsistencyFail((Kerb3961 *)L"Cannot uninitialize ciphers that are not initialized", v1);
  --Kerb3961::g_ciphersInitialized;
  if ( v2 == 1 )
  {
    v3 = qword_180029048;
    v5 = qword_180029048;
    while ( (void **)v3 != &Kerb3961::g_encryptions )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v3 + 32) + 24LL))(*(_QWORD *)(v3 + 32));
      utl::_TreeConstIt<utl::pair<unsigned int const,Kerb3961::EncryptionAlgorithm *>>::operator++(&v5);
      v3 = v5;
    }
    v4 = qword_180029068;
    v5 = qword_180029068;
    while ( (void **)v4 != &Kerb3961::g_checksums )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 32) + 24LL))(*(_QWORD *)(v4 + 32));
      utl::_TreeConstIt<utl::pair<unsigned int const,Kerb3961::EncryptionAlgorithm *>>::operator++(&v5);
      v4 = v5;
    }
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
}

```

## disassembly

```asm
0x180003610  sub     rsp, 28h
0x180003614  lea     rdx, [rsp+28h+SRWLock]
0x180003619  lea     rcx, ?g_cipherLock@Kerb3961@@3UCommonLock@1@A; Kerb3961::CommonLock Kerb3961::g_cipherLock
0x180003620  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x180003625  mov     eax, cs:?g_ciphersInitialized@Kerb3961@@3IA; uint Kerb3961::g_ciphersInitialized
0x18000362b  test    eax, eax
0x18000362d  jz      loc_1800036C5
0x180003633  add     eax, 0FFFFFFFFh
0x180003636  mov     cs:?g_ciphersInitialized@Kerb3961@@3IA, eax; uint Kerb3961::g_ciphersInitialized
0x18000363c  jnz     short loc_1800036B0
0x18000363e  mov     rax, cs:qword_180029048
0x180003645  mov     [rsp+28h+arg_0], rax
0x18000364a  lea     rcx, ?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x180003651  cmp     rax, rcx
0x180003654  jz      short loc_180003677
0x180003656  mov     rcx, [rax+20h]
0x18000365a  mov     rax, [rcx]
0x18000365d  mov     rax, [rax+18h]
0x180003661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003666  lea     rcx, [rsp+28h+arg_0]
0x18000366b  call    ??E?$_TreeConstIt@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>::operator++(void)
0x180003670  mov     rax, [rsp+28h+arg_0]
0x180003675  jmp     short loc_18000364A
0x180003677  mov     rax, cs:qword_180029068
0x18000367e  mov     [rsp+28h+arg_0], rax
0x180003683  lea     rcx, ?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x18000368a  cmp     rax, rcx
0x18000368d  jz      short loc_1800036B0
0x18000368f  mov     rcx, [rax+20h]
0x180003693  mov     rax, [rcx]
0x180003696  mov     rax, [rax+18h]
0x18000369a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000369f  lea     rcx, [rsp+28h+arg_0]
0x1800036a4  call    ??E?$_TreeConstIt@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>::operator++(void)
0x1800036a9  mov     rax, [rsp+28h+arg_0]
0x1800036ae  jmp     short loc_180003683
0x1800036b0  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x1800036b5  test    rcx, rcx
0x1800036b8  jz      short loc_1800036C0
0x1800036ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800036c0  add     rsp, 28h
0x1800036c4  retn
0x1800036c5  lea     rcx, aCannotUninitia; "Cannot uninitialize ciphers that are no"...
0x1800036cc  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
