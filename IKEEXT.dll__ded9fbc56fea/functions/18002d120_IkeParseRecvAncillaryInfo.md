# IkeParseRecvAncillaryInfo

- ea: `0x18002d120`
- end: `0x18002d92c`
- name: `IkeParseRecvAncillaryInfo`
- size: `2060`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800717b0`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x180019994`
- `0x18002d120`
- `0x180050850`
- `0x18005bce4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d1b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d1fe`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d376`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d3b1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d414`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d461`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d748`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d7b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d1b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d1fe`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d376`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d3b1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d414`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d461`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d748`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d7b8`
- `ntdll!EtwEventWriteTransfer` at `0x18002d2dd`
- `ntdll!EtwEventWriteTransfer` at `0x18002d545`
- `ntdll!EtwEventWriteTransfer` at `0x18002d894`
- `ntdll!EtwEventWriteTransfer` at `0x18002d2dd`
- `ntdll!EtwEventWriteTransfer` at `0x18002d545`
- `ntdll!EtwEventWriteTransfer` at `0x18002d894`

## pseudocode

```c
__int64 __fastcall IkeParseRecvAncillaryInfo(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  __int64 v4; // rbx
  __int64 v5; // r14
  LPCRITICAL_SECTION v6; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v9; // rcx
  DWORD v10; // ecx
  char *v11; // rax
  const WCHAR *v12; // rdx
  __int64 v13; // rax
  bool v14; // zf
  int v15; // eax
  __int64 v16; // rdi
  int v17; // r12d
  unsigned int v18; // esi
  _QWORD *v19; // rcx
  LPCRITICAL_SECTION v20; // rdx
  DWORD v21; // eax
  LPVOID v22; // rax
  LPVOID v23; // r8
  __int64 v24; // rbx
  DWORD v25; // eax
  __int64 *v26; // rax
  __int64 v27; // r9
  LPCRITICAL_SECTION v28; // rax
  DWORD v29; // ecx
  __int64 *v30; // rax
  __int64 v31; // rcx
  DWORD v32; // ecx
  char *v33; // rax
  const WCHAR *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // r9
  int v38; // eax
  __int64 v39; // r9
  LPCRITICAL_SECTION v40; // rax
  DWORD v41; // ecx
  __int64 *v42; // rax
  __int64 v43; // rcx
  DWORD v44; // ecx
  char *v45; // rax
  const WCHAR *v46; // rdx
  int v47; // eax
  __int64 v49; // [rsp+28h] [rbp-D8h]
  __int64 v50; // [rsp+30h] [rbp-D0h]
  unsigned int v51; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v52; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v53[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v54; // [rsp+58h] [rbp-A8h] BYREF
  int v55; // [rsp+5Ch] [rbp-A4h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int128 v57; // [rsp+70h] [rbp-90h] BYREF
  __int128 v58; // [rsp+80h] [rbp-80h]
  unsigned __int64 v59; // [rsp+90h] [rbp-70h]
  __int64 v60; // [rsp+98h] [rbp-68h]
  const WCHAR *v61; // [rsp+A0h] [rbp-60h]
  int v62; // [rsp+A8h] [rbp-58h]
  int v63; // [rsp+ACh] [rbp-54h]
  const char *v64; // [rsp+B0h] [rbp-50h]
  __int64 v65; // [rsp+B8h] [rbp-48h]
  char *v66; // [rsp+C0h] [rbp-40h] BYREF
  int v67; // [rsp+C8h] [rbp-38h]
  int v68; // [rsp+CCh] [rbp-34h]
  __int16 *v69; // [rsp+D0h] [rbp-30h]
  int v70; // [rsp+D8h] [rbp-28h]
  int v71; // [rsp+DCh] [rbp-24h]
  _QWORD *v72; // [rsp+E0h] [rbp-20h]
  __int64 v73; // [rsp+E8h] [rbp-18h]
  const WCHAR *v74; // [rsp+F0h] [rbp-10h]
  int v75; // [rsp+F8h] [rbp-8h]
  int v76; // [rsp+FCh] [rbp-4h]
  unsigned int *v77; // [rsp+100h] [rbp+0h]
  __int64 v78; // [rsp+108h] [rbp+8h]

  v2 = 0;
  v50 = a1;
  v4 = a1;
  v5 = -1;
  if ( (unsigned int)dword_180173278 > 5 )
  {
    a1 = qword_180173290;
    if ( (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
    {
      v6 = gIkeExtGlobals;
      if ( gIkeExtGlobals )
      {
        LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
        if ( LockSemaphore != -1 )
        {
          Value = (__int64 *)TlsGetValue(LockSemaphore);
          if ( Value )
          {
            v9 = *Value;
            v6 = gIkeExtGlobals;
LABEL_10:
            v52 = v9;
            v59 = (unsigned __int64)&v52;
            v60 = 8;
            if ( !v6 )
              goto LABEL_18;
            v10 = (DWORD)v6[86].LockSemaphore;
            if ( v10 == -1 )
              goto LABEL_18;
            v11 = (char *)TlsGetValue(v10);
            v12 = (const WCHAR *)(v11 + 8);
            if ( !v11 )
              v12 = 0;
            if ( v12 )
            {
              v13 = -1;
              do
                v14 = v12[++v13] == 0;
              while ( !v14 );
              v15 = 2 * v13 + 2;
            }
            else
            {
LABEL_18:
              v12 = &LocaleName;
              v15 = 2;
            }
            v62 = v15;
            *(_QWORD *)&v57 = off_180173280;
            v61 = v12;
            v63 = 0;
            v64 = "IkeParseRecvAncillaryInfo";
            v65 = 26;
            v53[0] = 0x50B000000LL;
            v53[1] = 1;
            *((_QWORD *)&v57 + 1) = *(unsigned __int16 *)off_180173280 | 0x200000000LL;
            *(_QWORD *)&v58 = &dword_180166EA4;
            *((_QWORD *)&v58 + 1) = 0x10000002DLL;
            v51 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwEventWriteTransfer(qword_180173298, v53, 0, 0, 5, &v57);
            goto LABEL_20;
          }
          v6 = gIkeExtGlobals;
        }
      }
      v9 = 0;
      goto LABEL_10;
    }
  }
LABEL_20:
  if ( *(_DWORD *)(v4 + 32) < 0x10u )
    v16 = 0;
  else
    v16 = *(_QWORD *)(v4 + 40);
  v17 = 0;
  while ( v16 )
  {
    if ( *(_DWORD *)(v16 + 12) != 19 )
    {
      if ( v16 == -16 )
        break;
      v18 = *(_DWORD *)(v16 + 16);
      v59 = v18;
      v57 = 0;
      v58 = 0;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v20 = gIkeExtGlobals;
        if ( !gIkeExtGlobals || (v21 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v21 == -1) )
        {
          v23 = 0;
        }
        else
        {
          v22 = TlsGetValue(v21);
          v20 = gIkeExtGlobals;
          v23 = v22;
          v19 = WPP_GLOBAL_Control;
        }
        v24 = (__int64)v23 + 8;
        if ( !v23 )
          v24 = 0;
        if ( v20
          && (v25 = (DWORD)v20[86].LockSemaphore, v25 != -1)
          && (v26 = (__int64 *)TlsGetValue(v25), v19 = WPP_GLOBAL_Control, v26) )
        {
          v27 = *v26;
        }
        else
        {
          LODWORD(v27) = 0;
        }
        LODWORD(v49) = v18;
        WPP_SF_iSL(v19[2], 23, (unsigned int)WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids, v27, v24, v49);
        v4 = v50;
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v28 = gIkeExtGlobals;
        if ( gIkeExtGlobals )
        {
          v29 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
          if ( v29 != -1 )
          {
            v30 = (__int64 *)TlsGetValue(v29);
            if ( v30 )
            {
              v31 = *v30;
              v28 = gIkeExtGlobals;
              goto LABEL_49;
            }
            v28 = gIkeExtGlobals;
          }
        }
        v31 = 0;
LABEL_49:
        v53[0] = v31;
        v72 = v53;
        v73 = 8;
        if ( !v28 )
          goto LABEL_57;
        v32 = (DWORD)v28[86].LockSemaphore;
        if ( v32 == -1 )
          goto LABEL_57;
        v33 = (char *)TlsGetValue(v32);
        v34 = (const WCHAR *)(v33 + 8);
        if ( !v33 )
          v34 = 0;
        if ( v34 )
        {
          v35 = -1;
          do
            v14 = v34[++v35] == 0;
          while ( !v14 );
          v36 = 2 * v35 + 2;
        }
        else
        {
LABEL_57:
          v34 = &LocaleName;
          v36 = 2;
        }
        v75 = v36;
        v74 = v34;
        v77 = &v51;
        v55 = 4;
        v66 = off_180173280;
        v76 = 0;
        v56 = 0;
        v51 = v18;
        v78 = 4;
        v54 = 184549376;
        v67 = *(unsigned __int16 *)off_180173280;
        v69 = &word_18015374E;
        v68 = 2;
        v70 = 75;
        v71 = 1;
        LODWORD(v52) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(qword_180173298, &v54, 0, 0, 5, &v66);
      }
      if ( v18 )
      {
        DWORD1(v57) = 3;
        v2 = WfpPnPLookupLocalIFProperties(&v57);
        if ( v2 )
          goto LABEL_78;
      }
      *(_DWORD *)(a2 + 184) = HIDWORD(v59);
      goto LABEL_75;
    }
    switch ( *(_BYTE *)(a2 + 56) )
    {
      case 1:
      case 4:
      case 7:
        if ( v16 != -16 )
        {
          v37 = 0;
          switch ( *(_BYTE *)(a2 + 56) )
          {
            case 1:
            case 4:
            case 7:
              *(_DWORD *)(a2 + 64) = *(_DWORD *)(v16 + 16);
              goto LABEL_67;
            case 5:
            case 6:
            case 8:
              v37 = WfpReportSysErrorAsWinError(a1, "IkeAddrSetAddrBytes", 87, 1);
LABEL_67:
              IkeReturnError(v37, "IkeAddrSetAddrBytes");
              *(_DWORD *)(a2 + 232) = *(_DWORD *)(v16 + 20);
              v59 = 0;
              v38 = *(_DWORD *)(v16 + 20);
              goto LABEL_73;
            default:
              goto LABEL_86;
          }
        }
        goto LABEL_85;
      case 5:
      case 6:
      case 8:
        if ( v16 == -16 )
          goto LABEL_85;
        v39 = 0;
        switch ( *(_BYTE *)(a2 + 56) )
        {
          case 1:
          case 4:
          case 7:
            v39 = WfpReportSysErrorAsWinError(a1, "IkeAddrSetAddrBytes", 87, 1);
            goto LABEL_72;
          case 5:
          case 6:
          case 8:
            *(_OWORD *)(a2 + 68) = *(_OWORD *)(v16 + 16);
LABEL_72:
            IkeReturnError(v39, "IkeAddrSetAddrBytes");
            *(_DWORD *)(a2 + 232) = *(_DWORD *)(v16 + 32);
            v59 = 0;
            v38 = *(_DWORD *)(v16 + 32);
LABEL_73:
            LODWORD(v59) = v38;
            v57 = 0;
            DWORD1(v57) = 3;
            v58 = 0;
            *(_QWORD *)(a2 + 224) = gIkeExtGlobals[84].SpinCount;
            v2 = WfpPnPLookupLocalIFProperties(&v57);
            if ( v2 )
              goto LABEL_78;
            *(_QWORD *)(a2 + 176) = *((_QWORD *)&v58 + 1);
            break;
          default:
            goto LABEL_86;
        }
        break;
      default:
LABEL_86:
        __fastfail(5u);
    }
LABEL_75:
    v16 += (*(_QWORD *)v16 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
    a1 = v16 + 16;
    if ( v16 + 16 > *(_QWORD *)(v4 + 40) + (unsigned __int64)*(unsigned int *)(v4 + 32) )
      v16 = 0;
    if ( (unsigned int)++v17 >= 2 )
      goto LABEL_78;
  }
LABEL_85:
  v2 = WfpReportSysErrorAsWinError(a1, "IkeParseRecvAncillaryInfo", 13804, 1);
LABEL_78:
  if ( (unsigned int)dword_180173278 > 5 && (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
  {
    v40 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v41 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v41 != -1 )
      {
        v42 = (__int64 *)TlsGetValue(v41);
        if ( v42 )
        {
          v43 = *v42;
          v40 = gIkeExtGlobals;
          goto LABEL_89;
        }
        v40 = gIkeExtGlobals;
      }
    }
    v43 = 0;
LABEL_89:
    v53[0] = v43;
    v72 = v53;
    v73 = 8;
    if ( !v40 )
      goto LABEL_96;
    v44 = (DWORD)v40[86].LockSemaphore;
    if ( v44 == -1 )
      goto LABEL_96;
    v45 = (char *)TlsGetValue(v44);
    v46 = (const WCHAR *)(v45 + 8);
    if ( !v45 )
      v46 = 0;
    if ( v46 )
    {
      do
        v14 = v46[++v5] == 0;
      while ( !v14 );
      v47 = 2 * v5 + 2;
    }
    else
    {
LABEL_96:
      v46 = &LocaleName;
      v47 = 2;
    }
    v75 = v47;
    v55 = 5;
    v66 = off_180173280;
    v74 = v46;
    v76 = 0;
    v77 = (unsigned int *)"IkeParseRecvAncillaryInfo";
    v78 = 26;
    v54 = 184549376;
    v56 = 1;
    v67 = *(unsigned __int16 *)off_180173280;
    v69 = (__int16 *)byte_180166E6B;
    v68 = 2;
    v70 = 45;
    v71 = 1;
    LODWORD(v52) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_180173298, &v54, 0, 0, 5, &v66);
  }
  return IkeReturnError(v2, "IkeParseRecvAncillaryInfo");
}

```

## disassembly

```asm
0x18002d120  mov     [rsp-8+arg_10], rbx
0x18002d125  push    rbp
0x18002d126  push    rsi
0x18002d127  push    rdi
0x18002d128  push    r12
0x18002d12a  push    r13
0x18002d12c  push    r14
0x18002d12e  push    r15
0x18002d130  lea     rbp, [rsp-20h]
0x18002d135  sub     rsp, 120h
0x18002d13c  mov     rax, cs:__security_cookie
0x18002d143  xor     rax, rsp
0x18002d146  mov     [rbp+50h+var_40], rax
0x18002d14a  mov     eax, cs:dword_180173278
0x18002d150  lea     rsi, aIkeparserecvan; "IkeParseRecvAncillaryInfo"
0x18002d157  xor     r15d, r15d
0x18002d15a  mov     [rsp+150h+var_120], rcx
0x18002d15f  lea     rdi, _TraceLoggingMetadata
0x18002d166  mov     r13, rdx
0x18002d169  mov     rbx, rcx
0x18002d16c  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18002d173  cmp     eax, 5
0x18002d176  jbe     loc_18002D2E3
0x18002d17c  mov     rcx, cs:qword_180173290
0x18002d183  mov     rax, cs:qword_180173288
0x18002d18a  test    al, 1
0x18002d18c  jz      loc_18002D2E3
0x18002d192  mov     rax, rcx
0x18002d195  and     eax, 1
0x18002d198  cmp     rax, rcx
0x18002d19b  jnz     loc_18002D2E3
0x18002d1a1  mov     rax, cs:gIkeExtGlobals
0x18002d1a8  test    rax, rax
0x18002d1ab  jz      short loc_18002D1D6
0x18002d1ad  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002d1b3  cmp     ecx, 0FFFFFFFFh
0x18002d1b6  jz      short loc_18002D1D6
0x18002d1b8  call    cs:__imp_TlsGetValue
0x18002d1be  test    rax, rax
0x18002d1c1  jz      short loc_18002D1CF
0x18002d1c3  mov     rcx, [rax]
0x18002d1c6  mov     rax, cs:gIkeExtGlobals
0x18002d1cd  jmp     short loc_18002D1D8
0x18002d1cf  mov     rax, cs:gIkeExtGlobals
0x18002d1d6  xor     ecx, ecx
0x18002d1d8  mov     [rsp+150h+var_110], rcx
0x18002d1dd  lea     rcx, [rsp+150h+var_110]
0x18002d1e2  mov     [rbp+50h+var_C0], rcx
0x18002d1e6  mov     [rbp+50h+var_B8], 8
0x18002d1ee  test    rax, rax
0x18002d1f1  jz      short loc_18002D235
0x18002d1f3  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002d1f9  cmp     ecx, 0FFFFFFFFh
0x18002d1fc  jz      short loc_18002D235
0x18002d1fe  call    cs:__imp_TlsGetValue
0x18002d204  mov     rcx, rax
0x18002d207  lea     rdx, [rax+8]
0x18002d20b  xor     eax, eax
0x18002d20d  test    rcx, rcx
0x18002d210  cmovz   rdx, rax
0x18002d214  test    rdx, rdx
0x18002d217  jz      short loc_18002D235
0x18002d219  mov     rax, r14
0x18002d21c  nop     dword ptr [rax+00h]
0x18002d220  cmp     [rdx+rax*2+2], r15w
0x18002d226  lea     rax, [rax+1]
0x18002d22a  jnz     short loc_18002D220
0x18002d22c  lea     eax, ds:2[rax*2]
0x18002d233  jmp     short loc_18002D241
0x18002d235  lea     rdx, LocaleName
0x18002d23c  mov     eax, 2
0x18002d241  mov     [rbp+50h+var_A8], eax
0x18002d244  xor     r9d, r9d
0x18002d247  movzx   eax, cs:word_180166E9A
0x18002d24e  xor     r8d, r8d
0x18002d251  mov     dword ptr [rsp+150h+var_108+4], eax
0x18002d255  mov     rax, cs:off_180173280
0x18002d25c  mov     qword ptr [rsp+150h+var_E0], rax
0x18002d261  mov     [rbp+50h+var_B0], rdx
0x18002d265  lea     rdx, [rsp+150h+var_108]
0x18002d26a  mov     [rbp+50h+var_A4], r15d
0x18002d26e  mov     [rbp+50h+var_A0], rsi
0x18002d272  mov     [rbp+50h+var_98], 1Ah
0x18002d27a  mov     dword ptr [rsp+150h+var_108], 0B000000h
0x18002d282  mov     [rsp+150h+var_100], 1
0x18002d28b  movzx   eax, word ptr [rax]
0x18002d28e  mov     dword ptr [rsp+150h+var_E0+8], eax
0x18002d292  lea     rax, dword_180166EA4
0x18002d299  mov     qword ptr [rbp+50h+var_D0], rax
0x18002d29d  lea     rax, _TraceLoggingMetadataEnd
0x18002d2a4  sub     eax, edi
0x18002d2a6  mov     dword ptr [rsp+150h+var_E0+0Ch], 2
0x18002d2ae  mov     dword ptr [rbp+50h+var_D0+8], 2Dh ; '-'
0x18002d2b5  mov     dword ptr [rbp+50h+var_D0+0Ch], 1
0x18002d2bc  mov     [rsp+150h+var_118], eax
0x18002d2c0  mov     eax, [rsp+150h+var_118]
0x18002d2c4  mov     rcx, cs:qword_180173298
0x18002d2cb  lea     rax, [rsp+150h+var_E0]
0x18002d2d0  mov     [rsp+150h+var_128], rax
0x18002d2d5  mov     dword ptr [rsp+150h+var_130], 5
0x18002d2dd  call    cs:__imp_EtwEventWriteTransfer
0x18002d2e3  cmp     dword ptr [rbx+20h], 10h
0x18002d2e7  jb      short loc_18002D2EF
0x18002d2e9  mov     rdi, [rbx+28h]
0x18002d2ed  jmp     short loc_18002D2F1
0x18002d2ef  xor     edi, edi
0x18002d2f1  xor     r12d, r12d
0x18002d2f4  lea     r10, __ImageBase
0x18002d2fb  lea     rdx, WPP_GLOBAL_Control
0x18002d302  test    rdi, rdi
0x18002d305  jz      loc_18002D75F
0x18002d30b  cmp     dword ptr [rdi+0Ch], 13h
0x18002d30f  jz      loc_18002D57C
0x18002d315  lea     rax, [rdi+10h]
0x18002d319  test    rax, rax
0x18002d31c  jz      loc_18002D75F
0x18002d322  mov     esi, [rax]
0x18002d324  xorps   xmm0, xmm0
0x18002d327  xor     ecx, ecx
0x18002d329  mov     [rbp+50h+var_C0], rcx
0x18002d32d  mov     dword ptr [rbp+50h+var_C0], esi
0x18002d330  movups  [rsp+150h+var_E0], xmm0
0x18002d335  movups  [rbp+50h+var_D0], xmm0
0x18002d339  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d340  cmp     rcx, rdx
0x18002d343  jz      loc_18002D3EE
0x18002d349  cmp     byte ptr [rcx+19h], 4
0x18002d34d  jb      loc_18002D3EE
0x18002d353  test    byte ptr [rcx+1Ch], 10h
0x18002d357  jz      loc_18002D3EE
0x18002d35d  mov     rdx, cs:gIkeExtGlobals
0x18002d364  test    rdx, rdx
0x18002d367  jz      short loc_18002D38F
0x18002d369  mov     eax, [rdx+0D88h]
0x18002d36f  cmp     eax, 0FFFFFFFFh
0x18002d372  jz      short loc_18002D38F
0x18002d374  mov     ecx, eax; dwTlsIndex
0x18002d376  call    cs:__imp_TlsGetValue
0x18002d37c  mov     rdx, cs:gIkeExtGlobals
0x18002d383  mov     r8, rax
0x18002d386  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d38d  jmp     short loc_18002D392
0x18002d38f  xor     r8d, r8d
0x18002d392  xor     eax, eax
0x18002d394  lea     rbx, [r8+8]
0x18002d398  test    r8, r8
0x18002d39b  cmovz   rbx, rax
0x18002d39f  test    rdx, rdx
0x18002d3a2  jz      short loc_18002D3C8
0x18002d3a4  mov     eax, [rdx+0D88h]
0x18002d3aa  cmp     eax, 0FFFFFFFFh
0x18002d3ad  jz      short loc_18002D3C8
0x18002d3af  mov     ecx, eax; dwTlsIndex
0x18002d3b1  call    cs:__imp_TlsGetValue
0x18002d3b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3be  test    rax, rax
0x18002d3c1  jz      short loc_18002D3C8
0x18002d3c3  mov     r9, [rax]
0x18002d3c6  jmp     short loc_18002D3CB
0x18002d3c8  xor     r9d, r9d
0x18002d3cb  mov     rcx, [rcx+10h]
0x18002d3cf  lea     r8, WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids
0x18002d3d6  mov     edx, 17h
0x18002d3db  mov     dword ptr [rsp+150h+var_128], esi
0x18002d3df  mov     [rsp+150h+var_130], rbx
0x18002d3e4  call    WPP_SF_iSL
0x18002d3e9  mov     rbx, [rsp+150h+var_120]
0x18002d3ee  mov     eax, cs:dword_180173278
0x18002d3f4  cmp     eax, 4
0x18002d3f7  jbe     loc_18002D54B
0x18002d3fd  mov     rax, cs:gIkeExtGlobals
0x18002d404  test    rax, rax
0x18002d407  jz      short loc_18002D435
0x18002d409  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002d40f  cmp     ecx, 0FFFFFFFFh
0x18002d412  jz      short loc_18002D435
0x18002d414  call    cs:__imp_TlsGetValue
0x18002d41a  test    rax, rax
0x18002d41d  jz      short loc_18002D42E
0x18002d41f  mov     rcx, [rax]
0x18002d422  xor     r8d, r8d
0x18002d425  mov     rax, cs:gIkeExtGlobals
0x18002d42c  jmp     short loc_18002D43B
0x18002d42e  mov     rax, cs:gIkeExtGlobals
0x18002d435  xor     r8d, r8d
0x18002d438  mov     ecx, r8d
0x18002d43b  mov     [rsp+150h+var_108], rcx
0x18002d440  lea     rcx, [rsp+150h+var_108]
0x18002d445  mov     [rbp+50h+var_70], rcx
0x18002d449  mov     [rbp+50h+var_68], 8
0x18002d451  test    rax, rax
0x18002d454  jz      short loc_18002D495
0x18002d456  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002d45c  cmp     ecx, 0FFFFFFFFh
0x18002d45f  jz      short loc_18002D495
0x18002d461  call    cs:__imp_TlsGetValue
0x18002d467  xor     r8d, r8d
0x18002d46a  test    rax, rax
0x18002d46d  lea     rdx, [rax+8]
0x18002d471  cmovz   rdx, r8
0x18002d475  test    rdx, rdx
0x18002d478  jz      short loc_18002D495
0x18002d47a  mov     rax, r14
0x18002d47d  nop     dword ptr [rax]
0x18002d480  cmp     [rdx+rax*2+2], r8w
0x18002d486  lea     rax, [rax+1]
0x18002d48a  jnz     short loc_18002D480
0x18002d48c  lea     eax, ds:2[rax*2]
0x18002d493  jmp     short loc_18002D4A1
0x18002d495  lea     rdx, LocaleName
0x18002d49c  mov     eax, 2
0x18002d4a1  mov     [rbp+50h+var_58], eax
0x18002d4a4  lea     rcx, _TraceLoggingMetadata
0x18002d4ab  mov     [rbp+50h+var_60], rdx
0x18002d4af  lea     rax, [rsp+150h+var_118]
0x18002d4b4  mov     [rbp+50h+var_50], rax
0x18002d4b8  lea     rdx, [rsp+150h+var_F8]
0x18002d4bd  movzx   eax, cs:word_180153744
0x18002d4c4  xor     r9d, r9d
0x18002d4c7  mov     [rsp+150h+var_F4], eax
0x18002d4cb  mov     rax, cs:off_180173280
0x18002d4d2  mov     [rbp+50h+var_90], rax
0x18002d4d6  mov     [rbp+50h+var_54], r8d
0x18002d4da  mov     [rsp+150h+var_F0], r8
0x18002d4df  xor     r8d, r8d
0x18002d4e2  mov     [rsp+150h+var_118], esi
0x18002d4e6  mov     [rbp+50h+var_48], 4
0x18002d4ee  mov     [rsp+150h+var_F8], 0B000000h
0x18002d4f6  movzx   eax, word ptr [rax]
0x18002d4f9  mov     [rbp+50h+var_88], eax
0x18002d4fc  lea     rax, word_18015374E
0x18002d503  mov     [rbp+50h+var_80], rax
0x18002d507  lea     rax, _TraceLoggingMetadataEnd
0x18002d50e  sub     eax, ecx
0x18002d510  mov     [rbp+50h+var_84], 2
0x18002d517  mov     [rbp+50h+var_78], 4Bh ; 'K'
0x18002d51e  mov     [rbp+50h+var_74], 1
0x18002d525  mov     dword ptr [rsp+150h+var_110], eax
0x18002d529  mov     eax, dword ptr [rsp+150h+var_110]
0x18002d52d  mov     rcx, cs:qword_180173298
0x18002d534  lea     rax, [rbp+50h+var_90]
0x18002d538  mov     [rsp+150h+var_128], rax
0x18002d53d  mov     dword ptr [rsp+150h+var_130], 5
0x18002d545  call    cs:__imp_EtwEventWriteTransfer
0x18002d54b  test    esi, esi
0x18002d54d  jz      short loc_18002D56D
0x18002d54f  lea     rcx, [rsp+150h+var_E0]
0x18002d554  mov     dword ptr [rsp+150h+var_E0+4], 3
0x18002d55c  call    WfpPnPLookupLocalIFProperties
0x18002d561  mov     r15, rax
0x18002d564  test    rax, rax
0x18002d567  jnz     loc_18002D6F6
0x18002d56d  mov     ecx, dword ptr [rbp+50h+var_C0+4]
0x18002d570  mov     [r13+0B8h], ecx
0x18002d577  jmp     loc_18002D6C7
0x18002d57c  movzx   edx, byte ptr [r13+38h]
0x18002d581  dec     edx; switch 8 cases
0x18002d583  cmp     edx, 7
0x18002d586  ja      def_18002D59A; jumptable 000000018002D59A default case, cases 2,3
0x18002d58c  movsxd  rax, edx
0x18002d58f  mov     ecx, ds:(jpt_18002D59A - 180000000h)[r10+rax*4]
0x18002d597  add     rcx, r10
0x18002d59a  jmp     rcx; switch jump
0x18002d59c  lea     r8, [rdi+10h]; jumptable 000000018002D59A cases 1,4,7
0x18002d5a0  test    r8, r8
0x18002d5a3  jz      loc_18002D75F
0x18002d5a9  xor     r9d, r9d
0x18002d5ac  cmp     edx, 7; switch 8 cases
0x18002d5af  ja      def_18002D59A; jumptable 000000018002D59A default case, cases 2,3
0x18002d5b5  movsxd  rax, edx
0x18002d5b8  mov     ecx, ds:(jpt_18002D5C3 - 180000000h)[r10+rax*4]
0x18002d5c0  add     rcx, r10
0x18002d5c3  jmp     rcx; switch jump
0x18002d5c5  mov     eax, [r8]; jumptable 000000018002D5C3 cases 0,3,6
0x18002d5c8  mov     [r13+40h], eax
0x18002d5cc  jmp     short loc_18002D5E9
0x18002d5ce  mov     r9d, 1; jumptable 000000018002D5C3 cases 4,5,7
0x18002d5d4  lea     rdx, aIkeaddrsetaddr_0; "IkeAddrSetAddrBytes"
0x18002d5db  mov     r8d, 57h ; 'W'
0x18002d5e1  call    WfpReportSysErrorAsWinError
0x18002d5e6  mov     r9, rax
0x18002d5e9  lea     rdx, aIkeaddrsetaddr_0; "IkeAddrSetAddrBytes"
0x18002d5f0  mov     rcx, r9
0x18002d5f3  call    IkeReturnError
0x18002d5f8  mov     eax, [rdi+14h]
0x18002d5fb  mov     [r13+0E8h], eax
0x18002d602  xor     eax, eax
0x18002d604  mov     [rbp+50h+var_C0], rax
0x18002d608  mov     eax, [rdi+14h]
0x18002d60b  jmp     short loc_18002D67E
0x18002d60d  lea     r8, [rdi+10h]; jumptable 000000018002D59A cases 5,6,8
0x18002d611  test    r8, r8
0x18002d614  jz      loc_18002D75F
0x18002d61a  xor     r9d, r9d
0x18002d61d  cmp     edx, 7; switch 8 cases
0x18002d620  ja      def_18002D59A; jumptable 000000018002D59A default case, cases 2,3
0x18002d626  movsxd  rax, edx
0x18002d629  mov     ecx, ds:(jpt_18002D634 - 180000000h)[r10+rax*4]
0x18002d631  add     rcx, r10
0x18002d634  jmp     rcx; switch jump
  ... truncated ...
```
