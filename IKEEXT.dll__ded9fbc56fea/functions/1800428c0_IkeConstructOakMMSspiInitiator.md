# IkeConstructOakMMSspiInitiator

- ea: `0x1800428c0`
- end: `0x180043268`
- name: `IkeConstructOakMMSspiInitiator`
- size: `2472`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `loader_planting, installer_update`

## callers

- `0x1800416f0`

## callees

- `0x18000251c`
- `0x180003cf0`
- `0x180008388`
- `0x180010770`
- `0x18001fab0`
- `0x180025d88`
- `0x1800428c0`
- `0x180045400`
- `0x1800460c0`
- `0x180046ab0`
- `0x180047450`
- `0x18004890c`
- `0x18004d2a8`
- `0x18004e908`
- `0x180050850`
- `0x18007ca4c`
- `0x18007ec38`
- `0x18007f2e8`
- `0x1800b4e30`
- `0x1800c1268`
- `0x1800e2aac`
- `0x1800f4550`
- `0x1800fbcc4`
- `0x180102470`
- `0x180117fa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004295a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004299f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180042ced`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180042d5e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180042da3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800430f5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004313a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004295a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004299f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180042ced`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180042d5e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180042da3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800430f5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004313a`
- `ntdll!EtwEventWriteTransfer` at `0x180042a70`
- `ntdll!EtwEventWriteTransfer` at `0x180042e87`
- `ntdll!EtwEventWriteTransfer` at `0x180043205`
- `ntdll!EtwEventWriteTransfer` at `0x180042a70`
- `ntdll!EtwEventWriteTransfer` at `0x180042e87`
- `ntdll!EtwEventWriteTransfer` at `0x180043205`

## pseudocode

```c
__int64 __fastcall IkeConstructOakMMSspiInitiator(__int64 LockSemaphore_low)
{
  __int64 v1; // rdi
  __int64 v2; // rsi
  LPCRITICAL_SECTION v3; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v6; // rcx
  DWORD v7; // ecx
  char *v8; // rax
  const WCHAR *v9; // rdx
  __int64 v10; // rax
  bool v11; // zf
  int v12; // eax
  _DWORD *v13; // rdx
  __int64 PeerSPN; // rbx
  unsigned int IPVersion; // eax
  __int64 v16; // r8
  unsigned int *v17; // rdx
  __int64 v18; // rax
  _QWORD *v19; // rbx
  __int64 *v20; // rax
  __int64 v21; // r14
  __int64 v22; // rbx
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v24; // rax
  DWORD v25; // ecx
  __int64 *v26; // rax
  __int64 v27; // rcx
  DWORD v28; // ecx
  char *v29; // rax
  const WCHAR *v30; // rdx
  __int64 v31; // rax
  int v32; // eax
  unsigned int *v33; // rdx
  unsigned int v34; // r8d
  __int64 v35; // rdx
  __int64 v36; // r8
  int AuthType; // eax
  int v38; // r9d
  __int64 v39; // r10
  LPCRITICAL_SECTION v40; // rax
  DWORD v41; // ecx
  __int64 *v42; // rax
  __int64 v43; // rcx
  DWORD v44; // ecx
  char *v45; // rax
  const WCHAR *v46; // rdx
  int v47; // esi
  __int64 v49; // [rsp+48h] [rbp-61h] BYREF
  char *v50; // [rsp+50h] [rbp-59h] BYREF
  int v51; // [rsp+58h] [rbp-51h]
  int v52; // [rsp+5Ch] [rbp-4Dh]
  __int16 *v53; // [rsp+60h] [rbp-49h]
  int v54; // [rsp+68h] [rbp-41h]
  int v55; // [rsp+6Ch] [rbp-3Dh]
  __int64 *v56; // [rsp+70h] [rbp-39h]
  __int64 v57; // [rsp+78h] [rbp-31h]
  const WCHAR *v58; // [rsp+80h] [rbp-29h]
  int v59; // [rsp+88h] [rbp-21h]
  int v60; // [rsp+8Ch] [rbp-1Dh]
  const char *v61; // [rsp+90h] [rbp-19h]
  __int64 v62; // [rsp+98h] [rbp-11h]
  _QWORD *v63; // [rsp+A0h] [rbp-9h]
  __int64 v64; // [rsp+A8h] [rbp-1h]
  _QWORD v65[2]; // [rsp+B0h] [rbp+7h] BYREF
  int v66; // [rsp+C0h] [rbp+17h] BYREF
  int v67; // [rsp+C4h] [rbp+1Bh]
  __int64 v68; // [rsp+C8h] [rbp+1Fh]

  v1 = LockSemaphore_low;
  v2 = -1;
  if ( (unsigned int)dword_180173278 <= 5 )
    goto LABEL_20;
  LockSemaphore_low = qword_180173290;
  if ( (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v3 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v3 = gIkeExtGlobals;
LABEL_9:
    v6 = 0;
    goto LABEL_10;
  }
  v6 = *Value;
  v3 = gIkeExtGlobals;
LABEL_10:
  v49 = v6;
  v56 = &v49;
  v57 = 8;
  if ( !v3 )
    goto LABEL_18;
  v7 = (DWORD)v3[86].LockSemaphore;
  if ( v7 == -1 )
    goto LABEL_18;
  v8 = (char *)TlsGetValue(v7);
  v9 = (const WCHAR *)(v8 + 8);
  if ( !v8 )
    v9 = 0;
  if ( v9 )
  {
    v10 = -1;
    do
      v11 = v9[++v10] == 0;
    while ( !v11 );
    v12 = 2 * v10 + 2;
  }
  else
  {
LABEL_18:
    v9 = &LocaleName;
    v12 = 2;
  }
  v59 = v12;
  v50 = off_180173280;
  v58 = v9;
  v60 = 0;
  v61 = "IkeConstructOakMMSspiInitiator";
  v62 = 31;
  v65[0] = 0x50B000000LL;
  v65[1] = 1;
  v51 = *(unsigned __int16 *)off_180173280;
  v53 = (__int16 *)&dword_180166EA4;
  v52 = 2;
  v54 = 45;
  v55 = 1;
  EtwEventWriteTransfer(qword_180173298, v65, 0, 0, 5, &v50);
LABEL_20:
  v13 = *(_DWORD **)(v1 + 600);
  switch ( *v13 )
  {
    case 0:
      IkeGetSspiContext(v1, 0, 0);
      PeerSPN = IkeConstructMMSA((__int64 *)(v1 + 696), v1 + 584, *(_QWORD *)(v1 + 736), 0, *(_QWORD *)(v1 + 960));
      if ( !PeerSPN )
      {
        *(_DWORD *)(*(_QWORD *)(v1 + 1088) + 8LL) = *(unsigned __int16 *)(v1 + 708)
                                                  - *(unsigned __int16 *)(v1 + 710)
                                                  - 4;
        PeerSPN = WfpMemAlloc(*(unsigned int *)(*(_QWORD *)(v1 + 1088) + 8LL), 8u);
        if ( !PeerSPN )
        {
          memcpy_0(
            *(void **)(*(_QWORD *)(v1 + 1088) + 16LL),
            (const void *)(*(unsigned __int16 *)(v1 + 710) + 4LL + *(_QWORD *)(v1 + 696)),
            *(unsigned int *)(*(_QWORD *)(v1 + 1088) + 8LL));
          PeerSPN = IkeOptionalConstructCoexistenceVendorId(
                      (int)v1 + 696,
                      (_BYTE *)(v1 + 376),
                      *(_QWORD *)(v1 + 1008) + 184LL,
                      v1);
          if ( !PeerSPN )
          {
            IPVersion = IkeAddrGetIPVersion(v1 + 376);
            PeerSPN = IkeConstructStandardVendorIds(v1 + 696, v1 + 584, IPVersion);
            if ( !PeerSPN )
              **(_DWORD **)(v1 + 600) = 1;
          }
        }
      }
      goto LABEL_76;
    case 1:
      PeerSPN = IkeOptionalConstructKEInitiator(v1 + 696, v1);
      if ( !PeerSPN )
      {
        PeerSPN = IkeConstructNonce(v1 + 584, v1 + 696, v16, v1 + 880);
        if ( !PeerSPN )
        {
          v17 = *(unsigned int **)(v1 + 744);
          v18 = *v17;
          if ( v17[80 * v18 + 14] )
          {
            *(_OWORD *)(*(_QWORD *)(v1 + 1088) + 24LL) = *(_OWORD *)&v17[80 * v18 + 14];
            *(_OWORD *)(320LL * **(unsigned int **)(v1 + 744) + *(_QWORD *)(v1 + 744) + 56) = 0;
          }
          PeerSPN = IkeGetPeerSPN(v1, *(_QWORD *)(v1 + 960));
          if ( !PeerSPN )
          {
            PeerSPN = IkeConstructSspi(v1, v1 + 696, *(_QWORD *)(v1 + 960));
            if ( !PeerSPN )
            {
              PeerSPN = IkeOptionalConstructNatDisc(v1 + 696, v1);
              if ( !PeerSPN )
                **(_DWORD **)(v1 + 600) = 2;
            }
          }
        }
      }
      goto LABEL_76;
    case 2:
    case 3:
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        if ( gIkeExtGlobals
          && (LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)LockSemaphore_low != -1)
          && (v20 = (__int64 *)TlsGetValue(LockSemaphore_low), v19 = WPP_GLOBAL_Control, v20) )
        {
          v21 = *v20;
        }
        else
        {
          LODWORD(v21) = 0;
        }
        v22 = v19[2];
        TlsPeerAddr = IkeGetTlsPeerAddr(LockSemaphore_low);
        WPP_SF_iSq(v22, 57, (unsigned int)WPP_142eefe8c0a8324bd0f22eb85fef74f7_Traceguids, v21, TlsPeerAddr, v1);
      }
      if ( (unsigned int)dword_180173278 <= 4 )
        goto LABEL_60;
      v24 = gIkeExtGlobals;
      if ( !gIkeExtGlobals )
        goto LABEL_49;
      v25 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v25 == -1 )
        goto LABEL_49;
      v26 = (__int64 *)TlsGetValue(v25);
      if ( v26 )
      {
        v27 = *v26;
        v24 = gIkeExtGlobals;
      }
      else
      {
        v24 = gIkeExtGlobals;
LABEL_49:
        v27 = 0;
      }
      v49 = v27;
      v56 = &v49;
      v57 = 8;
      if ( !v24 )
        goto LABEL_58;
      v28 = (DWORD)v24[86].LockSemaphore;
      if ( v28 == -1 )
        goto LABEL_58;
      v29 = (char *)TlsGetValue(v28);
      v30 = (const WCHAR *)(v29 + 8);
      if ( !v29 )
        v30 = 0;
      if ( v30 )
      {
        v31 = -1;
        do
          v11 = v30[++v31] == 0;
        while ( !v11 );
        v32 = 2 * v31 + 2;
      }
      else
      {
LABEL_58:
        v30 = &LocaleName;
        v32 = 2;
      }
      v59 = v32;
      v58 = v30;
      v61 = "IKE Kerb Continue for MM SA";
      v60 = 0;
      v63 = v65;
      v67 = 4;
      v50 = off_180173280;
      v62 = 28;
      v65[0] = v1;
      v64 = 8;
      v66 = 184549376;
      v68 = 0;
      v51 = *(unsigned __int16 *)off_180173280;
      v53 = &word_1801615C6;
      v52 = 2;
      v54 = 53;
      v55 = 1;
      EtwEventWriteTransfer(qword_180173298, &v66, 0, 0, 6, &v50);
LABEL_60:
      if ( (*(_DWORD *)(*(_QWORD *)(v1 + 960) + 72LL) & 0x20000) != 0 )
        goto LABEL_67;
      IkeUpdateNatState(v1 + 624, v1 + 584, v1);
      IkeCheckSAFloatInitiator(v1);
      PeerSPN = IkeInitSACrypto(v1 + 752, 320LL * **(unsigned int **)(v1 + 744) + *(_QWORD *)(v1 + 744) + 16LL, v1);
      if ( !PeerSPN )
      {
        v33 = *(unsigned int **)(v1 + 744);
        v34 = v33 ? v33[80 * *v33 + 12] : 13;
        PeerSPN = IkeConstructId(v1, (int)v1 + 696, v34, (int)v1 + 376, 0, 0, *(_QWORD *)(v1 + 1088) + 40LL);
        if ( !PeerSPN )
        {
          *(_DWORD *)(*(_QWORD *)(v1 + 960) + 72LL) |= 0x20000u;
LABEL_67:
          PeerSPN = IkeConstructSspi(v1, v1 + 696, *(_QWORD *)(v1 + 960));
          if ( !PeerSPN )
            **(_DWORD **)(v1 + 600) = 3;
        }
      }
LABEL_76:
      if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
        return IkeReturnError(PeerSPN, "IkeConstructOakMMSspiInitiator");
      v40 = gIkeExtGlobals;
      if ( !gIkeExtGlobals )
        goto LABEL_84;
      v41 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v41 == -1 )
        goto LABEL_84;
      v42 = (__int64 *)TlsGetValue(v41);
      if ( v42 )
      {
        v43 = *v42;
        v40 = gIkeExtGlobals;
      }
      else
      {
        v40 = gIkeExtGlobals;
LABEL_84:
        v43 = 0;
      }
      v65[0] = v43;
      v56 = v65;
      v57 = 8;
      if ( !v40 )
        goto LABEL_92;
      v44 = (DWORD)v40[86].LockSemaphore;
      if ( v44 == -1 )
        goto LABEL_92;
      v45 = (char *)TlsGetValue(v44);
      v46 = (const WCHAR *)(v45 + 8);
      if ( !v45 )
        v46 = 0;
      if ( v46 )
      {
        do
          v11 = v46[++v2] == 0;
        while ( !v11 );
        v47 = 2 * v2 + 2;
      }
      else
      {
LABEL_92:
        v46 = &LocaleName;
        v47 = 2;
      }
      v67 = 5;
      v50 = off_180173280;
      v58 = v46;
      v59 = v47;
      v60 = 0;
      v61 = "IkeConstructOakMMSspiInitiator";
      v62 = 31;
      v66 = 184549376;
      v68 = 1;
      v51 = *(unsigned __int16 *)off_180173280;
      v53 = (__int16 *)byte_180166E6B;
      v52 = 2;
      v54 = 45;
      v55 = 1;
      EtwEventWriteTransfer(qword_180173298, &v66, 0, 0, 5, &v50);
      return IkeReturnError(PeerSPN, "IkeConstructOakMMSspiInitiator");
    case 4:
      if ( (*(_DWORD *)(*(_QWORD *)(v1 + 960) + 72LL) & 0x20000) != 0
        || (IkeUpdateNatState(v1 + 624, v1 + 584, v1),
            IkeCheckSAFloatInitiator(v1),
            (PeerSPN = IkeInitSACrypto(
                         v1 + 752,
                         320LL * **(unsigned int **)(v1 + 744) + *(_QWORD *)(v1 + 744) + 16LL,
                         v1)) == 0)
        && (AuthType = IkeGetAuthType(*(_QWORD *)(v1 + 744), v35, v36, v1 + 376),
            (PeerSPN = IkeConstructId(v1, (int)v1 + 696, AuthType, v38, 0, 0, v39)) == 0) )
      {
        PeerSPN = IkeConstructOakMMHash(v1, 1);
        if ( !PeerSPN )
          **(_DWORD **)(v1 + 600) = 5;
      }
      goto LABEL_76;
    case 5:
      *v13 = 6;
      memcpy_0(*(void **)(v1 + 792), *(const void **)(v1 + 808), *(unsigned int *)(v1 + 800));
      PeerSPN = IkeBeginQMInitiator(0, v1);
      if ( !PeerSPN )
        IkeFreePacket(v1 + 696);
      goto LABEL_76;
    default:
      __fastfail(5u);
  }
}

```

## disassembly

```asm
0x1800428c0  mov     [rsp-8+arg_10], rsi
0x1800428c5  mov     [rsp-8+arg_18], rdi
0x1800428ca  push    rbp
0x1800428cb  push    r12
0x1800428cd  push    r13
0x1800428cf  push    r14
0x1800428d1  push    r15
0x1800428d3  lea     rbp, [rsp-37h]
0x1800428d8  sub     rsp, 0E0h
0x1800428df  mov     rax, cs:__security_cookie
0x1800428e6  xor     rax, rsp
0x1800428e9  mov     [rbp+57h+var_30], rax
0x1800428ed  mov     eax, cs:dword_180173278
0x1800428f3  lea     r12, aIkeconstructoa_3; "IkeConstructOakMMSspiInitiator"
0x1800428fa  xor     r15d, r15d
0x1800428fd  lea     r13, _TraceLoggingMetadataEnd
0x180042904  lea     r14, _TraceLoggingMetadata
0x18004290b  mov     rdi, rcx
0x18004290e  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180042915  cmp     eax, 5
0x180042918  jbe     loc_180042A76
0x18004291e  mov     rcx, cs:qword_180173290
0x180042925  mov     rax, cs:qword_180173288
0x18004292c  test    al, 1
0x18004292e  jz      loc_180042A76
0x180042934  mov     rax, rcx
0x180042937  and     eax, 1
0x18004293a  cmp     rax, rcx
0x18004293d  jnz     loc_180042A76
0x180042943  mov     rax, cs:gIkeExtGlobals
0x18004294a  test    rax, rax
0x18004294d  jz      short loc_180042978
0x18004294f  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180042955  cmp     ecx, 0FFFFFFFFh
0x180042958  jz      short loc_180042978
0x18004295a  call    cs:__imp_TlsGetValue
0x180042960  test    rax, rax
0x180042963  jz      short loc_180042971
0x180042965  mov     rcx, [rax]
0x180042968  mov     rax, cs:gIkeExtGlobals
0x18004296f  jmp     short loc_18004297B
0x180042971  mov     rax, cs:gIkeExtGlobals
0x180042978  mov     rcx, r15
0x18004297b  mov     [rbp+57h+var_B8], rcx
0x18004297f  lea     rcx, [rbp+57h+var_B8]
0x180042983  mov     [rbp+57h+var_90], rcx
0x180042987  mov     [rbp+57h+var_88], 8
0x18004298f  test    rax, rax
0x180042992  jz      short loc_1800429D5
0x180042994  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18004299a  cmp     ecx, 0FFFFFFFFh
0x18004299d  jz      short loc_1800429D5
0x18004299f  call    cs:__imp_TlsGetValue
0x1800429a5  test    rax, rax
0x1800429a8  lea     rdx, [rax+8]
0x1800429ac  cmovz   rdx, r15
0x1800429b0  test    rdx, rdx
0x1800429b3  jz      short loc_1800429D5
0x1800429b5  mov     rax, rsi
0x1800429b8  nop     dword ptr [rax+rax+00000000h]
0x1800429c0  cmp     [rdx+rax*2+2], r15w
0x1800429c6  lea     rax, [rax+1]
0x1800429ca  jnz     short loc_1800429C0
0x1800429cc  lea     eax, ds:2[rax*2]
0x1800429d3  jmp     short loc_1800429E1
0x1800429d5  lea     rdx, LocaleName
0x1800429dc  mov     eax, 2
0x1800429e1  mov     [rbp+57h+var_78], eax
0x1800429e4  xor     r9d, r9d
0x1800429e7  movzx   eax, cs:word_180166E9A
0x1800429ee  xor     r8d, r8d
0x1800429f1  mov     dword ptr [rbp+57h+var_50+4], eax
0x1800429f4  mov     rax, cs:off_180173280
0x1800429fb  mov     [rbp+57h+var_B0], rax
0x1800429ff  mov     [rbp+57h+var_80], rdx
0x180042a03  lea     rdx, [rbp+57h+var_50]
0x180042a07  mov     [rbp+57h+var_74], r15d
0x180042a0b  mov     [rbp+57h+var_70], r12
0x180042a0f  mov     [rbp+57h+var_68], 1Fh
0x180042a17  mov     dword ptr [rbp+57h+var_50], 0B000000h
0x180042a1e  mov     [rbp+57h+var_48], 1
0x180042a26  movzx   eax, word ptr [rax]
0x180042a29  mov     [rbp+57h+var_A8], eax
0x180042a2c  lea     rax, dword_180166EA4
0x180042a33  mov     [rbp+57h+var_A0], rax
0x180042a37  mov     rax, r13
0x180042a3a  sub     eax, r14d
0x180042a3d  mov     [rbp+57h+var_A4], 2
0x180042a44  mov     [rbp+57h+var_98], 2Dh ; '-'
0x180042a4b  mov     [rbp+57h+var_94], 1
0x180042a52  mov     [rbp+57h+var_C0], eax
0x180042a55  mov     eax, [rbp+57h+var_C0]
0x180042a58  mov     rcx, cs:qword_180173298
0x180042a5f  lea     rax, [rbp+57h+var_B0]
0x180042a63  mov     [rsp+100h+var_D8], rax
0x180042a68  mov     dword ptr [rsp+100h+var_E0], 5
0x180042a70  call    cs:__imp_EtwEventWriteTransfer
0x180042a76  mov     rdx, [rdi+258h]
0x180042a7d  mov     [rsp+100h+arg_8], rbx
0x180042a85  movsxd  rax, dword ptr [rdx]
0x180042a88  cmp     eax, 5; switch 6 cases
0x180042a8b  ja      def_180042AA3; jumptable 0000000180042AA3 default case
0x180042a91  lea     r8, __ImageBase
0x180042a98  mov     ecx, ds:(jpt_180042AA3 - 180000000h)[r8+rax*4]
0x180042aa0  add     rcx, r8
0x180042aa3  jmp     rcx; switch jump
0x180042aa5  xor     r8d, r8d; jumptable 0000000180042AA3 case 0
0x180042aa8  xor     edx, edx
0x180042aaa  mov     rcx, rdi
0x180042aad  call    IkeGetSspiContext
0x180042ab2  mov     rax, [rdi+3C0h]
0x180042ab9  lea     rdx, [rdi+248h]
0x180042ac0  mov     r8, [rdi+2E0h]
0x180042ac7  lea     rcx, [rdi+2B8h]
0x180042ace  xor     r9d, r9d
0x180042ad1  mov     [rsp+100h+var_E0], rax
0x180042ad6  call    IkeConstructMMSA
0x180042adb  mov     rbx, rax
0x180042ade  test    rax, rax
0x180042ae1  jnz     loc_1800430AA
0x180042ae7  movzx   ecx, word ptr [rdi+2C4h]
0x180042aee  mov     edx, 8; dwFlags
0x180042af3  movzx   eax, word ptr [rdi+2C6h]
0x180042afa  sub     ecx, eax
0x180042afc  mov     rax, [rdi+440h]
0x180042b03  sub     ecx, 4
0x180042b06  mov     [rax+8], ecx
0x180042b09  mov     rax, [rdi+440h]
0x180042b10  mov     ecx, [rax+8]; dwBytes
0x180042b13  lea     r8, [rax+10h]
0x180042b17  call    WfpMemAlloc
0x180042b1c  mov     rbx, rax
0x180042b1f  test    rax, rax
0x180042b22  jnz     loc_1800430AA
0x180042b28  mov     r9, [rdi+440h]
0x180042b2f  movzx   ecx, word ptr [rdi+2C6h]
0x180042b36  mov     rdx, [rdi+2B8h]
0x180042b3d  add     rcx, 4
0x180042b41  add     rdx, rcx; Src
0x180042b44  mov     r8d, [r9+8]; Size
0x180042b48  mov     rcx, [r9+10h]; void *
0x180042b4c  call    memcpy_0
0x180042b51  mov     r8, [rdi+3F0h]
0x180042b58  lea     rdx, [rdi+178h]
0x180042b5f  add     r8, 0B8h
0x180042b66  lea     rcx, [rdi+2B8h]
0x180042b6d  mov     r9, rdi
0x180042b70  call    IkeOptionalConstructCoexistenceVendorId
0x180042b75  mov     rbx, rax
0x180042b78  test    rax, rax
0x180042b7b  jnz     loc_1800430A3
0x180042b81  lea     rcx, [rdi+178h]
0x180042b88  call    IkeAddrGetIPVersion
0x180042b8d  mov     r8d, eax
0x180042b90  lea     rdx, [rdi+248h]
0x180042b97  lea     rcx, [rdi+2B8h]
0x180042b9e  call    IkeConstructStandardVendorIds
0x180042ba3  lea     r12, aIkeconstructoa_3; "IkeConstructOakMMSspiInitiator"
0x180042baa  mov     rbx, rax
0x180042bad  test    rax, rax
0x180042bb0  jnz     loc_1800430AA
0x180042bb6  mov     rax, [rdi+258h]
0x180042bbd  mov     dword ptr [rax], 1
0x180042bc3  jmp     loc_1800430AA
0x180042bc8  mov     rdx, rdi; jumptable 0000000180042AA3 case 1
0x180042bcb  lea     rcx, [rdi+2B8h]
0x180042bd2  call    IkeOptionalConstructKEInitiator
0x180042bd7  mov     rbx, rax
0x180042bda  test    rax, rax
0x180042bdd  jnz     loc_1800430AA
0x180042be3  lea     r9, [rdi+370h]
0x180042bea  lea     rcx, [rdi+248h]
0x180042bf1  lea     rdx, [rdi+2B8h]
0x180042bf8  call    IkeConstructNonce
0x180042bfd  mov     rbx, rax
0x180042c00  test    rax, rax
0x180042c03  jnz     loc_1800430AA
0x180042c09  mov     rdx, [rdi+2E8h]
0x180042c10  mov     eax, [rdx]
0x180042c12  lea     rcx, [rax+rax*4]
0x180042c16  shl     rcx, 6
0x180042c1a  cmp     [rcx+rdx+38h], r15d
0x180042c1f  jz      short loc_180042C4A
0x180042c21  movups  xmm0, xmmword ptr [rcx+rdx+38h]
0x180042c26  mov     rax, [rdi+440h]
0x180042c2d  movups  xmmword ptr [rax+18h], xmm0
0x180042c31  mov     rdx, [rdi+2E8h]
0x180042c38  xorps   xmm0, xmm0
0x180042c3b  mov     eax, [rdx]
0x180042c3d  lea     rcx, [rax+rax*4]
0x180042c41  shl     rcx, 6
0x180042c45  movups  xmmword ptr [rcx+rdx+38h], xmm0
0x180042c4a  mov     rdx, [rdi+3C0h]
0x180042c51  xor     r8d, r8d
0x180042c54  mov     rcx, rdi
0x180042c57  call    IkeGetPeerSPN
0x180042c5c  mov     rbx, rax
0x180042c5f  test    rax, rax
0x180042c62  jnz     loc_1800430AA
0x180042c68  mov     r8, [rdi+3C0h]
0x180042c6f  lea     rdx, [rdi+2B8h]
0x180042c76  mov     rcx, rdi
0x180042c79  call    IkeConstructSspi
0x180042c7e  mov     rbx, rax
0x180042c81  test    rax, rax
0x180042c84  jnz     loc_1800430AA
0x180042c8a  mov     rdx, rdi
0x180042c8d  lea     rcx, [rdi+2B8h]
0x180042c94  call    IkeOptionalConstructNatDisc
0x180042c99  mov     rbx, rax
0x180042c9c  test    rax, rax
0x180042c9f  jnz     loc_1800430AA
0x180042ca5  mov     rax, [rdi+258h]
0x180042cac  mov     dword ptr [rax], 2
0x180042cb2  jmp     loc_1800430AA
0x180042cb7  mov     rbx, cs:WPP_GLOBAL_Control; jumptable 0000000180042AA3 cases 2,3
0x180042cbe  lea     rax, WPP_GLOBAL_Control
0x180042cc5  cmp     rbx, rax
0x180042cc8  jz      short loc_180042D38
0x180042cca  cmp     byte ptr [rbx+19h], 4
0x180042cce  jb      short loc_180042D38
0x180042cd0  test    byte ptr [rbx+1Ch], 10h
0x180042cd4  jz      short loc_180042D38
0x180042cd6  mov     rax, cs:gIkeExtGlobals
0x180042cdd  test    rax, rax
0x180042ce0  jz      short loc_180042D04
0x180042ce2  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180042ce8  cmp     ecx, 0FFFFFFFFh
0x180042ceb  jz      short loc_180042D04
0x180042ced  call    cs:__imp_TlsGetValue
0x180042cf3  mov     rbx, cs:WPP_GLOBAL_Control
0x180042cfa  test    rax, rax
0x180042cfd  jz      short loc_180042D04
0x180042cff  mov     r14, [rax]
0x180042d02  jmp     short loc_180042D07
0x180042d04  mov     r14, r15
0x180042d07  mov     rbx, [rbx+10h]
0x180042d0b  call    IkeGetTlsPeerAddr
0x180042d10  mov     edx, 39h ; '9'
0x180042d15  mov     [rsp+100h+var_D8], rdi
0x180042d1a  mov     r9, r14
0x180042d1d  mov     [rsp+100h+var_E0], rax
0x180042d22  lea     r8, WPP_142eefe8c0a8324bd0f22eb85fef74f7_Traceguids
0x180042d29  mov     rcx, rbx
0x180042d2c  call    WPP_SF_iSq
0x180042d31  lea     r14, _TraceLoggingMetadata
0x180042d38  mov     eax, cs:dword_180173278
0x180042d3e  cmp     eax, 4
0x180042d41  jbe     loc_180042E8D
0x180042d47  mov     rax, cs:gIkeExtGlobals
0x180042d4e  test    rax, rax
0x180042d51  jz      short loc_180042D7C
0x180042d53  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180042d59  cmp     ecx, 0FFFFFFFFh
0x180042d5c  jz      short loc_180042D7C
0x180042d5e  call    cs:__imp_TlsGetValue
0x180042d64  test    rax, rax
0x180042d67  jz      short loc_180042D75
0x180042d69  mov     rcx, [rax]
0x180042d6c  mov     rax, cs:gIkeExtGlobals
0x180042d73  jmp     short loc_180042D7F
0x180042d75  mov     rax, cs:gIkeExtGlobals
0x180042d7c  mov     rcx, r15
0x180042d7f  mov     [rbp+57h+var_B8], rcx
0x180042d83  lea     rcx, [rbp+57h+var_B8]
0x180042d87  mov     [rbp+57h+var_90], rcx
0x180042d8b  mov     [rbp+57h+var_88], 8
0x180042d93  test    rax, rax
0x180042d96  jz      short loc_180042DD5
0x180042d98  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180042d9e  cmp     ecx, 0FFFFFFFFh
0x180042da1  jz      short loc_180042DD5
0x180042da3  call    cs:__imp_TlsGetValue
0x180042da9  test    rax, rax
0x180042dac  lea     rdx, [rax+8]
0x180042db0  cmovz   rdx, r15
0x180042db4  test    rdx, rdx
0x180042db7  jz      short loc_180042DD5
0x180042db9  mov     rax, rsi
0x180042dbc  nop     dword ptr [rax+00h]
0x180042dc0  cmp     [rdx+rax*2+2], r15w
0x180042dc6  lea     rax, [rax+1]
0x180042dca  jnz     short loc_180042DC0
0x180042dcc  lea     eax, ds:2[rax*2]
0x180042dd3  jmp     short loc_180042DE1
0x180042dd5  lea     rdx, LocaleName
0x180042ddc  mov     eax, 2
0x180042de1  mov     [rbp+57h+var_78], eax
0x180042de4  xor     r9d, r9d
0x180042de7  mov     [rbp+57h+var_80], rdx
0x180042deb  lea     rax, aIkeKerbContinu; "IKE Kerb Continue for MM SA"
0x180042df2  mov     [rbp+57h+var_70], rax
0x180042df6  lea     rdx, [rbp+57h+var_40]
0x180042dfa  lea     rax, [rbp+57h+var_50]
0x180042dfe  mov     [rbp+57h+var_74], r15d
0x180042e02  mov     [rbp+57h+var_60], rax
0x180042e06  xor     r8d, r8d
0x180042e09  movzx   eax, cs:word_1801615BC
0x180042e10  mov     [rbp+57h+var_3C], eax
0x180042e13  mov     rax, cs:off_180173280
  ... truncated ...
```
