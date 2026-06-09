# WsValidateCertificateAndUpdateInfo

- ea: `0x180025220`
- end: `0x180025820`
- name: `WsValidateCertificateAndUpdateInfo`
- size: `1536`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180020d14`
- `0x180021ff0`

## callees

- `0x1800211fc`
- `0x180022ac8`
- `0x180022b54`
- `0x180022b7c`
- `0x1800242ec`
- `0x180024ce8`
- `0x180024e70`
- `0x180025220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800253fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002544e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800256c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800253fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002544e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800256c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800254b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025508`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025577`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800254b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025508`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025577`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002563f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800257aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002563f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800257aa`
- `CRYPT32!CertOpenStore` at `0x1800252a8`
- `CRYPT32!CertOpenStore` at `0x1800252a8`
- `CRYPT32!CertFindCertificateInStore` at `0x180025362`
- `CRYPT32!CertFindCertificateInStore` at `0x180025362`
- `CRYPT32!CertCloseStore` at `0x180025656`
- `CRYPT32!CertCloseStore` at `0x1800257cb`
- `CRYPT32!CertCloseStore` at `0x180025656`
- `CRYPT32!CertCloseStore` at `0x1800257cb`
- `CRYPT32!CertFreeCertificateContext` at `0x180025648`
- `CRYPT32!CertFreeCertificateContext` at `0x1800257b8`
- `CRYPT32!CertFreeCertificateContext` at `0x180025648`
- `CRYPT32!CertFreeCertificateContext` at `0x1800257b8`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800255e3`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800255e3`

## pseudocode

```c
__int64 __fastcall WsValidateCertificateAndUpdateInfo(__int64 **a1, __int64 a2)
{
  __int64 *v2; // rax
  const CERT_CONTEXT *v4; // rbp
  char v5; // r12
  char v6; // r13
  __int64 v7; // rcx
  char v8; // r15
  HCERTSTORE v9; // r14
  DWORD LastError; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  PCCERT_CONTEXT CertificateInStore; // rax
  __int64 v19; // r8
  _QWORD *v20; // rcx
  _QWORD *v21; // rcx
  _QWORD *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rax
  SIZE_T v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rcx
  DWORD v30; // eax
  __int64 v32; // rbx
  DWORD v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  DWORD v39; // eax
  int pvData; // [rsp+30h] [rbp-68h] BYREF
  _OWORD pvFindPara[6]; // [rsp+38h] [rbp-60h] BYREF
  char v42; // [rsp+A0h] [rbp+8h]
  char v43; // [rsp+A8h] [rbp+10h]
  char v44; // [rsp+B0h] [rbp+18h]
  DWORD pcbData; // [rsp+B8h] [rbp+20h] BYREF

  pcbData = 4;
  pvData = 0;
  pvFindPara[0] = 0;
  v2 = *a1;
  v4 = 0;
  v42 = 0;
  v5 = 0;
  v43 = 0;
  v44 = 0;
  v6 = 0;
  v7 = **a1;
  v8 = 0;
  if ( !*(_QWORD *)*v2 || !*(_QWORD *)(v7 + 24) || !*(_QWORD *)(v7 + 64) )
  {
    v9 = 0;
    v11 = 87;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_73;
    }
    v16 = 77;
    v17 = 87;
LABEL_72:
    WPP_SF_d(v15[2], v16, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, v17);
    goto LABEL_73;
  }
  v9 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x28000u, *(const void **)(v7 + 64));
  if ( !v9 )
  {
    LastError = GetLastError();
    v11 = LastError;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v13 = 78;
LABEL_35:
      WPP_SF_d(v12[2], v13, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, LastError);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  v14 = LmConvertCryptStringToBinary(*(LPCWSTR *)(**a1 + 24), (DWORD *)pvFindPara);
  v11 = v14;
  if ( v14 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_73;
    }
    v16 = 79;
    v17 = v14;
    goto LABEL_72;
  }
  CertificateInStore = CertFindCertificateInStore(v9, 0x10001u, 0, 0x10000u, pvFindPara, 0);
  v4 = CertificateInStore;
  if ( !CertificateInStore )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v32 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v33 = GetLastError();
      WPP_SF_d(v32, 84, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, v33);
    }
    v11 = 1168;
    goto LABEL_73;
  }
  v20 = (_QWORD *)(**a1 + 8);
  if ( *v20 )
  {
LABEL_22:
    v21 = (_QWORD *)(**a1 + 16);
    if ( !*v21 )
    {
      if ( !(unsigned int)WsGetCertificateName(v21, 4, 1, v4) )
      {
        LastError = GetLastError();
        v11 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          v13 = 81;
          goto LABEL_35;
        }
        goto LABEL_36;
      }
      v5 = 1;
    }
    v22 = (_QWORD *)(**a1 + 32);
    if ( !*v22 )
    {
      if ( !(unsigned int)WsGetOptionalCertificateName(v22, 5, v19, v4) )
      {
        LastError = GetLastError();
        v11 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          v13 = 82;
          goto LABEL_35;
        }
        goto LABEL_36;
      }
      v6 = 1;
    }
    if ( !*(_QWORD *)(**a1 + 40) )
    {
      *(_QWORD *)(**a1 + 40) = LocalAlloc(0x40u, 0x2Au);
      v23 = *(_QWORD *)(**a1 + 40);
      if ( !v23 )
        return 0;
      RtlStringCbPrintfW(v23, 42, L"%llu", *(_QWORD *)&v4->pCertInfo->NotBefore);
      v43 = 1;
    }
    if ( *(_QWORD *)(**a1 + 48) )
    {
LABEL_45:
      v25 = **a1;
      if ( !*(_QWORD *)(v25 + 56) )
      {
        v26 = -1;
        do
          ++v26;
        while ( *(_WORD *)(*(_QWORD *)(v25 + 64) + 2 * v26) );
        v27 = 2 * v26 + 40;
        *(_QWORD *)(**a1 + 56) = LocalAlloc(0x40u, v27);
        v28 = **a1;
        v29 = *(_QWORD *)(v28 + 56);
        if ( !v29 )
          return 0;
        RtlStringCbPrintfW(v29, v27, L"%ws%ws", L"cert:\\LocalMachine\\", *(_QWORD *)(v28 + 64));
        v8 = 1;
      }
      *(_DWORD *)(**a1 + 80) = 0;
      *(_DWORD *)(**a1 + 88) = 0;
      if ( CertGetCertificateContextProperty(v4, 6u, &pvData, &pcbData) )
      {
        if ( *((_QWORD *)&pvFindPara[0] + 1) )
          LocalFree(*((HLOCAL *)&pvFindPara[0] + 1));
        CertFreeCertificateContext(v4);
        if ( !CertCloseStore(v9, 2u) )
        {
          v30 = GetLastError();
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, v30);
          }
        }
        return 0;
      }
      v11 = -1067646970;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids);
      }
      goto LABEL_73;
    }
    *(_QWORD *)(**a1 + 48) = LocalAlloc(0x40u, 0x2Au);
    v24 = *(_QWORD *)(**a1 + 48);
    if ( v24 )
    {
      RtlStringCbPrintfW(v24, 42, L"%llu", *(_QWORD *)&v4->pCertInfo->NotAfter);
      v44 = 1;
      goto LABEL_45;
    }
    return 0;
  }
  if ( (unsigned int)WsGetOptionalCertificateName(v20, 2, v19, CertificateInStore) )
  {
    v42 = 1;
    goto LABEL_22;
  }
  LastError = GetLastError();
  v11 = LastError;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v13 = 80;
    goto LABEL_35;
  }
LABEL_36:
  if ( !v11 )
    return 0;
LABEL_73:
  LOBYTE(a2) = v42;
  WsFreeCertificateMappingField(**a1 + 8, a2);
  LOBYTE(v34) = v5;
  WsFreeCertificateMappingField(**a1 + 16, v34);
  LOBYTE(v35) = v6;
  WsFreeCertificateMappingField(**a1 + 32, v35);
  LOBYTE(v36) = v43;
  WsFreeCertificateMappingField(**a1 + 40, v36);
  LOBYTE(v37) = v44;
  WsFreeCertificateMappingField(**a1 + 48, v37);
  LOBYTE(v38) = v8;
  WsFreeCertificateMappingField(**a1 + 56, v38);
  if ( *((_QWORD *)&pvFindPara[0] + 1) )
    LocalFree(*((HLOCAL *)&pvFindPara[0] + 1));
  if ( v4 )
    CertFreeCertificateContext(v4);
  if ( v9 )
  {
    if ( !CertCloseStore(v9, 2u) )
    {
      v39 = GetLastError();
      v11 = v39;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, v39);
      }
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180025220  mov     rax, rsp
0x180025223  push    rbx
0x180025224  push    rbp
0x180025225  push    rsi
0x180025226  push    rdi
0x180025227  push    r12
0x180025229  push    r13
0x18002522b  push    r14
0x18002522d  push    r15
0x18002522f  sub     rsp, 58h
0x180025233  xor     edi, edi
0x180025235  mov     dword ptr [rax+20h], 4
0x18002523c  mov     [rax-68h], edi
0x18002523f  xorps   xmm0, xmm0
0x180025242  movups  xmmword ptr [rax-60h], xmm0
0x180025246  mov     rax, [rcx]
0x180025249  mov     rsi, rcx
0x18002524c  mov     ebp, edi
0x18002524e  mov     [rsp+98h+arg_0], dil
0x180025256  mov     r12b, dil
0x180025259  mov     [rsp+98h+arg_8], dil
0x180025261  mov     [rsp+98h+arg_10], dil
0x180025269  mov     r13b, dil
0x18002526c  mov     rcx, [rax]
0x18002526f  mov     r15b, dil
0x180025272  cmp     [rcx], rdi
0x180025275  jz      loc_1800256EB
0x18002527b  cmp     [rcx+18h], rdi
0x18002527f  jz      loc_1800256EB
0x180025285  mov     rax, [rcx+40h]
0x180025289  test    rax, rax
0x18002528c  jz      loc_1800256EB
0x180025292  mov     r9d, 28000h; dwFlags
0x180025298  mov     [rsp+98h+pvPara], rax; pvPara
0x18002529d  xor     r8d, r8d; hCryptProv
0x1800252a0  lea     ecx, [rdi+0Ah]; lpszStoreProvider
0x1800252a3  mov     edx, 10001h; dwEncodingType
0x1800252a8  call    cs:__imp_CertOpenStore
0x1800252ae  mov     r14, rax
0x1800252b1  test    rax, rax
0x1800252b4  jnz     short loc_1800252F1
0x1800252b6  call    cs:__imp_GetLastError
0x1800252bc  mov     ebx, eax
0x1800252be  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800252c5  lea     rdi, WPP_GLOBAL_Control
0x1800252cc  cmp     rcx, rdi
0x1800252cf  jz      loc_18002548D
0x1800252d5  test    byte ptr [rcx+1Ch], 2
0x1800252d9  jz      loc_18002548D
0x1800252df  cmp     byte ptr [rcx+19h], 1
0x1800252e3  jb      loc_18002548D
0x1800252e9  lea     edx, [rbp+4Eh]
0x1800252ec  jmp     loc_18002547A
0x1800252f1  mov     rax, [rsi]
0x1800252f4  lea     rdx, [rsp+98h+pvFindPara]; pcbBinary
0x1800252f9  mov     rcx, [rax]
0x1800252fc  mov     rcx, [rcx+18h]; pszString
0x180025300  call    LmConvertCryptStringToBinary
0x180025305  mov     ebx, eax
0x180025307  test    eax, eax
0x180025309  jz      short loc_180025343
0x18002530b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180025312  lea     rdi, WPP_GLOBAL_Control
0x180025319  cmp     rcx, rdi
0x18002531c  jz      loc_180025728
0x180025322  test    byte ptr [rcx+1Ch], 2
0x180025326  jz      loc_180025728
0x18002532c  cmp     byte ptr [rcx+19h], 1
0x180025330  jb      loc_180025728
0x180025336  mov     edx, 4Fh ; 'O'
0x18002533b  mov     r9d, eax
0x18002533e  jmp     loc_180025718
0x180025343  mov     r9d, 10000h; dwFindType
0x180025349  mov     [rsp+98h+pPrevCertContext], rdi; pPrevCertContext
0x18002534e  lea     rax, [rsp+98h+pvFindPara]
0x180025353  xor     r8d, r8d; dwFindFlags
0x180025356  mov     rcx, r14; hCertStore
0x180025359  mov     [rsp+98h+pvPara], rax; pvFindPara
0x18002535e  lea     edx, [r9+1]; dwCertEncodingType
0x180025362  call    cs:__imp_CertFindCertificateInStore
0x180025368  mov     rbp, rax
0x18002536b  test    rax, rax
0x18002536e  jz      loc_1800256A4
0x180025374  mov     rcx, [rsi]
0x180025377  mov     rcx, [rcx]
0x18002537a  add     rcx, 8
0x18002537e  cmp     [rcx], rdi
0x180025381  jnz     short loc_1800253D9
0x180025383  mov     r9, rax
0x180025386  mov     edx, 2
0x18002538b  call    WsGetOptionalCertificateName
0x180025390  test    eax, eax
0x180025392  jnz     short loc_1800253D1
0x180025394  call    cs:__imp_GetLastError
0x18002539a  mov     ebx, eax
0x18002539c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800253a3  lea     rdi, WPP_GLOBAL_Control
0x1800253aa  cmp     rcx, rdi
0x1800253ad  jz      loc_18002548D
0x1800253b3  test    byte ptr [rcx+1Ch], 2
0x1800253b7  jz      loc_18002548D
0x1800253bd  cmp     byte ptr [rcx+19h], 1
0x1800253c1  jb      loc_18002548D
0x1800253c7  mov     edx, 50h ; 'P'
0x1800253cc  jmp     loc_18002547A
0x1800253d1  mov     [rsp+98h+arg_0], 1
0x1800253d9  mov     rax, [rsi]
0x1800253dc  mov     rcx, [rax]
0x1800253df  add     rcx, 10h
0x1800253e3  cmp     [rcx], rdi
0x1800253e6  jnz     short loc_18002542E
0x1800253e8  mov     edx, 4
0x1800253ed  mov     r9, rbp
0x1800253f0  lea     r8d, [rdx-3]
0x1800253f4  call    WsGetCertificateName
0x1800253f9  test    eax, eax
0x1800253fb  jnz     short loc_18002542B
0x1800253fd  call    cs:__imp_GetLastError
0x180025403  mov     ebx, eax
0x180025405  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002540c  lea     rdi, WPP_GLOBAL_Control
0x180025413  cmp     rcx, rdi
0x180025416  jz      short loc_18002548D
0x180025418  test    byte ptr [rcx+1Ch], 2
0x18002541c  jz      short loc_18002548D
0x18002541e  cmp     byte ptr [rcx+19h], 1
0x180025422  jb      short loc_18002548D
0x180025424  mov     edx, 51h ; 'Q'
0x180025429  jmp     short loc_18002547A
0x18002542b  mov     r12b, 1
0x18002542e  mov     rax, [rsi]
0x180025431  mov     rcx, [rax]
0x180025434  add     rcx, 20h ; ' '
0x180025438  cmp     [rcx], rdi
0x18002543b  jnz     short loc_18002549D
0x18002543d  mov     r9, rbp
0x180025440  mov     edx, 5
0x180025445  call    WsGetOptionalCertificateName
0x18002544a  test    eax, eax
0x18002544c  jnz     short loc_18002549A
0x18002544e  call    cs:__imp_GetLastError
0x180025454  mov     ebx, eax
0x180025456  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002545d  lea     rdi, WPP_GLOBAL_Control
0x180025464  cmp     rcx, rdi
0x180025467  jz      short loc_18002548D
0x180025469  test    byte ptr [rcx+1Ch], 2
0x18002546d  jz      short loc_18002548D
0x18002546f  cmp     byte ptr [rcx+19h], 1
0x180025473  jb      short loc_18002548D
0x180025475  mov     edx, 52h ; 'R'
0x18002547a  mov     rcx, [rcx+10h]
0x18002547e  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x180025485  mov     r9d, eax
0x180025488  call    WPP_SF_d
0x18002548d  test    ebx, ebx
0x18002548f  jnz     loc_180025728
0x180025495  jmp     loc_18002569D
0x18002549a  mov     r13b, 1
0x18002549d  mov     rax, [rsi]
0x1800254a0  mov     ebx, 2Ah ; '*'
0x1800254a5  mov     rcx, [rax]
0x1800254a8  cmp     [rcx+28h], rdi
0x1800254ac  jnz     short loc_1800254F4
0x1800254ae  mov     edx, ebx; uBytes
0x1800254b0  lea     ecx, [rbx+16h]; uFlags
0x1800254b3  call    cs:__imp_LocalAlloc
0x1800254b9  mov     rcx, [rsi]
0x1800254bc  mov     rdx, [rcx]
0x1800254bf  mov     [rdx+28h], rax
0x1800254c3  mov     rax, [rsi]
0x1800254c6  mov     rcx, [rax]
0x1800254c9  mov     rcx, [rcx+28h]
0x1800254cd  test    rcx, rcx
0x1800254d0  jz      loc_18002569D
0x1800254d6  mov     r9, [rbp+18h]
0x1800254da  lea     r8, aLlu; "%llu"
0x1800254e1  mov     edx, ebx
0x1800254e3  mov     r9, [r9+40h]
0x1800254e7  call    RtlStringCbPrintfW
0x1800254ec  mov     [rsp+98h+arg_8], 1
0x1800254f4  mov     rax, [rsi]
0x1800254f7  mov     rcx, [rax]
0x1800254fa  cmp     [rcx+30h], rdi
0x1800254fe  jnz     short loc_18002554A
0x180025500  mov     rdx, rbx; uBytes
0x180025503  mov     ecx, 40h ; '@'; uFlags
0x180025508  call    cs:__imp_LocalAlloc
0x18002550e  mov     rcx, [rsi]
0x180025511  mov     rdx, [rcx]
0x180025514  mov     [rdx+30h], rax
0x180025518  mov     rax, [rsi]
0x18002551b  mov     rcx, [rax]
0x18002551e  mov     rcx, [rcx+30h]
0x180025522  test    rcx, rcx
0x180025525  jz      loc_18002569D
0x18002552b  mov     r9, [rbp+18h]
0x18002552f  lea     r8, aLlu; "%llu"
0x180025536  mov     rdx, rbx
0x180025539  mov     r9, [r9+48h]
0x18002553d  call    RtlStringCbPrintfW
0x180025542  mov     [rsp+98h+arg_10], 1
0x18002554a  mov     rax, [rsi]
0x18002554d  mov     rcx, [rax]
0x180025550  cmp     [rcx+38h], rdi
0x180025554  jnz     short loc_1800255BC
0x180025556  mov     rdx, [rcx+40h]
0x18002555a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002555e  inc     rax
0x180025561  cmp     [rdx+rax*2], di
0x180025565  jnz     short loc_18002555E
0x180025567  lea     rbx, ds:28h[rax*2]
0x18002556f  mov     ecx, 40h ; '@'; uFlags
0x180025574  mov     rdx, rbx; uBytes
0x180025577  call    cs:__imp_LocalAlloc
0x18002557d  mov     rcx, [rsi]
0x180025580  mov     rdx, [rcx]
0x180025583  mov     [rdx+38h], rax
0x180025587  mov     rax, [rsi]
0x18002558a  mov     rax, [rax]
0x18002558d  mov     rcx, [rax+38h]
0x180025591  test    rcx, rcx
0x180025594  jz      loc_18002569D
0x18002559a  mov     rax, [rax+40h]
0x18002559e  lea     r9, aCertLocalmachi; "cert:\\LocalMachine\\"
0x1800255a5  lea     r8, aWsWs_0; "%ws%ws"
0x1800255ac  mov     [rsp+98h+pvPara], rax
0x1800255b1  mov     rdx, rbx
0x1800255b4  call    RtlStringCbPrintfW
0x1800255b9  mov     r15b, 1
0x1800255bc  mov     rax, [rsi]
0x1800255bf  lea     r9, [rsp+98h+pcbData]; pcbData
0x1800255c7  lea     r8, [rsp+98h+pvData]; pvData
0x1800255cc  mov     edx, 6; dwPropId
0x1800255d1  mov     rcx, [rax]
0x1800255d4  mov     [rcx+50h], edi
0x1800255d7  mov     rax, [rsi]
0x1800255da  mov     rcx, [rax]
0x1800255dd  mov     [rcx+58h], edi
0x1800255e0  mov     rcx, rbp; pCertContext
0x1800255e3  call    cs:__imp_CertGetCertificateContextProperty
0x1800255e9  test    eax, eax
0x1800255eb  jnz     short loc_180025635
0x1800255ed  mov     ebx, 0C05D0006h
0x1800255f2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800255f9  lea     rdi, WPP_GLOBAL_Control
0x180025600  cmp     rcx, rdi
0x180025603  jz      loc_180025728
0x180025609  test    byte ptr [rcx+1Ch], 2
0x18002560d  jz      loc_180025728
0x180025613  cmp     byte ptr [rcx+19h], 1
0x180025617  jb      loc_180025728
0x18002561d  mov     rcx, [rcx+10h]
0x180025621  lea     edx, [rax+53h]
0x180025624  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x18002562b  call    WPP_SF_
0x180025630  jmp     loc_180025728
0x180025635  mov     rcx, [rsp+98h+hMem]; hMem
0x18002563a  test    rcx, rcx
0x18002563d  jz      short loc_180025645
0x18002563f  call    cs:__imp_LocalFree
0x180025645  mov     rcx, rbp; pCertContext
0x180025648  call    cs:__imp_CertFreeCertificateContext
0x18002564e  mov     edx, 2; dwFlags
0x180025653  mov     rcx, r14; hCertStore
0x180025656  call    cs:__imp_CertCloseStore
0x18002565c  test    eax, eax
0x18002565e  jnz     short loc_18002569D
0x180025660  call    cs:__imp_GetLastError
0x180025666  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002566d  lea     rdi, WPP_GLOBAL_Control
0x180025674  cmp     rcx, rdi
0x180025677  jz      short loc_18002569D
0x180025679  test    byte ptr [rcx+1Ch], 2
0x18002567d  jz      short loc_18002569D
0x18002567f  cmp     byte ptr [rcx+19h], 1
0x180025683  jb      short loc_18002569D
0x180025685  mov     rcx, [rcx+10h]
0x180025689  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x180025690  mov     edx, 55h ; 'U'
0x180025695  mov     r9d, eax
0x180025698  call    WPP_SF_d
0x18002569d  xor     eax, eax
0x18002569f  jmp     loc_18002580F
0x1800256a4  mov     rbx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800256ab  lea     rdi, WPP_GLOBAL_Control
0x1800256b2  cmp     rbx, rdi
0x1800256b5  jz      short loc_1800256E4
0x1800256b7  test    byte ptr [rbx+1Ch], 2
0x1800256bb  jz      short loc_1800256E4
0x1800256bd  cmp     byte ptr [rbx+19h], 1
0x1800256c1  jb      short loc_1800256E4
0x1800256c3  mov     rbx, [rbx+10h]
0x1800256c7  call    cs:__imp_GetLastError
0x1800256cd  mov     edx, 54h ; 'T'
0x1800256d2  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x1800256d9  mov     r9d, eax
0x1800256dc  mov     rcx, rbx
0x1800256df  call    WPP_SF_d
0x1800256e4  mov     ebx, 490h
  ... truncated ...
```
