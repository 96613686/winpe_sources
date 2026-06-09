# JobExecution::PerformEnforcementPrechecks(_Job &)

- ea: `0x14000e6cc`
- end: `0x14000e9b5`
- name: `?PerformEnforcementPrechecks@JobExecution@@CAJAEAU_Job@@@Z`
- size: `745`
- prototype: `__int64 __fastcall(ULONG *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x14000dab4`

## callees

- `0x1400074d4`
- `0x14000e6cc`
- `0x14000e9bc`
- `0x14000faf4`
- `0x14000fc7c`
- `0x140012fe0`
- `0x140016da8`
- `0x140016ff0`
- `0x140018970`
- `0x140018b40`
- `0x14001a244`

## string_xrefs

- `0x14000e718`: `Enforcement precheck FAILED for job %1: App content is not ready.`
- `0x14000e77c`: `Enforcement precheck PASSED for job %1: App content is ready.`
- `0x14000e7c7`: `Enforcement precheck %1 for job %2: Enforcement thread %3 available.`
- `0x14000e837`: `Enforcement precheck %1 for job %2: The Windows Installer service %3 busy.`

## pseudocode

```c
__int64 __fastcall JobExecution::PerformEnforcementPrechecks(ULONG *a1)
{
  unsigned __int64 *v1; // r14
  int v3; // esi
  unsigned __int64 v4; // rax
  ULONG *v5; // rdx
  __int64 v6; // rdx
  int updated; // edi
  __int64 v8; // rdx
  ULONG *v9; // rdx
  const wchar_t *v10; // rdi
  const wchar_t *v11; // rbp
  const wchar_t *v12; // r9
  ULONG *v13; // r8
  const wchar_t *v14; // rdx
  const wchar_t *v15; // r15
  ULONG *v16; // rcx
  bool v17; // si
  const wchar_t *v18; // r9
  ULONG *v19; // r8
  const wchar_t *v20; // rdx
  bool v21; // si
  ULONG *v22; // r8
  const wchar_t *v23; // rdx
  wchar_t **v24; // rsi
  wchar_t *v25; // rcx
  int UserLogonStatus; // eax
  bool v27; // r12
  wchar_t *v28; // r9
  ULONG *v29; // r8
  __int64 v30; // rcx
  ULONG *v31; // r9
  bool v33; // [rsp+70h] [rbp+8h] BYREF

  v1 = (unsigned __int64 *)(a1 + 6);
  if ( a1[36] == 1 )
  {
    v3 = JobExecution::PerformValidation((const struct _Job *)a1);
    v4 = *v1;
    if ( v3 < 0 )
    {
      if ( v4 < 8 )
        v5 = a1;
      else
        v5 = *(ULONG **)a1;
      LogInfo(L"Enforcement precheck FAILED for job %1: App content is not ready.", v5);
      v6 = 25;
      if ( a1[80] >= 0xA )
        v6 = 30;
      updated = JobHelper::UpdateJobStatus(a1, v6, (unsigned int)v3);
      if ( updated >= 0 )
      {
        JobHelper::DeleteContent((__int64)a1, (__int64)(a1 + 8));
        LOBYTE(v8) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiHashMismatchFix>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_MsiHashMismatchFix>::GetImpl'::`2'::impl,
          v8);
        return (unsigned int)v3;
      }
      return (unsigned int)updated;
    }
    if ( v4 < 8 )
      v9 = a1;
    else
      v9 = *(ULONG **)a1;
    LogInfo(L"Enforcement precheck PASSED for job %1: App content is ready.", v9);
  }
  v10 = L"is not";
  v11 = L"is";
  v12 = L"is not";
  if ( !JobExecution::m_bIsEnforcementThreadRunning )
    v12 = L"is";
  if ( *v1 < 8 )
    v13 = a1;
  else
    v13 = *(ULONG **)a1;
  v14 = L"FAILED";
  v15 = L"PASSED";
  if ( !JobExecution::m_bIsEnforcementThreadRunning )
    v14 = L"PASSED";
  LogInfo(L"Enforcement precheck %1 for job %2: Enforcement thread %3 available.", v14, v13, v12);
  if ( JobExecution::m_bIsEnforcementThreadRunning )
  {
    v16 = a1;
LABEL_23:
    updated = JobHelper::UpdateJobStatus(v16, 55, 0);
    if ( updated >= 0 )
      return 1;
    return (unsigned int)updated;
  }
  v33 = 0;
  GetWindowsInstallerStatus(&v33);
  v17 = v33;
  v18 = L"is not";
  if ( !v33 )
    v18 = L"is";
  if ( *v1 < 8 )
    v19 = a1;
  else
    v19 = *(ULONG **)a1;
  v20 = L"PASSED";
  if ( !v33 )
    v20 = L"FAILED";
  LogInfo(L"Enforcement precheck %1 for job %2: The Windows Installer service %3 busy.", v20, v19, v18);
  v16 = a1;
  if ( !v17 )
    goto LABEL_23;
  v33 = 0;
  JobHelper::CheckJobIntentChanged((struct _Job *)a1, &v33);
  v21 = v33;
  if ( !v33 )
    v10 = L"is";
  if ( *v1 < 8 )
    v22 = a1;
  else
    v22 = *(ULONG **)a1;
  v23 = L"FAILED";
  if ( !v33 )
    v23 = L"PASSED";
  LogInfo(L"Enforcement precheck %1 for job %2: Job intent %3 the same.", v23, v22, v10);
  if ( v21 )
  {
    updated = JobExecution::RemoveFromJobsList((const struct _Job *)a1);
    if ( updated >= 0 )
      return (unsigned int)-2147467259;
  }
  else
  {
    updated = 0;
    if ( !a1[90] )
    {
      v24 = (wchar_t **)(a1 + 8);
      v33 = 0;
      if ( *((_QWORD *)a1 + 7) < 8u )
        v25 = (wchar_t *)(a1 + 8);
      else
        v25 = *v24;
      UserLogonStatus = GetUserLogonStatus(v25, a1[16], &v33);
      v27 = v33;
      if ( !v33 )
        v11 = L"is NOT";
      if ( *((_QWORD *)a1 + 7) < 8u )
        v28 = (wchar_t *)(a1 + 8);
      else
        v28 = *v24;
      if ( *v1 < 8 )
        v29 = a1;
      else
        v29 = *(ULONG **)a1;
      if ( !v33 )
        v15 = L"FAILED";
      LogInfo(
        L"Enforcement precheck %1 for job %2:  Managed user [%3] %4 present in session %5!d!. (0x%6!x!)",
        v15,
        v29,
        v28,
        v11,
        a1[16],
        UserLogonStatus);
      if ( !v27 )
      {
        if ( (byte_14002B9C1 & 0x40) != 0 )
        {
          if ( *v1 < 8 )
            v31 = a1;
          else
            v31 = *(ULONG **)a1;
          if ( *((_QWORD *)a1 + 7) >= 8u )
            v24 = (wchar_t **)*v24;
          McTemplateU0zz_EventWriteTransfer(v30, AppEnforcementRequiresUserSession, v24, v31);
        }
        updated = JobHelper::UpdateJobStatus(a1, 48, 2147943645LL);
        if ( updated >= 0 )
          return 1;
      }
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14000e6cc  mov     [rsp+arg_8], rbx
0x14000e6d1  mov     [rsp+arg_10], rbp
0x14000e6d6  push    rsi
0x14000e6d7  push    rdi
0x14000e6d8  push    r12
0x14000e6da  push    r14
0x14000e6dc  push    r15
0x14000e6de  sub     rsp, 40h
0x14000e6e2  mov     r12d, 1
0x14000e6e8  lea     r14, [rcx+18h]
0x14000e6ec  mov     rbx, rcx
0x14000e6ef  cmp     [rcx+90h], r12d
0x14000e6f6  jnz     loc_14000E788
0x14000e6fc  call    ?PerformValidation@JobExecution@@CAJAEBU_Job@@@Z; JobExecution::PerformValidation(_Job const &)
0x14000e701  mov     esi, eax
0x14000e703  mov     rax, [r14]
0x14000e706  test    esi, esi
0x14000e708  jns     short loc_14000E76E
0x14000e70a  cmp     rax, 8
0x14000e70e  jb      short loc_14000E715
0x14000e710  mov     rdx, [rbx]
0x14000e713  jmp     short loc_14000E718
0x14000e715  mov     rdx, rbx
0x14000e718  lea     rcx, aEnforcementPre_2; "Enforcement precheck FAILED for job %1:"...
0x14000e71f  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000e724  cmp     dword ptr [rbx+140h], 0Ah
0x14000e72b  mov     r8d, esi
0x14000e72e  mov     rcx, rbx
0x14000e731  mov     edx, 19h
0x14000e736  jb      short loc_14000E73D
0x14000e738  mov     edx, 1Eh
0x14000e73d  call    ?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z; JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)
0x14000e742  mov     edi, eax
0x14000e744  test    eax, eax
0x14000e746  js      loc_14000E99A
0x14000e74c  lea     rdx, [rbx+20h]
0x14000e750  mov     rcx, rbx
0x14000e753  call    ?DeleteContent@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; JobHelper::DeleteContent(std::wstring const &,std::wstring &)
0x14000e758  mov     dl, r12b
0x14000e75b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MsiHashMismatchFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MsiHashMismatchFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiHashMismatchFix> `wil::Feature<__WilFeatureTraits_Feature_MsiHashMismatchFix>::GetImpl(void)'::`2'::impl
0x14000e762  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_MsiHashMismatchFix@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiHashMismatchFix>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000e767  mov     edi, esi
0x14000e769  jmp     loc_14000E99A
0x14000e76e  cmp     rax, 8
0x14000e772  jb      short loc_14000E779
0x14000e774  mov     rdx, [rbx]
0x14000e777  jmp     short loc_14000E77C
0x14000e779  mov     rdx, rbx
0x14000e77c  lea     rcx, aEnforcementPre_3; "Enforcement precheck PASSED for job %1:"...
0x14000e783  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000e788  mov     al, cs:?m_bIsEnforcementThreadRunning@JobExecution@@0_NA; bool JobExecution::m_bIsEnforcementThreadRunning
0x14000e78e  lea     rdi, aIsNot_0; "is not"
0x14000e795  test    al, al
0x14000e797  lea     rbp, aIs; "is"
0x14000e79e  mov     r9, rdi
0x14000e7a1  cmovz   r9, rbp
0x14000e7a5  cmp     qword ptr [r14], 8
0x14000e7a9  jb      short loc_14000E7B0
0x14000e7ab  mov     r8, [rbx]
0x14000e7ae  jmp     short loc_14000E7B3
0x14000e7b0  mov     r8, rbx
0x14000e7b3  test    al, al
0x14000e7b5  lea     rdx, aFailed; "FAILED"
0x14000e7bc  lea     r15, aPassed; "PASSED"
0x14000e7c3  cmovz   rdx, r15
0x14000e7c7  lea     rcx, aEnforcementPre_0; "Enforcement precheck %1 for job %2: Enf"...
0x14000e7ce  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000e7d3  cmp     cs:?m_bIsEnforcementThreadRunning@JobExecution@@0_NA, 0; bool JobExecution::m_bIsEnforcementThreadRunning
0x14000e7da  jz      short loc_14000E7FE
0x14000e7dc  mov     rcx, rbx
0x14000e7df  mov     edx, 37h ; '7'
0x14000e7e4  xor     r8d, r8d
0x14000e7e7  call    ?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z; JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)
0x14000e7ec  mov     edi, eax
0x14000e7ee  test    eax, eax
0x14000e7f0  js      loc_14000E99A
0x14000e7f6  mov     edi, r12d
0x14000e7f9  jmp     loc_14000E99A
0x14000e7fe  lea     rcx, [rsp+68h+arg_0]; bool *
0x14000e803  mov     [rsp+68h+arg_0], 0
0x14000e808  call    ?GetWindowsInstallerStatus@@YAJAEA_N@Z; GetWindowsInstallerStatus(bool &)
0x14000e80d  mov     sil, [rsp+68h+arg_0]
0x14000e812  mov     r9, rdi
0x14000e815  test    sil, sil
0x14000e818  cmovz   r9, rbp
0x14000e81c  cmp     qword ptr [r14], 8
0x14000e820  jb      short loc_14000E827
0x14000e822  mov     r8, [rbx]
0x14000e825  jmp     short loc_14000E82A
0x14000e827  mov     r8, rbx
0x14000e82a  lea     r10, aFailed; "FAILED"
0x14000e831  test    sil, sil
0x14000e834  mov     rdx, r15
0x14000e837  lea     rcx, aEnforcementPre_1; "Enforcement precheck %1 for job %2: The"...
0x14000e83e  cmovz   rdx, r10
0x14000e842  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000e847  mov     rcx, rbx; struct _Job *
0x14000e84a  test    sil, sil
0x14000e84d  jz      short loc_14000E7DF
0x14000e84f  lea     rdx, [rsp+68h+arg_0]; bool *
0x14000e854  mov     [rsp+68h+arg_0], 0
0x14000e859  call    ?CheckJobIntentChanged@JobHelper@@SAJAEAU_Job@@AEA_N@Z; JobHelper::CheckJobIntentChanged(_Job &,bool &)
0x14000e85e  mov     sil, [rsp+68h+arg_0]
0x14000e863  test    sil, sil
0x14000e866  cmovz   rdi, rbp
0x14000e86a  cmp     qword ptr [r14], 8
0x14000e86e  jb      short loc_14000E875
0x14000e870  mov     r8, [rbx]
0x14000e873  jmp     short loc_14000E878
0x14000e875  mov     r8, rbx
0x14000e878  test    sil, sil
0x14000e87b  lea     rdx, aFailed; "FAILED"
0x14000e882  mov     r9, rdi
0x14000e885  lea     rcx, aEnforcementPre; "Enforcement precheck %1 for job %2: Job"...
0x14000e88c  cmovz   rdx, r15
0x14000e890  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000e895  test    sil, sil
0x14000e898  jz      short loc_14000E8B6
0x14000e89a  mov     rcx, rbx; struct _Job *
0x14000e89d  call    ?RemoveFromJobsList@JobExecution@@CAJAEBU_Job@@@Z; JobExecution::RemoveFromJobsList(_Job const &)
0x14000e8a2  mov     edi, eax
0x14000e8a4  test    eax, eax
0x14000e8a6  js      loc_14000E99A
0x14000e8ac  mov     edi, 80004005h
0x14000e8b1  jmp     loc_14000E99A
0x14000e8b6  xor     edi, edi
0x14000e8b8  cmp     [rbx+168h], edi
0x14000e8be  jnz     loc_14000E99A
0x14000e8c4  lea     rsi, [rbx+20h]
0x14000e8c8  mov     [rsp+68h+arg_0], dil
0x14000e8cd  cmp     qword ptr [rsi+18h], 8
0x14000e8d2  jb      short loc_14000E8D9
0x14000e8d4  mov     rcx, [rsi]
0x14000e8d7  jmp     short loc_14000E8DC
0x14000e8d9  mov     rcx, rsi; String2
0x14000e8dc  mov     edx, [rbx+40h]; SessionId
0x14000e8df  lea     r8, [rsp+68h+arg_0]; bool *
0x14000e8e4  call    ?GetUserLogonStatus@@YAJPEBGKAEA_N@Z; GetUserLogonStatus(ushort const *,ulong,bool &)
0x14000e8e9  mov     r12b, [rsp+68h+arg_0]
0x14000e8ee  lea     rdx, aIsNot; "is NOT"
0x14000e8f5  mov     ecx, [rbx+40h]
0x14000e8f8  test    r12b, r12b
0x14000e8fb  cmovz   rbp, rdx
0x14000e8ff  cmp     qword ptr [rsi+18h], 8
0x14000e904  jb      short loc_14000E90B
0x14000e906  mov     r9, [rsi]
0x14000e909  jmp     short loc_14000E90E
0x14000e90b  mov     r9, rsi
0x14000e90e  cmp     qword ptr [r14], 8
0x14000e912  jb      short loc_14000E919
0x14000e914  mov     r8, [rbx]
0x14000e917  jmp     short loc_14000E91C
0x14000e919  mov     r8, rbx
0x14000e91c  mov     [rsp+68h+var_38], eax
0x14000e920  lea     r10, aFailed; "FAILED"
0x14000e927  mov     [rsp+68h+var_40], ecx
0x14000e92b  test    r12b, r12b
0x14000e92e  lea     rcx, aEnforcementPre_5; "Enforcement precheck %1 for job %2:  Ma"...
0x14000e935  mov     [rsp+68h+var_48], rbp
0x14000e93a  cmovz   r15, r10
0x14000e93e  mov     rdx, r15
0x14000e941  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000e946  test    r12b, r12b
0x14000e949  jnz     short loc_14000E99A
0x14000e94b  test    cs:byte_14002B9C1, 40h
0x14000e952  jz      short loc_14000E97B
0x14000e954  cmp     qword ptr [r14], 8
0x14000e958  jb      short loc_14000E95F
0x14000e95a  mov     r9, [rbx]
0x14000e95d  jmp     short loc_14000E962
0x14000e95f  mov     r9, rbx
0x14000e962  cmp     qword ptr [rsi+18h], 8
0x14000e967  jb      short loc_14000E96C
0x14000e969  mov     rsi, [rsi]
0x14000e96c  mov     r8, rsi
0x14000e96f  lea     rdx, AppEnforcementRequiresUserSession
0x14000e976  call    McTemplateU0zz_EventWriteTransfer
0x14000e97b  mov     edx, 30h ; '0'
0x14000e980  mov     r8d, 800704DDh
0x14000e986  mov     rcx, rbx
0x14000e989  call    ?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z; JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)
0x14000e98e  mov     edi, eax
0x14000e990  test    eax, eax
0x14000e992  mov     eax, 1
0x14000e997  cmovns  edi, eax
0x14000e99a  lea     r11, [rsp+68h+var_28]
0x14000e99f  mov     eax, edi
0x14000e9a1  mov     rbx, [r11+38h]
0x14000e9a5  mov     rbp, [r11+40h]
0x14000e9a9  mov     rsp, r11
0x14000e9ac  pop     r15
0x14000e9ae  pop     r14
0x14000e9b0  pop     r12
0x14000e9b2  pop     rdi
0x14000e9b3  pop     rsi
0x14000e9b4  retn
```
