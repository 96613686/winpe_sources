# RegisterCipherSuite

- ea: `0x180003eb0`
- end: `0x180004034`
- name: `RegisterCipherSuite`
- size: `388`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180001340`
- `0x180001660`
- `0x180001690`
- `0x180001870`
- `0x1800018a0`

## callees

- `0x1800031a8`
- `0x180003cc4`
- `0x180003d70`
- `0x180003eb0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003fb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000401f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003fb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000401f`

## pseudocode

```c
char __fastcall RegisterCipherSuite(__int64 a1, __int64 a2)
{
  char v4; // di
  char v5; // bl
  bool v6; // r15
  char v7; // al
  bool v8; // al
  __int64 v10; // [rsp+20h] [rbp-28h] BYREF
  char v11; // [rsp+28h] [rbp-20h]
  __int64 v12; // [rsp+30h] [rbp-18h] BYREF
  char v13; // [rsp+38h] [rbp-10h]
  __int64 v14; // [rsp+80h] [rbp+38h] BYREF
  __int64 v15; // [rsp+88h] [rbp+40h] BYREF
  int v16; // [rsp+90h] [rbp+48h] BYREF
  PSRWLOCK SRWLock; // [rsp+98h] [rbp+50h] BYREF

  v15 = a2;
  v14 = a1;
  wil::srwlock::lock_exclusive(&Kerb3961::g_cipherLock, &SRWLock);
  v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 216LL))(a1);
  utl::map<unsigned int,Kerb3961::ChecksumAlgorithm *,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(
    &Kerb3961::g_encryptions,
    &v10,
    &v16,
    &v14);
  LODWORD(v14) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 104LL))(a2);
  utl::map<unsigned int,Kerb3961::ChecksumAlgorithm *,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(
    &Kerb3961::g_checksums,
    &v12,
    &v14,
    &v15);
  if ( !v13 || !v11 )
  {
    v4 = 0;
    goto LABEL_7;
  }
  v4 = 1;
  if ( !Kerb3961::g_ciphersInitialized )
  {
LABEL_7:
    v5 = 0;
    v6 = 0;
    goto LABEL_8;
  }
  v5 = 1;
  v6 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 16LL))(a1, &v14) >= 0;
  if ( *(int *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 16LL))(a2, &v14) < 0 )
  {
LABEL_8:
    v7 = 0;
    goto LABEL_9;
  }
  v7 = 1;
LABEL_9:
  v8 = !v5 || v7 && v6;
  if ( v4 && v8 )
  {
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 1;
  }
  else
  {
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 24LL))(a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
    }
    if ( v11 )
      utl::_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::EncryptionAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::EncryptionAlgorithm *>>,0>::erase(
        &Kerb3961::g_encryptions,
        &v14,
        v10);
    if ( v13 )
      utl::_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::EncryptionAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::EncryptionAlgorithm *>>,0>::erase(
        &Kerb3961::g_checksums,
        &v14,
        v12);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 0;
  }
}

```

## disassembly

```asm
0x180003eb0  mov     [rsp-30h+arg_8], rdx
0x180003eb5  mov     [rsp-30h+arg_0], rcx
0x180003eba  push    rbp
0x180003ebb  push    rbx
0x180003ebc  push    rsi
0x180003ebd  push    rdi
0x180003ebe  push    r14
0x180003ec0  push    r15
0x180003ec2  mov     rbp, rsp
0x180003ec5  sub     rsp, 48h
0x180003ec9  mov     rsi, rdx
0x180003ecc  mov     r14, rcx
0x180003ecf  lea     rdx, [rbp+SRWLock]
0x180003ed3  lea     rcx, ?g_cipherLock@Kerb3961@@3UCommonLock@1@A; Kerb3961::CommonLock Kerb3961::g_cipherLock
0x180003eda  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x180003edf  mov     rax, [r14]
0x180003ee2  mov     rcx, r14
0x180003ee5  mov     rax, [rax+0D8h]
0x180003eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ef1  lea     r9, [rbp+arg_0]
0x180003ef5  mov     [rbp+arg_10], eax
0x180003ef8  lea     r8, [rbp+arg_10]
0x180003efc  lea     rdx, [rbp+var_28]
0x180003f00  lea     rcx, ?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x180003f07  call    ??$try_emplace@AEAPEAUChecksumAlgorithm@Kerb3961@@$0A@@?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@_N@1@$$QEAIAEAPEAUChecksumAlgorithm@Kerb3961@@@Z; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(uint &&,Kerb3961::ChecksumAlgorithm * &)
0x180003f0c  mov     rax, [rsi]
0x180003f0f  mov     rcx, rsi
0x180003f12  mov     rax, [rax+68h]
0x180003f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f1b  lea     r9, [rbp+arg_8]
0x180003f1f  mov     dword ptr [rbp+arg_0], eax
0x180003f22  lea     r8, [rbp+arg_0]
0x180003f26  lea     rdx, [rbp+var_18]
0x180003f2a  lea     rcx, ?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x180003f31  call    ??$try_emplace@AEAPEAUChecksumAlgorithm@Kerb3961@@$0A@@?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@_N@1@$$QEAIAEAPEAUChecksumAlgorithm@Kerb3961@@@Z; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(uint &&,Kerb3961::ChecksumAlgorithm * &)
0x180003f36  cmp     [rbp+var_10], 0
0x180003f3a  jz      short loc_180003F87
0x180003f3c  cmp     [rbp+var_20], 0
0x180003f40  jz      short loc_180003F87
0x180003f42  cmp     cs:?g_ciphersInitialized@Kerb3961@@3IA, 0; uint Kerb3961::g_ciphersInitialized
0x180003f49  mov     dil, 1
0x180003f4c  jbe     short loc_180003F8A
0x180003f4e  mov     rax, [r14]
0x180003f51  lea     rdx, [rbp+arg_0]
0x180003f55  mov     rcx, r14
0x180003f58  mov     bl, dil
0x180003f5b  mov     rax, [rax+10h]
0x180003f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f64  lea     rdx, [rbp+arg_0]
0x180003f68  mov     rcx, rsi
0x180003f6b  cmp     dword ptr [rax], 0
0x180003f6e  mov     rax, [rsi]
0x180003f71  setnl   r15b
0x180003f75  mov     rax, [rax+10h]
0x180003f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f7e  cmp     dword ptr [rax], 0
0x180003f81  jl      short loc_180003F8F
0x180003f83  mov     al, bl
0x180003f85  jmp     short loc_180003F91
0x180003f87  xor     dil, dil
0x180003f8a  xor     bl, bl
0x180003f8c  xor     r15b, r15b
0x180003f8f  xor     al, al
0x180003f91  test    bl, bl
0x180003f93  jz      short loc_180003FA2
0x180003f95  test    al, al
0x180003f97  jz      short loc_180003F9E
0x180003f99  test    r15b, r15b
0x180003f9c  jnz     short loc_180003FA2
0x180003f9e  xor     al, al
0x180003fa0  jmp     short loc_180003FA4
0x180003fa2  mov     al, 1
0x180003fa4  test    dil, dil
0x180003fa7  jz      short loc_180003FC0
0x180003fa9  test    al, al
0x180003fab  jz      short loc_180003FC0
0x180003fad  mov     rcx, [rbp+SRWLock]; SRWLock
0x180003fb1  test    rcx, rcx
0x180003fb4  jz      short loc_180003FBC
0x180003fb6  call    cs:__imp_ReleaseSRWLockExclusive
0x180003fbc  mov     al, 1
0x180003fbe  jmp     short loc_180004027
0x180003fc0  test    bl, bl
0x180003fc2  jz      short loc_180003FE2
0x180003fc4  mov     rax, [rsi]
0x180003fc7  mov     rcx, rsi
0x180003fca  mov     rax, [rax+18h]
0x180003fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fd3  mov     rax, [r14]
0x180003fd6  mov     rcx, r14
0x180003fd9  mov     rax, [rax+18h]
0x180003fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fe2  cmp     [rbp+var_20], 0
0x180003fe6  jz      short loc_180003FFC
0x180003fe8  mov     r8, [rbp+var_28]
0x180003fec  lea     rdx, [rbp+arg_0]
0x180003ff0  lea     rcx, ?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x180003ff7  call    ?erase@?$_Tree@IU?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@U?$less@I@2@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@2@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@2@V?$_TreeConstIt@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@2@@Z; utl::_Tree<uint,utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>,0>::erase(utl::_TreeConstIt<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>)
0x180003ffc  cmp     [rbp+var_10], 0
0x180004000  jz      short loc_180004016
0x180004002  mov     r8, [rbp+var_18]
0x180004006  lea     rdx, [rbp+arg_0]
0x18000400a  lea     rcx, ?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x180004011  call    ?erase@?$_Tree@IU?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@U?$less@I@2@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@2@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@2@V?$_TreeConstIt@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@2@@Z; utl::_Tree<uint,utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>,0>::erase(utl::_TreeConstIt<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>)
0x180004016  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000401a  test    rcx, rcx
0x18000401d  jz      short loc_180004025
0x18000401f  call    cs:__imp_ReleaseSRWLockExclusive
0x180004025  xor     al, al
0x180004027  add     rsp, 48h
0x18000402b  pop     r15
0x18000402d  pop     r14
0x18000402f  pop     rdi
0x180004030  pop     rsi
0x180004031  pop     rbx
0x180004032  pop     rbp
0x180004033  retn
```
