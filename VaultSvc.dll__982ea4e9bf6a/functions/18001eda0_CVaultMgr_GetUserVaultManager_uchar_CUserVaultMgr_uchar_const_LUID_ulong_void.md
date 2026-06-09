# CVaultMgr::GetUserVaultManager(uchar,CUserVaultMgr * *,uchar * const,_LUID *,ulong *,void * *)

- ea: `0x18001eda0`
- end: `0x18001f661`
- name: `?GetUserVaultManager@CVaultMgr@@QEAAKEPEAPEAVCUserVaultMgr@@QEAEPEAU_LUID@@PEAKPEAPEAX@Z`
- size: `2241`
- prototype: `__int64 __fastcall(CVaultMgr *this, unsigned __int8, struct CUserVaultMgr **, unsigned __int8 *const, struct _LUID *)`
- caller_count: `10`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001dbe0`
- `0x18001e4f0`
- `0x180022290`
- `0x180026a80`
- `0x18002ba80`
- `0x18002d090`
- `0x180046040`
- `0x180046920`
- `0x180046d90`
- `0x180047890`

## callees

- `0x180003140`
- `0x18000cd28`
- `0x18000eb30`
- `0x180011110`
- `0x180013390`
- `0x180015568`
- `0x18001d460`
- `0x18001eda0`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18003be38`
- `0x18003d720`
- `0x18004b43c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ef75`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001efc6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ef75`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001efc6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ef83`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ef83`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001f0af`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001f0af`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001f097`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001f097`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001eeaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001eeaf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001eec8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001eec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f47a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f529`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eddb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f47a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f529`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f301`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f301`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f5d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f5d0`
- `RPCRT4!RpcRevertToSelf` at `0x18001f4c2`
- `RPCRT4!RpcRevertToSelf` at `0x18001f4c2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18001f5ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18001f5ae`
- `ntdll!RtlEqualSid` at `0x18001f0e9`
- `ntdll!RtlEqualSid` at `0x18001f0e9`
- `ntdll!RtlValidSid` at `0x18001f085`
- `ntdll!RtlValidSid` at `0x18001f085`
- `ntdll!RtlConvertSharedToExclusive` at `0x18001f2d6`
- `ntdll!RtlConvertSharedToExclusive` at `0x18001f2d6`
- `ntdll!NtSetInformationThread` at `0x18001f441`
- `ntdll!NtSetInformationThread` at `0x18001f4f0`
- `ntdll!NtSetInformationThread` at `0x18001f441`
- `ntdll!NtSetInformationThread` at `0x18001f4f0`
- `ntdll!RtlReleaseResource` at `0x18001f107`
- `ntdll!RtlReleaseResource` at `0x18001f1c3`
- `ntdll!RtlReleaseResource` at `0x18001f313`
- `ntdll!RtlReleaseResource` at `0x18001f39c`
- `ntdll!RtlReleaseResource` at `0x18001f107`
- `ntdll!RtlReleaseResource` at `0x18001f1c3`
- `ntdll!RtlReleaseResource` at `0x18001f313`
- `ntdll!RtlReleaseResource` at `0x18001f39c`
- `ntdll!RtlAcquireResourceShared` at `0x18001f07b`
- `ntdll!RtlAcquireResourceShared` at `0x18001f2aa`
- `ntdll!RtlAcquireResourceShared` at `0x18001f07b`
- `ntdll!RtlAcquireResourceShared` at `0x18001f2aa`

## pseudocode

```c
__int64 __fastcall CVaultMgr::GetUserVaultManager(
        CVaultMgr *this,
        unsigned __int8 a2,
        struct CUserVaultMgr **a3,
        unsigned __int8 *const a4,
        struct _LUID *a5)
{
  struct _LUID v8; // rbx
  unsigned int v9; // esi
  ULONG v11; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v14; // ebx
  void *v15; // rsi
  DWORD LengthSid; // eax
  __int64 v17; // r8
  int v18; // ecx
  __int64 v19; // rsi
  unsigned int HighPart; // r12d
  CVaultMgr *v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // r8
  struct CUserVaultMgr *v24; // rsi
  __int64 v25; // r8
  _QWORD *v26; // rax
  _QWORD *v27; // rax
  _QWORD *v28; // rax
  __int64 v29; // r8
  __int64 v30; // r8
  NTSTATUS v31; // eax
  NTSTATUS v32; // eax
  _BYTE *v33; // rbx
  __int64 v34; // rax
  SIZE_T v35; // rax
  _BYTE *v36; // rcx
  HANDLE ThreadInformation; // [rsp+30h] [rbp-D0h] BYREF
  struct _LUID v38; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v39[8]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  BOOL (__stdcall *v41)(HANDLE); // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v43; // [rsp+60h] [rbp-A0h]
  DWORD ReturnLength; // [rsp+68h] [rbp-98h] BYREF
  DWORD v45; // [rsp+6Ch] [rbp-94h] BYREF
  _OWORD v46[3]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-60h]
  _OWORD Sid[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v49; // [rsp+F0h] [rbp-10h]
  void *TokenInformation; // [rsp+100h] [rbp+0h] BYREF

  v41 = CloseHandle;
  TokenHandle = 0;
  v43 = 0;
  v39[0] = 0;
  hObject = 0;
  ThreadInformation = 0;
  v8 = 0;
  v38 = 0;
  v9 = CVaultRpcImpersonate::Impersonate((CVaultRpcImpersonate *)v39, 0);
  if ( v9 )
  {
LABEL_2:
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultRpcImpersonate::~CVaultRpcImpersonate((CVaultRpcImpersonate *)v39);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v41);
    return v9;
  }
  v11 = CVaultIntegrityLevel::Elevate((CVaultIntegrityLevel *)&ThreadInformation);
  v9 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, v11);
    goto LABEL_2;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, LastError);
LABEL_12:
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultRpcImpersonate::~CVaultRpcImpersonate((CVaultRpcImpersonate *)v39);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v41);
    return v14;
  }
  v15 = TokenHandle;
  ReturnLength = 0;
  memset(v46, 0, sizeof(v46));
  v47 = 0;
  v45 = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x54u, &ReturnLength) )
    goto LABEL_17;
  LengthSid = GetLengthSid(TokenInformation);
  ReturnLength = LengthSid;
  if ( LengthSid > 0x44 )
  {
    v9 = 122;
LABEL_18:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, v9);
    goto LABEL_2;
  }
  memcpy_0(Sid, TokenInformation, LengthSid);
  if ( GetTokenInformation(v15, TokenStatistics, v46, 0x38u, &v45) )
  {
    v8 = (struct _LUID)*((_QWORD *)&v46[0] + 1);
    v38 = (struct _LUID)*((_QWORD *)&v46[0] + 1);
  }
  else
  {
LABEL_17:
    v9 = GetLastError();
    if ( v9 )
      goto LABEL_18;
  }
  if ( a5 )
    *a5 = v8;
  if ( a4 )
  {
    *(_OWORD *)a4 = Sid[0];
    *((_OWORD *)a4 + 1) = Sid[1];
    *((_OWORD *)a4 + 2) = Sid[2];
    *((_OWORD *)a4 + 3) = Sid[3];
    *((_DWORD *)a4 + 16) = v49;
  }
  RtlAcquireResourceShared(&Resource, 1u);
  if ( RtlValidSid(Sid) && (v18 = *GetSidSubAuthorityCount(Sid), (_BYTE)v18) )
  {
    v19 = VaultGlobals::g_VaultMgr[*GetSidSubAuthority(Sid, v18 - 1) % 0xB];
    HighPart = v38.HighPart;
    if ( v19 )
    {
      while ( !RtlEqualSid(Sid, *(PSID *)v19) )
      {
        v19 = *(_QWORD *)(v19 + 16);
        if ( !v19 )
          goto LABEL_32;
      }
      (***(void (__fastcall ****)(_QWORD))(v19 + 8))(*(_QWORD *)(v19 + 8));
      *a3 = *(struct CUserVaultMgr **)(v19 + 8);
      RtlReleaseResource(&Resource);
    }
    else
    {
LABEL_32:
      RtlReleaseResource(&Resource);
      v21 = (CVaultMgr *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          75,
          &WPP_f1575cf6446936089985711df8c7b212_Traceguids,
          HighPart,
          v8.LowPart);
      v22 = CVaultMgr::CreateUserVaultManager(v21, Sid, &v38, a3);
      v9 = v22;
      if ( v22 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_LLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, v23, HighPart, v8.LowPart, v22);
        goto LABEL_2;
      }
    }
    v24 = *a3;
    if ( !*((_BYTE *)*a3 + 68) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          77,
          &WPP_f1575cf6446936089985711df8c7b212_Traceguids,
          HighPart,
          v8.LowPart);
      v14 = CUserVaultMgr::Initialize(*a3, TokenHandle, Sid, &v38, a2);
      if ( v14 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
        *a3 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_LLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, v25, (unsigned int)v38.HighPart, v38.LowPart, v14);
        goto LABEL_12;
      }
      v8.LowPart = v38.LowPart;
      HighPart = v38.HighPart;
      goto LABEL_64;
    }
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)v24 + 72), 1u);
    v26 = (_QWORD *)*((_QWORD *)v24 + 1);
    if ( v26 )
    {
      while ( *v26 != v8 )
      {
        v26 = (_QWORD *)v26[1];
        if ( !v26 )
          goto LABEL_54;
      }
      goto LABEL_63;
    }
LABEL_54:
    RtlConvertSharedToExclusive((PRTL_RESOURCE)((char *)v24 + 72));
    v27 = (_QWORD *)*((_QWORD *)v24 + 1);
    if ( v27 )
    {
      while ( *v27 != v8 )
      {
        v27 = (_QWORD *)v27[1];
        if ( !v27 )
          goto LABEL_57;
      }
      goto LABEL_63;
    }
LABEL_57:
    v28 = LocalAlloc(0x40u, 0x100u);
    if ( v28 )
    {
      *v28 = v8;
      v28[1] = *((_QWORD *)v24 + 1);
      *((_QWORD *)v24 + 1) = v28;
LABEL_63:
      RtlReleaseResource((PRTL_RESOURCE)((char *)v24 + 72));
LABEL_64:
      if ( a2 || *((_BYTE *)*a3 + 69) )
      {
        if ( ThreadInformation )
        {
          v31 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
          if ( v31 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids,
              (unsigned int)v31);
          CloseHandle(ThreadInformation);
          ThreadInformation = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids);
        }
        CVaultIntegrityLevel::~CVaultIntegrityLevel(&hObject);
        if ( v39[0] )
        {
          RpcRevertToSelf();
          v39[0] = 0;
        }
        if ( hObject )
        {
          v32 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &hObject, 8u);
          if ( v32 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids,
              (unsigned int)v32);
          CloseHandle(hObject);
          hObject = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids);
        }
        v33 = TokenHandle;
        if ( TokenHandle )
        {
          v34 = v43;
          if ( v43 )
          {
            do
            {
              *v33++ = 0;
              --v34;
            }
            while ( v34 );
            v33 = TokenHandle;
          }
          if ( v41 )
          {
            ((void (__fastcall *)(_BYTE *))v41)(v33);
          }
          else if ( v33 )
          {
            v35 = LocalSize(v33);
            if ( v35 )
            {
              v36 = v33;
              do
              {
                *v36++ = 0;
                --v35;
              }
              while ( v35 );
            }
            LocalFree(v33);
          }
        }
        return 0;
      }
      else
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
        *a3 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_LLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, v30, HighPart, v8.LowPart, 2016);
        CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
        CVaultRpcImpersonate::~CVaultRpcImpersonate((CVaultRpcImpersonate *)v39);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v41);
        return 2016;
      }
    }
    RtlReleaseResource((PRTL_RESOURCE)((char *)v24 + 72));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_LLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, v29, HighPart, v8.LowPart, 14);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
    *a3 = 0;
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultRpcImpersonate::~CVaultRpcImpersonate((CVaultRpcImpersonate *)v39);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v41);
    return 14;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_LLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, v17, (unsigned int)v38.HighPart, v8.LowPart, 87);
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultRpcImpersonate::~CVaultRpcImpersonate((CVaultRpcImpersonate *)v39);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v41);
    return 87;
  }
}

```

## disassembly

```asm
0x18001eda0  mov     [rsp-8+arg_0], rbx
0x18001eda5  push    rbp
0x18001eda6  push    rsi
0x18001eda7  push    rdi
0x18001eda8  push    r12
0x18001edaa  push    r13
0x18001edac  push    r14
0x18001edae  push    r15
0x18001edb0  lea     rbp, [rsp-70h]
0x18001edb5  sub     rsp, 170h
0x18001edbc  mov     rax, cs:__security_cookie
0x18001edc3  xor     rax, rsp
0x18001edc6  mov     [rbp+0A0h+var_40], rax
0x18001edca  mov     rdi, r9
0x18001edcd  mov     r14, r8
0x18001edd0  movzx   r13d, dl
0x18001edd4  mov     r15, [rbp+0A0h+arg_20]
0x18001eddb  mov     rax, cs:__imp_CloseHandle
0x18001ede2  mov     [rsp+1A0h+var_150], rax
0x18001ede7  xor     r12d, r12d
0x18001edea  mov     [rsp+1A0h+TokenHandle], r12
0x18001edef  mov     [rsp+1A0h+var_140], r12d
0x18001edf4  mov     [rsp+1A0h+var_160], r12b
0x18001edf9  mov     [rsp+1A0h+hObject], r12
0x18001edfe  mov     [rsp+1A0h+ThreadInformation], r12
0x18001ee03  mov     ebx, r12d
0x18001ee06  mov     qword ptr [rsp+1A0h+var_168.LowPart], rbx
0x18001ee0b  xor     edx, edx; int
0x18001ee0d  lea     rcx, [rsp+1A0h+var_160]; this
0x18001ee12  call    ?Impersonate@CVaultRpcImpersonate@@QEAAKH@Z; CVaultRpcImpersonate::Impersonate(int)
0x18001ee17  mov     esi, eax
0x18001ee19  test    eax, eax
0x18001ee1b  jz      short loc_18001EE45
0x18001ee1d  lea     rcx, [rsp+1A0h+ThreadInformation]; ThreadInformation
0x18001ee22  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18001ee27  nop
0x18001ee28  lea     rcx, [rsp+1A0h+var_160]; this
0x18001ee2d  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x18001ee32  nop
0x18001ee33  lea     rcx, [rsp+1A0h+var_150]
0x18001ee38  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001ee3d  nop
0x18001ee3e  mov     eax, esi
0x18001ee40  jmp     loc_18001F63A
0x18001ee45  lea     rcx, [rsp+1A0h+ThreadInformation]; this
0x18001ee4a  call    ?Elevate@CVaultIntegrityLevel@@QEAAKXZ; CVaultIntegrityLevel::Elevate(void)
0x18001ee4f  mov     esi, eax
0x18001ee51  test    eax, eax
0x18001ee53  jz      short loc_18001EEAF
0x18001ee55  lea     rdi, WPP_GLOBAL_Control
0x18001ee5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee63  cmp     rcx, rdi
0x18001ee66  jz      short loc_18001EE87
0x18001ee68  test    byte ptr [rcx+1Ch], 2
0x18001ee6c  jz      short loc_18001EE87
0x18001ee6e  mov     edx, 46h ; 'F'
0x18001ee73  mov     r9d, eax
0x18001ee76  lea     r8, WPP_f1575cf6446936089985711df8c7b212_Traceguids
0x18001ee7d  mov     rcx, [rcx+10h]
0x18001ee81  call    WPP_SF_d
0x18001ee86  nop
0x18001ee87  lea     rcx, [rsp+1A0h+ThreadInformation]; ThreadInformation
0x18001ee8c  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18001ee91  nop
0x18001ee92  lea     rcx, [rsp+1A0h+var_160]; this
0x18001ee97  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x18001ee9c  nop
0x18001ee9d  lea     rcx, [rsp+1A0h+var_150]
0x18001eea2  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001eea7  nop
0x18001eea8  mov     eax, esi
0x18001eeaa  jmp     loc_18001F63A
0x18001eeaf  call    cs:__imp_GetCurrentThread
0x18001eeb5  lea     r9, [rsp+1A0h+TokenHandle]; TokenHandle
0x18001eeba  mov     edx, 0Eh; DesiredAccess
0x18001eebf  mov     r8d, 1; OpenAsSelf
0x18001eec5  mov     rcx, rax; ThreadHandle
0x18001eec8  call    cs:__imp_OpenThreadToken
0x18001eece  test    eax, eax
0x18001eed0  jnz     short loc_18001EF34
0x18001eed2  call    cs:__imp_GetLastError
0x18001eed8  mov     ebx, eax
0x18001eeda  lea     rdi, WPP_GLOBAL_Control
0x18001eee1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eee8  cmp     rcx, rdi
0x18001eeeb  jz      short loc_18001EF0C
0x18001eeed  test    byte ptr [rcx+1Ch], 2
0x18001eef1  jz      short loc_18001EF0C
0x18001eef3  mov     edx, 47h ; 'G'
0x18001eef8  mov     r9d, eax
0x18001eefb  lea     r8, WPP_f1575cf6446936089985711df8c7b212_Traceguids
0x18001ef02  mov     rcx, [rcx+10h]
0x18001ef06  call    WPP_SF_d
0x18001ef0b  nop
0x18001ef0c  lea     rcx, [rsp+1A0h+ThreadInformation]; ThreadInformation
0x18001ef11  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18001ef16  nop
0x18001ef17  lea     rcx, [rsp+1A0h+var_160]; this
0x18001ef1c  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x18001ef21  nop
0x18001ef22  lea     rcx, [rsp+1A0h+var_150]
0x18001ef27  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001ef2c  nop
0x18001ef2d  mov     eax, ebx
0x18001ef2f  jmp     loc_18001F63A
0x18001ef34  mov     rsi, [rsp+1A0h+TokenHandle]
0x18001ef39  mov     [rsp+1A0h+var_138], r12d
0x18001ef3e  xorps   xmm0, xmm0
0x18001ef41  xor     eax, eax
0x18001ef43  movups  [rsp+1A0h+var_130], xmm0
0x18001ef48  movups  [rbp+0A0h+var_120], xmm0
0x18001ef4c  movups  [rbp+0A0h+var_110], xmm0
0x18001ef50  mov     [rbp+0A0h+var_100], rax
0x18001ef54  mov     [rsp+1A0h+var_134], r12d
0x18001ef59  lea     rax, [rsp+1A0h+var_138]
0x18001ef5e  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x18001ef63  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18001ef69  lea     r8, [rbp+0A0h+TokenInformation]; TokenInformation
0x18001ef6d  mov     edx, 1; TokenInformationClass
0x18001ef72  mov     rcx, rsi; TokenHandle
0x18001ef75  call    cs:__imp_GetTokenInformation
0x18001ef7b  test    eax, eax
0x18001ef7d  jz      short loc_18001EFD0
0x18001ef7f  mov     rcx, [rbp+0A0h+TokenInformation]; pSid
0x18001ef83  call    cs:__imp_GetLengthSid
0x18001ef89  mov     [rsp+1A0h+var_138], eax
0x18001ef8d  cmp     eax, 44h ; 'D'
0x18001ef90  jbe     short loc_18001EF99
0x18001ef92  mov     esi, 7Ah ; 'z'
0x18001ef97  jmp     short loc_18001EFDC
0x18001ef99  mov     r8d, eax; Size
0x18001ef9c  mov     rdx, [rbp+0A0h+TokenInformation]; Src
0x18001efa0  lea     rcx, [rbp+0A0h+Sid]; void *
0x18001efa4  call    memcpy_0
0x18001efa9  lea     rax, [rsp+1A0h+var_134]
0x18001efae  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x18001efb3  mov     r9d, 38h ; '8'; TokenInformationLength
0x18001efb9  lea     r8, [rsp+1A0h+var_130]; TokenInformation
0x18001efbe  mov     edx, 0Ah; TokenInformationClass
0x18001efc3  mov     rcx, rsi; TokenHandle
0x18001efc6  call    cs:__imp_GetTokenInformation
0x18001efcc  test    eax, eax
0x18001efce  jnz     short loc_18001F036
0x18001efd0  call    cs:__imp_GetLastError
0x18001efd6  mov     esi, eax
0x18001efd8  test    eax, eax
0x18001efda  jz      short loc_18001F040
0x18001efdc  lea     rdi, WPP_GLOBAL_Control
0x18001efe3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efea  cmp     rcx, rdi
0x18001efed  jz      short loc_18001F00E
0x18001efef  test    byte ptr [rcx+1Ch], 2
0x18001eff3  jz      short loc_18001F00E
0x18001eff5  mov     edx, 48h ; 'H'
0x18001effa  mov     r9d, esi
0x18001effd  lea     r8, WPP_f1575cf6446936089985711df8c7b212_Traceguids
0x18001f004  mov     rcx, [rcx+10h]
0x18001f008  call    WPP_SF_d
0x18001f00d  nop
0x18001f00e  lea     rcx, [rsp+1A0h+ThreadInformation]; ThreadInformation
0x18001f013  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18001f018  nop
0x18001f019  lea     rcx, [rsp+1A0h+var_160]; this
0x18001f01e  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x18001f023  nop
0x18001f024  lea     rcx, [rsp+1A0h+var_150]
0x18001f029  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001f02e  nop
0x18001f02f  mov     eax, esi
0x18001f031  jmp     loc_18001F63A
0x18001f036  mov     rbx, qword ptr [rsp+1A0h+var_130+8]
0x18001f03b  mov     qword ptr [rsp+1A0h+var_168.LowPart], rbx
0x18001f040  test    r15, r15
0x18001f043  jz      short loc_18001F048
0x18001f045  mov     [r15], rbx
0x18001f048  test    rdi, rdi
0x18001f04b  jz      short loc_18001F072
0x18001f04d  movaps  xmm0, [rbp+0A0h+Sid]
0x18001f051  movups  xmmword ptr [rdi], xmm0
0x18001f054  movaps  xmm1, [rbp+0A0h+var_E0]
0x18001f058  movups  xmmword ptr [rdi+10h], xmm1
0x18001f05c  movaps  xmm0, [rbp+0A0h+var_D0]
0x18001f060  movups  xmmword ptr [rdi+20h], xmm0
0x18001f064  movaps  xmm1, [rbp+0A0h+var_C0]
0x18001f068  movups  xmmword ptr [rdi+30h], xmm1
0x18001f06c  mov     eax, [rbp+0A0h+var_B0]
0x18001f06f  mov     [rdi+40h], eax
0x18001f072  mov     dl, 1; Wait
0x18001f074  lea     rcx, Resource; Resource
0x18001f07b  call    cs:__imp_RtlAcquireResourceShared
0x18001f081  lea     rcx, [rbp+0A0h+Sid]; Sid
0x18001f085  call    cs:__imp_RtlValidSid
0x18001f08b  test    al, al
0x18001f08d  jz      loc_18001F5DB
0x18001f093  lea     rcx, [rbp+0A0h+Sid]; pSid
0x18001f097  call    cs:__imp_GetSidSubAuthorityCount
0x18001f09d  movzx   ecx, byte ptr [rax]
0x18001f0a0  test    cl, cl
0x18001f0a2  jz      loc_18001F5DB
0x18001f0a8  lea     edx, [rcx-1]; nSubAuthority
0x18001f0ab  lea     rcx, [rbp+0A0h+Sid]; pSid
0x18001f0af  call    cs:__imp_GetSidSubAuthority
0x18001f0b5  mov     ecx, [rax]
0x18001f0b7  mov     eax, 0BA2E8BA3h
0x18001f0bc  mul     ecx
0x18001f0be  shr     edx, 3
0x18001f0c1  imul    eax, edx, 0Bh
0x18001f0c4  sub     ecx, eax
0x18001f0c6  lea     rsi, ?g_VaultMgr@VaultGlobals@@3VCVaultMgr@@A; CVaultMgr VaultGlobals::g_VaultMgr
0x18001f0cd  mov     rsi, [rsi+rcx*8]
0x18001f0d1  lea     rdi, WPP_GLOBAL_Control
0x18001f0d8  mov     r12d, [rsp+1A0h+var_168.HighPart]
0x18001f0dd  test    rsi, rsi
0x18001f0e0  jz      short loc_18001F100
0x18001f0e2  mov     rdx, [rsi]; Sid2
0x18001f0e5  lea     rcx, [rbp+0A0h+Sid]; Sid1
0x18001f0e9  call    cs:__imp_RtlEqualSid
0x18001f0ef  test    al, al
0x18001f0f1  jnz     loc_18001F1A6
0x18001f0f7  mov     rsi, [rsi+10h]
0x18001f0fb  test    rsi, rsi
0x18001f0fe  jnz     short loc_18001F0E2
0x18001f100  lea     rcx, Resource; Resource
0x18001f107  call    cs:__imp_RtlReleaseResource
0x18001f10d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f114  cmp     rcx, rdi
0x18001f117  jz      short loc_18001F13B
0x18001f119  test    byte ptr [rcx+1Ch], 8
0x18001f11d  jz      short loc_18001F13B
0x18001f11f  mov     edx, 4Bh ; 'K'
0x18001f124  mov     dword ptr [rsp+1A0h+ReturnLength], ebx
0x18001f128  mov     r9d, r12d
0x18001f12b  lea     r8, WPP_f1575cf6446936089985711df8c7b212_Traceguids
0x18001f132  mov     rcx, [rcx+10h]
0x18001f136  call    WPP_SF_dd
0x18001f13b  mov     r9, r14; struct CUserVaultMgr **
0x18001f13e  lea     r8, [rsp+1A0h+var_168]; struct _LUID *
0x18001f143  lea     rdx, [rbp+0A0h+Sid]; void *
0x18001f147  call    ?CreateUserVaultManager@CVaultMgr@@QEAAKPEAXPEAU_LUID@@PEAPEAVCUserVaultMgr@@@Z; CVaultMgr::CreateUserVaultManager(void *,_LUID *,CUserVaultMgr * *)
0x18001f14c  mov     esi, eax
0x18001f14e  test    eax, eax
0x18001f150  jz      short loc_18001F1C9
0x18001f152  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f159  cmp     rcx, rdi
0x18001f15c  jz      short loc_18001F17E
0x18001f15e  test    byte ptr [rcx+1Ch], 2
0x18001f162  jz      short loc_18001F17E
0x18001f164  mov     edx, 4Ch ; 'L'
0x18001f169  mov     [rsp+1A0h+var_178], eax
0x18001f16d  mov     dword ptr [rsp+1A0h+ReturnLength], ebx
0x18001f171  mov     r9d, r12d
0x18001f174  mov     rcx, [rcx+10h]
0x18001f178  call    WPP_SF_LLD
0x18001f17d  nop
0x18001f17e  lea     rcx, [rsp+1A0h+ThreadInformation]; ThreadInformation
0x18001f183  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18001f188  nop
0x18001f189  lea     rcx, [rsp+1A0h+var_160]; this
0x18001f18e  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x18001f193  nop
0x18001f194  lea     rcx, [rsp+1A0h+var_150]
0x18001f199  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001f19e  nop
0x18001f19f  mov     eax, esi
0x18001f1a1  jmp     loc_18001F63A
0x18001f1a6  mov     rcx, [rsi+8]
0x18001f1aa  mov     rax, [rcx]
0x18001f1ad  mov     rax, [rax]
0x18001f1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1b5  mov     rax, [rsi+8]
0x18001f1b9  mov     [r14], rax
0x18001f1bc  lea     rcx, Resource; Resource
0x18001f1c3  call    cs:__imp_RtlReleaseResource
0x18001f1c9  mov     rsi, [r14]
0x18001f1cc  cmp     byte ptr [rsi+44h], 0
0x18001f1d0  jnz     loc_18001F2A4
0x18001f1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1dd  cmp     rcx, rdi
0x18001f1e0  jz      short loc_18001F204
0x18001f1e2  test    byte ptr [rcx+1Ch], 8
0x18001f1e6  jz      short loc_18001F204
0x18001f1e8  mov     edx, 4Dh ; 'M'
0x18001f1ed  mov     dword ptr [rsp+1A0h+ReturnLength], ebx
0x18001f1f1  mov     r9d, r12d
0x18001f1f4  lea     r8, WPP_f1575cf6446936089985711df8c7b212_Traceguids
0x18001f1fb  mov     rcx, [rcx+10h]
0x18001f1ff  call    WPP_SF_dd
0x18001f204  mov     byte ptr [rsp+1A0h+ReturnLength], r13b; unsigned __int8
0x18001f209  lea     r9, [rsp+1A0h+var_168]; struct _LUID *
0x18001f20e  lea     r8, [rbp+0A0h+Sid]; void *
0x18001f212  mov     rdx, [rsp+1A0h+TokenHandle]; void *
0x18001f217  mov     rcx, [r14]; this
0x18001f21a  call    ?Initialize@CUserVaultMgr@@QEAAKPEAX0PEAU_LUID@@E@Z; CUserVaultMgr::Initialize(void *,void *,_LUID *,uchar)
0x18001f21f  mov     ebx, eax
0x18001f221  test    eax, eax
0x18001f223  jz      short loc_18001F295
0x18001f225  mov     rcx, [r14]
0x18001f228  mov     rdx, [rcx]
0x18001f22b  mov     rax, [rdx+8]
0x18001f22f  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
