# KerbGetExtendedSanFromCert(_CERT_CONTEXT const *)

- ea: `0x1800761d4`
- end: `0x180076840`
- name: `?KerbGetExtendedSanFromCert@@YA?AUKerbExtendedSanLookupResult@@PEBU_CERT_CONTEXT@@@Z`
- size: `1644`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180054598`
- `0x180074800`

## callees

- `0x1800038f0`
- `0x180003908`
- `0x1800101c4`
- `0x18005a060`
- `0x18005a090`
- `0x1800747a8`
- `0x1800761d4`
- `0x180076fc4`
- `0x180099c34`
- `0x180099c58`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076431`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800764c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007671a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007675e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076431`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800764c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007671a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007675e`
- `CRYPT32!CertFindExtension` at `0x180076279`
- `CRYPT32!CertFindExtension` at `0x1800765d8`
- `CRYPT32!CertFindExtension` at `0x180076279`
- `CRYPT32!CertFindExtension` at `0x1800765d8`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800762c6`
- `CRYPT32!CryptDecodeObjectEx` at `0x18007636f`
- `CRYPT32!CryptDecodeObjectEx` at `0x180076622`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800762c6`
- `CRYPT32!CryptDecodeObjectEx` at `0x18007636f`
- `CRYPT32!CryptDecodeObjectEx` at `0x180076622`
- `ntdll!RtlCopySid` at `0x1800763f2`
- `ntdll!RtlCopySid` at `0x1800766df`
- `ntdll!RtlCopySid` at `0x1800763f2`
- `ntdll!RtlCopySid` at `0x1800766df`
- `ntdll!RtlValidSid` at `0x18007632a`
- `ntdll!RtlValidSid` at `0x180076476`
- `ntdll!RtlValidSid` at `0x18007668f`
- `ntdll!RtlValidSid` at `0x18007632a`
- `ntdll!RtlValidSid` at `0x180076476`
- `ntdll!RtlValidSid` at `0x18007668f`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertStringSidToSidA` at `0x1800763cf`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertStringSidToSidA` at `0x1800763cf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800766b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800766b9`

## string_xrefs

- `0x180076674`: `tag:microsoft.com,2022-09-14:sid:`

## pseudocode

```c
__int64 __fastcall KerbGetExtendedSanFromCert(__int64 a1, __int64 a2)
{
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  __int64 v7; // xmm0_8
  PCERT_EXTENSION Extension; // rax
  DWORD v9; // r9d
  const BYTE *v10; // r8
  _QWORD *v11; // rbx
  unsigned int v12; // r12d
  __int64 v13; // rax
  __int64 v14; // r15
  DWORD v15; // r9d
  const BYTE *v16; // r8
  CHAR *v17; // rax
  CHAR *v18; // r15
  BOOL v19; // ebx
  NTSTATUS v20; // eax
  PSID v21; // rcx
  PSID v22; // rcx
  __int128 v23; // xmm1
  PSID v24; // rcx
  PSID v25; // rcx
  void *v26; // rcx
  PCERT_EXTENSION v27; // rax
  DWORD cbData; // r9d
  const BYTE *pbData; // r8
  unsigned int v30; // r15d
  __int64 v31; // rax
  const wchar_t *v32; // r13
  BOOL v33; // ebx
  NTSTATUS v34; // eax
  PSID v35; // rcx
  PSID v36; // rcx
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int64 result; // rax
  _OWORD v40[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+80h] [rbp-80h]
  PSID *p_hMem; // [rsp+88h] [rbp-78h] BYREF
  PSID v43; // [rsp+90h] [rbp-70h] BYREF
  char v44; // [rsp+98h] [rbp-68h]
  struct _CRYPT_DECODE_PARA pDecodePara; // [rsp+A0h] [rbp-60h] BYREF
  __int128 Sid; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v47; // [rsp+D0h] [rbp-30h]
  __int128 v48; // [rsp+E0h] [rbp-20h]
  __int128 v49; // [rsp+F0h] [rbp-10h]
  __int64 v50; // [rsp+100h] [rbp+0h]
  DWORD pcbStructInfo; // [rsp+160h] [rbp+60h] BYREF
  void *pvStructInfo; // [rsp+168h] [rbp+68h] BYREF
  PSID hMem; // [rsp+170h] [rbp+70h] BYREF
  PSID SourceSid; // [rsp+178h] [rbp+78h] BYREF

  if ( !a2 )
  {
    LODWORD(Sid) = -1073741811;
    memset_0((char *)&Sid + 4, 0, 0x44u);
    v4 = v47;
    *(_OWORD *)a1 = Sid;
    v5 = v48;
    *(_OWORD *)(a1 + 16) = v4;
    v6 = v49;
LABEL_3:
    *(_OWORD *)(a1 + 32) = v5;
    v7 = v50;
    goto LABEL_81;
  }
  *(_QWORD *)&pDecodePara.cbSize = 24;
  pDecodePara.pfnAlloc = MIDL_user_allocate;
  pDecodePara.pfnFree = MIDL_user_free;
  memset_0(&Sid, 0, 0x48u);
  Extension = CertFindExtension(
                "1.3.6.1.4.1.311.25.2",
                *(_DWORD *)(*(_QWORD *)(a2 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(a2 + 24) + 200LL));
  if ( !Extension )
  {
    v27 = CertFindExtension(
            "2.5.29.17",
            *(_DWORD *)(*(_QWORD *)(a2 + 24) + 192LL),
            *(CERT_EXTENSION **)(*(_QWORD *)(a2 + 24) + 200LL));
    if ( !v27 )
    {
LABEL_26:
      if ( !RtlValidSid((char *)&Sid + 4) )
      {
        LODWORD(v40[0]) = -1073741275;
        memset_0((char *)v40 + 4, 0, 0x44u);
        goto LABEL_80;
      }
      v23 = v47;
      LODWORD(Sid) = 0;
      *(_OWORD *)a1 = Sid;
      v5 = v48;
      *(_OWORD *)(a1 + 16) = v23;
      v6 = v49;
      goto LABEL_3;
    }
    cbData = v27->Value.cbData;
    pbData = v27->Value.pbData;
    pvStructInfo = 0;
    pcbStructInfo = 0;
    if ( !CryptDecodeObjectEx(1u, (LPCSTR)0xC, pbData, cbData, 0x8000u, &pDecodePara, &pvStructInfo, &pcbStructInfo)
      || !pcbStructInfo )
    {
      goto LABEL_50;
    }
    v11 = pvStructInfo;
    v30 = 0;
    if ( *(_DWORD *)pvStructInfo )
    {
      do
      {
        v31 = v11[1];
        if ( *(_DWORD *)(v31 + 24LL * v30) == 7 )
        {
          v32 = *(const wchar_t **)(v31 + 24LL * v30 + 8);
          if ( !wcsncmp_0(L"tag:microsoft.com,2022-09-14:sid:", v32, 0x21u) )
          {
            if ( RtlValidSid((char *)&Sid + 4) )
            {
              if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids);
              }
              LODWORD(v40[0]) = -1073739509;
              memset_0((char *)v40 + 4, 0, 0x44u);
              v26 = pvStructInfo;
              pvStructInfo = 0;
              goto LABEL_35;
            }
            hMem = 0;
            p_hMem = &hMem;
            v43 = 0;
            v44 = 1;
            v33 = ConvertStringSidToSidW(v32 + 33, &v43);
            wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
            if ( !v33 )
            {
              if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids);
              }
              LODWORD(v40[0]) = -1073739509;
              goto LABEL_69;
            }
            v34 = RtlCopySid(0x44u, (char *)&Sid + 4, hMem);
            if ( v34 < 0 )
            {
              LODWORD(v40[0]) = v34;
LABEL_69:
              memset_0((char *)v40 + 4, 0, 0x44u);
              v36 = hMem;
              hMem = 0;
              if ( v36 )
                LocalFree(v36);
              goto LABEL_34;
            }
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 2));
            }
            v35 = hMem;
            hMem = 0;
            if ( v35 )
              LocalFree(v35);
            v11 = pvStructInfo;
          }
        }
        ++v30;
      }
      while ( v30 < *(_DWORD *)v11 );
    }
LABEL_24:
    pvStructInfo = 0;
    if ( v11 )
      MIDL_user_free(v11);
    goto LABEL_26;
  }
  v9 = Extension->Value.cbData;
  v10 = Extension->Value.pbData;
  pvStructInfo = 0;
  pcbStructInfo = 0;
  if ( !CryptDecodeObjectEx(1u, (LPCSTR)0xC, v10, v9, 0x8000u, &pDecodePara, &pvStructInfo, &pcbStructInfo)
    || !pcbStructInfo )
  {
    goto LABEL_50;
  }
  v11 = pvStructInfo;
  v12 = 0;
  if ( !*(_DWORD *)pvStructInfo )
    goto LABEL_24;
  while ( 1 )
  {
    v13 = v11[1];
    if ( *(_DWORD *)(v13 + 24LL * v12) != 1 )
      goto LABEL_23;
    v14 = *(_QWORD *)(v13 + 24LL * v12 + 8);
    if ( strcmp_0(*(const char **)v14, "1.3.6.1.4.1.311.25.2.1") )
      goto LABEL_23;
    if ( RtlValidSid((char *)&Sid + 4) )
      break;
    v15 = *(_DWORD *)(v14 + 8);
    v16 = *(const BYTE **)(v14 + 16);
    hMem = 0;
    if ( !CryptDecodeObjectEx(1u, (LPCSTR)0x19, v16, v15, 0x8000u, &pDecodePara, &hMem, &pcbStructInfo) )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids);
      LODWORD(v40[0]) = -1073739509;
      goto LABEL_42;
    }
    v17 = (CHAR *)MIDL_user_allocate(*(unsigned int *)hMem + 1LL);
    v18 = v17;
    if ( !v17 )
    {
      LODWORD(v40[0]) = -1073741670;
LABEL_42:
      memset_0((char *)v40 + 4, 0, 0x44u);
      goto LABEL_32;
    }
    memcpy_0(v17, *((const void **)hMem + 1), *(unsigned int *)hMem);
    p_hMem = &SourceSid;
    v43 = 0;
    v44 = 1;
    v18[*(unsigned int *)hMem] = 0;
    SourceSid = 0;
    v19 = ConvertStringSidToSidA(v18, &v43);
    wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
    if ( !v19 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids);
      LODWORD(v40[0]) = -1073739509;
LABEL_29:
      memset_0((char *)v40 + 4, 0, 0x44u);
      v24 = SourceSid;
      SourceSid = 0;
      if ( v24 )
        LocalFree(v24);
      MIDL_user_free(v18);
LABEL_32:
      v25 = hMem;
      hMem = 0;
      if ( v25 )
        MIDL_user_free(v25);
      goto LABEL_34;
    }
    v20 = RtlCopySid(0x44u, (char *)&Sid + 4, SourceSid);
    if ( v20 < 0 )
    {
      LODWORD(v40[0]) = v20;
      goto LABEL_29;
    }
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v21 = SourceSid;
    SourceSid = 0;
    if ( v21 )
      LocalFree(v21);
    MIDL_user_free(v18);
    v22 = hMem;
    hMem = 0;
    if ( v22 )
      MIDL_user_free(v22);
    v11 = pvStructInfo;
LABEL_23:
    if ( ++v12 >= *(_DWORD *)v11 )
      goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids);
LABEL_50:
  LODWORD(v40[0]) = -1073739509;
  memset_0((char *)v40 + 4, 0, 0x44u);
LABEL_34:
  v26 = pvStructInfo;
  pvStructInfo = 0;
LABEL_35:
  if ( v26 )
    MIDL_user_free(v26);
LABEL_80:
  v37 = v40[1];
  *(_OWORD *)a1 = v40[0];
  v38 = v40[2];
  *(_OWORD *)(a1 + 16) = v37;
  v6 = v40[3];
  *(_OWORD *)(a1 + 32) = v38;
  v7 = v41;
LABEL_81:
  *(_OWORD *)(a1 + 48) = v6;
  result = a1;
  *(_QWORD *)(a1 + 64) = v7;
  return result;
}

```

## disassembly

```asm
0x1800761d4  push    rbp
0x1800761d6  push    rbx
0x1800761d7  push    rsi
0x1800761d8  push    rdi
0x1800761d9  push    r12
0x1800761db  push    r13
0x1800761dd  push    r14
0x1800761df  push    r15
0x1800761e1  lea     rbp, [rsp-18h]
0x1800761e6  sub     rsp, 118h
0x1800761ed  xor     r13d, r13d
0x1800761f0  mov     rbx, rdx
0x1800761f3  mov     rdi, rcx
0x1800761f6  test    rdx, rdx
0x1800761f9  jnz     short loc_180076234
0x1800761fb  lea     r8d, [rdx+44h]; Size
0x1800761ff  mov     dword ptr [rbp+50h+Sid], 0C000000Dh
0x180076206  lea     rcx, [rbp+50h+Sid+4]; void *
0x18007620a  call    memset_0
0x18007620f  movups  xmm0, [rbp+50h+Sid]
0x180076213  movups  xmm1, [rbp+50h+var_80]
0x180076217  movups  xmmword ptr [rdi], xmm0
0x18007621a  movups  xmm0, [rbp+50h+var_70]
0x18007621e  movups  xmmword ptr [rdi+10h], xmm1
0x180076222  movups  xmm1, [rbp+50h+var_60]
0x180076226  movups  xmmword ptr [rdi+20h], xmm0
0x18007622a  movsd   xmm0, [rbp+50h+var_50]
0x18007622f  jmp     loc_180076820
0x180076234  xor     edx, edx; Val
0x180076236  mov     qword ptr [rbp+50h+var_B0.cbSize], 18h
0x18007623e  lea     rax, MIDL_user_allocate
0x180076245  mov     [rbp+50h+var_B0.pfnAlloc], rax
0x180076249  lea     rcx, [rbp+50h+Sid]; void *
0x18007624d  lea     rax, MIDL_user_free
0x180076254  lea     r8d, [rdx+48h]; Size
0x180076258  mov     [rbp+50h+var_B0.pfnFree], rax
0x18007625c  call    memset_0
0x180076261  mov     rdx, [rbx+18h]
0x180076265  lea     rcx, a136141311252; "1.3.6.1.4.1.311.25.2"
0x18007626c  mov     r8, [rdx+0C8h]; rgExtensions
0x180076273  mov     edx, [rdx+0C0h]; cExtensions
0x180076279  call    cs:__imp_CertFindExtension
0x18007627f  mov     esi, 44h ; 'D'
0x180076284  test    rax, rax
0x180076287  jz      loc_1800765C0
0x18007628d  mov     r9d, [rax+10h]; cbEncoded
0x180076291  lea     rcx, [rbp+50h+arg_0]
0x180076295  mov     r8, [rax+18h]; pbEncoded
0x180076299  lea     edx, [rsi-38h]; lpszStructType
0x18007629c  mov     [rsp+150h+pcbStructInfo], rcx; pcbStructInfo
0x1800762a1  lea     rcx, [rbp+50h+arg_8]
0x1800762a5  mov     [rsp+150h+pvStructInfo], rcx; pvStructInfo
0x1800762aa  lea     rcx, [rbp+50h+var_B0]
0x1800762ae  mov     [rsp+150h+pDecodePara], rcx; pDecodePara
0x1800762b3  lea     ecx, [rsi-43h]; dwCertEncodingType
0x1800762b6  mov     [rbp+50h+arg_8], r13
0x1800762ba  mov     [rbp+50h+arg_0], r13d
0x1800762be  mov     [rsp+150h+dwFlags], 8000h; dwFlags
0x1800762c6  call    cs:__imp_CryptDecodeObjectEx
0x1800762cc  test    eax, eax
0x1800762ce  jz      loc_1800765A4
0x1800762d4  cmp     [rbp+50h+arg_0], r13d
0x1800762d8  jz      loc_1800765A4
0x1800762de  mov     rbx, [rbp+50h+arg_8]
0x1800762e2  mov     r12d, r13d
0x1800762e5  cmp     [rbx], r13d
0x1800762e8  jbe     loc_180076461
0x1800762ee  lea     r14, WPP_GLOBAL_Control
0x1800762f5  mov     eax, r12d
0x1800762f8  lea     rcx, [rax+rax*2]
0x1800762fc  mov     rax, [rbx+8]
0x180076300  cmp     dword ptr [rax+rcx*8], 1
0x180076304  jnz     loc_180076455
0x18007630a  mov     r15, [rax+rcx*8+8]
0x18007630f  lea     rdx, a1361413112521; "1.3.6.1.4.1.311.25.2.1"
0x180076316  mov     rcx, [r15]; Str1
0x180076319  call    strcmp_0
0x18007631e  test    eax, eax
0x180076320  jnz     loc_180076455
0x180076326  lea     rcx, [rbp+50h+Sid+4]; Sid
0x18007632a  call    cs:__imp_RtlValidSid
0x180076330  test    al, al
0x180076332  jnz     loc_18007657D
0x180076338  mov     r9d, [r15+8]; cbEncoded
0x18007633c  lea     rax, [rbp+50h+arg_0]
0x180076340  mov     r8, [r15+10h]; pbEncoded
0x180076344  mov     edx, 19h; lpszStructType
0x180076349  mov     [rsp+150h+pcbStructInfo], rax; pcbStructInfo
0x18007634e  lea     rax, [rbp+50h+hMem]
0x180076352  mov     [rsp+150h+pvStructInfo], rax; pvStructInfo
0x180076357  lea     rax, [rbp+50h+var_B0]
0x18007635b  mov     [rsp+150h+pDecodePara], rax; pDecodePara
0x180076360  lea     ecx, [rdx-18h]; dwCertEncodingType
0x180076363  mov     [rsp+150h+dwFlags], 8000h; dwFlags
0x18007636b  mov     [rbp+50h+hMem], r13
0x18007636f  call    cs:__imp_CryptDecodeObjectEx
0x180076375  test    eax, eax
0x180076377  jz      loc_18007654C
0x18007637d  mov     rax, [rbp+50h+hMem]
0x180076381  mov     ecx, [rax]
0x180076383  inc     rcx; size
0x180076386  call    MIDL_user_allocate
0x18007638b  mov     r15, rax
0x18007638e  test    rax, rax
0x180076391  jz      loc_180076533
0x180076397  mov     rdx, [rbp+50h+hMem]
0x18007639b  mov     rcx, rax; void *
0x18007639e  mov     r8d, [rdx]; Size
0x1800763a1  mov     rdx, [rdx+8]; Src
0x1800763a5  call    memcpy_0
0x1800763aa  mov     rcx, [rbp+50h+hMem]
0x1800763ae  lea     rax, [rbp+50h+SourceSid]
0x1800763b2  mov     [rbp+50h+var_C8], rax
0x1800763b6  mov     [rbp+50h+var_C0], r13
0x1800763ba  mov     [rbp+50h+var_B8], 1
0x1800763be  mov     edx, [rcx]
0x1800763c0  mov     rcx, r15; StringSid
0x1800763c3  mov     [rdx+r15], r13b
0x1800763c7  lea     rdx, [rbp+50h+var_C0]; Sid
0x1800763cb  mov     [rbp+50h+SourceSid], r13
0x1800763cf  call    cs:__imp_ConvertStringSidToSidA
0x1800763d5  lea     rcx, [rbp+50h+var_C8]
0x1800763d9  mov     ebx, eax
0x1800763db  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@U_SID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800763e0  test    ebx, ebx
0x1800763e2  jz      loc_1800764FF
0x1800763e8  mov     r8, [rbp+50h+SourceSid]; SourceSid
0x1800763ec  lea     rdx, [rbp+50h+Sid+4]; DestinationSid
0x1800763f0  mov     ecx, esi; DestinationSidLength
0x1800763f2  call    cs:__imp_RtlCopySid
0x1800763f8  test    eax, eax
0x1800763fa  js      loc_1800764A4
0x180076400  mov     rcx, cs:WPP_GLOBAL_Control
0x180076407  cmp     rcx, r14
0x18007640a  jz      short loc_180076424
0x18007640c  test    byte ptr [rcx+1Ch], 4
0x180076410  jz      short loc_180076424
0x180076412  mov     rcx, [rcx+10h]; LoggerHandle
0x180076416  lea     r9, [rbp+50h+Sid+4]
0x18007641a  mov     edx, 1Ah
0x18007641f  call    WPP_SF__sid_
0x180076424  mov     rcx, [rbp+50h+SourceSid]; hMem
0x180076428  mov     [rbp+50h+SourceSid], r13
0x18007642c  test    rcx, rcx
0x18007642f  jz      short loc_180076437
0x180076431  call    cs:__imp_LocalFree
0x180076437  mov     rcx, r15; void *
0x18007643a  call    MIDL_user_free
0x18007643f  mov     rcx, [rbp+50h+hMem]; void *
0x180076443  mov     [rbp+50h+hMem], r13
0x180076447  test    rcx, rcx
0x18007644a  jz      short loc_180076451
0x18007644c  call    MIDL_user_free
0x180076451  mov     rbx, [rbp+50h+arg_8]
0x180076455  inc     r12d
0x180076458  cmp     r12d, [rbx]
0x18007645b  jb      loc_1800762F5
0x180076461  mov     [rbp+50h+arg_8], r13
0x180076465  test    rbx, rbx
0x180076468  jz      short loc_180076472
0x18007646a  mov     rcx, rbx; void *
0x18007646d  call    MIDL_user_free
0x180076472  lea     rcx, [rbp+50h+Sid+4]; Sid
0x180076476  call    cs:__imp_RtlValidSid
0x18007647c  test    al, al
0x18007647e  jz      loc_1800767E5
0x180076484  movaps  xmm1, [rbp+50h+var_80]
0x180076488  mov     dword ptr [rbp+50h+Sid], r13d
0x18007648c  movaps  xmm0, [rbp+50h+Sid]
0x180076490  movups  xmmword ptr [rdi], xmm0
0x180076493  movaps  xmm0, [rbp+50h+var_70]
0x180076497  movups  xmmword ptr [rdi+10h], xmm1
0x18007649b  movaps  xmm1, [rbp+50h+var_60]
0x18007649f  jmp     loc_180076226
0x1800764a4  mov     dword ptr [rsp+150h+var_110], eax
0x1800764a8  mov     r8, rsi; Size
0x1800764ab  lea     rcx, [rsp+150h+var_110+4]; void *
0x1800764b0  xor     edx, edx; Val
0x1800764b2  call    memset_0
0x1800764b7  mov     rcx, [rbp+50h+SourceSid]; hMem
0x1800764bb  mov     [rbp+50h+SourceSid], r13
0x1800764bf  test    rcx, rcx
0x1800764c2  jz      short loc_1800764CA
0x1800764c4  call    cs:__imp_LocalFree
0x1800764ca  mov     rcx, r15; void *
0x1800764cd  call    MIDL_user_free
0x1800764d2  mov     rcx, [rbp+50h+hMem]; void *
0x1800764d6  mov     [rbp+50h+hMem], r13
0x1800764da  test    rcx, rcx
0x1800764dd  jz      short loc_1800764E4
0x1800764df  call    MIDL_user_free
0x1800764e4  mov     rcx, [rbp+50h+arg_8]; void *
0x1800764e8  mov     [rbp+50h+arg_8], r13
0x1800764ec  test    rcx, rcx
0x1800764ef  jz      loc_1800767FC
0x1800764f5  call    MIDL_user_free
0x1800764fa  jmp     loc_1800767FC
0x1800764ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180076506  cmp     rcx, r14
0x180076509  jz      short loc_180076526
0x18007650b  test    byte ptr [rcx+1Ch], 1
0x18007650f  jz      short loc_180076526
0x180076511  mov     rcx, [rcx+10h]
0x180076515  lea     r8, WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids
0x18007651c  mov     edx, 19h
0x180076521  call    WPP_SF_
0x180076526  mov     dword ptr [rsp+150h+var_110], 0C000090Bh
0x18007652e  jmp     loc_1800764A8
0x180076533  mov     dword ptr [rsp+150h+var_110], 0C000009Ah
0x18007653b  mov     r8, rsi; Size
0x18007653e  lea     rcx, [rsp+150h+var_110+4]; void *
0x180076543  xor     edx, edx; Val
0x180076545  call    memset_0
0x18007654a  jmp     short loc_1800764D2
0x18007654c  mov     rcx, cs:WPP_GLOBAL_Control
0x180076553  cmp     rcx, r14
0x180076556  jz      short loc_180076573
0x180076558  test    byte ptr [rcx+1Ch], 1
0x18007655c  jz      short loc_180076573
0x18007655e  mov     rcx, [rcx+10h]
0x180076562  lea     r8, WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids
0x180076569  mov     edx, 18h
0x18007656e  call    WPP_SF_
0x180076573  mov     dword ptr [rsp+150h+var_110], 0C000090Bh
0x18007657b  jmp     short loc_18007653B
0x18007657d  mov     rcx, cs:WPP_GLOBAL_Control
0x180076584  cmp     rcx, r14
0x180076587  jz      short loc_1800765A4
0x180076589  test    byte ptr [rcx+1Ch], 1
0x18007658d  jz      short loc_1800765A4
0x18007658f  mov     rcx, [rcx+10h]
0x180076593  lea     r8, WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids
0x18007659a  mov     edx, 17h
0x18007659f  call    WPP_SF_
0x1800765a4  mov     r8, rsi; Size
0x1800765a7  mov     dword ptr [rsp+150h+var_110], 0C000090Bh
0x1800765af  xor     edx, edx; Val
0x1800765b1  lea     rcx, [rsp+150h+var_110+4]; void *
0x1800765b6  call    memset_0
0x1800765bb  jmp     loc_1800764E4
0x1800765c0  mov     rdx, [rbx+18h]
0x1800765c4  lea     rcx, a252917; "2.5.29.17"
0x1800765cb  mov     r8, [rdx+0C8h]; rgExtensions
0x1800765d2  mov     edx, [rdx+0C0h]; cExtensions
0x1800765d8  call    cs:__imp_CertFindExtension
0x1800765de  test    rax, rax
0x1800765e1  jz      loc_180076472
0x1800765e7  mov     r9d, [rax+10h]; cbEncoded
0x1800765eb  lea     rcx, [rbp+50h+arg_0]
0x1800765ef  mov     r8, [rax+18h]; pbEncoded
0x1800765f3  mov     edx, 0Ch; lpszStructType
0x1800765f8  mov     [rsp+150h+pcbStructInfo], rcx; pcbStructInfo
0x1800765fd  lea     rcx, [rbp+50h+arg_8]
0x180076601  mov     [rsp+150h+pvStructInfo], rcx; pvStructInfo
0x180076606  lea     rcx, [rbp+50h+var_B0]
0x18007660a  mov     [rsp+150h+pDecodePara], rcx; pDecodePara
0x18007660f  lea     ecx, [rdx-0Bh]; dwCertEncodingType
0x180076612  mov     [rbp+50h+arg_8], r13
0x180076616  mov     [rbp+50h+arg_0], r13d
0x18007661a  mov     [rsp+150h+dwFlags], 8000h; dwFlags
0x180076622  call    cs:__imp_CryptDecodeObjectEx
0x180076628  test    eax, eax
0x18007662a  jz      loc_1800765A4
0x180076630  cmp     [rbp+50h+arg_0], r13d
0x180076634  jz      loc_1800765A4
0x18007663a  mov     rbx, [rbp+50h+arg_8]
0x18007663e  mov     r15d, r13d
0x180076641  cmp     [rbx], r13d
0x180076644  jbe     loc_180076461
0x18007664a  lea     r14, WPP_GLOBAL_Control
0x180076651  mov     eax, r15d
0x180076654  lea     rcx, [rax+rax*2]
0x180076658  mov     rax, [rbx+8]
0x18007665c  cmp     dword ptr [rax+rcx*8], 7
0x180076660  jnz     loc_180076729
0x180076666  mov     r13, [rax+rcx*8+8]
0x18007666b  mov     r8d, 21h ; '!'; MaxCount
0x180076671  mov     rdx, r13; String2
0x180076674  lea     rcx, aTagMicrosoftCo; "tag:microsoft.com,2022-09-14:sid:"
0x18007667b  call    wcsncmp_0
0x180076680  xor     r12d, r12d
0x180076683  test    eax, eax
0x180076685  jnz     loc_180076726
0x18007668b  lea     rcx, [rbp+50h+Sid+4]; Sid
0x18007668f  call    cs:__imp_RtlValidSid
0x180076695  test    al, al
0x180076697  jnz     loc_18007679A
0x18007669d  lea     rax, [rbp+50h+hMem]
0x1800766a1  mov     [rbp+50h+hMem], r12
0x1800766a5  lea     rcx, [r13+42h]; StringSid
0x1800766a9  mov     [rbp+50h+var_C8], rax
0x1800766ad  lea     rdx, [rbp+50h+var_C0]; Sid
0x1800766b1  mov     [rbp+50h+var_C0], r12
0x1800766b5  mov     [rbp+50h+var_B8], 1
0x1800766b9  call    cs:__imp_ConvertStringSidToSidW
0x1800766bf  lea     rcx, [rbp+50h+var_C8]
0x1800766c3  mov     ebx, eax
0x1800766c5  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@U_SID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800766ca  xor     r13d, r13d
0x1800766cd  test    ebx, ebx
  ... truncated ...
```
