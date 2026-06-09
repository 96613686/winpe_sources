# UnEnroll(ushort const *,ushort const *)

- ea: `0x140033dd0`
- end: `0x14003451c`
- name: `?UnEnroll@@YAJPEBG0@Z`
- size: `1868`
- prototype: `__int64 __fastcall(RPC_WSTR StringUuid, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x1400051cc`
- `0x1400052cc`
- `0x14000a0fc`
- `0x14000a6c4`
- `0x14001d65c`
- `0x14001d764`
- `0x140030a54`
- `0x1400337d8`
- `0x140033b18`
- `0x140033dd0`
- `0x140034544`
- `0x1400347e8`
- `0x140035078`
- `0x140035100`
- `0x14005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x14003402f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x14003402f`
- `dmEnrollEngine!EnrollEngineInitialize` at `0x140033fc0`
- `dmEnrollEngine!EnrollEngineInitialize` at `0x140033fc0`
- `dmEnrollEngine!GetEnrollmentPartnerOpaqueID` at `0x1400341ce`
- `dmEnrollEngine!GetEnrollmentPartnerOpaqueID` at `0x1400341ce`
- `dmEnrollEngine!GetEnrollmentState` at `0x14003437b`
- `dmEnrollEngine!GetEnrollmentState` at `0x14003437b`
- `dmEnrollEngine!GetEnrollmentSID` at `0x140034277`
- `dmEnrollEngine!GetEnrollmentSID` at `0x140034277`
- `dmEnrollEngine!GetEnrollmentType` at `0x140033ec2`
- `dmEnrollEngine!GetEnrollmentType` at `0x140033ec2`
- `dmEnrollEngine!__imp_?CleanupExpiredOMADMSessions@@YAXPEBG@Z` at `0x140033f9e`
- `dmEnrollEngine!__imp_?CleanupExpiredOMADMSessions@@YAXPEBG@Z` at `0x140033f9e`
- `DMCmnUtils!DmRevertToSelf` at `0x1400342ab`
- `DMCmnUtils!DmRevertToSelf` at `0x1400342ab`
- `DMCmnUtils!DmImpersonate` at `0x14003428c`
- `DMCmnUtils!DmImpersonate` at `0x14003428c`
- `omadmapi!__imp_?OmaDmWaitForAllSessionsCompletion@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@K@Z` at `0x140033fb0`
- `omadmapi!__imp_?OmaDmWaitForAllSessionsCompletion@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@K@Z` at `0x140033fb0`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x1400340bd`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x1400340bd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140033f76`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140033f76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140033f43`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140033f43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140034111`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140034235`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140034259`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400343ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400343cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400343f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003441c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140034111`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140034235`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140034259`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400343ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400343cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400343f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003441c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140034103`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140034227`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003424b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003439d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400343c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400343ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003440e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140034103`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140034227`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003424b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003439d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400343c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400343ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003440e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140033f94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140034125`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140033f94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140034125`
- `RPCRT4!UuidFromStringW` at `0x140033e33`
- `RPCRT4!UuidFromStringW` at `0x140033e44`
- `RPCRT4!UuidFromStringW` at `0x140033e33`
- `RPCRT4!UuidFromStringW` at `0x140033e44`
- `dsreg!DsrBeginDeviceUnjoin` at `0x140033f60`
- `dsreg!DsrBeginDeviceUnjoin` at `0x140033f60`

## string_xrefs

- `0x1400342ce`: `RemoveAWA`
- `0x140034071`: `com.microsoft:mdm.unenrollment.userrequest`

## pseudocode

```c
__int64 __fastcall UnEnroll(RPC_WSTR StringUuid, const unsigned __int16 *a2)
{
  RPC_STATUS v3; // eax
  __int64 v4; // r8
  signed int v5; // ebx
  void (*v6)(void); // rax
  int EnrollmentType; // eax
  __int64 v8; // r8
  unsigned int *v9; // rax
  __int64 v10; // r9
  __int64 *v11; // rdx
  __int64 v12; // r8
  char *EventW; // rbx
  int v14; // edi
  CEnrollmentLogger *Logger; // rax
  int v16; // r13d
  __int64 v17; // r8
  int ServerVersion; // r12d
  void *v19; // rdi
  const wchar_t *v20; // rax
  HANDLE ProcessHeap; // rax
  int EnrollmentPartnerOpaqueID; // eax
  __int64 v24; // r8
  HANDLE v25; // rdi
  HANDLE v26; // rax
  void *v27; // rdi
  HANDLE v28; // rax
  int EnrollmentSID; // edi
  int v30; // ebx
  const unsigned __int16 *v31; // rcx
  int v32; // eax
  char *v33; // rcx
  CEnrollmentLogger *v34; // rax
  __int64 v35; // r8
  int EnrollmentState; // eax
  HANDLE v37; // rbx
  HANDLE v38; // rax
  void *v39; // rbx
  HANDLE v40; // rax
  HANDLE v41; // rbx
  HANDLE v42; // rax
  void *v43; // rbx
  HANDLE v44; // rax
  int v45; // [rsp+20h] [rbp-E0h]
  unsigned int v46; // [rsp+40h] [rbp-C0h] BYREF
  int v47; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID lpMem[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v50; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hHandle[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v52; // [rsp+88h] [rbp-78h] BYREF
  UUID Uuid; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v54; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int *v55; // [rsp+B0h] [rbp-50h]
  __int64 v56; // [rsp+B8h] [rbp-48h]
  int v57; // [rsp+C0h] [rbp-40h]
  int v58; // [rsp+C4h] [rbp-3Ch]
  __int64 v59; // [rsp+C8h] [rbp-38h]
  __int128 v60; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v61[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  v48 = 0;
  Uuid = 0;
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(StringUuid, EnterpriseDiagnosticsUnEnrollmentNotInitiatedByTheUser, StringUuid);
  if ( UuidFromStringW(StringUuid, &Uuid) )
  {
    v3 = UuidFromStringW(StringUuid, &Uuid);
    v5 = v3 | 0x80010000;
    if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
    {
      v46 = v3 | 0x80010000;
      v55 = &v46;
      v56 = 4;
      McGenEventWrite_EventWriteTransfer(
        WP_ENROLLMENT_CLIENT_PROVIDER_Context,
        StartingUnenrollmentFailedEvent,
        v4,
        2,
        &v54);
    }
    if ( !v48 )
      return (unsigned int)v5;
    v6 = *(void (**)(void))(*(_QWORD *)v48 + 112LL);
    goto LABEL_83;
  }
  v50 = 0;
  *(UUID *)lpMem = Uuid;
  EnrollmentType = GetEnrollmentType(lpMem, &v50);
  v5 = EnrollmentType;
  if ( EnrollmentType < 0 )
  {
    if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
    {
      v46 = EnrollmentType;
      v9 = &v46;
LABEL_11:
      v55 = v9;
      v56 = 4;
      v10 = 2;
      v11 = StartingUnenrollmentFailedEvent;
LABEL_80:
      McGenEventWrite_EventWriteTransfer(WP_ENROLLMENT_CLIENT_PROVIDER_Context, v11, v8, v10, &v54);
      goto LABEL_81;
    }
    goto LABEL_81;
  }
  if ( v50 == 6 )
  {
    if ( (unsigned __int8)IsConvertLocalAccountToAADAccountPresent()
      || (unsigned __int8)IsCreateAndSignInAADUserPresent() )
    {
      if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
      {
        v46 = -2147467263;
        v55 = &v46;
        v56 = 4;
        McGenEventWrite_EventWriteTransfer(
          WP_ENROLLMENT_CLIENT_PROVIDER_Context,
          StartingUnenrollmentFailedEvent,
          v12,
          2,
          &v54);
      }
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 112LL))(v48);
      return 2147500033LL;
    }
    else
    {
      *(_OWORD *)hHandle = 0;
      EventW = (char *)CreateEventW(0, 0, 0, 0);
      hHandle[0] = EventW;
      v14 = DsrBeginDeviceUnjoin(UnjoinCallback, hHandle, 0);
      if ( v14 >= 0 )
      {
        if ( WaitForSingleObject(hHandle[0], 0x493E0u) || (v14 = (int)hHandle[1], SLODWORD(hHandle[1]) >= 0) )
        {
          if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(EventW);
          goto LABEL_20;
        }
      }
      Logger = CEnrollmentLogger::GetLogger();
      *(UUID *)lpMem = Uuid;
      CEnrollmentLogger::LogServerUnenrollAADUnjoinFailed(Logger, v14, (struct _GUID *)lpMem);
      lpMem[0] = 0;
      v16 = 0;
      ServerVersion = GetServerVersion(StringUuid, lpMem);
      v19 = lpMem[0];
      if ( ServerVersion < 0 || _o_wcstod(lpMem[0], 0) < 4.0 )
      {
        v20 = L"2";
      }
      else
      {
        v16 = 1;
        v20 = L"AADJ Unregister Failed";
      }
      v55 = 0;
      v59 = 0;
      v60 = 0;
      v54.Data1 = 64;
      *(_QWORD *)v54.Data4 = L"com.microsoft:mdm.unenrollment.userrequest";
      *(_DWORD *)&v54.Data2 = 1226;
      v56 = (__int64)v20;
      v57 = v16;
      v58 = 2;
      if ( StringUuid )
        OmaDmInitiateSessionAsDevice(StringUuid, 1, 2, &v54, 1, 0, 9);
      if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
      {
        v46 = ServerVersion;
        v55 = &v46;
        v56 = 4;
        McGenEventWrite_EventWriteTransfer(
          WP_ENROLLMENT_CLIENT_PROVIDER_Context,
          StartingUnenrollmentFailedEvent,
          v17,
          2,
          &v54);
      }
      if ( v19 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v19);
      }
      if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(EventW);
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 112LL))(v48);
      return (unsigned int)ServerVersion;
    }
  }
  else
  {
    if ( v50 != 13 )
      goto LABEL_20;
    lpMem[0] = 0;
    hHandle[0] = 0;
    v54 = Uuid;
    EnrollmentPartnerOpaqueID = GetEnrollmentPartnerOpaqueID(&v54, lpMem);
    v5 = EnrollmentPartnerOpaqueID;
    if ( EnrollmentPartnerOpaqueID < 0 )
    {
      if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
      {
        v47 = EnrollmentPartnerOpaqueID;
        v55 = (unsigned int *)&v47;
        v56 = 4;
        McGenEventWrite_EventWriteTransfer(
          WP_ENROLLMENT_CLIENT_PROVIDER_Context,
          StartingUnenrollmentFailedEvent,
          v24,
          2,
          &v54);
      }
      v25 = hHandle[0];
      hHandle[0] = 0;
      if ( v25 )
      {
        v26 = GetProcessHeap();
        HeapFree(v26, 0, v25);
      }
      v27 = lpMem[0];
      lpMem[0] = 0;
      if ( v27 )
      {
        v28 = GetProcessHeap();
        HeapFree(v28, 0, v27);
      }
      goto LABEL_81;
    }
    v54 = Uuid;
    EnrollmentSID = GetEnrollmentSID(&v54, hHandle);
    if ( EnrollmentSID < 0 )
      goto LABEL_60;
    v30 = DmImpersonate((const unsigned __int16 *)hHandle[0]) >> 31;
    EnrollmentSID = DeleteAWAAccount(v31, (const unsigned __int16 *)lpMem[0]);
    v32 = 0;
    if ( (unsigned __int8)v30 != 1 )
      v32 = DmRevertToSelf();
    if ( v32 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
        (const char *)(unsigned int)v32,
        v45);
    if ( EnrollmentSID < 0
      && ((EnrollmentSID = StringCchPrintfW(v61, 0x104u, L"-%s %s", L"RemoveAWA", lpMem[0]), EnrollmentSID < 0)
       || (EnrollmentSID = RunCmdAsUser(v33, v61, (unsigned __int16 *)hHandle[0]), EnrollmentSID < 0))
      || EnrollmentSID == 267011 )
    {
LABEL_60:
      v34 = CEnrollmentLogger::GetLogger();
      v54 = Uuid;
      CEnrollmentLogger::LogServerUnenrollTBRemoveAccountFailed(v34, EnrollmentSID, &v54);
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v47 = EnrollmentSID;
        v55 = (unsigned int *)&v47;
        v56 = 4;
        McGenEventWrite_EventWriteTransfer(
          MDM_ENTERPRISE_DIAGNOSTICS_Context,
          EnterpriseDiagnosticsUnenrollmentDeleteAccountFailed,
          v35,
          2,
          &v54);
      }
    }
    v46 = 63;
    v54 = Uuid;
    EnrollmentState = GetEnrollmentState(&v54, &v46);
    if ( v46 != 4 && EnrollmentState != -2147024894 )
    {
      v37 = hHandle[0];
      hHandle[0] = 0;
      if ( v37 )
      {
        v38 = GetProcessHeap();
        HeapFree(v38, 0, v37);
      }
      v39 = lpMem[0];
      lpMem[0] = 0;
      if ( v39 )
      {
        v40 = GetProcessHeap();
        HeapFree(v40, 0, v39);
      }
LABEL_20:
      CleanupExpiredOMADMSessions(StringUuid);
      OmaDmWaitForAllSessionsCompletion(StringUuid, 1, 10000);
      v5 = EnrollEngineInitialize(1, 0, &v48);
      if ( v5 < 0
        || (v52 = 0,
            v5 = (*(__int64 (__fastcall **)(__int64, UUID *, _QWORD, __int64 *))(*(_QWORD *)v48 + 32LL))(
                   v48,
                   &Uuid,
                   0,
                   &v52),
            v5 < 0)
        || (v54 = Uuid,
            v5 = WaitForUnenrollment(v48, v52, &v54),
            v52 = 0,
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 120LL))(v48),
            v5 < 0) )
      {
        if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
        {
          v47 = v5;
          v9 = (unsigned int *)&v47;
          goto LABEL_11;
        }
      }
      else if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 1) != 0 )
      {
        v10 = 1;
        v11 = UnenrollmentFinishedEvent;
        goto LABEL_80;
      }
LABEL_81:
      if ( !v48 )
        return (unsigned int)v5;
      v6 = *(void (**)(void))(*(_QWORD *)v48 + 112LL);
LABEL_83:
      v6();
      return (unsigned int)v5;
    }
    v41 = hHandle[0];
    hHandle[0] = 0;
    if ( v41 )
    {
      v42 = GetProcessHeap();
      HeapFree(v42, 0, v41);
    }
    v43 = lpMem[0];
    lpMem[0] = 0;
    if ( v43 )
    {
      v44 = GetProcessHeap();
      HeapFree(v44, 0, v43);
    }
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 112LL))(v48);
    return 0;
  }
}

```

## disassembly

```asm
0x140033dd0  push    rbp
0x140033dd2  push    rbx
0x140033dd3  push    rsi
0x140033dd4  push    rdi
0x140033dd5  push    r12
0x140033dd7  push    r13
0x140033dd9  push    r14
0x140033ddb  push    r15
0x140033ddd  lea     rbp, [rsp-208h]
0x140033de5  sub     rsp, 308h
0x140033dec  mov     rax, cs:__security_cookie
0x140033df3  xor     rax, rsp
0x140033df6  mov     [rbp+240h+var_50], rax
0x140033dfd  mov     r15, rcx
0x140033e00  xor     r12d, r12d
0x140033e03  mov     [rsp+340h+var_2F0], r12
0x140033e08  xorps   xmm0, xmm0
0x140033e0b  movups  xmmword ptr [rbp+240h+Uuid.Data1], xmm0
0x140033e0f  lea     r13d, [r12+2]
0x140033e14  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, r13b
0x140033e1b  jz      short loc_140033E2C
0x140033e1d  mov     r8, rcx
0x140033e20  lea     rdx, EnterpriseDiagnosticsUnEnrollmentNotInitiatedByTheUser
0x140033e27  call    McTemplateU0z_EventWriteTransfer
0x140033e2c  lea     rdx, [rbp+240h+Uuid]; Uuid
0x140033e30  mov     rcx, r15; StringUuid
0x140033e33  call    cs:__imp_UuidFromStringW
0x140033e39  test    eax, eax
0x140033e3b  jz      short loc_140033EA9
0x140033e3d  lea     rdx, [rbp+240h+Uuid]; Uuid
0x140033e41  mov     rcx, r15; StringUuid
0x140033e44  call    cs:__imp_UuidFromStringW
0x140033e4a  mov     ebx, eax
0x140033e4c  or      ebx, 80010000h
0x140033e52  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, r13b
0x140033e59  jz      short loc_140033E8F
0x140033e5b  mov     [rsp+340h+var_300], ebx
0x140033e5f  lea     rax, [rsp+340h+var_300]
0x140033e64  mov     [rbp+240h+var_290], rax
0x140033e68  mov     [rbp+240h+var_288], 4
0x140033e70  lea     rax, [rbp+240h+var_2A0]
0x140033e74  mov     [rsp+340h+var_320], rax
0x140033e79  mov     r9d, r13d
0x140033e7c  lea     rdx, StartingUnenrollmentFailedEvent
0x140033e83  lea     rcx, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x140033e8a  call    McGenEventWrite_EventWriteTransfer
0x140033e8f  mov     rcx, [rsp+340h+var_2F0]
0x140033e94  test    rcx, rcx
0x140033e97  jz      loc_1400344E2
0x140033e9d  mov     rdx, [rcx]
0x140033ea0  mov     rax, [rdx+70h]
0x140033ea4  jmp     loc_1400344DD
0x140033ea9  mov     [rsp+340h+var_2D0], r12d
0x140033eae  movaps  xmm0, xmmword ptr [rbp+240h+Uuid.Data1]
0x140033eb2  movdqa  xmmword ptr [rsp+340h+lpMem], xmm0
0x140033eb8  lea     rdx, [rsp+340h+var_2D0]
0x140033ebd  lea     rcx, [rsp+340h+lpMem]
0x140033ec2  call    cs:__imp_GetEnrollmentType
0x140033ec8  mov     ebx, eax
0x140033eca  test    eax, eax
0x140033ecc  jns     short loc_140033F03
0x140033ece  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, r13b
0x140033ed5  jz      loc_1400344CC
0x140033edb  mov     [rsp+340h+var_300], eax
0x140033edf  lea     rax, [rsp+340h+var_300]
0x140033ee4  mov     [rbp+240h+var_290], rax
0x140033ee8  mov     [rbp+240h+var_288], 4
0x140033ef0  lea     rax, [rbp+240h+var_2A0]
0x140033ef4  mov     r9d, r13d
0x140033ef7  lea     rdx, StartingUnenrollmentFailedEvent
0x140033efe  jmp     loc_1400344BB
0x140033f03  mov     esi, 4
0x140033f08  lea     r14d, [rsi-3]
0x140033f0c  cmp     [rsp+340h+var_2D0], 6
0x140033f11  jnz     loc_1400341A7
0x140033f17  call    IsConvertLocalAccountToAADAccountPresent
0x140033f1c  test    al, al
0x140033f1e  jnz     loc_14003414A
0x140033f24  call    IsCreateAndSignInAADUserPresent
0x140033f29  test    al, al
0x140033f2b  jnz     loc_14003414A
0x140033f31  xorps   xmm0, xmm0
0x140033f34  movups  xmmword ptr [rsp+340h+hHandle], xmm0
0x140033f39  xor     r9d, r9d; lpName
0x140033f3c  xor     r8d, r8d; bInitialState
0x140033f3f  xor     edx, edx; bManualReset
0x140033f41  xor     ecx, ecx; lpEventAttributes
0x140033f43  call    cs:__imp_CreateEventW
0x140033f49  mov     rbx, rax
0x140033f4c  mov     [rsp+340h+hHandle], rax
0x140033f51  xor     r8d, r8d
0x140033f54  lea     rdx, [rsp+340h+hHandle]
0x140033f59  lea     rcx, UnjoinCallback
0x140033f60  call    cs:__imp_DsrBeginDeviceUnjoin
0x140033f66  mov     edi, eax
0x140033f68  test    eax, eax
0x140033f6a  js      short loc_140033FEB
0x140033f6c  mov     edx, 493E0h; dwMilliseconds
0x140033f71  mov     rcx, [rsp+340h+hHandle]; hHandle
0x140033f76  call    cs:__imp_WaitForSingleObject
0x140033f7c  test    eax, eax
0x140033f7e  jnz     short loc_140033F87
0x140033f80  mov     edi, dword ptr [rbp+240h+hHandle+8]
0x140033f83  test    edi, edi
0x140033f85  js      short loc_140033FEB
0x140033f87  lea     rax, [rbx-1]
0x140033f8b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140033f8f  ja      short loc_140033F9B
0x140033f91  mov     rcx, rbx; hObject
0x140033f94  call    cs:__imp_CloseHandle
0x140033f9a  nop
0x140033f9b  mov     rcx, r15
0x140033f9e  call    cs:__imp_?CleanupExpiredOMADMSessions@@YAXPEBG@Z; CleanupExpiredOMADMSessions(ushort const *)
0x140033fa4  mov     r8d, 2710h
0x140033faa  mov     edx, r14d
0x140033fad  mov     rcx, r15
0x140033fb0  call    cs:__imp_?OmaDmWaitForAllSessionsCompletion@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@K@Z; OmaDmWaitForAllSessionsCompletion(ushort const *,tagDMACCOUNTLOOKUPTYPE,ulong)
0x140033fb6  lea     r8, [rsp+340h+var_2F0]
0x140033fbb  xor     edx, edx
0x140033fbd  mov     ecx, r14d
0x140033fc0  call    cs:__imp_EnrollEngineInitialize
0x140033fc6  mov     ebx, eax
0x140033fc8  test    eax, eax
0x140033fca  jns     loc_140034440
0x140033fd0  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, r13b
0x140033fd7  jz      loc_1400344CC
0x140033fdd  mov     [rsp+340h+var_2F8], ebx
0x140033fe1  lea     rax, [rsp+340h+var_2F8]
0x140033fe6  jmp     loc_140033EE4
0x140033feb  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140033ff0  movaps  xmm0, xmmword ptr [rbp+240h+Uuid.Data1]
0x140033ff4  movdqa  xmmword ptr [rsp+340h+lpMem], xmm0
0x140033ffa  lea     r8, [rsp+340h+lpMem]; struct _GUID
0x140033fff  mov     edx, edi; int
0x140034001  mov     rcx, rax; this
0x140034004  call    ?LogServerUnenrollAADUnjoinFailed@CEnrollmentLogger@@QEAAXJU_GUID@@@Z; CEnrollmentLogger::LogServerUnenrollAADUnjoinFailed(long,_GUID)
0x140034009  mov     [rsp+340h+lpMem], r12
0x14003400e  mov     r13d, r12d
0x140034011  lea     rdx, [rsp+340h+lpMem]
0x140034016  mov     rcx, r15
0x140034019  call    GetServerVersion
0x14003401e  mov     r12d, eax
0x140034021  mov     rdi, [rsp+340h+lpMem]
0x140034026  test    eax, eax
0x140034028  js      short loc_14003404B
0x14003402a  xor     edx, edx
0x14003402c  mov     rcx, rdi
0x14003402f  call    cs:__imp__o_wcstod
0x140034035  comisd  xmm0, cs:__real@4010000000000000
0x14003403d  jb      short loc_14003404B
0x14003403f  mov     r13d, r14d
0x140034042  lea     rax, aAadjUnregister; "AADJ Unregister Failed"
0x140034049  jmp     short loc_140034052
0x14003404b  lea     rax, a2; "2"
0x140034052  mov     [rbp+240h+var_290], 0
0x14003405a  mov     [rbp+240h+var_278], 0
0x140034062  xorps   xmm0, xmm0
0x140034065  movdqa  [rbp+240h+var_270], xmm0
0x14003406a  mov     [rbp+240h+var_2A0.Data1], 40h ; '@'
0x140034071  lea     rcx, aComMicrosoftMd; "com.microsoft:mdm.unenrollment.userrequ"...
0x140034078  mov     qword ptr [rbp+240h+var_2A0.Data4], rcx
0x14003407c  mov     dword ptr [rbp+240h+var_2A0.Data2], 4CAh
0x140034083  mov     [rbp+240h+var_288], rax
0x140034087  mov     [rbp+240h+var_280], r13d
0x14003408b  mov     r13d, 2
0x140034091  mov     [rbp+240h+var_27C], r13d
0x140034095  test    r15, r15
0x140034098  jz      short loc_1400340C3
0x14003409a  mov     [rsp+340h+var_310], 9
0x1400340a2  mov     [rsp+340h+var_318], 0
0x1400340ab  mov     dword ptr [rsp+340h+var_320], r14d
0x1400340b0  lea     r9, [rbp+240h+var_2A0]
0x1400340b4  mov     r8d, r13d
0x1400340b7  mov     edx, r14d
0x1400340ba  mov     rcx, r15
0x1400340bd  call    cs:__imp_OmaDmInitiateSessionAsDevice
0x1400340c3  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, r13b
0x1400340ca  jz      short loc_1400340FE
0x1400340cc  mov     [rsp+340h+var_300], r12d
0x1400340d1  lea     rax, [rsp+340h+var_300]
0x1400340d6  mov     [rbp+240h+var_290], rax
0x1400340da  mov     [rbp+240h+var_288], rsi
0x1400340de  lea     rax, [rbp+240h+var_2A0]
0x1400340e2  mov     [rsp+340h+var_320], rax
0x1400340e7  mov     r9d, r13d
0x1400340ea  lea     rdx, StartingUnenrollmentFailedEvent
0x1400340f1  lea     rcx, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x1400340f8  call    McGenEventWrite_EventWriteTransfer
0x1400340fd  nop
0x1400340fe  test    rdi, rdi
0x140034101  jz      short loc_140034118
0x140034103  call    cs:__imp_GetProcessHeap
0x140034109  mov     rcx, rax; hHeap
0x14003410c  mov     r8, rdi; lpMem
0x14003410f  xor     edx, edx; dwFlags
0x140034111  call    cs:__imp_HeapFree
0x140034117  nop
0x140034118  lea     rax, [rbx-1]
0x14003411c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140034120  ja      short loc_14003412C
0x140034122  mov     rcx, rbx; hObject
0x140034125  call    cs:__imp_CloseHandle
0x14003412b  nop
0x14003412c  mov     rcx, [rsp+340h+var_2F0]
0x140034131  test    rcx, rcx
0x140034134  jz      short loc_140034142
0x140034136  mov     rax, [rcx]
0x140034139  mov     rax, [rax+70h]
0x14003413d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034142  mov     eax, r12d
0x140034145  jmp     loc_1400344E4
0x14003414a  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, r13b
0x140034151  jz      short loc_140034187
0x140034153  mov     [rsp+340h+var_300], 80004001h
0x14003415b  lea     rax, [rsp+340h+var_300]
0x140034160  mov     [rbp+240h+var_290], rax
0x140034164  mov     [rbp+240h+var_288], rsi
0x140034168  lea     rax, [rbp+240h+var_2A0]
0x14003416c  mov     [rsp+340h+var_320], rax
0x140034171  mov     r9d, r13d
0x140034174  lea     rdx, StartingUnenrollmentFailedEvent
0x14003417b  lea     rcx, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x140034182  call    McGenEventWrite_EventWriteTransfer
0x140034187  mov     rcx, [rsp+340h+var_2F0]
0x14003418c  test    rcx, rcx
0x14003418f  jz      short loc_14003419D
0x140034191  mov     rax, [rcx]
0x140034194  mov     rax, [rax+70h]
0x140034198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003419d  mov     eax, 80004001h
0x1400341a2  jmp     loc_1400344E4
0x1400341a7  cmp     [rsp+340h+var_2D0], 0Dh
0x1400341ac  jnz     loc_140033F9B
0x1400341b2  mov     [rsp+340h+lpMem], r12
0x1400341b7  mov     [rsp+340h+hHandle], r12
0x1400341bc  movaps  xmm0, xmmword ptr [rbp+240h+Uuid.Data1]
0x1400341c0  movdqa  xmmword ptr [rbp+240h+var_2A0.Data1], xmm0
0x1400341c5  lea     rdx, [rsp+340h+lpMem]
0x1400341ca  lea     rcx, [rbp+240h+var_2A0]
0x1400341ce  call    cs:__imp_GetEnrollmentPartnerOpaqueID
0x1400341d4  mov     ebx, eax
0x1400341d6  test    eax, eax
0x1400341d8  jns     loc_140034265
0x1400341de  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, r13b
0x1400341e5  jz      short loc_140034218
0x1400341e7  mov     [rsp+340h+var_2F8], eax
0x1400341eb  lea     rax, [rsp+340h+var_2F8]
0x1400341f0  mov     [rbp+240h+var_290], rax
0x1400341f4  mov     [rbp+240h+var_288], rsi
0x1400341f8  lea     rax, [rbp+240h+var_2A0]
0x1400341fc  mov     [rsp+340h+var_320], rax
0x140034201  mov     r9d, r13d
0x140034204  lea     rdx, StartingUnenrollmentFailedEvent
0x14003420b  lea     rcx, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x140034212  call    McGenEventWrite_EventWriteTransfer
0x140034217  nop
0x140034218  mov     rdi, [rsp+340h+hHandle]
0x14003421d  mov     [rsp+340h+hHandle], r12
0x140034222  test    rdi, rdi
0x140034225  jz      short loc_14003423C
0x140034227  call    cs:__imp_GetProcessHeap
0x14003422d  mov     rcx, rax; hHeap
0x140034230  mov     r8, rdi; lpMem
0x140034233  xor     edx, edx; dwFlags
0x140034235  call    cs:__imp_HeapFree
0x14003423b  nop
0x14003423c  mov     rdi, [rsp+340h+lpMem]
0x140034241  mov     [rsp+340h+lpMem], r12
0x140034246  test    rdi, rdi
0x140034249  jz      short loc_140034260
0x14003424b  call    cs:__imp_GetProcessHeap
0x140034251  mov     rcx, rax; hHeap
0x140034254  mov     r8, rdi; lpMem
0x140034257  xor     edx, edx; dwFlags
0x140034259  call    cs:__imp_HeapFree
0x14003425f  nop
0x140034260  jmp     loc_1400344CC
0x140034265  movaps  xmm0, xmmword ptr [rbp+240h+Uuid.Data1]
0x140034269  movdqa  xmmword ptr [rbp+240h+var_2A0.Data1], xmm0
0x14003426e  lea     rdx, [rsp+340h+hHandle]
0x140034273  lea     rcx, [rbp+240h+var_2A0]
0x140034277  call    cs:__imp_GetEnrollmentSID
0x14003427d  mov     edi, eax
0x14003427f  test    eax, eax
0x140034281  js      loc_14003430C
0x140034287  mov     rcx, [rsp+340h+hHandle]
0x14003428c  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x140034292  mov     ebx, eax
0x140034294  shr     ebx, 1Fh
0x140034297  mov     rdx, [rsp+340h+lpMem]; unsigned __int16 *
0x14003429c  call    ?DeleteAWAAccount@@YAJPEBG0@Z; DeleteAWAAccount(ushort const *,ushort const *)
0x1400342a1  mov     edi, eax
0x1400342a3  mov     eax, r12d
0x1400342a6  xor     bl, r14b
0x1400342a9  jz      short loc_1400342B1
0x1400342ab  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x1400342b1  mov     rcx, [rbp+248h]; this
0x1400342b8  test    eax, eax
0x1400342ba  js      loc_140034507
0x1400342c0  test    edi, edi
  ... truncated ...
```
