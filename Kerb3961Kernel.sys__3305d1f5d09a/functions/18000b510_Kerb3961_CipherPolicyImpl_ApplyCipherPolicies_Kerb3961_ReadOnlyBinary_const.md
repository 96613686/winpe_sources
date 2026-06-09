# Kerb3961::CipherPolicyImpl::ApplyCipherPolicies(Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000b510`
- end: `0x18000ba18`
- name: `?ApplyCipherPolicies@CipherPolicyImpl@Kerb3961@@UEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `1288`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callees

- `0x180003a38`
- `0x180006c38`
- `0x18000a714`
- `0x18000aac8`
- `0x18000b510`
- `0x18000c894`
- `0x18000d128`
- `0x180011760`
- `0x1800118cc`
- `0x180012240`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000b9d4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000b9d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b9e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b9e0`

## string_xrefs

- `0x18000ba0b`: `You can only retrieve the global policy following a successful call to Read()`
- `0x18000b9a4`: `reader.Read(marshaledPolicies)`
- `0x18000b806`: `reader.ApplyCipher(encryption.second)`
- `0x18000b90c`: `reader.ApplyChecksum(checksum.second)`

## pseudocode

```c
int *__fastcall Kerb3961::CipherPolicyImpl::ApplyCipherPolicies(__int64 a1, int *a2, unsigned __int64 *a3)
{
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rcx
  _DWORD *v10; // r8
  __int64 v11; // rax
  int *v12; // rbx
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rcx
  int v16; // ecx
  bool v17; // zf
  __int64 v18; // rax
  char *v19; // rcx
  __int64 i; // rbx
  __int64 v21; // rdi
  unsigned int v22; // eax
  _QWORD *v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  void (__fastcall *v26)(__int64, char **, _QWORD *); // rsi
  unsigned int v27; // edx
  _QWORD *v28; // r8
  __int64 v29; // rax
  __int64 v30; // rcx
  int v31; // r8d
  unsigned int v32; // edi
  char *v33; // rcx
  __int64 j; // rbx
  __int64 v35; // rdi
  unsigned int v36; // eax
  _QWORD *v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  void (__fastcall *v40)(__int64, char **, _QWORD *); // r15
  unsigned int v41; // edx
  _QWORD *v42; // r8
  __int64 v43; // rax
  __int64 v44; // rcx
  int v45; // ebx
  int v46; // r8d
  int v47; // r8d
  _BYTE v49[16]; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v50[16]; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int64 v51; // [rsp+50h] [rbp-29h]
  _DWORD *v52; // [rsp+58h] [rbp-21h]
  _QWORD v53[2]; // [rsp+60h] [rbp-19h] BYREF
  _QWORD *v54; // [rsp+70h] [rbp-9h]
  __int64 v55; // [rsp+78h] [rbp-1h]
  _QWORD v56[2]; // [rsp+80h] [rbp+7h] BYREF
  _QWORD *v57; // [rsp+90h] [rbp+17h]
  __int64 v58; // [rsp+98h] [rbp+1Fh]
  char *v59; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v60; // [rsp+F0h] [rbp+77h] BYREF

  wil::push_lock::acquire_exclusive(a1 + 16, &v60);
  v7 = *a3;
  v53[0] = v53;
  v51 = 0;
  v53[1] = v53;
  v54 = v53;
  v56[0] = v56;
  v56[1] = v56;
  v57 = v56;
  v52 = 0;
  v55 = 0;
  v58 = 0;
  if ( v7 < 0x18 )
  {
LABEL_85:
    v19 = "remainingSize >= MarshaledPolicyHeaderSize";
    goto LABEL_86;
  }
  v6 = a3[1];
  v8 = *(_QWORD *)(v6 + 16);
  if ( v8 > v7 )
  {
LABEL_84:
    v19 = "header->TotalLength <= remainingSize";
    goto LABEL_86;
  }
  v9 = *(_QWORD *)(v6 + 8);
  if ( !v9 )
  {
LABEL_83:
    v19 = "header->ContentLength > 0";
    goto LABEL_86;
  }
  if ( v9 > v8 - 24 )
  {
LABEL_82:
    v19 = "header->ContentLength <= header->TotalLength - MarshaledPolicyHeaderSize";
    goto LABEL_86;
  }
  if ( *(_DWORD *)v6 != 1 )
  {
    v19 = "header->Type == MarshaledPolicyType::Global";
    goto LABEL_86;
  }
  if ( *(_DWORD *)(v6 + 4) )
  {
    v19 = "header->Id == 0";
    goto LABEL_86;
  }
  v10 = (_DWORD *)(v6 + 24);
  v51 = *(_QWORD *)(v6 + 8);
  v52 = (_DWORD *)(v6 + 24);
  v11 = *(_QWORD *)(v6 + 16);
  v12 = (int *)(v6 + v11);
  v13 = v7 - v11;
  if ( !v13 )
    goto LABEL_22;
  while ( 1 )
  {
    if ( v13 < 0x18 )
      goto LABEL_85;
    v14 = *((_QWORD *)v12 + 2);
    if ( v14 > v13 )
      goto LABEL_84;
    v15 = *((_QWORD *)v12 + 1);
    if ( !v15 )
      goto LABEL_83;
    if ( v15 > v14 - 24 )
      goto LABEL_82;
    v16 = *v12;
    if ( (unsigned int)(*v12 - 2) > 1 )
    {
      v19 = "header->Type == MarshaledPolicyType::Encryption || header->Type == MarshaledPolicyType::Checksum";
      goto LABEL_86;
    }
    if ( !v12[1] )
    {
      v19 = "header->Id != 0";
LABEL_86:
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v19, (const char *)v6);
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"reader.Read(marshaledPolicies)",
        (const char *)0xC000000DLL,
        v47);
      goto LABEL_87;
    }
    v59 = (char *)(v12 + 6);
    if ( v16 == 2 )
    {
      utl::map<unsigned int,Kerb3961::ReadOnlyBinary,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ReadOnlyBinary>>>::try_emplace<unsigned __int64 const &,unsigned char const *,0>(
        v53,
        v49);
      v17 = v49[8] == 0;
    }
    else
    {
      utl::map<unsigned int,Kerb3961::ReadOnlyBinary,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ReadOnlyBinary>>>::try_emplace<unsigned __int64 const &,unsigned char const *,0>(
        v56,
        v50);
      v17 = v50[8] == 0;
    }
    if ( v17 )
    {
      v19 = "result.second";
      goto LABEL_86;
    }
    v18 = *((_QWORD *)v12 + 2);
    v13 -= v18;
    if ( !v13 )
      break;
    v12 = (int *)((char *)v12 + v18);
  }
  v10 = v52;
  v9 = v51;
LABEL_22:
  if ( !v9 )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"You can only retrieve the global policy following a successful call to Read()",
      (const unsigned __int16 *)v6);
  if ( v9 != 20 )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"globalBlob.length == sizeof(MarshaledGlobalPolicyData)",
      (const char *)v6);
LABEL_87:
    *a2 = -1073741811;
    goto LABEL_88;
  }
  Kerb3961::g_supportedEncryptionTypes = *v10;
  Kerb3961::g_assumedEncryptionTypes = v10[1];
  Kerb3961::g_realmEncryptionTypes = v10[2];
  Kerb3961::g_krbtgtEncryptionTypes = v10[3];
  Kerb3961::g_trustEncryptionTypes = v10[4];
  for ( i = *(_QWORD *)(a1 + 40);
        ;
        i = utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(i, v23) )
  {
    if ( i == a1 + 24 )
    {
      for ( j = *(_QWORD *)(a1 + 72);
            ;
            j = utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(j, v37) )
      {
        if ( j == a1 + 56 )
        {
          v45 = *(_DWORD *)Kerb3961::CipherPolicyImpl::OrderCiphers(a1, &v59);
          if ( v45 >= 0 )
          {
            *a2 = 0;
          }
          else
          {
            Kerb3961::Logging::Verify::StatusFailed(
              (Kerb3961::Logging::Verify *)"OrderCiphers()",
              (const char *)(unsigned int)v45,
              v46);
            *a2 = v45;
          }
          goto LABEL_88;
        }
        v35 = *(_QWORD *)(j + 32);
        v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 104LL))(v35);
        if ( v57 == v56 )
          goto LABEL_74;
        v38 = v56[0];
        v37 = v56;
        do
        {
          if ( *(_DWORD *)(v38 + 24) >= v36 )
          {
            v37 = (_QWORD *)v38;
            v39 = 8;
          }
          else
          {
            v39 = 16;
          }
          v38 = *(_QWORD *)(v38 + v39);
        }
        while ( (_UNKNOWN *)v38 != &utl::_TreeSentinel );
        if ( v37 == v56 || v36 < *((_DWORD *)v37 + 6) )
        {
LABEL_74:
          LODWORD(v59) = 0;
          goto LABEL_75;
        }
        v40 = *(void (__fastcall **)(__int64, char **, _QWORD *))(*(_QWORD *)v35 + 80LL);
        v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 104LL))(v35);
        v42 = v56;
        if ( v57 != v56 )
        {
          v43 = v56[0];
          do
          {
            if ( *(_DWORD *)(v43 + 24) >= v41 )
            {
              v42 = (_QWORD *)v43;
              v44 = 8;
            }
            else
            {
              v44 = 16;
            }
            v43 = *(_QWORD *)(v43 + v44);
          }
          while ( (_UNKNOWN *)v43 != &utl::_TreeSentinel );
          if ( v42 != v56 )
          {
            if ( v41 >= *((_DWORD *)v42 + 6) )
              goto LABEL_72;
            v42 = v56;
          }
        }
        __int2c();
LABEL_72:
        v40(v35, &v59, v42 + 4);
        v32 = (unsigned int)v59;
        if ( (int)v59 < 0 )
        {
          v33 = "reader.ApplyChecksum(checksum.second)";
          goto LABEL_51;
        }
LABEL_75:
        LOBYTE(v37) = 1;
      }
    }
    v21 = *(_QWORD *)(i + 32);
    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 216LL))(v21);
    if ( v54 == v53 )
      goto LABEL_48;
    v24 = v53[0];
    v23 = v53;
    do
    {
      if ( *(_DWORD *)(v24 + 24) >= v22 )
      {
        v23 = (_QWORD *)v24;
        v25 = 8;
      }
      else
      {
        v25 = 16;
      }
      v24 = *(_QWORD *)(v25 + v24);
    }
    while ( (_UNKNOWN *)v24 != &utl::_TreeSentinel );
    if ( v23 == v53 || v22 < *((_DWORD *)v23 + 6) )
    {
LABEL_48:
      LODWORD(v59) = 0;
      goto LABEL_49;
    }
    v26 = *(void (__fastcall **)(__int64, char **, _QWORD *))(*(_QWORD *)v21 + 104LL);
    v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 216LL))(v21);
    v28 = v53;
    if ( v54 != v53 )
    {
      v29 = v53[0];
      do
      {
        if ( *(_DWORD *)(v29 + 24) >= v27 )
        {
          v28 = (_QWORD *)v29;
          v30 = 8;
        }
        else
        {
          v30 = 16;
        }
        v29 = *(_QWORD *)(v29 + v30);
      }
      while ( (_UNKNOWN *)v29 != &utl::_TreeSentinel );
      if ( v28 != v53 )
      {
        if ( v27 >= *((_DWORD *)v28 + 6) )
          goto LABEL_46;
        v28 = v53;
      }
    }
    __int2c();
LABEL_46:
    v26(v21, &v59, v28 + 4);
    v32 = (unsigned int)v59;
    if ( (int)v59 < 0 )
      break;
LABEL_49:
    LOBYTE(v23) = 1;
  }
  v33 = "reader.ApplyCipher(encryption.second)";
LABEL_51:
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v33, (const char *)v32, v31);
  *a2 = v32;
LABEL_88:
  utl::_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>::~_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>(v56);
  utl::_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>::~_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>(v53);
  if ( v60 )
  {
    ExReleasePushLockExclusiveEx(v60, 0);
    KeLeaveCriticalRegion();
  }
  return a2;
}

```

## disassembly

```asm
0x18000b510  mov     [rsp-8+arg_8], rbx
0x18000b515  push    rbp
0x18000b516  push    rsi
0x18000b517  push    rdi
0x18000b518  push    r12
0x18000b51a  push    r13
0x18000b51c  push    r14
0x18000b51e  push    r15
0x18000b520  lea     rbp, [rsp-27h]
0x18000b525  sub     rsp, 0A0h
0x18000b52c  mov     r14, rdx
0x18000b52f  mov     r13, rcx
0x18000b532  add     rcx, 10h
0x18000b536  lea     rdx, [rbp+57h+arg_10]
0x18000b53a  mov     rbx, r8
0x18000b53d  call    ?acquire_exclusive@push_lock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_KP6AXPEA_K@_E$1?release_push_lock_exclusive@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEA_KPEA_K$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x18000b542  mov     rdi, [rbx]
0x18000b545  lea     rax, [rbp+57h+var_70]
0x18000b549  xor     r12d, r12d
0x18000b54c  mov     [rbp+57h+var_70], rax
0x18000b550  mov     [rbp+57h+var_80], r12
0x18000b554  lea     rax, [rbp+57h+var_70]
0x18000b558  mov     [rbp+57h+var_68], rax
0x18000b55c  mov     [rbp+57h+var_60], rax
0x18000b560  lea     rax, [rbp+57h+var_50]
0x18000b564  mov     [rbp+57h+var_50], rax
0x18000b568  lea     rax, [rbp+57h+var_50]
0x18000b56c  mov     [rbp+57h+var_48], rax
0x18000b570  mov     [rbp+57h+var_40], rax
0x18000b574  mov     [rbp+57h+var_78], r12
0x18000b578  mov     [rbp+57h+var_58], r12
0x18000b57c  mov     [rbp+57h+var_38], r12
0x18000b580  cmp     rdi, 18h
0x18000b584  jb      loc_18000B993
0x18000b58a  mov     rdx, [rbx+8]
0x18000b58e  mov     rax, [rdx+10h]
0x18000b592  cmp     rax, rdi
0x18000b595  ja      loc_18000B98A
0x18000b59b  mov     rcx, [rdx+8]
0x18000b59f  test    rcx, rcx
0x18000b5a2  jz      loc_18000B981
0x18000b5a8  add     rax, 0FFFFFFFFFFFFFFE8h
0x18000b5ac  cmp     rcx, rax
0x18000b5af  ja      loc_18000B978
0x18000b5b5  cmp     dword ptr [rdx], 1
0x18000b5b8  jnz     loc_18000B96F
0x18000b5be  cmp     [rdx+4], r12d
0x18000b5c2  jnz     loc_18000B966
0x18000b5c8  lea     r8, [rdx+18h]
0x18000b5cc  mov     [rbp+57h+var_80], rcx
0x18000b5d0  mov     [rbp+57h+var_78], r8
0x18000b5d4  mov     rax, [rdx+10h]
0x18000b5d8  lea     rbx, [rdx+rax]
0x18000b5dc  sub     rdi, rax
0x18000b5df  jz      loc_18000B695
0x18000b5e5  cmp     rdi, 18h
0x18000b5e9  jb      loc_18000B993
0x18000b5ef  mov     rax, [rbx+10h]
0x18000b5f3  cmp     rax, rdi
0x18000b5f6  ja      loc_18000B98A
0x18000b5fc  lea     r9, [rbx+8]
0x18000b600  mov     rcx, [r9]
0x18000b603  test    rcx, rcx
0x18000b606  jz      loc_18000B981
0x18000b60c  add     rax, 0FFFFFFFFFFFFFFE8h
0x18000b610  cmp     rcx, rax
0x18000b613  ja      loc_18000B978
0x18000b619  mov     ecx, [rbx]
0x18000b61b  lea     eax, [rcx-2]
0x18000b61e  cmp     eax, 1
0x18000b621  ja      loc_18000B736
0x18000b627  lea     r8, [rbx+4]
0x18000b62b  cmp     [r8], r12d
0x18000b62e  jz      loc_18000B72A
0x18000b634  lea     rax, [rbx+18h]
0x18000b638  mov     [rbp+57h+arg_0], rax
0x18000b63c  lea     rax, [rbp+57h+arg_0]
0x18000b640  mov     [rsp+0D0h+var_B0], rax
0x18000b645  cmp     ecx, 2
0x18000b648  jnz     short loc_18000B65D
0x18000b64a  lea     rdx, [rbp+57h+var_A0]
0x18000b64e  lea     rcx, [rbp+57h+var_70]
0x18000b652  call    ??$try_emplace@AEB_KPEBE$0A@@?$map@IUReadOnlyBinary@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@4@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@utl@@_N@1@AEBIAEB_K$$QEAPEBE@Z; utl::map<uint,Kerb3961::ReadOnlyBinary,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ReadOnlyBinary>>>::try_emplace<unsigned __int64 const &,uchar const *,0>(uint const &,unsigned __int64 const &,uchar const * &&)
0x18000b657  cmp     [rbp+57h+var_98], r12b
0x18000b65b  jmp     short loc_18000B66E
0x18000b65d  lea     rdx, [rbp+57h+var_90]
0x18000b661  lea     rcx, [rbp+57h+var_50]
0x18000b665  call    ??$try_emplace@AEB_KPEBE$0A@@?$map@IUReadOnlyBinary@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@4@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@utl@@_N@1@AEBIAEB_K$$QEAPEBE@Z; utl::map<uint,Kerb3961::ReadOnlyBinary,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ReadOnlyBinary>>>::try_emplace<unsigned __int64 const &,uchar const *,0>(uint const &,unsigned __int64 const &,uchar const * &&)
0x18000b66a  cmp     [rbp+57h+var_88], r12b
0x18000b66e  jz      short loc_18000B681
0x18000b670  mov     rax, [rbx+10h]
0x18000b674  sub     rdi, rax
0x18000b677  jz      short loc_18000B68D
0x18000b679  add     rbx, rax
0x18000b67c  jmp     loc_18000B5E5
0x18000b681  lea     rcx, aResultSecond; "result.second"
0x18000b688  jmp     loc_18000B99A
0x18000b68d  mov     r8, [rbp+57h+var_78]
0x18000b691  mov     rcx, [rbp+57h+var_80]
0x18000b695  test    rcx, rcx
0x18000b698  jz      loc_18000BA0B
0x18000b69e  cmp     rcx, 14h
0x18000b6a2  jnz     loc_18000B958
0x18000b6a8  mov     eax, [r8]
0x18000b6ab  lea     r15, [r13+18h]
0x18000b6af  mov     cs:?g_supportedEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A, eax; Kerb3961::EncryptionTypeBitmask Kerb3961::g_supportedEncryptionTypes
0x18000b6b5  lea     rsi, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000b6bc  mov     eax, [r8+4]
0x18000b6c0  mov     cs:?g_assumedEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A, eax; Kerb3961::EncryptionTypeBitmask Kerb3961::g_assumedEncryptionTypes
0x18000b6c6  mov     eax, [r8+8]
0x18000b6ca  mov     cs:?g_realmEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A, eax; Kerb3961::EncryptionTypeBitmask Kerb3961::g_realmEncryptionTypes
0x18000b6d0  mov     eax, [r8+0Ch]
0x18000b6d4  mov     cs:?g_krbtgtEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A, eax; Kerb3961::EncryptionTypeBitmask Kerb3961::g_krbtgtEncryptionTypes
0x18000b6da  mov     eax, [r8+10h]
0x18000b6de  mov     cs:?g_trustEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A, eax; Kerb3961::EncryptionTypeBitmask Kerb3961::g_trustEncryptionTypes
0x18000b6e4  mov     rbx, [r15+10h]
0x18000b6e8  cmp     rbx, r15
0x18000b6eb  jz      loc_18000B81C
0x18000b6f1  mov     rdi, [rbx+20h]
0x18000b6f5  mov     rcx, rdi
0x18000b6f8  mov     rax, [rdi]
0x18000b6fb  mov     rax, [rax+0D8h]
0x18000b702  call    _guard_dispatch_icall
0x18000b707  lea     rcx, [rbp+57h+var_70]
0x18000b70b  cmp     [rbp+57h+var_60], rcx
0x18000b70f  jz      loc_18000B7F0
0x18000b715  mov     rcx, [rbp+57h+var_70]
0x18000b719  lea     rdx, [rbp+57h+var_70]
0x18000b71d  cmp     [rcx+18h], eax
0x18000b720  jnb     short loc_18000B742
0x18000b722  mov     r8d, 10h
0x18000b728  jmp     short loc_18000B74B
0x18000b72a  lea     rcx, aHeaderId0_0; "header->Id != 0"
0x18000b731  jmp     loc_18000B99A
0x18000b736  lea     rcx, aHeaderTypeMars; "header->Type == MarshaledPolicyType::En"...
0x18000b73d  jmp     loc_18000B99A
0x18000b742  mov     rdx, rcx
0x18000b745  mov     r8d, 8
0x18000b74b  mov     rcx, [r8+rcx]
0x18000b74f  cmp     rcx, rsi
0x18000b752  jnz     short loc_18000B71D
0x18000b754  lea     rcx, [rbp+57h+var_70]
0x18000b758  cmp     rdx, rcx
0x18000b75b  jz      loc_18000B7F0
0x18000b761  cmp     eax, [rdx+18h]
0x18000b764  jb      loc_18000B7F0
0x18000b76a  mov     rax, [rdi]
0x18000b76d  mov     rcx, rdi
0x18000b770  mov     rsi, [rax+68h]
0x18000b774  mov     rax, [rax+0D8h]
0x18000b77b  call    _guard_dispatch_icall
0x18000b780  mov     edx, eax
0x18000b782  lea     r8, [rbp+57h+var_70]
0x18000b786  lea     rax, [rbp+57h+var_70]
0x18000b78a  cmp     [rbp+57h+var_60], rax
0x18000b78e  jz      short loc_18000B7CB
0x18000b790  mov     rax, [rbp+57h+var_70]
0x18000b794  cmp     [rax+18h], edx
0x18000b797  jnb     short loc_18000B7A0
0x18000b799  mov     ecx, 10h
0x18000b79e  jmp     short loc_18000B7A8
0x18000b7a0  mov     r8, rax
0x18000b7a3  mov     ecx, 8
0x18000b7a8  mov     rax, [rax+rcx]
0x18000b7ac  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000b7b3  cmp     rax, rcx
0x18000b7b6  jnz     short loc_18000B794
0x18000b7b8  lea     rax, [rbp+57h+var_70]
0x18000b7bc  cmp     r8, rax
0x18000b7bf  jz      short loc_18000B7CB
0x18000b7c1  cmp     edx, [r8+18h]
0x18000b7c5  jnb     short loc_18000B7CD
0x18000b7c7  lea     r8, [rbp+57h+var_70]
0x18000b7cb  int     2Ch; Windows NT - assertion failure
0x18000b7cd  add     r8, 20h ; ' '
0x18000b7d1  lea     rdx, [rbp+57h+arg_0]
0x18000b7d5  mov     rcx, rdi
0x18000b7d8  mov     rax, rsi
0x18000b7db  call    _guard_dispatch_icall
0x18000b7e0  mov     edi, dword ptr [rbp+57h+arg_0]
0x18000b7e3  test    edi, edi
0x18000b7e5  js      short loc_18000B806
0x18000b7e7  lea     rsi, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000b7ee  jmp     short loc_18000B7F4
0x18000b7f0  mov     dword ptr [rbp+57h+arg_0], r12d
0x18000b7f4  mov     dl, 1
0x18000b7f6  mov     rcx, rbx
0x18000b7f9  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(bool)
0x18000b7fe  mov     rbx, rax
0x18000b801  jmp     loc_18000B6E8
0x18000b806  lea     rcx, aReaderApplycip; "reader.ApplyCipher(encryption.second)"
0x18000b80d  mov     edx, edi; char *
0x18000b80f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000b814  mov     [r14], edi
0x18000b817  jmp     loc_18000B9B7
0x18000b81c  lea     rsi, [r13+38h]
0x18000b820  mov     rbx, [rsi+10h]
0x18000b824  cmp     rbx, rsi
0x18000b827  jz      loc_18000B92E
0x18000b82d  mov     rdi, [rbx+20h]
0x18000b831  mov     rcx, rdi
0x18000b834  mov     rax, [rdi]
0x18000b837  mov     rax, [rax+68h]
0x18000b83b  call    _guard_dispatch_icall
0x18000b840  lea     rcx, [rbp+57h+var_50]
0x18000b844  cmp     [rbp+57h+var_40], rcx
0x18000b848  jz      loc_18000B918
0x18000b84e  mov     rcx, [rbp+57h+var_50]
0x18000b852  lea     rdx, [rbp+57h+var_50]
0x18000b856  cmp     [rcx+18h], eax
0x18000b859  jnb     short loc_18000B863
0x18000b85b  mov     r8d, 10h
0x18000b861  jmp     short loc_18000B86C
0x18000b863  mov     rdx, rcx
0x18000b866  mov     r8d, 8
0x18000b86c  mov     rcx, [rcx+r8]
0x18000b870  lea     r8, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000b877  cmp     rcx, r8
0x18000b87a  jnz     short loc_18000B856
0x18000b87c  lea     rcx, [rbp+57h+var_50]
0x18000b880  cmp     rdx, rcx
0x18000b883  jz      loc_18000B918
0x18000b889  cmp     eax, [rdx+18h]
0x18000b88c  jb      loc_18000B918
0x18000b892  mov     rax, [rdi]
0x18000b895  mov     rcx, rdi
0x18000b898  mov     r15, [rax+50h]
0x18000b89c  mov     rax, [rax+68h]
0x18000b8a0  call    _guard_dispatch_icall
0x18000b8a5  mov     edx, eax
0x18000b8a7  lea     r8, [rbp+57h+var_50]
0x18000b8ab  lea     rax, [rbp+57h+var_50]
0x18000b8af  cmp     [rbp+57h+var_40], rax
0x18000b8b3  jz      short loc_18000B8F0
0x18000b8b5  mov     rax, [rbp+57h+var_50]
0x18000b8b9  cmp     [rax+18h], edx
0x18000b8bc  jnb     short loc_18000B8C5
0x18000b8be  mov     ecx, 10h
0x18000b8c3  jmp     short loc_18000B8CD
0x18000b8c5  mov     r8, rax
0x18000b8c8  mov     ecx, 8
0x18000b8cd  mov     rax, [rax+rcx]
0x18000b8d1  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000b8d8  cmp     rax, rcx
0x18000b8db  jnz     short loc_18000B8B9
0x18000b8dd  lea     rax, [rbp+57h+var_50]
0x18000b8e1  cmp     r8, rax
0x18000b8e4  jz      short loc_18000B8F0
0x18000b8e6  cmp     edx, [r8+18h]
0x18000b8ea  jnb     short loc_18000B8F2
0x18000b8ec  lea     r8, [rbp+57h+var_50]
0x18000b8f0  int     2Ch; Windows NT - assertion failure
0x18000b8f2  add     r8, 20h ; ' '
0x18000b8f6  lea     rdx, [rbp+57h+arg_0]
0x18000b8fa  mov     rcx, rdi
0x18000b8fd  mov     rax, r15
0x18000b900  call    _guard_dispatch_icall
0x18000b905  mov     edi, dword ptr [rbp+57h+arg_0]
0x18000b908  test    edi, edi
0x18000b90a  jns     short loc_18000B91C
0x18000b90c  lea     rcx, aReaderApplyche; "reader.ApplyChecksum(checksum.second)"
0x18000b913  jmp     loc_18000B80D
0x18000b918  mov     dword ptr [rbp+57h+arg_0], r12d
0x18000b91c  mov     dl, 1
0x18000b91e  mov     rcx, rbx
0x18000b921  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(bool)
0x18000b926  mov     rbx, rax
0x18000b929  jmp     loc_18000B824
0x18000b92e  lea     rdx, [rbp+57h+arg_0]
0x18000b932  mov     rcx, r13
0x18000b935  call    ?OrderCiphers@CipherPolicyImpl@Kerb3961@@QEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@XZ; Kerb3961::CipherPolicyImpl::OrderCiphers(void)
0x18000b93a  mov     ebx, [rax]
0x18000b93c  test    ebx, ebx
0x18000b93e  jns     short loc_18000B953
0x18000b940  mov     edx, ebx; char *
0x18000b942  lea     rcx, aOrderciphers; "OrderCiphers()"
0x18000b949  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000b94e  mov     [r14], ebx
0x18000b951  jmp     short loc_18000B9B7
0x18000b953  mov     [r14], r12d
0x18000b956  jmp     short loc_18000B9B7
0x18000b958  lea     rcx, aGlobalblobLeng; "globalBlob.length == sizeof(MarshaledGl"...
0x18000b95f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000b964  jmp     short loc_18000B9B0
0x18000b966  lea     rcx, aHeaderId0; "header->Id == 0"
0x18000b96d  jmp     short loc_18000B99A
0x18000b96f  lea     rcx, aHeaderTypeMars_0; "header->Type == MarshaledPolicyType::Gl"...
0x18000b976  jmp     short loc_18000B99A
0x18000b978  lea     rcx, aHeaderContentl; "header->ContentLength <= header->TotalL"...
0x18000b97f  jmp     short loc_18000B99A
0x18000b981  lea     rcx, aHeaderContentl_0; "header->ContentLength > 0"
0x18000b988  jmp     short loc_18000B99A
0x18000b98a  lea     rcx, aHeaderTotallen; "header->TotalLength <= remainingSize"
0x18000b991  jmp     short loc_18000B99A
0x18000b993  lea     rcx, aRemainingsizeM; "remainingSize >= MarshaledPolicyHeaderS"...
0x18000b99a  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000b99f  mov     edx, 0C000000Dh; char *
0x18000b9a4  lea     rcx, aReaderReadMars; "reader.Read(marshaledPolicies)"
0x18000b9ab  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000b9b0  mov     dword ptr [r14], 0C000000Dh
  ... truncated ...
```
