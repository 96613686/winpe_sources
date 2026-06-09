# MinCryptVerifyCertificateWithPolicy2

- ea: `0x140066604`
- end: `0x1400670ea`
- name: `MinCryptVerifyCertificateWithPolicy2`
- size: `2790`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005e3c4`

## callees

- `0x14001cb6c`
- `0x140026514`
- `0x140066088`
- `0x140066364`
- `0x140066398`
- `0x1400663d0`
- `0x140066424`
- `0x1400664ac`
- `0x140066518`
- `0x1400665b0`
- `0x140066604`
- `0x14006710c`
- `0x140067258`
- `0x14006738c`
- `0x14006759c`
- `0x1400676a0`
- `0x140083d68`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x140066e08`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x140066e08`

## pseudocode

```c
__int64 __fastcall MinCryptVerifyCertificateWithPolicy2(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v6; // esi
  int v7; // r12d
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // r15
  int CertificateEKUs; // edi
  unsigned int v12; // edx
  __int64 v13; // r8
  unsigned int v14; // ecx
  unsigned int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // r14
  __int64 v18; // r8
  __int64 v19; // r9
  char v20; // r15
  char v21; // r14
  int v22; // eax
  __int64 v23; // r15
  char *v24; // rdi
  __int64 v25; // rdx
  unsigned int v26; // r12d
  char *v27; // rax
  __int64 v28; // r8
  char *Src; // r10
  __int64 v30; // r9
  unsigned int v31; // eax
  unsigned int v32; // ecx
  unsigned int v33; // eax
  unsigned int v34; // r14d
  unsigned int v35; // eax
  unsigned int v36; // ecx
  char CommonName; // al
  unsigned int v38; // eax
  unsigned int v39; // ecx
  __int64 v40; // r8
  const void **v41; // r12
  unsigned int v42; // eax
  int v43; // eax
  int v44; // r15d
  unsigned int v45; // ecx
  _OWORD *v46; // r15
  __int64 RootByKey; // rax
  int v48; // edx
  __int64 v49; // r8
  __int64 v50; // rdx
  unsigned int v51; // ecx
  unsigned int v52; // eax
  unsigned int v53; // eax
  int v54; // edx
  unsigned int v55; // eax
  unsigned int v56; // eax
  unsigned int v57; // eax
  __int64 i; // r15
  __int64 *v59; // r14
  int v60; // edx
  unsigned int v61; // ecx
  unsigned int v62; // eax
  unsigned int v63; // eax
  __int64 IssuerCertificateByName; // rax
  __int64 v65; // rdi
  int v66; // r14d
  int v68; // [rsp+64h] [rbp-114h] BYREF
  int v69; // [rsp+68h] [rbp-110h]
  int v70; // [rsp+6Ch] [rbp-10Ch]
  int v71; // [rsp+70h] [rbp-108h]
  void *v72; // [rsp+78h] [rbp-100h]
  __int64 v73; // [rsp+80h] [rbp-F8h]
  char v74; // [rsp+88h] [rbp-F0h]
  int v75; // [rsp+8Ch] [rbp-ECh] BYREF
  unsigned int v76; // [rsp+90h] [rbp-E8h] BYREF
  int v77; // [rsp+94h] [rbp-E4h]
  int v78; // [rsp+98h] [rbp-E0h]
  int v79; // [rsp+9Ch] [rbp-DCh]
  __int64 v80; // [rsp+A0h] [rbp-D8h]
  char v81; // [rsp+A8h] [rbp-D0h]
  int v82; // [rsp+ACh] [rbp-CCh]
  unsigned int v83; // [rsp+B0h] [rbp-C8h]
  __int64 v84; // [rsp+B8h] [rbp-C0h] BYREF
  __int64 v85; // [rsp+C0h] [rbp-B8h] BYREF
  __int64 v86; // [rsp+C8h] [rbp-B0h]
  unsigned int v87; // [rsp+D0h] [rbp-A8h]
  unsigned int v88; // [rsp+D4h] [rbp-A4h]
  __int64 v89; // [rsp+D8h] [rbp-A0h] BYREF
  int v90; // [rsp+E0h] [rbp-98h]
  unsigned int v91; // [rsp+E4h] [rbp-94h]
  int v92; // [rsp+E8h] [rbp-90h]
  __int64 v93; // [rsp+F0h] [rbp-88h] BYREF
  __int64 v94; // [rsp+F8h] [rbp-80h]
  char *v95; // [rsp+100h] [rbp-78h]
  __int64 v96; // [rsp+108h] [rbp-70h]
  unsigned int v97; // [rsp+110h] [rbp-68h]
  __int64 v98; // [rsp+118h] [rbp-60h]
  __int64 v99; // [rsp+120h] [rbp-58h]
  __int64 v100; // [rsp+128h] [rbp-50h]
  __int64 v101; // [rsp+130h] [rbp-48h]
  unsigned int v102; // [rsp+138h] [rbp-40h]
  int v103[2]; // [rsp+140h] [rbp-38h]

  v98 = a3;
  v80 = a1;
  v101 = a5;
  v83 = 0;
  v75 = 50;
  v78 = 0;
  v76 = 0;
  v68 = 0;
  v69 = 0;
  v6 = 0;
  v70 = 0;
  v77 = 0;
  v94 = 0;
  v79 = 0;
  v93 = 0;
  v7 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v84 = 0;
  v85 = 0;
  LOBYTE(v82) = 0;
  v8 = 0x7FFFFFFFFFFFFFFFLL;
  v96 = 0x7FFFFFFFFFFFFFFFLL;
  v100 = a1;
  v9 = MincryptAlloc(2976);
  v10 = v9;
  v86 = v9;
  if ( !v9 )
  {
    CertificateEKUs = -1073741801;
LABEL_145:
    Src = (char *)v72;
    goto LABEL_146;
  }
  v73 = v9 + 800;
  v72 = (void *)(v9 + 1776);
  CertificateEKUs = I_MinCryptGetCertificateEKUs(a1 + 224, &v75, v9);
  if ( CertificateEKUs < 0 )
    goto LABEL_145;
  v12 = 0;
  v13 = 0;
  while ( 1 )
  {
    v91 = v12;
    if ( v12 >= v75 )
      break;
    v14 = *(_DWORD *)(v10 + 16LL * v12);
    v15 = (v14 + 3) & 0xFFFFFFFC;
    if ( v15 < v14 )
    {
      CertificateEKUs = -1073741675;
      goto LABEL_145;
    }
    v6 = v13 + v15;
    if ( (unsigned int)v13 + v15 < (unsigned int)v13 )
    {
      v6 = -1;
      v70 = -1;
      CertificateEKUs = -1073741675;
      v16 = -1;
    }
    else
    {
      v70 = v13 + v15;
      CertificateEKUs = 0;
      v16 = v13 + v15;
    }
    if ( CertificateEKUs < 0 )
      goto LABEL_145;
    v6 = v16 + 16;
    if ( v16 + 16 < v16 )
    {
      v6 = -1;
      v70 = -1;
      CertificateEKUs = -1073741675;
      v13 = 0xFFFFFFFFLL;
    }
    else
    {
      v70 = v16 + 16;
      CertificateEKUs = 0;
      v13 = v6;
    }
    if ( CertificateEKUs < 0 )
      goto LABEL_145;
    ++v12;
  }
  v17 = v80;
  if ( !(unsigned __int8)MinAsn1DecodeTime(v80 + 128, &v84, v13, 3221225621LL)
    || !(unsigned __int8)MinAsn1DecodeTime(v17 + 144, &v85, v18, v19) )
  {
    v84 = 0;
    v85 = 0;
  }
  v20 = I_MinCryptCheckEKU(&qword_1400B6338, (unsigned int)v75, v10);
  if ( v20 && g_FlightSignedNotBefore > 0 && v84 < g_FlightSignedNotBefore )
  {
    v68 |= 0x600000u;
LABEL_24:
    CertificateEKUs = -1073740283;
    goto LABEL_145;
  }
  if ( !g_IgnoreLifetimeSigningEKU && (unsigned __int8)I_MinCryptCheckEKU(&qword_1400B6328, (unsigned int)v75, v86) )
  {
    v21 = 0;
    v74 = 0;
    v89 = 0;
    MincryptQuerySystemTime(&v89);
    if ( !v20 && v89 < v84 || v89 > v85 )
    {
      v21 = 1;
      v74 = 1;
    }
    if ( v21 )
    {
      v68 |= 0x400000u;
      goto LABEL_24;
    }
    v17 = v80;
  }
  v22 = v78;
  while ( 1 )
  {
    if ( v22 )
      goto LABEL_145;
    v23 = 120LL * (unsigned int)v77;
    v24 = (char *)v72;
    v88 = MinCryptDecodeHashAlgorithmIdentifier(v17 + 48);
    v26 = v88;
    if ( v88 == 0x8000 )
      v26 = 32782;
    LODWORD(v89) = v26;
    CertificateEKUs = HashpHashMemory(v26, v25, v17 + 32, &v24[v23 + 8], &v76);
    if ( CertificateEKUs < 0 )
    {
      v68 |= 0x40000u;
LABEL_40:
      v7 = v71;
      goto LABEL_145;
    }
    if ( v88 == 0x8000 )
    {
      v87 = *(_DWORD *)(v17 + 32);
      v27 = *(char **)(v17 + 40);
      v28 = v76;
    }
    else
    {
      v27 = (char *)v72 + v23 + 8;
      *(_QWORD *)v103 = v27;
      v28 = v76;
      v87 = v76;
      v102 = v76;
    }
    v95 = v27;
    Src = (char *)v72;
    *(_DWORD *)((char *)v72 + v23) = v26;
    *(_DWORD *)&Src[v23 + 4] = v28;
    v30 = v80;
    *(_OWORD *)&Src[v23 + 104] = *(_OWORD *)(v80 + 16);
    v31 = *(_DWORD *)(v30 + 16);
    v32 = (v31 + 3) & 0xFFFFFFFC;
    if ( v32 < v31 )
      break;
    v33 = v6;
    v6 += v32;
    if ( v6 < v33 )
    {
      v6 = -1;
      v70 = -1;
      CertificateEKUs = -1073741675;
      v34 = -1;
    }
    else
    {
      v70 = v6;
      CertificateEKUs = 0;
      v34 = v6;
    }
    if ( CertificateEKUs < 0 )
      goto LABEL_46;
    *(_OWORD *)&Src[v23 + 72] = 0;
    *(_OWORD *)&Src[v23 + 88] = 0;
    if ( a5 )
    {
      if ( (unsigned __int8)I_MinCryptGetCommonName(v30 + 160) )
      {
        Src = (char *)v72;
        v35 = *(unsigned __int16 *)((char *)v72 + v23 + 80);
        v36 = (v35 + 3) & 0xFFFFFFFC;
        if ( v36 < v35 )
          break;
        v6 = v34 + v36;
        if ( v34 + v36 < v34 )
        {
          v6 = -1;
          v70 = -1;
          CertificateEKUs = -1073741675;
          v34 = -1;
        }
        else
        {
          v70 = v34 + v36;
          CertificateEKUs = 0;
          v34 += v36;
        }
        if ( CertificateEKUs < 0 )
          goto LABEL_46;
      }
      CommonName = I_MinCryptGetCommonName(v80 + 112);
      Src = (char *)v72;
      if ( CommonName )
      {
        v38 = *(unsigned __int16 *)((char *)v72 + v23 + 96);
        v39 = (v38 + 3) & 0xFFFFFFFC;
        if ( v39 < v38 )
          break;
        v6 = v34 + v39;
        if ( v34 + v39 < v34 )
        {
          v6 = -1;
          v70 = -1;
          CertificateEKUs = -1073741675;
          v34 = -1;
        }
        else
        {
          v70 = v34 + v39;
          CertificateEKUs = 0;
          v34 += v39;
        }
        if ( CertificateEKUs < 0 )
          goto LABEL_46;
      }
      v28 = v76;
    }
    ++v77;
    v6 = v34 + 120;
    if ( v34 + 120 < v34 )
    {
      v6 = -1;
      CertificateEKUs = -1073741675;
    }
    else
    {
      CertificateEKUs = 0;
    }
    v70 = v6;
    if ( CertificateEKUs < 0 )
      goto LABEL_46;
    if ( (unsigned __int8)I_MinCryptIsCertificateHashRevokedV2((unsigned int)v89, &Src[v23 + 8], v28, &v93) )
    {
      v79 = 1;
      v68 |= 0x200000u;
      if ( v93 < v8 )
        v8 = v93;
      v96 = v8;
    }
    v17 = v80;
    v41 = (const void **)(v80 + 112);
    v42 = *(_DWORD *)(v80 + 112);
    if ( v42 == *(_DWORD *)(v80 + 160) )
    {
      v43 = memcmp_0(*(const void **)(v80 + 120), *(const void **)(v80 + 168), v42);
      v44 = (unsigned __int8)v82;
      if ( !v43 )
        v44 = 1;
      v82 = v44;
      v81 = v44;
    }
    else
    {
      LOBYTE(v44) = v82;
    }
    LOBYTE(v40) = v44;
    CertificateEKUs = MincryptValidateBasicConstraints(v17 + 224, v83, v40, &v68);
    if ( CertificateEKUs < 0 )
      goto LABEL_40;
    if ( (_BYTE)v44 )
    {
      v46 = (_OWORD *)(v17 + 176);
      RootByKey = I_MinCryptFindRootByKey(v17 + 176);
      if ( RootByKey )
      {
        v46 = (_OWORD *)(RootByKey + 16);
        v68 |= *(_DWORD *)(RootByKey + 32) | 1;
        v7 = *(_DWORD *)(RootByKey + 36);
      }
      else
      {
        if ( !a5 )
        {
          CertificateEKUs = -1073740760;
          goto LABEL_40;
        }
        v68 |= 1u;
        v7 = 2;
      }
      v71 = v7;
      if ( a5 )
      {
        v48 = v69;
        v49 = v73;
        *(_OWORD *)(v73 + 16LL * (unsigned int)v69) = *v46;
        v50 = (unsigned int)(v48 + 1);
        v69 = v50;
        v51 = (*(_DWORD *)v46 + 3) & 0xFFFFFFFC;
        if ( v51 < *(_DWORD *)v46 )
          goto LABEL_87;
        v52 = v6;
        v6 += v51;
        if ( v6 < v52 )
        {
          v6 = -1;
          CertificateEKUs = -1073741675;
          v53 = -1;
        }
        else
        {
          CertificateEKUs = 0;
          v53 = v6;
        }
        v70 = v6;
        if ( CertificateEKUs < 0 )
          goto LABEL_88;
        v6 = v53 + 16;
        if ( v53 + 16 < v53 )
        {
          v6 = -1;
          CertificateEKUs = -1073741675;
        }
        else
        {
          CertificateEKUs = 0;
        }
        v70 = v6;
        if ( CertificateEKUs < 0 )
          goto LABEL_88;
      }
      v78 = 1;
      v92 = 1;
    }
    else
    {
      if ( a5 )
      {
        v54 = v69;
        v49 = v73;
        *(_OWORD *)(v73 + 16LL * (unsigned int)v69) = *(_OWORD *)(v17 + 176);
        v50 = (unsigned int)(v54 + 1);
        v69 = v50;
        v55 = *(_DWORD *)(v17 + 176);
        v45 = (v55 + 3) & 0xFFFFFFFC;
        if ( v45 < v55 )
        {
          CertificateEKUs = -1073741675;
LABEL_101:
          v7 = v71;
          goto LABEL_88;
        }
        v56 = v6;
        v6 += v45;
        if ( v6 < v56 )
        {
          v6 = -1;
          CertificateEKUs = -1073741675;
          v57 = -1;
        }
        else
        {
          CertificateEKUs = 0;
          v57 = v6;
        }
        v70 = v6;
        if ( CertificateEKUs < 0 )
          goto LABEL_101;
        v6 = v57 + 16;
        if ( v57 + 16 < v57 )
        {
          v6 = -1;
          CertificateEKUs = -1073741675;
        }
        else
        {
          CertificateEKUs = 0;
        }
        v70 = v6;
        if ( CertificateEKUs < 0 )
          goto LABEL_101;
      }
      v90 = 0;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v90 = i;
        if ( (unsigned int)i >= 0x13 )
          break;
        v59 = &RootTable[5 * i];
        if ( *(_DWORD *)v41 == *(_DWORD *)v59
          && RtlCompareMemory(v41[1], (const void *)RootTable[5 * i + 1], *(unsigned int *)v41) == v45 )
        {
          goto LABEL_116;
        }
      }
      v59 = 0;
LABEL_116:
      if ( v59 )
      {
        v46 = v59 + 2;
        v68 |= *((_DWORD *)v59 + 8);
        v7 = *((_DWORD *)v59 + 9);
        v71 = v7;
        v78 = 1;
        v92 = 1;
        if ( a5 )
        {
          v60 = v69;
          v49 = v73;
          *(_OWORD *)(v73 + 16LL * (unsigned int)v69) = *v46;
          v50 = (unsigned int)(v60 + 1);
          v69 = v50;
          v61 = (*(_DWORD *)v46 + 3) & 0xFFFFFFFC;
          if ( v61 < *(_DWORD *)v46 )
          {
LABEL_87:
            CertificateEKUs = -1073741675;
LABEL_88:
            Src = (char *)v72;
            goto LABEL_147;
          }
          v62 = v6;
          v6 += v61;
          if ( v6 < v62 )
          {
            v6 = -1;
            CertificateEKUs = -1073741675;
            v63 = -1;
          }
          else
          {
            CertificateEKUs = 0;
            v63 = v6;
          }
          v70 = v6;
          if ( CertificateEKUs < 0 )
            goto LABEL_88;
          v6 = v63 + 16;
          if ( v63 + 16 < v63 )
          {
            v6 = -1;
            CertificateEKUs = -1073741675;
          }
          else
          {
            CertificateEKUs = 0;
          }
          v70 = v6;
          if ( CertificateEKUs < 0 )
            goto LABEL_88;
        }
      }
      else
      {
        IssuerCertificateByName = I_MinCryptFindIssuerCertificateByName(v41, 3, v98);
        v65 = IssuerCertificateByName;
        v94 = IssuerCertificateByName;
        v99 = IssuerCertificateByName;
        if ( IssuerCertificateByName )
        {
          v65 = IssuerCertificateByName
              & -(__int64)((unsigned int)MinCryptDecodeHashAlgorithmIdentifier(IssuerCertificateByName + 48) != 0);
          v94 = v65;
          v99 = v65;
        }
        if ( !v65 )
        {
          v7 = 1;
          v71 = 1;
          goto LABEL_132;
        }
        v46 = (_OWORD *)(v65 + 176);
        v7 = v71;
      }
      v17 = v80;
    }
    CertificateEKUs = MinCryptVerifySignedHash2(v88, (_DWORD)v95, v87, (int)v17 + 64, (__int64)v46);
    if ( CertificateEKUs < 0 )
    {
      v68 |= 0x40000u;
      goto LABEL_145;
    }
    v22 = v78;
    if ( !v78 )
    {
      v97 = ++v83;
      if ( v83 >= 0xA )
      {
        v7 = 1;
        v71 = 1;
LABEL_132:
        if ( a5 )
        {
          v68 |= 0x10u;
          CertificateEKUs = 0;
        }
        else
        {
          v68 |= 0x20000u;
          CertificateEKUs = -1073740760;
        }
        v50 = (unsigned int)v69;
        Src = (char *)v72;
        v49 = v73;
        goto LABEL_147;
      }
      v17 = v94;
      v80 = v94;
      v100 = v94;
    }
  }
  CertificateEKUs = -1073741675;
LABEL_46:
  v7 = v71;
LABEL_146:
  v50 = (unsigned int)v69;
  v49 = v73;
LABEL_147:
  v66 = v79;
  if ( a5 )
  {
    *(_DWORD *)a5 = 48;
    *(_DWORD *)(a5 + 4) = CertificateEKUs;
    *(_DWORD *)(a5 + 8) = v68;
    *(_QWORD *)(a5 + 16) = 0;
    *(_QWORD *)(a5 + 32) = v84;
    *(_QWORD *)(a5 + 40) = v85;
    if ( v66 )
      *(_QWORD *)(a5 + 24) = v8;
    if ( CertificateEKUs >= 0 )
      CertificateEKUs = I_MincryptAddChainInfo(a5, v6, v75, v50, v77, v7, v86, v49, Src);
  }
  if ( v86 )
    MincryptFree(v86, v50, v49);
  if ( CertificateEKUs >= 0 && v66 )
    return (unsigned int)-1073740285;
  return (unsigned int)CertificateEKUs;
}

```

## disassembly

```asm
0x140066604  mov     rax, rsp
0x140066607  mov     [rax+10h], rbx
0x14006660b  mov     [rax+20h], rsi
0x14006660f  push    rdi
0x140066610  push    r12
0x140066612  push    r13
0x140066614  push    r14
0x140066616  push    r15
0x140066618  sub     rsp, 140h
0x14006661f  mov     [rsp+168h+var_60], r8
0x140066627  mov     r14, rcx
0x14006662a  mov     [rax-0D8h], rcx
0x140066631  mov     r13, qword ptr [rsp+168h+arg_20]
0x140066639  mov     [rsp+168h+var_48], r13
0x140066641  xor     ecx, ecx
0x140066643  mov     [rsp+168h+var_118], ecx
0x140066647  mov     [rax-0C8h], ecx
0x14006664d  mov     [rsp+168h+var_EC], 32h ; '2'
0x140066655  mov     [rax-0E0h], ecx
0x14006665b  mov     [rax-0E8h], ecx
0x140066661  mov     [rsp+168h+var_114], ecx
0x140066665  mov     [rsp+168h+var_110], ecx
0x140066669  mov     esi, ecx
0x14006666b  mov     [rsp+168h+var_10C], ecx
0x14006666f  mov     [rax-0E4h], ecx
0x140066675  mov     [rax-80h], rcx
0x140066679  mov     [rax-0DCh], ecx
0x14006667f  mov     [rax-88h], rcx
0x140066686  mov     r12d, ecx
0x140066689  mov     [rsp+168h+var_108], ecx
0x14006668d  mov     [rsp+168h+var_100], rcx
0x140066692  mov     [rax-0B0h], rcx
0x140066699  mov     [rsp+168h+var_F8], rcx
0x14006669e  mov     [rax-0C0h], rcx
0x1400666a5  mov     [rax-0B8h], rcx
0x1400666ac  mov     byte ptr [rsp+168h+var_CC], cl
0x1400666b3  mov     rbx, 7FFFFFFFFFFFFFFFh
0x1400666bd  mov     [rax-70h], rbx
0x1400666c1  mov     [rax-50h], r14
0x1400666c5  mov     ecx, 0BA0h
0x1400666ca  call    MincryptAlloc
0x1400666cf  mov     r15, rax
0x1400666d2  mov     [rsp+168h+var_B0], rax
0x1400666da  test    rax, rax
0x1400666dd  jnz     short loc_1400666ED
0x1400666df  mov     edi, 0C0000017h
0x1400666e4  mov     [rsp+168h+var_118], edi
0x1400666e8  jmp     loc_14006700D
0x1400666ed  add     rax, 320h
0x1400666f3  mov     [rsp+168h+var_F8], rax
0x1400666f8  add     rax, 3D0h
0x1400666fe  mov     [rsp+168h+var_100], rax
0x140066703  lea     rcx, [r14+0E0h]
0x14006670a  mov     r8, r15
0x14006670d  lea     rdx, [rsp+168h+var_EC]
0x140066712  call    I_MinCryptGetCertificateEKUs
0x140066717  mov     edi, eax
0x140066719  mov     [rsp+168h+var_118], eax
0x14006671d  test    eax, eax
0x14006671f  js      loc_14006700D
0x140066725  xor     edx, edx
0x140066727  xor     r8d, r8d
0x14006672a  mov     r9d, 0C0000095h
0x140066730  or      r10d, 0FFFFFFFFh
0x140066734  mov     [rsp+168h+var_94], edx
0x14006673b  cmp     edx, [rsp+168h+var_EC]
0x14006673f  jnb     loc_1400667C5
0x140066745  mov     eax, edx
0x140066747  add     rax, rax
0x14006674a  mov     ecx, [r15+rax*8]
0x14006674e  lea     eax, [rcx+3]
0x140066751  and     eax, 0FFFFFFFCh
0x140066754  cmp     eax, ecx
0x140066756  jnb     short loc_140066765
0x140066758  mov     edi, r9d
0x14006675b  mov     [rsp+168h+var_118], r9d
0x140066760  jmp     loc_14006700D
0x140066765  lea     esi, [r8+rax]
0x140066769  cmp     esi, r8d
0x14006676c  jb      short loc_140066778
0x14006676e  mov     [rsp+168h+var_10C], esi
0x140066772  xor     edi, edi
0x140066774  mov     eax, esi
0x140066776  jmp     short loc_140066786
0x140066778  mov     esi, r10d
0x14006677b  mov     [rsp+168h+var_10C], r10d
0x140066780  mov     edi, r9d
0x140066783  mov     eax, r10d
0x140066786  mov     [rsp+168h+var_118], edi
0x14006678a  test    edi, edi
0x14006678c  js      loc_14006700D
0x140066792  lea     esi, [rax+10h]
0x140066795  cmp     esi, eax
0x140066797  jb      short loc_1400667A4
0x140066799  mov     [rsp+168h+var_10C], esi
0x14006679d  xor     edi, edi
0x14006679f  mov     r8d, esi
0x1400667a2  jmp     short loc_1400667B2
0x1400667a4  mov     esi, r10d
0x1400667a7  mov     [rsp+168h+var_10C], r10d
0x1400667ac  mov     edi, r9d
0x1400667af  mov     r8d, r10d
0x1400667b2  mov     [rsp+168h+var_118], edi
0x1400667b6  test    edi, edi
0x1400667b8  js      loc_14006700D
0x1400667be  inc     edx
0x1400667c0  jmp     loc_140066734
0x1400667c5  mov     r14, [rsp+168h+var_D8]
0x1400667cd  lea     rcx, [r14+80h]
0x1400667d4  lea     rdx, [rsp+168h+var_C0]
0x1400667dc  call    MinAsn1DecodeTime
0x1400667e1  test    al, al
0x1400667e3  jz      short loc_1400667FD
0x1400667e5  lea     rcx, [r14+90h]
0x1400667ec  lea     rdx, [rsp+168h+var_B8]
0x1400667f4  call    MinAsn1DecodeTime
0x1400667f9  test    al, al
0x1400667fb  jnz     short loc_140066815
0x1400667fd  mov     [rsp+168h+var_C0], 0
0x140066809  mov     [rsp+168h+var_B8], 0
0x140066815  mov     r8, r15
0x140066818  mov     edx, [rsp+168h+var_EC]
0x14006681c  lea     rcx, qword_1400B6338
0x140066823  call    I_MinCryptCheckEKU
0x140066828  mov     r15b, al
0x14006682b  test    al, al
0x14006682d  jz      short loc_140066866
0x14006682f  mov     rax, cs:g_FlightSignedNotBefore
0x140066836  test    rax, rax
0x140066839  jle     short loc_140066866
0x14006683b  xor     cl, cl
0x14006683d  movzx   edx, cl
0x140066840  cmp     [rsp+168h+var_C0], rax
0x140066848  mov     eax, 1
0x14006684d  cmovl   edx, eax
0x140066850  test    dl, dl
0x140066852  jz      short loc_140066866
0x140066854  or      [rsp+168h+var_114], 600000h
0x14006685c  mov     edi, 0C0000605h
0x140066861  jmp     loc_1400666E4
0x140066866  cmp     cs:g_IgnoreLifetimeSigningEKU, 0
0x14006686d  jnz     short loc_1400668ED
0x14006686f  mov     r8, [rsp+168h+var_B0]
0x140066877  mov     edx, [rsp+168h+var_EC]
0x14006687b  lea     rcx, qword_1400B6328
0x140066882  call    I_MinCryptCheckEKU
0x140066887  test    al, al
0x140066889  jz      short loc_1400668ED
0x14006688b  xor     r14b, r14b
0x14006688e  mov     [rsp+168h+var_F0], r14b
0x140066893  mov     [rsp+168h+var_A0], 0
0x14006689f  lea     rcx, [rsp+168h+var_A0]
0x1400668a7  call    MincryptQuerySystemTime
0x1400668ac  mov     rax, [rsp+168h+var_A0]
0x1400668b4  test    r15b, r15b
0x1400668b7  jnz     short loc_1400668C3
0x1400668b9  cmp     rax, [rsp+168h+var_C0]
0x1400668c1  jl      short loc_1400668CD
0x1400668c3  cmp     rax, [rsp+168h+var_B8]
0x1400668cb  jle     short loc_1400668D5
0x1400668cd  mov     r14b, 1
0x1400668d0  mov     [rsp+168h+var_F0], r14b
0x1400668d5  test    r14b, r14b
0x1400668d8  jz      short loc_1400668E5
0x1400668da  bts     [rsp+168h+var_114], 16h
0x1400668e0  jmp     loc_14006685C
0x1400668e5  mov     r14, [rsp+168h+var_D8]
0x1400668ed  mov     eax, [rsp+168h+var_E0]
0x1400668f4  test    eax, eax
0x1400668f6  jnz     loc_14006700D
0x1400668fc  mov     eax, [rsp+168h+var_E4]
0x140066903  imul    r15, rax, 78h ; 'x'
0x140066907  mov     rdi, [rsp+168h+var_100]
0x14006690c  lea     rcx, [r14+30h]
0x140066910  call    MinCryptDecodeHashAlgorithmIdentifier
0x140066915  mov     [rsp+168h+var_A4], eax
0x14006691c  mov     r12d, eax
0x14006691f  mov     ecx, 800Eh
0x140066924  cmp     eax, 8000h
0x140066929  cmovz   r12d, ecx
0x14006692d  mov     dword ptr [rsp+168h+var_A0], r12d
0x140066935  lea     rax, [rsp+168h+var_E8]
0x14006693d  mov     qword ptr [rsp+168h+var_148], rax
0x140066942  lea     r9, [rdi+8]
0x140066946  add     r9, r15
0x140066949  lea     r8, [r14+20h]
0x14006694d  mov     ecx, r12d
0x140066950  call    HashpHashMemory
0x140066955  mov     edi, eax
0x140066957  mov     [rsp+168h+var_118], eax
0x14006695b  test    eax, eax
0x14006695d  jns     short loc_14006696F
0x14006695f  bts     [rsp+168h+var_114], 12h
0x140066965  mov     r12d, [rsp+168h+var_108]
0x14006696a  jmp     loc_14006700D
0x14006696f  cmp     [rsp+168h+var_A4], 8000h
0x14006697a  jnz     short loc_140066995
0x14006697c  mov     eax, [r14+20h]
0x140066980  mov     [rsp+168h+var_A8], eax
0x140066987  mov     rax, [r14+28h]
0x14006698b  mov     r8d, [rsp+168h+var_E8]
0x140066993  jmp     short loc_1400669C2
0x140066995  mov     rax, [rsp+168h+var_100]
0x14006699a  add     rax, 8
0x14006699e  add     rax, r15
0x1400669a1  mov     qword ptr [rsp+168h+var_38], rax
0x1400669a9  mov     r8d, [rsp+168h+var_E8]
0x1400669b1  mov     edx, r8d
0x1400669b4  mov     [rsp+168h+var_A8], edx
0x1400669bb  mov     [rsp+168h+var_40], edx
0x1400669c2  mov     [rsp+168h+var_78], rax
0x1400669ca  mov     r10, [rsp+168h+var_100]
0x1400669cf  mov     [r15+r10], r12d
0x1400669d3  mov     [r15+r10+4], r8d
0x1400669d8  mov     r9, [rsp+168h+var_D8]
0x1400669e0  movups  xmm0, xmmword ptr [r9+10h]
0x1400669e5  movdqu  xmmword ptr [r15+r10+68h], xmm0
0x1400669ec  mov     eax, [r9+10h]
0x1400669f0  lea     ecx, [rax+3]
0x1400669f3  and     ecx, 0FFFFFFFCh
0x1400669f6  cmp     ecx, eax
0x1400669f8  jnb     short loc_140066A0D
0x1400669fa  mov     edi, 0C0000095h
0x1400669ff  mov     [rsp+168h+var_118], edi
0x140066a03  mov     r12d, [rsp+168h+var_108]
0x140066a08  jmp     loc_140067012
0x140066a0d  mov     eax, esi
0x140066a0f  add     esi, ecx
0x140066a11  cmp     esi, eax
0x140066a13  jb      short loc_140066A20
0x140066a15  mov     [rsp+168h+var_10C], esi
0x140066a19  xor     edi, edi
0x140066a1b  mov     r14d, esi
0x140066a1e  jmp     short loc_140066A31
0x140066a20  or      eax, 0FFFFFFFFh
0x140066a23  mov     esi, eax
0x140066a25  mov     [rsp+168h+var_10C], eax
0x140066a29  mov     edi, 0C0000095h
0x140066a2e  mov     r14d, eax
0x140066a31  mov     [rsp+168h+var_118], edi
0x140066a35  test    edi, edi
0x140066a37  js      short loc_140066A03
0x140066a39  lea     rdx, [r10+48h]
0x140066a3d  add     rdx, r15
0x140066a40  xorps   xmm0, xmm0
0x140066a43  movups  xmmword ptr [rdx], xmm0
0x140066a46  lea     r12, [r15+r10]
0x140066a4a  xorps   xmm1, xmm1
0x140066a4d  movups  xmmword ptr [r12+58h], xmm1
0x140066a53  test    r13, r13
0x140066a56  jz      loc_140066B22
0x140066a5c  lea     rcx, [r9+0A0h]
0x140066a63  call    I_MinCryptGetCommonName
0x140066a68  test    al, al
0x140066a6a  jz      short loc_140066AB6
0x140066a6c  mov     r10, [rsp+168h+var_100]
0x140066a71  movzx   eax, word ptr [r15+r10+50h]
0x140066a77  lea     ecx, [rax+3]
0x140066a7a  and     ecx, 0FFFFFFFCh
0x140066a7d  cmp     ecx, eax
0x140066a7f  jb      loc_1400669FA
0x140066a85  lea     esi, [r14+rcx]
0x140066a89  cmp     esi, r14d
0x140066a8c  jb      short loc_140066A99
0x140066a8e  mov     [rsp+168h+var_10C], esi
0x140066a92  xor     edi, edi
0x140066a94  mov     r14d, esi
0x140066a97  jmp     short loc_140066AAA
0x140066a99  or      eax, 0FFFFFFFFh
0x140066a9c  mov     esi, eax
0x140066a9e  mov     [rsp+168h+var_10C], eax
0x140066aa2  mov     edi, 0C0000095h
0x140066aa7  mov     r14d, eax
0x140066aaa  mov     [rsp+168h+var_118], edi
0x140066aae  test    edi, edi
0x140066ab0  js      loc_140066A03
0x140066ab6  mov     rcx, [rsp+168h+var_D8]
0x140066abe  add     rcx, 70h ; 'p'
0x140066ac2  lea     rdx, [r12+58h]
0x140066ac7  call    I_MinCryptGetCommonName
0x140066acc  mov     r10, [rsp+168h+var_100]
0x140066ad1  test    al, al
0x140066ad3  jz      short loc_140066B1A
0x140066ad5  movzx   eax, word ptr [r15+r10+60h]
0x140066adb  lea     ecx, [rax+3]
0x140066ade  and     ecx, 0FFFFFFFCh
0x140066ae1  cmp     ecx, eax
0x140066ae3  jb      loc_1400669FA
0x140066ae9  lea     esi, [r14+rcx]
0x140066aed  cmp     esi, r14d
0x140066af0  jb      short loc_140066AFD
0x140066af2  mov     [rsp+168h+var_10C], esi
0x140066af6  xor     edi, edi
0x140066af8  mov     r14d, esi
0x140066afb  jmp     short loc_140066B0E
0x140066afd  or      eax, 0FFFFFFFFh
0x140066b00  mov     esi, eax
0x140066b02  mov     [rsp+168h+var_10C], eax
0x140066b06  mov     edi, 0C0000095h
0x140066b0b  mov     r14d, eax
  ... truncated ...
```
