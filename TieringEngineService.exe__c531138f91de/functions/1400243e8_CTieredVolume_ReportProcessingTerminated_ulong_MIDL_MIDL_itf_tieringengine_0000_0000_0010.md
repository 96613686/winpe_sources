# CTieredVolume::ReportProcessingTerminated(ulong,__MIDL___MIDL_itf_tieringengine_0000_0000_0010 *)

- ea: `0x1400243e8`
- end: `0x140024941`
- name: `?ReportProcessingTerminated@CTieredVolume@@AEAAJKPEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0010@@@Z`
- size: `1369`
- prototype: `__int64 __fastcall(CTieredVolume *this, char, struct __MIDL___MIDL_itf_tieringengine_0000_0000_0010 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14003ad70`

## callees

- `0x140004ef0`
- `0x140005420`
- `0x14000a03c`
- `0x14000b7f8`
- `0x140017708`
- `0x140017930`
- `0x140017e78`
- `0x1400194ec`
- `0x14001cb24`
- `0x14001cb9c`
- `0x1400211a4`
- `0x140023bb8`
- `0x1400243e8`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140024582`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400245fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002460f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140024582`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400245fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002460f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140024529`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140024594`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140024529`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140024594`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14002464e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14002464e`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1400246bb`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1400246bb`

## pseudocode

```c
__int64 __fastcall CTieredVolume::ReportProcessingTerminated(
        CTieredVolume *this,
        char a2,
        struct __MIDL___MIDL_itf_tieringengine_0000_0000_0010 *a3)
{
  int v6; // r9d
  int v7; // eax
  bool v8; // dl
  __int64 v9; // r8
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  int v12; // r9d
  int v13; // eax
  unsigned __int16 v15; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[8]; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+58h] [rbp-A8h]
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  __int64 v23; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v25[16]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v26; // [rsp+90h] [rbp-70h]
  __int64 v27; // [rsp+98h] [rbp-68h]
  __int64 v28; // [rsp+A0h] [rbp-60h]
  unsigned int v29; // [rsp+A8h] [rbp-58h]
  int v30; // [rsp+ACh] [rbp-54h]
  __int64 *v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  __int64 *v33; // [rsp+C0h] [rbp-40h]
  __int64 v34; // [rsp+C8h] [rbp-38h]
  __int64 *v35; // [rsp+D0h] [rbp-30h]
  __int64 v36; // [rsp+D8h] [rbp-28h]
  __int64 *v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+E8h] [rbp-18h]
  int *v39; // [rsp+F0h] [rbp-10h]
  __int64 v40; // [rsp+F8h] [rbp-8h]
  int *v41; // [rsp+100h] [rbp+0h]
  __int64 v42; // [rsp+108h] [rbp+8h]
  unsigned __int64 *p_UnbiasedTime; // [rsp+110h] [rbp+10h]
  __int64 v44; // [rsp+118h] [rbp+18h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::ReportProcessingTerminated";
  CHResultImp::CHResultImp((CHResultImp *)v19);
  if ( (a2 & 1) != 0 )
  {
    v6 = *((_DWORD *)this + 46);
    if ( v6 == 7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Z(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          87,
          &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
          (char *)this + 672);
      }
      v7 = CTieredVolume::BeginOrCompleteDefragReconcile(this, 0);
      if ( v7 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
          (_DWORD)this + 672,
          v7);
      }
      AcquireSRWLockExclusive((PSRWLOCK)this + 3);
      if ( *((_DWORD *)this + 46) == 7 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Z(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            89,
            &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
            (char *)this + 672);
        }
        *((_DWORD *)this + 46) = 2;
      }
      if ( this != (CTieredVolume *)-24LL )
        ReleaseSRWLockExclusive((PSRWLOCK)this + 3);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_dZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        v6,
        (__int64)this + 672);
    }
LABEL_53:
    v20 = 0;
    goto LABEL_54;
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 3);
  if ( *((_DWORD *)this + 46) != 7 )
  {
    if ( this != (CTieredVolume *)-24LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 3);
    TieringJetDatabase::CloseDatabase((CTieredVolume *)((char *)this + 1504), 0, 0);
    TieringJetDatabase::WaitForDatabaseClose((CTieredVolume *)((char *)this + 1504), v8);
    CTieredVolume::UninitializeJetInstance(this, (unsigned __int64 *)this + 143);
    *((_BYTE *)this + 1136) = 0;
    DeleteFileW(*((LPCWSTR *)this + 104));
    v10 = *((unsigned int *)this + 79);
    *((_QWORD *)this + 33) = *(_QWORD *)a3 / v10;
    *((_QWORD *)this + 34) = *((_QWORD *)a3 + 1) / v10;
    *((_QWORD *)this + 66) = *((_QWORD *)a3 + 2) / v10;
    *((_QWORD *)this + 67) = *((_QWORD *)a3 + 3) / v10;
    *((_DWORD *)this + 136) = *((_DWORD *)a3 + 8);
    if ( *((_QWORD *)this + 208) )
    {
      UnbiasedTime = 0;
      QueryUnbiasedInterruptTime(&UnbiasedTime);
      v11 = (UnbiasedTime - *((_QWORD *)this + 208) + 599999999) / 0x23C34600;
      if ( *((_BYTE *)this + 1672) )
        LODWORD(v11) = v11 - *((_DWORD *)this + 137);
      *((_DWORD *)this + 138) = v11;
      *((_QWORD *)this + 208) = 0;
      *((_BYTE *)this + 1672) = 0;
    }
    if ( (Microsoft_Windows_Storage_TieringEnableBits & 1) != 0 )
    {
      LODWORD(UnbiasedTime) = *((_DWORD *)this + 138);
      v18 = *((_DWORD *)this + 137);
      v17 = *((_DWORD *)this + 136);
      v24 = *((_QWORD *)this + 67);
      v23 = *((_QWORD *)this + 66);
      v22 = *((_QWORD *)this + 34);
      v21 = *((_QWORD *)this + 33);
      v15 = *((_WORD *)this + 348) >> 1;
      v26 = &v15;
      v27 = 2;
      v28 = *((_QWORD *)this + 88);
      v29 = 2 * v15;
      v30 = 0;
      v31 = &v21;
      v32 = 8;
      v33 = &v22;
      v34 = 8;
      v35 = &v23;
      v36 = 8;
      v37 = &v24;
      v38 = 8;
      v39 = &v17;
      v40 = 4;
      v41 = &v18;
      v42 = 4;
      p_UnbiasedTime = &UnbiasedTime;
      v44 = 4;
      v12 = McGenEventWrite_EventWriteTransfer(v29, TIERENGINE_EVENT_PROCESS_RESULTS, v9, 10, v25);
    }
    else
    {
      v12 = 0;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_dZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        91,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        v12,
        (__int64)this + 672);
    }
    v13 = CTieredVolume::LogTierOptimizationReport(this);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_dZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        v13,
        (__int64)this + 672);
    }
    CTieringEngineLib::SqmVolumeTierInternalStatistics(
      *((CTieringEngineLib **)this + 2),
      (const struct _GUID *)this + 49,
      (CTieredVolume *)((char *)this + 208));
    *((_DWORD *)this + 81) = 0;
    *(_QWORD *)((char *)this + 556) = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        (char *)this + 672);
    }
    *((_DWORD *)this + 46) = 1;
    goto LABEL_53;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Z(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      90,
      &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
      (char *)this + 672);
  }
  *((_DWORD *)this + 46) = 2;
  v20 = 0;
  if ( this != (CTieredVolume *)-24LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 3);
LABEL_54:
  CHResultImp::~CHResultImp((CHResultImp *)v19);
  return 0;
}

```

## disassembly

```asm
0x1400243e8  push    rbp
0x1400243ea  push    rbx
0x1400243eb  push    rsi
0x1400243ec  push    rdi
0x1400243ed  push    r14
0x1400243ef  push    r15
0x1400243f1  lea     rbp, [rsp-38h]
0x1400243f6  sub     rsp, 138h
0x1400243fd  mov     rax, cs:__security_cookie
0x140024404  xor     rax, rsp
0x140024407  mov     [rbp+60h+var_40], rax
0x14002440b  mov     r15, r8
0x14002440e  mov     ebx, edx
0x140024410  mov     rdi, rcx
0x140024413  mov     ecx, 8
0x140024418  mov     rax, gs:58h
0x140024421  mov     r9, [rax]
0x140024424  lea     rax, aCtieredvolumeR; "CTieredVolume::ReportProcessingTerminat"...
0x14002442b  mov     [rcx+r9], rax
0x14002442f  lea     rcx, [rsp+160h+var_110]; this
0x140024434  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140024439  nop
0x14002443a  test    bl, 1
0x14002443d  jz      loc_14002458D
0x140024443  mov     r9d, [rdi+0B8h]
0x14002444a  xor     esi, esi
0x14002444c  cmp     r9d, 7
0x140024450  jz      short loc_1400244A1
0x140024452  lea     rbx, WPP_GLOBAL_Control
0x140024459  mov     rcx, cs:WPP_GLOBAL_Control
0x140024460  cmp     rcx, rbx
0x140024463  jz      loc_140024915
0x140024469  test    byte ptr [rcx+1Ch], 1
0x14002446d  jz      loc_140024915
0x140024473  cmp     byte ptr [rcx+19h], 4
0x140024477  jb      loc_140024915
0x14002447d  lea     rax, [rdi+2A0h]
0x140024484  lea     edx, [rsi+56h]
0x140024487  mov     [rsp+160h+var_140], rax
0x14002448c  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140024493  mov     rcx, [rcx+10h]
0x140024497  call    WPP_SF_dZ
0x14002449c  jmp     loc_140024915
0x1400244a1  lea     rbx, WPP_GLOBAL_Control
0x1400244a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400244af  cmp     rcx, rbx
0x1400244b2  jz      short loc_1400244DC
0x1400244b4  test    byte ptr [rcx+1Ch], 1
0x1400244b8  jz      short loc_1400244DC
0x1400244ba  cmp     byte ptr [rcx+19h], 4
0x1400244be  jb      short loc_1400244DC
0x1400244c0  lea     r9, [rdi+2A0h]
0x1400244c7  mov     edx, 57h ; 'W'
0x1400244cc  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x1400244d3  mov     rcx, [rcx+10h]
0x1400244d7  call    WPP_SF_Z
0x1400244dc  xor     edx, edx; bool
0x1400244de  mov     rcx, rdi; this
0x1400244e1  call    ?BeginOrCompleteDefragReconcile@CTieredVolume@@AEAAJ_N@Z; CTieredVolume::BeginOrCompleteDefragReconcile(bool)
0x1400244e6  test    eax, eax
0x1400244e8  jns     short loc_140024522
0x1400244ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400244f1  cmp     rcx, rbx
0x1400244f4  jz      short loc_140024522
0x1400244f6  test    byte ptr [rcx+1Ch], 1
0x1400244fa  jz      short loc_140024522
0x1400244fc  cmp     byte ptr [rcx+19h], 2
0x140024500  jb      short loc_140024522
0x140024502  lea     r9, [rdi+2A0h]
0x140024509  mov     edx, 58h ; 'X'
0x14002450e  mov     dword ptr [rsp+160h+var_140], eax
0x140024512  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140024519  mov     rcx, [rcx+10h]
0x14002451d  call    WPP_SF_Zd
0x140024522  lea     r14, [rdi+18h]
0x140024526  mov     rcx, r14; SRWLock
0x140024529  call    cs:__imp_AcquireSRWLockExclusive
0x14002452f  cmp     dword ptr [rdi+0B8h], 7
0x140024536  jnz     short loc_140024576
0x140024538  mov     rcx, cs:WPP_GLOBAL_Control
0x14002453f  cmp     rcx, rbx
0x140024542  jz      short loc_14002456C
0x140024544  test    byte ptr [rcx+1Ch], 1
0x140024548  jz      short loc_14002456C
0x14002454a  cmp     byte ptr [rcx+19h], 4
0x14002454e  jb      short loc_14002456C
0x140024550  lea     r9, [rdi+2A0h]
0x140024557  mov     edx, 59h ; 'Y'
0x14002455c  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140024563  mov     rcx, [rcx+10h]
0x140024567  call    WPP_SF_Z
0x14002456c  mov     dword ptr [rdi+0B8h], 2
0x140024576  test    r14, r14
0x140024579  jz      loc_140024915
0x14002457f  mov     rcx, r14; SRWLock
0x140024582  call    cs:__imp_ReleaseSRWLockExclusive
0x140024588  jmp     loc_140024915
0x14002458d  lea     r14, [rdi+18h]
0x140024591  mov     rcx, r14; SRWLock
0x140024594  call    cs:__imp_AcquireSRWLockExclusive
0x14002459a  cmp     dword ptr [rdi+0B8h], 7
0x1400245a1  jnz     short loc_140024605
0x1400245a3  lea     rbx, WPP_GLOBAL_Control
0x1400245aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400245b1  cmp     rcx, rbx
0x1400245b4  jz      short loc_1400245DE
0x1400245b6  test    byte ptr [rcx+1Ch], 1
0x1400245ba  jz      short loc_1400245DE
0x1400245bc  cmp     byte ptr [rcx+19h], 4
0x1400245c0  jb      short loc_1400245DE
0x1400245c2  lea     r9, [rdi+2A0h]
0x1400245c9  mov     edx, 5Ah ; 'Z'
0x1400245ce  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x1400245d5  mov     rcx, [rcx+10h]
0x1400245d9  call    WPP_SF_Z
0x1400245de  mov     dword ptr [rdi+0B8h], 2
0x1400245e8  xor     esi, esi
0x1400245ea  mov     [rsp+160h+var_108], esi
0x1400245ee  test    r14, r14
0x1400245f1  jz      loc_140024919
0x1400245f7  mov     rcx, r14; SRWLock
0x1400245fa  call    cs:__imp_ReleaseSRWLockExclusive
0x140024600  jmp     loc_140024919
0x140024605  xor     esi, esi
0x140024607  test    r14, r14
0x14002460a  jz      short loc_140024615
0x14002460c  mov     rcx, r14; SRWLock
0x14002460f  call    cs:__imp_ReleaseSRWLockExclusive
0x140024615  lea     rbx, [rdi+5E0h]
0x14002461c  xor     r8d, r8d; bool
0x14002461f  xor     edx, edx; bool
0x140024621  mov     rcx, rbx; this
0x140024624  call    ?CloseDatabase@TieringJetDatabase@@QEAAJ_N0@Z; TieringJetDatabase::CloseDatabase(bool,bool)
0x140024629  mov     rcx, rbx; this
0x14002462c  call    ?WaitForDatabaseClose@TieringJetDatabase@@QEAAJ_N@Z; TieringJetDatabase::WaitForDatabaseClose(bool)
0x140024631  lea     rdx, [rdi+478h]; unsigned __int64 *
0x140024638  mov     rcx, rdi; this
0x14002463b  call    ?UninitializeJetInstance@CTieredVolume@@QEAAJPEA_K@Z; CTieredVolume::UninitializeJetInstance(unsigned __int64 *)
0x140024640  mov     [rdi+470h], sil
0x140024647  mov     rcx, [rdi+340h]; lpFileName
0x14002464e  call    cs:__imp_DeleteFileW
0x140024654  lea     r14, [rdi+0D0h]
0x14002465b  mov     ecx, [r14+6Ch]
0x14002465f  xor     edx, edx
0x140024661  mov     rax, [r15]
0x140024664  div     rcx
0x140024667  mov     [rdi+108h], rax
0x14002466e  xor     edx, edx
0x140024670  mov     rax, [r15+8]
0x140024674  div     rcx
0x140024677  mov     [rdi+110h], rax
0x14002467e  xor     edx, edx
0x140024680  mov     rax, [r15+10h]
0x140024684  div     rcx
0x140024687  mov     [rdi+210h], rax
0x14002468e  xor     edx, edx
0x140024690  mov     rax, [r15+18h]
0x140024694  div     rcx
0x140024697  mov     [rdi+218h], rax
0x14002469e  mov     eax, [r15+20h]
0x1400246a2  mov     [rdi+220h], eax
0x1400246a8  cmp     [rdi+680h], rsi
0x1400246af  jz      short loc_140024708
0x1400246b1  mov     [rsp+160h+UnbiasedTime], rsi
0x1400246b6  lea     rcx, [rsp+160h+UnbiasedTime]; UnbiasedTime
0x1400246bb  call    cs:__imp_QueryUnbiasedInterruptTime
0x1400246c1  mov     rcx, [rsp+160h+UnbiasedTime]
0x1400246c6  sub     rcx, [rdi+680h]
0x1400246cd  add     rcx, 23C345FFh
0x1400246d4  mov     rax, 0E5109EC205D7BEA7h
0x1400246de  mul     rcx
0x1400246e1  shr     rdx, 1Dh
0x1400246e5  cmp     [rdi+688h], sil
0x1400246ec  jz      short loc_1400246F4
0x1400246ee  sub     edx, [rdi+224h]
0x1400246f4  mov     [rdi+228h], edx
0x1400246fa  mov     [rdi+680h], rsi
0x140024701  mov     [rdi+688h], sil
0x140024708  test    cs:Microsoft_Windows_Storage_TieringEnableBits, 1
0x14002470f  jz      loc_140024830
0x140024715  mov     eax, [rdi+228h]
0x14002471b  mov     dword ptr [rsp+160h+UnbiasedTime], eax
0x14002471f  mov     eax, [rdi+224h]
0x140024725  mov     [rsp+160h+var_118], eax
0x140024729  mov     eax, [rdi+220h]
0x14002472f  mov     [rsp+160h+var_120], eax
0x140024733  mov     rax, [rdi+218h]
0x14002473a  mov     [rsp+160h+var_E8], rax
0x14002473f  mov     rax, [rdi+210h]
0x140024746  mov     [rsp+160h+var_F0], rax
0x14002474b  mov     rax, [rdi+110h]
0x140024752  mov     [rsp+160h+var_F8], rax
0x140024757  mov     rax, [rdi+108h]
0x14002475e  mov     [rsp+160h+var_100], rax
0x140024763  movzx   eax, word ptr [rdi+2B8h]
0x14002476a  shr     ax, 1
0x14002476d  movzx   ecx, ax
0x140024770  mov     [rsp+160h+var_130], cx
0x140024775  lea     rax, [rsp+160h+var_130]
0x14002477a  mov     [rbp+60h+var_D0], rax
0x14002477e  mov     [rbp+60h+var_C8], 2
0x140024786  mov     rax, [rdi+2C0h]
0x14002478d  mov     [rbp+60h+var_C0], rax
0x140024791  add     ecx, ecx
0x140024793  mov     [rbp+60h+var_B8], ecx
0x140024796  mov     [rbp+60h+var_B4], esi
0x140024799  lea     rax, [rsp+160h+var_100]
0x14002479e  mov     [rbp+60h+var_B0], rax
0x1400247a2  mov     [rbp+60h+var_A8], 8
0x1400247aa  lea     rax, [rsp+160h+var_F8]
0x1400247af  mov     [rbp+60h+var_A0], rax
0x1400247b3  mov     [rbp+60h+var_98], 8
0x1400247bb  lea     rax, [rsp+160h+var_F0]
0x1400247c0  mov     [rbp+60h+var_90], rax
0x1400247c4  mov     [rbp+60h+var_88], 8
0x1400247cc  lea     rax, [rsp+160h+var_E8]
0x1400247d1  mov     [rbp+60h+var_80], rax
0x1400247d5  mov     [rbp+60h+var_78], 8
0x1400247dd  lea     rax, [rsp+160h+var_120]
0x1400247e2  mov     [rbp+60h+var_70], rax
0x1400247e6  mov     [rbp+60h+var_68], 4
0x1400247ee  lea     rax, [rsp+160h+var_118]
0x1400247f3  mov     [rbp+60h+var_60], rax
0x1400247f7  mov     [rbp+60h+var_58], 4
0x1400247ff  lea     rax, [rsp+160h+UnbiasedTime]
0x140024804  mov     [rbp+60h+var_50], rax
0x140024808  mov     [rbp+60h+var_48], 4
0x140024810  lea     rax, [rbp+60h+var_E0]
0x140024814  mov     [rsp+160h+var_140], rax
0x140024819  mov     r9d, 0Ah
0x14002481f  lea     rdx, TIERENGINE_EVENT_PROCESS_RESULTS
0x140024826  call    McGenEventWrite_EventWriteTransfer
0x14002482b  mov     r9d, eax
0x14002482e  jmp     short loc_140024833
0x140024830  mov     r9d, esi
0x140024833  lea     rbx, WPP_GLOBAL_Control
0x14002483a  mov     rcx, cs:WPP_GLOBAL_Control
0x140024841  cmp     rcx, rbx
0x140024844  jz      short loc_140024873
0x140024846  test    byte ptr [rcx+1Ch], 1
0x14002484a  jz      short loc_140024873
0x14002484c  cmp     byte ptr [rcx+19h], 4
0x140024850  jb      short loc_140024873
0x140024852  lea     rax, [rdi+2A0h]
0x140024859  mov     edx, 5Bh ; '['
0x14002485e  mov     [rsp+160h+var_140], rax
0x140024863  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x14002486a  mov     rcx, [rcx+10h]
0x14002486e  call    WPP_SF_dZ
0x140024873  mov     rcx, rdi; this
0x140024876  call    ?LogTierOptimizationReport@CTieredVolume@@AEAAJXZ; CTieredVolume::LogTierOptimizationReport(void)
0x14002487b  mov     rcx, cs:WPP_GLOBAL_Control
0x140024882  cmp     rcx, rbx
0x140024885  jz      short loc_1400248B7
0x140024887  test    byte ptr [rcx+1Ch], 1
0x14002488b  jz      short loc_1400248B7
0x14002488d  cmp     byte ptr [rcx+19h], 4
0x140024891  jb      short loc_1400248B7
0x140024893  lea     r9, [rdi+2A0h]
0x14002489a  mov     edx, 5Ch ; '\'
0x14002489f  mov     [rsp+160h+var_140], r9
0x1400248a4  mov     r9d, eax
0x1400248a7  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x1400248ae  mov     rcx, [rcx+10h]
0x1400248b2  call    WPP_SF_dZ
0x1400248b7  lea     rdx, [rdi+310h]; struct _GUID *
0x1400248be  mov     r8, r14; struct __MIDL___MIDL_itf_tieringengine_0000_0000_0009 *
0x1400248c1  mov     rcx, [rdi+10h]; this
0x1400248c5  call    ?SqmVolumeTierInternalStatistics@CTieringEngineLib@@QEAAXAEBU_GUID@@PEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0009@@@Z; CTieringEngineLib::SqmVolumeTierInternalStatistics(_GUID const &,__MIDL___MIDL_itf_tieringengine_0000_0000_0009 *)
0x1400248ca  mov     [rdi+144h], esi
0x1400248d0  mov     [rdi+22Ch], rsi
0x1400248d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400248de  cmp     rcx, rbx
0x1400248e1  jz      short loc_14002490B
0x1400248e3  test    byte ptr [rcx+1Ch], 1
0x1400248e7  jz      short loc_14002490B
0x1400248e9  cmp     byte ptr [rcx+19h], 4
0x1400248ed  jb      short loc_14002490B
0x1400248ef  lea     r9, [rdi+2A0h]
0x1400248f6  mov     edx, 5Dh ; ']'
0x1400248fb  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140024902  mov     rcx, [rcx+10h]
0x140024906  call    WPP_SF_Z
0x14002490b  mov     dword ptr [rdi+0B8h], 1
0x140024915  mov     [rsp+160h+var_108], esi
0x140024919  lea     rcx, [rsp+160h+var_110]; this
0x14002491e  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140024923  xor     eax, eax
0x140024925  mov     rcx, [rbp+60h+var_40]
0x140024929  xor     rcx, rsp; StackCookie
0x14002492c  call    __security_check_cookie
0x140024931  add     rsp, 138h
0x140024938  pop     r15
0x14002493a  pop     r14
0x14002493c  pop     rdi
0x14002493d  pop     rsi
0x14002493e  pop     rbx
0x14002493f  pop     rbp
0x140024940  retn
```
