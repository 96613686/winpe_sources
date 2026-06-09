# DeviceCastle::Library::Internal::DatabasePersistence::EnsureStorageFolder(ushort const *)

- ea: `0x18004e8c8`
- end: `0x18004eca5`
- name: `?EnsureStorageFolder@DatabasePersistence@Internal@Library@DeviceCastle@@AEAAJPEBG@Z`
- size: `989`
- prototype: `__int64 __fastcall(DeviceCastle::Library::Internal::DatabasePersistence *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004de90`

## callees

- `0x1800049a0`
- `0x18000584c`
- `0x180013014`
- `0x180013274`
- `0x18003c35c`
- `0x180047250`
- `0x18004736c`
- `0x1800474d8`
- `0x180047564`
- `0x180048218`
- `0x18004bf9c`
- `0x18004e148`
- `0x18004e650`
- `0x18004e8c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ea19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ea19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e9e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ebe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e9e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ebe7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ea21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ea21`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004ebdd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004ebdd`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18004ea5b`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18004eac2`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18004ea5b`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18004eac2`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18004ea3e`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18004ea3e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004e9d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004e9d9`

## string_xrefs

- `0x18004ec47`: `Device Castle could not create a storage folder '%1!s!'.  The error code was %2!#08I32x!.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeviceCastle::Library::Internal::DatabasePersistence::EnsureStorageFolder(
        DeviceCastle::Library::Internal::DatabasePersistence *this,
        unsigned __int16 *a2)
{
  char v4; // r15
  char *v5; // rcx
  int v6; // ebx
  __int64 v7; // rbx
  signed int LastError; // eax
  PSECURITY_DESCRIPTOR v9; // rsi
  void *v10; // rdi
  DWORD v11; // ebx
  __int64 v12; // r8
  unsigned __int64 v13; // rdx
  LPCWSTR *v14; // rdi
  __int64 v15; // rbx
  int v16; // edi
  __int64 v17; // rdx
  LPCWSTR *v18; // rcx
  __int64 v19; // rdx
  LPCWSTR *v20; // rcx
  wchar_t *v21; // rdx
  const WCHAR *v22; // rcx
  __int128 *v23; // rax
  __int128 v24; // xmm2
  __int128 v25; // xmm3
  LPCWSTR *v26; // rax
  bool v28; // [rsp+30h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-31h] BYREF
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+40h] [rbp-29h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+48h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v33; // [rsp+60h] [rbp-9h]
  LPCWSTR lpPathName[2]; // [rsp+68h] [rbp-1h] BYREF
  __int128 v35; // [rsp+78h] [rbp+Fh]

  v4 = 1;
  if ( *((_QWORD *)this + 4) )
  {
    v5 = (char *)this + 16;
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(char **)v5;
    v6 = DeviceCastle::Library::Internal::Utilities::CheckFolderExistence((const unsigned __int16 *)v5);
    if ( v6 < 0 )
      return (unsigned int)v6;
  }
  else
  {
    v6 = 1;
  }
  if ( !v6 )
    return 0;
  pv = 0;
  *(_OWORD *)lpPathName = 0;
  *(_QWORD *)&v35 = 0;
  *((_QWORD *)&v35 + 1) = 7;
  LOWORD(lpPathName[0]) = 0;
  v28 = 0;
  v6 = DeviceCastle::Library::Internal::DatabasePersistence::CheckBaseFolder(&v28);
  if ( v6 < 0 )
    goto LABEL_9;
  if ( *((_QWORD *)&v35 + 1) < 0x104u )
  {
    v7 = v35;
    ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAX_K_Z___V___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(lpPathName);
    *(_QWORD *)&v35 = v7;
  }
  if ( v28 )
  {
    std::wstring::operator=(lpPathName, (char *)DeviceCastle::Library::Internal::g_pCastleInstance + 48);
    v16 = 2;
    v4 = 0;
    goto LABEL_33;
  }
  *(_OWORD *)SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  LODWORD(SecurityDescriptor[0]) = 24;
  v33 = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:SYG:SYD:(A;;RC;;;PS)",
          1u,
          &SecurityDescriptor[1],
          &SecurityDescriptorSize) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_9;
  }
  v9 = SecurityDescriptor[1];
  ObjectDescriptor = SecurityDescriptor[1];
  v10 = pv;
  if ( pv )
  {
    v11 = GetLastError();
    CoTaskMemFree(v10);
    SetLastError(v11);
  }
  pv = 0;
  v6 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0x8800u, 0, (PWSTR *)&pv);
  if ( v6 < 0 )
  {
    if ( v9 )
    {
      ObjectDescriptor = v9;
      DestroyPrivateObjectSecurity(&ObjectDescriptor);
    }
    goto LABEL_9;
  }
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)pv + v13) );
  if ( v13 > *((_QWORD *)&v35 + 1) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      lpPathName,
      v13,
      v12,
      pv);
  }
  else
  {
    v14 = lpPathName;
    if ( *((_QWORD *)&v35 + 1) > 7u )
      v14 = (LPCWSTR *)lpPathName[0];
    *(_QWORD *)&v35 = v13;
    v15 = 2 * v13;
    memmove_0(v14, pv, 2 * v13);
    *(_WORD *)((char *)v14 + v15) = 0;
  }
  v16 = 0;
  if ( v9 )
  {
    ObjectDescriptor = v9;
    DestroyPrivateObjectSecurity(&ObjectDescriptor);
  }
  while ( 1 )
  {
LABEL_33:
    switch ( v16 )
    {
      case 0:
        v21 = L"\\Microsoft";
        goto LABEL_54;
      case 1:
        v21 = L"\\DeviceCastle";
LABEL_54:
        std::wstring::append(lpPathName, v21);
        goto LABEL_55;
      case 2:
        if ( v4 )
        {
          v19 = v35;
          v20 = lpPathName;
          if ( (unsigned __int64)v35 >= *((_QWORD *)&v35 + 1) )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(lpPathName);
          }
          else
          {
            *(_QWORD *)&v35 = v35 + 1;
            if ( *((_QWORD *)&v35 + 1) > 7u )
              v20 = (LPCWSTR *)lpPathName[0];
            *(_DWORD *)((char *)v20 + 2 * v19) = 92;
          }
        }
        std::wstring::operator+=(lpPathName);
        goto LABEL_55;
    }
    if ( v16 != 3 )
      break;
    DeviceCastle::Library::Internal::DatabasePersistence::EnsureOwnerFile(this, lpPathName);
    if ( !a2 || !*a2 )
      goto LABEL_59;
    v17 = v35;
    v18 = lpPathName;
    if ( (unsigned __int64)v35 >= *((_QWORD *)&v35 + 1) )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(lpPathName);
    }
    else
    {
      *(_QWORD *)&v35 = v35 + 1;
      if ( *((_QWORD *)&v35 + 1) > 7u )
        v18 = (LPCWSTR *)lpPathName[0];
      *(_DWORD *)((char *)v18 + 2 * v17) = 92;
    }
    std::wstring::append(lpPathName, a2);
    *((_BYTE *)this + 48) = 1;
LABEL_55:
    v22 = (const WCHAR *)lpPathName;
    if ( *((_QWORD *)&v35 + 1) > 7u )
      v22 = lpPathName[0];
    if ( !CreateDirectoryW(v22, 0) )
    {
      v6 = GetLastError();
      if ( v6 != 183 )
      {
        v26 = lpPathName;
        if ( *((_QWORD *)&v35 + 1) > 7u )
          v26 = (LPCWSTR *)lpPathName[0];
        DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
          DeviceCastle::Library::Internal::g_pCastleInstance,
          2u,
          *((struct DeviceCastle::Library::CallerIdentity **)this + 1),
          L"Device Castle could not create a storage folder '%1!s!'.  The error code was %2!#08I32x!.",
          v26,
          v6);
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
        goto LABEL_9;
      }
    }
LABEL_59:
    ++v16;
  }
  v23 = (__int128 *)((char *)this + 16);
  if ( (LPCWSTR *)((char *)this + 16) != lpPathName )
  {
    v24 = *v23;
    v25 = *((_OWORD *)this + 2);
    *v23 = *(_OWORD *)lpPathName;
    *((_OWORD *)this + 2) = v35;
    *(_OWORD *)lpPathName = v24;
    v35 = v25;
  }
  v6 = 0;
LABEL_9:
  std::wstring::~wstring(lpPathName);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004e8c8  mov     [rsp-8+arg_10], rbx
0x18004e8cd  push    rbp
0x18004e8ce  push    rsi
0x18004e8cf  push    rdi
0x18004e8d0  push    r12
0x18004e8d2  push    r13
0x18004e8d4  push    r14
0x18004e8d6  push    r15
0x18004e8d8  lea     rbp, [rsp-27h]
0x18004e8dd  sub     rsp, 90h
0x18004e8e4  mov     rax, cs:__security_cookie
0x18004e8eb  xor     rax, rsp
0x18004e8ee  mov     [rbp+57h+var_38], rax
0x18004e8f2  mov     r12, rdx
0x18004e8f5  mov     r14, rcx
0x18004e8f8  mov     r15d, 1
0x18004e8fe  xor     r13d, r13d
0x18004e901  cmp     [rcx+20h], r13
0x18004e905  jz      short loc_18004E926
0x18004e907  add     rcx, 10h
0x18004e90b  cmp     qword ptr [rcx+18h], 7
0x18004e910  jbe     short loc_18004E915
0x18004e912  mov     rcx, [rcx]; unsigned __int16 *
0x18004e915  call    ?CheckFolderExistence@Utilities@Internal@Library@DeviceCastle@@SAJPEBG@Z; DeviceCastle::Library::Internal::Utilities::CheckFolderExistence(ushort const *)
0x18004e91a  mov     ebx, eax
0x18004e91c  test    eax, eax
0x18004e91e  js      loc_18004EC7C
0x18004e924  jmp     short loc_18004E929
0x18004e926  mov     ebx, r15d
0x18004e929  test    ebx, ebx
0x18004e92b  jz      loc_18004EC79
0x18004e931  mov     [rbp+57h+pv], r13
0x18004e935  xorps   xmm0, xmm0
0x18004e938  movups  xmmword ptr [rbp+57h+lpPathName], xmm0
0x18004e93c  mov     qword ptr [rbp+57h+var_48], r13
0x18004e940  mov     qword ptr [rbp+57h+var_48+8], 7
0x18004e948  mov     word ptr [rbp+57h+lpPathName], r13w
0x18004e94d  mov     [rbp+57h+var_90], r13b
0x18004e951  lea     rcx, [rbp+57h+var_90]; bool *
0x18004e955  call    ?CheckBaseFolder@DatabasePersistence@Internal@Library@DeviceCastle@@CAJPEA_N@Z; DeviceCastle::Library::Internal::DatabasePersistence::CheckBaseFolder(bool *)
0x18004e95a  mov     ebx, eax
0x18004e95c  test    eax, eax
0x18004e95e  jns     short loc_18004E982
0x18004e960  lea     rcx, [rbp+57h+lpPathName]
0x18004e964  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e969  nop
0x18004e96a  mov     rcx, [rbp+57h+pv]; pv
0x18004e96e  test    rcx, rcx
0x18004e971  jz      loc_18004EC7C
0x18004e977  call    cs:__imp_CoTaskMemFree
0x18004e97d  jmp     loc_18004EC7C
0x18004e982  mov     edx, 104h
0x18004e987  cmp     qword ptr [rbp+57h+var_48+8], rdx
0x18004e98b  jnb     short loc_18004E9A1
0x18004e98d  mov     rbx, qword ptr [rbp+57h+var_48]
0x18004e991  sub     rdx, rbx
0x18004e994  lea     rcx, [rbp+57h+lpPathName]; Src
0x18004e998  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x18004e99d  mov     qword ptr [rbp+57h+var_48], rbx
0x18004e9a1  cmp     [rbp+57h+var_90], r13b
0x18004e9a5  jnz     loc_18004EACA
0x18004e9ab  xorps   xmm0, xmm0
0x18004e9ae  xor     eax, eax
0x18004e9b0  movups  xmmword ptr [rbp+57h+SecurityDescriptor], xmm0
0x18004e9b4  mov     [rbp+57h+var_60], rax
0x18004e9b8  mov     [rbp+57h+SecurityDescriptorSize], r13d
0x18004e9bc  mov     dword ptr [rbp+57h+SecurityDescriptor], 18h
0x18004e9c3  mov     dword ptr [rbp+57h+var_60], r13d
0x18004e9c7  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18004e9cb  lea     r8, [rbp+57h+SecurityDescriptor+8]; SecurityDescriptor
0x18004e9cf  mov     edx, r15d; StringSDRevision
0x18004e9d2  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;RC;;;PS)"
0x18004e9d9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004e9df  test    eax, eax
0x18004e9e1  jnz     short loc_18004E9FD
0x18004e9e3  call    cs:__imp_GetLastError
0x18004e9e9  mov     ebx, eax
0x18004e9eb  test    eax, eax
0x18004e9ed  jle     short loc_18004E9F8
0x18004e9ef  movzx   ebx, ax
0x18004e9f2  or      ebx, 80070000h
0x18004e9f8  jmp     loc_18004E960
0x18004e9fd  mov     rsi, [rbp+57h+SecurityDescriptor+8]
0x18004ea01  mov     [rbp+57h+ObjectDescriptor], rsi
0x18004ea05  mov     rdi, [rbp+57h+pv]
0x18004ea09  test    rdi, rdi
0x18004ea0c  jz      short loc_18004EA27
0x18004ea0e  call    cs:__imp_GetLastError
0x18004ea14  mov     ebx, eax
0x18004ea16  mov     rcx, rdi; pv
0x18004ea19  call    cs:__imp_CoTaskMemFree
0x18004ea1f  mov     ecx, ebx; dwErrCode
0x18004ea21  call    cs:__imp_SetLastError
0x18004ea27  mov     [rbp+57h+pv], r13
0x18004ea2b  lea     r9, [rbp+57h+pv]; ppszPath
0x18004ea2f  xor     r8d, r8d; hToken
0x18004ea32  mov     edx, 8800h; dwFlags
0x18004ea37  lea     rcx, FOLDERID_LocalAppData; rfid
0x18004ea3e  call    cs:__imp_SHGetKnownFolderPath
0x18004ea44  mov     ebx, eax
0x18004ea46  test    eax, eax
0x18004ea48  jns     short loc_18004EA66
0x18004ea4a  test    rsi, rsi
0x18004ea4d  jz      loc_18004E960
0x18004ea53  mov     [rbp+57h+ObjectDescriptor], rsi
0x18004ea57  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x18004ea5b  call    cs:__imp_DestroyPrivateObjectSecurity
0x18004ea61  jmp     loc_18004E960
0x18004ea66  mov     r9, [rbp+57h+pv]
0x18004ea6a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004ea6e  inc     rdx
0x18004ea71  cmp     [r9+rdx*2], r13w
0x18004ea76  jnz     short loc_18004EA6E
0x18004ea78  cmp     rdx, qword ptr [rbp+57h+var_48+8]
0x18004ea7c  ja      short loc_18004EAA9
0x18004ea7e  lea     rdi, [rbp+57h+lpPathName]
0x18004ea82  cmp     qword ptr [rbp+57h+var_48+8], 7
0x18004ea87  cmova   rdi, [rbp+57h+lpPathName]
0x18004ea8c  mov     qword ptr [rbp+57h+var_48], rdx
0x18004ea90  lea     rbx, [rdx+rdx]
0x18004ea94  mov     r8, rbx; Size
0x18004ea97  mov     rdx, r9; Src
0x18004ea9a  mov     rcx, rdi; void *
0x18004ea9d  call    memmove_0
0x18004eaa2  mov     [rdi+rbx], r13w
0x18004eaa7  jmp     short loc_18004EAB2
0x18004eaa9  lea     rcx, [rbp+57h+lpPathName]
0x18004eaad  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18004eab2  mov     edi, r13d
0x18004eab5  test    rsi, rsi
0x18004eab8  jz      short loc_18004EAE6
0x18004eaba  mov     [rbp+57h+ObjectDescriptor], rsi
0x18004eabe  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x18004eac2  call    cs:__imp_DestroyPrivateObjectSecurity
0x18004eac8  jmp     short loc_18004EAE6
0x18004eaca  mov     rdx, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; DeviceCastle::Library::DeviceCastleInternal * DeviceCastle::Library::Internal::g_pCastleInstance
0x18004ead1  add     rdx, 30h ; '0'
0x18004ead5  lea     rcx, [rbp+57h+lpPathName]
0x18004ead9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004eade  mov     edi, 2
0x18004eae3  mov     r15b, r13b
0x18004eae6  mov     esi, 5Ch ; '\'
0x18004eaeb  mov     ecx, edi
0x18004eaed  test    edi, edi
0x18004eaef  jz      loc_18004EBBD
0x18004eaf5  sub     ecx, 1
0x18004eaf8  jz      loc_18004EBB4
0x18004eafe  sub     ecx, 1
0x18004eb01  jz      short loc_18004EB6C
0x18004eb03  cmp     ecx, 1
0x18004eb06  jnz     loc_18004EBFD
0x18004eb0c  lea     rdx, [rbp+57h+lpPathName]; Src
0x18004eb10  mov     rcx, r14; this
0x18004eb13  call    ?EnsureOwnerFile@DatabasePersistence@Internal@Library@DeviceCastle@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DeviceCastle::Library::Internal::DatabasePersistence::EnsureOwnerFile(std::wstring &)
0x18004eb18  test    r12, r12
0x18004eb1b  jz      loc_18004EBF6
0x18004eb21  cmp     r13w, [r12]
0x18004eb26  jz      loc_18004EBF6
0x18004eb2c  mov     rdx, qword ptr [rbp+57h+var_48]
0x18004eb30  lea     rcx, [rbp+57h+lpPathName]; Src
0x18004eb34  cmp     rdx, qword ptr [rbp+57h+var_48+8]
0x18004eb38  jnb     short loc_18004EB51
0x18004eb3a  lea     rax, [rdx+1]
0x18004eb3e  mov     qword ptr [rbp+57h+var_48], rax
0x18004eb42  cmp     qword ptr [rbp+57h+var_48+8], 7
0x18004eb47  cmova   rcx, [rbp+57h+lpPathName]
0x18004eb4c  mov     [rcx+rdx*2], esi
0x18004eb4f  jmp     short loc_18004EB59
0x18004eb51  mov     r9d, esi
0x18004eb54  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x18004eb59  mov     rdx, r12; void *
0x18004eb5c  lea     rcx, [rbp+57h+lpPathName]; Src
0x18004eb60  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004eb65  mov     byte ptr [r14+30h], 1
0x18004eb6a  jmp     short loc_18004EBCD
0x18004eb6c  test    r15b, r15b
0x18004eb6f  jz      short loc_18004EB9E
0x18004eb71  mov     rdx, qword ptr [rbp+57h+var_48]
0x18004eb75  lea     rcx, [rbp+57h+lpPathName]; Src
0x18004eb79  cmp     rdx, qword ptr [rbp+57h+var_48+8]
0x18004eb7d  jnb     short loc_18004EB96
0x18004eb7f  lea     rax, [rdx+1]
0x18004eb83  mov     qword ptr [rbp+57h+var_48], rax
0x18004eb87  cmp     qword ptr [rbp+57h+var_48+8], 7
0x18004eb8c  cmova   rcx, [rbp+57h+lpPathName]
0x18004eb91  mov     [rcx+rdx*2], esi
0x18004eb94  jmp     short loc_18004EB9E
0x18004eb96  mov     r9d, esi
0x18004eb99  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x18004eb9e  mov     rdx, [r14+8]
0x18004eba2  add     rdx, 0A0h
0x18004eba9  lea     rcx, [rbp+57h+lpPathName]; Src
0x18004ebad  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x18004ebb2  jmp     short loc_18004EBCD
0x18004ebb4  lea     rdx, aDevicecastle; "\\DeviceCastle"
0x18004ebbb  jmp     short loc_18004EBC4
0x18004ebbd  lea     rdx, aMicrosoft; "\\Microsoft"
0x18004ebc4  lea     rcx, [rbp+57h+lpPathName]; Src
0x18004ebc8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004ebcd  lea     rcx, [rbp+57h+lpPathName]
0x18004ebd1  cmp     qword ptr [rbp+57h+var_48+8], 7
0x18004ebd6  cmova   rcx, [rbp+57h+lpPathName]; lpPathName
0x18004ebdb  xor     edx, edx; lpSecurityAttributes
0x18004ebdd  call    cs:__imp_CreateDirectoryW
0x18004ebe3  test    eax, eax
0x18004ebe5  jnz     short loc_18004EBF6
0x18004ebe7  call    cs:__imp_GetLastError
0x18004ebed  mov     ebx, eax
0x18004ebef  cmp     eax, 0B7h
0x18004ebf4  jnz     short loc_18004EC30
0x18004ebf6  inc     edi
0x18004ebf8  jmp     loc_18004EAEB
0x18004ebfd  lea     rax, [r14+10h]
0x18004ec01  lea     rcx, [rbp+57h+lpPathName]
0x18004ec05  cmp     rax, rcx
0x18004ec08  jz      short loc_18004EC28
0x18004ec0a  movups  xmm2, xmmword ptr [rax]
0x18004ec0d  movups  xmm3, xmmword ptr [rax+10h]
0x18004ec11  movups  xmm0, xmmword ptr [rbp+57h+lpPathName]
0x18004ec15  movups  xmmword ptr [rax], xmm0
0x18004ec18  movups  xmm1, [rbp+57h+var_48]
0x18004ec1c  movups  xmmword ptr [rax+10h], xmm1
0x18004ec20  movups  xmmword ptr [rbp+57h+lpPathName], xmm2
0x18004ec24  movups  [rbp+57h+var_48], xmm3
0x18004ec28  mov     ebx, r13d
0x18004ec2b  jmp     loc_18004E960
0x18004ec30  lea     rax, [rbp+57h+lpPathName]
0x18004ec34  cmp     qword ptr [rbp+57h+var_48+8], 7
0x18004ec39  cmova   rax, [rbp+57h+lpPathName]
0x18004ec3e  mov     [rsp+0C0h+var_98], ebx
0x18004ec42  mov     [rsp+0C0h+var_A0], rax
0x18004ec47  lea     r9, aDeviceCastleCo_4; "Device Castle could not create a storag"...
0x18004ec4e  mov     r8, [r14+8]; struct DeviceCastle::Library::CallerIdentity *
0x18004ec52  mov     edx, 2; unsigned int
0x18004ec57  mov     rcx, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; this
0x18004ec5e  call    ?LogFormattedMessage@DeviceCastleInternal@Library@DeviceCastle@@QEBAXKPEAVCallerIdentity@23@PEBGZZ; DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(ulong,DeviceCastle::Library::CallerIdentity *,ushort const *,...)
0x18004ec63  test    ebx, ebx
0x18004ec65  jle     loc_18004E960
0x18004ec6b  movzx   ebx, bx
0x18004ec6e  or      ebx, 80070000h
0x18004ec74  jmp     loc_18004E960
0x18004ec79  mov     ebx, r13d
0x18004ec7c  mov     eax, ebx
0x18004ec7e  mov     rcx, [rbp+57h+var_38]
0x18004ec82  xor     rcx, rsp; StackCookie
0x18004ec85  call    __security_check_cookie
0x18004ec8a  mov     rbx, [rsp+0C0h+arg_10]
0x18004ec92  add     rsp, 90h
0x18004ec99  pop     r15
0x18004ec9b  pop     r14
0x18004ec9d  pop     r13
0x18004ec9f  pop     r12
0x18004eca1  pop     rdi
0x18004eca2  pop     rsi
0x18004eca3  pop     rbp
0x18004eca4  retn
```
