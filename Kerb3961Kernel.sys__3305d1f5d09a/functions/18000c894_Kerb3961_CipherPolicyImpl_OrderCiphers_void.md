# Kerb3961::CipherPolicyImpl::OrderCiphers(void)

- ea: `0x18000c894`
- end: `0x18000cbbd`
- name: `?OrderCiphers@CipherPolicyImpl@Kerb3961@@QEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `809`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000b510`
- `0x18000c140`
- `0x18000cef0`

## callees

- `0x180006c38`
- `0x18000a714`
- `0x18000b300`
- `0x18000c894`
- `0x18000d128`
- `0x180011760`
- `0x180012240`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000cb89`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000cb89`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000cb95`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000cb95`

## pseudocode

```c
_DWORD *__fastcall Kerb3961::CipherPolicyImpl::OrderCiphers(_QWORD *a1, _DWORD *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  const char *v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rcx
  const char *v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rax
  __int64 *v13; // r11
  __int64 v14; // rbx
  __int64 v15; // r10
  unsigned __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rax
  __int64 *v19; // r11
  __int64 v20; // rbx
  __int64 v21; // r10
  __int64 v23; // [rsp+20h] [rbp-60h] BYREF
  __int64 v24; // [rsp+28h] [rbp-58h] BYREF
  __int64 v25; // [rsp+30h] [rbp-50h] BYREF
  __int64 v26; // [rsp+38h] [rbp-48h] BYREF
  __int64 v27; // [rsp+40h] [rbp-40h] BYREF
  __int64 *v28; // [rsp+48h] [rbp-38h]
  __int64 *v29; // [rsp+50h] [rbp-30h]
  __int64 v30; // [rsp+58h] [rbp-28h]
  __int64 v31; // [rsp+60h] [rbp-20h] BYREF
  __int64 *v32; // [rsp+68h] [rbp-18h]
  __int64 *v33; // [rsp+70h] [rbp-10h]
  __int64 v34; // [rsp+78h] [rbp-8h]
  unsigned int v35; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v36; // [rsp+B8h] [rbp+38h] BYREF

  wil::push_lock::acquire_exclusive(&Kerb3961::g_cipherLock, &v36);
  v4 = qword_18001A3C0;
  v27 = (__int64)&v27;
  v28 = &v27;
  v29 = &v27;
  v30 = 0;
  while ( (_UNKNOWN **)v4 != &Kerb3961::g_encryptions )
  {
    v5 = *(_QWORD *)(v4 + 32);
    v23 = *(_QWORD *)(v4 + 24);
    v24 = v5;
    v35 = ~(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 64LL))(v5);
    utl::map<unsigned int,Kerb3961::ChecksumAlgorithm *,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(
      &v27,
      &v25,
      &v35,
      &v24);
    if ( !v25 )
    {
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"pos != nullptr", v6);
      *a2 = -1073741801;
      goto LABEL_29;
    }
    if ( !(_BYTE)v26 )
    {
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"inserted", v6);
      *a2 = -1073741771;
      goto LABEL_29;
    }
    LOBYTE(v6) = 1;
    v4 = utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(v4, v6);
  }
  v7 = qword_18001A3E0;
  v31 = (__int64)&v31;
  v32 = &v31;
  v33 = &v31;
  v34 = 0;
  while ( (_UNKNOWN **)v7 != &Kerb3961::g_checksums )
  {
    v8 = *(_QWORD *)(v7 + 32);
    v25 = *(_QWORD *)(v7 + 24);
    v26 = v8;
    v35 = ~(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v8 + 40LL))(v8);
    utl::map<unsigned int,Kerb3961::ChecksumAlgorithm *,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(
      &v31,
      &v23,
      &v35,
      &v26);
    if ( !v23 )
    {
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"pos != nullptr", v9);
      *a2 = -1073741801;
      goto LABEL_28;
    }
    if ( !(_BYTE)v24 )
    {
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"inserted", v9);
      *a2 = -1073741771;
      goto LABEL_28;
    }
    LOBYTE(v9) = 1;
    v7 = utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(v7, v9);
  }
  v10 = (unsigned __int64)(a1 + 3);
  v11 = a1[3];
  v12 = (__int64 *)a1[4];
  v13 = (__int64 *)a1[5];
  v14 = a1[6];
  if ( v29 == &v27 )
  {
    *(_QWORD *)v10 = v10;
    v15 = 0;
    a1[4] = a1 + 3;
    a1[5] = a1 + 3;
  }
  else
  {
    v15 = v30;
    *(_QWORD *)(v27 & 0xFFFFFFFFFFFFFFFEuLL) = v10 | 1;
    *(_QWORD *)v10 = v27;
    a1[4] = v28;
    a1[5] = v29;
  }
  a1[6] = v15;
  if ( v13 == (__int64 *)v10 )
  {
    v30 = 0;
    v27 = (__int64)&v27;
    v12 = &v27;
    v29 = &v27;
  }
  else
  {
    *(_QWORD *)(v11 & 0xFFFFFFFFFFFFFFFEuLL) = (char *)&v27 + 1;
    v27 = v11;
    v29 = v13;
    v30 = v14;
  }
  v16 = (unsigned __int64)(a1 + 7);
  v28 = v12;
  v17 = a1[7];
  v18 = (__int64 *)a1[8];
  v19 = (__int64 *)a1[9];
  v20 = a1[10];
  if ( v33 == &v31 )
  {
    *(_QWORD *)v16 = v16;
    v21 = 0;
    a1[8] = a1 + 7;
    a1[9] = a1 + 7;
  }
  else
  {
    v21 = v34;
    *(_QWORD *)(v31 & 0xFFFFFFFFFFFFFFFEuLL) = v16 | 1;
    *(_QWORD *)v16 = v31;
    a1[8] = v32;
    a1[9] = v33;
  }
  a1[10] = v21;
  if ( v19 == (__int64 *)v16 )
  {
    v34 = 0;
    v31 = (__int64)&v31;
    v18 = &v31;
    v33 = &v31;
  }
  else
  {
    *(_QWORD *)(v17 & 0xFFFFFFFFFFFFFFFEuLL) = (char *)&v31 + 1;
    v31 = v17;
    v33 = v19;
    v34 = v20;
  }
  v32 = v18;
  *a2 = 0;
LABEL_28:
  utl::_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>::~_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>(&v31);
LABEL_29:
  utl::_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>::~_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>(&v27);
  if ( v36 )
  {
    ExReleasePushLockExclusiveEx(v36, 0);
    KeLeaveCriticalRegion();
  }
  return a2;
}

```

## disassembly

```asm
0x18000c894  mov     [rsp-18h+arg_0], rbx
0x18000c899  mov     [rsp-18h+arg_8], rsi
0x18000c89e  push    rbp
0x18000c89f  push    rdi
0x18000c8a0  push    r14
0x18000c8a2  mov     rbp, rsp
0x18000c8a5  sub     rsp, 80h
0x18000c8ac  mov     rdi, rdx
0x18000c8af  mov     r14, rcx
0x18000c8b2  lea     rdx, [rbp+arg_18]
0x18000c8b6  lea     rcx, ?g_cipherLock@Kerb3961@@3UCommonLock@1@A; Kerb3961::CommonLock Kerb3961::g_cipherLock
0x18000c8bd  call    ?acquire_exclusive@push_lock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_KP6AXPEA_K@_E$1?release_push_lock_exclusive@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEA_KPEA_K$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x18000c8c2  mov     rbx, cs:qword_18001A3C0
0x18000c8c9  lea     rax, [rbp+var_40]
0x18000c8cd  mov     [rbp+var_40], rax
0x18000c8d1  lea     rax, [rbp+var_40]
0x18000c8d5  mov     [rbp+var_38], rax
0x18000c8d9  mov     [rbp+var_30], rax
0x18000c8dd  mov     [rbp+var_28], 0
0x18000c8e5  lea     rax, ?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x18000c8ec  cmp     rbx, rax
0x18000c8ef  jz      loc_18000C975
0x18000c8f5  mov     rcx, [rbx+20h]
0x18000c8f9  mov     rax, [rbx+18h]
0x18000c8fd  mov     [rbp+var_60], rax
0x18000c901  mov     [rbp+var_58], rcx
0x18000c905  mov     rax, [rcx]
0x18000c908  mov     rax, [rax+40h]
0x18000c90c  call    _guard_dispatch_icall
0x18000c911  not     eax
0x18000c913  lea     r9, [rbp+var_58]
0x18000c917  lea     r8, [rbp+arg_10]
0x18000c91b  mov     [rbp+arg_10], eax
0x18000c91e  lea     rdx, [rbp+var_50]
0x18000c922  lea     rcx, [rbp+var_40]
0x18000c926  call    ??$try_emplace@AEAPEAUChecksumAlgorithm@Kerb3961@@$0A@@?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@_N@1@$$QEAIAEAPEAUChecksumAlgorithm@Kerb3961@@@Z; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(uint &&,Kerb3961::ChecksumAlgorithm * &)
0x18000c92b  cmp     [rbp+var_50], 0
0x18000c930  jz      short loc_18000C95E
0x18000c932  cmp     byte ptr [rbp+var_48], 0
0x18000c936  jz      short loc_18000C947
0x18000c938  mov     dl, 1
0x18000c93a  mov     rcx, rbx
0x18000c93d  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(bool)
0x18000c942  mov     rbx, rax
0x18000c945  jmp     short loc_18000C8E5
0x18000c947  lea     rcx, aInserted; "inserted"
0x18000c94e  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000c953  mov     dword ptr [rdi], 0C0000035h
0x18000c959  jmp     loc_18000CB75
0x18000c95e  lea     rcx, aPosNullptr; "pos != nullptr"
0x18000c965  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000c96a  mov     dword ptr [rdi], 0C0000017h
0x18000c970  jmp     loc_18000CB75
0x18000c975  mov     rbx, cs:qword_18001A3E0
0x18000c97c  lea     rax, [rbp+var_20]
0x18000c980  mov     [rbp+var_20], rax
0x18000c984  lea     rax, [rbp+var_20]
0x18000c988  mov     [rbp+var_18], rax
0x18000c98c  mov     [rbp+var_10], rax
0x18000c990  mov     [rbp+var_8], 0
0x18000c998  lea     rax, ?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x18000c99f  cmp     rbx, rax
0x18000c9a2  jz      loc_18000CA28
0x18000c9a8  mov     rcx, [rbx+20h]
0x18000c9ac  mov     rax, [rbx+18h]
0x18000c9b0  mov     [rbp+var_50], rax
0x18000c9b4  mov     [rbp+var_48], rcx
0x18000c9b8  mov     rax, [rcx]
0x18000c9bb  mov     rax, [rax+28h]
0x18000c9bf  call    _guard_dispatch_icall
0x18000c9c4  not     eax
0x18000c9c6  lea     r9, [rbp+var_48]
0x18000c9ca  lea     r8, [rbp+arg_10]
0x18000c9ce  mov     [rbp+arg_10], eax
0x18000c9d1  lea     rdx, [rbp+var_60]
0x18000c9d5  lea     rcx, [rbp+var_20]
0x18000c9d9  call    ??$try_emplace@AEAPEAUChecksumAlgorithm@Kerb3961@@$0A@@?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@_N@1@$$QEAIAEAPEAUChecksumAlgorithm@Kerb3961@@@Z; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(uint &&,Kerb3961::ChecksumAlgorithm * &)
0x18000c9de  cmp     [rbp+var_60], 0
0x18000c9e3  jz      short loc_18000CA11
0x18000c9e5  cmp     byte ptr [rbp+var_58], 0
0x18000c9e9  jz      short loc_18000C9FA
0x18000c9eb  mov     dl, 1
0x18000c9ed  mov     rcx, rbx
0x18000c9f0  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(bool)
0x18000c9f5  mov     rbx, rax
0x18000c9f8  jmp     short loc_18000C998
0x18000c9fa  lea     rcx, aInserted; "inserted"
0x18000ca01  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000ca06  mov     dword ptr [rdi], 0C0000035h
0x18000ca0c  jmp     loc_18000CB6C
0x18000ca11  lea     rcx, aPosNullptr; "pos != nullptr"
0x18000ca18  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000ca1d  mov     dword ptr [rdi], 0C0000017h
0x18000ca23  jmp     loc_18000CB6C
0x18000ca28  lea     r8, [r14+18h]
0x18000ca2c  mov     r9, [r8]
0x18000ca2f  lea     rcx, [rbp+var_40]
0x18000ca33  mov     rax, [r8+8]
0x18000ca37  mov     r11, [r8+10h]
0x18000ca3b  mov     rbx, [r8+18h]
0x18000ca3f  cmp     [rbp+var_30], rcx
0x18000ca43  jnz     short loc_18000CA55
0x18000ca45  mov     [r8], r8
0x18000ca48  xor     r10d, r10d
0x18000ca4b  mov     [r8+8], r8
0x18000ca4f  mov     [r8+10h], r8
0x18000ca53  jmp     short loc_18000CA82
0x18000ca55  mov     rcx, [rbp+var_40]
0x18000ca59  mov     rdx, r8
0x18000ca5c  mov     r10, [rbp+var_28]
0x18000ca60  or      rdx, 1
0x18000ca64  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000ca68  mov     [rcx], rdx
0x18000ca6b  mov     rcx, [rbp+var_40]
0x18000ca6f  mov     [r8], rcx
0x18000ca72  mov     rcx, [rbp+var_38]
0x18000ca76  mov     [r8+8], rcx
0x18000ca7a  mov     rcx, [rbp+var_30]
0x18000ca7e  mov     [r8+10h], rcx
0x18000ca82  mov     [r8+18h], r10
0x18000ca86  cmp     r11, r8
0x18000ca89  jnz     short loc_18000CAA5
0x18000ca8b  lea     rax, [rbp+var_40]
0x18000ca8f  mov     [rbp+var_28], 0
0x18000ca97  mov     [rbp+var_40], rax
0x18000ca9b  lea     rax, [rbp+var_40]
0x18000ca9f  mov     [rbp+var_30], rax
0x18000caa3  jmp     short loc_18000CAC3
0x18000caa5  lea     rdx, [rbp+var_40]
0x18000caa9  mov     rcx, r9
0x18000caac  or      rdx, 1
0x18000cab0  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000cab4  mov     [rcx], rdx
0x18000cab7  mov     [rbp+var_40], r9
0x18000cabb  mov     [rbp+var_30], r11
0x18000cabf  mov     [rbp+var_28], rbx
0x18000cac3  lea     r8, [r14+38h]
0x18000cac7  mov     [rbp+var_38], rax
0x18000cacb  mov     r9, [r8]
0x18000cace  lea     rcx, [rbp+var_20]
0x18000cad2  mov     rax, [r8+8]
0x18000cad6  mov     r11, [r8+10h]
0x18000cada  mov     rbx, [r8+18h]
0x18000cade  cmp     [rbp+var_10], rcx
0x18000cae2  jnz     short loc_18000CAF4
0x18000cae4  mov     [r8], r8
0x18000cae7  xor     r10d, r10d
0x18000caea  mov     [r8+8], r8
0x18000caee  mov     [r8+10h], r8
0x18000caf2  jmp     short loc_18000CB21
0x18000caf4  mov     rcx, [rbp+var_20]
0x18000caf8  mov     rdx, r8
0x18000cafb  mov     r10, [rbp+var_8]
0x18000caff  or      rdx, 1
0x18000cb03  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000cb07  mov     [rcx], rdx
0x18000cb0a  mov     rcx, [rbp+var_20]
0x18000cb0e  mov     [r8], rcx
0x18000cb11  mov     rcx, [rbp+var_18]
0x18000cb15  mov     [r8+8], rcx
0x18000cb19  mov     rcx, [rbp+var_10]
0x18000cb1d  mov     [r8+10h], rcx
0x18000cb21  mov     [r8+18h], r10
0x18000cb25  cmp     r11, r8
0x18000cb28  jnz     short loc_18000CB44
0x18000cb2a  lea     rax, [rbp+var_20]
0x18000cb2e  mov     [rbp+var_8], 0
0x18000cb36  mov     [rbp+var_20], rax
0x18000cb3a  lea     rax, [rbp+var_20]
0x18000cb3e  mov     [rbp+var_10], rax
0x18000cb42  jmp     short loc_18000CB62
0x18000cb44  lea     rdx, [rbp+var_20]
0x18000cb48  mov     rcx, r9
0x18000cb4b  or      rdx, 1
0x18000cb4f  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000cb53  mov     [rcx], rdx
0x18000cb56  mov     [rbp+var_20], r9
0x18000cb5a  mov     [rbp+var_10], r11
0x18000cb5e  mov     [rbp+var_8], rbx
0x18000cb62  mov     [rbp+var_18], rax
0x18000cb66  mov     dword ptr [rdi], 0
0x18000cb6c  lea     rcx, [rbp+var_20]
0x18000cb70  call    ??1?$_Tree@IU?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@U?$less@I@2@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<uint,utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>,0>::~_Tree<uint,utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>,0>(void)
0x18000cb75  lea     rcx, [rbp+var_40]
0x18000cb79  call    ??1?$_Tree@IU?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@U?$less@I@2@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<uint,utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>,0>::~_Tree<uint,utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>,0>(void)
0x18000cb7e  mov     rcx, [rbp+arg_18]
0x18000cb82  test    rcx, rcx
0x18000cb85  jz      short loc_18000CBA1
0x18000cb87  xor     edx, edx
0x18000cb89  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18000cb90  nop     dword ptr [rax+rax+00h]
0x18000cb95  call    cs:__imp_KeLeaveCriticalRegion
0x18000cb9c  nop     dword ptr [rax+rax+00h]
0x18000cba1  lea     r11, [rsp+80h+var_s0]
0x18000cba9  mov     rax, rdi
0x18000cbac  mov     rbx, [r11+20h]
0x18000cbb0  mov     rsi, [r11+28h]
0x18000cbb4  mov     rsp, r11
0x18000cbb7  pop     r14
0x18000cbb9  pop     rdi
0x18000cbba  pop     rbp
0x18000cbbb  retn
```
