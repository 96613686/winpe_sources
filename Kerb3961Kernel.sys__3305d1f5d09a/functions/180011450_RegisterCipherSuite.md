# RegisterCipherSuite

- ea: `0x180011450`
- end: `0x180011630`
- name: `RegisterCipherSuite`
- size: `480`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800010b0`
- `0x1800010e0`
- `0x180001110`
- `0x180001140`
- `0x180001320`

## callees

- `0x180006c38`
- `0x18000b300`
- `0x18000d128`
- `0x180010f40`
- `0x180011450`
- `0x180011b40`
- `0x180012240`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180011558`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180011608`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180011558`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180011608`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180011564`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180011614`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180011564`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180011614`

## pseudocode

```c
char __fastcall RegisterCipherSuite(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  char v5; // di
  char v6; // bl
  bool v7; // si
  char v8; // al
  bool v9; // al
  unsigned __int64 *v11; // rbx
  unsigned __int64 *v12; // rbx
  unsigned __int64 *v13; // [rsp+20h] [rbp-28h] BYREF
  char v14; // [rsp+28h] [rbp-20h]
  unsigned __int64 *v15; // [rsp+30h] [rbp-18h] BYREF
  char v16; // [rsp+38h] [rbp-10h]
  __int64 v17; // [rsp+80h] [rbp+38h] BYREF
  __int64 v18; // [rsp+88h] [rbp+40h] BYREF
  int v19; // [rsp+90h] [rbp+48h] BYREF
  __int64 v20; // [rsp+98h] [rbp+50h] BYREF

  v18 = a2;
  v17 = a1;
  wil::push_lock::acquire_exclusive(&Kerb3961::g_cipherLock, &v20);
  v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 216LL))(a1);
  utl::map<unsigned int,Kerb3961::ChecksumAlgorithm *,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(
    &Kerb3961::g_encryptions,
    &v13,
    &v19,
    &v17);
  LODWORD(v17) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 104LL))(a2);
  utl::map<unsigned int,Kerb3961::ChecksumAlgorithm *,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(
    &Kerb3961::g_checksums,
    &v15,
    &v17,
    &v18);
  if ( !v16 || !v14 )
  {
    v5 = 0;
    goto LABEL_7;
  }
  v5 = 1;
  if ( !Kerb3961::g_ciphersInitialized )
  {
LABEL_7:
    v6 = 0;
    v7 = 0;
    goto LABEL_8;
  }
  v6 = 1;
  v7 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 16LL))(a1, &v17) >= 0;
  if ( *(int *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 16LL))(a2, &v17) < 0 )
  {
LABEL_8:
    v8 = 0;
    goto LABEL_9;
  }
  v8 = 1;
LABEL_9:
  v9 = !v6 || v8 && v7;
  if ( v5 && v9 )
  {
    if ( v20 )
    {
      ExReleasePushLockExclusiveEx(v20, 0);
      KeLeaveCriticalRegion();
    }
    return 1;
  }
  else
  {
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 24LL))(a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
    }
    if ( v14 )
    {
      v11 = v13;
      LOBYTE(v4) = 1;
      utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(v13, v4);
      utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_HeadUnlinkNode(
        &Kerb3961::g_encryptions,
        v11);
      --qword_18001A3C8;
      Kerb3961Free(v11);
    }
    if ( v16 )
    {
      v12 = v15;
      LOBYTE(v4) = 1;
      utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(v15, v4);
      utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_HeadUnlinkNode(
        &Kerb3961::g_checksums,
        v12);
      --qword_18001A3E8;
      Kerb3961Free(v12);
    }
    if ( v20 )
    {
      ExReleasePushLockExclusiveEx(v20, 0);
      KeLeaveCriticalRegion();
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180011450  mov     [rsp-30h+arg_8], rdx
0x180011455  mov     [rsp-30h+arg_0], rcx
0x18001145a  push    rbp
0x18001145b  push    rbx
0x18001145c  push    rsi
0x18001145d  push    rdi
0x18001145e  push    r14
0x180011460  push    r15
0x180011462  mov     rbp, rsp
0x180011465  sub     rsp, 48h
0x180011469  mov     r14, rdx
0x18001146c  mov     r15, rcx
0x18001146f  lea     rdx, [rbp+arg_18]
0x180011473  lea     rcx, ?g_cipherLock@Kerb3961@@3UCommonLock@1@A; Kerb3961::CommonLock Kerb3961::g_cipherLock
0x18001147a  call    ?acquire_exclusive@push_lock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_KP6AXPEA_K@_E$1?release_push_lock_exclusive@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEA_KPEA_K$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x18001147f  mov     rax, [r15]
0x180011482  mov     rcx, r15
0x180011485  mov     rax, [rax+0D8h]
0x18001148c  call    _guard_dispatch_icall
0x180011491  lea     r9, [rbp+arg_0]
0x180011495  mov     [rbp+arg_10], eax
0x180011498  lea     r8, [rbp+arg_10]
0x18001149c  lea     rdx, [rbp+var_28]
0x1800114a0  lea     rcx, ?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x1800114a7  call    ??$try_emplace@AEAPEAUChecksumAlgorithm@Kerb3961@@$0A@@?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@_N@1@$$QEAIAEAPEAUChecksumAlgorithm@Kerb3961@@@Z; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(uint &&,Kerb3961::ChecksumAlgorithm * &)
0x1800114ac  mov     rax, [r14]
0x1800114af  mov     rcx, r14
0x1800114b2  mov     rax, [rax+68h]
0x1800114b6  call    _guard_dispatch_icall
0x1800114bb  lea     r9, [rbp+arg_8]
0x1800114bf  mov     dword ptr [rbp+arg_0], eax
0x1800114c2  lea     r8, [rbp+arg_0]
0x1800114c6  lea     rdx, [rbp+var_18]
0x1800114ca  lea     rcx, ?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x1800114d1  call    ??$try_emplace@AEAPEAUChecksumAlgorithm@Kerb3961@@$0A@@?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@_N@1@$$QEAIAEAPEAUChecksumAlgorithm@Kerb3961@@@Z; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(uint &&,Kerb3961::ChecksumAlgorithm * &)
0x1800114d6  cmp     [rbp+var_10], 0
0x1800114da  jz      short loc_180011527
0x1800114dc  cmp     [rbp+var_20], 0
0x1800114e0  jz      short loc_180011527
0x1800114e2  cmp     cs:?g_ciphersInitialized@Kerb3961@@3IA, 0; uint Kerb3961::g_ciphersInitialized
0x1800114e9  mov     dil, 1
0x1800114ec  jbe     short loc_18001152A
0x1800114ee  mov     rax, [r15]
0x1800114f1  lea     rdx, [rbp+arg_0]
0x1800114f5  mov     rcx, r15
0x1800114f8  mov     bl, dil
0x1800114fb  mov     rax, [rax+10h]
0x1800114ff  call    _guard_dispatch_icall
0x180011504  lea     rdx, [rbp+arg_0]
0x180011508  mov     rcx, r14
0x18001150b  cmp     dword ptr [rax], 0
0x18001150e  mov     rax, [r14]
0x180011511  setnl   sil
0x180011515  mov     rax, [rax+10h]
0x180011519  call    _guard_dispatch_icall
0x18001151e  cmp     dword ptr [rax], 0
0x180011521  jl      short loc_18001152F
0x180011523  mov     al, bl
0x180011525  jmp     short loc_180011531
0x180011527  xor     dil, dil
0x18001152a  xor     bl, bl
0x18001152c  xor     sil, sil
0x18001152f  xor     al, al
0x180011531  test    bl, bl
0x180011533  jz      short loc_180011542
0x180011535  test    al, al
0x180011537  jz      short loc_18001153E
0x180011539  test    sil, sil
0x18001153c  jnz     short loc_180011542
0x18001153e  xor     al, al
0x180011540  jmp     short loc_180011544
0x180011542  mov     al, 1
0x180011544  test    dil, dil
0x180011547  jz      short loc_180011577
0x180011549  test    al, al
0x18001154b  jz      short loc_180011577
0x18001154d  mov     rcx, [rbp+arg_18]
0x180011551  test    rcx, rcx
0x180011554  jz      short loc_180011570
0x180011556  xor     edx, edx
0x180011558  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18001155f  nop     dword ptr [rax+rax+00h]
0x180011564  call    cs:__imp_KeLeaveCriticalRegion
0x18001156b  nop     dword ptr [rax+rax+00h]
0x180011570  mov     al, 1
0x180011572  jmp     loc_180011622
0x180011577  test    bl, bl
0x180011579  jz      short loc_180011599
0x18001157b  mov     rax, [r14]
0x18001157e  mov     rcx, r14
0x180011581  mov     rax, [rax+18h]
0x180011585  call    _guard_dispatch_icall
0x18001158a  mov     rax, [r15]
0x18001158d  mov     rcx, r15
0x180011590  mov     rax, [rax+18h]
0x180011594  call    _guard_dispatch_icall
0x180011599  cmp     [rbp+var_20], 0
0x18001159d  jz      short loc_1800115CB
0x18001159f  mov     rbx, [rbp+var_28]
0x1800115a3  mov     dl, 1
0x1800115a5  mov     rcx, rbx
0x1800115a8  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(bool)
0x1800115ad  mov     rdx, rbx
0x1800115b0  lea     rcx, ?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x1800115b7  call    ?_HeadUnlinkNode@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAXPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@@Z; utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_HeadUnlinkNode(utl::_TreeNode<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>> *)
0x1800115bc  dec     cs:qword_18001A3C8
0x1800115c3  mov     rcx, rbx
0x1800115c6  call    Kerb3961Free
0x1800115cb  cmp     [rbp+var_10], 0
0x1800115cf  jz      short loc_1800115FD
0x1800115d1  mov     rbx, [rbp+var_18]
0x1800115d5  mov     dl, 1
0x1800115d7  mov     rcx, rbx
0x1800115da  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(bool)
0x1800115df  mov     rdx, rbx
0x1800115e2  lea     rcx, ?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x1800115e9  call    ?_HeadUnlinkNode@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAXPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@@Z; utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_HeadUnlinkNode(utl::_TreeNode<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>> *)
0x1800115ee  dec     cs:qword_18001A3E8
0x1800115f5  mov     rcx, rbx
0x1800115f8  call    Kerb3961Free
0x1800115fd  mov     rcx, [rbp+arg_18]
0x180011601  test    rcx, rcx
0x180011604  jz      short loc_180011620
0x180011606  xor     edx, edx
0x180011608  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18001160f  nop     dword ptr [rax+rax+00h]
0x180011614  call    cs:__imp_KeLeaveCriticalRegion
0x18001161b  nop     dword ptr [rax+rax+00h]
0x180011620  xor     al, al
0x180011622  add     rsp, 48h
0x180011626  pop     r15
0x180011628  pop     r14
0x18001162a  pop     rdi
0x18001162b  pop     rsi
0x18001162c  pop     rbx
0x18001162d  pop     rbp
0x18001162e  retn
```
