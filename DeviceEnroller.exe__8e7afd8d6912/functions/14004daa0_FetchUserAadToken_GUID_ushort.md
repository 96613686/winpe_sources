# FetchUserAadToken(_GUID,ushort * *)

- ea: `0x14004daa0`
- end: `0x14004dcb4`
- name: `?FetchUserAadToken@@YAJU_GUID@@PEAPEAG@Z`
- size: `532`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004c794`

## callees

- `0x140005c69`
- `0x14004d848`
- `0x14004daa0`
- `0x14004e8d4`
- `0x14004f4d0`

## import_xrefs

- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x14004dba9`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x14004dba9`
- `dmEnrollEngine!GetEnrollmentType` at `0x14004db57`
- `dmEnrollEngine!GetEnrollmentType` at `0x14004db57`
- `DMCmnUtils!DmGetAadUserToken` at `0x14004dc3f`
- `DMCmnUtils!DmGetAadUserToken` at `0x14004dc3f`
- `DMCmnUtils!DmGetActiveUserSid` at `0x14004dbef`
- `DMCmnUtils!DmGetActiveUserSid` at `0x14004dbef`
- `DMCmnUtils!DmImpersonate` at `0x14004dc08`
- `DMCmnUtils!DmImpersonate` at `0x14004dc08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dbca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dbca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004dbdd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004dbdd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004dbd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004dc6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004dc99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004dbd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004dc6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004dc99`

## string_xrefs

- `0x14004db27`: `FetchUserAadToken - IsRunningInSystemContext() failed - Error 0x%1!x!`
- `0x14004db3b`: `FetchUserAadToken - not running as system context`
- `0x14004dbb5`: `FetchUserAadToken - GetEnrollmentAadResourceUrl failed`
- `0x14004dbfb`: `FetchUserAadToken - DmGetActiveUserSid failed`
- `0x14004db65`: `FetchUserAadToken - GetEnrollmentType failed`
- `0x14004db8d`: `FetchUserAadToken - not AAD type enrollment, skipping`
- `0x14004dc4b`: `FetchUserAadToken - DmGetAadUserToken failed`
- `0x14004dc14`: `FetchUserAadToken - DmImpersonate failed`

## pseudocode

```c
__int64 __fastcall FetchUserAadToken(struct _GUID *a1, unsigned __int16 **a2)
{
  int v4; // eax
  int EnrollmentType; // eax
  int AadUserToken; // ebx
  const wchar_t *v7; // rcx
  int EnrollmentAadResourceUrl; // eax
  HLOCAL v9; // rdi
  DWORD LastError; // ebx
  int ActiveUserSid; // eax
  int v12; // eax
  int v14; // [rsp+30h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 *v16; // [rsp+40h] [rbp-40h] BYREF
  const unsigned __int16 *v17; // [rsp+48h] [rbp-38h] BYREF
  __int128 v18; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v19[3]; // [rsp+60h] [rbp-20h] BYREF
  char v20; // [rsp+78h] [rbp-8h]
  bool v21; // [rsp+B0h] [rbp+30h] BYREF
  int v22; // [rsp+B8h] [rbp+38h] BYREF

  v17 = 0;
  v16 = 0;
  v22 = 63;
  v14 = 0;
  v21 = 0;
  hMem = 0;
  v19[0] = &v17;
  v19[1] = &v16;
  v19[2] = &v14;
  v20 = 1;
  if ( !memcmp_0(a1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
  {
LABEL_22:
    wil::details::lambda_call__lambda_159a528f88c4b2c318bfd9979f3095ee___::_lambda_call__lambda_159a528f88c4b2c318bfd9979f3095ee___(v19);
    if ( hMem )
      LocalFree(hMem);
    return 0;
  }
  v4 = IsRunningInSystemContext(&v21);
  if ( v4 < 0 )
  {
    LogTelemetryError(L"FetchUserAadToken - IsRunningInSystemContext() failed - Error 0x%1!x!", (unsigned int)v4);
    goto LABEL_22;
  }
  if ( !v21 )
  {
    LogTelemetryError(L"FetchUserAadToken - not running as system context", (unsigned int)v4);
    goto LABEL_22;
  }
  v18 = (__int128)*a1;
  EnrollmentType = GetEnrollmentType(&v18, &v22);
  AadUserToken = EnrollmentType;
  if ( EnrollmentType >= 0 )
  {
    if ( ((1LL << v22) & 0x5402060) != 0 || !v22 )
    {
      v18 = (__int128)*a1;
      EnrollmentAadResourceUrl = GetEnrollmentAadResourceUrl(&v18, &v17);
      if ( EnrollmentAadResourceUrl < 0 )
      {
        LogTelemetryError(
          L"FetchUserAadToken - GetEnrollmentAadResourceUrl failed",
          (unsigned int)EnrollmentAadResourceUrl);
        goto LABEL_22;
      }
      v9 = hMem;
      if ( hMem )
      {
        LastError = GetLastError();
        LocalFree(v9);
        SetLastError(LastError);
      }
      hMem = 0;
      ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&hMem);
      if ( ActiveUserSid < 0 )
      {
        LogTelemetryError(L"FetchUserAadToken - DmGetActiveUserSid failed", (unsigned int)ActiveUserSid);
        goto LABEL_22;
      }
      v12 = DmImpersonate((const unsigned __int16 *)hMem);
      if ( v12 < 0 )
      {
        LogTelemetryError(L"FetchUserAadToken - DmImpersonate failed", (unsigned int)v12);
        goto LABEL_22;
      }
      v14 = 1;
      AadUserToken = DmGetAadUserToken(L"de50c81f-5f80-4771-b66b-cebd28ccdfc1", v17, 0, &v16, 0);
      if ( AadUserToken >= 0 )
      {
        *a2 = v16;
        v16 = 0;
        goto LABEL_26;
      }
      v7 = L"FetchUserAadToken - DmGetAadUserToken failed";
    }
    else
    {
      v7 = L"FetchUserAadToken - not AAD type enrollment, skipping";
    }
    LogTelemetryError(v7, (unsigned int)AadUserToken);
    goto LABEL_22;
  }
  LogTelemetryError(L"FetchUserAadToken - GetEnrollmentType failed", (unsigned int)EnrollmentType);
LABEL_26:
  wil::details::lambda_call__lambda_159a528f88c4b2c318bfd9979f3095ee___::_lambda_call__lambda_159a528f88c4b2c318bfd9979f3095ee___(v19);
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)AadUserToken;
}

```

## disassembly

```asm
0x14004daa0  mov     [rsp-18h+arg_0], rbx
0x14004daa5  push    rbp
0x14004daa6  push    rsi
0x14004daa7  push    rdi
0x14004daa8  mov     rbp, rsp
0x14004daab  sub     rsp, 80h
0x14004dab2  mov     rsi, rdx
0x14004dab5  mov     rdi, rcx
0x14004dab8  mov     [rbp+var_38], 0
0x14004dac0  mov     [rbp+var_40], 0
0x14004dac8  mov     [rbp+arg_18], 3Fh ; '?'
0x14004dacf  mov     [rbp+var_50], 0
0x14004dad6  mov     [rbp+arg_10], 0
0x14004dada  mov     [rbp+hMem], 0
0x14004dae2  lea     rax, [rbp+var_38]
0x14004dae6  mov     [rbp+var_20], rax
0x14004daea  lea     rax, [rbp+var_40]
0x14004daee  mov     [rbp+var_18], rax
0x14004daf2  lea     rax, [rbp+var_50]
0x14004daf6  mov     [rbp+var_10], rax
0x14004dafa  mov     [rbp+var_8], 1
0x14004dafe  mov     r8d, 10h; Size
0x14004db04  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x14004db0b  call    memcmp_0
0x14004db10  test    eax, eax
0x14004db12  jz      loc_14004DC5A
0x14004db18  lea     rcx, [rbp+arg_10]; bool *
0x14004db1c  call    ?IsRunningInSystemContext@@YAJAEA_N@Z; IsRunningInSystemContext(bool &)
0x14004db21  test    eax, eax
0x14004db23  jns     short loc_14004DB33
0x14004db25  mov     edx, eax
0x14004db27  lea     rcx, aFetchuseraadto_3; "FetchUserAadToken - IsRunningInSystemCo"...
0x14004db2e  jmp     loc_14004DC54
0x14004db33  cmp     [rbp+arg_10], 0
0x14004db37  jnz     short loc_14004DB47
0x14004db39  mov     edx, eax
0x14004db3b  lea     rcx, aFetchuseraadto; "FetchUserAadToken - not running as syst"...
0x14004db42  jmp     loc_14004DC54
0x14004db47  movaps  xmm0, xmmword ptr [rdi]
0x14004db4a  movdqa  [rbp+var_30], xmm0
0x14004db4f  lea     rdx, [rbp+arg_18]
0x14004db53  lea     rcx, [rbp+var_30]
0x14004db57  call    cs:__imp_GetEnrollmentType
0x14004db5d  mov     ebx, eax
0x14004db5f  test    eax, eax
0x14004db61  jns     short loc_14004DB76
0x14004db63  mov     edx, eax
0x14004db65  lea     rcx, aFetchuseraadto_0; "FetchUserAadToken - GetEnrollmentType f"...
0x14004db6c  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004db71  jmp     loc_14004DC86
0x14004db76  mov     ecx, [rbp+arg_18]
0x14004db79  mov     eax, 1
0x14004db7e  shl     rax, cl
0x14004db81  test    rax, 5402060h
0x14004db87  jnz     short loc_14004DB99
0x14004db89  test    ecx, ecx
0x14004db8b  jz      short loc_14004DB99
0x14004db8d  lea     rcx, aFetchuseraadto_2; "FetchUserAadToken - not AAD type enroll"...
0x14004db94  jmp     loc_14004DC52
0x14004db99  movaps  xmm0, xmmword ptr [rdi]
0x14004db9c  movdqa  [rbp+var_30], xmm0
0x14004dba1  lea     rdx, [rbp+var_38]
0x14004dba5  lea     rcx, [rbp+var_30]
0x14004dba9  call    cs:__imp_GetEnrollmentAadResourceUrl
0x14004dbaf  test    eax, eax
0x14004dbb1  jns     short loc_14004DBC1
0x14004dbb3  mov     edx, eax
0x14004dbb5  lea     rcx, aFetchuseraadto_1; "FetchUserAadToken - GetEnrollmentAadRes"...
0x14004dbbc  jmp     loc_14004DC54
0x14004dbc1  mov     rdi, [rbp+hMem]
0x14004dbc5  test    rdi, rdi
0x14004dbc8  jz      short loc_14004DBE3
0x14004dbca  call    cs:__imp_GetLastError
0x14004dbd0  mov     ebx, eax
0x14004dbd2  mov     rcx, rdi; hMem
0x14004dbd5  call    cs:__imp_LocalFree
0x14004dbdb  mov     ecx, ebx; dwErrCode
0x14004dbdd  call    cs:__imp_SetLastError
0x14004dbe3  mov     [rbp+hMem], 0
0x14004dbeb  lea     rcx, [rbp+hMem]
0x14004dbef  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x14004dbf5  test    eax, eax
0x14004dbf7  jns     short loc_14004DC04
0x14004dbf9  mov     edx, eax
0x14004dbfb  lea     rcx, aFetchuseraadto_4; "FetchUserAadToken - DmGetActiveUserSid "...
0x14004dc02  jmp     short loc_14004DC54
0x14004dc04  mov     rcx, [rbp+hMem]
0x14004dc08  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x14004dc0e  test    eax, eax
0x14004dc10  jns     short loc_14004DC1D
0x14004dc12  mov     edx, eax
0x14004dc14  lea     rcx, aFetchuseraadto_6; "FetchUserAadToken - DmImpersonate faile"...
0x14004dc1b  jmp     short loc_14004DC54
0x14004dc1d  mov     [rbp+var_50], 1
0x14004dc24  mov     [rsp+80h+var_60], 0
0x14004dc2d  lea     r9, [rbp+var_40]
0x14004dc31  xor     r8d, r8d
0x14004dc34  mov     rdx, [rbp+var_38]
0x14004dc38  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x14004dc3f  call    cs:__imp_?DmGetAadUserToken@@YAJPEBG00PEAPEAGPEAH@Z; DmGetAadUserToken(ushort const *,ushort const *,ushort const *,ushort * *,int *)
0x14004dc45  mov     ebx, eax
0x14004dc47  test    eax, eax
0x14004dc49  jns     short loc_14004DC77
0x14004dc4b  lea     rcx, aFetchuseraadto_5; "FetchUserAadToken - DmGetAadUserToken f"...
0x14004dc52  mov     edx, ebx
0x14004dc54  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004dc59  nop
0x14004dc5a  lea     rcx, [rbp+var_20]
0x14004dc5e  call    wil__details__lambda_call__lambda_159a528f88c4b2c318bfd9979f3095ee______lambda_call__lambda_159a528f88c4b2c318bfd9979f3095ee___
0x14004dc63  nop
0x14004dc64  mov     rcx, [rbp+hMem]; hMem
0x14004dc68  test    rcx, rcx
0x14004dc6b  jz      short loc_14004DC73
0x14004dc6d  call    cs:__imp_LocalFree
0x14004dc73  xor     eax, eax
0x14004dc75  jmp     short loc_14004DCA1
0x14004dc77  mov     rax, [rbp+var_40]
0x14004dc7b  mov     [rsi], rax
0x14004dc7e  mov     [rbp+var_40], 0
0x14004dc86  lea     rcx, [rbp+var_20]
0x14004dc8a  call    wil__details__lambda_call__lambda_159a528f88c4b2c318bfd9979f3095ee______lambda_call__lambda_159a528f88c4b2c318bfd9979f3095ee___
0x14004dc8f  nop
0x14004dc90  mov     rcx, [rbp+hMem]; hMem
0x14004dc94  test    rcx, rcx
0x14004dc97  jz      short loc_14004DC9F
0x14004dc99  call    cs:__imp_LocalFree
0x14004dc9f  mov     eax, ebx
0x14004dca1  mov     rbx, [rsp+80h+arg_0]
0x14004dca9  add     rsp, 80h
0x14004dcb0  pop     rdi
0x14004dcb1  pop     rsi
0x14004dcb2  pop     rbp
0x14004dcb3  retn
```
