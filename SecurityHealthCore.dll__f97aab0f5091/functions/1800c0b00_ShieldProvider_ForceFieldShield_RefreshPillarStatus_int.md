# ShieldProvider::ForceFieldShield::RefreshPillarStatus(int *)

- ea: `0x1800c0b00`
- end: `0x1800c0e28`
- name: `?RefreshPillarStatus@ForceFieldShield@ShieldProvider@@UEAAJPEAH@Z`
- size: `808`
- prototype: `__int64 __fastcall(ShieldProvider::ForceFieldShield *__hidden this, int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180004ae0`
- `0x18000ccd4`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x180011730`
- `0x1800c07bc`
- `0x1800c0b00`
- `0x1800c0e30`
- `0x1800df1b0`
- `0x1800df668`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800c0bf7`
- `KERNEL32!GetLastError` at `0x1800c0bf7`
- `KERNEL32!CloseHandle` at `0x1800c0c82`
- `KERNEL32!CloseHandle` at `0x1800c0cc9`
- `KERNEL32!CloseHandle` at `0x1800c0d30`
- `KERNEL32!CloseHandle` at `0x1800c0c82`
- `KERNEL32!CloseHandle` at `0x1800c0cc9`
- `KERNEL32!CloseHandle` at `0x1800c0d30`
- `KERNEL32!GetCurrentThread` at `0x1800c0bd9`
- `KERNEL32!GetCurrentThread` at `0x1800c0bd9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c0bed`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c0bed`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::RefreshPillarStatus(
        ShieldProvider::ForceFieldShield *this,
        int *a2)
{
  int TokenInformationImpl; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  char i; // al
  HANDLE CurrentThread; // rax
  void *v9; // r8
  enum _TOKEN_INFORMATION_CLASS v10; // r9d
  signed int LastError; // eax
  void *v12; // r8
  void *v13; // rbx
  const struct std::nothrow_t *v14; // rdx
  int v15; // r14d
  void *v16; // rcx
  __int64 v18; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v19[24]; // [rsp+28h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+38h] BYREF
  void *v21; // [rsp+80h] [rbp+40h] BYREF
  void *v22; // [rsp+88h] [rbp+48h] BYREF

  if ( a2 )
  {
    v18 = 0;
    TokenInformationImpl = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&v18);
    if ( TokenInformationImpl >= 0 )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
        v19,
        (char *)this + 56);
      for ( i = 1; ; i = 0 )
      {
        v19[16] = i;
        if ( !i )
          break;
        if ( !*((_QWORD *)this + 16) )
        {
          TokenHandle = 0;
          CurrentThread = GetCurrentThread();
          if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
          {
            LastError = GetLastError();
            TokenInformationImpl = LastError;
            if ( LastError > 0 )
              TokenInformationImpl = (unsigned __int16)LastError | 0x80070000;
            if ( TokenInformationImpl < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  36,
                  WPP_3533d4a562073f930570ad4a944aa956_Traceguids,
                  (unsigned int)TokenInformationImpl);
              goto LABEL_26;
            }
          }
          v22 = 0;
          TokenInformationImpl = CommonUtil::UtilGetTokenInformationImpl(
                                   (CommonUtil *)&v22,
                                   (void **)TokenHandle,
                                   v9,
                                   v10);
          if ( TokenInformationImpl < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                37,
                WPP_3533d4a562073f930570ad4a944aa956_Traceguids,
                (unsigned int)TokenInformationImpl);
            if ( v22 )
              operator delete(v22, (const struct std::nothrow_t *)0x10);
LABEL_26:
            if ( TokenHandle )
              CloseHandle(TokenHandle);
            CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v19);
            goto LABEL_51;
          }
          v13 = v22;
          v21 = 0;
          v15 = CommonUtil::UtilConvertSidToStringSid((CommonUtil *)&v21, *(PSID *)v22, v12);
          if ( v15 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                38,
                WPP_3533d4a562073f930570ad4a944aa956_Traceguids,
                (unsigned int)v15);
            if ( v21 )
              operator delete(v21, v14);
            operator delete(v13, (const struct std::nothrow_t *)0x10);
            if ( TokenHandle )
              CloseHandle(TokenHandle);
            CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v19);
            TokenInformationImpl = v15;
            goto LABEL_51;
          }
          v16 = (void *)*((_QWORD *)this + 16);
          if ( v16 )
            operator delete(v16, v14);
          *((_QWORD *)this + 16) = v21;
          operator delete(v13, (const struct std::nothrow_t *)0x10);
          if ( TokenHandle )
            CloseHandle(TokenHandle);
        }
      }
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v19);
      TokenInformationImpl = ShieldProvider::ForceFieldShield::PopulateForceFieldProviders((const wchar_t **)this);
      if ( TokenInformationImpl >= 0 )
      {
        TokenInformationImpl = ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(
                                 (struct Shield_ForceFieldProviderInfo **)this,
                                 a2);
        if ( TokenInformationImpl < 0 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 40;
            goto LABEL_50;
          }
        }
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 39;
          goto LABEL_50;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 35;
LABEL_50:
        WPP_SF_d(v5[2], v6, WPP_3533d4a562073f930570ad4a944aa956_Traceguids, (unsigned int)TokenInformationImpl);
      }
    }
LABEL_51:
    CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v18);
  }
  else
  {
    TokenInformationImpl = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_3533d4a562073f930570ad4a944aa956_Traceguids, 2147942487LL);
  }
  return (unsigned int)TokenInformationImpl;
}

```

## disassembly

```asm
0x1800c0b00  mov     [rsp-28h+arg_0], rbx
0x1800c0b05  push    rbp
0x1800c0b06  push    rsi
0x1800c0b07  push    r13
0x1800c0b09  push    r14
0x1800c0b0b  push    r15
0x1800c0b0d  mov     rbp, rsp
0x1800c0b10  sub     rsp, 40h
0x1800c0b14  mov     r15, rdx
0x1800c0b17  mov     rsi, rcx
0x1800c0b1a  test    rdx, rdx
0x1800c0b1d  jnz     short loc_1800C0B61
0x1800c0b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0b26  lea     rax, WPP_GLOBAL_Control
0x1800c0b2d  mov     ebx, 80070057h
0x1800c0b32  cmp     rcx, rax
0x1800c0b35  jz      loc_1800C0E14
0x1800c0b3b  test    byte ptr [rcx+1Ch], 1
0x1800c0b3f  jz      loc_1800C0E14
0x1800c0b45  mov     rcx, [rcx+10h]
0x1800c0b49  lea     edx, [r15+22h]
0x1800c0b4d  mov     r9d, ebx
0x1800c0b50  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c0b57  call    WPP_SF_d
0x1800c0b5c  jmp     loc_1800C0E14
0x1800c0b61  lea     rcx, [rbp+var_20]
0x1800c0b65  mov     [rbp+var_20], 0
0x1800c0b6d  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x1800c0b72  mov     ebx, eax
0x1800c0b74  test    eax, eax
0x1800c0b76  jns     short loc_1800C0BA3
0x1800c0b78  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0b7f  lea     rax, WPP_GLOBAL_Control
0x1800c0b86  cmp     rcx, rax
0x1800c0b89  jz      loc_1800C0E0B
0x1800c0b8f  test    byte ptr [rcx+1Ch], 1
0x1800c0b93  jz      loc_1800C0E0B
0x1800c0b99  mov     edx, 23h ; '#'
0x1800c0b9e  jmp     loc_1800C0DF8
0x1800c0ba3  lea     rdx, [rsi+38h]
0x1800c0ba7  lea     rcx, [rbp+var_18]
0x1800c0bab  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800c0bb0  mov     al, 1
0x1800c0bb2  mov     r13d, 10h
0x1800c0bb8  mov     [rbp+var_8], al
0x1800c0bbb  test    al, al
0x1800c0bbd  jz      loc_1800C0D92
0x1800c0bc3  cmp     qword ptr [rsi+80h], 0
0x1800c0bcb  jnz     loc_1800C0C88
0x1800c0bd1  mov     [rbp+TokenHandle], 0
0x1800c0bd9  call    cs:__imp_GetCurrentThread
0x1800c0bdf  xor     r8d, r8d; OpenAsSelf
0x1800c0be2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800c0be6  mov     rcx, rax; ThreadHandle
0x1800c0be9  lea     edx, [r8+8]; DesiredAccess
0x1800c0bed  call    cs:__imp_OpenThreadToken
0x1800c0bf3  test    eax, eax
0x1800c0bf5  jnz     short loc_1800C0C10
0x1800c0bf7  call    cs:__imp_GetLastError
0x1800c0bfd  mov     ebx, eax
0x1800c0bff  test    eax, eax
0x1800c0c01  jle     short loc_1800C0C0C
0x1800c0c03  movzx   ebx, ax
0x1800c0c06  or      ebx, 80070000h
0x1800c0c0c  test    ebx, ebx
0x1800c0c0e  js      short loc_1800C0C8F
0x1800c0c10  mov     rdx, [rbp+TokenHandle]; void **
0x1800c0c14  lea     rcx, [rbp+arg_18]; this
0x1800c0c18  mov     [rbp+arg_18], 0
0x1800c0c20  call    ?UtilGetTokenInformationImpl@CommonUtil@@YAJPEAPEAXPEAXW4_TOKEN_INFORMATION_CLASS@@@Z; CommonUtil::UtilGetTokenInformationImpl(void * *,void *,_TOKEN_INFORMATION_CLASS)
0x1800c0c25  mov     ebx, eax
0x1800c0c27  test    eax, eax
0x1800c0c29  js      loc_1800C0D47
0x1800c0c2f  mov     rbx, [rbp+arg_18]
0x1800c0c33  lea     rcx, [rbp+arg_10]; this
0x1800c0c37  mov     [rbp+arg_10], 0
0x1800c0c3f  mov     rdx, [rbx]; Sid
0x1800c0c42  call    ?UtilConvertSidToStringSid@CommonUtil@@YAJPEAPEAGPEAX@Z; CommonUtil::UtilConvertSidToStringSid(ushort * *,void *)
0x1800c0c47  mov     r14d, eax
0x1800c0c4a  test    eax, eax
0x1800c0c4c  js      loc_1800C0CDD
0x1800c0c52  mov     rcx, [rsi+80h]; void *
0x1800c0c59  test    rcx, rcx
0x1800c0c5c  jz      short loc_1800C0C63
0x1800c0c5e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c0c63  mov     rax, [rbp+arg_10]
0x1800c0c67  mov     rdx, r13; struct std::nothrow_t *
0x1800c0c6a  mov     rcx, rbx; void *
0x1800c0c6d  mov     [rsi+80h], rax
0x1800c0c74  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c0c79  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c0c7d  test    rcx, rcx
0x1800c0c80  jz      short loc_1800C0C88
0x1800c0c82  call    cs:__imp_CloseHandle
0x1800c0c88  xor     al, al
0x1800c0c8a  jmp     loc_1800C0BB8
0x1800c0c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0c96  lea     rax, WPP_GLOBAL_Control
0x1800c0c9d  cmp     rcx, rax
0x1800c0ca0  jz      short loc_1800C0CC0
0x1800c0ca2  test    byte ptr [rcx+1Ch], 1
0x1800c0ca6  jz      short loc_1800C0CC0
0x1800c0ca8  mov     rcx, [rcx+10h]
0x1800c0cac  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c0cb3  mov     edx, 24h ; '$'
0x1800c0cb8  mov     r9d, ebx
0x1800c0cbb  call    WPP_SF_d
0x1800c0cc0  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c0cc4  test    rcx, rcx
0x1800c0cc7  jz      short loc_1800C0CCF
0x1800c0cc9  call    cs:__imp_CloseHandle
0x1800c0ccf  lea     rcx, [rbp+var_18]
0x1800c0cd3  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800c0cd8  jmp     loc_1800C0E0B
0x1800c0cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0ce4  lea     rax, WPP_GLOBAL_Control
0x1800c0ceb  cmp     rcx, rax
0x1800c0cee  jz      short loc_1800C0D0E
0x1800c0cf0  test    byte ptr [rcx+1Ch], 1
0x1800c0cf4  jz      short loc_1800C0D0E
0x1800c0cf6  mov     rcx, [rcx+10h]
0x1800c0cfa  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c0d01  mov     edx, 26h ; '&'
0x1800c0d06  mov     r9d, r14d
0x1800c0d09  call    WPP_SF_d
0x1800c0d0e  mov     rcx, [rbp+arg_10]; void *
0x1800c0d12  test    rcx, rcx
0x1800c0d15  jz      short loc_1800C0D1C
0x1800c0d17  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c0d1c  mov     rdx, r13; struct std::nothrow_t *
0x1800c0d1f  mov     rcx, rbx; void *
0x1800c0d22  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c0d27  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c0d2b  test    rcx, rcx
0x1800c0d2e  jz      short loc_1800C0D36
0x1800c0d30  call    cs:__imp_CloseHandle
0x1800c0d36  lea     rcx, [rbp+var_18]
0x1800c0d3a  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800c0d3f  mov     ebx, r14d
0x1800c0d42  jmp     loc_1800C0E0B
0x1800c0d47  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0d4e  lea     rax, WPP_GLOBAL_Control
0x1800c0d55  cmp     rcx, rax
0x1800c0d58  jz      short loc_1800C0D78
0x1800c0d5a  test    byte ptr [rcx+1Ch], 1
0x1800c0d5e  jz      short loc_1800C0D78
0x1800c0d60  mov     rcx, [rcx+10h]
0x1800c0d64  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c0d6b  mov     edx, 25h ; '%'
0x1800c0d70  mov     r9d, ebx
0x1800c0d73  call    WPP_SF_d
0x1800c0d78  mov     rcx, [rbp+arg_18]; void *
0x1800c0d7c  test    rcx, rcx
0x1800c0d7f  jz      loc_1800C0CC0
0x1800c0d85  mov     rdx, r13; struct std::nothrow_t *
0x1800c0d88  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c0d8d  jmp     loc_1800C0CC0
0x1800c0d92  lea     rcx, [rbp+var_18]
0x1800c0d96  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800c0d9b  mov     rcx, rsi; this
0x1800c0d9e  call    ?PopulateForceFieldProviders@ForceFieldShield@ShieldProvider@@AEAAJXZ; ShieldProvider::ForceFieldShield::PopulateForceFieldProviders(void)
0x1800c0da3  mov     ebx, eax
0x1800c0da5  test    eax, eax
0x1800c0da7  jns     short loc_1800C0DC9
0x1800c0da9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0db0  lea     rax, WPP_GLOBAL_Control
0x1800c0db7  cmp     rcx, rax
0x1800c0dba  jz      short loc_1800C0E0B
0x1800c0dbc  test    byte ptr [rcx+1Ch], 1
0x1800c0dc0  jz      short loc_1800C0E0B
0x1800c0dc2  mov     edx, 27h ; '''
0x1800c0dc7  jmp     short loc_1800C0DF8
0x1800c0dc9  mov     rdx, r15; int *
0x1800c0dcc  mov     rcx, rsi; this
0x1800c0dcf  call    ?RefreshPillarStatusForUser@ForceFieldShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(int *)
0x1800c0dd4  mov     ebx, eax
0x1800c0dd6  test    eax, eax
0x1800c0dd8  jns     short loc_1800C0E0B
0x1800c0dda  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0de1  lea     rax, WPP_GLOBAL_Control
0x1800c0de8  cmp     rcx, rax
0x1800c0deb  jz      short loc_1800C0E0B
0x1800c0ded  test    byte ptr [rcx+1Ch], 1
0x1800c0df1  jz      short loc_1800C0E0B
0x1800c0df3  mov     edx, 28h ; '('
0x1800c0df8  mov     rcx, [rcx+10h]
0x1800c0dfc  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c0e03  mov     r9d, ebx
0x1800c0e06  call    WPP_SF_d
0x1800c0e0b  lea     rcx, [rbp+var_20]
0x1800c0e0f  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800c0e14  mov     eax, ebx
0x1800c0e16  mov     rbx, [rsp+40h+arg_0]
0x1800c0e1b  add     rsp, 40h
0x1800c0e1f  pop     r15
0x1800c0e21  pop     r14
0x1800c0e23  pop     r13
0x1800c0e25  pop     rsi
0x1800c0e26  pop     rbp
0x1800c0e27  retn
```
