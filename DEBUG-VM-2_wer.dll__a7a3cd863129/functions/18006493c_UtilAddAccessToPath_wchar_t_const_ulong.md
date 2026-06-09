# UtilAddAccessToPath(wchar_t const *,ulong)

- ea: `0x18006493c`
- end: `0x180065054`
- name: `?UtilAddAccessToPath@@YAJPEB_WK@Z`
- size: `1816`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180063d74`
- `0x18008b3dc`

## callees

- `0x18000716c`
- `0x1800072cc`
- `0x180007e10`
- `0x180007e34`
- `0x18001c650`
- `0x18001daa8`
- `0x180023dc4`
- `0x180023e8c`
- `0x18002bed4`
- `0x18002cdd0`
- `0x1800303dc`
- `0x180045184`
- `0x18006493c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180064c6c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180064c6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180064ccc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180064ccc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180064c57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180064c57`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180064cda`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180064cda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800649eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064aaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064ba2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064ce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800649eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064aaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064ba2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064ce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800649c6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800649c6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180064f18`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180064f18`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180064f71`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180064f71`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180064fc0`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180064fc0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180064bf4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180064bf4`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180064aa5`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180064b98`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180064aa5`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180064b98`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064d4c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064e3d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064d4c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064e3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064eb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064eb7`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180064ecc`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180064ecc`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UtilAddAccessToPath(const wchar_t *a1, DWORD a2)
{
  int v4; // ebx
  HANDLE FileW; // rax
  HANDLE v6; // rdi
  DWORD LastError; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  char *v11; // rdx
  DWORD v12; // eax
  DWORD v13; // eax
  __int64 unique_oversize_for; // rax
  PSECURITY_DESCRIPTOR v15; // rbx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  DWORD v19; // eax
  DWORD v20; // eax
  void **v21; // rbx
  HANDLE CurrentThread; // rax
  DWORD v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  void **v27; // rbx
  HANDLE CurrentProcess; // rax
  DWORD v29; // eax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  char *v33; // rdx
  DWORD v34; // eax
  DWORD v35; // eax
  __int64 v36; // rax
  LPWCH *v37; // rbx
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  DWORD v41; // eax
  HLOCAL v42; // rcx
  DWORD v43; // eax
  DWORD v44; // eax
  DWORD v45; // eax
  DWORD v46; // eax
  const wchar_t *v48; // [rsp+40h] [rbp-79h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp-71h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-69h] BYREF
  BOOL bDaclDefaulted; // [rsp+58h] [rbp-61h] BYREF
  PACL pDacl; // [rsp+60h] [rbp-59h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-51h] BYREF
  LPVOID TokenInformation; // [rsp+70h] [rbp-49h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+78h] [rbp-41h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-39h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v58; // [rsp+D0h] [rbp+17h]
  DWORD nLengthNeeded; // [rsp+120h] [rbp+67h] BYREF
  BOOL bDaclPresent; // [rsp+130h] [rbp+77h] BYREF
  int v61; // [rsp+138h] [rbp+7Fh] BYREF

  nLengthNeeded = 0;
  pSecurityDescriptor = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v58 = 0;
  pDacl = 0;
  hMem = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  Handle = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    goto LABEL_77;
  }
  FileW = CreateFileW(a1, 0x60000u, 3u, 0, 3u, 0x2200000u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&Handle, FileW);
  v6 = Handle;
  if ( (unsigned __int64)Handle + 1 <= 1 )
  {
    LastError = GetLastError();
    v4 = ERROR_HR_FROM_WIN32(LastError);
    if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
    {
      v11 = byte_1800C6561;
LABEL_7:
      v48 = a1;
      v61 = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v8,
        (_DWORD)v11,
        v9,
        v10,
        (__int64)&v48,
        (__int64)&v61);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  v4 = UtilVerifyFilePath(a1, Handle);
  if ( v4 >= 0 )
  {
    if ( GetKernelObjectSecurity(v6, 4u, 0, 0, &nLengthNeeded) )
    {
      v13 = nLengthNeeded;
    }
    else
    {
      v12 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v12);
      v13 = nLengthNeeded;
      if ( !nLengthNeeded || v4 != -2147024774 )
      {
        if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
        {
          v11 = &byte_1800C65D7;
          goto LABEL_7;
        }
        goto LABEL_77;
      }
    }
    unique_oversize_for = tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(&v61, v13);
    utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
      &pSecurityDescriptor,
      unique_oversize_for);
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v61);
    v15 = pSecurityDescriptor;
    if ( !pSecurityDescriptor )
    {
      v4 = -2147024882;
      if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      {
        v61 = -2147024882;
        v48 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v16,
          (unsigned int)&word_1800C6616,
          v17,
          v18,
          (__int64)&v48,
          (__int64)&v61);
      }
      goto LABEL_77;
    }
    if ( !GetKernelObjectSecurity(v6, 4u, pSecurityDescriptor, nLengthNeeded, &nLengthNeeded) )
    {
      v19 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v19);
      if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      {
        v11 = byte_1800C6653;
        goto LABEL_7;
      }
      goto LABEL_77;
    }
    if ( !GetSecurityDescriptorDacl(v15, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v20 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v20);
      if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      {
        v11 = (char *)word_1800C6692;
        goto LABEL_7;
      }
      goto LABEL_77;
    }
    if ( !bDaclPresent )
      pDacl = 0;
    v21 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 0, v21) )
    {
      v23 = GetLastError();
      ERROR_HR_FROM_WIN32(v23);
      if ( (unsigned int)dword_1800D8000 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      {
        v61 = v25;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v24,
          (unsigned int)&dword_1800C66CC,
          v25,
          v26,
          (__int64)&v61);
      }
      v27 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, v27) )
      {
        v29 = GetLastError();
        v4 = ERROR_HR_FROM_WIN32(v29);
        if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
          goto LABEL_77;
        v33 = (char *)&dword_1800C6704;
        goto LABEL_42;
      }
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &nLengthNeeded) )
    {
      v35 = nLengthNeeded;
    }
    else
    {
      v34 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v34);
      v35 = nLengthNeeded;
      if ( !nLengthNeeded || v4 != -2147024774 )
      {
        if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
          goto LABEL_77;
        v33 = byte_1800C673D;
        goto LABEL_42;
      }
    }
    v36 = tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(&v61, v35);
    utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
      &TokenInformation,
      v36);
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v61);
    v37 = (LPWCH *)TokenInformation;
    if ( !TokenInformation )
    {
      v4 = -2147024882;
      if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      {
        v61 = -2147024882;
        v48 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v38,
          (unsigned int)byte_1800C6773,
          v39,
          v40,
          (__int64)&v48,
          (__int64)&v61);
      }
      goto LABEL_77;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, nLengthNeeded, &nLengthNeeded) )
    {
      pListOfExplicitEntries.grfAccessPermissions = a2;
      pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
      pListOfExplicitEntries.grfInheritance = 3;
      pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
      *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
      pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
      pListOfExplicitEntries.Trustee.ptstrName = *v37;
      v42 = hMem;
      hMem = 0;
      if ( v42 )
        LocalFree(v42);
      v43 = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, (PACL *)&hMem);
      if ( !v43 )
      {
        if ( InitializeSecurityDescriptor(SecurityDescriptor, 1u) )
        {
          if ( SetSecurityDescriptorDacl(SecurityDescriptor, 1, (PACL)hMem, 0) )
          {
            if ( SetKernelObjectSecurity(v6, 4u, SecurityDescriptor) )
            {
              v4 = 0;
              goto LABEL_77;
            }
            v46 = GetLastError();
            v4 = ERROR_HR_FROM_WIN32(v46);
            if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
            {
              v11 = &byte_1800C6897;
              goto LABEL_7;
            }
          }
          else
          {
            v45 = GetLastError();
            v4 = ERROR_HR_FROM_WIN32(v45);
            if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
            {
              v11 = byte_1800C685D;
              goto LABEL_7;
            }
          }
        }
        else
        {
          v44 = GetLastError();
          v4 = ERROR_HR_FROM_WIN32(v44);
          if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
          {
            v11 = (char *)&dword_1800C681C;
            goto LABEL_7;
          }
        }
        goto LABEL_77;
      }
      v4 = ERROR_HR_FROM_WIN32(v43);
      if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
        goto LABEL_77;
      v33 = byte_1800C67E9;
    }
    else
    {
      v41 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v41);
      if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
        goto LABEL_77;
      v33 = byte_1800C67B3;
    }
LABEL_42:
    v61 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v30,
      (_DWORD)v33,
      v31,
      v32,
      (__int64)&v61);
    goto LABEL_77;
  }
  if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
  {
    v11 = (char *)&word_1800C659E;
    goto LABEL_7;
  }
LABEL_77:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&Handle);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&TokenInformation);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
  __1__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&hMem);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&pSecurityDescriptor);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006493c  mov     [rsp-8+arg_8], rbx
0x180064941  push    rbp
0x180064942  push    rsi
0x180064943  push    rdi
0x180064944  push    r12
0x180064946  push    r13
0x180064948  push    r14
0x18006494a  push    r15
0x18006494c  lea     rbp, [rsp-27h]
0x180064951  sub     rsp, 0E0h
0x180064958  mov     r15d, edx
0x18006495b  mov     r14, rcx
0x18006495e  xor     r12d, r12d
0x180064961  mov     [rbp+57h+nLengthNeeded], r12d
0x180064965  mov     [rbp+57h+pSecurityDescriptor], r12
0x180064969  xorps   xmm0, xmm0
0x18006496c  xor     eax, eax
0x18006496e  movups  [rbp+57h+SecurityDescriptor], xmm0
0x180064972  movups  [rbp+57h+var_50], xmm0
0x180064976  mov     [rbp+57h+var_40], rax
0x18006497a  mov     [rbp+57h+pDacl], r12
0x18006497e  mov     [rbp+57h+hMem], r12
0x180064982  mov     [rbp+57h+TokenHandle], r12
0x180064986  mov     [rbp+57h+TokenInformation], r12
0x18006498a  mov     [rbp+57h+bDaclPresent], r12d
0x18006498e  mov     [rbp+57h+bDaclDefaulted], r12d
0x180064992  mov     [rbp+57h+Handle], r12
0x180064996  test    rcx, rcx
0x180064999  jnz     short loc_1800649A5
0x18006499b  mov     ebx, 80070057h
0x1800649a0  jmp     loc_180065006
0x1800649a5  mov     [rsp+110h+hTemplateFile], r12; hTemplateFile
0x1800649aa  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800649b2  mov     eax, 3
0x1800649b7  mov     [rsp+110h+dwCreationDisposition], eax; dwCreationDisposition
0x1800649bb  xor     r9d, r9d; lpSecurityAttributes
0x1800649be  mov     r8d, eax; dwShareMode
0x1800649c1  mov     edx, 60000h; dwDesiredAccess
0x1800649c6  call    cs:__imp_CreateFileW
0x1800649cc  mov     rdx, rax
0x1800649cf  lea     rcx, [rbp+57h+Handle]
0x1800649d3  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800649d8  mov     rdi, [rbp+57h+Handle]
0x1800649dc  lea     rax, [rdi+1]
0x1800649e0  mov     r13d, 1
0x1800649e6  cmp     rax, r13
0x1800649e9  ja      short loc_180064A4B
0x1800649eb  call    cs:__imp_GetLastError
0x1800649f1  mov     ecx, eax; unsigned int
0x1800649f3  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800649f8  mov     ebx, eax
0x1800649fa  mov     eax, cs:dword_1800D8000
0x180064a00  cmp     eax, 2
0x180064a03  jbe     loc_180065006
0x180064a09  lea     edx, [r13+7]
0x180064a0d  lea     rcx, dword_1800D8000
0x180064a14  call    _tlgKeywordOn
0x180064a19  test    al, al
0x180064a1b  jz      loc_180065006
0x180064a21  lea     rdx, byte_1800C6561
0x180064a28  lea     rax, [rbp+57h+arg_18]
0x180064a2c  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax
0x180064a31  lea     rax, [rbp+57h+var_D0]
0x180064a35  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180064a3a  mov     [rbp+57h+var_D0], r14
0x180064a3e  mov     [rbp+57h+arg_18], ebx
0x180064a41  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180064a46  jmp     loc_180065006
0x180064a4b  mov     rdx, rdi; void *
0x180064a4e  mov     rcx, r14; wchar_t *
0x180064a51  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x180064a56  mov     ebx, eax
0x180064a58  test    eax, eax
0x180064a5a  jns     short loc_180064A8D
0x180064a5c  mov     ecx, cs:dword_1800D8000
0x180064a62  cmp     ecx, 2
0x180064a65  jbe     loc_180065006
0x180064a6b  mov     edx, 8
0x180064a70  lea     rcx, dword_1800D8000
0x180064a77  call    _tlgKeywordOn
0x180064a7c  test    al, al
0x180064a7e  jz      loc_180065006
0x180064a84  lea     rdx, word_1800C659E
0x180064a8b  jmp     short loc_180064A28
0x180064a8d  lea     rax, [rbp+57h+nLengthNeeded]
0x180064a91  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; lpnLengthNeeded
0x180064a96  xor     r9d, r9d; nLength
0x180064a99  xor     r8d, r8d; pSecurityDescriptor
0x180064a9c  lea     esi, [r9+4]
0x180064aa0  mov     edx, esi; RequestedInformation
0x180064aa2  mov     rcx, rdi; Handle
0x180064aa5  call    cs:__imp_GetKernelObjectSecurity
0x180064aab  test    eax, eax
0x180064aad  jnz     short loc_180064B01
0x180064aaf  call    cs:__imp_GetLastError
0x180064ab5  mov     ecx, eax; unsigned int
0x180064ab7  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180064abc  mov     ebx, eax
0x180064abe  mov     eax, [rbp+57h+nLengthNeeded]
0x180064ac1  test    eax, eax
0x180064ac3  jz      short loc_180064ACD
0x180064ac5  cmp     ebx, 8007007Ah
0x180064acb  jz      short loc_180064B04
0x180064acd  mov     eax, cs:dword_1800D8000
0x180064ad3  cmp     eax, 2
0x180064ad6  jbe     loc_180065006
0x180064adc  mov     edx, 8
0x180064ae1  lea     rcx, dword_1800D8000
0x180064ae8  call    _tlgKeywordOn
0x180064aed  test    al, al
0x180064aef  jz      loc_180065006
0x180064af5  lea     rdx, byte_1800C65D7
0x180064afc  jmp     loc_180064A28
0x180064b01  mov     eax, [rbp+57h+nLengthNeeded]
0x180064b04  mov     edx, eax
0x180064b06  lea     rcx, [rbp+57h+arg_18]
0x180064b0a  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x180064b0f  mov     rdx, rax
0x180064b12  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x180064b16  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x180064b1b  lea     rcx, [rbp+57h+arg_18]; void *
0x180064b1f  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180064b24  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x180064b28  test    rbx, rbx
0x180064b2b  jnz     short loc_180064B83
0x180064b2d  mov     ebx, 8007000Eh
0x180064b32  mov     eax, cs:dword_1800D8000
0x180064b38  cmp     eax, 2
0x180064b3b  jbe     loc_180065006
0x180064b41  mov     edx, 8
0x180064b46  lea     rcx, dword_1800D8000
0x180064b4d  call    _tlgKeywordOn
0x180064b52  test    al, al
0x180064b54  jz      loc_180065006
0x180064b5a  mov     [rbp+57h+arg_18], 8007000Eh
0x180064b61  mov     [rbp+57h+var_D0], r14
0x180064b65  lea     rax, [rbp+57h+arg_18]
0x180064b69  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax
0x180064b6e  lea     rax, [rbp+57h+var_D0]
0x180064b72  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180064b77  lea     rdx, word_1800C6616
0x180064b7e  jmp     loc_180064A41
0x180064b83  lea     rax, [rbp+57h+nLengthNeeded]
0x180064b87  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; lpnLengthNeeded
0x180064b8c  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180064b90  mov     r8, rbx; pSecurityDescriptor
0x180064b93  mov     edx, esi; RequestedInformation
0x180064b95  mov     rcx, rdi; Handle
0x180064b98  call    cs:__imp_GetKernelObjectSecurity
0x180064b9e  test    eax, eax
0x180064ba0  jnz     short loc_180064BE5
0x180064ba2  call    cs:__imp_GetLastError
0x180064ba8  mov     ecx, eax; unsigned int
0x180064baa  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180064baf  mov     ebx, eax
0x180064bb1  mov     eax, cs:dword_1800D8000
0x180064bb7  cmp     eax, 2
0x180064bba  jbe     loc_180065006
0x180064bc0  mov     edx, 8
0x180064bc5  lea     rcx, dword_1800D8000
0x180064bcc  call    _tlgKeywordOn
0x180064bd1  test    al, al
0x180064bd3  jz      loc_180065006
0x180064bd9  lea     rdx, byte_1800C6653
0x180064be0  jmp     loc_180064A28
0x180064be5  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180064be9  lea     r8, [rbp+57h+pDacl]; pDacl
0x180064bed  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180064bf1  mov     rcx, rbx; pSecurityDescriptor
0x180064bf4  call    cs:__imp_GetSecurityDescriptorDacl
0x180064bfa  test    eax, eax
0x180064bfc  jnz     short loc_180064C41
0x180064bfe  call    cs:__imp_GetLastError
0x180064c04  mov     ecx, eax; unsigned int
0x180064c06  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180064c0b  mov     ebx, eax
0x180064c0d  mov     eax, cs:dword_1800D8000
0x180064c13  cmp     eax, 2
0x180064c16  jbe     loc_180065006
0x180064c1c  mov     edx, 8
0x180064c21  lea     rcx, dword_1800D8000
0x180064c28  call    _tlgKeywordOn
0x180064c2d  test    al, al
0x180064c2f  jz      loc_180065006
0x180064c35  lea     rdx, word_1800C6692
0x180064c3c  jmp     loc_180064A28
0x180064c41  cmp     [rbp+57h+bDaclPresent], r12d
0x180064c45  jnz     short loc_180064C4B
0x180064c47  mov     [rbp+57h+pDacl], r12
0x180064c4b  lea     rcx, [rbp+57h+TokenHandle]
0x180064c4f  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180064c54  mov     rbx, rax
0x180064c57  call    cs:__imp_GetCurrentThread
0x180064c5d  mov     r9, rbx; TokenHandle
0x180064c60  xor     r8d, r8d; OpenAsSelf
0x180064c63  lea     esi, [r8+8]
0x180064c67  mov     edx, esi; DesiredAccess
0x180064c69  mov     rcx, rax; ThreadHandle
0x180064c6c  call    cs:__imp_OpenThreadToken
0x180064c72  test    eax, eax
0x180064c74  jnz     loc_180064D36
0x180064c7a  call    cs:__imp_GetLastError
0x180064c80  mov     ecx, eax; unsigned int
0x180064c82  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180064c87  mov     r8d, eax
0x180064c8a  mov     ecx, cs:dword_1800D8000
0x180064c90  cmp     ecx, 3
0x180064c93  jbe     short loc_180064CC0
0x180064c95  mov     edx, esi
0x180064c97  lea     rcx, dword_1800D8000
0x180064c9e  call    _tlgKeywordOn
0x180064ca3  test    al, al
0x180064ca5  jz      short loc_180064CC0
0x180064ca7  mov     [rbp+57h+arg_18], r8d
0x180064cab  lea     rax, [rbp+57h+arg_18]
0x180064caf  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180064cb4  lea     rdx, dword_1800C66CC
0x180064cbb  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180064cc0  lea     rcx, [rbp+57h+TokenHandle]
0x180064cc4  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180064cc9  mov     rbx, rax
0x180064ccc  call    cs:__imp_GetCurrentProcess
0x180064cd2  mov     r8, rbx; TokenHandle
0x180064cd5  mov     edx, esi; DesiredAccess
0x180064cd7  mov     rcx, rax; ProcessHandle
0x180064cda  call    cs:__imp_OpenProcessToken
0x180064ce0  test    eax, eax
0x180064ce2  jnz     short loc_180064D36
0x180064ce4  call    cs:__imp_GetLastError
0x180064cea  mov     ecx, eax; unsigned int
0x180064cec  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180064cf1  mov     ebx, eax
0x180064cf3  mov     eax, cs:dword_1800D8000
0x180064cf9  cmp     eax, 2
0x180064cfc  jbe     loc_180065006
0x180064d02  mov     rdx, rsi
0x180064d05  lea     rcx, dword_1800D8000
0x180064d0c  call    _tlgKeywordOn
0x180064d11  test    al, al
0x180064d13  jz      loc_180065006
0x180064d19  lea     rdx, dword_1800C6704
0x180064d20  lea     rax, [rbp+57h+arg_18]
0x180064d24  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180064d29  mov     [rbp+57h+arg_18], ebx
0x180064d2c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180064d31  jmp     loc_180065006
0x180064d36  lea     rax, [rbp+57h+nLengthNeeded]
0x180064d3a  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; ReturnLength
0x180064d3f  xor     r9d, r9d; TokenInformationLength
0x180064d42  xor     r8d, r8d; TokenInformation
0x180064d45  mov     edx, r13d; TokenInformationClass
0x180064d48  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180064d4c  call    cs:__imp_GetTokenInformation
0x180064d52  test    eax, eax
0x180064d54  jnz     short loc_180064DA6
0x180064d56  call    cs:__imp_GetLastError
0x180064d5c  mov     ecx, eax; unsigned int
0x180064d5e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180064d63  mov     ebx, eax
0x180064d65  mov     eax, [rbp+57h+nLengthNeeded]
0x180064d68  test    eax, eax
0x180064d6a  jz      short loc_180064D74
0x180064d6c  cmp     ebx, 8007007Ah
0x180064d72  jz      short loc_180064DA9
0x180064d74  mov     eax, cs:dword_1800D8000
0x180064d7a  cmp     eax, 2
0x180064d7d  jbe     loc_180065006
0x180064d83  mov     rdx, rsi
0x180064d86  lea     rcx, dword_1800D8000
0x180064d8d  call    _tlgKeywordOn
0x180064d92  test    al, al
0x180064d94  jz      loc_180065006
0x180064d9a  lea     rdx, byte_1800C673D
0x180064da1  jmp     loc_180064D20
0x180064da6  mov     eax, [rbp+57h+nLengthNeeded]
0x180064da9  mov     edx, eax
0x180064dab  lea     rcx, [rbp+57h+arg_18]
0x180064daf  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x180064db4  mov     rdx, rax
0x180064db7  lea     rcx, [rbp+57h+TokenInformation]
0x180064dbb  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x180064dc0  lea     rcx, [rbp+57h+arg_18]; void *
0x180064dc4  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180064dc9  mov     rbx, [rbp+57h+TokenInformation]
0x180064dcd  test    rbx, rbx
0x180064dd0  jnz     short loc_180064E26
0x180064dd2  mov     ebx, 8007000Eh
0x180064dd7  mov     eax, cs:dword_1800D8000
0x180064ddd  cmp     eax, 2
0x180064de0  jbe     loc_180065006
0x180064de6  mov     rdx, rsi
0x180064de9  lea     rcx, dword_1800D8000
0x180064df0  call    _tlgKeywordOn
0x180064df5  test    al, al
0x180064df7  jz      loc_180065006
0x180064dfd  mov     [rbp+57h+arg_18], 8007000Eh
0x180064e04  mov     [rbp+57h+var_D0], r14
0x180064e08  lea     rax, [rbp+57h+arg_18]
0x180064e0c  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax
0x180064e11  lea     rax, [rbp+57h+var_D0]
  ... truncated ...
```
