# JobExecution::HandleJobCheckEnforcement(_Job &)

- ea: `0x14000d470`
- end: `0x14000d890`
- name: `?HandleJobCheckEnforcement@JobExecution@@CAJAEAU_Job@@@Z`
- size: `1056`
- prototype: `__int64 __fastcall(struct _Job *)`
- caller_count: `2`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000eae8`
- `0x14000eea4`

## callees

- `0x140003674`
- `0x1400036ac`
- `0x140006480`
- `0x140006604`
- `0x1400068c8`
- `0x14000740c`
- `0x1400074d4`
- `0x140008a50`
- `0x14000d470`
- `0x140012328`
- `0x14001273c`
- `0x1400177bc`
- `0x140018b40`
- `0x140019fcc`
- `0x14001a0c4`
- `0x14001a244`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000d870`
- `KERNEL32!LeaveCriticalSection` at `0x14000d870`
- `KERNEL32!EnterCriticalSection` at `0x14000d4a0`
- `KERNEL32!EnterCriticalSection` at `0x14000d4a0`

## string_xrefs

- `0x14000d66a`: `Completed enforcement for Job %1.  A system restart is needed to complete the installation.`
- `0x14000d54e`: `Processing Job %1.  Another MSI installation is in progress.`
- `0x14000d571`: `Processing Job %1. MSIExec failed to open the MSI package. Initiating content download.`
- `0x14000d7c1`: `Processing job %1.  Found app installed without any enforcement results.`
- `0x14000d85d`: `The enforcement thread is still running. Waiting on result.`

## pseudocode

```c
__int64 __fastcall JobExecution::HandleJobCheckEnforcement(struct _Job *a1)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // r8
  char v5; // di
  unsigned int v6; // edx
  int updated; // ebx
  struct _Job *v8; // rdx
  __int64 v9; // rcx
  struct _Job *v10; // rdx
  struct _Job *v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  struct _Job *v14; // rdx
  struct _Job *v15; // rdx
  struct _Job *v16; // rdx
  struct _Job *v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  char v20; // bl
  __int64 v21; // rdx
  struct _Job *v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rdx
  struct _Job *v27; // rdx
  struct _Job *v28; // rdx
  __int64 v30; // [rsp+28h] [rbp-61h] BYREF
  _WORD v31[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v32; // [rsp+40h] [rbp-49h]
  __int64 v33; // [rsp+48h] [rbp-41h]
  _BYTE v34[32]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v35[32]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v36[32]; // [rsp+90h] [rbp+7h] BYREF

  EnterCriticalSection(&JobExecution::m_critSec);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::find(
    v2,
    &v30,
    a1);
  if ( v30 == JobExecution::m_mapEnforcementCompleteJobList )
  {
    if ( JobExecution::m_bIsEnforcementThreadRunning )
    {
      updated = 0;
      LogInfo(L"The enforcement thread is still running. Waiting on result.");
      goto LABEL_77;
    }
    v33 = 7;
    v32 = 0;
    v31[0] = 0;
    if ( *((_BYTE *)a1 + 388) )
    {
      v19 = std::wstring::wstring(v36, (char *)a1 + 104);
      v20 = 1;
    }
    else
    {
      v19 = std::wstring::wstring(v35, &word_14001E5B4);
      v20 = 2;
    }
    std::wstring::wstring(v34, v19);
    if ( (v20 & 2) != 0 )
    {
      v20 &= ~2u;
      LOBYTE(v21) = 1;
      std::wstring::_Tidy(v35, v21, 0);
    }
    if ( (v20 & 1) != 0 )
    {
      LOBYTE(v21) = 1;
      std::wstring::_Tidy(v36, v21, 0);
    }
    if ( *((_DWORD *)a1 + 36) == 1 && (unsigned __int8)IsMSIAppInstalled((LPCWSTR)a1 + 36) )
    {
      if ( *((_QWORD *)a1 + 3) < 8u )
        v22 = a1;
      else
        v22 = *(struct _Job **)a1;
      LogInfo(L"Processing job %1.  Found app installed without any enforcement results.", v22);
      v23 = 70;
    }
    else
    {
      if ( (unsigned int)(*((_DWORD *)a1 + 94) + 1) > *((_DWORD *)a1 + 95) )
      {
        if ( *((_QWORD *)a1 + 3) < 8u )
          v27 = a1;
        else
          v27 = *(struct _Job **)a1;
        LogError(L"Processing Job %1. Max number of enforcement retries have been reached.", v27);
        v23 = 60;
        v24 = 2147549183LL;
        goto LABEL_66;
      }
      if ( *((_QWORD *)a1 + 3) < 8u )
        v28 = a1;
      else
        v28 = *(struct _Job **)a1;
      LogError(L"Processing Job %1. No enforcement results found.  Will retry enforcement.", v28);
      v23 = 55;
    }
    v24 = 0;
LABEL_66:
    updated = JobHelper::UpdateJobStatus(a1, v23, v24);
    LOBYTE(v25) = 1;
    std::wstring::_Tidy(v34, v25, 0);
    LOBYTE(v26) = 1;
    std::wstring::_Tidy(v31, v26, 0);
    goto LABEL_77;
  }
  v3 = *(_DWORD *)(v30 + 64);
  if ( (v3 & 0x80000000) == 0 )
  {
    if ( *((_QWORD *)a1 + 3) < 8u )
      v17 = a1;
    else
      v17 = *(struct _Job **)a1;
    LogInfo(L"Enforcement for job %1 succeeded.", v17);
    v4 = v3;
    goto LABEL_47;
  }
  if ( v3 == -2147021886 || v3 == -2147023255 )
  {
    updated = JobHelper::UpdateJobStatus(a1, 70, 0);
    if ( updated < 0 )
      goto LABEL_77;
    v5 = 1;
    if ( *((_QWORD *)a1 + 3) < 8u )
      v16 = a1;
    else
      v16 = *(struct _Job **)a1;
    LogInfo(L"Completed enforcement for Job %1.  A system restart is needed to complete the installation.", v16);
    goto LABEL_49;
  }
  if ( v3 == -2147023189 )
  {
    v4 = 0;
LABEL_47:
    updated = JobHelper::UpdateJobStatus(a1, 70, v4);
    if ( updated < 0 )
      goto LABEL_77;
    v5 = 1;
    goto LABEL_49;
  }
  v5 = 0;
  if ( v3 != -2147023278 )
  {
    if ( v3 == -2147023277 )
    {
      if ( *((_QWORD *)a1 + 3) < 8u )
        v10 = a1;
      else
        v10 = *(struct _Job **)a1;
      LogInfo(L"Processing Job %1. MSIExec failed to open the MSI package. Initiating content download.", v10);
      if ( (unsigned int)(*((_DWORD *)a1 + 94) + 1) <= *((_DWORD *)a1 + 95) )
      {
        v12 = 10;
      }
      else
      {
        if ( *((_QWORD *)a1 + 3) < 8u )
          v11 = a1;
        else
          v11 = *(struct _Job **)a1;
        LogError(L"Processing Job %1. Max number of enforcement retries have been reached.", v11);
        v12 = 60;
      }
      v13 = 2147944019LL;
    }
    else
    {
      if ( *((_QWORD *)a1 + 3) < 8u )
        v14 = a1;
      else
        v14 = *(struct _Job **)a1;
      LogError(L"Enforcement failed for job %1. Error 0x%2!x!", v14, v3);
      if ( (unsigned int)(*((_DWORD *)a1 + 94) + 1) <= *((_DWORD *)a1 + 95) )
      {
        updated = JobHelper::UpdateJobStatus(a1, 55, v3);
        if ( updated < 0 )
          goto LABEL_77;
        goto LABEL_49;
      }
      if ( *((_QWORD *)a1 + 3) < 8u )
        v15 = a1;
      else
        v15 = *(struct _Job **)a1;
      LogError(L"Processing Job %1. Max number of enforcement retries have been reached.", v15);
      v13 = v3;
      v12 = 60;
    }
    updated = JobHelper::UpdateJobStatus(a1, v12, v13);
    if ( updated < 0 )
      goto LABEL_77;
    goto LABEL_49;
  }
  v6 = *((_DWORD *)a1 + 94);
  *((_DWORD *)a1 + 94) = v6 - 1;
  updated = JobHelper::UpdateEnforcementRetryIndex(a1, v6);
  if ( updated < 0 )
    goto LABEL_77;
  updated = JobHelper::UpdateJobStatus(a1, 55, 2147944018LL);
  if ( updated < 0 )
    goto LABEL_77;
  if ( *((_QWORD *)a1 + 3) < 8u )
    v8 = a1;
  else
    v8 = *(struct _Job **)a1;
  LogInfo(L"Processing Job %1.  Another MSI installation is in progress.", v8);
LABEL_49:
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::erase(
    v9,
    a1);
  if ( v5 )
  {
    JobHelper::DeleteContent((__int64)a1, (__int64)a1 + 32);
    v18 = std::char_traits<unsigned short>::length(&word_14001E5B4);
    std::wstring::assign((char *)a1 + 200, &word_14001E5B4, v18);
    updated = JobHelper::UpdateDownloadLocation(a1, (__int64)a1 + 32, (const unsigned __int16 *)a1 + 100);
  }
LABEL_77:
  LeaveCriticalSection(&JobExecution::m_critSec);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14000d470  push    rbp
0x14000d472  push    rbx
0x14000d473  push    rsi
0x14000d474  push    rdi
0x14000d475  lea     rbp, [rsp-3Fh]
0x14000d47a  sub     rsp, 0C8h
0x14000d481  mov     rax, cs:__security_cookie
0x14000d488  xor     rax, rsp
0x14000d48b  mov     [rbp+57h+var_30], rax
0x14000d48f  mov     rsi, rcx
0x14000d492  mov     [rbp+57h+var_C0], 0
0x14000d499  lea     rcx, ?m_critSec@JobExecution@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14000d4a0  call    cs:__imp_EnterCriticalSection
0x14000d4a6  mov     r8, rsi
0x14000d4a9  lea     rdx, [rbp+57h+var_B8]
0x14000d4ad  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::find(std::wstring const &)
0x14000d4b2  mov     rax, [rbp+57h+var_B8]
0x14000d4b6  cmp     rax, cs:?m_mapEnforcementCompleteJobList@JobExecution@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@A; std::map<std::wstring,ulong> JobExecution::m_mapEnforcementCompleteJobList
0x14000d4bd  jz      loc_14000D708
0x14000d4c3  mov     ebx, [rax+40h]
0x14000d4c6  test    ebx, ebx
0x14000d4c8  jns     loc_14000D678
0x14000d4ce  cmp     ebx, 80070BC2h
0x14000d4d4  jz      loc_14000D63F
0x14000d4da  cmp     ebx, 80070669h
0x14000d4e0  jz      loc_14000D63F
0x14000d4e6  cmp     ebx, 800706ABh
0x14000d4ec  jnz     short loc_14000D4F6
0x14000d4ee  xor     r8d, r8d
0x14000d4f1  jmp     loc_14000D696
0x14000d4f6  xor     dil, dil
0x14000d4f9  cmp     ebx, 80070652h
0x14000d4ff  jnz     short loc_14000D55A
0x14000d501  mov     edx, [rsi+178h]; unsigned int
0x14000d507  lea     eax, [rdx-1]
0x14000d50a  mov     [rsi+178h], eax
0x14000d510  mov     rcx, rsi; struct _Job *
0x14000d513  call    ?UpdateEnforcementRetryIndex@JobHelper@@SAJAEAU_Job@@K@Z; JobHelper::UpdateEnforcementRetryIndex(_Job &,ulong)
0x14000d518  mov     ebx, eax
0x14000d51a  test    eax, eax
0x14000d51c  js      loc_14000D869
0x14000d522  mov     edx, 37h ; '7'
0x14000d527  mov     r8d, 80070652h
0x14000d52d  mov     rcx, rsi
0x14000d530  call    ?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z; JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)
0x14000d535  mov     ebx, eax
0x14000d537  test    eax, eax
0x14000d539  js      loc_14000D869
0x14000d53f  cmp     qword ptr [rsi+18h], 8
0x14000d544  jb      short loc_14000D54B
0x14000d546  mov     rdx, [rsi]
0x14000d549  jmp     short loc_14000D54E
0x14000d54b  mov     rdx, rsi
0x14000d54e  lea     rcx, aProcessingJob1; "Processing Job %1.  Another MSI install"...
0x14000d555  jmp     loc_14000D671
0x14000d55a  cmp     ebx, 80070653h
0x14000d560  jnz     short loc_14000D5D1
0x14000d562  cmp     qword ptr [rsi+18h], 8
0x14000d567  jb      short loc_14000D56E
0x14000d569  mov     rdx, [rsi]
0x14000d56c  jmp     short loc_14000D571
0x14000d56e  mov     rdx, rsi
0x14000d571  lea     rcx, aProcessingJob1_3; "Processing Job %1. MSIExec failed to op"...
0x14000d578  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000d57d  mov     eax, [rsi+178h]
0x14000d583  inc     eax
0x14000d585  cmp     eax, [rsi+17Ch]
0x14000d58b  jbe     short loc_14000D5CA
0x14000d58d  cmp     qword ptr [rsi+18h], 8
0x14000d592  jb      short loc_14000D599
0x14000d594  mov     rdx, [rsi]
0x14000d597  jmp     short loc_14000D59C
0x14000d599  mov     rdx, rsi
0x14000d59c  lea     rcx, aProcessingJob1_1; "Processing Job %1. Max number of enforc"...
0x14000d5a3  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000d5a8  mov     edx, 3Ch ; '<'
0x14000d5ad  mov     r8d, 80070653h
0x14000d5b3  mov     rcx, rsi
0x14000d5b6  call    ?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z; JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)
0x14000d5bb  mov     ebx, eax
0x14000d5bd  test    eax, eax
0x14000d5bf  js      loc_14000D869
0x14000d5c5  jmp     loc_14000D6B0
0x14000d5ca  mov     edx, 0Ah
0x14000d5cf  jmp     short loc_14000D5AD
0x14000d5d1  cmp     qword ptr [rsi+18h], 8
0x14000d5d6  jb      short loc_14000D5DD
0x14000d5d8  mov     rdx, [rsi]
0x14000d5db  jmp     short loc_14000D5E0
0x14000d5dd  mov     rdx, rsi
0x14000d5e0  mov     r8d, ebx
0x14000d5e3  lea     rcx, aEnforcementFai; "Enforcement failed for job %1. Error 0x"...
0x14000d5ea  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000d5ef  mov     eax, [rsi+178h]
0x14000d5f5  inc     eax
0x14000d5f7  cmp     eax, [rsi+17Ch]
0x14000d5fd  jbe     short loc_14000D624
0x14000d5ff  cmp     qword ptr [rsi+18h], 8
0x14000d604  jb      short loc_14000D60B
0x14000d606  mov     rdx, [rsi]
0x14000d609  jmp     short loc_14000D60E
0x14000d60b  mov     rdx, rsi
0x14000d60e  lea     rcx, aProcessingJob1_1; "Processing Job %1. Max number of enforc"...
0x14000d615  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000d61a  mov     r8d, ebx
0x14000d61d  mov     edx, 3Ch ; '<'
0x14000d622  jmp     short loc_14000D5B3
0x14000d624  mov     r8d, ebx
0x14000d627  mov     edx, 37h ; '7'
0x14000d62c  mov     rcx, rsi
0x14000d62f  call    ?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z; JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)
0x14000d634  mov     ebx, eax
0x14000d636  test    eax, eax
0x14000d638  jns     short loc_14000D6B0
0x14000d63a  jmp     loc_14000D869
0x14000d63f  xor     r8d, r8d
0x14000d642  lea     edx, [r8+46h]
0x14000d646  mov     rcx, rsi
0x14000d649  call    ?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z; JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)
0x14000d64e  mov     ebx, eax
0x14000d650  test    eax, eax
0x14000d652  js      loc_14000D869
0x14000d658  mov     dil, 1
0x14000d65b  cmp     qword ptr [rsi+18h], 8
0x14000d660  jb      short loc_14000D667
0x14000d662  mov     rdx, [rsi]
0x14000d665  jmp     short loc_14000D66A
0x14000d667  mov     rdx, rsi
0x14000d66a  lea     rcx, aCompletedEnfor; "Completed enforcement for Job %1.  A sy"...
0x14000d671  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000d676  jmp     short loc_14000D6B0
0x14000d678  cmp     qword ptr [rsi+18h], 8
0x14000d67d  jb      short loc_14000D684
0x14000d67f  mov     rdx, [rsi]
0x14000d682  jmp     short loc_14000D687
0x14000d684  mov     rdx, rsi
0x14000d687  lea     rcx, aEnforcementFor; "Enforcement for job %1 succeeded."
0x14000d68e  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000d693  mov     r8d, ebx
0x14000d696  mov     edx, 46h ; 'F'
0x14000d69b  mov     rcx, rsi
0x14000d69e  call    ?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z; JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)
0x14000d6a3  test    eax, eax
0x14000d6a5  mov     ebx, eax
0x14000d6a7  js      loc_14000D869
0x14000d6ad  mov     dil, 1
0x14000d6b0  mov     rdx, rsi
0x14000d6b3  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::erase(std::wstring const &)
0x14000d6b8  test    dil, dil
0x14000d6bb  jz      loc_14000D869
0x14000d6c1  lea     rdx, [rsi+20h]
0x14000d6c5  mov     rcx, rsi
0x14000d6c8  call    ?DeleteContent@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; JobHelper::DeleteContent(std::wstring const &,std::wstring &)
0x14000d6cd  lea     rbx, [rsi+0C8h]
0x14000d6d4  lea     rcx, word_14001E5B4
0x14000d6db  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14000d6e0  mov     r8, rax
0x14000d6e3  lea     rdx, word_14001E5B4
0x14000d6ea  mov     rcx, rbx
0x14000d6ed  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14000d6f2  mov     r8, rbx
0x14000d6f5  lea     rdx, [rsi+20h]
0x14000d6f9  mov     rcx, rsi
0x14000d6fc  call    ?UpdateDownloadLocation@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@0@Z; JobHelper::UpdateDownloadLocation(std::wstring const &,std::wstring &,std::wstring const &)
0x14000d701  mov     ebx, eax
0x14000d703  jmp     loc_14000D869
0x14000d708  cmp     cs:?m_bIsEnforcementThreadRunning@JobExecution@@0_NA, 0; bool JobExecution::m_bIsEnforcementThreadRunning
0x14000d70f  jnz     loc_14000D85B
0x14000d715  mov     [rbp+57h+var_98], 7
0x14000d71d  mov     [rbp+57h+var_A0], 0
0x14000d725  xor     eax, eax
0x14000d727  mov     [rbp+57h+var_B0], ax
0x14000d72b  cmp     [rsi+184h], al
0x14000d731  jz      short loc_14000D748
0x14000d733  lea     rdx, [rsi+68h]
0x14000d737  lea     rcx, [rbp+57h+var_50]
0x14000d73b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000d740  nop
0x14000d741  mov     ebx, 1
0x14000d746  jmp     short loc_14000D75D
0x14000d748  lea     rdx, word_14001E5B4
0x14000d74f  lea     rcx, [rbp+57h+var_70]
0x14000d753  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000d758  mov     ebx, 2
0x14000d75d  mov     rdx, rax
0x14000d760  lea     rcx, [rbp+57h+var_90]
0x14000d764  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x14000d769  nop
0x14000d76a  test    bl, 2
0x14000d76d  jz      short loc_14000D781
0x14000d76f  and     ebx, 0FFFFFFFDh
0x14000d772  xor     r8d, r8d
0x14000d775  mov     dl, 1
0x14000d777  lea     rcx, [rbp+57h+var_70]
0x14000d77b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000d780  nop
0x14000d781  test    bl, 1
0x14000d784  jz      short loc_14000D794
0x14000d786  xor     r8d, r8d
0x14000d789  mov     dl, 1
0x14000d78b  lea     rcx, [rbp+57h+var_50]
0x14000d78f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000d794  cmp     dword ptr [rsi+90h], 1
0x14000d79b  jnz     short loc_14000D7FE
0x14000d79d  lea     r8, [rsi+20h]
0x14000d7a1  lea     rcx, [rsi+48h]; szProduct
0x14000d7a5  lea     rdx, [rbp+57h+var_90]
0x14000d7a9  call    ?IsMSIAppInstalled@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; IsMSIAppInstalled(std::wstring const &,std::wstring const &,std::wstring const &)
0x14000d7ae  test    al, al
0x14000d7b0  jz      short loc_14000D7FE
0x14000d7b2  cmp     qword ptr [rsi+18h], 8
0x14000d7b7  jb      short loc_14000D7BE
0x14000d7b9  mov     rdx, [rsi]
0x14000d7bc  jmp     short loc_14000D7C1
0x14000d7be  mov     rdx, rsi
0x14000d7c1  lea     rcx, aProcessingJob1_2; "Processing job %1.  Found app installed"...
0x14000d7c8  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000d7cd  mov     edx, 46h ; 'F'
0x14000d7d2  xor     r8d, r8d
0x14000d7d5  mov     rcx, rsi
0x14000d7d8  call    ?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z; JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)
0x14000d7dd  mov     ebx, eax
0x14000d7df  xor     r8d, r8d
0x14000d7e2  mov     dl, 1
0x14000d7e4  lea     rcx, [rbp+57h+var_90]
0x14000d7e8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000d7ed  nop
0x14000d7ee  xor     r8d, r8d
0x14000d7f1  mov     dl, 1
0x14000d7f3  lea     rcx, [rbp+57h+var_B0]
0x14000d7f7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000d7fc  jmp     short loc_14000D869
0x14000d7fe  mov     eax, [rsi+178h]
0x14000d804  inc     eax
0x14000d806  cmp     eax, [rsi+17Ch]
0x14000d80c  jbe     short loc_14000D836
0x14000d80e  cmp     qword ptr [rsi+18h], 8
0x14000d813  jb      short loc_14000D81A
0x14000d815  mov     rdx, [rsi]
0x14000d818  jmp     short loc_14000D81D
0x14000d81a  mov     rdx, rsi
0x14000d81d  lea     rcx, aProcessingJob1_1; "Processing Job %1. Max number of enforc"...
0x14000d824  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000d829  mov     edx, 3Ch ; '<'
0x14000d82e  mov     r8d, 8000FFFFh
0x14000d834  jmp     short loc_14000D7D5
0x14000d836  cmp     qword ptr [rsi+18h], 8
0x14000d83b  jb      short loc_14000D842
0x14000d83d  mov     rdx, [rsi]
0x14000d840  jmp     short loc_14000D845
0x14000d842  mov     rdx, rsi
0x14000d845  lea     rcx, aProcessingJob1_0; "Processing Job %1. No enforcement resul"...
0x14000d84c  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000d851  mov     edx, 37h ; '7'
0x14000d856  jmp     loc_14000D7D2
0x14000d85b  xor     ebx, ebx
0x14000d85d  lea     rcx, aTheEnforcement; "The enforcement thread is still running"...
0x14000d864  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000d869  lea     rcx, ?m_critSec@JobExecution@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14000d870  call    cs:__imp_LeaveCriticalSection
0x14000d876  mov     eax, ebx
0x14000d878  mov     rcx, [rbp+57h+var_30]
0x14000d87c  xor     rcx, rsp; StackCookie
0x14000d87f  call    __security_check_cookie
0x14000d884  add     rsp, 0C8h
0x14000d88b  pop     rdi
0x14000d88c  pop     rsi
0x14000d88d  pop     rbx
0x14000d88e  pop     rbp
0x14000d88f  retn
```
