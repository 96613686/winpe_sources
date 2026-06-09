# Kerb3961::CipherPolicyImpl::ApplyCipherPolicies(Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000a2a0`
- end: `0x18000a78b`
- name: `?ApplyCipherPolicies@CipherPolicyImpl@Kerb3961@@UEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `1259`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callees

- `0x180002c64`
- `0x180002fc0`
- `0x1800032f4`
- `0x180003380`
- `0x1800033f4`
- `0x180003d70`
- `0x18000a2a0`
- `0x18000d1ec`
- `0x18000e558`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a75a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a75a`

## string_xrefs

- `0x18000a72c`: `reader.Read(marshaledPolicies)`
- `0x18000a596`: `reader.ApplyCipher(encryption.second)`
- `0x18000a69b`: `reader.ApplyChecksum(checksum.second)`
- `0x18000a77e`: `You can only retrieve the global policy following a successful call to Read()`

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
  int v15; // ecx
  bool v16; // zf
  __int64 v17; // rax
  char *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rbx
  unsigned int v21; // eax
  __int64 v22; // rcx
  _QWORD *v23; // rdx
  __int64 v24; // r8
  void (__fastcall *v25)(__int64, char **, _QWORD *); // rdi
  unsigned int v26; // edx
  _QWORD *v27; // r8
  __int64 v28; // rax
  __int64 v29; // rcx
  int v30; // r8d
  int v31; // ebx
  char *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rbx
  unsigned int v35; // eax
  __int64 v36; // rcx
  _QWORD *v37; // rdx
  __int64 v38; // r8
  void (__fastcall *v39)(__int64, char **, _QWORD *); // rsi
  unsigned int v40; // edx
  _QWORD *v41; // r8
  __int64 v42; // rax
  __int64 v43; // rcx
  int v44; // r8d
  _BYTE v46[16]; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v47[16]; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int64 v48; // [rsp+50h] [rbp-29h]
  _DWORD *v49; // [rsp+58h] [rbp-21h]
  _QWORD v50[2]; // [rsp+60h] [rbp-19h] BYREF
  _QWORD *v51; // [rsp+70h] [rbp-9h]
  __int64 v52; // [rsp+78h] [rbp-1h]
  _QWORD v53[2]; // [rsp+80h] [rbp+7h] BYREF
  _QWORD *v54; // [rsp+90h] [rbp+17h]
  __int64 v55; // [rsp+98h] [rbp+1Fh]
  char *v56; // [rsp+E0h] [rbp+67h] BYREF
  PSRWLOCK SRWLock; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v58; // [rsp+F8h] [rbp+7Fh] BYREF

  wil::srwlock::lock_exclusive(a1 + 16, &SRWLock);
  v7 = *a3;
  v50[0] = v50;
  v48 = 0;
  v50[1] = v50;
  v51 = v50;
  v53[0] = v53;
  v53[1] = v53;
  v54 = v53;
  v49 = 0;
  v52 = 0;
  v55 = 0;
  if ( v7 < 0x18 )
  {
LABEL_85:
    v18 = "remainingSize >= MarshaledPolicyHeaderSize";
    goto LABEL_86;
  }
  v6 = a3[1];
  v8 = *(_QWORD *)(v6 + 16);
  if ( v8 > v7 )
  {
LABEL_84:
    v18 = "header->TotalLength <= remainingSize";
    goto LABEL_86;
  }
  v9 = *(_QWORD *)(v6 + 8);
  if ( !v9 )
  {
LABEL_83:
    v18 = "header->ContentLength > 0";
    goto LABEL_86;
  }
  if ( v9 > v8 - 24 )
  {
LABEL_82:
    v18 = "header->ContentLength <= header->TotalLength - MarshaledPolicyHeaderSize";
    goto LABEL_86;
  }
  if ( *(_DWORD *)v6 != 1 )
  {
    v18 = "header->Type == MarshaledPolicyType::Global";
    goto LABEL_86;
  }
  if ( *(_DWORD *)(v6 + 4) )
  {
    v18 = "header->Id == 0";
    goto LABEL_86;
  }
  v10 = (_DWORD *)(v6 + 24);
  v48 = *(_QWORD *)(v6 + 8);
  v49 = (_DWORD *)(v6 + 24);
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
    if ( !*((_QWORD *)v12 + 1) )
      goto LABEL_83;
    if ( *((_QWORD *)v12 + 1) > v14 - 24 )
      goto LABEL_82;
    v15 = *v12;
    if ( (unsigned int)(*v12 - 2) > 1 )
    {
      v18 = "header->Type == MarshaledPolicyType::Encryption || header->Type == MarshaledPolicyType::Checksum";
      goto LABEL_86;
    }
    if ( !v12[1] )
    {
      v18 = "header->Id != 0";
LABEL_86:
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v18, (const char *)v6);
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"reader.Read(marshaledPolicies)",
        (const char *)0xC000000DLL,
        v44);
      goto LABEL_87;
    }
    v56 = (char *)(v12 + 6);
    if ( v15 == 2 )
    {
      utl::map<unsigned int,Kerb3961::ReadOnlyBinary,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ReadOnlyBinary>>>::try_emplace<unsigned __int64 const &,unsigned char const *,0>(
        v50,
        v46);
      v16 = v46[8] == 0;
    }
    else
    {
      utl::map<unsigned int,Kerb3961::ReadOnlyBinary,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ReadOnlyBinary>>>::try_emplace<unsigned __int64 const &,unsigned char const *,0>(
        v53,
        v47);
      v16 = v47[8] == 0;
    }
    if ( v16 )
    {
      v18 = "result.second";
      goto LABEL_86;
    }
    v17 = *((_QWORD *)v12 + 2);
    v13 -= v17;
    if ( !v13 )
      break;
    v12 = (int *)((char *)v12 + v17);
  }
  v10 = v49;
  v9 = v48;
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
  v19 = *(_QWORD *)(a1 + 40);
  v58 = v19;
  while ( v19 != a1 + 24 )
  {
    v20 = *(_QWORD *)(v19 + 32);
    v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 216LL))(v20);
    if ( v51 == v50 )
      goto LABEL_48;
    v22 = v50[0];
    v23 = v50;
    do
    {
      if ( *(_DWORD *)(v22 + 24) >= v21 )
      {
        v23 = (_QWORD *)v22;
        v24 = 8;
      }
      else
      {
        v24 = 16;
      }
      v22 = *(_QWORD *)(v24 + v22);
    }
    while ( (void **)v22 != &utl::_TreeSentinel );
    if ( v23 == v50 || v21 < *((_DWORD *)v23 + 6) )
    {
LABEL_48:
      LODWORD(v56) = 0;
      goto LABEL_49;
    }
    v25 = *(void (__fastcall **)(__int64, char **, _QWORD *))(*(_QWORD *)v20 + 104LL);
    v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 216LL))(v20);
    v27 = v50;
    if ( v51 != v50 )
    {
      v28 = v50[0];
      do
      {
        if ( *(_DWORD *)(v28 + 24) >= v26 )
        {
          v27 = (_QWORD *)v28;
          v29 = 8;
        }
        else
        {
          v29 = 16;
        }
        v28 = *(_QWORD *)(v28 + v29);
      }
      while ( (void **)v28 != &utl::_TreeSentinel );
      if ( v27 != v50 )
      {
        if ( v26 >= *((_DWORD *)v27 + 6) )
          goto LABEL_46;
        v27 = v50;
      }
    }
    __int2c();
LABEL_46:
    v25(v20, &v56, v27 + 4);
    v31 = (int)v56;
    if ( (int)v56 < 0 )
    {
      v32 = "reader.ApplyCipher(encryption.second)";
      goto LABEL_51;
    }
LABEL_49:
    utl::_TreeConstIt<utl::pair<unsigned int const,Kerb3961::EncryptionAlgorithm *>>::operator++(&v58);
    v19 = v58;
  }
  v33 = *(_QWORD *)(a1 + 72);
  v58 = v33;
  while ( 2 )
  {
    if ( v33 != a1 + 56 )
    {
      v34 = *(_QWORD *)(v33 + 32);
      v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 104LL))(v34);
      if ( v54 == v53 )
        goto LABEL_74;
      v36 = v53[0];
      v37 = v53;
      do
      {
        if ( *(_DWORD *)(v36 + 24) >= v35 )
        {
          v37 = (_QWORD *)v36;
          v38 = 8;
        }
        else
        {
          v38 = 16;
        }
        v36 = *(_QWORD *)(v36 + v38);
      }
      while ( (void **)v36 != &utl::_TreeSentinel );
      if ( v37 == v53 || v35 < *((_DWORD *)v37 + 6) )
      {
LABEL_74:
        LODWORD(v56) = 0;
      }
      else
      {
        v39 = *(void (__fastcall **)(__int64, char **, _QWORD *))(*(_QWORD *)v34 + 80LL);
        v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 104LL))(v34);
        v41 = v53;
        if ( v54 == v53 )
          goto LABEL_71;
        v42 = v53[0];
        do
        {
          if ( *(_DWORD *)(v42 + 24) >= v40 )
          {
            v41 = (_QWORD *)v42;
            v43 = 8;
          }
          else
          {
            v43 = 16;
          }
          v42 = *(_QWORD *)(v42 + v43);
        }
        while ( (void **)v42 != &utl::_TreeSentinel );
        if ( v41 == v53 )
        {
LABEL_71:
          __int2c();
        }
        else if ( v40 < *((_DWORD *)v41 + 6) )
        {
          v41 = v53;
          goto LABEL_71;
        }
        v39(v34, &v56, v41 + 4);
        v31 = (int)v56;
        if ( (int)v56 < 0 )
        {
          v32 = "reader.ApplyChecksum(checksum.second)";
          goto LABEL_51;
        }
      }
      utl::_TreeConstIt<utl::pair<unsigned int const,Kerb3961::EncryptionAlgorithm *>>::operator++(&v58);
      v33 = v58;
      continue;
    }
    break;
  }
  v31 = *(_DWORD *)Kerb3961::CipherPolicyImpl::OrderCiphers(a1, &v56);
  if ( v31 >= 0 )
  {
    *a2 = 0;
  }
  else
  {
    v32 = "OrderCiphers()";
LABEL_51:
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v32, (const char *)(unsigned int)v31, v30);
    *a2 = v31;
  }
LABEL_88:
  utl::_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>::~_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>(v53);
  utl::_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>::~_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>(v50);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return a2;
}

```

## disassembly

```asm
0x18000a2a0  mov     [rsp-8+arg_8], rbx
0x18000a2a5  push    rbp
0x18000a2a6  push    rsi
0x18000a2a7  push    rdi
0x18000a2a8  push    r12
0x18000a2aa  push    r13
0x18000a2ac  push    r14
0x18000a2ae  push    r15
0x18000a2b0  lea     rbp, [rsp-27h]
0x18000a2b5  sub     rsp, 0A0h
0x18000a2bc  mov     r14, rdx
0x18000a2bf  mov     r15, rcx
0x18000a2c2  add     rcx, 10h
0x18000a2c6  lea     rdx, [rbp+57h+SRWLock]
0x18000a2ca  mov     rbx, r8
0x18000a2cd  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x18000a2d2  mov     rdi, [rbx]
0x18000a2d5  lea     rax, [rbp+57h+var_70]
0x18000a2d9  xor     r12d, r12d
0x18000a2dc  mov     [rbp+57h+var_70], rax
0x18000a2e0  mov     [rbp+57h+var_80], r12
0x18000a2e4  lea     rax, [rbp+57h+var_70]
0x18000a2e8  mov     [rbp+57h+var_68], rax
0x18000a2ec  mov     [rbp+57h+var_60], rax
0x18000a2f0  lea     rax, [rbp+57h+var_50]
0x18000a2f4  mov     [rbp+57h+var_50], rax
0x18000a2f8  lea     rax, [rbp+57h+var_50]
0x18000a2fc  mov     [rbp+57h+var_48], rax
0x18000a300  mov     [rbp+57h+var_40], rax
0x18000a304  mov     [rbp+57h+var_78], r12
0x18000a308  mov     [rbp+57h+var_58], r12
0x18000a30c  mov     [rbp+57h+var_38], r12
0x18000a310  cmp     rdi, 18h
0x18000a314  jb      loc_18000A71B
0x18000a31a  mov     rdx, [rbx+8]
0x18000a31e  mov     rax, [rdx+10h]
0x18000a322  cmp     rax, rdi
0x18000a325  ja      loc_18000A712
0x18000a32b  mov     rcx, [rdx+8]
0x18000a32f  test    rcx, rcx
0x18000a332  jz      loc_18000A709
0x18000a338  add     rax, 0FFFFFFFFFFFFFFE8h
0x18000a33c  cmp     rcx, rax
0x18000a33f  ja      loc_18000A700
0x18000a345  cmp     dword ptr [rdx], 1
0x18000a348  jnz     loc_18000A6F7
0x18000a34e  cmp     [rdx+4], r12d
0x18000a352  jnz     loc_18000A6EE
0x18000a358  lea     r8, [rdx+18h]
0x18000a35c  mov     [rbp+57h+var_80], rcx
0x18000a360  mov     [rbp+57h+var_78], r8
0x18000a364  mov     rax, [rdx+10h]
0x18000a368  lea     rbx, [rdx+rax]
0x18000a36c  sub     rdi, rax
0x18000a36f  jz      loc_18000A422
0x18000a375  cmp     rdi, 18h
0x18000a379  jb      loc_18000A71B
0x18000a37f  mov     rax, [rbx+10h]
0x18000a383  cmp     rax, rdi
0x18000a386  ja      loc_18000A712
0x18000a38c  lea     r9, [rbx+8]
0x18000a390  cmp     [r9], r12
0x18000a393  jbe     loc_18000A709
0x18000a399  add     rax, 0FFFFFFFFFFFFFFE8h
0x18000a39d  cmp     [r9], rax
0x18000a3a0  ja      loc_18000A700
0x18000a3a6  mov     ecx, [rbx]
0x18000a3a8  lea     eax, [rcx-2]
0x18000a3ab  cmp     eax, 1
0x18000a3ae  ja      loc_18000A4C8
0x18000a3b4  lea     r8, [rbx+4]
0x18000a3b8  cmp     [r8], r12d
0x18000a3bb  jz      loc_18000A4BC
0x18000a3c1  lea     rax, [rbx+18h]
0x18000a3c5  mov     [rbp+57h+arg_0], rax
0x18000a3c9  lea     rax, [rbp+57h+arg_0]
0x18000a3cd  mov     [rsp+0D0h+var_B0], rax
0x18000a3d2  cmp     ecx, 2
0x18000a3d5  jnz     short loc_18000A3EA
0x18000a3d7  lea     rdx, [rbp+57h+var_A0]
0x18000a3db  lea     rcx, [rbp+57h+var_70]
0x18000a3df  call    ??$try_emplace@AEB_KPEBE$0A@@?$map@IUReadOnlyBinary@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@4@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@utl@@_N@1@AEBIAEB_K$$QEAPEBE@Z; utl::map<uint,Kerb3961::ReadOnlyBinary,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ReadOnlyBinary>>>::try_emplace<unsigned __int64 const &,uchar const *,0>(uint const &,unsigned __int64 const &,uchar const * &&)
0x18000a3e4  cmp     [rbp+57h+var_98], r12b
0x18000a3e8  jmp     short loc_18000A3FB
0x18000a3ea  lea     rdx, [rbp+57h+var_90]
0x18000a3ee  lea     rcx, [rbp+57h+var_50]
0x18000a3f2  call    ??$try_emplace@AEB_KPEBE$0A@@?$map@IUReadOnlyBinary@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@4@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@utl@@_N@1@AEBIAEB_K$$QEAPEBE@Z; utl::map<uint,Kerb3961::ReadOnlyBinary,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ReadOnlyBinary>>>::try_emplace<unsigned __int64 const &,uchar const *,0>(uint const &,unsigned __int64 const &,uchar const * &&)
0x18000a3f7  cmp     [rbp+57h+var_88], r12b
0x18000a3fb  jz      short loc_18000A40E
0x18000a3fd  mov     rax, [rbx+10h]
0x18000a401  sub     rdi, rax
0x18000a404  jz      short loc_18000A41A
0x18000a406  add     rbx, rax
0x18000a409  jmp     loc_18000A375
0x18000a40e  lea     rcx, aResultSecond; "result.second"
0x18000a415  jmp     loc_18000A722
0x18000a41a  mov     r8, [rbp+57h+var_78]
0x18000a41e  mov     rcx, [rbp+57h+var_80]
0x18000a422  test    rcx, rcx
0x18000a425  jz      loc_18000A77E
0x18000a42b  cmp     rcx, 14h
0x18000a42f  jnz     loc_18000A6E0
0x18000a435  mov     eax, [r8]
0x18000a438  lea     rsi, [r15+18h]
0x18000a43c  mov     cs:?g_supportedEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A, eax; Kerb3961::EncryptionTypeBitmask Kerb3961::g_supportedEncryptionTypes
0x18000a442  lea     r13d, [rcx-4]
0x18000a446  mov     eax, [r8+4]
0x18000a44a  lea     rdi, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000a451  mov     cs:?g_assumedEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A, eax; Kerb3961::EncryptionTypeBitmask Kerb3961::g_assumedEncryptionTypes
0x18000a457  mov     eax, [r8+8]
0x18000a45b  mov     cs:?g_realmEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A, eax; Kerb3961::EncryptionTypeBitmask Kerb3961::g_realmEncryptionTypes
0x18000a461  mov     eax, [r8+0Ch]
0x18000a465  mov     cs:?g_krbtgtEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A, eax; Kerb3961::EncryptionTypeBitmask Kerb3961::g_krbtgtEncryptionTypes
0x18000a46b  mov     eax, [r8+10h]
0x18000a46f  mov     cs:?g_trustEncryptionTypes@Kerb3961@@3TEncryptionTypeBitmask@1@A, eax; Kerb3961::EncryptionTypeBitmask Kerb3961::g_trustEncryptionTypes
0x18000a475  mov     rax, [rsi+10h]
0x18000a479  mov     [rbp+57h+arg_18], rax
0x18000a47d  cmp     rax, rsi
0x18000a480  jz      loc_18000A5AC
0x18000a486  mov     rbx, [rax+20h]
0x18000a48a  mov     rcx, rbx
0x18000a48d  mov     rax, [rbx]
0x18000a490  mov     rax, [rax+0D8h]
0x18000a497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a49c  lea     rcx, [rbp+57h+var_70]
0x18000a4a0  cmp     [rbp+57h+var_60], rcx
0x18000a4a4  jz      loc_18000A580
0x18000a4aa  mov     rcx, [rbp+57h+var_70]
0x18000a4ae  lea     rdx, [rbp+57h+var_70]
0x18000a4b2  cmp     [rcx+18h], eax
0x18000a4b5  jnb     short loc_18000A4D4
0x18000a4b7  mov     r8, r13
0x18000a4ba  jmp     short loc_18000A4DD
0x18000a4bc  lea     rcx, aHeaderId0_0; "header->Id != 0"
0x18000a4c3  jmp     loc_18000A722
0x18000a4c8  lea     rcx, aHeaderTypeMars; "header->Type == MarshaledPolicyType::En"...
0x18000a4cf  jmp     loc_18000A722
0x18000a4d4  mov     rdx, rcx
0x18000a4d7  mov     r8d, 8
0x18000a4dd  mov     rcx, [r8+rcx]
0x18000a4e1  cmp     rcx, rdi
0x18000a4e4  jnz     short loc_18000A4B2
0x18000a4e6  lea     rcx, [rbp+57h+var_70]
0x18000a4ea  cmp     rdx, rcx
0x18000a4ed  jz      loc_18000A580
0x18000a4f3  cmp     eax, [rdx+18h]
0x18000a4f6  jb      loc_18000A580
0x18000a4fc  mov     rax, [rbx]
0x18000a4ff  mov     rcx, rbx
0x18000a502  mov     rdi, [rax+68h]
0x18000a506  mov     rax, [rax+0D8h]
0x18000a50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a512  mov     edx, eax
0x18000a514  lea     r8, [rbp+57h+var_70]
0x18000a518  lea     rax, [rbp+57h+var_70]
0x18000a51c  cmp     [rbp+57h+var_60], rax
0x18000a520  jz      short loc_18000A55B
0x18000a522  mov     rax, [rbp+57h+var_70]
0x18000a526  cmp     [rax+18h], edx
0x18000a529  jnb     short loc_18000A530
0x18000a52b  mov     rcx, r13
0x18000a52e  jmp     short loc_18000A538
0x18000a530  mov     r8, rax
0x18000a533  mov     ecx, 8
0x18000a538  mov     rax, [rax+rcx]
0x18000a53c  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000a543  cmp     rax, rcx
0x18000a546  jnz     short loc_18000A526
0x18000a548  lea     rax, [rbp+57h+var_70]
0x18000a54c  cmp     r8, rax
0x18000a54f  jz      short loc_18000A55B
0x18000a551  cmp     edx, [r8+18h]
0x18000a555  jnb     short loc_18000A55D
0x18000a557  lea     r8, [rbp+57h+var_70]
0x18000a55b  int     2Ch; Windows NT - assertion failure
0x18000a55d  add     r8, 20h ; ' '
0x18000a561  lea     rdx, [rbp+57h+arg_0]
0x18000a565  mov     rcx, rbx
0x18000a568  mov     rax, rdi
0x18000a56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a570  mov     ebx, dword ptr [rbp+57h+arg_0]
0x18000a573  test    ebx, ebx
0x18000a575  js      short loc_18000A596
0x18000a577  lea     rdi, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000a57e  jmp     short loc_18000A584
0x18000a580  mov     dword ptr [rbp+57h+arg_0], r12d
0x18000a584  lea     rcx, [rbp+57h+arg_18]
0x18000a588  call    ??E?$_TreeConstIt@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>::operator++(void)
0x18000a58d  mov     rax, [rbp+57h+arg_18]
0x18000a591  jmp     loc_18000A47D
0x18000a596  lea     rcx, aReaderApplycip; "reader.ApplyCipher(encryption.second)"
0x18000a59d  mov     edx, ebx; char *
0x18000a59f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000a5a4  mov     [r14], ebx
0x18000a5a7  jmp     loc_18000A73F
0x18000a5ac  lea     rdi, [r15+38h]
0x18000a5b0  mov     rax, [rdi+10h]
0x18000a5b4  mov     [rbp+57h+arg_18], rax
0x18000a5b8  cmp     rax, rdi
0x18000a5bb  jz      loc_18000A6BD
0x18000a5c1  mov     rbx, [rax+20h]
0x18000a5c5  mov     rcx, rbx
0x18000a5c8  mov     rax, [rbx]
0x18000a5cb  mov     rax, [rax+68h]
0x18000a5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5d4  lea     rcx, [rbp+57h+var_50]
0x18000a5d8  cmp     [rbp+57h+var_40], rcx
0x18000a5dc  jz      loc_18000A6A7
0x18000a5e2  mov     rcx, [rbp+57h+var_50]
0x18000a5e6  lea     rdx, [rbp+57h+var_50]
0x18000a5ea  cmp     [rcx+18h], eax
0x18000a5ed  jnb     short loc_18000A5F4
0x18000a5ef  mov     r8, r13
0x18000a5f2  jmp     short loc_18000A5FD
0x18000a5f4  mov     rdx, rcx
0x18000a5f7  mov     r8d, 8
0x18000a5fd  mov     rcx, [rcx+r8]
0x18000a601  lea     r8, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000a608  cmp     rcx, r8
0x18000a60b  jnz     short loc_18000A5EA
0x18000a60d  lea     rcx, [rbp+57h+var_50]
0x18000a611  cmp     rdx, rcx
0x18000a614  jz      loc_18000A6A7
0x18000a61a  cmp     eax, [rdx+18h]
0x18000a61d  jb      loc_18000A6A7
0x18000a623  mov     rax, [rbx]
0x18000a626  mov     rcx, rbx
0x18000a629  mov     rsi, [rax+50h]
0x18000a62d  mov     rax, [rax+68h]
0x18000a631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a636  mov     edx, eax
0x18000a638  lea     r8, [rbp+57h+var_50]
0x18000a63c  lea     rax, [rbp+57h+var_50]
0x18000a640  cmp     [rbp+57h+var_40], rax
0x18000a644  jz      short loc_18000A67F
0x18000a646  mov     rax, [rbp+57h+var_50]
0x18000a64a  cmp     [rax+18h], edx
0x18000a64d  jnb     short loc_18000A654
0x18000a64f  mov     rcx, r13
0x18000a652  jmp     short loc_18000A65C
0x18000a654  mov     r8, rax
0x18000a657  mov     ecx, 8
0x18000a65c  mov     rax, [rax+rcx]
0x18000a660  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000a667  cmp     rax, rcx
0x18000a66a  jnz     short loc_18000A64A
0x18000a66c  lea     rax, [rbp+57h+var_50]
0x18000a670  cmp     r8, rax
0x18000a673  jz      short loc_18000A67F
0x18000a675  cmp     edx, [r8+18h]
0x18000a679  jnb     short loc_18000A681
0x18000a67b  lea     r8, [rbp+57h+var_50]
0x18000a67f  int     2Ch; Windows NT - assertion failure
0x18000a681  add     r8, 20h ; ' '
0x18000a685  lea     rdx, [rbp+57h+arg_0]
0x18000a689  mov     rcx, rbx
0x18000a68c  mov     rax, rsi
0x18000a68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a694  mov     ebx, dword ptr [rbp+57h+arg_0]
0x18000a697  test    ebx, ebx
0x18000a699  jns     short loc_18000A6AB
0x18000a69b  lea     rcx, aReaderApplyche; "reader.ApplyChecksum(checksum.second)"
0x18000a6a2  jmp     loc_18000A59D
0x18000a6a7  mov     dword ptr [rbp+57h+arg_0], r12d
0x18000a6ab  lea     rcx, [rbp+57h+arg_18]
0x18000a6af  call    ??E?$_TreeConstIt@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>::operator++(void)
0x18000a6b4  mov     rax, [rbp+57h+arg_18]
0x18000a6b8  jmp     loc_18000A5B8
0x18000a6bd  lea     rdx, [rbp+57h+arg_0]
0x18000a6c1  mov     rcx, r15
0x18000a6c4  call    ?OrderCiphers@CipherPolicyImpl@Kerb3961@@QEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@XZ; Kerb3961::CipherPolicyImpl::OrderCiphers(void)
0x18000a6c9  mov     ebx, [rax]
0x18000a6cb  test    ebx, ebx
0x18000a6cd  jns     short loc_18000A6DB
0x18000a6cf  lea     rcx, aOrderciphers; "OrderCiphers()"
0x18000a6d6  jmp     loc_18000A59D
0x18000a6db  mov     [r14], r12d
0x18000a6de  jmp     short loc_18000A73F
0x18000a6e0  lea     rcx, aGlobalblobLeng; "globalBlob.length == sizeof(MarshaledGl"...
0x18000a6e7  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000a6ec  jmp     short loc_18000A738
0x18000a6ee  lea     rcx, aHeaderId0; "header->Id == 0"
0x18000a6f5  jmp     short loc_18000A722
0x18000a6f7  lea     rcx, aHeaderTypeMars_0; "header->Type == MarshaledPolicyType::Gl"...
0x18000a6fe  jmp     short loc_18000A722
0x18000a700  lea     rcx, aHeaderContentl; "header->ContentLength <= header->TotalL"...
0x18000a707  jmp     short loc_18000A722
0x18000a709  lea     rcx, aHeaderContentl_0; "header->ContentLength > 0"
0x18000a710  jmp     short loc_18000A722
0x18000a712  lea     rcx, aHeaderTotallen; "header->TotalLength <= remainingSize"
0x18000a719  jmp     short loc_18000A722
0x18000a71b  lea     rcx, aRemainingsizeM; "remainingSize >= MarshaledPolicyHeaderS"...
0x18000a722  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000a727  mov     edx, 0C000000Dh; char *
0x18000a72c  lea     rcx, aReaderReadMars; "reader.Read(marshaledPolicies)"
0x18000a733  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000a738  mov     dword ptr [r14], 0C000000Dh
0x18000a73f  lea     rcx, [rbp+57h+var_50]
0x18000a743  call    ??1?$_Tree@IU?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@U?$less@I@2@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<uint,utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>,0>::~_Tree<uint,utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>,0>(void)
0x18000a748  lea     rcx, [rbp+57h+var_70]
  ... truncated ...
```
