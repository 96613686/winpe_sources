# BfeObjectAdd

- ea: `0x18000aef4`
- end: `0x18000b824`
- name: `BfeObjectAdd`
- size: `2352`
- prototype: `__int64 __fastcall(unsigned int, _QWORD *, void *, _QWORD *)`
- caller_count: `6`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008cb0`
- `0x18000a140`
- `0x18000a730`
- `0x18002e69c`
- `0x180056c50`
- `0x180061e90`

## callees

- `0x180005264`
- `0x1800060a8`
- `0x180007430`
- `0x180007460`
- `0x180007f6c`
- `0x180008240`
- `0x1800082a4`
- `0x180008320`
- `0x1800084e0`
- `0x18000aef4`
- `0x18000f1a8`
- `0x180010360`
- `0x180010ad0`
- `0x18001236c`
- `0x180012b54`
- `0x180012be0`
- `0x180018b74`
- `0x180030180`
- `0x180038350`
- `0x18004e230`
- `0x1800542bc`
- `0x1800575c4`
- `0x180058b30`
- `0x180087dc0`
- `0x18008b010`

## import_xrefs

- `ntdll!RtlInsertEntryHashTable` at `0x18000b125`
- `ntdll!RtlInsertEntryHashTable` at `0x18000b32b`
- `ntdll!RtlInsertEntryHashTable` at `0x18000b125`
- `ntdll!RtlInsertEntryHashTable` at `0x18000b32b`
- `ntdll!RtlLookupEntryHashTable` at `0x18000b0e3`
- `ntdll!RtlLookupEntryHashTable` at `0x18000b277`
- `ntdll!RtlLookupEntryHashTable` at `0x18000b0e3`
- `ntdll!RtlLookupEntryHashTable` at `0x18000b277`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000b554`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000b5b8`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000b554`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000b5b8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b300`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b300`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b350`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b350`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000b252`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000b252`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000b2da`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000b2da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000af99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b4ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000af99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b4ca`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000b67e`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000b69c`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000b67e`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000b69c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b046`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b158`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b492`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b046`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b158`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b492`
- `RPCRT4!UuidCreate` at `0x18000b56b`
- `RPCRT4!UuidCreate` at `0x18000b56b`

## string_xrefs

- `0x18000b57c`: `UuidCreate`
- `0x18000b6b4`: `RtlCreateHashTable`
- `0x18000b785`: `RtlCreateHashTable`
- `0x18000b5fa`: `BfeSessionRundownCreate`

## pseudocode

```c
__int64 __fastcall BfeObjectAdd(unsigned int a1, _QWORD *a2, void *a3, _QWORD *a4)
{
  unsigned int v5; // r14d
  __int64 v6; // r15
  __int64 v7; // r13
  __int64 v8; // rdi
  __int64 v9; // rbx
  char *v10; // rax
  __int64 v11; // rcx
  char *v12; // rsi
  _QWORD *v13; // rdx
  _QWORD *v14; // rcx
  __int64 *Value; // rax
  __int64 v16; // rax
  UUID *v17; // rax
  UUID *v18; // rbx
  __int64 v19; // rdi
  __int64 v20; // r14
  __int64 v21; // rdx
  __int64 v22; // r12
  __int64 i; // rax
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 *v26; // rax
  __int64 v27; // rax
  void *v28; // r9
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rbx
  __int64 v32; // r14
  __int64 v33; // r12
  __int64 v34; // rdx
  __int64 v35; // r15
  __int64 j; // rax
  _BYTE *v37; // rbx
  __int64 v38; // rcx
  __int64 v39; // rbx
  __int64 v40; // rcx
  __int64 v42; // rdi
  _QWORD *Key; // rax
  __int64 v44; // rcx
  __int64 v45; // r8
  const char *v46; // rdx
  __int64 *v47; // rax
  __int64 v48; // r14
  char *v49; // rax
  __int64 v50; // rcx
  char *v51; // rbx
  __int64 v52; // rax
  char **v53; // rcx
  unsigned int v54; // eax
  __int64 v55; // rax
  __int64 v56; // rax
  int v57; // r8d
  int v58; // r8d
  char *v60; // [rsp+38h] [rbp-41h] BYREF
  PSECURITY_DESCRIPTOR CreatorDescriptor; // [rsp+40h] [rbp-39h]
  _QWORD *v62; // [rsp+48h] [rbp-31h]
  _QWORD *v63; // [rsp+50h] [rbp-29h]
  __int128 v64; // [rsp+58h] [rbp-21h] BYREF
  const char *v65; // [rsp+68h] [rbp-11h]
  __int64 v66; // [rsp+70h] [rbp-9h]
  char **v67; // [rsp+78h] [rbp-1h]
  __int64 v68; // [rsp+80h] [rbp+7h]

  v5 = a1;
  v6 = 408LL * (int)a1;
  v63 = a4;
  v7 = v6 + gBfeObjMgr;
  CreatorDescriptor = a3;
  v62 = a2;
  v60 = 0;
  if ( a1 >= 7 || !*(_DWORD *)v7 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v8 = BfeAccessCheck(*(char **)(v7 + 344), 1u, 0);
  if ( v8 )
    goto LABEL_106;
  v9 = *(_QWORD *)(v7 + 64);
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
  {
    v12 = v60;
    v8 = WfpMemAlloc25B(v9 + 144);
  }
  else
  {
    v10 = (char *)HeapAlloc(gWfpHeap, 8u, v9 + 144);
    v12 = v10;
    if ( v10 )
    {
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v10));
    }
    else
    {
      v55 = WfpReportSysErrorAsNtStatus(v11, "HeapAlloc", 3221225495LL);
      v8 = v55;
      if ( v55 )
        WfpReportError(v55, "WfpMemAlloc");
    }
  }
  if ( v8 )
  {
LABEL_81:
    if ( v12 )
    {
      if ( !*v62 && (v12[8] & 0x10) != 0 )
      {
        BfeObjectGetPublicState(v12);
        BfeObjectTraceAddFailure(v5);
      }
      BfeObjectDeleteAlways(v12);
    }
LABEL_106:
    if ( v8 )
      WfpReportError(v8, "BfeObjectAdd");
    return v8;
  }
  *(_QWORD *)v12 = v7;
  BfeIterateAssociationEnterLock();
  *((_QWORD *)v12 + 11) = v12 + 80;
  *((_QWORD *)v12 + 10) = v12 + 80;
  *((_QWORD *)v12 + 13) = v12 + 96;
  *((_QWORD *)v12 + 12) = v12 + 96;
  BfeIterateAssociationLeaveLock();
  v13 = *(_QWORD **)(v7 + 360);
  v14 = v12 + 128;
  if ( *v13 != v7 + 352 )
    goto LABEL_11;
  *v14 = v7 + 352;
  *((_QWORD *)v12 + 17) = v13;
  *v13 = v14;
  *(_QWORD *)(v7 + 360) = v14;
  *((_DWORD *)v12 + 2) |= 4u;
  if ( !*(_DWORD *)(gBfeObjMgr + 2860) )
    *((_DWORD *)v12 + 2) |= 1u;
  Value = (__int64 *)TlsGetValue(gBfeContextComponent);
  if ( Value )
  {
    v16 = *Value;
    if ( v16 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(v16 + 16) + 32LL) & 1) != 0 )
      {
        v47 = (__int64 *)TlsGetValue(gBfeContextComponent);
        if ( v47 )
          v48 = *v47;
        else
          v48 = 0;
        v60 = 0;
        *((_QWORD *)v12 + 15) = 0;
        if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
        {
          v51 = v60;
          v8 = WfpMemAlloc25B(0x28u);
        }
        else
        {
          v49 = (char *)HeapAlloc(gWfpHeap, 0, 0x28u);
          v51 = v49;
          if ( v49 )
          {
            v8 = 0;
            if ( gWfpTrackHeapBytes )
              _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v49));
          }
          else
          {
            v56 = WfpReportSysErrorAsNtStatus(v50, "HeapAlloc", 3221225495LL);
            v8 = v56;
            if ( v56 )
              WfpReportError(v56, "WfpMemAlloc");
          }
        }
        if ( v8 )
        {
          WfpReportError(v8, "BfeSessionRundownCreate");
          goto LABEL_80;
        }
        *((_QWORD *)v51 + 2) = v48;
        *((_QWORD *)v51 + 3) = BfeObjectDeleteAlways;
        v52 = v48 + 64;
        *((_QWORD *)v51 + 4) = v12;
        v53 = *(char ***)(v48 + 72);
        if ( *v53 != (char *)(v48 + 64) )
LABEL_11:
          __fastfail(3u);
        v5 = a1;
        *(_QWORD *)v51 = v52;
        *((_QWORD *)v51 + 1) = v53;
        *v53 = v51;
        *(_QWORD *)(v52 + 8) = v51;
        *((_QWORD *)v12 + 15) = v51;
      }
    }
  }
  v17 = (UUID *)(*(__int64 (__fastcall **)(_QWORD))(v7 + 112))(*a2);
  v18 = v17;
  if ( v17 && memcmp_0(v17, &qword_1800B3930, 0x10u) || (v54 = UuidCreate(v18)) == 0 )
  {
    v19 = gBfeObjMgr;
    v65 = 0;
    v64 = 0;
    if ( v5 >= 7 || !*(_DWORD *)(v6 + gBfeObjMgr) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v20 = v6 + v19;
    v21 = *(_QWORD *)v18->Data4 ^ *(_QWORD *)&v18->Data1;
    v22 = -1;
    if ( !v21 )
      v21 = -1;
    for ( i = RtlLookupEntryHashTable(v6 + v19 + 240, v21, &v64); ; i = RtlGetNextEntryHashTable(v20 + 240, &v64) )
    {
      if ( !i )
        goto LABEL_27;
      v42 = i - 16;
      Key = (_QWORD *)BfeObjectGetKey(i - 16);
      v44 = *Key - *(_QWORD *)&v18->Data1;
      if ( *Key == *(_QWORD *)&v18->Data1 )
        v44 = Key[1] - *(_QWORD *)v18->Data4;
      if ( !v44 && (unsigned int)BfeObjectIsVisible(v42) )
        break;
    }
    BfeObjectIsVisible(v42);
    if ( v42 )
    {
LABEL_90:
      v45 = 2150760457LL;
      v46 = "BfeObjectAdd";
      goto LABEL_105;
    }
LABEL_27:
    *((_QWORD *)v12 + 4) = *(_QWORD *)v18->Data4 ^ *(_QWORD *)&v18->Data1;
    Feature_Servicing_BFEObjectLocking__private_ReportDeviceUsage();
    v8 = 0;
    v24 = *((_QWORD *)v12 + 4);
    if ( !v24 )
    {
      *((_QWORD *)v12 + 4) = -1;
      v24 = -1;
    }
    if ( !(unsigned __int8)RtlInsertEntryHashTable(v7 + 240, v12 + 16, v24, 0) )
    {
      v8 = WfpReportSysErrorAsNtStatus(v25, "RtlCreateHashTable", 3221225495LL);
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v58, 0, (__int64)"WfpHashtableInsert", v8);
        }
        if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
        {
          LODWORD(v60) = v8;
          v65 = "WfpHashtableInsert";
          v66 = 19;
          v67 = &v60;
          v68 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
            (unsigned int)WFP_USERMODE_ERROR,
            v58,
            3,
            (__int64)&v64);
          goto LABEL_80;
        }
      }
    }
    if ( !v8 )
    {
      WfpRestructureHashtable(v7 + 240);
      *((_DWORD *)v12 + 2) |= 0x20u;
      if ( (v12[8] & 1) != 0 )
      {
        v29 = BfeObjectSecurityLoad(*(PSECURITY_DESCRIPTOR *)(v7 + 344), 0, (__int64)(v12 + 112));
      }
      else
      {
        v26 = (__int64 *)TlsGetValue(gBfeContextComponent);
        if ( v26 && (v27 = *v26) != 0 )
          v28 = *(void **)(v27 + 40);
        else
          v28 = 0;
        v29 = BfeObjectSecurityCreate(
                *(PSECURITY_DESCRIPTOR *)(v7 + 344),
                CreatorDescriptor,
                0,
                v28,
                (__int64)(v12 + 112));
      }
      v8 = v29;
      if ( !v29 )
      {
        if ( !v12 || !*(_QWORD *)v12 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v8 = (*(__int64 (__fastcall **)(char *, _QWORD *))(v7 + 88))(v12 + 144, v62);
        if ( !v8 )
        {
          *((_DWORD *)v12 + 2) |= 0x10u;
          if ( !*(_DWORD *)(v7 + 336) )
            goto LABEL_72;
          if ( !v12 || !*(_QWORD *)v12 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            if ( !v12 || !*(_QWORD *)v12 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          v30 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 104LL))(v12 + 144);
          v31 = gBfeObjMgr;
          v32 = v30;
          v64 = 0;
          v65 = 0;
          if ( a1 >= 7 || !*(_DWORD *)(v6 + gBfeObjMgr) )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( *(_DWORD *)(v6 + v31 + 336) )
          {
            v33 = v6 + v31;
            RtlAcquireSRWLockShared(v6 + v31 + 328);
            v34 = v32;
            if ( !v32 )
              v34 = -1;
            v35 = v31 + v6;
            for ( j = RtlLookupEntryHashTable(v35 + 288, v34, &v64); j; j = RtlGetNextEntryHashTable(v35 + 288, &v64) )
            {
              v37 = (_BYTE *)(j - 40);
              if ( j == 40 || !*(_QWORD *)v37 )
                MicrosoftTelemetryAssertTriggeredNoArgs();
              if ( (v37[8] & 8) == 0 )
              {
                if ( !*(_QWORD *)v37 )
                {
                  MicrosoftTelemetryAssertTriggeredNoArgs();
                  if ( !*(_QWORD *)v37 )
                    MicrosoftTelemetryAssertTriggeredNoArgs();
                }
                if ( (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v37 + 104LL))(v37 + 144) == v32 )
                {
                  v8 = (__int64)v37;
                  break;
                }
              }
            }
            RtlReleaseSRWLockShared(v33 + 328);
            if ( v8 )
              goto LABEL_90;
            v22 = -1;
          }
          *((_QWORD *)v12 + 7) = v32;
          Feature_Servicing_BFEObjectLocking__private_ReportDeviceUsage();
          RtlAcquireSRWLockExclusive(v7 + 328);
          v39 = 0;
          if ( *((_QWORD *)v12 + 7) )
            v22 = *((_QWORD *)v12 + 7);
          else
            *((_QWORD *)v12 + 7) = -1;
          if ( (unsigned __int8)RtlInsertEntryHashTable(v7 + 288, v12 + 40, v22, 0) )
            goto LABEL_69;
          v39 = WfpReportSysErrorAsNtStatus(v40, "RtlCreateHashTable", 3221225495LL);
          if ( !v39 )
            goto LABEL_69;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v57, 0, (__int64)"WfpHashtableInsert", v39);
          }
          if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
          {
            LODWORD(v60) = v39;
            v67 = &v60;
            v65 = "WfpHashtableInsert";
            v66 = 19;
            v68 = 4;
            McGenEventWrite_EtwEventWriteTransfer(
              (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
              (unsigned int)WFP_USERMODE_ERROR,
              v57,
              3,
              (__int64)&v64);
            v8 = v39;
          }
          else
          {
LABEL_69:
            v8 = v39;
            if ( !v39 )
            {
              WfpRestructureHashtable(v7 + 288);
              *((_DWORD *)v12 + 2) |= 0x40u;
            }
          }
          RtlReleaseSRWLockExclusive(v7 + 328);
          if ( !v39 )
          {
LABEL_72:
            if ( (v12[8] & 2) != 0 )
            {
              BfeSessionRundownDestroy(v12 + 120);
              *((_QWORD *)v12 + 15) = 0;
              *(_DWORD *)(gBfeObjMgr + 2856) = 1;
            }
            if ( v63 )
            {
              *v63 = v12;
              goto LABEL_76;
            }
            goto LABEL_106;
          }
        }
      }
    }
LABEL_80:
    v5 = a1;
    goto LABEL_81;
  }
  v45 = v54;
  v46 = "UuidCreate";
LABEL_105:
  v8 = WfpReportSysErrorAsWinError(v38, v46, v45);
LABEL_76:
  if ( v8 )
    goto LABEL_80;
  return v8;
}

```

## disassembly

```asm
0x18000aef4  push    rbp
0x18000aef6  push    rbx
0x18000aef7  push    rsi
0x18000aef8  push    rdi
0x18000aef9  push    r12
0x18000aefb  push    r13
0x18000aefd  push    r14
0x18000aeff  push    r15
0x18000af01  lea     rbp, [rsp-1Fh]
0x18000af06  sub     rsp, 98h
0x18000af0d  mov     rax, cs:__security_cookie
0x18000af14  xor     rax, rsp
0x18000af17  mov     [rbp+57h+var_48], rax
0x18000af1b  mov     r13, cs:gBfeObjMgr
0x18000af22  mov     r12, rdx
0x18000af25  movsxd  r14, ecx
0x18000af28  imul    r15, r14, 198h
0x18000af2f  mov     [rbp+57h+var_80], r9
0x18000af33  add     r13, r15
0x18000af36  mov     [rbp+57h+CreatorDescriptor], r8
0x18000af3a  mov     [rbp+57h+var_88], rdx
0x18000af3e  mov     [rbp+57h+var_A0], r14d
0x18000af42  mov     [rbp+57h+var_98], 0
0x18000af4a  cmp     r14d, 7
0x18000af4e  jnb     short loc_18000AF57
0x18000af50  cmp     dword ptr [r13+0], 0
0x18000af55  jnz     short loc_18000AF5C
0x18000af57  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000af5c  mov     rcx, [r13+158h]; pSecurityDescriptor
0x18000af63  xor     r8d, r8d
0x18000af66  lea     edx, [r8+1]
0x18000af6a  call    BfeAccessCheck
0x18000af6f  mov     rdi, rax
0x18000af72  test    rax, rax
0x18000af75  jnz     loc_18000B590
0x18000af7b  mov     rbx, [r13+40h]
0x18000af7f  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000af84  lea     edx, [rdi+8]; dwFlags
0x18000af87  test    eax, eax
0x18000af89  jnz     short loc_18000B001
0x18000af8b  mov     rcx, cs:gWfpHeap; hHeap
0x18000af92  lea     r8, [rbx+90h]; dwBytes
0x18000af99  call    cs:__imp_HeapAlloc
0x18000af9f  mov     rsi, rax
0x18000afa2  test    rax, rax
0x18000afa5  jz      loc_18000B60E
0x18000afab  cmp     cs:gWfpTrackHeapBytes, edi
0x18000afb1  jnz     loc_18000B672
0x18000afb7  test    rdi, rdi
0x18000afba  jnz     loc_18000B3FA
0x18000afc0  mov     [rsi], r13
0x18000afc3  call    BfeIterateAssociationEnterLock
0x18000afc8  lea     rax, [rsi+50h]
0x18000afcc  mov     [rax+8], rax
0x18000afd0  mov     [rax], rax
0x18000afd3  lea     rax, [rsi+60h]
0x18000afd7  mov     [rax+8], rax
0x18000afdb  mov     [rax], rax
0x18000afde  call    BfeIterateAssociationLeaveLock
0x18000afe3  lea     rax, [r13+160h]
0x18000afea  mov     rdx, [rax+8]
0x18000afee  lea     rcx, [rsi+80h]
0x18000aff5  cmp     [rdx], rax
0x18000aff8  jz      short loc_18000B01A
0x18000affa  mov     ecx, 3
0x18000afff  int     29h; Win8: RtlFailFast(ecx)
0x18000b001  lea     r8, [rbp+57h+var_98]
0x18000b005  lea     rcx, [rbx+90h]; dwBytes
0x18000b00c  call    WfpMemAlloc25B
0x18000b011  mov     rsi, [rbp+57h+var_98]
0x18000b015  mov     rdi, rax
0x18000b018  jmp     short loc_18000AFB7
0x18000b01a  mov     [rcx], rax
0x18000b01d  mov     [rcx+8], rdx
0x18000b021  mov     [rdx], rcx
0x18000b024  mov     [rax+8], rcx
0x18000b028  or      dword ptr [rsi+8], 4
0x18000b02c  mov     rax, cs:gBfeObjMgr
0x18000b033  cmp     dword ptr [rax+0B2Ch], 0
0x18000b03a  jz      loc_18000B7EF
0x18000b040  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000b046  call    cs:__imp_TlsGetValue
0x18000b04c  test    rax, rax
0x18000b04f  jz      short loc_18000B067
0x18000b051  mov     rax, [rax]
0x18000b054  test    rax, rax
0x18000b057  jz      short loc_18000B067
0x18000b059  mov     rax, [rax+10h]
0x18000b05d  test    byte ptr [rax+20h], 1
0x18000b061  jnz     loc_18000B48C
0x18000b067  mov     rcx, [r12]
0x18000b06b  mov     rax, [r13+70h]
0x18000b06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b074  mov     rbx, rax
0x18000b077  test    rax, rax
0x18000b07a  jz      loc_18000B568
0x18000b080  mov     r8d, 10h; Size
0x18000b086  lea     rdx, qword_1800B3930; Buf2
0x18000b08d  mov     rcx, rax; Buf1
0x18000b090  call    memcmp_0
0x18000b095  test    eax, eax
0x18000b097  jz      loc_18000B568
0x18000b09d  mov     rdi, cs:gBfeObjMgr
0x18000b0a4  xor     eax, eax
0x18000b0a6  mov     [rbp+57h+var_68], rax
0x18000b0aa  xorps   xmm0, xmm0
0x18000b0ad  movups  [rbp+57h+var_78], xmm0
0x18000b0b1  cmp     r14d, 7
0x18000b0b5  jnb     short loc_18000B0BD
0x18000b0b7  cmp     [r15+rdi], eax
0x18000b0bb  jnz     short loc_18000B0C2
0x18000b0bd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b0c2  mov     rdx, [rbx]
0x18000b0c5  lea     r14, [r15+rdi]
0x18000b0c9  xor     rdx, [rbx+8]
0x18000b0cd  lea     r8, [rbp+57h+var_78]
0x18000b0d1  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000b0d8  lea     rcx, [r14+0F0h]
0x18000b0df  cmovz   rdx, r12
0x18000b0e3  call    cs:__imp_RtlLookupEntryHashTable
0x18000b0e9  test    rax, rax
0x18000b0ec  jnz     loc_18000B434
0x18000b0f2  mov     rax, [rbx]
0x18000b0f5  xor     rax, [rbx+8]
0x18000b0f9  mov     [rsi+20h], rax
0x18000b0fd  call    Feature_Servicing_BFEObjectLocking__private_ReportDeviceUsage
0x18000b102  lea     rdx, [rsi+10h]
0x18000b106  xor     edi, edi
0x18000b108  mov     r8, [rdx+10h]
0x18000b10c  test    r8, r8
0x18000b10f  jnz     short loc_18000B118
0x18000b111  mov     [rdx+10h], r12
0x18000b115  mov     r8, r12
0x18000b118  lea     r14, [r13+0F0h]
0x18000b11f  xor     r9d, r9d
0x18000b122  mov     rcx, r14
0x18000b125  call    cs:__imp_RtlInsertEntryHashTable
0x18000b12b  test    al, al
0x18000b12d  jz      loc_18000B77F
0x18000b133  test    rdi, rdi
0x18000b136  jnz     loc_18000B3F6
0x18000b13c  mov     rcx, r14
0x18000b13f  call    WfpRestructureHashtable
0x18000b144  or      dword ptr [rsi+8], 20h
0x18000b148  test    byte ptr [rsi+8], 1
0x18000b14c  jnz     loc_18000B7F8
0x18000b152  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000b158  call    cs:__imp_TlsGetValue
0x18000b15e  test    rax, rax
0x18000b161  jz      loc_18000B5EA
0x18000b167  mov     rax, [rax]
0x18000b16a  test    rax, rax
0x18000b16d  jz      loc_18000B5EA
0x18000b173  mov     r9, [rax+28h]; Token
0x18000b177  mov     rdx, [rbp+57h+CreatorDescriptor]; CreatorDescriptor
0x18000b17b  lea     rax, [rsi+70h]
0x18000b17f  mov     rcx, [r13+158h]; ParentDescriptor
0x18000b186  xor     r8d, r8d; IsContainerObject
0x18000b189  mov     qword ptr [rsp+0D0h+IsContainerObject], rax; __int64
0x18000b18e  call    BfeObjectSecurityCreate
0x18000b193  mov     rdi, rax
0x18000b196  test    rax, rax
0x18000b199  jnz     loc_18000B3F6
0x18000b19f  test    rsi, rsi
0x18000b1a2  jz      short loc_18000B1AA
0x18000b1a4  cmp     qword ptr [rsi], 0
0x18000b1a8  jnz     short loc_18000B1AF
0x18000b1aa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b1af  mov     rdx, [rbp+57h+var_88]
0x18000b1b3  lea     rbx, [rsi+90h]
0x18000b1ba  mov     rax, [r13+58h]
0x18000b1be  mov     rcx, rbx
0x18000b1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1c6  mov     rdi, rax
0x18000b1c9  test    rax, rax
0x18000b1cc  jnz     loc_18000B3F6
0x18000b1d2  or      dword ptr [rsi+8], 10h
0x18000b1d6  cmp     [r13+150h], eax
0x18000b1dd  jz      loc_18000B35F
0x18000b1e3  test    rsi, rsi
0x18000b1e6  jz      short loc_18000B1ED
0x18000b1e8  cmp     [rsi], rax
0x18000b1eb  jnz     short loc_18000B201
0x18000b1ed  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b1f2  test    rsi, rsi
0x18000b1f5  jz      short loc_18000B1FC
0x18000b1f7  cmp     [rsi], rdi
0x18000b1fa  jnz     short loc_18000B201
0x18000b1fc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b201  mov     rax, [rsi]
0x18000b204  mov     rcx, rbx
0x18000b207  mov     rax, [rax+68h]
0x18000b20b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b210  mov     rbx, cs:gBfeObjMgr
0x18000b217  mov     r14, rax
0x18000b21a  xor     eax, eax
0x18000b21c  xorps   xmm0, xmm0
0x18000b21f  cmp     [rbp+57h+var_A0], 7
0x18000b223  movups  [rbp+57h+var_78], xmm0
0x18000b227  mov     [rbp+57h+var_68], rax
0x18000b22b  jnb     short loc_18000B233
0x18000b22d  cmp     [r15+rbx], edi
0x18000b231  jnz     short loc_18000B238
0x18000b233  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b238  cmp     [r15+rbx+150h], edi
0x18000b240  jz      loc_18000B2ED
0x18000b246  lea     r12, [r15+rbx]
0x18000b24a  lea     rcx, [r12+148h]
0x18000b252  call    cs:__imp_RtlAcquireSRWLockShared
0x18000b258  test    r14, r14
0x18000b25b  lea     r8, [rbp+57h+var_78]
0x18000b25f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000b266  mov     rdx, r14
0x18000b269  cmovz   rdx, rax
0x18000b26d  add     r15, rbx
0x18000b270  lea     rcx, [r15+120h]
0x18000b277  call    cs:__imp_RtlLookupEntryHashTable
0x18000b27d  test    rax, rax
0x18000b280  jz      short loc_18000B2D2
0x18000b282  lea     rbx, [rax-28h]
0x18000b286  test    rbx, rbx
0x18000b289  jz      short loc_18000B290
0x18000b28b  cmp     [rbx], rdi
0x18000b28e  jnz     short loc_18000B295
0x18000b290  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b295  test    byte ptr [rbx+8], 8
0x18000b299  jnz     loc_18000B549
0x18000b29f  cmp     [rbx], rdi
0x18000b2a2  jnz     short loc_18000B2B3
0x18000b2a4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b2a9  cmp     [rbx], rdi
0x18000b2ac  jnz     short loc_18000B2B3
0x18000b2ae  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b2b3  mov     rax, [rbx]
0x18000b2b6  lea     rcx, [rbx+90h]
0x18000b2bd  mov     rax, [rax+68h]
0x18000b2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2c6  cmp     rax, r14
0x18000b2c9  jnz     loc_18000B549
0x18000b2cf  mov     rdi, rbx
0x18000b2d2  lea     rcx, [r12+148h]
0x18000b2da  call    cs:__imp_RtlReleaseSRWLockShared
0x18000b2e0  test    rdi, rdi
0x18000b2e3  jnz     loc_18000B47A
0x18000b2e9  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000b2ed  mov     [rsi+38h], r14
0x18000b2f1  call    Feature_Servicing_BFEObjectLocking__private_ReportDeviceUsage
0x18000b2f6  lea     r15, [r13+148h]
0x18000b2fd  mov     rcx, r15
0x18000b300  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000b306  lea     rdx, [rsi+28h]
0x18000b30a  mov     rbx, rdi
0x18000b30d  cmp     [rdx+10h], rdi
0x18000b311  jnz     loc_18000B55F
0x18000b317  mov     [rdx+10h], r12
0x18000b31b  lea     r14, [r13+120h]
0x18000b322  xor     r9d, r9d
0x18000b325  mov     rcx, r14
0x18000b328  mov     r8, r12
0x18000b32b  call    cs:__imp_RtlInsertEntryHashTable
0x18000b331  test    al, al
0x18000b333  jz      loc_18000B6AE
0x18000b339  mov     rdi, rbx
0x18000b33c  test    rbx, rbx
0x18000b33f  jnz     short loc_18000B34D
0x18000b341  mov     rcx, r14
0x18000b344  call    WfpRestructureHashtable
0x18000b349  or      dword ptr [rsi+8], 40h
0x18000b34d  mov     rcx, r15
0x18000b350  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000b356  test    rbx, rbx
0x18000b359  jnz     loc_18000B3F6
0x18000b35f  test    byte ptr [rsi+8], 2
0x18000b363  jnz     loc_18000B5C3
0x18000b369  mov     rax, [rbp+57h+var_80]
0x18000b36d  test    rax, rax
0x18000b370  jz      loc_18000B590
0x18000b376  mov     [rax], rsi
0x18000b379  test    rdi, rdi
0x18000b37c  jnz     short loc_18000B3F6
0x18000b37e  mov     rax, rdi
0x18000b381  mov     rcx, [rbp+57h+var_48]
0x18000b385  xor     rcx, rsp; StackCookie
0x18000b388  call    __security_check_cookie
0x18000b38d  add     rsp, 98h
0x18000b394  pop     r15
0x18000b396  pop     r14
0x18000b398  pop     r13
0x18000b39a  pop     r12
0x18000b39c  pop     rdi
0x18000b39d  pop     rsi
0x18000b39e  pop     rbx
0x18000b39f  pop     rbp
0x18000b3a0  retn
0x18000b3a1  test    cs:byte_1800F30F5, 1
0x18000b3a8  jz      loc_18000B133
0x18000b3ae  lea     rax, aWfphashtablein; "WfpHashtableInsert"
0x18000b3b5  mov     dword ptr [rbp+57h+var_98], edi
0x18000b3b8  mov     [rbp+57h+var_68], rax
0x18000b3bc  lea     rdx, WFP_USERMODE_ERROR
  ... truncated ...
```
