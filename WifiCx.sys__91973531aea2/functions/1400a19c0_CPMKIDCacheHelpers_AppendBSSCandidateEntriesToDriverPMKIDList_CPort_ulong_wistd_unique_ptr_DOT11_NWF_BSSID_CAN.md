# CPMKIDCacheHelpers::AppendBSSCandidateEntriesToDriverPMKIDList(CPort &,ulong &,wistd::unique_ptr<DOT11_NWF_BSSID_CANDIDATE [0],wistd::default_delete<DOT11_NWF_BSSID_CANDIDATE [0]>> &,ulong *,ulong *)

- ea: `0x1400a19c0`
- end: `0x1400a1f95`
- name: `?AppendBSSCandidateEntriesToDriverPMKIDList@CPMKIDCacheHelpers@@SAXAEAVCPort@@AEAKAEAV?$unique_ptr@$$BY0A@UDOT11_NWF_BSSID_CANDIDATE@@U?$default_delete@$$BY0A@UDOT11_NWF_BSSID_CANDIDATE@@@wistd@@@wistd@@PEAK3@Z`
- size: `1493`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140084a9c`

## callees

- `0x14000688c`
- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x14000d054`
- `0x14001a630`
- `0x140021d44`
- `0x140024a20`
- `0x140050574`
- `0x1400a1004`
- `0x1400a19c0`
- `0x1400b0448`
- `0x1400b18bc`
- `0x1400b66f0`
- `0x1400dfd00`
- `0x1400e0100`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400a1cab`
- `ntoskrnl!RtlCompareMemory` at `0x1400a1da5`
- `ntoskrnl!RtlCompareMemory` at `0x1400a1e16`
- `ntoskrnl!RtlCompareMemory` at `0x1400a1cab`
- `ntoskrnl!RtlCompareMemory` at `0x1400a1da5`
- `ntoskrnl!RtlCompareMemory` at `0x1400a1e16`

## pseudocode

```c
void __fastcall CPMKIDCacheHelpers::AppendBSSCandidateEntriesToDriverPMKIDList(
        __int64 a1,
        unsigned int *a2,
        struct DOT11_NWF_BSSID_CANDIDATE **a3,
        unsigned int *a4,
        _DWORD *a5)
{
  unsigned int *v5; // r12
  __int64 v7; // r15
  struct CBSSEntry **v8; // rax
  int v9; // edx
  struct CBSSEntry **Base; // rbx
  CPropertyCache *v11; // r13
  struct _WFC_CONNECTION_PROFILE_PARAMETERS *v12; // r8
  int MatchingBSSEntriesForConnect; // eax
  int v14; // edx
  int v15; // r9d
  unsigned __int8 PropertyBooleanOrDefault; // al
  __int64 v17; // rcx
  int v18; // r8d
  __int64 v19; // r14
  void *v20; // rax
  int v21; // edx
  struct DOT11_NWF_BSSID_CANDIDATE *v22; // rdi
  unsigned int v23; // ecx
  unsigned int v24; // r8d
  unsigned __int8 *v25; // r12
  struct DOT11_NWF_BSSID_CANDIDATE *v26; // r14
  __int64 v27; // r13
  struct DOT11_NWF_BSSID_CANDIDATE *v28; // rsi
  _DWORD *v29; // rcx
  unsigned int v30; // r8d
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int v33; // esi
  int PropertyBuffer; // eax
  int v35; // edx
  int v36; // r8d
  unsigned __int8 *v37; // rcx
  __int64 v38; // r13
  struct DOT11_NWF_BSSID_CANDIDATE *v39; // r14
  __int64 v40; // r12
  struct DOT11_NWF_BSSID_CANDIDATE *v41; // r15
  __int64 v42; // rbx
  unsigned __int8 *v43; // rsi
  unsigned __int8 *v44; // rax
  char *v45; // rsi
  int v46; // r15d
  unsigned int v47; // r13d
  char *v48; // r14
  __int64 v49; // r13
  unsigned __int8 *v50; // rdi
  unsigned __int8 *v51; // r12
  unsigned int v52; // edi
  int v53; // edx
  unsigned int *v54; // rax
  unsigned int v55; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v56; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v57; // [rsp+48h] [rbp-B8h]
  unsigned __int8 *v58; // [rsp+50h] [rbp-B0h] BYREF
  CPropertyCache *v59; // [rsp+58h] [rbp-A8h]
  struct DOT11_NWF_BSSID_CANDIDATE **v60; // [rsp+60h] [rbp-A0h]
  void *v61; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 *v62; // [rsp+70h] [rbp-90h]
  struct CBSSEntry **v63; // [rsp+78h] [rbp-88h]
  unsigned int *v64; // [rsp+80h] [rbp-80h]
  unsigned int *v65; // [rsp+88h] [rbp-78h]
  _DWORD *v66; // [rsp+90h] [rbp-70h]
  _QWORD v67[12]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v68[320]; // [rsp+100h] [rbp+0h] BYREF

  v5 = a2;
  v66 = a5;
  v65 = a4;
  v60 = a3;
  v64 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      59,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
  }
  v7 = 40;
  if ( *v5 > 0x28 )
    v7 = *v5;
  v8 = (struct CBSSEntry **)operator new(saturated_mul((unsigned int)v7, 8u));
  v63 = v8;
  Base = v8;
  if ( v8 )
  {
    memset(v8, 0, 8 * v7);
    _WFC_CONNECTION_PROFILE_PARAMETERS::_WFC_CONNECTION_PROFILE_PARAMETERS((_WFC_CONNECTION_PROFILE_PARAMETERS *)v68);
    v11 = (CPropertyCache *)(a1 + 480);
    v59 = (CPropertyCache *)(a1 + 480);
    MatchingBSSEntriesForConnect = CConnectHelpers::PopulateConnectionParameters(
                                     (CConnectHelpers *)(a1 + 480),
                                     (struct CPortPropertyCache *)v68,
                                     v12);
    if ( MatchingBSSEntriesForConnect )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v15 = 61;
LABEL_14:
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          1,
          v15,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          MatchingBSSEntriesForConnect);
      }
    }
    else
    {
      memset(v67, 0, 88);
      v67[0] = v68;
      LODWORD(v67[2]) = *(_DWORD *)(*(_QWORD *)(a1 + 136) + 4648LL);
      PropertyBooleanOrDefault = CPropertyCache::GetPropertyBooleanOrDefault((CPropertyCache *)(a1 + 480), 0x14u, 0);
      v17 = *(_QWORD *)(a1 + 136);
      v55 = v7;
      LOBYTE(v67[7]) = PropertyBooleanOrDefault != 0;
      MatchingBSSEntriesForConnect = CBSSListManager::FindMatchingBSSEntriesForConnect(
                                       (CBSSListManager *)(v17 + 1336),
                                       (struct _BSS_ENTRY_CONNECT_MATCHING_CRITERIA *)v67,
                                       0x2CB41780u,
                                       &v55,
                                       Base);
      if ( !MatchingBSSEntriesForConnect )
      {
        v19 = v55;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v14) = 5;
          WPP_RECORDER_SF_Ld(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            v18,
            63,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            v55,
            *v5);
        }
        v20 = operator new(saturated_mul((unsigned int)v7, 0x10u));
        v61 = v20;
        v22 = (struct DOT11_NWF_BSSID_CANDIDATE *)v20;
        if ( v20 )
        {
          memset(v20, 0, 16LL * (unsigned int)v7);
          v23 = *v5;
          v56 = v7;
          details::RemoveDuplicates(v23, *v60, &v56, v22);
          v24 = v56;
          v57 = v56;
          v25 = (unsigned __int8 *)Base;
          v58 = (unsigned __int8 *)&Base[v19];
          if ( Base != (struct CBSSEntry **)v58 )
          {
            do
            {
              if ( v24 >= (unsigned int)v7 )
                break;
              v26 = v22;
              v27 = *(_QWORD *)v25;
              v28 = (struct DOT11_NWF_BSSID_CANDIDATE *)((char *)v22 + 16 * v56);
              while ( 1 )
              {
                v29 = (_DWORD *)(v27 + 32);
                if ( v26 == v28 )
                {
                  v30 = v57;
                  v31 = 2LL * v57;
                  *((_DWORD *)v22 + 2 * v31) = *v29;
                  *((_WORD *)v22 + 4 * v31 + 2) = *(_WORD *)(v27 + 36);
                  v32 = *(_BYTE *)(v27 + 44) != 0 ? 6 : 0;
                  v24 = v30 + 1;
                  v57 = v24;
                  *(_DWORD *)((char *)v22 + 8 * v31 + 6) = *(_DWORD *)(v32 + v27 + 32);
                  *((_WORD *)v22 + 4 * v31 + 5) = *(_WORD *)(v32 + v27 + 36);
                  *((_DWORD *)v22 + 2 * v31 + 3) = *(_DWORD *)(v27 + 888);
                  goto LABEL_28;
                }
                if ( RtlCompareMemory(v29, v26, 6u) == 6 )
                  break;
                v26 = (struct DOT11_NWF_BSSID_CANDIDATE *)((char *)v26 + 16);
              }
              v24 = v57;
LABEL_28:
              v25 += 8;
            }
            while ( v25 != v58 );
            v11 = v59;
          }
          v58 = 0;
          v55 = 0;
          v33 = 0;
          PropertyBuffer = CPropertyCache::GetPropertyBuffer(v11, 0x2Cu, &v55, &v58);
          v37 = v58;
          LODWORD(v59) = PropertyBuffer;
          if ( !PropertyBuffer && v55 >= 0xC )
            v33 = *((_DWORD *)v58 + 1);
          v38 = 2LL * v56;
          v55 = 0;
          v39 = v22;
          v40 = v33;
          v41 = (struct DOT11_NWF_BSSID_CANDIDATE *)((char *)v22 + 16 * v56);
          if ( v22 != v41 )
          {
            v42 = 28LL * v33;
            do
            {
              v43 = v37 + 12;
              v44 = &v37[v42 + 12];
              v62 = v44;
              while ( v43 != v44 )
              {
                if ( RtlCompareMemory(v39, v43, 6u) == 6 )
                  goto LABEL_40;
                v44 = v62;
                v43 += 28;
              }
              ++v55;
LABEL_40:
              v37 = v58;
              v39 = (struct DOT11_NWF_BSSID_CANDIDATE *)((char *)v39 + 16);
            }
            while ( v39 != v41 );
            Base = v63;
          }
          v45 = (char *)v22 + 8 * v38;
          v46 = 0;
          v47 = v57;
          v48 = &v45[16 * (v57 - v56)];
          if ( v45 != v48 )
          {
            v49 = 28 * v40;
            do
            {
              v50 = v37 + 12;
              v51 = &v37[v49 + 12];
              while ( v50 != v51 )
              {
                if ( RtlCompareMemory(v45, v50, 6u) == 6 )
                  goto LABEL_49;
                v50 += 28;
              }
              ++v46;
LABEL_49:
              v37 = v58;
              v45 += 16;
            }
            while ( v45 != v48 );
            v47 = v57;
          }
          v52 = v55;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v35) = 4;
            WPP_RECORDER_SF_dDd(
              WPP_GLOBAL_Control->DeviceExtension,
              v35,
              v36,
              65,
              (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
              v47,
              v55,
              v46);
          }
          wistd::unique_ptr<DOT11_NWF_BSSID_CANDIDATE [0],wistd::default_delete<DOT11_NWF_BSSID_CANDIDATE [0]>>::swap(
            v60,
            &v61);
          v54 = v65;
          *v64 = v47;
          *v54 = v52;
          *v66 = v46;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            LOBYTE(v53) = 5;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v53,
              1,
              66,
              (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
              (char)v59);
          }
          if ( v61 )
            operator delete(v61);
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v21) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v21,
            1,
            64,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
        }
        goto LABEL_61;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v15 = 62;
        goto LABEL_14;
      }
    }
LABEL_61:
    operator delete(Base);
    return;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      1,
      60,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
  }
}

```

## disassembly

```asm
0x1400a19c0  push    rbp
0x1400a19c2  push    rbx
0x1400a19c3  push    rsi
0x1400a19c4  push    rdi
0x1400a19c5  push    r12
0x1400a19c7  push    r13
0x1400a19c9  push    r14
0x1400a19cb  push    r15
0x1400a19cd  lea     rbp, [rsp-158h]
0x1400a19d5  sub     rsp, 258h
0x1400a19dc  mov     rax, cs:__security_cookie
0x1400a19e3  xor     rax, rsp
0x1400a19e6  mov     [rbp+190h+var_50], rax
0x1400a19ed  mov     rax, [rbp+190h+arg_20]
0x1400a19f4  mov     r12, rdx
0x1400a19f7  mov     [rbp+190h+var_200], rax
0x1400a19fb  mov     rdi, rcx
0x1400a19fe  mov     [rbp+190h+var_208], r9
0x1400a1a02  mov     [rsp+290h+var_230], r8
0x1400a1a07  mov     [rbp+190h+var_210], rdx
0x1400a1a0b  lea     r13, WPP_RECORDER_INITIALIZED
0x1400a1a12  xor     r14d, r14d
0x1400a1a15  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a1a1c  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a1a23  jz      short loc_1400A1A53
0x1400a1a25  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1a2c  cmp     byte ptr [rcx+29h], 5
0x1400a1a30  jnb     short loc_1400A1A39
0x1400a1a32  cmp     [rcx+48h], r14w
0x1400a1a37  jz      short loc_1400A1A53
0x1400a1a39  mov     rcx, [rcx+40h]
0x1400a1a3d  mov     r9d, 3Bh ; ';'
0x1400a1a43  mov     dl, 5
0x1400a1a45  mov     [rsp+290h+Base], rax
0x1400a1a4a  lea     r8d, [r9-3Ah]
0x1400a1a4e  call    WPP_RECORDER_SF_
0x1400a1a53  mov     eax, [r12]
0x1400a1a57  mov     r15d, 28h ; '('
0x1400a1a5d  cmp     eax, r15d
0x1400a1a60  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400a1a67  cmova   r15d, eax
0x1400a1a6b  mov     eax, 8
0x1400a1a70  mov     esi, r15d
0x1400a1a73  mul     rsi
0x1400a1a76  cmovb   rax, rcx
0x1400a1a7a  mov     rcx, rax; unsigned __int64
0x1400a1a7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400a1a82  mov     [rsp+290h+var_218], rax
0x1400a1a87  mov     rbx, rax
0x1400a1a8a  test    rax, rax
0x1400a1a8d  jz      loc_1400A1F40
0x1400a1a93  lea     r8, ds:0[r15*8]; Size
0x1400a1a9b  xor     edx, edx; Val
0x1400a1a9d  mov     rcx, rax; void *
0x1400a1aa0  call    memset
0x1400a1aa5  lea     rcx, [rbp+190h+var_190]; this
0x1400a1aa9  call    ??0_WFC_CONNECTION_PROFILE_PARAMETERS@@QEAA@XZ; _WFC_CONNECTION_PROFILE_PARAMETERS::_WFC_CONNECTION_PROFILE_PARAMETERS(void)
0x1400a1aae  lea     r13, [rdi+1E0h]
0x1400a1ab5  mov     rcx, r13; this
0x1400a1ab8  mov     [rsp+290h+var_238], r13
0x1400a1abd  lea     rdx, [rbp+190h+var_190]; struct CPortPropertyCache *
0x1400a1ac1  call    ?PopulateConnectionParameters@CConnectHelpers@@YAHPEAVCPortPropertyCache@@PEAU_WFC_CONNECTION_PROFILE_PARAMETERS@@@Z; CConnectHelpers::PopulateConnectionParameters(CPortPropertyCache *,_WFC_CONNECTION_PROFILE_PARAMETERS *)
0x1400a1ac6  test    eax, eax
0x1400a1ac8  jz      short loc_1400A1AE9
0x1400a1aca  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400a1ad1  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400a1ad8  jz      loc_1400A1F36
0x1400a1ade  mov     r9d, 3Dh ; '='
0x1400a1ae4  jmp     loc_1400A1B83
0x1400a1ae9  xor     eax, eax
0x1400a1aeb  lea     rcx, [rbp+190h+var_1F0]; void *
0x1400a1aef  xor     edx, edx; Val
0x1400a1af1  mov     [rbp+190h+var_1DC], eax
0x1400a1af4  mov     [rbp+190h+var_1BE], ax
0x1400a1af8  mov     [rbp+190h+var_1B4], eax
0x1400a1afb  lea     r8d, [rax+48h]; Size
0x1400a1aff  call    memset
0x1400a1b04  lea     rax, [rbp+190h+var_190]
0x1400a1b08  mov     [rbp+190h+var_1A8], r14
0x1400a1b0c  mov     [rbp+190h+var_1F0], rax
0x1400a1b10  xor     r8d, r8d; unsigned __int8
0x1400a1b13  mov     rax, [rdi+88h]
0x1400a1b1a  mov     [rbp+190h+var_1A0], r14
0x1400a1b1e  lea     edx, [r8+14h]; unsigned int
0x1400a1b22  mov     ecx, [rax+1228h]
0x1400a1b28  mov     [rbp+190h+var_1E0], ecx
0x1400a1b2b  mov     rcx, r13; this
0x1400a1b2e  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x1400a1b33  mov     rcx, [rdi+88h]
0x1400a1b3a  lea     r9, [rsp+290h+var_250]; unsigned int *
0x1400a1b3f  test    al, al
0x1400a1b41  mov     [rsp+290h+var_250], r15d
0x1400a1b46  mov     r8d, 2CB41780h; unsigned int
0x1400a1b4c  mov     [rsp+290h+Base], rbx; Base
0x1400a1b51  setnz   [rbp+190h+var_1B8]
0x1400a1b55  lea     rdx, [rbp+190h+var_1F0]; struct _BSS_ENTRY_CONNECT_MATCHING_CRITERIA *
0x1400a1b59  add     rcx, 538h; this
0x1400a1b60  call    ?FindMatchingBSSEntriesForConnect@CBSSListManager@@QEAAHPEAU_BSS_ENTRY_CONNECT_MATCHING_CRITERIA@@KPEAKPEAPEAVCBSSEntry@@@Z; CBSSListManager::FindMatchingBSSEntriesForConnect(_BSS_ENTRY_CONNECT_MATCHING_CRITERIA *,ulong,ulong *,CBSSEntry * *)
0x1400a1b65  test    eax, eax
0x1400a1b67  jz      short loc_1400A1BB0
0x1400a1b69  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400a1b70  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400a1b77  jz      loc_1400A1F36
0x1400a1b7d  mov     r9d, 3Eh ; '>'
0x1400a1b83  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1b8a  mov     r8d, 1
0x1400a1b90  mov     [rsp+290h+var_268], eax
0x1400a1b94  mov     dl, 2
0x1400a1b96  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a1b9d  mov     [rsp+290h+Base], rax
0x1400a1ba2  mov     rcx, [rcx+40h]
0x1400a1ba6  call    WPP_RECORDER_SF_d
0x1400a1bab  jmp     loc_1400A1F36
0x1400a1bb0  mov     r14d, [rsp+290h+var_250]
0x1400a1bb5  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400a1bbc  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400a1bc3  jz      short loc_1400A1C04
0x1400a1bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1bcc  cmp     byte ptr [rcx+29h], 5
0x1400a1bd0  jnb     short loc_1400A1BDA
0x1400a1bd2  xor     edi, edi
0x1400a1bd4  cmp     [rcx+48h], di
0x1400a1bd8  jz      short loc_1400A1C04
0x1400a1bda  mov     eax, [r12]
0x1400a1bde  mov     r9d, 3Fh ; '?'
0x1400a1be4  mov     rcx, [rcx+40h]
0x1400a1be8  mov     dl, 5
0x1400a1bea  mov     [rsp+290h+var_260], eax
0x1400a1bee  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a1bf5  mov     [rsp+290h+var_268], r14d
0x1400a1bfa  mov     [rsp+290h+Base], rax
0x1400a1bff  call    WPP_RECORDER_SF_Ld
0x1400a1c04  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400a1c0b  mov     eax, 10h
0x1400a1c10  mul     rsi
0x1400a1c13  cmovb   rax, rcx
0x1400a1c17  mov     rcx, rax; unsigned __int64
0x1400a1c1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400a1c1f  mov     [rsp+290h+var_228], rax
0x1400a1c24  mov     rdi, rax
0x1400a1c27  test    rax, rax
0x1400a1c2a  jz      loc_1400A1EFE
0x1400a1c30  shl     rsi, 4
0x1400a1c34  xor     edx, edx; Val
0x1400a1c36  mov     r8, rsi; Size
0x1400a1c39  mov     rcx, rax; void *
0x1400a1c3c  call    memset
0x1400a1c41  mov     rdx, [rsp+290h+var_230]
0x1400a1c46  lea     r8, [rsp+290h+var_24C]; unsigned int *
0x1400a1c4b  mov     ecx, [r12]; unsigned int
0x1400a1c4f  mov     r9, rdi; struct DOT11_NWF_BSSID_CANDIDATE *
0x1400a1c52  mov     [rsp+290h+var_24C], r15d
0x1400a1c57  mov     rdx, [rdx]; struct DOT11_NWF_BSSID_CANDIDATE *
0x1400a1c5a  call    ?RemoveDuplicates@details@@YAXKPEAUDOT11_NWF_BSSID_CANDIDATE@@AEAK0@Z; details::RemoveDuplicates(ulong,DOT11_NWF_BSSID_CANDIDATE *,ulong &,DOT11_NWF_BSSID_CANDIDATE *)
0x1400a1c5f  mov     r8d, [rsp+290h+var_24C]
0x1400a1c64  lea     rax, [rbx+r14*8]
0x1400a1c68  mov     [rsp+290h+var_248], r8d
0x1400a1c6d  mov     r12, rbx
0x1400a1c70  mov     [rsp+290h+var_240], rax
0x1400a1c75  cmp     rbx, rax
0x1400a1c78  jz      loc_1400A1D2A
0x1400a1c7e  cmp     r8d, r15d
0x1400a1c81  jnb     loc_1400A1D25
0x1400a1c87  mov     esi, [rsp+290h+var_24C]
0x1400a1c8b  mov     r14, rdi
0x1400a1c8e  mov     r13, [r12]
0x1400a1c92  shl     rsi, 4
0x1400a1c96  add     rsi, rdi
0x1400a1c99  lea     rcx, [r13+20h]; Source1
0x1400a1c9d  cmp     r14, rsi
0x1400a1ca0  jz      short loc_1400A1CC3
0x1400a1ca2  mov     r8d, 6; Length
0x1400a1ca8  mov     rdx, r14; Source2
0x1400a1cab  call    cs:__imp_RtlCompareMemory
0x1400a1cb2  nop     dword ptr [rax+rax+00h]
0x1400a1cb7  cmp     rax, 6
0x1400a1cbb  jz      short loc_1400A1D11
0x1400a1cbd  add     r14, 10h
0x1400a1cc1  jmp     short loc_1400A1C99
0x1400a1cc3  mov     eax, [rcx]
0x1400a1cc5  mov     r8d, [rsp+290h+var_248]
0x1400a1cca  mov     edx, r8d
0x1400a1ccd  add     rdx, rdx
0x1400a1cd0  mov     [rdi+rdx*8], eax
0x1400a1cd3  movzx   eax, word ptr [rcx+4]
0x1400a1cd7  mov     [rdi+rdx*8+4], ax
0x1400a1cdc  mov     al, [r13+2Ch]
0x1400a1ce0  neg     al
0x1400a1ce2  sbb     rcx, rcx
0x1400a1ce5  and     ecx, 6
0x1400a1ce8  inc     r8d
0x1400a1ceb  mov     [rsp+290h+var_248], r8d
0x1400a1cf0  mov     eax, [rcx+r13+20h]
0x1400a1cf5  mov     [rdi+rdx*8+6], eax
0x1400a1cf9  movzx   eax, word ptr [rcx+r13+24h]
0x1400a1cff  mov     [rdi+rdx*8+0Ah], ax
0x1400a1d04  mov     eax, [r13+378h]
0x1400a1d0b  mov     [rdi+rdx*8+0Ch], eax
0x1400a1d0f  jmp     short loc_1400A1D16
0x1400a1d11  mov     r8d, [rsp+290h+var_248]
0x1400a1d16  add     r12, 8
0x1400a1d1a  cmp     r12, [rsp+290h+var_240]
0x1400a1d1f  jnz     loc_1400A1C7E
0x1400a1d25  mov     r13, [rsp+290h+var_238]
0x1400a1d2a  xor     r14d, r14d
0x1400a1d2d  lea     r9, [rsp+290h+var_240]; unsigned __int8 **
0x1400a1d32  lea     r8, [rsp+290h+var_250]; unsigned int *
0x1400a1d37  mov     [rsp+290h+var_240], r14
0x1400a1d3c  mov     rcx, r13; this
0x1400a1d3f  mov     [rsp+290h+var_250], r14d
0x1400a1d44  mov     esi, r14d
0x1400a1d47  lea     edx, [r14+2Ch]; unsigned int
0x1400a1d4b  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400a1d50  mov     rcx, [rsp+290h+var_240]
0x1400a1d55  mov     dword ptr [rsp+290h+var_238], eax
0x1400a1d59  test    eax, eax
0x1400a1d5b  jnz     short loc_1400A1D67
0x1400a1d5d  cmp     [rsp+290h+var_250], 0Ch
0x1400a1d62  jb      short loc_1400A1D67
0x1400a1d64  mov     esi, [rcx+4]
0x1400a1d67  mov     r13d, [rsp+290h+var_24C]
0x1400a1d6c  add     r13, r13
0x1400a1d6f  mov     [rsp+290h+var_250], r14d
0x1400a1d74  mov     r14, rdi
0x1400a1d77  mov     r12d, esi
0x1400a1d7a  lea     r15, [rdi+r13*8]
0x1400a1d7e  cmp     rdi, r15
0x1400a1d81  jz      short loc_1400A1DD9
0x1400a1d83  imul    rbx, r12, 1Ch
0x1400a1d87  lea     rsi, [rcx+0Ch]
0x1400a1d8b  lea     rax, [rbx+rsi]
0x1400a1d8f  mov     [rsp+290h+var_220], rax
0x1400a1d94  cmp     rsi, rax
0x1400a1d97  jz      short loc_1400A1DC2
0x1400a1d99  mov     r8d, 6; Length
0x1400a1d9f  mov     rdx, rsi; Source2
0x1400a1da2  mov     rcx, r14; Source1
0x1400a1da5  call    cs:__imp_RtlCompareMemory
0x1400a1dac  nop     dword ptr [rax+rax+00h]
0x1400a1db1  cmp     rax, 6
0x1400a1db5  jz      short loc_1400A1DC6
0x1400a1db7  mov     rax, [rsp+290h+var_220]
0x1400a1dbc  add     rsi, 1Ch
0x1400a1dc0  jmp     short loc_1400A1D94
0x1400a1dc2  inc     [rsp+290h+var_250]
0x1400a1dc6  mov     rcx, [rsp+290h+var_240]
0x1400a1dcb  add     r14, 10h
0x1400a1dcf  cmp     r14, r15
0x1400a1dd2  jnz     short loc_1400A1D87
0x1400a1dd4  mov     rbx, [rsp+290h+var_218]
0x1400a1dd9  lea     rsi, [rdi+r13*8]
0x1400a1ddd  xor     r15d, r15d
0x1400a1de0  mov     r13d, [rsp+290h+var_248]
0x1400a1de5  mov     r14d, r13d
0x1400a1de8  sub     r14d, [rsp+290h+var_24C]
0x1400a1ded  shl     r14, 4
0x1400a1df1  add     r14, rsi
0x1400a1df4  cmp     rsi, r14
0x1400a1df7  jz      short loc_1400A1E44
0x1400a1df9  imul    r13, r12, 1Ch
0x1400a1dfd  lea     rdi, [rcx+0Ch]
0x1400a1e01  lea     r12, [rdi+r13]
0x1400a1e05  cmp     rdi, r12
0x1400a1e08  jz      short loc_1400A1E2E
0x1400a1e0a  mov     r8d, 6; Length
0x1400a1e10  mov     rdx, rdi; Source2
0x1400a1e13  mov     rcx, rsi; Source1
0x1400a1e16  call    cs:__imp_RtlCompareMemory
0x1400a1e1d  nop     dword ptr [rax+rax+00h]
0x1400a1e22  cmp     rax, 6
0x1400a1e26  jz      short loc_1400A1E31
0x1400a1e28  add     rdi, 1Ch
0x1400a1e2c  jmp     short loc_1400A1E05
0x1400a1e2e  inc     r15d
0x1400a1e31  mov     rcx, [rsp+290h+var_240]
0x1400a1e36  add     rsi, 10h
0x1400a1e3a  cmp     rsi, r14
0x1400a1e3d  jnz     short loc_1400A1DFD
0x1400a1e3f  mov     r13d, [rsp+290h+var_248]
0x1400a1e44  mov     edi, [rsp+290h+var_250]
0x1400a1e48  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400a1e4f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a1e56  lea     r14, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a1e5d  jz      short loc_1400A1E8A
0x1400a1e5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1e66  mov     r9d, 41h ; 'A'
0x1400a1e6c  mov     [rsp+290h+var_258], r15d
0x1400a1e71  mov     dl, 4
0x1400a1e73  mov     [rsp+290h+var_260], edi
0x1400a1e77  mov     [rsp+290h+var_268], r13d
0x1400a1e7c  mov     rcx, [rcx+40h]
0x1400a1e80  mov     [rsp+290h+Base], r14
0x1400a1e85  call    WPP_RECORDER_SF_dDd
0x1400a1e8a  mov     rcx, [rsp+290h+var_230]
0x1400a1e8f  lea     rdx, [rsp+290h+var_228]
0x1400a1e94  call    ?swap@?$unique_ptr@$$BY0A@UDOT11_NWF_BSSID_CANDIDATE@@U?$default_delete@$$BY0A@UDOT11_NWF_BSSID_CANDIDATE@@@wistd@@@wistd@@QEAAXAEAV12@@Z; wistd::unique_ptr<DOT11_NWF_BSSID_CANDIDATE [0],wistd::default_delete<DOT11_NWF_BSSID_CANDIDATE [0]>>::swap(wistd::unique_ptr<DOT11_NWF_BSSID_CANDIDATE [0],wistd::default_delete<DOT11_NWF_BSSID_CANDIDATE [0]>> &)
0x1400a1e99  mov     rax, [rbp+190h+var_208]
0x1400a1e9d  mov     rcx, [rbp+190h+var_210]
0x1400a1ea1  mov     [rcx], r13d
0x1400a1ea4  mov     [rax], edi
  ... truncated ...
```
