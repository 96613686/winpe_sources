# CAppList::MarkRSOPEntryAsRemoved(CAppInfo *,int)

- ea: `0x18000a7c0`
- end: `0x18000ac88`
- name: `?MarkRSOPEntryAsRemoved@CAppList@@QEAAJPEAVCAppInfo@@H@Z`
- size: `1224`
- prototype: `__int64 __fastcall(IWbemServices **this, struct CAppInfo *, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000239c`
- `0x18000b16c`

## callees

- `0x1800060fc`
- `0x18000a148`
- `0x18000a6e4`
- `0x18000a7c0`
- `0x18000c42c`
- `0x18000c790`
- `0x18001b1a0`
- `0x180029cc0`
- `0x180029e18`
- `0x180029fd0`
- `0x18002a3d4`
- `0x18002a4a4`
- `0x18002a57c`
- `0x18002a6cc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac64`
- `USERENV!RsopResetPolicySettingStatus` at `0x18000aac6`
- `USERENV!RsopResetPolicySettingStatus` at `0x18000ab5c`
- `USERENV!RsopResetPolicySettingStatus` at `0x18000aac6`
- `USERENV!RsopResetPolicySettingStatus` at `0x18000ab5c`

## string_xrefs

- `0x18000a976`: `OnDemandFileExtension`
- `0x18000a996`: `OnDemandFileExtension`
- `0x18000a9ac`: `OnDemandClsid`
- `0x18000a9cc`: `OnDemandClsid`

## pseudocode

```c
__int64 __fastcall CAppList::MarkRSOPEntryAsRemoved(IWbemServices **this, struct CAppInfo *a2, int a3)
{
  int v6; // r15d
  int inited; // ebx
  const unsigned __int16 *RsopAppCriteria; // rax
  unsigned __int16 *v9; // rsi
  int v10; // eax
  const unsigned __int16 *v11; // r8
  int v12; // eax
  int v13; // eax
  int v14; // eax
  const unsigned __int16 *v15; // r8
  HRESULT v16; // eax
  int v17; // eax
  const unsigned __int16 *v18; // r8
  IWbemServices *v19; // rcx
  void **v21; // [rsp+30h] [rbp-50h] BYREF
  IWbemClassObject *pSettingInstance; // [rsp+38h] [rbp-48h]
  int v23; // [rsp+40h] [rbp-40h]
  __int64 v24; // [rsp+48h] [rbp-38h]
  __int64 v25; // [rsp+50h] [rbp-30h]
  struct CAppInfo *v26; // [rsp+58h] [rbp-28h]
  __int64 v27; // [rsp+60h] [rbp-20h]
  __int64 v28; // [rsp+68h] [rbp-18h]
  __int64 i; // [rsp+70h] [rbp-10h]
  int v30; // [rsp+B0h] [rbp+30h] BYREF
  int v31; // [rsp+C0h] [rbp+40h] BYREF

  if ( *(_DWORD *)&gDebugLevel )
    _DebugMsg(4, 0xC25u, *((_QWORD *)a2 + 5), *((_QWORD *)a2 + 9));
  v6 = 0;
  if ( !*((_DWORD *)a2 + 75) )
    v6 = a3;
  inited = CAppList::InitRsopLog((CAppList *)this);
  if ( inited >= 0 )
  {
    inited = -2147024882;
    RsopAppCriteria = CAppInfo::GetRsopAppCriteria(a2);
    v9 = (unsigned __int16 *)RsopAppCriteria;
    if ( RsopAppCriteria )
    {
      inited = CGroupPolicyLog::GetEnum((CGroupPolicyLog *)this, RsopAppCriteria);
      if ( inited >= 0 )
      {
        v24 = 0;
        v25 = 0;
        pSettingInstance = 0;
        v23 = 1;
        v21 = &CConflict::`vftable';
        v26 = a2;
        v27 = 0;
        v28 = 1;
        for ( i = 0; ; i = 0 )
        {
          v31 = 0;
          inited = CGroupPolicyLog::GetNextRecord((CGroupPolicyLog *)this, (struct CGroupPolicyRecord *)&v21);
          if ( inited
            || (inited = CGroupPolicyRecord::GetValue((CGroupPolicyRecord *)&v21, L"precedence", &v31), inited < 0) )
          {
LABEL_59:
            CConflict::~CConflict((HLOCAL *)&v21);
            goto LABEL_62;
          }
          if ( v31 != 1 )
          {
            inited = CGroupPolicyLog::DeleteRecord((CGroupPolicyLog *)this, (struct CGroupPolicyRecord *)&v21, 1);
            if ( inited < 0 )
              goto LABEL_59;
            goto LABEL_51;
          }
          if ( (*((_BYTE *)a2 + 224) & 1) == 0 )
            goto LABEL_39;
          if ( LODWORD(this[11][10].lpVtbl) != 4 )
            goto LABEL_39;
          v31 = 0;
          v30 = 0;
          if ( (int)CGroupPolicyRecord::GetValue((CGroupPolicyRecord *)&v21, L"ApplyCause", &v31) < 0
            || (int)CGroupPolicyRecord::GetValue((CGroupPolicyRecord *)&v21, L"Eligibility", &v30) < 0 )
          {
            goto LABEL_39;
          }
          v10 = CGroupPolicyRecord::SetValue((CGroupPolicyRecord *)&v21, L"ApplyCause", 1);
          if ( v10 >= 0 )
          {
            v10 = CGroupPolicyRecord::SetValue((CGroupPolicyRecord *)&v21, L"Eligibility", 1);
            if ( v10 >= 0 || !*(_DWORD *)&gDebugLevel )
              goto LABEL_22;
            v11 = L"Eligibility";
          }
          else
          {
            if ( !*(_DWORD *)&gDebugLevel )
              goto LABEL_22;
            v11 = L"ApplyCause";
          }
          _DebugMsg(4, 0xC29u, v11, (unsigned int)v10);
LABEL_22:
          v12 = CGroupPolicyRecord::ClearValue((CGroupPolicyRecord *)&v21, L"OnDemandFileExtension");
          if ( v12 < 0 && *(_DWORD *)&gDebugLevel )
            _DebugMsg(4, 0xC29u, L"OnDemandFileExtension", (unsigned int)v12);
          v13 = CGroupPolicyRecord::ClearValue((CGroupPolicyRecord *)&v21, L"OnDemandClsid");
          if ( v13 < 0 && *(_DWORD *)&gDebugLevel )
            _DebugMsg(4, 0xC29u, L"OnDemandClsid", (unsigned int)v13);
          v14 = CGroupPolicyRecord::ClearValue((CGroupPolicyRecord *)&v21, L"OnDemandProgid");
          if ( v14 >= 0 )
          {
            if ( ((int (__fastcall *)(IWbemServices *, IWbemClassObject *, _QWORD, _QWORD, _QWORD))this[4]->lpVtbl->PutInstance)(
                   this[4],
                   pSettingInstance,
                   0,
                   0,
                   0) < 0 )
              goto LABEL_39;
            v14 = CGroupPolicyRecord::SetValue((CGroupPolicyRecord *)&v21, L"ApplyCause", v31);
            if ( v14 >= 0 )
            {
              v14 = CGroupPolicyRecord::SetValue((CGroupPolicyRecord *)&v21, L"Eligibility", v30);
              if ( v14 >= 0 || !*(_DWORD *)&gDebugLevel )
                goto LABEL_39;
              v15 = L"Eligibility";
            }
            else
            {
              if ( !*(_DWORD *)&gDebugLevel )
                goto LABEL_39;
              v15 = L"ApplyCause";
            }
          }
          else
          {
            if ( !*(_DWORD *)&gDebugLevel )
              goto LABEL_39;
            v15 = L"OnDemandProgid";
          }
          _DebugMsg(4, 0xC29u, v15, (unsigned int)v14);
LABEL_39:
          if ( v6 && ((*((_BYTE *)a2 + 224) & 2) != 0 || LODWORD(this[11][10].lpVtbl) != 1) )
            v16 = CGroupPolicyLog::DeleteRecord((CGroupPolicyLog *)this, (struct CGroupPolicyRecord *)&v21, 1);
          else
            v16 = RsopResetPolicySettingStatus(0, this[4], pSettingInstance);
          inited = v16;
          if ( v16 < 0 )
            goto LABEL_59;
          v17 = CGroupPolicyRecord::SetValue((CGroupPolicyRecord *)&v21, L"EntryType", 2);
          inited = v17;
          if ( v17 < 0 )
          {
            if ( !*(_DWORD *)&gDebugLevel )
              goto LABEL_59;
            v18 = L"EntryType";
            goto LABEL_58;
          }
          v17 = CGroupPolicyRecord::SetValue((CGroupPolicyRecord *)&v21, L"precedence", 0);
          inited = v17;
          if ( v17 < 0 )
          {
            if ( !*(_DWORD *)&gDebugLevel )
              goto LABEL_59;
            v18 = L"precedence";
LABEL_58:
            _DebugMsg(4, 0xC29u, v18, (unsigned int)v17);
            goto LABEL_59;
          }
          inited = CAppInfo::WriteRemovalProperties(a2, (struct CGroupPolicyRecord *)&v21);
          if ( inited < 0 )
            goto LABEL_59;
          inited = ((__int64 (__fastcall *)(IWbemServices *, IWbemClassObject *, _QWORD, _QWORD, _QWORD))this[4]->lpVtbl->PutInstance)(
                     this[4],
                     pSettingInstance,
                     0,
                     0,
                     0);
          if ( inited < 0 )
            goto LABEL_59;
          RsopResetPolicySettingStatus(0, this[4], pSettingInstance);
          CConflict::LogFailure((CConflict *)&v21);
LABEL_51:
          CConflict::~CConflict((HLOCAL *)&v21);
          v24 = 0;
          v25 = 0;
          pSettingInstance = 0;
          v23 = 1;
          v21 = &CConflict::`vftable';
          v26 = a2;
          v27 = 0;
          v28 = 1;
        }
      }
    }
    LocalFree(v9);
  }
  v9 = 0;
LABEL_62:
  v19 = this[3];
  if ( v19 )
    ((void (__fastcall *)(IWbemServices *))v19->lpVtbl->Release)(v19);
  this[3] = 0;
  if ( v6 && inited >= 0 )
    inited = CGroupPolicyLog::ClearLog((CGroupPolicyLog *)this, v9, 1);
  LocalFree(v9);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000a7c0  mov     [rsp-28h+arg_8], rbx
0x18000a7c5  mov     [rsp-28h+arg_18], rsi
0x18000a7ca  push    rbp
0x18000a7cb  push    rdi
0x18000a7cc  push    r13
0x18000a7ce  push    r14
0x18000a7d0  push    r15
0x18000a7d2  mov     rbp, rsp
0x18000a7d5  sub     rsp, 80h
0x18000a7dc  mov     ebx, r8d
0x18000a7df  mov     r14, rdx
0x18000a7e2  mov     rdi, rcx
0x18000a7e5  xor     r13d, r13d
0x18000a7e8  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x18000a7ef  jz      short loc_18000A807
0x18000a7f1  mov     r9, [rdx+48h]
0x18000a7f5  mov     r8, [rdx+28h]
0x18000a7f9  mov     edx, 0C25h; unsigned int
0x18000a7fe  lea     ecx, [r13+4]; unsigned int
0x18000a802  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000a807  mov     r15d, r13d
0x18000a80a  cmp     [r14+12Ch], r13d
0x18000a811  cmovz   r15d, ebx
0x18000a815  mov     rcx, rdi; this
0x18000a818  call    ?InitRsopLog@CAppList@@AEAAJXZ; CAppList::InitRsopLog(void)
0x18000a81d  mov     ebx, eax
0x18000a81f  test    eax, eax
0x18000a821  js      loc_18000AC29
0x18000a827  mov     ebx, 8007000Eh
0x18000a82c  mov     rcx, r14; this
0x18000a82f  call    ?GetRsopAppCriteria@CAppInfo@@AEAAPEAGXZ; CAppInfo::GetRsopAppCriteria(void)
0x18000a834  mov     rsi, rax
0x18000a837  test    rax, rax
0x18000a83a  jz      loc_18000AC20
0x18000a840  mov     rdx, rax; unsigned __int16 *
0x18000a843  mov     rcx, rdi; this
0x18000a846  call    ?GetEnum@CGroupPolicyLog@@IEAAJPEBG@Z; CGroupPolicyLog::GetEnum(ushort const *)
0x18000a84b  mov     ebx, eax
0x18000a84d  test    eax, eax
0x18000a84f  js      loc_18000AC20
0x18000a855  mov     [rbp+var_38], r13
0x18000a859  mov     [rbp+var_30], r13
0x18000a85d  mov     [rbp+pSettingInstance], r13
0x18000a861  mov     [rbp+var_40], 1
0x18000a868  lea     rax, ??_7CConflict@@6B@; const CConflict::`vftable'
0x18000a86f  mov     [rbp+var_50], rax
0x18000a873  mov     [rbp+var_28], r14
0x18000a877  mov     [rbp+var_20], r13
0x18000a87b  mov     [rbp+var_18], 1
0x18000a883  mov     [rbp+var_10], r13
0x18000a887  jmp     loc_18000ABC4
0x18000a88c  lea     r8, [rbp+arg_10]; int *
0x18000a890  lea     rdx, aPrecedence; "precedence"
0x18000a897  lea     rcx, [rbp+var_50]; this
0x18000a89b  call    ?GetValue@CGroupPolicyRecord@@QEAAJPEBGPEAJ@Z; CGroupPolicyRecord::GetValue(ushort const *,long *)
0x18000a8a0  mov     ebx, eax
0x18000a8a2  test    eax, eax
0x18000a8a4  js      loc_18000AC15
0x18000a8aa  cmp     [rbp+arg_10], 1
0x18000a8ae  jnz     loc_18000AB6D
0x18000a8b4  mov     ebx, 1
0x18000a8b9  test    [r14+0E0h], bl
0x18000a8c0  jz      loc_18000AA93
0x18000a8c6  mov     rax, [rdi+58h]
0x18000a8ca  cmp     dword ptr [rax+50h], 4
0x18000a8ce  jnz     loc_18000AA93
0x18000a8d4  mov     [rbp+arg_10], r13d
0x18000a8d8  mov     [rbp+arg_0], r13d
0x18000a8dc  lea     r8, [rbp+arg_10]; int *
0x18000a8e0  lea     rdx, aApplycause; "ApplyCause"
0x18000a8e7  lea     rcx, [rbp+var_50]; this
0x18000a8eb  call    ?GetValue@CGroupPolicyRecord@@QEAAJPEBGPEAJ@Z; CGroupPolicyRecord::GetValue(ushort const *,long *)
0x18000a8f0  test    eax, eax
0x18000a8f2  js      loc_18000AA93
0x18000a8f8  lea     r8, [rbp+arg_0]; int *
0x18000a8fc  lea     rdx, aEligibility; "Eligibility"
0x18000a903  lea     rcx, [rbp+var_50]; this
0x18000a907  call    ?GetValue@CGroupPolicyRecord@@QEAAJPEBGPEAJ@Z; CGroupPolicyRecord::GetValue(ushort const *,long *)
0x18000a90c  test    eax, eax
0x18000a90e  js      loc_18000AA93
0x18000a914  mov     r8d, ebx; int
0x18000a917  lea     rdx, aApplycause; "ApplyCause"
0x18000a91e  lea     rcx, [rbp+var_50]; this
0x18000a922  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x18000a927  test    eax, eax
0x18000a929  jns     short loc_18000A93D
0x18000a92b  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x18000a932  jz      short loc_18000A976
0x18000a934  lea     r8, aApplycause; "ApplyCause"
0x18000a93b  jmp     short loc_18000A964
0x18000a93d  mov     r8d, ebx; int
0x18000a940  lea     rdx, aEligibility; "Eligibility"
0x18000a947  lea     rcx, [rbp+var_50]; this
0x18000a94b  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x18000a950  test    eax, eax
0x18000a952  jns     short loc_18000A976
0x18000a954  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x18000a95b  jz      short loc_18000A976
0x18000a95d  lea     r8, aEligibility; "Eligibility"
0x18000a964  mov     r9d, eax
0x18000a967  mov     edx, 0C29h; unsigned int
0x18000a96c  mov     ecx, 4; unsigned int
0x18000a971  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000a976  lea     rdx, aOndemandfileex; "OnDemandFileExtension"
0x18000a97d  lea     rcx, [rbp+var_50]; this
0x18000a981  call    ?ClearValue@CGroupPolicyRecord@@QEAAJPEBG@Z; CGroupPolicyRecord::ClearValue(ushort const *)
0x18000a986  test    eax, eax
0x18000a988  jns     short loc_18000A9AC
0x18000a98a  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x18000a991  jz      short loc_18000A9AC
0x18000a993  mov     r9d, eax
0x18000a996  lea     r8, aOndemandfileex; "OnDemandFileExtension"
0x18000a99d  mov     edx, 0C29h; unsigned int
0x18000a9a2  mov     ecx, 4; unsigned int
0x18000a9a7  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000a9ac  lea     rdx, aOndemandclsid; "OnDemandClsid"
0x18000a9b3  lea     rcx, [rbp+var_50]; this
0x18000a9b7  call    ?ClearValue@CGroupPolicyRecord@@QEAAJPEBG@Z; CGroupPolicyRecord::ClearValue(ushort const *)
0x18000a9bc  test    eax, eax
0x18000a9be  jns     short loc_18000A9E2
0x18000a9c0  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x18000a9c7  jz      short loc_18000A9E2
0x18000a9c9  mov     r9d, eax
0x18000a9cc  lea     r8, aOndemandclsid; "OnDemandClsid"
0x18000a9d3  mov     edx, 0C29h; unsigned int
0x18000a9d8  mov     ecx, 4; unsigned int
0x18000a9dd  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000a9e2  lea     rdx, aOndemandprogid; "OnDemandProgid"
0x18000a9e9  lea     rcx, [rbp+var_50]; this
0x18000a9ed  call    ?ClearValue@CGroupPolicyRecord@@QEAAJPEBG@Z; CGroupPolicyRecord::ClearValue(ushort const *)
0x18000a9f2  test    eax, eax
0x18000a9f4  jns     short loc_18000AA0C
0x18000a9f6  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x18000a9fd  jz      loc_18000AA93
0x18000aa03  lea     r8, aOndemandprogid; "OnDemandProgid"
0x18000aa0a  jmp     short loc_18000AA81
0x18000aa0c  mov     rcx, [rdi+20h]
0x18000aa10  mov     rax, [rcx]
0x18000aa13  mov     [rsp+80h+var_60], r13
0x18000aa18  xor     r9d, r9d
0x18000aa1b  xor     r8d, r8d
0x18000aa1e  mov     rdx, [rbp+pSettingInstance]
0x18000aa22  mov     rax, [rax+70h]
0x18000aa26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa2b  test    eax, eax
0x18000aa2d  js      short loc_18000AA93
0x18000aa2f  mov     r8d, [rbp+arg_10]; int
0x18000aa33  lea     rdx, aApplycause; "ApplyCause"
0x18000aa3a  lea     rcx, [rbp+var_50]; this
0x18000aa3e  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x18000aa43  test    eax, eax
0x18000aa45  jns     short loc_18000AA59
0x18000aa47  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x18000aa4e  jz      short loc_18000AA93
0x18000aa50  lea     r8, aApplycause; "ApplyCause"
0x18000aa57  jmp     short loc_18000AA81
0x18000aa59  mov     r8d, [rbp+arg_0]; int
0x18000aa5d  lea     rdx, aEligibility; "Eligibility"
0x18000aa64  lea     rcx, [rbp+var_50]; this
0x18000aa68  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x18000aa6d  test    eax, eax
0x18000aa6f  jns     short loc_18000AA93
0x18000aa71  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x18000aa78  jz      short loc_18000AA93
0x18000aa7a  lea     r8, aEligibility; "Eligibility"
0x18000aa81  mov     r9d, eax
0x18000aa84  mov     edx, 0C29h; unsigned int
0x18000aa89  mov     ecx, 4; unsigned int
0x18000aa8e  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000aa93  test    r15d, r15d
0x18000aa96  jz      short loc_18000AABC
0x18000aa98  test    byte ptr [r14+0E0h], 2
0x18000aaa0  jnz     short loc_18000AAAB
0x18000aaa2  mov     rax, [rdi+58h]
0x18000aaa6  cmp     [rax+50h], ebx
0x18000aaa9  jz      short loc_18000AABC
0x18000aaab  mov     r8d, ebx; int
0x18000aaae  lea     rdx, [rbp+var_50]; struct CGroupPolicyRecord *
0x18000aab2  mov     rcx, rdi; this
0x18000aab5  call    ?DeleteRecord@CGroupPolicyLog@@QEAAJPEAVCGroupPolicyRecord@@H@Z; CGroupPolicyLog::DeleteRecord(CGroupPolicyRecord *,int)
0x18000aaba  jmp     short loc_18000AACC
0x18000aabc  mov     r8, [rbp+pSettingInstance]; pSettingInstance
0x18000aac0  mov     rdx, [rdi+20h]; pServices
0x18000aac4  xor     ecx, ecx; dwFlags
0x18000aac6  call    cs:__imp_RsopResetPolicySettingStatus
0x18000aacc  mov     ebx, eax
0x18000aace  test    eax, eax
0x18000aad0  js      loc_18000AC15
0x18000aad6  mov     r8d, 2; int
0x18000aadc  lea     rdx, aEntrytype; "EntryType"
0x18000aae3  lea     rcx, [rbp+var_50]; this
0x18000aae7  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x18000aaec  mov     ebx, eax
0x18000aaee  test    eax, eax
0x18000aaf0  js      loc_18000ABF2
0x18000aaf6  xor     r8d, r8d; int
0x18000aaf9  lea     rdx, aPrecedence; "precedence"
0x18000ab00  lea     rcx, [rbp+var_50]; this
0x18000ab04  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x18000ab09  mov     ebx, eax
0x18000ab0b  test    eax, eax
0x18000ab0d  js      loc_18000ABE0
0x18000ab13  lea     rdx, [rbp+var_50]; struct CGroupPolicyRecord *
0x18000ab17  mov     rcx, r14; this
0x18000ab1a  call    ?WriteRemovalProperties@CAppInfo@@QEAAJPEAVCGroupPolicyRecord@@@Z; CAppInfo::WriteRemovalProperties(CGroupPolicyRecord *)
0x18000ab1f  mov     ebx, eax
0x18000ab21  test    eax, eax
0x18000ab23  js      loc_18000AC15
0x18000ab29  mov     rcx, [rdi+20h]
0x18000ab2d  mov     rax, [rcx]
0x18000ab30  mov     [rsp+80h+var_60], r13
0x18000ab35  xor     r9d, r9d
0x18000ab38  xor     r8d, r8d
0x18000ab3b  mov     rdx, [rbp+pSettingInstance]
0x18000ab3f  mov     rax, [rax+70h]
0x18000ab43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab48  mov     ebx, eax
0x18000ab4a  test    eax, eax
0x18000ab4c  js      loc_18000AC15
0x18000ab52  mov     r8, [rbp+pSettingInstance]; pSettingInstance
0x18000ab56  mov     rdx, [rdi+20h]; pServices
0x18000ab5a  xor     ecx, ecx; dwFlags
0x18000ab5c  call    cs:__imp_RsopResetPolicySettingStatus
0x18000ab62  lea     rcx, [rbp+var_50]; this
0x18000ab66  call    ?LogFailure@CConflict@@QEAAJXZ; CConflict::LogFailure(void)
0x18000ab6b  jmp     short loc_18000AB89
0x18000ab6d  mov     r8d, 1; int
0x18000ab73  lea     rdx, [rbp+var_50]; struct CGroupPolicyRecord *
0x18000ab77  mov     rcx, rdi; this
0x18000ab7a  call    ?DeleteRecord@CGroupPolicyLog@@QEAAJPEAVCGroupPolicyRecord@@H@Z; CGroupPolicyLog::DeleteRecord(CGroupPolicyRecord *,int)
0x18000ab7f  mov     ebx, eax
0x18000ab81  test    eax, eax
0x18000ab83  js      loc_18000AC15
0x18000ab89  lea     rcx, [rbp+var_50]; this
0x18000ab8d  call    ??1CConflict@@UEAA@XZ; CConflict::~CConflict(void)
0x18000ab92  mov     [rbp+var_38], r13
0x18000ab96  mov     [rbp+var_30], r13
0x18000ab9a  mov     [rbp+pSettingInstance], r13
0x18000ab9e  mov     [rbp+var_40], 1
0x18000aba5  lea     rax, ??_7CConflict@@6B@; const CConflict::`vftable'
0x18000abac  mov     [rbp+var_50], rax
0x18000abb0  mov     [rbp+var_28], r14
0x18000abb4  mov     [rbp+var_20], r13
0x18000abb8  mov     [rbp+var_18], 1
0x18000abc0  mov     [rbp+var_10], r13
0x18000abc4  mov     [rbp+arg_10], r13d
0x18000abc8  lea     rdx, [rbp+var_50]; struct CGroupPolicyRecord *
0x18000abcc  mov     rcx, rdi; this
0x18000abcf  call    ?GetNextRecord@CGroupPolicyLog@@QEAAJPEAVCGroupPolicyRecord@@@Z; CGroupPolicyLog::GetNextRecord(CGroupPolicyRecord *)
0x18000abd4  test    eax, eax
0x18000abd6  mov     ebx, eax
0x18000abd8  jz      loc_18000A88C
0x18000abde  jmp     short loc_18000AC15
0x18000abe0  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x18000abe7  jz      short loc_18000AC15
0x18000abe9  lea     r8, aPrecedence; "precedence"
0x18000abf0  jmp     short loc_18000AC02
0x18000abf2  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x18000abf9  jz      short loc_18000AC15
0x18000abfb  lea     r8, aEntrytype; "EntryType"
0x18000ac02  mov     r9d, eax
0x18000ac05  mov     edx, 0C29h; unsigned int
0x18000ac0a  mov     ecx, 4; unsigned int
0x18000ac0f  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000ac14  nop
0x18000ac15  lea     rcx, [rbp+var_50]; this
0x18000ac19  call    ??1CConflict@@UEAA@XZ; CConflict::~CConflict(void)
0x18000ac1e  jmp     short loc_18000AC2C
0x18000ac20  mov     rcx, rsi; hMem
0x18000ac23  call    cs:__imp_LocalFree
0x18000ac29  mov     rsi, r13
0x18000ac2c  mov     rcx, [rdi+18h]
0x18000ac30  test    rcx, rcx
0x18000ac33  jz      short loc_18000AC41
0x18000ac35  mov     rax, [rcx]
0x18000ac38  mov     rax, [rax+10h]
0x18000ac3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac41  mov     [rdi+18h], r13
0x18000ac45  test    r15d, r15d
0x18000ac48  jz      short loc_18000AC61
0x18000ac4a  test    ebx, ebx
0x18000ac4c  js      short loc_18000AC61
0x18000ac4e  mov     r8d, 1; int
0x18000ac54  mov     rdx, rsi; unsigned __int16 *
0x18000ac57  mov     rcx, rdi; this
0x18000ac5a  call    ?ClearLog@CGroupPolicyLog@@QEAAJPEBGH@Z; CGroupPolicyLog::ClearLog(ushort const *,int)
0x18000ac5f  mov     ebx, eax
0x18000ac61  mov     rcx, rsi; hMem
0x18000ac64  call    cs:__imp_LocalFree
0x18000ac6a  mov     eax, ebx
0x18000ac6c  lea     r11, [rsp+80h+var_s0]
0x18000ac74  mov     rbx, [r11+38h]
0x18000ac78  mov     rsi, [r11+48h]
0x18000ac7c  mov     rsp, r11
0x18000ac7f  pop     r15
0x18000ac81  pop     r14
0x18000ac83  pop     r13
0x18000ac85  pop     rdi
0x18000ac86  pop     rbp
0x18000ac87  retn
  ... truncated ...
```
