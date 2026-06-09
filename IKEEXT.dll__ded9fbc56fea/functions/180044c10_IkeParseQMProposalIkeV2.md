# IkeParseQMProposalIkeV2

- ea: `0x180044c10`
- end: `0x1800453f8`
- name: `IkeParseQMProposalIkeV2`
- size: `2024`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800faf48`

## callees

- `0x1800061ec`
- `0x180006870`
- `0x180008388`
- `0x1800087f0`
- `0x180016e50`
- `0x180044c10`
- `0x180050850`
- `0x18006dec8`
- `0x18010f368`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044cc1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044d08`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044f87`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044fc2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004502c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045074`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004529c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800452e0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044cc1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044d08`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044f87`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044fc2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004502c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045074`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004529c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800452e0`
- `ntdll!EtwEventWriteTransfer` at `0x180044ddb`
- `ntdll!EtwEventWriteTransfer` at `0x18004516d`
- `ntdll!EtwEventWriteTransfer` at `0x1800453c0`
- `ntdll!EtwEventWriteTransfer` at `0x180044ddb`
- `ntdll!EtwEventWriteTransfer` at `0x18004516d`
- `ntdll!EtwEventWriteTransfer` at `0x1800453c0`
- `WS2_32!__imp_ntohl` at `0x180044f38`
- `WS2_32!__imp_ntohl` at `0x180044f38`
- `WS2_32!__imp_ntohs` at `0x180044e40`
- `WS2_32!__imp_ntohs` at `0x180044e40`

## string_xrefs

- `0x180044e21`: `IkeCopyIncomingData`

## pseudocode

```c
__int64 __fastcall IkeParseQMProposalIkeV2(__int64 a1, int a2, _QWORD *a3)
{
  unsigned __int8 v3; // di
  _QWORD *v4; // r15
  __int64 v6; // rsi
  LPCRITICAL_SECTION v7; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v10; // rcx
  DWORD v11; // ecx
  char *v12; // rax
  const WCHAR *v13; // rdx
  __int64 v14; // rax
  bool v15; // zf
  int v16; // eax
  unsigned __int8 v17; // r14
  u_short i; // r13
  __int64 v19; // rax
  __int64 v20; // rbx
  u_short v21; // ax
  __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned int v24; // edi
  u_long v25; // ecx
  _QWORD *v26; // rcx
  LPCRITICAL_SECTION v27; // rdx
  DWORD v28; // eax
  LPVOID v29; // rax
  LPVOID v30; // r8
  __int64 v31; // rbx
  DWORD v32; // eax
  __int64 *v33; // rax
  __int64 v34; // r9
  LPCRITICAL_SECTION v35; // rax
  DWORD v36; // ecx
  __int64 *v37; // rax
  __int64 v38; // rcx
  DWORD v39; // ecx
  char *v40; // rax
  const WCHAR *v41; // rdx
  __int64 v42; // rax
  int v43; // eax
  LPCRITICAL_SECTION v44; // rax
  DWORD v45; // ecx
  __int64 *v46; // rax
  __int64 v47; // rcx
  DWORD v48; // ecx
  char *v49; // rax
  const WCHAR *v50; // rdx
  __int64 v51; // r13
  int v52; // eax
  unsigned int v54; // [rsp+40h] [rbp-C0h]
  __int64 v55; // [rsp+48h] [rbp-B8h]
  u_short v56; // [rsp+50h] [rbp-B0h]
  int v57; // [rsp+54h] [rbp-ACh]
  u_long netlong; // [rsp+68h] [rbp-98h] BYREF
  __int64 v61; // [rsp+70h] [rbp-90h] BYREF
  int v62; // [rsp+78h] [rbp-88h] BYREF
  int v63; // [rsp+7Ch] [rbp-84h] BYREF
  char *v64; // [rsp+80h] [rbp-80h] BYREF
  int v65; // [rsp+88h] [rbp-78h]
  int v66; // [rsp+8Ch] [rbp-74h]
  char *v67; // [rsp+90h] [rbp-70h]
  int v68; // [rsp+98h] [rbp-68h]
  int v69; // [rsp+9Ch] [rbp-64h]
  __int64 *v70; // [rsp+A0h] [rbp-60h]
  __int64 v71; // [rsp+A8h] [rbp-58h]
  const WCHAR *v72; // [rsp+B0h] [rbp-50h]
  int v73; // [rsp+B8h] [rbp-48h]
  int v74; // [rsp+BCh] [rbp-44h]
  const char *v75; // [rsp+C0h] [rbp-40h]
  __int64 v76; // [rsp+C8h] [rbp-38h]
  int *v77; // [rsp+D0h] [rbp-30h]
  __int64 v78; // [rsp+D8h] [rbp-28h]
  _QWORD v79[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v80; // [rsp+F0h] [rbp-10h] BYREF
  int v81; // [rsp+F4h] [rbp-Ch]
  __int64 v82; // [rsp+F8h] [rbp-8h]

  *a3 = 0;
  v3 = 0;
  v4 = a3;
  v55 = 0;
  netlong = 0;
  v6 = 0;
  v57 = 1;
  v54 = 0;
  if ( (unsigned int)dword_180173278 > 5 && (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
  {
    v7 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( LockSemaphore != -1 )
      {
        Value = (__int64 *)TlsGetValue(LockSemaphore);
        if ( Value )
        {
          v10 = *Value;
          v7 = gIkeExtGlobals;
LABEL_10:
          v61 = v10;
          v70 = &v61;
          v71 = 8;
          if ( !v7 )
            goto LABEL_18;
          v11 = (DWORD)v7[86].LockSemaphore;
          if ( v11 == -1 )
            goto LABEL_18;
          v12 = (char *)TlsGetValue(v11);
          v13 = (const WCHAR *)(v12 + 8);
          if ( !v12 )
            v13 = 0;
          if ( v13 )
          {
            v14 = -1;
            do
              v15 = v13[++v14] == 0;
            while ( !v15 );
            v16 = 2 * v14 + 2;
          }
          else
          {
LABEL_18:
            v13 = &LocaleName;
            v16 = 2;
          }
          v73 = v16;
          v64 = off_180173280;
          v72 = v13;
          v74 = 0;
          v75 = "IkeParseQMProposalIkeV2";
          v76 = 24;
          v79[0] = 0x50B000000LL;
          v79[1] = 1;
          v65 = *(unsigned __int16 *)off_180173280;
          v67 = (char *)&dword_180166EA4;
          v66 = 2;
          v68 = 45;
          v69 = 1;
          EtwEventWriteTransfer(qword_180173298, v79, 0, 0, 5, &v64);
          goto LABEL_20;
        }
        v7 = gIkeExtGlobals;
      }
    }
    v10 = 0;
    goto LABEL_10;
  }
LABEL_20:
  v17 = 0;
  for ( i = 0; ; i = v56 )
  {
    v19 = IkeVerifyIncomingDataSize(a1, 8);
    if ( !v19 )
    {
      v55 = *(_QWORD *)(*(unsigned __int16 *)(a1 + 12) + *(_QWORD *)a1);
      v17 = BYTE4(v55);
      i = WORD1(v55);
    }
    v20 = IkeReturnError(v19, "IkeCopyIncomingData");
    if ( v20 )
      break;
    v21 = ntohs(i);
    *(_WORD *)(a1 + 12) += 8;
    v56 = v21;
    if ( !HIBYTE(v55) || a2 && v54 >= 2 )
      goto LABEL_79;
    if ( v54 )
    {
      if ( v17 < v3 )
        goto LABEL_79;
      if ( v17 == v3 )
      {
        if ( (unsigned int)++v57 > 2 )
          goto LABEL_79;
      }
      else
      {
        v57 = 1;
      }
    }
    LOBYTE(v22) = 1;
    v20 = IkeExpandQMPolicy(v4, v22);
    if ( v20 )
      break;
    ++*(_WORD *)(*v4 + 6LL);
    if ( BYTE6(v55) != 4 )
      goto LABEL_79;
    v20 = IkeCopyIncomingData(&netlong);
    if ( v20 )
      break;
    *(_WORD *)(a1 + 12) += 4;
    v24 = 0;
    if ( !HIBYTE(v55) )
      goto LABEL_72;
    do
    {
      v25 = netlong;
      v6 = 488LL * v54 + 8 + *a3;
      *(_BYTE *)(v6 + 480) = v17;
      *(_DWORD *)(v6 + 36) = ntohl(v25);
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v27 = gIkeExtGlobals;
        if ( !gIkeExtGlobals || (v28 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v28 == -1) )
        {
          v30 = 0;
        }
        else
        {
          v29 = TlsGetValue(v28);
          v26 = WPP_GLOBAL_Control;
          v30 = v29;
          v27 = gIkeExtGlobals;
        }
        v31 = (__int64)v30 + 8;
        if ( !v30 )
          v31 = 0;
        if ( v27
          && (v32 = (DWORD)v27[86].LockSemaphore, v32 != -1)
          && (v33 = (__int64 *)TlsGetValue(v32), v26 = WPP_GLOBAL_Control, v33) )
        {
          v34 = *v33;
        }
        else
        {
          LODWORD(v34) = 0;
        }
        WPP_SF_iSDD(
          v26[2],
          20,
          (unsigned int)WPP_f7416a5e69af345e38b1e64d61a85976_Traceguids,
          v34,
          v31,
          v17,
          *(_DWORD *)(v6 + 36));
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v35 = gIkeExtGlobals;
        if ( gIkeExtGlobals )
        {
          v36 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
          if ( v36 != -1 )
          {
            v37 = (__int64 *)TlsGetValue(v36);
            if ( v37 )
            {
              v38 = *v37;
              v35 = gIkeExtGlobals;
LABEL_59:
              v79[0] = v38;
              v70 = v79;
              v71 = 8;
              if ( !v35 )
                goto LABEL_67;
              v39 = (DWORD)v35[86].LockSemaphore;
              if ( v39 == -1 )
                goto LABEL_67;
              v40 = (char *)TlsGetValue(v39);
              v41 = (const WCHAR *)(v40 + 8);
              if ( !v40 )
                v41 = 0;
              if ( v41 )
              {
                v42 = -1;
                do
                  v15 = v41[++v42] == 0;
                while ( !v15 );
                v43 = 2 * v42 + 2;
              }
              else
              {
LABEL_67:
                v41 = &LocaleName;
                v43 = 2;
              }
              v73 = v43;
              v72 = v41;
              v74 = 0;
              v76 = 4;
              v78 = 4;
              v80 = 184549376;
              v82 = 0;
              v62 = v17;
              v75 = (const char *)&v62;
              v63 = *(_DWORD *)(v6 + 36);
              v77 = &v63;
              v81 = 4;
              v64 = off_180173280;
              v65 = *(unsigned __int16 *)off_180173280;
              v67 = byte_180162A49;
              v66 = 2;
              v68 = 60;
              v69 = 1;
              LODWORD(v61) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EtwEventWriteTransfer(qword_180173298, &v80, 0, 0, 6, &v64);
              goto LABEL_69;
            }
            v35 = gIkeExtGlobals;
          }
        }
        v38 = 0;
        goto LABEL_59;
      }
LABEL_69:
      v20 = IkeParseQMTransformsIkeV2(a1, BYTE5(v55), v6);
      if ( v20 )
        goto LABEL_80;
      ++v24;
    }
    while ( v24 < HIBYTE(v55) );
    v4 = a3;
LABEL_72:
    if ( !*(_WORD *)(v6 + 444) )
    {
      *(_DWORD *)(v6 + 384) = 0;
      *(_WORD *)(v6 + 444) = 1;
      v20 = IkeReturnError(0, "InsertDhToRcvTransformQmIkeV2");
      if ( v20 )
        break;
    }
    v23 = *(unsigned __int16 *)(v6 + 476);
    if ( !(_WORD)v23 )
    {
      *(_WORD *)(v6 + 446) = 0;
      *(_WORD *)(v6 + 476) = 1;
      v20 = IkeReturnError(0, "InsertEsnToRcvTransformQmIkeV2");
      if ( v20 )
        break;
    }
    v3 = v17;
    ++v54;
    if ( (_BYTE)v55 != 2 )
    {
      if ( !(_BYTE)v55 )
        break;
LABEL_79:
      v20 = WfpReportSysErrorAsWinError(v23, "IkeParseQMProposalIkeV2", 13843, 1);
      break;
    }
  }
LABEL_80:
  if ( (unsigned int)dword_180173278 > 5 && (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
  {
    v44 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v45 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v45 != -1 )
      {
        v46 = (__int64 *)TlsGetValue(v45);
        if ( v46 )
        {
          v47 = *v46;
          v44 = gIkeExtGlobals;
          goto LABEL_89;
        }
        v44 = gIkeExtGlobals;
      }
    }
    v47 = 0;
LABEL_89:
    v79[0] = v47;
    v70 = v79;
    v71 = 8;
    if ( !v44 )
      goto LABEL_97;
    v48 = (DWORD)v44[86].LockSemaphore;
    if ( v48 == -1 )
      goto LABEL_97;
    v49 = (char *)TlsGetValue(v48);
    v50 = (const WCHAR *)(v49 + 8);
    if ( !v49 )
      v50 = 0;
    if ( v50 )
    {
      v51 = -1;
      do
        v15 = v50[++v51] == 0;
      while ( !v15 );
      v52 = 2 * v51 + 2;
    }
    else
    {
LABEL_97:
      v50 = &LocaleName;
      v52 = 2;
    }
    v73 = v52;
    v81 = 5;
    v64 = off_180173280;
    v72 = v50;
    v74 = 0;
    v75 = "IkeParseQMProposalIkeV2";
    v76 = 24;
    v80 = 184549376;
    v82 = 1;
    v65 = *(unsigned __int16 *)off_180173280;
    v67 = byte_180166E6B;
    v66 = 2;
    v68 = 45;
    v69 = 1;
    LODWORD(v61) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_180173298, &v80, 0, 0, 5, &v64);
  }
  return IkeReturnError(v20, "IkeParseQMProposalIkeV2");
}

```

## disassembly

```asm
0x180044c10  mov     [rsp-8+arg_8], rbx
0x180044c15  push    rbp
0x180044c16  push    rsi
0x180044c17  push    rdi
0x180044c18  push    r12
0x180044c1a  push    r13
0x180044c1c  push    r14
0x180044c1e  push    r15
0x180044c20  lea     rbp, [rsp-10h]
0x180044c25  sub     rsp, 110h
0x180044c2c  mov     rax, cs:__security_cookie
0x180044c33  xor     rax, rsp
0x180044c36  mov     [rbp+40h+var_40], rax
0x180044c3a  xor     ebx, ebx
0x180044c3c  mov     [rsp+140h+var_E0], r8
0x180044c41  mov     [r8], rbx
0x180044c44  lea     r14, aIkeparseqmprop; "IkeParseQMProposalIkeV2"
0x180044c4b  mov     eax, cs:dword_180173278
0x180044c51  xor     dil, dil
0x180044c54  mov     [rsp+140h+var_E8], edx
0x180044c58  mov     r15, r8
0x180044c5b  mov     [rsp+140h+var_F8], rbx
0x180044c60  mov     r12, rcx
0x180044c63  mov     [rsp+140h+netlong], ebx
0x180044c67  mov     esi, ebx
0x180044c69  mov     [rsp+140h+var_EC], 1
0x180044c71  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180044c78  mov     [rsp+140h+var_100], ebx
0x180044c7c  cmp     eax, 5
0x180044c7f  jbe     loc_180044DE1
0x180044c85  mov     rcx, cs:qword_180173290
0x180044c8c  mov     rax, cs:qword_180173288
0x180044c93  test    al, 1
0x180044c95  jz      loc_180044DE1
0x180044c9b  mov     rax, rcx
0x180044c9e  and     eax, 1
0x180044ca1  cmp     rax, rcx
0x180044ca4  jnz     loc_180044DE1
0x180044caa  mov     rax, cs:gIkeExtGlobals
0x180044cb1  test    rax, rax
0x180044cb4  jz      short loc_180044CDF
0x180044cb6  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180044cbc  cmp     ecx, 0FFFFFFFFh
0x180044cbf  jz      short loc_180044CDF
0x180044cc1  call    cs:__imp_TlsGetValue
0x180044cc7  test    rax, rax
0x180044cca  jz      short loc_180044CD8
0x180044ccc  mov     rcx, [rax]
0x180044ccf  mov     rax, cs:gIkeExtGlobals
0x180044cd6  jmp     short loc_180044CE2
0x180044cd8  mov     rax, cs:gIkeExtGlobals
0x180044cdf  mov     rcx, rbx
0x180044ce2  mov     [rsp+140h+var_D0], rcx
0x180044ce7  lea     rcx, [rsp+140h+var_D0]
0x180044cec  mov     [rbp+40h+var_A0], rcx
0x180044cf0  mov     [rbp+40h+var_98], 8
0x180044cf8  test    rax, rax
0x180044cfb  jz      short loc_180044D35
0x180044cfd  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180044d03  cmp     ecx, 0FFFFFFFFh
0x180044d06  jz      short loc_180044D35
0x180044d08  call    cs:__imp_TlsGetValue
0x180044d0e  test    rax, rax
0x180044d11  lea     rdx, [rax+8]
0x180044d15  cmovz   rdx, rbx
0x180044d19  test    rdx, rdx
0x180044d1c  jz      short loc_180044D35
0x180044d1e  mov     rax, r13
0x180044d21  cmp     [rdx+rax*2+2], bx
0x180044d26  lea     rax, [rax+1]
0x180044d2a  jnz     short loc_180044D21
0x180044d2c  lea     eax, ds:2[rax*2]
0x180044d33  jmp     short loc_180044D41
0x180044d35  lea     rdx, LocaleName
0x180044d3c  mov     eax, 2
0x180044d41  mov     [rbp+40h+var_88], eax
0x180044d44  lea     rcx, _TraceLoggingMetadata
0x180044d4b  movzx   eax, cs:word_180166E9A
0x180044d52  xor     r9d, r9d
0x180044d55  mov     dword ptr [rbp+40h+var_60+4], eax
0x180044d58  xor     r8d, r8d
0x180044d5b  mov     rax, cs:off_180173280
0x180044d62  mov     [rbp+40h+var_C0], rax
0x180044d66  mov     [rbp+40h+var_90], rdx
0x180044d6a  lea     rdx, [rbp+40h+var_60]
0x180044d6e  mov     [rbp+40h+var_84], ebx
0x180044d71  mov     [rbp+40h+var_80], r14
0x180044d75  mov     [rbp+40h+var_78], 18h
0x180044d7d  mov     dword ptr [rbp+40h+var_60], 0B000000h
0x180044d84  mov     [rbp+40h+var_58], 1
0x180044d8c  movzx   eax, word ptr [rax]
0x180044d8f  mov     [rbp+40h+var_B8], eax
0x180044d92  lea     rax, dword_180166EA4
0x180044d99  mov     [rbp+40h+var_B0], rax
0x180044d9d  lea     rax, _TraceLoggingMetadataEnd
0x180044da4  sub     eax, ecx
0x180044da6  mov     [rbp+40h+var_B4], 2
0x180044dad  mov     [rbp+40h+var_A8], 2Dh ; '-'
0x180044db4  mov     [rbp+40h+var_A4], 1
0x180044dbb  mov     [rsp+140h+var_F0], eax
0x180044dbf  mov     eax, [rsp+140h+var_F0]
0x180044dc3  mov     rcx, cs:qword_180173298
0x180044dca  lea     rax, [rbp+40h+var_C0]
0x180044dce  mov     [rsp+140h+var_118], rax
0x180044dd3  mov     dword ptr [rsp+140h+var_120], 5
0x180044ddb  call    cs:__imp_EtwEventWriteTransfer
0x180044de1  movzx   r14d, byte ptr [rsp+140h+var_F8+4]
0x180044de7  movzx   r13d, word ptr [rsp+140h+var_F8+2]
0x180044ded  nop     dword ptr [rax]
0x180044df0  mov     edx, 8
0x180044df5  mov     rcx, r12
0x180044df8  call    IkeVerifyIncomingDataSize
0x180044dfd  test    rax, rax
0x180044e00  jnz     short loc_180044E21
0x180044e02  movzx   edx, word ptr [r12+0Ch]
0x180044e08  mov     rcx, [r12]
0x180044e0c  mov     rdx, [rdx+rcx]
0x180044e10  mov     [rsp+140h+var_F8], rdx
0x180044e15  movzx   r14d, byte ptr [rsp+140h+var_F8+4]
0x180044e1b  movzx   r13d, word ptr [rsp+140h+var_F8+2]
0x180044e21  lea     rdx, aIkecopyincomin; "IkeCopyIncomingData"
0x180044e28  mov     rcx, rax
0x180044e2b  call    IkeReturnError
0x180044e30  mov     rbx, rax
0x180044e33  test    rax, rax
0x180044e36  jnz     loc_18004524A
0x180044e3c  movzx   ecx, r13w; netshort
0x180044e40  call    cs:__imp_ntohs
0x180044e46  add     word ptr [r12+0Ch], 8
0x180044e4d  movzx   r13d, byte ptr [rsp+140h+var_F8+7]
0x180044e53  mov     word ptr [rsp+140h+var_F0], ax
0x180044e58  test    r13b, r13b
0x180044e5b  jz      short loc_180044E86
0x180044e5d  mov     eax, [rsp+140h+var_100]
0x180044e61  cmp     [rsp+140h+var_E8], ebx
0x180044e65  jz      short loc_180044E6C
0x180044e67  cmp     eax, 2
0x180044e6a  jnb     short loc_180044E86
0x180044e6c  test    eax, eax
0x180044e6e  jz      short loc_180044EB1
0x180044e70  cmp     r14b, dil
0x180044e73  jb      short loc_180044E86
0x180044e75  jnz     short loc_180044EA9
0x180044e77  mov     edi, [rsp+140h+var_EC]
0x180044e7b  inc     edi
0x180044e7d  mov     [rsp+140h+var_EC], edi
0x180044e81  cmp     edi, 2
0x180044e84  jbe     short loc_180044EB1
0x180044e86  lea     rdi, aIkeparseqmprop; "IkeParseQMProposalIkeV2"
0x180044e8d  mov     r9d, 1
0x180044e93  mov     rdx, rdi
0x180044e96  mov     r8d, 3613h
0x180044e9c  call    WfpReportSysErrorAsWinError
0x180044ea1  mov     rbx, rax
0x180044ea4  jmp     loc_180045251
0x180044ea9  mov     [rsp+140h+var_EC], 1
0x180044eb1  mov     dl, 1
0x180044eb3  mov     rcx, r15
0x180044eb6  call    IkeExpandQMPolicy
0x180044ebb  mov     rbx, rax
0x180044ebe  test    rax, rax
0x180044ec1  jnz     loc_18004524A
0x180044ec7  mov     rax, [r15]
0x180044eca  inc     word ptr [rax+6]
0x180044ece  cmp     byte ptr [rsp+140h+var_F8+6], 4
0x180044ed3  jnz     short loc_180044E86
0x180044ed5  mov     r8d, 4
0x180044edb  lea     rcx, [rsp+140h+netlong]; void *
0x180044ee0  mov     rdx, r12
0x180044ee3  call    IkeCopyIncomingData
0x180044ee8  mov     rbx, rax
0x180044eeb  test    rax, rax
0x180044eee  jnz     loc_18004524A
0x180044ef4  add     word ptr [r12+0Ch], 4
0x180044efb  xor     edi, edi
0x180044efd  test    r13d, r13d
0x180044f00  jz      loc_18004519F
0x180044f06  mov     eax, [rsp+140h+var_100]
0x180044f0a  imul    r15, rax, 1E8h
0x180044f11  add     r15, 8
0x180044f15  nop     word ptr [rax+rax+00000000h]
0x180044f20  mov     rax, [rsp+140h+var_E0]
0x180044f25  mov     ecx, [rsp+140h+netlong]; netlong
0x180044f29  mov     rbx, [rax]
0x180044f2c  lea     rsi, [r15+rbx]
0x180044f30  mov     [rbx+r15+1E0h], r14b
0x180044f38  call    cs:__imp_ntohl
0x180044f3e  mov     [rbx+r15+24h], eax
0x180044f43  mov     rcx, cs:WPP_GLOBAL_Control
0x180044f4a  lea     rax, WPP_GLOBAL_Control
0x180044f51  cmp     rcx, rax
0x180044f54  jz      loc_180045006
0x180044f5a  cmp     byte ptr [rcx+19h], 4
0x180044f5e  jb      loc_180045006
0x180044f64  test    byte ptr [rcx+1Ch], 10h
0x180044f68  jz      loc_180045006
0x180044f6e  mov     rdx, cs:gIkeExtGlobals
0x180044f75  test    rdx, rdx
0x180044f78  jz      short loc_180044FA0
0x180044f7a  mov     eax, [rdx+0D88h]
0x180044f80  cmp     eax, 0FFFFFFFFh
0x180044f83  jz      short loc_180044FA0
0x180044f85  mov     ecx, eax; dwTlsIndex
0x180044f87  call    cs:__imp_TlsGetValue
0x180044f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180044f94  mov     r8, rax
0x180044f97  mov     rdx, cs:gIkeExtGlobals
0x180044f9e  jmp     short loc_180044FA3
0x180044fa0  xor     r8d, r8d
0x180044fa3  xor     eax, eax
0x180044fa5  lea     rbx, [r8+8]
0x180044fa9  test    r8, r8
0x180044fac  cmovz   rbx, rax
0x180044fb0  test    rdx, rdx
0x180044fb3  jz      short loc_180044FD9
0x180044fb5  mov     eax, [rdx+0D88h]
0x180044fbb  cmp     eax, 0FFFFFFFFh
0x180044fbe  jz      short loc_180044FD9
0x180044fc0  mov     ecx, eax; dwTlsIndex
0x180044fc2  call    cs:__imp_TlsGetValue
0x180044fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180044fcf  test    rax, rax
0x180044fd2  jz      short loc_180044FD9
0x180044fd4  mov     r9, [rax]
0x180044fd7  jmp     short loc_180044FDC
0x180044fd9  xor     r9d, r9d
0x180044fdc  mov     eax, [rsi+24h]
0x180044fdf  mov     edx, 14h
0x180044fe4  mov     rcx, [rcx+10h]
0x180044fe8  mov     [rsp+140h+var_110], eax
0x180044fec  movzx   r8d, r14b
0x180044ff0  mov     dword ptr [rsp+140h+var_118], r8d
0x180044ff5  lea     r8, WPP_f7416a5e69af345e38b1e64d61a85976_Traceguids
0x180044ffc  mov     [rsp+140h+var_120], rbx
0x180045001  call    WPP_SF_iSDD
0x180045006  mov     eax, cs:dword_180173278
0x18004500c  cmp     eax, 4
0x18004500f  jbe     loc_180045173
0x180045015  mov     rax, cs:gIkeExtGlobals
0x18004501c  test    rax, rax
0x18004501f  jz      short loc_18004504C
0x180045021  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180045027  cmp     ecx, 0FFFFFFFFh
0x18004502a  jz      short loc_18004504C
0x18004502c  call    cs:__imp_TlsGetValue
0x180045032  test    rax, rax
0x180045035  jz      short loc_180045045
0x180045037  mov     rcx, [rax]
0x18004503a  xor     ebx, ebx
0x18004503c  mov     rax, cs:gIkeExtGlobals
0x180045043  jmp     short loc_180045050
0x180045045  mov     rax, cs:gIkeExtGlobals
0x18004504c  xor     ebx, ebx
0x18004504e  mov     ecx, ebx
0x180045050  mov     [rbp+40h+var_60], rcx
0x180045054  lea     rcx, [rbp+40h+var_60]
0x180045058  mov     [rbp+40h+var_A0], rcx
0x18004505c  mov     [rbp+40h+var_98], 8
0x180045064  test    rax, rax
0x180045067  jz      short loc_1800450A6
0x180045069  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18004506f  cmp     ecx, 0FFFFFFFFh
0x180045072  jz      short loc_1800450A6
0x180045074  call    cs:__imp_TlsGetValue
0x18004507a  test    rax, rax
0x18004507d  lea     rdx, [rax+8]
0x180045081  cmovz   rdx, rbx
0x180045085  test    rdx, rdx
0x180045088  jz      short loc_1800450A6
0x18004508a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180045091  cmp     word ptr [rdx+rax*2+2], 0
0x180045097  lea     rax, [rax+1]
0x18004509b  jnz     short loc_180045091
0x18004509d  lea     eax, ds:2[rax*2]
0x1800450a4  jmp     short loc_1800450B2
0x1800450a6  lea     rdx, LocaleName
0x1800450ad  mov     eax, 2
0x1800450b2  mov     [rbp+40h+var_88], eax
0x1800450b5  lea     rcx, _TraceLoggingMetadata
0x1800450bc  mov     [rbp+40h+var_90], rdx
0x1800450c0  xor     r9d, r9d
0x1800450c3  mov     [rbp+40h+var_84], ebx
0x1800450c6  lea     rdx, [rbp+40h+var_50]
0x1800450ca  mov     [rbp+40h+var_78], 4
0x1800450d2  xor     r8d, r8d
0x1800450d5  mov     [rbp+40h+var_68], 4
0x1800450dd  mov     [rbp+40h+var_50], 0B000000h
0x1800450e4  mov     [rbp+40h+var_48], rbx
0x1800450e8  movzx   eax, r14b
0x1800450ec  mov     [rsp+140h+var_C8], eax
0x1800450f0  lea     rax, [rsp+140h+var_C8]
0x1800450f5  mov     [rbp+40h+var_80], rax
0x1800450f9  mov     eax, [rsi+24h]
0x1800450fc  mov     [rsp+140h+var_C4], eax
0x180045100  lea     rax, [rsp+140h+var_C4]
0x180045105  mov     [rbp+40h+var_70], rax
0x180045109  movzx   eax, cs:word_180162A3F
0x180045110  mov     [rbp+40h+var_4C], eax
0x180045113  mov     rax, cs:off_180173280
0x18004511a  mov     [rbp+40h+var_C0], rax
  ... truncated ...
```
