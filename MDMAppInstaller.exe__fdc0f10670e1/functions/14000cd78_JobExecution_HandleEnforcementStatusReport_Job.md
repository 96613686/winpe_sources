# JobExecution::HandleEnforcementStatusReport(_Job &)

- ea: `0x14000cd78`
- end: `0x14000d12b`
- name: `?HandleEnforcementStatusReport@JobExecution@@CAJAEAU_Job@@@Z`
- size: `947`
- prototype: `__int64 __fastcall(struct _Job *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000eae8`
- `0x14000eea4`

## callees

- `0x140006480`
- `0x14000740c`
- `0x1400074d4`
- `0x14000759c`
- `0x14000775c`
- `0x140009598`
- `0x14000cd78`
- `0x14000e09c`
- `0x14000e194`
- `0x14000faf4`
- `0x140012e98`
- `0x140012f38`
- `0x140016800`
- `0x140016da8`
- `0x140017a88`
- `0x140018d08`
- `0x14001a418`
- `0x14001a8d0`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x14000cf0a`
- `ADVAPI32!RevertToSelf` at `0x14000cf0a`

## string_xrefs

- `0x14000cf41`: `MSI installation failed for %1 from %2 with %3!d!`
- `0x14000d038`: `Unable to complete the OMADM notification.  Status report remains Unsent for job %1.`

## pseudocode

```c
__int64 __fastcall JobExecution::HandleEnforcementStatusReport(struct _Job *a1)
{
  int updated; // esi
  bool v3; // r14
  const wchar_t *v4; // r15
  const wchar_t *v5; // r12
  ULONG v6; // edi
  wchar_t *v7; // rcx
  int UserLogonStatus; // ecx
  const wchar_t *v9; // rax
  wchar_t **v10; // r9
  struct _Job *v11; // r8
  const wchar_t *v12; // rdx
  bool v13; // di
  struct _Job *v14; // r8
  int v15; // eax
  bool v16; // r14
  int v17; // r9d
  char *v18; // rdi
  char *v19; // r8
  struct _Job *v20; // rdx
  int v21; // r8d
  char *v22; // rdx
  _QWORD *v23; // rcx
  int v24; // eax
  int v25; // edx
  int v26; // ecx
  const unsigned __int16 *v27; // rcx
  char v28; // al
  __int64 v29; // rdx
  __int64 v30; // rcx
  struct _Job *v31; // rdx
  struct _Job *v32; // rdx
  struct _Job *v33; // rdx
  bool v35; // [rsp+40h] [rbp-19h] BYREF
  bool v36; // [rsp+41h] [rbp-18h] BYREF
  unsigned __int16 *v37[3]; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int64 v38; // [rsp+60h] [rbp+7h]
  wchar_t *String2[3]; // [rsp+68h] [rbp+Fh] BYREF
  unsigned __int64 v40; // [rsp+80h] [rbp+27h]

  v40 = 7;
  String2[2] = 0;
  LOWORD(String2[0]) = 0;
  updated = 0;
  v3 = 0;
  v35 = 0;
  v4 = L"is";
  v5 = L"PASSED";
  if ( !*((_DWORD *)a1 + 90) )
  {
    v6 = *((_DWORD *)a1 + 16);
    std::wstring::operator=((__int64)String2, (__int64)a1 + 32);
    v7 = (wchar_t *)String2;
    if ( v40 >= 8 )
      v7 = String2[0];
    UserLogonStatus = GetUserLogonStatus(v7, v6, &v35);
    v9 = L"is";
    v3 = v35;
    if ( !v35 )
      v9 = L"is NOT";
    v10 = String2;
    if ( v40 >= 8 )
      v10 = (wchar_t **)String2[0];
    if ( *((_QWORD *)a1 + 3) < 8u )
      v11 = a1;
    else
      v11 = *(struct _Job **)a1;
    v12 = L"PASSED";
    if ( !v35 )
      v12 = L"FAILED";
    LogInfo(
      L"Status reporting precheck %1 for Job %2: Managed user [%3] %4 present in session %5!d!. (0x%6!x!)",
      v12,
      v11,
      v10,
      v9,
      v6,
      UserLogonStatus);
  }
  v35 = 0;
  GetNetworkConnectionStatus(&v35);
  v13 = v35;
  if ( !v35 )
    v4 = L"is NOT";
  if ( *((_QWORD *)a1 + 3) < 8u )
    v14 = a1;
  else
    v14 = *(struct _Job **)a1;
  if ( !v35 )
    v5 = L"FAILED";
  LogInfo(L"Status reporting precheck %1 for Job %2: A network connection %3 available.", v5, v14, v4);
  if ( !*((_DWORD *)a1 + 38) && (v3 || *((_DWORD *)a1 + 90) == 1) && v13 )
  {
    v38 = 7;
    v37[2] = 0;
    LOWORD(v37[0]) = 0;
    v36 = 0;
    v35 = 0;
    v15 = IsRunningInSystemContext(&v35);
    v16 = v35;
    if ( v15 >= 0 && !v35 )
      RevertToSelf();
    v17 = *((_DWORD *)a1 + 40);
    v18 = (char *)a1 + 392;
    if ( v17 )
    {
      if ( *((_QWORD *)a1 + 52) < 8u )
        v19 = (char *)a1 + 392;
      else
        v19 = *(char **)v18;
      if ( *((_QWORD *)a1 + 3) < 8u )
        v20 = a1;
      else
        v20 = *(struct _Job **)a1;
      LogTelemetryError(L"MSI installation failed for %1 from %2 with %3!d!", v20, v19);
      v21 = *((_DWORD *)a1 + 40);
    }
    else
    {
      v21 = 0;
    }
    if ( *((_QWORD *)a1 + 52) < 8u )
      LODWORD(v22) = (_DWORD)a1 + 392;
    else
      v22 = *(char **)v18;
    v23 = (_QWORD *)((char *)a1 + 424);
    if ( *((_QWORD *)a1 + 56) >= 8u )
      v23 = (_QWORD *)*v23;
    LOBYTE(v17) = !v16;
    v24 = JobExecution::OmaDmMsiInitiateSession((_DWORD)v23, (_DWORD)v22, v21, v17, (__int64)a1 + 72, (__int64)v37);
    if ( v24 < 0 )
    {
      if ( (byte_14002B9C1 & 0x40) != 0 )
      {
        if ( *((_QWORD *)a1 + 52) >= 8u )
          v18 = *(char **)v18;
        McTemplateU0zdd_EventWriteTransfer(v26, v25, (_DWORD)v18, *((_DWORD *)a1 + 40), v24);
      }
      updated = JobHelper::UpdateJobStatusReport(a1);
      if ( updated < 0 )
        goto LABEL_51;
      if ( *((_QWORD *)a1 + 3) < 8u )
        v32 = a1;
      else
        v32 = *(struct _Job **)a1;
      LogWarn(L"OMADM client is in a bad state.  Marking job status report as Sent for job %1.", v32);
    }
    else
    {
      v27 = (const unsigned __int16 *)v37;
      if ( v38 >= 8 )
        v27 = v37[0];
      v28 = JobExecution::OmaDmMsiConfirmSession(v27, &v36);
      if ( v36 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
        {
          if ( *((_QWORD *)a1 + 52) >= 8u )
            v18 = *(char **)v18;
          McTemplateU0zd_EventWriteTransfer(v30, v29, v18, *((unsigned int *)a1 + 40));
        }
        updated = JobHelper::UpdateJobStatusReport(a1);
        if ( updated < 0 )
          goto LABEL_51;
      }
      else
      {
        if ( (byte_14002B9C1 & 0x40) != 0 )
        {
          if ( *((_QWORD *)a1 + 52) >= 8u )
            v18 = *(char **)v18;
          McTemplateU0zdd_EventWriteTransfer(v30, v29, (_DWORD)v18, *((_DWORD *)a1 + 40), v28);
        }
        if ( *((_QWORD *)a1 + 3) < 8u )
          v31 = a1;
        else
          v31 = *(struct _Job **)a1;
        LogError(L"Unable to complete the OMADM notification.  Status report remains Unsent for job %1.", v31);
      }
    }
    if ( *((_DWORD *)a1 + 36) == 2 )
    {
      updated = JobHelper::DeleteJob(a1, (__int64)a1 + 32);
      if ( updated >= 0 )
        updated = JobExecution::RemoveFromJobsList(a1);
    }
LABEL_51:
    std::wstring::_Tidy(v37, 1, 0);
    goto LABEL_76;
  }
  if ( *((_QWORD *)a1 + 3) < 8u )
    v33 = a1;
  else
    v33 = *(struct _Job **)a1;
  LogInfo(L"Status reporting prechecks not satisfied for job %1 (hr=0x%2!x!).", v33, 0);
  *((_DWORD *)a1 + 39) = 30;
LABEL_76:
  std::wstring::_Tidy(String2, 1, 0);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14000cd78  mov     [rsp-8+arg_8], rbx
0x14000cd7d  mov     [rsp-8+arg_10], rsi
0x14000cd82  push    rbp
0x14000cd83  push    rdi
0x14000cd84  push    r12
0x14000cd86  push    r14
0x14000cd88  push    r15
0x14000cd8a  lea     rbp, [rsp-37h]
0x14000cd8f  sub     rsp, 90h
0x14000cd96  mov     rax, cs:__security_cookie
0x14000cd9d  xor     rax, rsp
0x14000cda0  mov     [rbp+57h+var_28], rax
0x14000cda4  mov     rbx, rcx
0x14000cda7  mov     [rbp+57h+var_30], 7
0x14000cdaf  mov     [rbp+57h+var_38], 0
0x14000cdb7  xor     eax, eax
0x14000cdb9  mov     word ptr [rbp+57h+String2], ax
0x14000cdbd  xor     esi, esi
0x14000cdbf  xor     r14b, r14b
0x14000cdc2  mov     [rbp+57h+var_70], r14b
0x14000cdc6  lea     r15, aIs; "is"
0x14000cdcd  lea     r12, aPassed; "PASSED"
0x14000cdd4  cmp     [rcx+168h], esi
0x14000cdda  jnz     loc_14000CE67
0x14000cde0  mov     edi, [rcx+40h]
0x14000cde3  lea     rdx, [rcx+20h]
0x14000cde7  lea     rcx, [rbp+57h+String2]
0x14000cdeb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14000cdf0  lea     rcx, [rbp+57h+String2]
0x14000cdf4  cmp     [rbp+57h+var_30], 8
0x14000cdf9  cmovnb  rcx, [rbp+57h+String2]; String2
0x14000cdfe  lea     r8, [rbp+57h+var_70]; bool *
0x14000ce02  mov     edx, edi; SessionId
0x14000ce04  call    ?GetUserLogonStatus@@YAJPEBGKAEA_N@Z; GetUserLogonStatus(ushort const *,ulong,bool &)
0x14000ce09  mov     ecx, eax
0x14000ce0b  mov     rax, r15
0x14000ce0e  mov     r14b, [rbp+57h+var_70]
0x14000ce12  test    r14b, r14b
0x14000ce15  lea     rdx, aIsNot; "is NOT"
0x14000ce1c  cmovz   rax, rdx
0x14000ce20  lea     r9, [rbp+57h+String2]
0x14000ce24  cmp     [rbp+57h+var_30], 8
0x14000ce29  cmovnb  r9, [rbp+57h+String2]
0x14000ce2e  cmp     qword ptr [rbx+18h], 8
0x14000ce33  jb      short loc_14000CE3A
0x14000ce35  mov     r8, [rbx]
0x14000ce38  jmp     short loc_14000CE3D
0x14000ce3a  mov     r8, rbx
0x14000ce3d  mov     rdx, r12
0x14000ce40  test    r14b, r14b
0x14000ce43  lea     r10, aFailed; "FAILED"
0x14000ce4a  cmovz   rdx, r10
0x14000ce4e  mov     [rsp+0B0h+var_80], ecx
0x14000ce52  mov     dword ptr [rsp+0B0h+var_88], edi
0x14000ce56  mov     [rsp+0B0h+var_90], rax
0x14000ce5b  lea     rcx, aStatusReportin; "Status reporting precheck %1 for Job %2"...
0x14000ce62  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000ce67  mov     [rbp+57h+var_70], sil
0x14000ce6b  lea     rcx, [rbp+57h+var_70]; bool *
0x14000ce6f  call    ?GetNetworkConnectionStatus@@YAJAEA_N@Z; GetNetworkConnectionStatus(bool &)
0x14000ce74  mov     dil, [rbp+57h+var_70]
0x14000ce78  test    dil, dil
0x14000ce7b  lea     rax, aIsNot; "is NOT"
0x14000ce82  cmovz   r15, rax
0x14000ce86  cmp     qword ptr [rbx+18h], 8
0x14000ce8b  jb      short loc_14000CE92
0x14000ce8d  mov     r8, [rbx]
0x14000ce90  jmp     short loc_14000CE95
0x14000ce92  mov     r8, rbx
0x14000ce95  test    dil, dil
0x14000ce98  lea     rax, aFailed; "FAILED"
0x14000ce9f  cmovz   r12, rax
0x14000cea3  mov     r9, r15
0x14000cea6  mov     rdx, r12
0x14000cea9  lea     rcx, aStatusReportin_0; "Status reporting precheck %1 for Job %2"...
0x14000ceb0  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000ceb5  cmp     [rbx+98h], esi
0x14000cebb  jnz     loc_14000D0CB
0x14000cec1  test    r14b, r14b
0x14000cec4  jnz     short loc_14000CED3
0x14000cec6  cmp     dword ptr [rbx+168h], 1
0x14000cecd  jnz     loc_14000D0CB
0x14000ced3  test    dil, dil
0x14000ced6  jz      loc_14000D0CB
0x14000cedc  mov     [rbp+57h+var_50], 7
0x14000cee4  mov     [rbp+57h+var_58], rsi
0x14000cee8  xor     eax, eax
0x14000ceea  mov     word ptr [rbp+57h+var_68], ax
0x14000ceee  mov     [rbp+57h+var_6F], al
0x14000cef1  mov     [rbp+57h+var_70], al
0x14000cef4  lea     rcx, [rbp+57h+var_70]; bool *
0x14000cef8  call    ?IsRunningInSystemContext@@YAJAEA_N@Z; IsRunningInSystemContext(bool &)
0x14000cefd  mov     r14b, [rbp+57h+var_70]
0x14000cf01  test    eax, eax
0x14000cf03  js      short loc_14000CF10
0x14000cf05  test    r14b, r14b
0x14000cf08  jnz     short loc_14000CF10
0x14000cf0a  call    cs:__imp_RevertToSelf
0x14000cf10  mov     r9d, [rbx+0A0h]
0x14000cf17  lea     rdi, [rbx+188h]
0x14000cf1e  test    r9d, r9d
0x14000cf21  jz      short loc_14000CF56
0x14000cf23  cmp     qword ptr [rdi+18h], 8
0x14000cf28  jb      short loc_14000CF2F
0x14000cf2a  mov     r8, [rdi]
0x14000cf2d  jmp     short loc_14000CF32
0x14000cf2f  mov     r8, rdi
0x14000cf32  cmp     qword ptr [rbx+18h], 8
0x14000cf37  jb      short loc_14000CF3E
0x14000cf39  mov     rdx, [rbx]
0x14000cf3c  jmp     short loc_14000CF41
0x14000cf3e  mov     rdx, rbx
0x14000cf41  lea     rcx, aMsiInstallatio; "MSI installation failed for %1 from %2 "...
0x14000cf48  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14000cf4d  mov     r8d, [rbx+0A0h]
0x14000cf54  jmp     short loc_14000CF59
0x14000cf56  xor     r8d, r8d
0x14000cf59  test    r14b, r14b
0x14000cf5c  setz    r9b
0x14000cf60  cmp     qword ptr [rdi+18h], 8
0x14000cf65  jb      short loc_14000CF6C
0x14000cf67  mov     rdx, [rdi]
0x14000cf6a  jmp     short loc_14000CF6F
0x14000cf6c  mov     rdx, rdi
0x14000cf6f  lea     rcx, [rbx+1A8h]
0x14000cf76  cmp     qword ptr [rcx+18h], 8
0x14000cf7b  jb      short loc_14000CF80
0x14000cf7d  mov     rcx, [rcx]
0x14000cf80  lea     rax, [rbx+48h]
0x14000cf84  lea     r10, [rbp+57h+var_68]
0x14000cf88  mov     [rsp+0B0h+var_88], r10
0x14000cf8d  mov     [rsp+0B0h+var_90], rax
0x14000cf92  call    ?OmaDmMsiInitiateSession@JobExecution@@CAJPEBG0H_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; JobExecution::OmaDmMsiInitiateSession(ushort const *,ushort const *,int,bool,std::wstring &,std::wstring &)
0x14000cf97  test    eax, eax
0x14000cf99  js      loc_14000D046
0x14000cf9f  lea     rcx, [rbp+57h+var_68]
0x14000cfa3  cmp     [rbp+57h+var_50], 8
0x14000cfa8  cmovnb  rcx, [rbp+57h+var_68]; unsigned __int16 *
0x14000cfad  lea     rdx, [rbp+57h+var_6F]; bool *
0x14000cfb1  call    ?OmaDmMsiConfirmSession@JobExecution@@CAJPEBGAEA_N@Z; JobExecution::OmaDmMsiConfirmSession(ushort const *,bool &)
0x14000cfb6  cmp     [rbp+57h+var_6F], 0
0x14000cfba  jz      short loc_14000D003
0x14000cfbc  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x14000cfc3  jz      short loc_14000CFDE
0x14000cfc5  cmp     qword ptr [rdi+18h], 8
0x14000cfca  jb      short loc_14000CFCF
0x14000cfcc  mov     rdi, [rdi]
0x14000cfcf  mov     r9d, [rbx+0A0h]
0x14000cfd6  mov     r8, rdi
0x14000cfd9  call    McTemplateU0zd_EventWriteTransfer
0x14000cfde  mov     rcx, rbx
0x14000cfe1  call    ?UpdateJobStatusReport@JobHelper@@SAJAEAU_Job@@W4JobStatusReport@@@Z; JobHelper::UpdateJobStatusReport(_Job &,JobStatusReport)
0x14000cfe6  mov     esi, eax
0x14000cfe8  test    eax, eax
0x14000cfea  jns     loc_14000D099
0x14000cff0  xor     r8d, r8d
0x14000cff3  mov     dl, 1
0x14000cff5  lea     rcx, [rbp+57h+var_68]
0x14000cff9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000cffe  jmp     loc_14000D0F3
0x14000d003  test    cs:byte_14002B9C1, 40h
0x14000d00a  jz      short loc_14000D029
0x14000d00c  cmp     qword ptr [rdi+18h], 8
0x14000d011  jb      short loc_14000D016
0x14000d013  mov     rdi, [rdi]
0x14000d016  mov     dword ptr [rsp+0B0h+var_90], eax
0x14000d01a  mov     r9d, [rbx+0A0h]
0x14000d021  mov     r8, rdi
0x14000d024  call    McTemplateU0zdd_EventWriteTransfer
0x14000d029  cmp     qword ptr [rbx+18h], 8
0x14000d02e  jb      short loc_14000D035
0x14000d030  mov     rdx, [rbx]
0x14000d033  jmp     short loc_14000D038
0x14000d035  mov     rdx, rbx
0x14000d038  lea     rcx, aUnableToComple; "Unable to complete the OMADM notificati"...
0x14000d03f  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000d044  jmp     short loc_14000D099
0x14000d046  test    cs:byte_14002B9C1, 40h
0x14000d04d  jz      short loc_14000D06C
0x14000d04f  cmp     qword ptr [rdi+18h], 8
0x14000d054  jb      short loc_14000D059
0x14000d056  mov     rdi, [rdi]
0x14000d059  mov     dword ptr [rsp+0B0h+var_90], eax
0x14000d05d  mov     r9d, [rbx+0A0h]
0x14000d064  mov     r8, rdi
0x14000d067  call    McTemplateU0zdd_EventWriteTransfer
0x14000d06c  mov     rcx, rbx
0x14000d06f  call    ?UpdateJobStatusReport@JobHelper@@SAJAEAU_Job@@W4JobStatusReport@@@Z; JobHelper::UpdateJobStatusReport(_Job &,JobStatusReport)
0x14000d074  mov     esi, eax
0x14000d076  test    eax, eax
0x14000d078  js      loc_14000CFF0
0x14000d07e  cmp     qword ptr [rbx+18h], 8
0x14000d083  jb      short loc_14000D08A
0x14000d085  mov     rdx, [rbx]
0x14000d088  jmp     short loc_14000D08D
0x14000d08a  mov     rdx, rbx
0x14000d08d  lea     rcx, aOmadmClientIsI; "OMADM client is in a bad state.  Markin"...
0x14000d094  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x14000d099  cmp     dword ptr [rbx+90h], 2
0x14000d0a0  jnz     loc_14000CFF0
0x14000d0a6  lea     rdx, [rbx+20h]
0x14000d0aa  mov     rcx, rbx
0x14000d0ad  call    ?DeleteJob@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; JobHelper::DeleteJob(std::wstring const &,std::wstring &)
0x14000d0b2  mov     esi, eax
0x14000d0b4  test    eax, eax
0x14000d0b6  js      loc_14000CFF0
0x14000d0bc  mov     rcx, rbx; struct _Job *
0x14000d0bf  call    ?RemoveFromJobsList@JobExecution@@CAJAEBU_Job@@@Z; JobExecution::RemoveFromJobsList(_Job const &)
0x14000d0c4  mov     esi, eax
0x14000d0c6  jmp     loc_14000CFF0
0x14000d0cb  cmp     qword ptr [rbx+18h], 8
0x14000d0d0  jb      short loc_14000D0D7
0x14000d0d2  mov     rdx, [rbx]
0x14000d0d5  jmp     short loc_14000D0DA
0x14000d0d7  mov     rdx, rbx
0x14000d0da  xor     r8d, r8d
0x14000d0dd  lea     rcx, aStatusReportin_1; "Status reporting prechecks not satisfie"...
0x14000d0e4  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000d0e9  mov     dword ptr [rbx+9Ch], 1Eh
0x14000d0f3  xor     r8d, r8d
0x14000d0f6  mov     dl, 1
0x14000d0f8  lea     rcx, [rbp+57h+String2]
0x14000d0fc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000d101  mov     eax, esi
0x14000d103  mov     rcx, [rbp+57h+var_28]
0x14000d107  xor     rcx, rsp; StackCookie
0x14000d10a  call    __security_check_cookie
0x14000d10f  lea     r11, [rsp+0B0h+var_20]
0x14000d117  mov     rbx, [r11+38h]
0x14000d11b  mov     rsi, [r11+40h]
0x14000d11f  mov     rsp, r11
0x14000d122  pop     r15
0x14000d124  pop     r14
0x14000d126  pop     r12
0x14000d128  pop     rdi
0x14000d129  pop     rbp
0x14000d12a  retn
```
