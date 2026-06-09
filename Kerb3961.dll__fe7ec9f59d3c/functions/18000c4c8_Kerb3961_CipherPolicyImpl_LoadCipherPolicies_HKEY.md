# Kerb3961::CipherPolicyImpl::LoadCipherPolicies(HKEY__ *)

- ea: `0x18000c4c8`
- end: `0x18000c93e`
- name: `?LoadCipherPolicies@CipherPolicyImpl@Kerb3961@@QEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@PEAUHKEY__@@@Z`
- size: `1142`
- prototype: `int *__fastcall(__int64, int *, HKEY)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000c400`
- `0x18000d8b0`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180003380`
- `0x1800033f4`
- `0x180003d70`
- `0x18000c4c8`
- `0x18000c944`
- `0x18000e05c`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c8f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c8f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c656`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c813`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c656`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c813`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c627`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c68d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c6dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c749`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c7e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c84a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c89a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c627`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c68d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c6dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c749`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c7e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c84a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c89a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c62f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c695`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c7ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c852`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c62f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c695`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c7ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c61c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c61c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c83f`

## string_xrefs

- `0x18000c924`: `A policy must either be for the computer or domain`
- `0x18000c710`: `terminatedCopy.assign(name.buffer, name.length)`
- `0x18000c8cd`: `terminatedCopy.assign(name.buffer, name.length)`

## pseudocode

```c
int *__fastcall Kerb3961::CipherPolicyImpl::LoadCipherPolicies(__int64 a1, int *a2, HKEY a3)
{
  const unsigned __int16 *v6; // rdx
  int v7; // edi
  int *v8; // rbx
  int *PolicyDword; // rax
  wchar_t **v10; // rbx
  int *v11; // rax
  __int64 v12; // rax
  __int64 v13; // r14
  const unsigned __int16 *v14; // rdx
  const char *v15; // rdx
  HKEY v16; // rsi
  DWORD v17; // ebx
  LSTATUS v18; // eax
  HKEY v19; // r8
  HKEY v20; // rsi
  DWORD v21; // ebx
  int *v22; // rax
  int *v23; // rax
  WCHAR *v24; // rcx
  WCHAR *v25; // rax
  __int64 v26; // rax
  __int64 v27; // r14
  const unsigned __int16 *v28; // rdx
  const char *v29; // rdx
  HKEY v30; // rsi
  DWORD LastError; // ebx
  LSTATUS v32; // eax
  HKEY v33; // r8
  HKEY v34; // rsi
  DWORD v35; // ebx
  int *v36; // rax
  int *v37; // rax
  HKEY hKey; // [rsp+30h] [rbp-39h] BYREF
  __int64 i; // [rsp+38h] [rbp-31h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-29h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+48h] [rbp-21h] BYREF
  _WORD v43[8]; // [rsp+58h] [rbp-11h] BYREF
  LPCWSTR v44[2]; // [rsp+68h] [rbp-1h] BYREF
  _WORD v45[8]; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v46; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v47; // [rsp+90h] [rbp+27h]
  int v48; // [rsp+98h] [rbp+2Fh]
  char v49; // [rsp+D0h] [rbp+67h] BYREF
  char v50; // [rsp+E8h] [rbp+7Fh] BYREF

  wil::srwlock::lock_exclusive(&Kerb3961::g_cipherLock, &SRWLock);
  if ( (*(_BYTE *)(a1 + 12) & 3) == 0 || (((*(_BYTE *)(a1 + 12) & 3) - 1LL) & *(_BYTE *)(a1 + 12) & 3) != 0 )
    Kerb3961::ConsistencyFail((Kerb3961 *)L"A policy must either be for the computer or domain", v6);
  v7 = 0;
  if ( (*(_BYTE *)(a1 + 12) & 2) != 0 )
  {
    v8 = (int *)&off_18001F9E0;
    do
    {
      PolicyDword = (int *)Kerb3961::CipherPolicyImpl::LoadPolicyDword(
                             a1,
                             (unsigned int)&v49,
                             (_DWORD)v8,
                             (_DWORD)a3,
                             0);
      if ( v7 >= 0 )
        v7 = *PolicyDword;
      v8 += 8;
    }
    while ( v8 != &load_config_used );
  }
  else
  {
    v10 = &off_18001F9C0;
    do
    {
      v11 = (int *)Kerb3961::CipherPolicyImpl::LoadPolicyDword(a1, (unsigned int)&v49, (_DWORD)v10, (_DWORD)a3, 0);
      if ( v7 >= 0 )
        v7 = *v11;
      v10 += 4;
    }
    while ( v10 != &off_18001F9E0 );
  }
  if ( (*(_BYTE *)(a1 + 12) & 2) != 0 )
  {
LABEL_68:
    *a2 = v7;
    goto LABEL_69;
  }
  v12 = qword_180029048;
  for ( i = qword_180029048; ; v12 = i )
  {
    if ( (void **)v12 == &Kerb3961::g_encryptions )
    {
      v26 = qword_180029068;
      for ( i = qword_180029068; ; v26 = i )
      {
        if ( (void **)v26 == &Kerb3961::g_checksums )
          goto LABEL_68;
        v27 = *(_QWORD *)(v26 + 32);
        if ( a3 )
          break;
        v37 = (int *)(*(__int64 (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v27 + 48LL))(v27, &v50, 0);
        if ( v7 >= 0 )
          v7 = *v37;
LABEL_66:
        utl::_TreeConstIt<utl::pair<unsigned int const,Kerb3961::EncryptionAlgorithm *>>::operator++(&i);
      }
      hKey = 0;
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 32LL))(v27, &v46);
      if ( v48 < 0 )
        Kerb3961::ConsistencyFail((Kerb3961 *)L"Cipher failed to provide a name", v28);
      v44[0] = v45;
      v44[1] = v45;
      v45[0] = 0;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v44,
                               v47,
                               v46) )
      {
        Kerb3961::Logging::Verify::ConditionFailed(
          (Kerb3961::Logging::Verify *)"terminatedCopy.assign(name.buffer, name.length)",
          v29);
        v24 = (WCHAR *)v44[0];
        v25 = v45;
        goto LABEL_39;
      }
      v30 = hKey;
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(v30);
        SetLastError(LastError);
      }
      hKey = 0;
      v32 = RegOpenKeyExW(a3, v44[0], 0, 0x2000000u, &hKey);
      if ( (unsigned int)(v32 - 2) <= 1 )
      {
        v34 = hKey;
        if ( hKey )
        {
          v35 = GetLastError();
          RegCloseKey(v34);
          SetLastError(v35);
        }
        v33 = 0;
        hKey = 0;
      }
      else
      {
        if ( v32 )
        {
          if ( v7 >= 0 )
            v7 = -1073741801;
LABEL_60:
          if ( v44[0] != v45 )
            operator delete((void *)v44[0], (const struct std::nothrow_t *)&std::nothrow);
          if ( hKey )
            RegCloseKey(hKey);
          goto LABEL_66;
        }
        v33 = hKey;
      }
      v36 = (int *)(*(__int64 (__fastcall **)(__int64, char *, HKEY))(*(_QWORD *)v27 + 48LL))(v27, &v49, v33);
      if ( v7 >= 0 )
        v7 = *v36;
      goto LABEL_60;
    }
    v13 = *(_QWORD *)(v12 + 32);
    if ( a3 )
      break;
    v23 = (int *)(*(__int64 (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v13 + 72LL))(v13, &v50, 0);
    if ( v7 >= 0 )
      v7 = *v23;
LABEL_37:
    utl::_TreeConstIt<utl::pair<unsigned int const,Kerb3961::EncryptionAlgorithm *>>::operator++(&i);
  }
  hKey = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 32LL))(v13, &v46);
  if ( v48 < 0 )
    Kerb3961::ConsistencyFail((Kerb3961 *)L"Cipher failed to provide a name", v14);
  lpSubKey[0] = v43;
  lpSubKey[1] = v43;
  v43[0] = 0;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          lpSubKey,
                          v47,
                          v46) )
  {
    v16 = hKey;
    if ( hKey )
    {
      v17 = GetLastError();
      RegCloseKey(v16);
      SetLastError(v17);
    }
    hKey = 0;
    v18 = RegOpenKeyExW(a3, lpSubKey[0], 0, 0x2000000u, &hKey);
    if ( (unsigned int)(v18 - 2) <= 1 )
    {
      v20 = hKey;
      if ( hKey )
      {
        v21 = GetLastError();
        RegCloseKey(v20);
        SetLastError(v21);
      }
      v19 = 0;
      hKey = 0;
    }
    else
    {
      if ( v18 )
      {
        if ( v7 >= 0 )
          v7 = -1073741801;
LABEL_31:
        if ( lpSubKey[0] != v43 )
          operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_37;
      }
      v19 = hKey;
    }
    v22 = (int *)(*(__int64 (__fastcall **)(__int64, char *, HKEY))(*(_QWORD *)v13 + 72LL))(v13, &v49, v19);
    if ( v7 >= 0 )
      v7 = *v22;
    goto LABEL_31;
  }
  Kerb3961::Logging::Verify::ConditionFailed(
    (Kerb3961::Logging::Verify *)"terminatedCopy.assign(name.buffer, name.length)",
    v15);
  v24 = (WCHAR *)lpSubKey[0];
  v25 = v43;
LABEL_39:
  *a2 = -1073741801;
  if ( v24 != v25 )
    operator delete(v24, (const struct std::nothrow_t *)&std::nothrow);
  if ( hKey )
    RegCloseKey(hKey);
LABEL_69:
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return a2;
}

```

## disassembly

```asm
0x18000c4c8  mov     [rsp-8+arg_8], rbx
0x18000c4cd  mov     [rsp-8+arg_10], rsi
0x18000c4d2  push    rbp
0x18000c4d3  push    rdi
0x18000c4d4  push    r12
0x18000c4d6  push    r14
0x18000c4d8  push    r15
0x18000c4da  lea     rbp, [rsp-37h]
0x18000c4df  sub     rsp, 0A0h
0x18000c4e6  mov     r15, rdx
0x18000c4e9  mov     rsi, rcx
0x18000c4ec  lea     rdx, [rbp+57h+SRWLock]
0x18000c4f0  mov     r12, r8
0x18000c4f3  lea     rcx, ?g_cipherLock@Kerb3961@@3UCommonLock@1@A; Kerb3961::CommonLock Kerb3961::g_cipherLock
0x18000c4fa  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x18000c4ff  mov     al, [rsi+0Ch]
0x18000c502  and     al, 3
0x18000c504  jz      loc_18000C924
0x18000c50a  movzx   r8d, al
0x18000c50e  lea     rax, [r8-1]
0x18000c512  test    r8, rax
0x18000c515  jnz     loc_18000C924
0x18000c51b  xor     edi, edi
0x18000c51d  test    byte ptr [rsi+0Ch], 2
0x18000c521  jz      short loc_18000C559
0x18000c523  lea     rbx, off_18001F9E0; "DefaultDomainSupportedEncTypes"
0x18000c52a  mov     r9, r12
0x18000c52d  mov     byte ptr [rsp+0C0h+phkResult], 0
0x18000c532  mov     r8, rbx
0x18000c535  lea     rdx, [rbp+57h+arg_0]
0x18000c539  mov     rcx, rsi
0x18000c53c  call    ?LoadPolicyDword@CipherPolicyImpl@Kerb3961@@QEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUDwordPolicyValue@2@PEAUHKEY__@@_N@Z; Kerb3961::CipherPolicyImpl::LoadPolicyDword(Kerb3961::DwordPolicyValue const &,HKEY__ *,bool)
0x18000c541  test    edi, edi
0x18000c543  js      short loc_18000C547
0x18000c545  mov     edi, [rax]
0x18000c547  add     rbx, 20h ; ' '
0x18000c54b  lea     rax, _load_config_used
0x18000c552  cmp     rbx, rax
0x18000c555  jnz     short loc_18000C52A
0x18000c557  jmp     short loc_18000C58D
0x18000c559  lea     rbx, off_18001F9C0; "supportedEncryptionTypes"
0x18000c560  mov     r9, r12
0x18000c563  mov     byte ptr [rsp+0C0h+phkResult], 0
0x18000c568  mov     r8, rbx
0x18000c56b  lea     rdx, [rbp+57h+arg_0]
0x18000c56f  mov     rcx, rsi
0x18000c572  call    ?LoadPolicyDword@CipherPolicyImpl@Kerb3961@@QEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUDwordPolicyValue@2@PEAUHKEY__@@_N@Z; Kerb3961::CipherPolicyImpl::LoadPolicyDword(Kerb3961::DwordPolicyValue const &,HKEY__ *,bool)
0x18000c577  test    edi, edi
0x18000c579  js      short loc_18000C57D
0x18000c57b  mov     edi, [rax]
0x18000c57d  add     rbx, 20h ; ' '
0x18000c581  lea     rax, off_18001F9E0; "DefaultDomainSupportedEncTypes"
0x18000c588  cmp     rbx, rax
0x18000c58b  jnz     short loc_18000C560
0x18000c58d  test    byte ptr [rsi+0Ch], 2
0x18000c591  jnz     loc_18000C8E6
0x18000c597  mov     rax, cs:qword_180029048
0x18000c59e  mov     [rbp+57h+var_88], rax
0x18000c5a2  lea     rcx, ?g_encryptions@Kerb3961@@3V?$map@IPEAUEncryptionAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::EncryptionAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>> Kerb3961::g_encryptions
0x18000c5a9  cmp     rax, rcx
0x18000c5ac  jz      loc_18000C754
0x18000c5b2  mov     r14, [rax+20h]
0x18000c5b6  mov     rcx, r14
0x18000c5b9  test    r12, r12
0x18000c5bc  jz      loc_18000C6E5
0x18000c5c2  mov     [rbp+57h+hKey], 0
0x18000c5ca  lea     rdx, [rbp+57h+var_38]
0x18000c5ce  mov     rax, [r14]
0x18000c5d1  mov     rax, [rax+20h]
0x18000c5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5da  cmp     [rbp+57h+var_28], 0
0x18000c5de  jl      loc_18000C931
0x18000c5e4  mov     r8, [rbp+57h+var_38]
0x18000c5e8  lea     rax, [rbp+57h+var_68]
0x18000c5ec  mov     rdx, [rbp+57h+var_30]
0x18000c5f0  lea     rcx, [rbp+57h+lpSubKey]
0x18000c5f4  mov     [rbp+57h+lpSubKey], rax
0x18000c5f8  lea     rax, [rbp+57h+var_68]
0x18000c5fc  mov     [rbp+57h+var_70], rax
0x18000c600  xor     eax, eax
0x18000c602  mov     [rbp+57h+var_68], ax
0x18000c606  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000c60b  test    al, al
0x18000c60d  jz      loc_18000C710
0x18000c613  mov     rsi, [rbp+57h+hKey]
0x18000c617  test    rsi, rsi
0x18000c61a  jz      short loc_18000C635
0x18000c61c  call    cs:__imp_GetLastError
0x18000c622  mov     rcx, rsi; hKey
0x18000c625  mov     ebx, eax
0x18000c627  call    cs:__imp_RegCloseKey
0x18000c62d  mov     ecx, ebx; dwErrCode
0x18000c62f  call    cs:__imp_SetLastError
0x18000c635  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000c639  lea     rax, [rbp+57h+hKey]
0x18000c63d  mov     r9d, 2000000h; samDesired
0x18000c643  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000c648  xor     r8d, r8d; ulOptions
0x18000c64b  mov     [rbp+57h+hKey], 0
0x18000c653  mov     rcx, r12; hKey
0x18000c656  call    cs:__imp_RegOpenKeyExW
0x18000c65c  lea     ecx, [rax-2]
0x18000c65f  cmp     ecx, 1
0x18000c662  jbe     short loc_18000C679
0x18000c664  test    eax, eax
0x18000c666  jz      short loc_18000C673
0x18000c668  test    edi, edi
0x18000c66a  js      short loc_18000C6BB
0x18000c66c  mov     edi, 0C0000017h
0x18000c671  jmp     short loc_18000C6BB
0x18000c673  mov     r8, [rbp+57h+hKey]
0x18000c677  jmp     short loc_18000C6A2
0x18000c679  mov     rsi, [rbp+57h+hKey]
0x18000c67d  test    rsi, rsi
0x18000c680  jz      short loc_18000C69B
0x18000c682  call    cs:__imp_GetLastError
0x18000c688  mov     rcx, rsi; hKey
0x18000c68b  mov     ebx, eax
0x18000c68d  call    cs:__imp_RegCloseKey
0x18000c693  mov     ecx, ebx; dwErrCode
0x18000c695  call    cs:__imp_SetLastError
0x18000c69b  xor     r8d, r8d
0x18000c69e  mov     [rbp+57h+hKey], r8
0x18000c6a2  mov     rax, [r14]
0x18000c6a5  lea     rdx, [rbp+57h+arg_0]
0x18000c6a9  mov     rcx, r14
0x18000c6ac  mov     rax, [rax+48h]
0x18000c6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6b5  test    edi, edi
0x18000c6b7  js      short loc_18000C6BB
0x18000c6b9  mov     edi, [rax]
0x18000c6bb  mov     rcx, [rbp+57h+lpSubKey]; void *
0x18000c6bf  lea     rax, [rbp+57h+var_68]
0x18000c6c3  cmp     rcx, rax
0x18000c6c6  jz      short loc_18000C6D4
0x18000c6c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c6cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c6d4  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c6d8  test    rcx, rcx
0x18000c6db  jz      short loc_18000C6FE
0x18000c6dd  call    cs:__imp_RegCloseKey
0x18000c6e3  jmp     short loc_18000C6FE
0x18000c6e5  mov     rax, [r14]
0x18000c6e8  lea     rdx, [rbp+57h+arg_18]
0x18000c6ec  xor     r8d, r8d
0x18000c6ef  mov     rax, [rax+48h]
0x18000c6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6f8  test    edi, edi
0x18000c6fa  js      short loc_18000C6FE
0x18000c6fc  mov     edi, [rax]
0x18000c6fe  lea     rcx, [rbp+57h+var_88]
0x18000c702  call    ??E?$_TreeConstIt@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>::operator++(void)
0x18000c707  mov     rax, [rbp+57h+var_88]
0x18000c70b  jmp     loc_18000C5A2
0x18000c710  lea     rcx, aTerminatedcopy; "terminatedCopy.assign(name.buffer, name"...
0x18000c717  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000c71c  mov     rcx, [rbp+57h+lpSubKey]; void *
0x18000c720  lea     rax, [rbp+57h+var_68]
0x18000c724  mov     dword ptr [r15], 0C0000017h
0x18000c72b  cmp     rcx, rax
0x18000c72e  jz      short loc_18000C73C
0x18000c730  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c737  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c73c  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c740  test    rcx, rcx
0x18000c743  jz      loc_18000C8E9
0x18000c749  call    cs:__imp_RegCloseKey
0x18000c74f  jmp     loc_18000C8E9
0x18000c754  mov     rax, cs:qword_180029068
0x18000c75b  mov     [rbp+57h+var_88], rax
0x18000c75f  lea     rcx, ?g_checksums@Kerb3961@@3V?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@A; utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>> Kerb3961::g_checksums
0x18000c766  cmp     rax, rcx
0x18000c769  jz      loc_18000C8E6
0x18000c76f  mov     r14, [rax+20h]
0x18000c773  mov     rcx, r14
0x18000c776  test    r12, r12
0x18000c779  jz      loc_18000C8A2
0x18000c77f  mov     [rbp+57h+hKey], 0
0x18000c787  lea     rdx, [rbp+57h+var_38]
0x18000c78b  mov     rax, [r14]
0x18000c78e  mov     rax, [rax+20h]
0x18000c792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c797  cmp     [rbp+57h+var_28], 0
0x18000c79b  jl      loc_18000C917
0x18000c7a1  mov     r8, [rbp+57h+var_38]
0x18000c7a5  lea     rax, [rbp+57h+var_48]
0x18000c7a9  mov     rdx, [rbp+57h+var_30]
0x18000c7ad  lea     rcx, [rbp+57h+var_58]
0x18000c7b1  mov     [rbp+57h+var_58], rax
0x18000c7b5  lea     rax, [rbp+57h+var_48]
0x18000c7b9  mov     [rbp+57h+var_50], rax
0x18000c7bd  xor     eax, eax
0x18000c7bf  mov     [rbp+57h+var_48], ax
0x18000c7c3  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000c7c8  test    al, al
0x18000c7ca  jz      loc_18000C8CD
0x18000c7d0  mov     rsi, [rbp+57h+hKey]
0x18000c7d4  test    rsi, rsi
0x18000c7d7  jz      short loc_18000C7F2
0x18000c7d9  call    cs:__imp_GetLastError
0x18000c7df  mov     rcx, rsi; hKey
0x18000c7e2  mov     ebx, eax
0x18000c7e4  call    cs:__imp_RegCloseKey
0x18000c7ea  mov     ecx, ebx; dwErrCode
0x18000c7ec  call    cs:__imp_SetLastError
0x18000c7f2  mov     rdx, [rbp+57h+var_58]; lpSubKey
0x18000c7f6  lea     rax, [rbp+57h+hKey]
0x18000c7fa  mov     r9d, 2000000h; samDesired
0x18000c800  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000c805  xor     r8d, r8d; ulOptions
0x18000c808  mov     [rbp+57h+hKey], 0
0x18000c810  mov     rcx, r12; hKey
0x18000c813  call    cs:__imp_RegOpenKeyExW
0x18000c819  lea     ecx, [rax-2]
0x18000c81c  cmp     ecx, 1
0x18000c81f  jbe     short loc_18000C836
0x18000c821  test    eax, eax
0x18000c823  jz      short loc_18000C830
0x18000c825  test    edi, edi
0x18000c827  js      short loc_18000C878
0x18000c829  mov     edi, 0C0000017h
0x18000c82e  jmp     short loc_18000C878
0x18000c830  mov     r8, [rbp+57h+hKey]
0x18000c834  jmp     short loc_18000C85F
0x18000c836  mov     rsi, [rbp+57h+hKey]
0x18000c83a  test    rsi, rsi
0x18000c83d  jz      short loc_18000C858
0x18000c83f  call    cs:__imp_GetLastError
0x18000c845  mov     rcx, rsi; hKey
0x18000c848  mov     ebx, eax
0x18000c84a  call    cs:__imp_RegCloseKey
0x18000c850  mov     ecx, ebx; dwErrCode
0x18000c852  call    cs:__imp_SetLastError
0x18000c858  xor     r8d, r8d
0x18000c85b  mov     [rbp+57h+hKey], r8
0x18000c85f  mov     rax, [r14]
0x18000c862  lea     rdx, [rbp+57h+arg_0]
0x18000c866  mov     rcx, r14
0x18000c869  mov     rax, [rax+30h]
0x18000c86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c872  test    edi, edi
0x18000c874  js      short loc_18000C878
0x18000c876  mov     edi, [rax]
0x18000c878  mov     rcx, [rbp+57h+var_58]; void *
0x18000c87c  lea     rax, [rbp+57h+var_48]
0x18000c880  cmp     rcx, rax
0x18000c883  jz      short loc_18000C891
0x18000c885  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c88c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c891  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c895  test    rcx, rcx
0x18000c898  jz      short loc_18000C8BB
0x18000c89a  call    cs:__imp_RegCloseKey
0x18000c8a0  jmp     short loc_18000C8BB
0x18000c8a2  mov     rax, [r14]
0x18000c8a5  lea     rdx, [rbp+57h+arg_18]
0x18000c8a9  xor     r8d, r8d
0x18000c8ac  mov     rax, [rax+30h]
0x18000c8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8b5  test    edi, edi
0x18000c8b7  js      short loc_18000C8BB
0x18000c8b9  mov     edi, [rax]
0x18000c8bb  lea     rcx, [rbp+57h+var_88]
0x18000c8bf  call    ??E?$_TreeConstIt@U?$pair@$$CBIPEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<utl::pair<uint const,Kerb3961::EncryptionAlgorithm *>>::operator++(void)
0x18000c8c4  mov     rax, [rbp+57h+var_88]
0x18000c8c8  jmp     loc_18000C75F
0x18000c8cd  lea     rcx, aTerminatedcopy; "terminatedCopy.assign(name.buffer, name"...
0x18000c8d4  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000c8d9  mov     rcx, [rbp+57h+var_58]
0x18000c8dd  lea     rax, [rbp+57h+var_48]
0x18000c8e1  jmp     loc_18000C724
0x18000c8e6  mov     [r15], edi
0x18000c8e9  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000c8ed  test    rcx, rcx
0x18000c8f0  jz      short loc_18000C8F8
0x18000c8f2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c8f8  lea     r11, [rsp+0C0h+var_20]
0x18000c900  mov     rax, r15
0x18000c903  mov     rbx, [r11+38h]
0x18000c907  mov     rsi, [r11+40h]
0x18000c90b  mov     rsp, r11
0x18000c90e  pop     r15
0x18000c910  pop     r14
0x18000c912  pop     r12
0x18000c914  pop     rdi
0x18000c915  pop     rbp
0x18000c916  retn
0x18000c917  lea     rcx, aCipherFailedTo; "Cipher failed to provide a name"
0x18000c91e  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
0x18000c924  lea     rcx, aAPolicyMustEit; "A policy must either be for the compute"...
0x18000c92b  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
0x18000c931  lea     rcx, aCipherFailedTo; "Cipher failed to provide a name"
0x18000c938  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
