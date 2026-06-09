# ShieldProvider::DataProtectionShield::RefreshPillarStatus(int *)

- ea: `0x180079a00`
- end: `0x180079d40`
- name: `?RefreshPillarStatus@DataProtectionShield@ShieldProvider@@UEAAJPEAH@Z`
- size: `832`
- prototype: `__int64 __fastcall(ShieldProvider::DataProtectionShield *__hidden this, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180004ae0`
- `0x18000ccd4`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x180011730`
- `0x180076ea0`
- `0x18007963c`
- `0x180079a00`
- `0x180079d48`
- `0x1800df1b0`
- `0x1800df668`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180079af2`
- `KERNEL32!GetLastError` at `0x180079af2`
- `KERNEL32!CloseHandle` at `0x180079bb8`
- `KERNEL32!CloseHandle` at `0x180079bf9`
- `KERNEL32!CloseHandle` at `0x180079c5b`
- `KERNEL32!CloseHandle` at `0x180079bb8`
- `KERNEL32!CloseHandle` at `0x180079bf9`
- `KERNEL32!CloseHandle` at `0x180079c5b`
- `KERNEL32!GetCurrentThread` at `0x180079ad4`
- `KERNEL32!GetCurrentThread` at `0x180079ad4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180079ae8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180079ae8`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::RefreshPillarStatus(
        ShieldProvider::DataProtectionShield *this,
        int *a2)
{
  unsigned int v4; // ebx
  int refreshed; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  char i; // al
  HANDLE CurrentThread; // rax
  void *v10; // r8
  enum _TOKEN_INFORMATION_CLASS v11; // r9d
  signed int LastError; // eax
  int TokenInformationImpl; // eax
  void *v14; // r8
  void *v15; // rbx
  int v16; // eax
  const struct std::nothrow_t *v17; // rdx
  unsigned int v18; // r12d
  void *v19; // rcx
  int v20; // eax
  __int64 v22; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v23[24]; // [rsp+28h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+38h] BYREF
  void *v25; // [rsp+80h] [rbp+40h] BYREF
  void *v26; // [rsp+88h] [rbp+48h] BYREF

  if ( a2 )
  {
    v22 = 0;
    refreshed = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&v22);
    v4 = refreshed;
    if ( refreshed >= 0 )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
        v23,
        (char *)this + 56);
      for ( i = 1; ; i = 0 )
      {
        v23[16] = i;
        if ( !i )
          break;
        if ( !*((_QWORD *)this + 16) )
        {
          TokenHandle = 0;
          CurrentThread = GetCurrentThread();
          if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            if ( (v4 & 0x80000000) != 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, v4);
              goto LABEL_30;
            }
          }
          v26 = 0;
          TokenInformationImpl = CommonUtil::UtilGetTokenInformationImpl(
                                   (CommonUtil *)&v26,
                                   (void **)TokenHandle,
                                   v10,
                                   v11);
          v4 = TokenInformationImpl;
          if ( TokenInformationImpl < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                38,
                WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
                (unsigned int)TokenInformationImpl);
            if ( v26 )
              operator delete(v26, (const struct std::nothrow_t *)0x10);
LABEL_30:
            if ( TokenHandle )
              CloseHandle(TokenHandle);
            CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v23);
            goto LABEL_55;
          }
          v15 = v26;
          v25 = 0;
          v16 = CommonUtil::UtilConvertSidToStringSid((CommonUtil *)&v25, *(PSID *)v26, v14);
          v18 = v16;
          if ( v16 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                39,
                WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
                (unsigned int)v16);
            if ( v25 )
              operator delete(v25, v17);
            operator delete(v15, (const struct std::nothrow_t *)0x10);
            if ( TokenHandle )
              CloseHandle(TokenHandle);
            CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v23);
            v4 = v18;
            goto LABEL_55;
          }
          v19 = (void *)*((_QWORD *)this + 16);
          if ( v19 )
            operator delete(v19, v17);
          *((_QWORD *)this + 16) = v25;
          v20 = ShieldProvider::DataProtectionShield::CheckIsOneDriveInstalled(
                  (ShieldProvider::DataProtectionShield *)v19,
                  (bool *)this + 161);
          if ( v20 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              40,
              WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
              (unsigned int)v20);
          operator delete(v15, (const struct std::nothrow_t *)0x10);
          if ( TokenHandle )
            CloseHandle(TokenHandle);
        }
      }
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v23);
      refreshed = ShieldProvider::DataProtectionShield::PopulateCloudBackupProviders((const wchar_t **)this);
      v4 = refreshed;
      if ( refreshed >= 0 )
      {
        refreshed = ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(
                      (struct Shield_CloudBackupProviderInfo **)this,
                      a2);
        v4 = refreshed;
        if ( refreshed < 0 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v7 = 42;
            goto LABEL_54;
          }
        }
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 41;
          goto LABEL_54;
        }
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 36;
LABEL_54:
        WPP_SF_d(v6[2], v7, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, (unsigned int)refreshed);
      }
    }
LABEL_55:
    CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v22);
  }
  else
  {
    v4 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, 2147942487LL);
  }
  return v4;
}

```

## disassembly

```asm
0x180079a00  mov     [rsp-28h+arg_0], rbx
0x180079a05  push    rbp
0x180079a06  push    rsi
0x180079a07  push    r12
0x180079a09  push    r13
0x180079a0b  push    r15
0x180079a0d  mov     rbp, rsp
0x180079a10  sub     rsp, 40h
0x180079a14  xor     r12d, r12d
0x180079a17  mov     r13, rdx
0x180079a1a  mov     r15, rcx
0x180079a1d  test    rdx, rdx
0x180079a20  jnz     short loc_180079A64
0x180079a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180079a29  lea     rsi, WPP_GLOBAL_Control
0x180079a30  mov     ebx, 80070057h
0x180079a35  cmp     rcx, rsi
0x180079a38  jz      loc_180079D2C
0x180079a3e  test    byte ptr [rcx+1Ch], 1
0x180079a42  jz      loc_180079D2C
0x180079a48  mov     rcx, [rcx+10h]
0x180079a4c  lea     edx, [r13+23h]
0x180079a50  mov     r9d, ebx
0x180079a53  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180079a5a  call    WPP_SF_d
0x180079a5f  jmp     loc_180079D2C
0x180079a64  lea     rcx, [rbp+var_20]
0x180079a68  mov     [rbp+var_20], r12
0x180079a6c  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x180079a71  mov     ebx, eax
0x180079a73  test    eax, eax
0x180079a75  jns     short loc_180079AA2
0x180079a77  mov     rcx, cs:WPP_GLOBAL_Control
0x180079a7e  lea     rsi, WPP_GLOBAL_Control
0x180079a85  cmp     rcx, rsi
0x180079a88  jz      loc_180079D23
0x180079a8e  test    byte ptr [rcx+1Ch], 1
0x180079a92  jz      loc_180079D23
0x180079a98  mov     edx, 24h ; '$'
0x180079a9d  jmp     loc_180079D10
0x180079aa2  lea     rdx, [r15+38h]
0x180079aa6  lea     rcx, [rbp+var_18]
0x180079aaa  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180079aaf  mov     al, 1
0x180079ab1  lea     rsi, WPP_GLOBAL_Control
0x180079ab8  mov     [rbp+var_8], al
0x180079abb  test    al, al
0x180079abd  jz      loc_180079CB8
0x180079ac3  cmp     [r15+80h], r12
0x180079aca  jnz     loc_180079BBE
0x180079ad0  mov     [rbp+TokenHandle], r12
0x180079ad4  call    cs:__imp_GetCurrentThread
0x180079ada  xor     r8d, r8d; OpenAsSelf
0x180079add  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180079ae1  mov     rcx, rax; ThreadHandle
0x180079ae4  lea     edx, [r8+8]; DesiredAccess
0x180079ae8  call    cs:__imp_OpenThreadToken
0x180079aee  test    eax, eax
0x180079af0  jnz     short loc_180079B0F
0x180079af2  call    cs:__imp_GetLastError
0x180079af8  mov     ebx, eax
0x180079afa  test    eax, eax
0x180079afc  jle     short loc_180079B07
0x180079afe  movzx   ebx, ax
0x180079b01  or      ebx, 80070000h
0x180079b07  test    ebx, ebx
0x180079b09  js      loc_180079BC6
0x180079b0f  mov     rdx, [rbp+TokenHandle]; void **
0x180079b13  lea     rcx, [rbp+arg_18]; this
0x180079b17  mov     [rbp+arg_18], r12
0x180079b1b  call    ?UtilGetTokenInformationImpl@CommonUtil@@YAJPEAPEAXPEAXW4_TOKEN_INFORMATION_CLASS@@@Z; CommonUtil::UtilGetTokenInformationImpl(void * *,void *,_TOKEN_INFORMATION_CLASS)
0x180079b20  mov     ebx, eax
0x180079b22  test    eax, eax
0x180079b24  js      loc_180079C72
0x180079b2a  mov     rbx, [rbp+arg_18]
0x180079b2e  lea     rcx, [rbp+arg_10]; this
0x180079b32  mov     [rbp+arg_10], r12
0x180079b36  mov     rdx, [rbx]; Sid
0x180079b39  call    ?UtilConvertSidToStringSid@CommonUtil@@YAJPEAPEAGPEAX@Z; CommonUtil::UtilConvertSidToStringSid(ushort * *,void *)
0x180079b3e  mov     r12d, eax
0x180079b41  test    eax, eax
0x180079b43  js      loc_180079C0D
0x180079b49  mov     rcx, [r15+80h]; void *
0x180079b50  xor     r12d, r12d
0x180079b53  test    rcx, rcx
0x180079b56  jz      short loc_180079B5D
0x180079b58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180079b5d  mov     rax, [rbp+arg_10]
0x180079b61  lea     rdx, [r15+0A1h]; bool *
0x180079b68  mov     [r15+80h], rax
0x180079b6f  call    ?CheckIsOneDriveInstalled@DataProtectionShield@ShieldProvider@@AEAAJPEA_N@Z; ShieldProvider::DataProtectionShield::CheckIsOneDriveInstalled(bool *)
0x180079b74  test    eax, eax
0x180079b76  jns     short loc_180079BA2
0x180079b78  mov     rcx, cs:WPP_GLOBAL_Control
0x180079b7f  cmp     rcx, rsi
0x180079b82  jz      short loc_180079BA2
0x180079b84  test    byte ptr [rcx+1Ch], 1
0x180079b88  jz      short loc_180079BA2
0x180079b8a  mov     rcx, [rcx+10h]
0x180079b8e  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180079b95  mov     edx, 28h ; '('
0x180079b9a  mov     r9d, eax
0x180079b9d  call    WPP_SF_d
0x180079ba2  mov     edx, 10h; struct std::nothrow_t *
0x180079ba7  mov     rcx, rbx; void *
0x180079baa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180079baf  mov     rcx, [rbp+TokenHandle]; hObject
0x180079bb3  test    rcx, rcx
0x180079bb6  jz      short loc_180079BBE
0x180079bb8  call    cs:__imp_CloseHandle
0x180079bbe  mov     al, r12b
0x180079bc1  jmp     loc_180079AB8
0x180079bc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180079bcd  cmp     rcx, rsi
0x180079bd0  jz      short loc_180079BF0
0x180079bd2  test    byte ptr [rcx+1Ch], 1
0x180079bd6  jz      short loc_180079BF0
0x180079bd8  mov     rcx, [rcx+10h]
0x180079bdc  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180079be3  mov     edx, 25h ; '%'
0x180079be8  mov     r9d, ebx
0x180079beb  call    WPP_SF_d
0x180079bf0  mov     rcx, [rbp+TokenHandle]; hObject
0x180079bf4  test    rcx, rcx
0x180079bf7  jz      short loc_180079BFF
0x180079bf9  call    cs:__imp_CloseHandle
0x180079bff  lea     rcx, [rbp+var_18]
0x180079c03  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180079c08  jmp     loc_180079D23
0x180079c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180079c14  cmp     rcx, rsi
0x180079c17  jz      short loc_180079C37
0x180079c19  test    byte ptr [rcx+1Ch], 1
0x180079c1d  jz      short loc_180079C37
0x180079c1f  mov     rcx, [rcx+10h]
0x180079c23  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180079c2a  mov     edx, 27h ; '''
0x180079c2f  mov     r9d, r12d
0x180079c32  call    WPP_SF_d
0x180079c37  mov     rcx, [rbp+arg_10]; void *
0x180079c3b  test    rcx, rcx
0x180079c3e  jz      short loc_180079C45
0x180079c40  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180079c45  mov     edx, 10h; struct std::nothrow_t *
0x180079c4a  mov     rcx, rbx; void *
0x180079c4d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180079c52  mov     rcx, [rbp+TokenHandle]; hObject
0x180079c56  test    rcx, rcx
0x180079c59  jz      short loc_180079C61
0x180079c5b  call    cs:__imp_CloseHandle
0x180079c61  lea     rcx, [rbp+var_18]
0x180079c65  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180079c6a  mov     ebx, r12d
0x180079c6d  jmp     loc_180079D23
0x180079c72  mov     rcx, cs:WPP_GLOBAL_Control
0x180079c79  cmp     rcx, rsi
0x180079c7c  jz      short loc_180079C9C
0x180079c7e  test    byte ptr [rcx+1Ch], 1
0x180079c82  jz      short loc_180079C9C
0x180079c84  mov     rcx, [rcx+10h]
0x180079c88  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180079c8f  mov     edx, 26h ; '&'
0x180079c94  mov     r9d, eax
0x180079c97  call    WPP_SF_d
0x180079c9c  mov     rcx, [rbp+arg_18]; void *
0x180079ca0  test    rcx, rcx
0x180079ca3  jz      loc_180079BF0
0x180079ca9  mov     edx, 10h; struct std::nothrow_t *
0x180079cae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180079cb3  jmp     loc_180079BF0
0x180079cb8  lea     rcx, [rbp+var_18]
0x180079cbc  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180079cc1  mov     rcx, r15; this
0x180079cc4  call    ?PopulateCloudBackupProviders@DataProtectionShield@ShieldProvider@@AEAAJXZ; ShieldProvider::DataProtectionShield::PopulateCloudBackupProviders(void)
0x180079cc9  mov     ebx, eax
0x180079ccb  test    eax, eax
0x180079ccd  jns     short loc_180079CE8
0x180079ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180079cd6  cmp     rcx, rsi
0x180079cd9  jz      short loc_180079D23
0x180079cdb  test    byte ptr [rcx+1Ch], 1
0x180079cdf  jz      short loc_180079D23
0x180079ce1  mov     edx, 29h ; ')'
0x180079ce6  jmp     short loc_180079D10
0x180079ce8  mov     rdx, r13; int *
0x180079ceb  mov     rcx, r15; this
0x180079cee  call    ?RefreshPillarStatusForUser@DataProtectionShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(int *)
0x180079cf3  mov     ebx, eax
0x180079cf5  test    eax, eax
0x180079cf7  jns     short loc_180079D23
0x180079cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180079d00  cmp     rcx, rsi
0x180079d03  jz      short loc_180079D23
0x180079d05  test    byte ptr [rcx+1Ch], 1
0x180079d09  jz      short loc_180079D23
0x180079d0b  mov     edx, 2Ah ; '*'
0x180079d10  mov     rcx, [rcx+10h]
0x180079d14  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180079d1b  mov     r9d, eax
0x180079d1e  call    WPP_SF_d
0x180079d23  lea     rcx, [rbp+var_20]
0x180079d27  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x180079d2c  mov     eax, ebx
0x180079d2e  mov     rbx, [rsp+40h+arg_0]
0x180079d33  add     rsp, 40h
0x180079d37  pop     r15
0x180079d39  pop     r13
0x180079d3b  pop     r12
0x180079d3d  pop     rsi
0x180079d3e  pop     rbp
0x180079d3f  retn
```
