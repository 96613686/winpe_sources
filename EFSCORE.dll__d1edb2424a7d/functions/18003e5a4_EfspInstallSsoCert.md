# EfspInstallSsoCert

- ea: `0x18003e5a4`
- end: `0x18003eb31`
- name: `EfspInstallSsoCert`
- size: `1421`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180036aac`

## callees

- `0x180004f86`
- `0x1800102f0`
- `0x180010bf0`
- `0x180012d68`
- `0x18001ee88`
- `0x18001efb8`
- `0x180027934`
- `0x1800350d0`
- `0x180038138`
- `0x18003854c`
- `0x180039838`
- `0x18003cfe0`
- `0x18003e5a4`
- `0x180063600`
- `0x180063698`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18003e636`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18003e636`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003e718`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003eaf9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003e718`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003eaf9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003e6ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003e6ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e9a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e9a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e6b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e9ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e6b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e9ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003eb07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003eb07`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003e980`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003e980`
- `CRYPT32!CertFreeCertificateContext` at `0x18003e99a`
- `CRYPT32!CertFreeCertificateContext` at `0x18003eab8`
- `CRYPT32!CertFreeCertificateContext` at `0x18003eac6`
- `CRYPT32!CertFreeCertificateContext` at `0x18003e99a`
- `CRYPT32!CertFreeCertificateContext` at `0x18003eab8`
- `CRYPT32!CertFreeCertificateContext` at `0x18003eac6`

## pseudocode

```c
__int64 __fastcall EfspInstallSsoCert(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  unsigned __int16 *v3; // rdx
  HANDLE MutexW; // r12
  unsigned __int16 *v6; // r14
  void *CertHashFromCertContext; // rsi
  PCCERT_CONTEXT v8; // r13
  int v9; // r15d
  DWORD MutexName; // edi
  int v11; // eax
  DWORD v12; // eax
  int v13; // eax
  void *v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  PCCERT_CONTEXT v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  DWORD v21; // eax
  char v22; // r15
  int v23; // r8d
  unsigned int v24; // r15d
  DWORD LastError; // edi
  int v26; // ebx
  const CERT_CONTEXT *CertContextFromCertHash; // rax
  int v28; // ebx
  __int64 v29; // rax
  __int64 v30; // rdx
  unsigned __int16 *i; // rax
  unsigned int v33; // [rsp+38h] [rbp-59h] BYREF
  void *v34; // [rsp+40h] [rbp-51h] BYREF
  PCCERT_CONTEXT v35; // [rsp+48h] [rbp-49h] BYREF
  unsigned __int16 *v36; // [rsp+50h] [rbp-41h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+58h] [rbp-39h] BYREF
  LPCWSTR lpName; // [rsp+60h] [rbp-31h]
  __int64 v39; // [rsp+68h] [rbp-29h]
  __int64 v40; // [rsp+70h] [rbp-21h] BYREF
  __int128 v41; // [rsp+78h] [rbp-19h] BYREF
  __int64 v42; // [rsp+88h] [rbp-9h]
  __int64 v43; // [rsp+90h] [rbp-1h]
  __int128 *v44; // [rsp+98h] [rbp+7h]
  size_t Size; // [rsp+110h] [rbp+7Fh] BYREF

  v3 = *(unsigned __int16 **)(a1 + 24);
  MutexW = 0;
  v36 = 0;
  LODWORD(Size) = 0;
  v6 = 0;
  v33 = 0;
  v41 = 0;
  v42 = 0;
  CertHashFromCertContext = 0;
  v43 = 0;
  v8 = 0;
  v34 = 0;
  v9 = 0;
  pCertContext = 0;
  v35 = 0;
  v39 = 0;
  lpName = 0;
  v40 = 0;
  MutexName = EfspGenerateMutexName(L"Local\\{0F56A024-6F1E-4bce-9CEC-36C3F0BC9C3C}", v3);
  if ( MutexName )
    goto LABEL_42;
  MutexW = CreateMutexW(0, 1, lpName);
  if ( !MutexW )
  {
    MutexName = GetLastError();
    v11 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, MutexName, 12, 206);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v11, 12, 206);
    goto LABEL_54;
  }
  if ( GetLastError() != 183 )
  {
    EfsSsoObtainSmartcardCredsFromLSA(&v36, &pCertContext);
    v17 = pCertContext;
    v6 = v36;
    if ( pCertContext )
    {
      if ( v36 )
      {
        v18 = EfspSelectSSoCert(pCertContext, v36, &v35, &v33);
        MutexName = v18;
        if ( v18 )
        {
          v20 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v18, 12, 78);
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v20, 12, 78);
          v8 = v35;
LABEL_41:
          v9 = 1;
          goto LABEL_42;
        }
        v8 = v35;
        if ( !v35 )
        {
          MutexName = -2146885628;
          fnEfsLogTrace0(v19, EFS_SSO_OPERATION_LOGON_CERT_NOT_AVAILABLE, 12, 3156);
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2146885628, 12, 85);
          goto LABEL_41;
        }
        CertHashFromCertContext = (void *)GetCertHashFromCertContext(v35, (DWORD *)&Size);
        if ( CertHashFromCertContext )
        {
          v24 = Size;
          LastError = 0;
          v26 = 20;
          while ( 1 )
          {
            CertContextFromCertHash = (const CERT_CONTEXT *)GetCertContextFromCertHash(
                                                              CertHashFromCertContext,
                                                              v24,
                                                              0x10000);
            if ( CertContextFromCertHash )
              break;
            LastError = GetLastError();
            Sleep(0x2710u);
            if ( --v26 <= 0 )
            {
              v28 = 0;
              goto LABEL_31;
            }
          }
          v28 = 1;
          CertFreeCertificateContext(CertContextFromCertHash);
LABEL_31:
          SetLastError(LastError);
          if ( v28 )
          {
            LODWORD(v41) = v8->dwCertEncodingType;
            *((_QWORD *)&v41 + 1) = v8->pbCertEncoded;
            DWORD1(v41) = v8->cbCertEncoded;
            v44 = &v41;
            v21 = EfspInstallCertAsUserKey((struct _EFS_USER_INFO *)a1, (__int64)v6);
            MutexName = v21;
            if ( !v21 )
            {
              v9 = 1;
              goto LABEL_36;
            }
            v22 = 119;
            goto LABEL_25;
          }
          v21 = GetLastError();
          v22 = 105;
        }
        else
        {
          v21 = GetLastError();
          v22 = 97;
        }
        MutexName = v21;
LABEL_25:
        v23 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v21, 12, v22);
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v23, 12, v22);
        goto LABEL_41;
      }
    }
    else if ( !v36 )
    {
      goto LABEL_39;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_39:
    MutexName = -2146885628;
    fnEfsLogTrace0(v17, EFS_SSO_OPERATION_LOGON_CERT_NOT_AVAILABLE, 12, 3136);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2146885628, 12, 65);
    goto LABEL_41;
  }
  v12 = WaitForSingleObject(MutexW, 0xFFFFFFFF);
  if ( v12 == -1 )
  {
    MutexName = GetLastError();
    v13 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, MutexName, 12, 239);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v13, 12, 239);
    goto LABEL_54;
  }
  MutexName = 0;
  if ( v12 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  ReleaseMutex(MutexW);
  if ( (unsigned int)EfsGetKeyFromCache(a1, 36, 0) )
  {
    LODWORD(Size) = *(_DWORD *)(*(_QWORD *)v39 + 4LL);
    v14 = wil::details::heap_allocator::allocate((unsigned int)Size);
    CertHashFromCertContext = v14;
    if ( !v14 )
    {
      MutexName = 8;
      v15 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 8, 12, 12);
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v15, 12, 12);
      goto LABEL_52;
    }
    memcpy_0(v14, *(const void **)(*(_QWORD *)v39 + 8LL), (unsigned int)Size);
    goto LABEL_36;
  }
  if ( !(unsigned int)GetCurrentKey_LoadFromRegistrySafe(a1, &v40, &v34, &Size) )
  {
    CertHashFromCertContext = v34;
LABEL_36:
    *a2 = CertHashFromCertContext;
    CertHashFromCertContext = 0;
    *a3 = Size;
LABEL_42:
    if ( v6 )
    {
      v29 = -1;
      do
        ++v29;
      while ( v6[v29] );
      v30 = 2 * v29;
      for ( i = v6; v30; --v30 )
      {
        *(_BYTE *)i = 0;
        i = (unsigned __int16 *)((char *)i + 1);
      }
      EfsFreeHeap(v6);
    }
    if ( pCertContext )
      CertFreeCertificateContext(pCertContext);
    if ( v8 )
      CertFreeCertificateContext(v8);
    goto LABEL_52;
  }
  MutexName = -2146885628;
  fnEfsLogTrace0(v16, EFS_SSO_OPERATION_LOGON_CERT_NOT_AVAILABLE, 12, 3125);
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2146885628, 12, 54);
  CertHashFromCertContext = v34;
  v9 = 0;
LABEL_52:
  if ( CertHashFromCertContext )
    EfsFreeHeap(CertHashFromCertContext);
LABEL_54:
  if ( lpName )
    EfsFreeHeap((LPVOID)lpName);
  if ( v9 )
  {
    if ( !MutexW )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    ReleaseMutex(MutexW);
  }
  if ( MutexW )
    CloseHandle(MutexW);
  if ( v40 )
    EfsReleaseUserKeyInfo();
  return MutexName;
}

```

## disassembly

```asm
0x18003e5a4  mov     rax, rsp
0x18003e5a7  mov     [rax+18h], r8
0x18003e5ab  mov     [rax+10h], rdx
0x18003e5af  mov     [rax+8], rcx
0x18003e5b3  push    rbp
0x18003e5b4  push    rbx
0x18003e5b5  push    rsi
0x18003e5b6  push    rdi
0x18003e5b7  push    r12
0x18003e5b9  push    r13
0x18003e5bb  push    r14
0x18003e5bd  push    r15
0x18003e5bf  lea     rbp, [rax-5Fh]
0x18003e5c3  sub     rsp, 0A8h
0x18003e5ca  mov     rdx, [rcx+18h]; unsigned __int16 *
0x18003e5ce  lea     r8, [rbp+57h+lpName]
0x18003e5d2  xor     r12d, r12d
0x18003e5d5  mov     rbx, rcx
0x18003e5d8  xorps   xmm0, xmm0
0x18003e5db  mov     [rbp+57h+var_98], r12
0x18003e5df  lea     rcx, aLocal0f56a0246; "Local\\{0F56A024-6F1E-4bce-9CEC-36C3F0B"...
0x18003e5e6  mov     dword ptr [rbp+57h+Size], r12d
0x18003e5ea  mov     r14d, r12d
0x18003e5ed  mov     [rbp+57h+var_B0], r12d
0x18003e5f1  movups  [rbp+57h+var_70], xmm0
0x18003e5f5  mov     [rbp+57h+var_60], r12
0x18003e5f9  mov     esi, r12d
0x18003e5fc  mov     [rbp+57h+var_58], r12
0x18003e600  mov     r13d, r12d
0x18003e603  mov     [rbp+57h+var_A8], r12
0x18003e607  mov     r15d, r12d
0x18003e60a  mov     [rbp+57h+pCertContext], r12
0x18003e60e  mov     [rbp+57h+var_A0], r12
0x18003e612  mov     [rbp+57h+var_80], r12
0x18003e616  mov     [rbp+57h+lpName], r12
0x18003e61a  mov     [rbp+57h+var_78], r12
0x18003e61e  call    EfspGenerateMutexName
0x18003e623  mov     edi, eax
0x18003e625  test    eax, eax
0x18003e627  jnz     loc_18003EA78
0x18003e62d  mov     r8, [rbp+57h+lpName]; lpName
0x18003e631  lea     edx, [rax+1]; bInitialOwner
0x18003e634  xor     ecx, ecx; lpMutexAttributes
0x18003e636  call    cs:__imp_CreateMutexW
0x18003e63c  mov     r12, rax
0x18003e63f  test    rax, rax
0x18003e642  jnz     short loc_18003E694
0x18003e644  call    cs:__imp_GetLastError
0x18003e64a  mov     rcx, cs:g_hPublisher
0x18003e651  lea     ebx, [r13+0Ch]
0x18003e655  mov     esi, 0BCEh
0x18003e65a  lea     rdx, EFS_API_ERROR
0x18003e661  mov     r9d, ebx
0x18003e664  mov     dword ptr [rsp+0E0h+var_C0], esi
0x18003e668  mov     r8d, eax
0x18003e66b  mov     edi, eax
0x18003e66d  call    fnEfsLogTrace1
0x18003e672  mov     rcx, cs:g_hPublisher
0x18003e679  lea     rdx, EFS_TRACE_ERROR
0x18003e680  mov     r9d, ebx
0x18003e683  mov     dword ptr [rsp+0E0h+var_C0], esi
0x18003e687  mov     r8d, eax
0x18003e68a  call    fnEfsLogTrace1
0x18003e68f  jmp     loc_18003EAD9
0x18003e694  call    cs:__imp_GetLastError
0x18003e69a  cmp     eax, 0B7h
0x18003e69f  jnz     loc_18003E839
0x18003e6a5  or      edi, 0FFFFFFFFh
0x18003e6a8  mov     rcx, r12; hHandle
0x18003e6ab  mov     edx, edi; dwMilliseconds
0x18003e6ad  call    cs:__imp_WaitForSingleObject
0x18003e6b3  cmp     eax, edi
0x18003e6b5  jnz     short loc_18003E70A
0x18003e6b7  call    cs:__imp_GetLastError
0x18003e6bd  mov     rcx, cs:g_hPublisher
0x18003e6c4  lea     rdx, EFS_API_ERROR
0x18003e6cb  mov     ebx, 0Ch
0x18003e6d0  mov     esi, 0BEFh
0x18003e6d5  mov     r9d, ebx
0x18003e6d8  mov     dword ptr [rsp+0E0h+var_C0], esi
0x18003e6dc  mov     r8d, eax
0x18003e6df  mov     edi, eax
0x18003e6e1  call    fnEfsLogTrace1
0x18003e6e6  mov     rcx, cs:g_hPublisher
0x18003e6ed  lea     rdx, EFS_TRACE_ERROR
0x18003e6f4  mov     r9d, ebx
0x18003e6f7  mov     dword ptr [rsp+0E0h+var_C0], esi
0x18003e6fb  mov     r8d, eax
0x18003e6fe  call    fnEfsLogTrace1
0x18003e703  xor     esi, esi
0x18003e705  jmp     loc_18003EAD9
0x18003e70a  xor     edi, edi
0x18003e70c  test    eax, eax
0x18003e70e  jz      short loc_18003E715
0x18003e710  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "rc == WAIT_OBJECT_0")
0x18003e715  mov     rcx, r12; hMutex
0x18003e718  call    cs:__imp_ReleaseMutex
0x18003e71e  xor     r9d, r9d
0x18003e721  lea     rax, [rbp+57h+var_80]
0x18003e725  mov     [rsp+28h], rax
0x18003e72a  xor     r8d, r8d
0x18003e72d  mov     rcx, rbx
0x18003e730  mov     dword ptr [rsp+0E0h+var_C0], edi
0x18003e734  lea     edx, [r9+24h]
0x18003e738  call    EfsGetKeyFromCache
0x18003e73d  test    eax, eax
0x18003e73f  jz      loc_18003E7C6
0x18003e745  mov     rbx, [rbp+57h+var_80]
0x18003e749  mov     rax, [rbx]
0x18003e74c  mov     ecx, [rax+4]; unsigned __int64
0x18003e74f  mov     dword ptr [rbp+57h+Size], ecx
0x18003e752  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18003e757  mov     rsi, rax
0x18003e75a  test    rax, rax
0x18003e75d  jnz     short loc_18003E7AE
0x18003e75f  mov     rcx, cs:g_hPublisher
0x18003e766  lea     edi, [rax+8]
0x18003e769  lea     ebx, [rax+0Ch]
0x18003e76c  mov     r14d, 0C0Ch
0x18003e772  mov     r9d, ebx
0x18003e775  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x18003e77a  mov     r8d, edi
0x18003e77d  lea     rdx, EFS_API_ERROR
0x18003e784  call    fnEfsLogTrace1
0x18003e789  mov     rcx, cs:g_hPublisher
0x18003e790  lea     rdx, EFS_TRACE_ERROR
0x18003e797  mov     r9d, ebx
0x18003e79a  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x18003e79f  mov     r8d, eax
0x18003e7a2  call    fnEfsLogTrace1
0x18003e7a7  xor     ebx, ebx
0x18003e7a9  jmp     loc_18003EACC
0x18003e7ae  mov     rdx, [rbx]
0x18003e7b1  mov     rcx, rax; void *
0x18003e7b4  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18003e7b8  mov     rdx, [rdx+8]; Src
0x18003e7bc  call    memcpy_0
0x18003e7c1  jmp     loc_18003EA0E
0x18003e7c6  lea     r9, [rbp+57h+Size]
0x18003e7ca  mov     rcx, rbx
0x18003e7cd  lea     r8, [rbp+57h+var_A8]
0x18003e7d1  lea     rdx, [rbp+57h+var_78]
0x18003e7d5  call    GetCurrentKey_LoadFromRegistrySafe
0x18003e7da  test    eax, eax
0x18003e7dc  jnz     short loc_18003E7E7
0x18003e7de  mov     rsi, [rbp+57h+var_A8]
0x18003e7e2  jmp     loc_18003EA0E
0x18003e7e7  mov     ebx, 0Ch
0x18003e7ec  lea     rdx, EFS_SSO_OPERATION_LOGON_CERT_NOT_AVAILABLE
0x18003e7f3  mov     r15d, 80092004h
0x18003e7f9  mov     r8d, ebx
0x18003e7fc  mov     r9d, 0C35h
0x18003e802  mov     edi, r15d
0x18003e805  call    fnEfsLogTrace0
0x18003e80a  mov     rcx, cs:g_hPublisher
0x18003e811  lea     rdx, EFS_TRACE_ERROR
0x18003e818  mov     r9d, ebx
0x18003e81b  mov     dword ptr [rsp+0E0h+var_C0], 0C36h
0x18003e823  mov     r8d, r15d
0x18003e826  call    fnEfsLogTrace1
0x18003e82b  mov     rsi, [rbp+57h+var_A8]
0x18003e82f  xor     ebx, ebx
0x18003e831  mov     r15d, ebx
0x18003e834  jmp     loc_18003EACC
0x18003e839  lea     rdx, [rbp+57h+pCertContext]
0x18003e83d  lea     rcx, [rbp+57h+var_98]
0x18003e841  call    EfsSsoObtainSmartcardCredsFromLSA
0x18003e846  mov     rcx, [rbp+57h+pCertContext]; pCertContext
0x18003e84a  xor     ebx, ebx
0x18003e84c  mov     r14, [rbp+57h+var_98]
0x18003e850  test    rcx, rcx
0x18003e853  jz      loc_18003EA24
0x18003e859  test    r14, r14
0x18003e85c  jz      loc_18003EA29
0x18003e862  lea     r9, [rbp+57h+var_B0]; unsigned int *
0x18003e866  mov     rdx, r14; unsigned __int16 *
0x18003e869  lea     r8, [rbp+57h+var_A0]; struct _CERT_CONTEXT **
0x18003e86d  call    ?EfspSelectSSoCert@@YAKPEBU_CERT_CONTEXT@@PEBGPEAPEBU1@PEAK@Z; EfspSelectSSoCert(_CERT_CONTEXT const *,ushort const *,_CERT_CONTEXT const * *,ulong *)
0x18003e872  mov     edi, eax
0x18003e874  test    eax, eax
0x18003e876  jz      short loc_18003E8C8
0x18003e878  mov     rcx, cs:g_hPublisher
0x18003e87f  lea     rdx, EFS_API_ERROR
0x18003e886  mov     ebx, 0Ch
0x18003e88b  mov     r15d, 0C4Eh
0x18003e891  mov     r9d, ebx
0x18003e894  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x18003e899  mov     r8d, eax
0x18003e89c  call    fnEfsLogTrace1
0x18003e8a1  mov     rcx, cs:g_hPublisher
0x18003e8a8  lea     rdx, EFS_TRACE_ERROR
0x18003e8af  mov     r9d, ebx
0x18003e8b2  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x18003e8b7  mov     r8d, eax
0x18003e8ba  call    fnEfsLogTrace1
0x18003e8bf  mov     r13, [rbp+57h+var_A0]
0x18003e8c3  jmp     loc_18003EA72
0x18003e8c8  mov     r13, [rbp+57h+var_A0]
0x18003e8cc  test    r13, r13
0x18003e8cf  jnz     short loc_18003E900
0x18003e8d1  lea     ebx, [r13+0Ch]
0x18003e8d5  mov     r15d, 80092004h
0x18003e8db  mov     r8d, ebx
0x18003e8de  lea     rdx, EFS_SSO_OPERATION_LOGON_CERT_NOT_AVAILABLE
0x18003e8e5  mov     r9d, 0C54h
0x18003e8eb  mov     edi, r15d
0x18003e8ee  call    fnEfsLogTrace0
0x18003e8f3  mov     dword ptr [rsp+0E0h+var_C0], 0C55h
0x18003e8fb  jmp     loc_18003EA59
0x18003e900  lea     rdx, [rbp+57h+Size]; pcbData
0x18003e904  mov     rcx, r13; pCertContext
0x18003e907  call    GetCertHashFromCertContext
0x18003e90c  mov     rsi, rax
0x18003e90f  test    rax, rax
0x18003e912  jnz     short loc_18003E952
0x18003e914  call    cs:__imp_GetLastError
0x18003e91a  mov     r15d, 0C61h
0x18003e920  mov     edi, eax
0x18003e922  mov     rcx, cs:g_hPublisher
0x18003e929  lea     rdx, EFS_API_ERROR
0x18003e930  mov     ebx, 0Ch
0x18003e935  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x18003e93a  mov     r9d, ebx
0x18003e93d  mov     r8d, eax
0x18003e940  call    fnEfsLogTrace1
0x18003e945  mov     r8d, eax
0x18003e948  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x18003e94d  jmp     loc_18003EA5C
0x18003e952  mov     r15d, dword ptr [rbp+57h+Size]
0x18003e956  mov     edi, ebx
0x18003e958  mov     ebx, 14h
0x18003e95d  mov     r8d, 10000h
0x18003e963  mov     edx, r15d
0x18003e966  mov     rcx, rsi
0x18003e969  call    GetCertContextFromCertHash
0x18003e96e  test    rax, rax
0x18003e971  jnz     short loc_18003E992
0x18003e973  call    cs:__imp_GetLastError
0x18003e979  mov     ecx, 2710h; dwMilliseconds
0x18003e97e  mov     edi, eax
0x18003e980  call    cs:__imp_Sleep
0x18003e986  xor     eax, eax
0x18003e988  dec     ebx
0x18003e98a  test    ebx, ebx
0x18003e98c  jg      short loc_18003E95D
0x18003e98e  mov     ebx, eax
0x18003e990  jmp     short loc_18003E9A0
0x18003e992  mov     rcx, rax; pCertContext
0x18003e995  mov     ebx, 1
0x18003e99a  call    cs:__imp_CertFreeCertificateContext
0x18003e9a0  mov     ecx, edi; dwErrCode
0x18003e9a2  call    cs:__imp_SetLastError
0x18003e9a8  test    ebx, ebx
0x18003e9aa  jnz     short loc_18003E9BD
0x18003e9ac  call    cs:__imp_GetLastError
0x18003e9b2  mov     r15d, 0C69h
0x18003e9b8  jmp     loc_18003E920
0x18003e9bd  mov     eax, [r13+0]
0x18003e9c1  lea     rdx, [rbp+57h+var_60]
0x18003e9c5  mov     r8d, [rbp+57h+var_B0]
0x18003e9c9  mov     r9d, 1
0x18003e9cf  mov     rcx, [rbp+57h+arg_0]; struct _EFS_USER_INFO *
0x18003e9d3  mov     dword ptr [rbp+57h+var_70], eax
0x18003e9d6  mov     rax, [r13+8]
0x18003e9da  mov     qword ptr [rbp+57h+var_70+8], rax
0x18003e9de  mov     eax, [r13+10h]
0x18003e9e2  mov     dword ptr [rbp+57h+var_70+4], eax
0x18003e9e5  lea     rax, [rbp+57h+var_70]
0x18003e9e9  mov     [rbp+57h+var_50], rax
0x18003e9ed  mov     [rsp+0E0h+var_C0], r14; __int64
0x18003e9f2  call    EfspInstallCertAsUserKey
0x18003e9f7  mov     edi, eax
0x18003e9f9  test    eax, eax
0x18003e9fb  jz      short loc_18003EA08
0x18003e9fd  mov     r15d, 0C77h
0x18003ea03  jmp     loc_18003E922
0x18003ea08  mov     r15d, 1
0x18003ea0e  mov     rax, [rbp+57h+arg_8]
0x18003ea12  xor     ebx, ebx
0x18003ea14  mov     rcx, [rbp+57h+arg_10]
0x18003ea18  mov     [rax], rsi
0x18003ea1b  mov     esi, ebx
0x18003ea1d  mov     eax, dword ptr [rbp+57h+Size]
0x18003ea20  mov     [rcx], eax
0x18003ea22  jmp     short loc_18003EA7A
0x18003ea24  test    r14, r14
0x18003ea27  jz      short loc_18003EA2E
0x18003ea29  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "NULL == pcLogonCert && NULL == wszPIN")
0x18003ea2e  mov     ebx, 0Ch
0x18003ea33  lea     rdx, EFS_SSO_OPERATION_LOGON_CERT_NOT_AVAILABLE
0x18003ea3a  mov     r15d, 80092004h
0x18003ea40  mov     r8d, ebx
0x18003ea43  mov     r9d, 0C40h
0x18003ea49  mov     edi, r15d
0x18003ea4c  call    fnEfsLogTrace0
0x18003ea51  mov     dword ptr [rsp+0E0h+var_C0], 0C41h
0x18003ea59  mov     r8d, r15d
0x18003ea5c  mov     rcx, cs:g_hPublisher
0x18003ea63  lea     rdx, EFS_TRACE_ERROR
0x18003ea6a  mov     r9d, ebx
  ... truncated ...
```
