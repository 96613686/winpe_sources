# BfeObjectAdd

- ea: `0x18000b5b4`
- end: `0x18000bf29`
- name: `BfeObjectAdd`
- size: `2421`
- prototype: ``
- caller_count: `6`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180009220`
- `0x18000a770`
- `0x18000ada0`
- `0x180030154`
- `0x180058b30`
- `0x1800641c0`

## callees

- `0x1800051ac`
- `0x180006584`
- `0x180007958`
- `0x18000798c`
- `0x1800084ec`
- `0x1800087f0`
- `0x180008868`
- `0x1800088f0`
- `0x180008adc`
- `0x18000b5b4`
- `0x18000fb34`
- `0x180010d60`
- `0x180011510`
- `0x180012d8c`
- `0x1800135ac`
- `0x180013640`
- `0x1800197d0`
- `0x180031aa8`
- `0x180036e40`
- `0x1800383f0`
- `0x18004fb50`
- `0x1800560f8`
- `0x1800592f4`
- `0x18005aa60`
- `0x18008ad60`
- `0x18008e010`

## import_xrefs

- `ntdll!RtlInsertEntryHashTable` at `0x18000b7f7`
- `ntdll!RtlInsertEntryHashTable` at `0x18000b9f9`
- `ntdll!RtlInsertEntryHashTable` at `0x18000b7f7`
- `ntdll!RtlInsertEntryHashTable` at `0x18000b9f9`
- `ntdll!RtlLookupEntryHashTable` at `0x18000b7af`
- `ntdll!RtlLookupEntryHashTable` at `0x18000b95b`
- `ntdll!RtlLookupEntryHashTable` at `0x18000b7af`
- `ntdll!RtlLookupEntryHashTable` at `0x18000b95b`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000bc8f`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000bcf6`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000bc8f`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000bcf6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b9c8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b9c8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ba24`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ba24`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000b930`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000b930`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000b99c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000b99c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b659`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bbab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b659`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bbab`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000bd77`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000bd9b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000bd77`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000bd9b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b70c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b830`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000bb6d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b70c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b830`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000bb6d`
- `RPCRT4!UuidCreate` at `0x18000bc3c`
- `RPCRT4!UuidCreate` at `0x18000bc3c`

## string_xrefs

- `0x18000bc53`: `UuidCreate`
- `0x18000bdb9`: `RtlCreateHashTable`
- `0x18000be8a`: `RtlCreateHashTable`
- `0x18000bcd7`: `BfeSessionRundownCreate`

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
  __int64 v37; // rbx
  __int64 v38; // rcx
  __int64 v39; // rbx
  __int64 v40; // rcx
  __int64 PublicState; // rax
  __int64 v43; // rdi
  _QWORD *Key; // rax
  __int64 v45; // rcx
  __int64 v46; // r8
  const char *v47; // rdx
  __int64 *v48; // rax
  __int64 v49; // r14
  char *v50; // rax
  __int64 v51; // rcx
  char *v52; // rbx
  __int64 v53; // rax
  char **v54; // rcx
  unsigned int v55; // eax
  __int64 v56; // rax
  __int64 v57; // rax
  int v58; // r8d
  int v59; // r8d
  char *v61; // [rsp+38h] [rbp-41h] BYREF
  PSECURITY_DESCRIPTOR CreatorDescriptor; // [rsp+40h] [rbp-39h]
  _QWORD *v63; // [rsp+48h] [rbp-31h]
  _QWORD *v64; // [rsp+50h] [rbp-29h]
  __int128 v65; // [rsp+58h] [rbp-21h] BYREF
  const char *v66; // [rsp+68h] [rbp-11h]
  __int64 v67; // [rsp+70h] [rbp-9h]
  char **v68; // [rsp+78h] [rbp-1h]
  __int64 v69; // [rsp+80h] [rbp+7h]

  v5 = a1;
  v6 = 408LL * (int)a1;
  v64 = a4;
  v7 = v6 + gBfeObjMgr;
  CreatorDescriptor = a3;
  v63 = a2;
  v61 = 0;
  if ( a1 >= 7 || !*(_DWORD *)v7 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v8 = BfeAccessCheck(*(char **)(v7 + 344), 1u, 0);
  if ( v8 )
    goto LABEL_99;
  v9 = *(_QWORD *)(v7 + 64);
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
  {
    v12 = v61;
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
      v56 = WfpReportSysErrorAsNtStatus(v11, "HeapAlloc", 3221225495LL);
      v8 = v56;
      if ( v56 )
        WfpReportError(v56, "WfpMemAlloc");
    }
  }
  if ( v8 )
  {
LABEL_75:
    if ( v12 )
    {
      if ( !*v63 && (v12[8] & 0x10) != 0 )
      {
        PublicState = BfeObjectGetPublicState(v12);
        BfeObjectTraceAddFailure(v5, PublicState);
      }
      BfeObjectDeleteAlways(v12);
    }
LABEL_99:
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
        v48 = (__int64 *)TlsGetValue(gBfeContextComponent);
        if ( v48 )
          v49 = *v48;
        else
          v49 = 0;
        v61 = 0;
        *((_QWORD *)v12 + 15) = 0;
        if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
        {
          v52 = v61;
          v8 = WfpMemAlloc25B(0x28u);
        }
        else
        {
          v50 = (char *)HeapAlloc(gWfpHeap, 0, 0x28u);
          v52 = v50;
          if ( v50 )
          {
            v8 = 0;
            if ( gWfpTrackHeapBytes )
              _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v50));
          }
          else
          {
            v57 = WfpReportSysErrorAsNtStatus(v51, "HeapAlloc", 3221225495LL);
            v8 = v57;
            if ( v57 )
              WfpReportError(v57, "WfpMemAlloc");
          }
        }
        if ( v8 )
        {
          WfpReportError(v8, "BfeSessionRundownCreate");
          goto LABEL_74;
        }
        *((_QWORD *)v52 + 2) = v49;
        *((_QWORD *)v52 + 3) = BfeObjectDeleteAlways;
        v53 = v49 + 64;
        *((_QWORD *)v52 + 4) = v12;
        v54 = *(char ***)(v49 + 72);
        if ( *v54 != (char *)(v49 + 64) )
LABEL_11:
          __fastfail(3u);
        v5 = a1;
        *(_QWORD *)v52 = v53;
        *((_QWORD *)v52 + 1) = v54;
        *v54 = v52;
        *(_QWORD *)(v53 + 8) = v52;
        *((_QWORD *)v12 + 15) = v52;
      }
    }
  }
  v17 = (UUID *)(*(__int64 (__fastcall **)(_QWORD))(v7 + 112))(*a2);
  v18 = v17;
  if ( v17 && memcmp_0(v17, &qword_1800B69A8, 0x10u) || (v55 = UuidCreate(v18)) == 0 )
  {
    v19 = gBfeObjMgr;
    v66 = 0;
    v65 = 0;
    if ( v5 >= 7 || !*(_DWORD *)(v6 + gBfeObjMgr) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v20 = v6 + v19;
    v21 = *(_QWORD *)&v18->Data1 ^ *(_QWORD *)v18->Data4;
    v22 = -1;
    if ( !v21 )
      v21 = -1;
    for ( i = RtlLookupEntryHashTable(v6 + v19 + 240, v21, &v65); ; i = RtlGetNextEntryHashTable(v20 + 240, &v65) )
    {
      if ( !i )
        goto LABEL_27;
      v43 = i - 16;
      Key = (_QWORD *)BfeObjectGetKey(i - 16);
      v45 = *Key - *(_QWORD *)&v18->Data1;
      if ( *Key == *(_QWORD *)&v18->Data1 )
        v45 = Key[1] - *(_QWORD *)v18->Data4;
      if ( !v45 && (unsigned int)BfeObjectIsVisible(v43) )
        break;
    }
    BfeObjectIsVisible(v43);
    if ( v43 )
    {
LABEL_84:
      v46 = 2150760457LL;
      v47 = "BfeObjectAdd";
      goto LABEL_98;
    }
LABEL_27:
    *((_QWORD *)v12 + 4) = *(_QWORD *)&v18->Data1 ^ *(_QWORD *)v18->Data4;
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
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v59, 0, (__int64)"WfpHashtableInsert", v8);
        }
        if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
        {
          LODWORD(v61) = v8;
          v66 = "WfpHashtableInsert";
          v67 = 19;
          v68 = &v61;
          v69 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
            (unsigned int)WFP_USERMODE_ERROR,
            v59,
            3,
            (__int64)&v65);
          goto LABEL_74;
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
        v29 = BfeObjectSecurityCreate(*(char **)(v7 + 344), CreatorDescriptor, 0, v28, (_QWORD *)v12 + 14);
      }
      v8 = v29;
      if ( !v29 )
      {
        if ( !v12 || !*(_QWORD *)v12 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v8 = (*(__int64 (__fastcall **)(char *, _QWORD *))(v7 + 88))(v12 + 144, v63);
        if ( !v8 )
        {
          *((_DWORD *)v12 + 2) |= 0x10u;
          if ( !*(_DWORD *)(v7 + 336) )
            goto LABEL_66;
          if ( !v12 || !*(_QWORD *)v12 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            if ( !v12 || !*(_QWORD *)v12 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          v30 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 104LL))(v12 + 144);
          v31 = gBfeObjMgr;
          v32 = v30;
          v65 = 0;
          v66 = 0;
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
            for ( j = RtlLookupEntryHashTable(v35 + 288, v34, &v65); j; j = RtlGetNextEntryHashTable(v35 + 288, &v65) )
            {
              v37 = j - 40;
              if ( (unsigned int)BfeObjectIsVisible(j - 40) && BfeObjectGetId(v37) == v32 )
              {
                v8 = v37;
                break;
              }
            }
            RtlReleaseSRWLockShared(v33 + 328);
            if ( v8 )
              goto LABEL_84;
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
            goto LABEL_63;
          v39 = WfpReportSysErrorAsNtStatus(v40, "RtlCreateHashTable", 3221225495LL);
          if ( !v39 )
            goto LABEL_63;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v58, 0, (__int64)"WfpHashtableInsert", v39);
          }
          if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
          {
            LODWORD(v61) = v39;
            v68 = &v61;
            v66 = "WfpHashtableInsert";
            v67 = 19;
            v69 = 4;
            McGenEventWrite_EtwEventWriteTransfer(
              (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
              (unsigned int)WFP_USERMODE_ERROR,
              v58,
              3,
              (__int64)&v65);
            v8 = v39;
          }
          else
          {
LABEL_63:
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
LABEL_66:
            if ( (v12[8] & 2) != 0 )
            {
              BfeSessionRundownDestroy(v12 + 120);
              *((_QWORD *)v12 + 15) = 0;
              *(_DWORD *)(gBfeObjMgr + 2856) = 1;
            }
            if ( v64 )
            {
              *v64 = v12;
              goto LABEL_70;
            }
            goto LABEL_99;
          }
        }
      }
    }
LABEL_74:
    v5 = a1;
    goto LABEL_75;
  }
  v46 = v55;
  v47 = "UuidCreate";
LABEL_98:
  v8 = WfpReportSysErrorAsWinError(v38, v47, v46);
LABEL_70:
  if ( v8 )
    goto LABEL_74;
  return v8;
}

```

## disassembly

```asm
0x18000b5b4  push    rbp
0x18000b5b6  push    rbx
0x18000b5b7  push    rsi
0x18000b5b8  push    rdi
0x18000b5b9  push    r12
0x18000b5bb  push    r13
0x18000b5bd  push    r14
0x18000b5bf  push    r15
0x18000b5c1  lea     rbp, [rsp-1Fh]
0x18000b5c6  sub     rsp, 98h
0x18000b5cd  mov     rax, cs:__security_cookie
0x18000b5d4  xor     rax, rsp
0x18000b5d7  mov     [rbp+57h+var_48], rax
0x18000b5db  mov     r13, cs:gBfeObjMgr
0x18000b5e2  mov     r12, rdx
0x18000b5e5  movsxd  r14, ecx
0x18000b5e8  imul    r15, r14, 198h
0x18000b5ef  mov     [rbp+57h+var_80], r9
0x18000b5f3  add     r13, r15
0x18000b5f6  mov     [rbp+57h+CreatorDescriptor], r8
0x18000b5fa  mov     [rbp+57h+var_88], rdx
0x18000b5fe  mov     [rbp+57h+var_A0], r14d
0x18000b602  mov     [rbp+57h+var_98], 0
0x18000b60a  cmp     r14d, 7
0x18000b60e  jnb     short loc_18000B617
0x18000b610  cmp     dword ptr [r13+0], 0
0x18000b615  jnz     short loc_18000B61C
0x18000b617  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b61c  mov     rcx, [r13+158h]; pSecurityDescriptor
0x18000b623  xor     r8d, r8d
0x18000b626  lea     edx, [r8+1]
0x18000b62a  call    BfeAccessCheck
0x18000b62f  mov     rdi, rax
0x18000b632  test    rax, rax
0x18000b635  jnz     loc_18000BC67
0x18000b63b  mov     rbx, [r13+40h]
0x18000b63f  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000b644  lea     edx, [rdi+8]; dwFlags
0x18000b647  test    eax, eax
0x18000b649  jnz     short loc_18000B6C7
0x18000b64b  mov     rcx, cs:gWfpHeap; hHeap
0x18000b652  lea     r8, [rbx+90h]; dwBytes
0x18000b659  call    cs:__imp_HeapAlloc
0x18000b660  nop     dword ptr [rax+rax+00h]
0x18000b665  mov     rsi, rax
0x18000b668  test    rax, rax
0x18000b66b  jz      loc_18000BD07
0x18000b671  cmp     cs:gWfpTrackHeapBytes, edi
0x18000b677  jnz     loc_18000BD6B
0x18000b67d  test    rdi, rdi
0x18000b680  jnz     loc_18000BAD5
0x18000b686  mov     [rsi], r13
0x18000b689  call    BfeIterateAssociationEnterLock
0x18000b68e  lea     rax, [rsi+50h]
0x18000b692  mov     [rax+8], rax
0x18000b696  mov     [rax], rax
0x18000b699  lea     rax, [rsi+60h]
0x18000b69d  mov     [rax+8], rax
0x18000b6a1  mov     [rax], rax
0x18000b6a4  call    BfeIterateAssociationLeaveLock
0x18000b6a9  lea     rax, [r13+160h]
0x18000b6b0  mov     rdx, [rax+8]
0x18000b6b4  lea     rcx, [rsi+80h]
0x18000b6bb  cmp     [rdx], rax
0x18000b6be  jz      short loc_18000B6E0
0x18000b6c0  mov     ecx, 3
0x18000b6c5  int     29h; Win8: RtlFailFast(ecx)
0x18000b6c7  lea     r8, [rbp+57h+var_98]
0x18000b6cb  lea     rcx, [rbx+90h]; dwBytes
0x18000b6d2  call    WfpMemAlloc25B
0x18000b6d7  mov     rsi, [rbp+57h+var_98]
0x18000b6db  mov     rdi, rax
0x18000b6de  jmp     short loc_18000B67D
0x18000b6e0  mov     [rcx], rax
0x18000b6e3  mov     [rcx+8], rdx
0x18000b6e7  mov     [rdx], rcx
0x18000b6ea  mov     [rax+8], rcx
0x18000b6ee  or      dword ptr [rsi+8], 4
0x18000b6f2  mov     rax, cs:gBfeObjMgr
0x18000b6f9  cmp     dword ptr [rax+0B2Ch], 0
0x18000b700  jz      loc_18000BEF4
0x18000b706  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000b70c  call    cs:__imp_TlsGetValue
0x18000b713  nop     dword ptr [rax+rax+00h]
0x18000b718  test    rax, rax
0x18000b71b  jz      short loc_18000B733
0x18000b71d  mov     rax, [rax]
0x18000b720  test    rax, rax
0x18000b723  jz      short loc_18000B733
0x18000b725  mov     rax, [rax+10h]
0x18000b729  test    byte ptr [rax+20h], 1
0x18000b72d  jnz     loc_18000BB67
0x18000b733  mov     rcx, [r12]
0x18000b737  mov     rax, [r13+70h]
0x18000b73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b740  mov     rbx, rax
0x18000b743  test    rax, rax
0x18000b746  jz      loc_18000BC39
0x18000b74c  mov     r8d, 10h; Size
0x18000b752  lea     rdx, qword_1800B69A8; Buf2
0x18000b759  mov     rcx, rax; Buf1
0x18000b75c  call    memcmp_0
0x18000b761  test    eax, eax
0x18000b763  jz      loc_18000BC39
0x18000b769  mov     rdi, cs:gBfeObjMgr
0x18000b770  xor     eax, eax
0x18000b772  mov     [rbp+57h+var_68], rax
0x18000b776  xorps   xmm0, xmm0
0x18000b779  movups  [rbp+57h+var_78], xmm0
0x18000b77d  cmp     r14d, 7
0x18000b781  jnb     short loc_18000B789
0x18000b783  cmp     [r15+rdi], eax
0x18000b787  jnz     short loc_18000B78E
0x18000b789  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b78e  mov     rdx, [rbx+8]
0x18000b792  lea     r14, [r15+rdi]
0x18000b796  xor     rdx, [rbx]
0x18000b799  lea     r8, [rbp+57h+var_78]
0x18000b79d  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000b7a4  lea     rcx, [r14+0F0h]
0x18000b7ab  cmovz   rdx, r12
0x18000b7af  call    cs:__imp_RtlLookupEntryHashTable
0x18000b7b6  nop     dword ptr [rax+rax+00h]
0x18000b7bb  test    rax, rax
0x18000b7be  jnz     loc_18000BB0F
0x18000b7c4  mov     rax, [rbx+8]
0x18000b7c8  xor     rax, [rbx]
0x18000b7cb  mov     [rsi+20h], rax
0x18000b7cf  call    Feature_Servicing_BFEObjectLocking__private_ReportDeviceUsage
0x18000b7d4  lea     rdx, [rsi+10h]
0x18000b7d8  xor     edi, edi
0x18000b7da  mov     r8, [rdx+10h]
0x18000b7de  test    r8, r8
0x18000b7e1  jnz     short loc_18000B7EA
0x18000b7e3  mov     [rdx+10h], r12
0x18000b7e7  mov     r8, r12
0x18000b7ea  lea     r14, [r13+0F0h]
0x18000b7f1  xor     r9d, r9d
0x18000b7f4  mov     rcx, r14
0x18000b7f7  call    cs:__imp_RtlInsertEntryHashTable
0x18000b7fe  nop     dword ptr [rax+rax+00h]
0x18000b803  test    al, al
0x18000b805  jz      loc_18000BE84
0x18000b80b  test    rdi, rdi
0x18000b80e  jnz     loc_18000BAD1
0x18000b814  mov     rcx, r14
0x18000b817  call    WfpRestructureHashtable
0x18000b81c  or      dword ptr [rsi+8], 20h
0x18000b820  test    byte ptr [rsi+8], 1
0x18000b824  jnz     loc_18000BEFD
0x18000b82a  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000b830  call    cs:__imp_TlsGetValue
0x18000b837  nop     dword ptr [rax+rax+00h]
0x18000b83c  test    rax, rax
0x18000b83f  jz      loc_18000BCC7
0x18000b845  mov     rax, [rax]
0x18000b848  test    rax, rax
0x18000b84b  jz      loc_18000BCC7
0x18000b851  mov     r9, [rax+28h]; Token
0x18000b855  mov     rdx, [rbp+57h+CreatorDescriptor]; CreatorDescriptor
0x18000b859  lea     rax, [rsi+70h]
0x18000b85d  mov     rcx, [r13+158h]; ParentDescriptor
0x18000b864  xor     r8d, r8d; IsContainerObject
0x18000b867  mov     qword ptr [rsp+0D0h+IsContainerObject], rax; __int64
0x18000b86c  call    BfeObjectSecurityCreate
0x18000b871  mov     rdi, rax
0x18000b874  test    rax, rax
0x18000b877  jnz     loc_18000BAD1
0x18000b87d  test    rsi, rsi
0x18000b880  jz      short loc_18000B888
0x18000b882  cmp     qword ptr [rsi], 0
0x18000b886  jnz     short loc_18000B88D
0x18000b888  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b88d  mov     rdx, [rbp+57h+var_88]
0x18000b891  lea     rbx, [rsi+90h]
0x18000b898  mov     rax, [r13+58h]
0x18000b89c  mov     rcx, rbx
0x18000b89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8a4  mov     rdi, rax
0x18000b8a7  test    rax, rax
0x18000b8aa  jnz     loc_18000BAD1
0x18000b8b0  or      dword ptr [rsi+8], 10h
0x18000b8b4  cmp     [r13+150h], eax
0x18000b8bb  jz      loc_18000BA39
0x18000b8c1  test    rsi, rsi
0x18000b8c4  jz      short loc_18000B8CB
0x18000b8c6  cmp     [rsi], rax
0x18000b8c9  jnz     short loc_18000B8DF
0x18000b8cb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b8d0  test    rsi, rsi
0x18000b8d3  jz      short loc_18000B8DA
0x18000b8d5  cmp     [rsi], rdi
0x18000b8d8  jnz     short loc_18000B8DF
0x18000b8da  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b8df  mov     rax, [rsi]
0x18000b8e2  mov     rcx, rbx
0x18000b8e5  mov     rax, [rax+68h]
0x18000b8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8ee  mov     rbx, cs:gBfeObjMgr
0x18000b8f5  mov     r14, rax
0x18000b8f8  xor     eax, eax
0x18000b8fa  xorps   xmm0, xmm0
0x18000b8fd  cmp     [rbp+57h+var_A0], 7
0x18000b901  movups  [rbp+57h+var_78], xmm0
0x18000b905  mov     [rbp+57h+var_68], rax
0x18000b909  jnb     short loc_18000B911
0x18000b90b  cmp     [r15+rbx], edi
0x18000b90f  jnz     short loc_18000B916
0x18000b911  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b916  cmp     [r15+rbx+150h], edi
0x18000b91e  jz      loc_18000B9B5
0x18000b924  lea     r12, [r15+rbx]
0x18000b928  lea     rcx, [r12+148h]
0x18000b930  call    cs:__imp_RtlAcquireSRWLockShared
0x18000b937  nop     dword ptr [rax+rax+00h]
0x18000b93c  test    r14, r14
0x18000b93f  lea     r8, [rbp+57h+var_78]
0x18000b943  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000b94a  mov     rdx, r14
0x18000b94d  cmovz   rdx, rax
0x18000b951  add     r15, rbx
0x18000b954  lea     rcx, [r15+120h]
0x18000b95b  call    cs:__imp_RtlLookupEntryHashTable
0x18000b962  nop     dword ptr [rax+rax+00h]
0x18000b967  test    rax, rax
0x18000b96a  jz      short loc_18000B994
0x18000b96c  lea     rbx, [rax-28h]
0x18000b970  mov     rcx, rbx
0x18000b973  call    BfeObjectIsVisible
0x18000b978  test    eax, eax
0x18000b97a  jz      loc_18000BCEB
0x18000b980  mov     rcx, rbx
0x18000b983  call    BfeObjectGetId
0x18000b988  cmp     rax, r14
0x18000b98b  jnz     loc_18000BCEB
0x18000b991  mov     rdi, rbx
0x18000b994  lea     rcx, [r12+148h]
0x18000b99c  call    cs:__imp_RtlReleaseSRWLockShared
0x18000b9a3  nop     dword ptr [rax+rax+00h]
0x18000b9a8  test    rdi, rdi
0x18000b9ab  jnz     loc_18000BB55
0x18000b9b1  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000b9b5  mov     [rsi+38h], r14
0x18000b9b9  call    Feature_Servicing_BFEObjectLocking__private_ReportDeviceUsage
0x18000b9be  lea     r15, [r13+148h]
0x18000b9c5  mov     rcx, r15
0x18000b9c8  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000b9cf  nop     dword ptr [rax+rax+00h]
0x18000b9d4  lea     rdx, [rsi+28h]
0x18000b9d8  mov     rbx, rdi
0x18000b9db  cmp     [rdx+10h], rdi
0x18000b9df  jnz     loc_18000BC30
0x18000b9e5  mov     [rdx+10h], r12
0x18000b9e9  lea     r14, [r13+120h]
0x18000b9f0  xor     r9d, r9d
0x18000b9f3  mov     rcx, r14
0x18000b9f6  mov     r8, r12
0x18000b9f9  call    cs:__imp_RtlInsertEntryHashTable
0x18000ba00  nop     dword ptr [rax+rax+00h]
0x18000ba05  test    al, al
0x18000ba07  jz      loc_18000BDB3
0x18000ba0d  mov     rdi, rbx
0x18000ba10  test    rbx, rbx
0x18000ba13  jnz     short loc_18000BA21
0x18000ba15  mov     rcx, r14
0x18000ba18  call    WfpRestructureHashtable
0x18000ba1d  or      dword ptr [rsi+8], 40h
0x18000ba21  mov     rcx, r15
0x18000ba24  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000ba2b  nop     dword ptr [rax+rax+00h]
0x18000ba30  test    rbx, rbx
0x18000ba33  jnz     loc_18000BAD1
0x18000ba39  test    byte ptr [rsi+8], 2
0x18000ba3d  jnz     loc_18000BCA0
0x18000ba43  mov     rax, [rbp+57h+var_80]
0x18000ba47  test    rax, rax
0x18000ba4a  jz      loc_18000BC67
0x18000ba50  mov     [rax], rsi
0x18000ba53  test    rdi, rdi
0x18000ba56  jnz     short loc_18000BAD1
0x18000ba58  mov     rax, rdi
0x18000ba5b  mov     rcx, [rbp+57h+var_48]
0x18000ba5f  xor     rcx, rsp; StackCookie
0x18000ba62  call    __security_check_cookie
0x18000ba67  add     rsp, 98h
0x18000ba6e  pop     r15
0x18000ba70  pop     r14
0x18000ba72  pop     r13
0x18000ba74  pop     r12
0x18000ba76  pop     rdi
0x18000ba77  pop     rsi
0x18000ba78  pop     rbx
0x18000ba79  pop     rbp
0x18000ba7a  retn
0x18000ba7c  test    cs:byte_1800F6115, 1
0x18000ba83  jz      loc_18000B80B
0x18000ba89  lea     rax, aWfphashtablein; "WfpHashtableInsert"
0x18000ba90  mov     dword ptr [rbp+57h+var_98], edi
0x18000ba93  mov     [rbp+57h+var_68], rax
0x18000ba97  lea     rdx, WFP_USERMODE_ERROR
  ... truncated ...
```
