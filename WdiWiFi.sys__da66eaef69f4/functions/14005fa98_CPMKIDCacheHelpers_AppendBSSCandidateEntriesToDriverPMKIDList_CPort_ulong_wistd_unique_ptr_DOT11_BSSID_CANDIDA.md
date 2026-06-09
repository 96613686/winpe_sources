# CPMKIDCacheHelpers::AppendBSSCandidateEntriesToDriverPMKIDList(CPort &,ulong &,wistd::unique_ptr<DOT11_BSSID_CANDIDATE [0],wistd::default_delete<DOT11_BSSID_CANDIDATE [0]>> &,ulong *,ulong *)

- ea: `0x14005fa98`
- end: `0x14006004b`
- name: `?AppendBSSCandidateEntriesToDriverPMKIDList@CPMKIDCacheHelpers@@SAXAEAVCPort@@AEAKAEAV?$unique_ptr@$$BY0A@UDOT11_BSSID_CANDIDATE@@U?$default_delete@$$BY0A@UDOT11_BSSID_CANDIDATE@@@wistd@@@wistd@@PEAK3@Z`
- size: `1459`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1400886f0`

## callees

- `0x1400109f8`
- `0x140012214`
- `0x140013000`
- `0x140016240`
- `0x140023ae0`
- `0x140024574`
- `0x140028e90`
- `0x140034e04`
- `0x140034ec4`
- `0x14005fa98`
- `0x140060054`
- `0x140069a90`
- `0x1400836f4`
- `0x1400c2678`
- `0x1400c2750`
- `0x1400da740`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005fb1a`
- `ntoskrnl!ExAllocatePool2` at `0x14005fc14`
- `ntoskrnl!ExAllocatePool2` at `0x14005fb1a`
- `ntoskrnl!ExAllocatePool2` at `0x14005fc14`

## pseudocode

```c
void __fastcall CPMKIDCacheHelpers::AppendBSSCandidateEntriesToDriverPMKIDList(
        CPropertyCache *a1,
        unsigned int *a2,
        struct DOT11_BSSID_CANDIDATE **a3,
        unsigned int *a4,
        _DWORD *a5)
{
  unsigned int *v5; // r15
  __int64 v7; // r14
  __int64 v8; // rax
  struct CBSSEntry **Pool2; // rax
  int v10; // edx
  struct CBSSEntry **v11; // rbx
  CPropertyCache *v12; // r13
  int MatchingBSSEntriesForConnect; // eax
  int v14; // edx
  unsigned __int8 PropertyBooleanOrDefault; // al
  _WFC_PROPERTY_ENTRY *m_PropertyTable; // rcx
  int v17; // r8d
  __int64 v18; // r12
  __int64 v19; // rax
  struct DOT11_BSSID_CANDIDATE *v20; // rax
  int v21; // edx
  struct DOT11_BSSID_CANDIDATE *v22; // rsi
  unsigned int v23; // ecx
  unsigned int v24; // r15d
  struct CBSSEntry **v25; // r12
  struct CBSSEntry **i; // rdi
  int v27; // r12d
  int PropertyBuffer; // eax
  int v29; // edx
  int v30; // r8d
  unsigned __int8 *v31; // r13
  unsigned int v32; // r14d
  unsigned __int8 *v33; // rdi
  int v34; // edi
  char *v35; // rsi
  int v36; // edx
  int v37; // r9d
  struct CBSSEntry *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rdx
  struct DOT11_BSSID_CANDIDATE *v41; // rbx
  char v42; // al
  unsigned int v43; // ecx
  char *v44; // rbx
  char v45; // al
  int v46; // ecx
  __int64 v47; // [rsp+28h] [rbp-D8h]
  unsigned int v48; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v49; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int8 *v50; // [rsp+48h] [rbp-B8h] BYREF
  struct CBSSEntry *v51; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+58h] [rbp-A8h] BYREF
  struct CBSSEntry **v53; // [rsp+60h] [rbp-A0h]
  void *v54; // [rsp+68h] [rbp-98h] BYREF
  struct _BSS_ENTRY_CONNECT_MATCHING_CRITERIA v55; // [rsp+70h] [rbp-90h] BYREF
  _WFC_CONNECTION_PROFILE_PARAMETERS v56; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int *v57; // [rsp+198h] [rbp+98h]

  v57 = a2;
  v5 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      33,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids);
  }
  v7 = 40;
  if ( *v5 > 0x28 )
    v7 = *v5;
  v8 = 8LL * (unsigned int)v7;
  if ( !is_mul_ok((unsigned int)v7, 8u) )
    v8 = -1;
  Pool2 = (struct CBSSEntry **)ExAllocatePool2(64, v8, 1198089303);
  v53 = Pool2;
  v11 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 8 * v7);
    _WFC_CONNECTION_PROFILE_PARAMETERS::_WFC_CONNECTION_PROFILE_PARAMETERS(&v56);
    v12 = a1 + 39;
    MatchingBSSEntriesForConnect = CConnectHelpers::PopulateConnectionParameters(a1 + 39, &v56);
    if ( MatchingBSSEntriesForConnect )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v37 = 35;
LABEL_38:
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          1,
          v37,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          MatchingBSSEntriesForConnect);
      }
    }
    else
    {
      memset(&v55, 0, sizeof(v55));
      v55.pConnectionParameters = &v56;
      v55.AdapterConnectionCapabilityFlags = a1[3].m_PropertyTable[86].ULongProperty;
      PropertyBooleanOrDefault = CPropertyCache::GetPropertyBooleanOrDefault(a1 + 39, 0x14u, 0);
      m_PropertyTable = a1[3].m_PropertyTable;
      v48 = v7;
      v55.isFTConnection = PropertyBooleanOrDefault != 0;
      MatchingBSSEntriesForConnect = CBSSListManager::FindMatchingBSSEntriesForConnect(
                                       (CBSSListManager *)&m_PropertyTable[24].BufferProperty.m_CurrentElementCount,
                                       &v55,
                                       0x2CB41780u,
                                       &v48,
                                       v11);
      if ( !MatchingBSSEntriesForConnect )
      {
        v18 = v48;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v14) = 5;
          WPP_RECORDER_SF_Ld(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            v17,
            37,
            (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
            v48,
            *v5);
        }
        v19 = 12LL * (unsigned int)v7;
        if ( !is_mul_ok((unsigned int)v7, 0xCu) )
          v19 = -1;
        v20 = (struct DOT11_BSSID_CANDIDATE *)ExAllocatePool2(64, v19, 1198089303);
        v54 = v20;
        v22 = v20;
        if ( v20 )
        {
          memset(v20, 0, 12 * v7);
          v23 = *v5;
          v48 = v7;
          details::RemoveDuplicates(v23, *a3, &v48, v22);
          v24 = v48;
          v25 = &v11[v18];
          for ( i = v11; i != v25; ++i )
          {
            v51 = *i;
            if ( v24 >= (unsigned int)v7 )
              break;
            v50 = (unsigned __int8 *)&v51;
            if ( !details::Any_DOT11_BSSID_CANDIDATE__lambda_5e729216adc61f999db31673bcaecc91___(
                    v48,
                    (char *)v22,
                    (__int64)&v50) )
            {
              v38 = v51;
              v39 = v24++;
              v40 = v39;
              *(_DWORD *)v22[v40].BSSID = *(_DWORD *)v51->m_BssID;
              *(_WORD *)&v22[v40].BSSID[4] = *(_WORD *)&v38->m_BssID[4];
              v22[v40].uFlags = v51->m_ConnectionCapabilityFlags;
            }
          }
          v50 = 0;
          v49 = 0;
          v27 = 0;
          PropertyBuffer = CPropertyCache::GetPropertyBuffer(v12, 0x2Bu, &v49, &v50);
          v31 = v50;
          LODWORD(v51) = PropertyBuffer;
          if ( !PropertyBuffer && v49 >= 0xC )
            v27 = *((_DWORD *)v50 + 1);
          v32 = 0;
          v49 = 0;
          v33 = (unsigned __int8 *)v22;
          v52 = 3LL * v48;
          if ( v22 != &v22[v48] )
          {
            v41 = &v22[v48];
            do
            {
              v50 = v33;
              v42 = details::Any_DOT11_PMKID_ENTRY__lambda_7f428fa086b30c38ef50c92ebff364c7___(
                      v27,
                      (char *)v31 + 12,
                      (const void **)&v50);
              v43 = v32 + 1;
              if ( v42 )
                v43 = v32;
              v33 += 12;
              v32 = v43;
            }
            while ( v33 != (unsigned __int8 *)v41 );
            v11 = v53;
            v22 = (struct DOT11_BSSID_CANDIDATE *)v54;
            v49 = v43;
          }
          v34 = 0;
          v35 = (char *)v22 + 4 * v52;
          if ( v35 != &v35[12 * (v24 - v48)] )
          {
            v44 = &v35[12 * (v24 - v48)];
            do
            {
              v52 = (__int64)v35;
              v45 = details::Any_DOT11_PMKID_ENTRY__lambda_7f428fa086b30c38ef50c92ebff364c7___(
                      v27,
                      (char *)v31 + 12,
                      (const void **)&v52);
              v46 = v34 + 1;
              if ( v45 )
                v46 = v34;
              v35 += 12;
              v34 = v46;
            }
            while ( v35 != v44 );
            v11 = v53;
            v32 = v49;
          }
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v29) = 4;
            WPP_RECORDER_SF_ddd(
              WPP_GLOBAL_Control->DeviceExtension,
              v29,
              v30,
              39,
              (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
              v24,
              v32,
              v34);
          }
          wistd::unique_ptr<DOT11_BSSID_CANDIDATE [0],wistd::default_delete<DOT11_BSSID_CANDIDATE [0]>>::swap(a3, &v54);
          *a4 = v32;
          *v57 = v24;
          *a5 = v34;
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            LOBYTE(v36) = 5;
            LODWORD(v47) = (_DWORD)v51;
            WPP_RECORDER_SF_D(
              WPP_GLOBAL_Control->DeviceExtension,
              v36,
              1,
              40,
              (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
              v47);
          }
          if ( v54 )
            operator delete(v54);
        }
        else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v21) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v21,
            1,
            38,
            (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids);
        }
        goto LABEL_26;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v37 = 36;
        goto LABEL_38;
      }
    }
LABEL_26:
    operator delete(v11);
    return;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      34,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids);
  }
}

```

## disassembly

```asm
0x14005fa98  mov     rax, rsp
0x14005fa9b  mov     [rax+8], rbx
0x14005fa9f  mov     [rax+20h], r9
0x14005faa3  mov     [rax+18h], r8
0x14005faa7  mov     [rax+10h], rdx
0x14005faab  push    rbp
0x14005faac  push    rsi
0x14005faad  push    rdi
0x14005faae  push    r12
0x14005fab0  push    r13
0x14005fab2  push    r14
0x14005fab4  push    r15
0x14005fab6  lea     rbp, [rsp-50h]
0x14005fabb  sub     rsp, 150h
0x14005fac2  mov     r15, rdx
0x14005fac5  mov     rsi, rcx
0x14005fac8  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14005facf  xor     r12d, r12d
0x14005fad2  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14005fad9  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14005fae0  jnz     loc_14005FDF1
0x14005fae6  mov     eax, [r15]
0x14005fae9  mov     r14d, 28h ; '('
0x14005faef  cmp     eax, r14d
0x14005faf2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14005faf9  mov     r8d, 47696457h
0x14005faff  cmova   r14d, eax
0x14005fb03  mov     eax, 8
0x14005fb08  mov     edi, r14d
0x14005fb0b  mul     rdi
0x14005fb0e  cmovb   rax, rcx
0x14005fb12  mov     ecx, 40h ; '@'
0x14005fb17  mov     rdx, rax
0x14005fb1a  call    cs:__imp_ExAllocatePool2
0x14005fb21  nop     dword ptr [rax+rax+00h]
0x14005fb26  mov     [rsp+180h+var_120], rax
0x14005fb2b  mov     rbx, rax
0x14005fb2e  test    rax, rax
0x14005fb31  jz      loc_140060011
0x14005fb37  lea     r8, ds:0[r14*8]; Size
0x14005fb3f  xor     edx, edx; Val
0x14005fb41  mov     rcx, rax; void *
0x14005fb44  call    memset
0x14005fb49  lea     rcx, [rbp+80h+var_D0]; this
0x14005fb4d  call    ??0_WFC_CONNECTION_PROFILE_PARAMETERS@@QEAA@XZ; _WFC_CONNECTION_PROFILE_PARAMETERS::_WFC_CONNECTION_PROFILE_PARAMETERS(void)
0x14005fb52  lea     r13, [rsi+3A8h]
0x14005fb59  mov     rcx, r13; this
0x14005fb5c  lea     rdx, [rbp+80h+var_D0]; struct _WFC_CONNECTION_PROFILE_PARAMETERS *
0x14005fb60  call    ?PopulateConnectionParameters@CConnectHelpers@@SAHPEAVCPortPropertyCache@@PEAU_WFC_CONNECTION_PROFILE_PARAMETERS@@@Z; CConnectHelpers::PopulateConnectionParameters(CPortPropertyCache *,_WFC_CONNECTION_PROFILE_PARAMETERS *)
0x14005fb65  test    eax, eax
0x14005fb67  jnz     loc_14005FE28
0x14005fb6d  xor     edx, edx; Val
0x14005fb6f  lea     r8d, [rax+40h]; Size
0x14005fb73  lea     rcx, [rsp+180h+var_110]; void *
0x14005fb78  call    memset
0x14005fb7d  lea     rax, [rbp+80h+var_D0]
0x14005fb81  xor     r8d, r8d; unsigned __int8
0x14005fb84  mov     [rsp+180h+var_110.pConnectionParameters], rax
0x14005fb89  mov     rax, [rsi+58h]
0x14005fb8d  lea     edx, [r8+14h]; unsigned int
0x14005fb91  mov     ecx, [rax+12E0h]
0x14005fb97  mov     [rbp+80h+var_110.AdapterConnectionCapabilityFlags], ecx
0x14005fb9a  mov     rcx, r13; this
0x14005fb9d  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x14005fba2  mov     rcx, [rsi+58h]
0x14005fba6  lea     r9, [rsp+180h+var_140]; unsigned int *
0x14005fbab  test    al, al
0x14005fbad  mov     [rsp+180h+var_140], r14d
0x14005fbb2  mov     r8d, 2CB41780h; unsigned int
0x14005fbb8  mov     [rsp+180h+var_160], rbx; struct CBSSEntry **
0x14005fbbd  setnz   [rbp+80h+var_110.isFTConnection]
0x14005fbc1  lea     rdx, [rsp+180h+var_110]; struct _BSS_ENTRY_CONNECT_MATCHING_CRITERIA *
0x14005fbc6  add     rcx, 568h; this
0x14005fbcd  call    ?FindMatchingBSSEntriesForConnect@CBSSListManager@@QEAAHPEAU_BSS_ENTRY_CONNECT_MATCHING_CRITERIA@@KPEAKPEAPEAVCBSSEntry@@@Z; CBSSListManager::FindMatchingBSSEntriesForConnect(_BSS_ENTRY_CONNECT_MATCHING_CRITERIA *,ulong,ulong *,CBSSEntry * *)
0x14005fbd2  test    eax, eax
0x14005fbd4  jnz     loc_14005FE44
0x14005fbda  mov     r12d, [rsp+180h+var_140]; __annotation("TMF:",
0x14005fbdf  lea     rcx, WPP_RECORDER_INITIALIZED
0x14005fbe6  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14005fbed  jnz     loc_14005FDAA
0x14005fbf3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14005fbfa  mov     eax, 0Ch
0x14005fbff  mul     rdi
0x14005fc02  mov     r8d, 47696457h
0x14005fc08  cmovb   rax, rcx
0x14005fc0c  mov     ecx, 40h ; '@'
0x14005fc11  mov     rdx, rax
0x14005fc14  call    cs:__imp_ExAllocatePool2
0x14005fc1b  nop     dword ptr [rax+rax+00h]
0x14005fc20  mov     [rsp+180h+var_118], rax
0x14005fc25  mov     rsi, rax
0x14005fc28  test    rax, rax
0x14005fc2b  jz      loc_14005FD72
0x14005fc31  lea     r8, [r14+r14*2]
0x14005fc35  xor     edx, edx; Val
0x14005fc37  shl     r8, 2; Size
0x14005fc3b  mov     rcx, rax; void *
0x14005fc3e  call    memset
0x14005fc43  mov     rdx, [rbp+80h+arg_10]
0x14005fc4a  lea     r8, [rsp+180h+var_140]; unsigned int *
0x14005fc4f  mov     ecx, [r15]; unsigned int
0x14005fc52  mov     r9, rsi; struct DOT11_BSSID_CANDIDATE *
0x14005fc55  mov     [rsp+180h+var_140], r14d
0x14005fc5a  mov     rdx, [rdx]; struct DOT11_BSSID_CANDIDATE *
0x14005fc5d  call    ?RemoveDuplicates@details@@YAXKPEAUDOT11_BSSID_CANDIDATE@@AEAK0@Z; details::RemoveDuplicates(ulong,DOT11_BSSID_CANDIDATE *,ulong &,DOT11_BSSID_CANDIDATE *)
0x14005fc62  mov     r15d, [rsp+180h+var_140]
0x14005fc67  lea     r12, [rbx+r12*8]
0x14005fc6b  mov     rdi, rbx
0x14005fc6e  cmp     rbx, r12
0x14005fc71  jnz     loc_14005FE8B
0x14005fc77  xor     edi, edi
0x14005fc79  lea     r9, [rsp+180h+var_138]; unsigned __int8 **
0x14005fc7e  lea     r8, [rsp+180h+var_13C]; unsigned int *
0x14005fc83  mov     [rsp+180h+var_138], rdi
0x14005fc88  mov     rcx, r13; this
0x14005fc8b  mov     [rsp+180h+var_13C], edi
0x14005fc8f  mov     r12d, edi
0x14005fc92  lea     edx, [rdi+2Bh]; unsigned int
0x14005fc95  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x14005fc9a  mov     r13, [rsp+180h+var_138]
0x14005fc9f  mov     dword ptr [rsp+180h+var_130], eax
0x14005fca3  test    eax, eax
0x14005fca5  jz      loc_14005FEFC
0x14005fcab  mov     ecx, [rsp+180h+var_140]
0x14005fcaf  mov     r14d, edi
0x14005fcb2  mov     [rsp+180h+var_13C], edi
0x14005fcb6  mov     rdi, rsi
0x14005fcb9  lea     rax, [rcx+rcx*2]
0x14005fcbd  mov     [rsp+180h+var_128], rax
0x14005fcc2  lea     rax, [rsi+rax*4]
0x14005fcc6  cmp     rsi, rax
0x14005fcc9  jnz     loc_14005FF10
0x14005fccf  mov     rax, [rsp+180h+var_128]
0x14005fcd4  xor     edi, edi
0x14005fcd6  lea     rsi, [rsi+rax*4]
0x14005fcda  mov     eax, r15d
0x14005fcdd  sub     eax, [rsp+180h+var_140]
0x14005fce1  lea     rcx, [rax+rax*2]
0x14005fce5  lea     rax, [rsi+rcx*4]
0x14005fce9  cmp     rsi, rax
0x14005fcec  jnz     loc_14005FF52
0x14005fcf2  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14005fcf9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14005fd00  lea     r12, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14005fd07  jnz     loc_14005FF8D
0x14005fd0d  mov     rcx, [rbp+80h+arg_10]
0x14005fd14  lea     rdx, [rsp+180h+var_118]
0x14005fd19  call    ?swap@?$unique_ptr@$$BY0A@UDOT11_BSSID_CANDIDATE@@U?$default_delete@$$BY0A@UDOT11_BSSID_CANDIDATE@@@wistd@@@wistd@@QEAAXAEAV12@@Z; wistd::unique_ptr<DOT11_BSSID_CANDIDATE [0],wistd::default_delete<DOT11_BSSID_CANDIDATE [0]>>::swap(wistd::unique_ptr<DOT11_BSSID_CANDIDATE [0],wistd::default_delete<DOT11_BSSID_CANDIDATE [0]>> &)
0x14005fd1e  mov     rax, [rbp+80h+arg_18]
0x14005fd25  mov     rcx, [rbp+80h+arg_8]
0x14005fd2c  mov     [rax], r14d
0x14005fd2f  mov     rax, [rbp+80h+arg_20]
0x14005fd36  mov     [rcx], r15d
0x14005fd39  mov     [rax], edi
0x14005fd3b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14005fd42  jz      short loc_14005FD61
0x14005fd44  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fd4b  cmp     byte ptr [rcx+29h], 5
0x14005fd4f  jnb     loc_14005FFBD
0x14005fd55  xor     edi, edi
0x14005fd57  cmp     [rcx+48h], di
0x14005fd5b  jnz     loc_14005FFBD
0x14005fd61  mov     rcx, [rsp+180h+var_118]; void *
0x14005fd66  test    rcx, rcx
0x14005fd69  jz      short loc_14005FD86
0x14005fd6b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005fd70  jmp     short loc_14005FD86
0x14005fd72  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14005fd79  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14005fd80  jnz     loc_14005FFE4
0x14005fd86  mov     rcx, rbx; void *
0x14005fd89  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005fd8e  mov     rbx, [rsp+180h+arg_0]
0x14005fd96  add     rsp, 150h
0x14005fd9d  pop     r15
0x14005fd9f  pop     r14
0x14005fda1  pop     r13
0x14005fda3  pop     r12
0x14005fda5  pop     rdi
0x14005fda6  pop     rsi
0x14005fda7  pop     rbp
0x14005fda8  retn
0x14005fdaa  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fdb1  cmp     byte ptr [rcx+29h], 5
0x14005fdb5  jnb     short loc_14005FDC3
0x14005fdb7  xor     eax, eax
0x14005fdb9  cmp     [rcx+48h], ax
0x14005fdbd  jz      loc_14005FBF3
0x14005fdc3  mov     eax, [r15]
0x14005fdc6  mov     r9d, 25h ; '%'
0x14005fdcc  mov     rcx, [rcx+40h]
0x14005fdd0  mov     dl, 5
0x14005fdd2  mov     [rsp+180h+var_150], eax
0x14005fdd6  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14005fddd  mov     dword ptr [rsp+180h+var_158], r12d
0x14005fde2  mov     [rsp+180h+var_160], rax
0x14005fde7  call    WPP_RECORDER_SF_Ld
0x14005fdec  jmp     loc_14005FBF3
0x14005fdf1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fdf8  cmp     byte ptr [rcx+29h], 5
0x14005fdfc  jnb     short loc_14005FE09
0x14005fdfe  cmp     [rcx+48h], r12w
0x14005fe03  jz      loc_14005FAE6
0x14005fe09  mov     rcx, [rcx+40h]
0x14005fe0d  mov     r9d, 21h ; '!'
0x14005fe13  mov     dl, 5
0x14005fe15  mov     [rsp+180h+var_160], rax
0x14005fe1a  lea     r8d, [r9-20h]
0x14005fe1e  call    WPP_RECORDER_SF_
0x14005fe23  jmp     loc_14005FAE6
0x14005fe28  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14005fe2f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14005fe36  jz      loc_14005FD86
0x14005fe3c  mov     r9d, 23h ; '#'
0x14005fe42  jmp     short loc_14005FE5E
0x14005fe44  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14005fe4b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14005fe52  jz      loc_14005FD86
0x14005fe58  mov     r9d, 24h ; '$'
0x14005fe5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fe65  mov     r8d, 1
0x14005fe6b  mov     dword ptr [rsp+180h+var_158], eax
0x14005fe6f  mov     dl, 2
0x14005fe71  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14005fe78  mov     [rsp+180h+var_160], rax
0x14005fe7d  mov     rcx, [rcx+40h]
0x14005fe81  call    WPP_RECORDER_SF_D
0x14005fe86  jmp     loc_14005FD86
0x14005fe8b  mov     rax, [rdi]
0x14005fe8e  mov     [rsp+180h+var_130], rax
0x14005fe93  cmp     r15d, r14d
0x14005fe96  jnb     loc_14005FC77
0x14005fe9c  mov     ecx, [rsp+180h+var_140]
0x14005fea0  lea     rax, [rsp+180h+var_130]
0x14005fea5  lea     r8, [rsp+180h+var_138]
0x14005feaa  mov     [rsp+180h+var_138], rax
0x14005feaf  mov     rdx, rsi
0x14005feb2  call    details__Any_DOT11_BSSID_CANDIDATE__lambda_5e729216adc61f999db31673bcaecc91___
0x14005feb7  test    al, al
0x14005feb9  jnz     short loc_14005FEEE
0x14005febb  mov     rcx, [rsp+180h+var_130]
0x14005fec0  mov     eax, r15d
0x14005fec3  inc     r15d
0x14005fec6  lea     rdx, [rax+rax*2]
0x14005feca  mov     eax, [rcx+1BCh]
0x14005fed0  mov     [rsi+rdx*4], eax
0x14005fed3  movzx   eax, word ptr [rcx+1C0h]
0x14005feda  mov     [rsi+rdx*4+4], ax
0x14005fedf  mov     rax, [rsp+180h+var_130]
0x14005fee4  mov     ecx, [rax+2D8h]
0x14005feea  mov     [rsi+rdx*4+8], ecx
0x14005feee  add     rdi, 8
0x14005fef2  cmp     rdi, r12
0x14005fef5  jnz     short loc_14005FE8B
0x14005fef7  jmp     loc_14005FC77
0x14005fefc  cmp     [rsp+180h+var_13C], 0Ch
0x14005ff01  jb      loc_14005FCAB
0x14005ff07  mov     r12d, [r13+4]
0x14005ff0b  jmp     loc_14005FCAB
0x14005ff10  mov     rbx, rax
0x14005ff13  lea     rdx, [r13+0Ch]
0x14005ff17  mov     [rsp+180h+var_138], rdi
0x14005ff1c  lea     r8, [rsp+180h+var_138]
0x14005ff21  mov     ecx, r12d
0x14005ff24  call    details__Any_DOT11_PMKID_ENTRY__lambda_7f428fa086b30c38ef50c92ebff364c7___
0x14005ff29  test    al, al
0x14005ff2b  lea     ecx, [r14+1]
0x14005ff2f  cmovnz  ecx, r14d
0x14005ff33  add     rdi, 0Ch
0x14005ff37  mov     r14d, ecx
0x14005ff3a  cmp     rdi, rbx
0x14005ff3d  jnz     short loc_14005FF13
0x14005ff3f  mov     rbx, [rsp+180h+var_120]
0x14005ff44  mov     rsi, [rsp+180h+var_118]
0x14005ff49  mov     [rsp+180h+var_13C], ecx
0x14005ff4d  jmp     loc_14005FCCF
0x14005ff52  mov     rbx, rax
0x14005ff55  lea     rdx, [r13+0Ch]
0x14005ff59  mov     [rsp+180h+var_128], rsi
0x14005ff5e  lea     r8, [rsp+180h+var_128]
0x14005ff63  mov     ecx, r12d
0x14005ff66  call    details__Any_DOT11_PMKID_ENTRY__lambda_7f428fa086b30c38ef50c92ebff364c7___
0x14005ff6b  test    al, al
0x14005ff6d  lea     ecx, [rdi+1]
0x14005ff70  cmovnz  ecx, edi
0x14005ff73  add     rsi, 0Ch
0x14005ff77  mov     edi, ecx
0x14005ff79  cmp     rsi, rbx
0x14005ff7c  jnz     short loc_14005FF55
0x14005ff7e  mov     rbx, [rsp+180h+var_120]
0x14005ff83  mov     r14d, [rsp+180h+var_13C]
0x14005ff88  jmp     loc_14005FCF2
0x14005ff8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ff94  mov     r9d, 27h ; '''
0x14005ff9a  mov     [rsp+180h+var_148], edi
0x14005ff9e  mov     dl, 4
0x14005ffa0  mov     [rsp+180h+var_150], r14d
0x14005ffa5  mov     dword ptr [rsp+180h+var_158], r15d
0x14005ffaa  mov     rcx, [rcx+40h]
0x14005ffae  mov     [rsp+180h+var_160], r12
  ... truncated ...
```
