# CEnumQueryMetadataReader::Next(ulong,ushort * *,ulong *)

- ea: `0x180062bf0`
- end: `0x1800631a7`
- name: `?Next@CEnumQueryMetadataReader@@UEAAJKPEAPEAGPEAK@Z`
- size: `1463`
- prototype: `int(CEnumQueryMetadataReader *__hidden this, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x180025d9c`
- `0x18002ae60`
- `0x1800319d0`
- `0x1800319f0`
- `0x18003573c`
- `0x180037a04`
- `0x180037b8c`
- `0x180038fe0`
- `0x18003906c`
- `0x180061564`
- `0x180062bf0`
- `0x1800631b0`
- `0x1800631f0`
- `0x1800bd9d4`
- `0x1800e5e60`
- `0x1800e6af4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180062e2a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180062e44`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180062e2a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180062e44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180062f60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180062f60`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180062dd3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180062de3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180062dd3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180062de3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063189`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063189`

## pseudocode

```c
__int64 __fastcall CEnumQueryMetadataReader::Next(
        CEnumQueryMetadataReader *this,
        unsigned int a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  unsigned int v4; // r12d
  CMTALock *v8; // rbx
  char *v9; // r14
  char *v10; // r15
  int v11; // eax
  int NameGuidMappingInfo; // esi
  unsigned int i; // r8d
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned int j; // r13d
  struct tagPROPVARIANT *v18; // rdx
  int v19; // edi
  unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rsi
  unsigned __int16 *v24; // rax
  bool v25; // zf
  int v26; // ecx
  int v27; // eax
  int v28; // ecx
  unsigned __int16 *bstrVal; // rdi
  int v30; // eax
  unsigned __int64 v31; // r8
  unsigned int v32; // edi
  unsigned __int16 **v33; // rbx
  unsigned __int16 *v34; // rcx
  unsigned int v35; // [rsp+40h] [rbp-C0h] BYREF
  int v36; // [rsp+44h] [rbp-BCh]
  CMILCOMBase *v37; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v38; // [rsp+50h] [rbp-B0h] BYREF
  CEnumQueryMetadataReader *v39; // [rsp+58h] [rbp-A8h]
  unsigned __int16 **v40; // [rsp+60h] [rbp-A0h]
  CEnumQueryMetadataReader *v41; // [rsp+68h] [rbp-98h]
  unsigned int *v42; // [rsp+70h] [rbp-90h]
  CMTALock *v43; // [rsp+78h] [rbp-88h]
  void *Block; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v45; // [rsp+88h] [rbp-78h]
  int v46; // [rsp+90h] [rbp-70h]
  __int64 v47; // [rsp+94h] [rbp-6Ch]
  _BYTE v48[24]; // [rsp+A0h] [rbp-60h] BYREF
  void *v49; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE *v50; // [rsp+C0h] [rbp-40h]
  int v51; // [rsp+C8h] [rbp-38h]
  __int64 v52; // [rsp+CCh] [rbp-34h]
  _BYTE v53[24]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 v54[128]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v55[128]; // [rsp+1F0h] [rbp+F0h] BYREF

  v4 = 0;
  v41 = this;
  v42 = a4;
  v40 = a3;
  v49 = v53;
  v51 = 1;
  v50 = v53;
  v8 = (CEnumQueryMetadataReader *)((char *)this - 56);
  v52 = 1;
  Block = v48;
  v9 = 0;
  v46 = 1;
  v47 = 1;
  v10 = 0;
  v45 = v48;
  v35 = 0;
  v37 = 0;
  v36 = 0;
  v43 = (CEnumQueryMetadataReader *)((char *)this - 56);
  CMTALock::Enter((CEnumQueryMetadataReader *)((char *)this - 56));
  if ( !a3 )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147024809);
    NameGuidMappingInfo = -2147024809;
    goto LABEL_13;
  }
  memset_0(a3, 0, 8LL * a2);
  v39 = (CEnumQueryMetadataReader *)((char *)this - 72);
  v11 = CEnumQueryMetadataReader::EnsureInitialized((CEnumQueryMetadataReader *)((char *)this - 72));
  NameGuidMappingInfo = v11;
  if ( v11 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_13;
LABEL_50:
    v26 = v11;
LABEL_43:
    DoStackCapture(v26);
    goto LABEL_13;
  }
  NameGuidMappingInfo = DynArrayImpl<0>::Grow((unsigned int)&v49, 24, a2, 0, 0);
  if ( NameGuidMappingInfo < 0
    || (v9 = (char *)v49 + (unsigned int)(24 * HIDWORD(v52)),
        HIDWORD(v52) += a2,
        NameGuidMappingInfo = DynArrayImpl<0>::Grow((unsigned int)&Block, 24, a2, 0, 0),
        NameGuidMappingInfo < 0) )
  {
    if ( (_DWORD)g_doStackCaptures )
    {
      DoStackCapture(NameGuidMappingInfo);
      v25 = (_DWORD)g_doStackCaptures == 0;
      goto LABEL_41;
    }
    goto LABEL_13;
  }
  v10 = (char *)Block + (unsigned int)(24 * HIDWORD(v47));
  HIDWORD(v47) += a2;
  for ( i = 0; i < a2; *(_QWORD *)&v10[8 * v15 + 16] = 0 )
  {
    v14 = i++;
    v15 = 3 * v14;
    *(_OWORD *)&v9[8 * v15] = 0;
    *(_QWORD *)&v9[8 * v15 + 16] = 0;
    *(_OWORD *)&v10[8 * v15] = 0;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, char *, _QWORD, unsigned int *))(**((_QWORD **)this + 4)
                                                                                          + 24LL))(
          *((_QWORD *)this + 4),
          a2,
          v9,
          v10,
          0,
          &v35);
  NameGuidMappingInfo = v11;
  if ( v11 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_13;
    goto LABEL_50;
  }
  v36 = 1;
  for ( j = 0; ; ++j )
  {
    if ( j >= v35 )
    {
      if ( v42 )
        *v42 = v35;
      goto LABEL_12;
    }
    v18 = (struct tagPROPVARIANT *)&v9[24 * j];
    if ( v18->vt == 31 )
    {
      bstrVal = v18->bstrVal;
      v38 = bstrVal;
      NameGuidMappingInfo = CCodecFactory::GetNameGuidMappingInfo(&v37);
      if ( NameGuidMappingInfo < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_12;
        v28 = NameGuidMappingInfo;
        goto LABEL_66;
      }
      v30 = CMappingInfo::MapSchemaToSchemaName(
              v37,
              (const struct _GUID *)((char *)v41 + 8),
              bstrVal,
              (const unsigned __int16 **)&v38);
      NameGuidMappingInfo = 0;
      if ( v30 != -2003292352 )
        NameGuidMappingInfo = v30;
      if ( NameGuidMappingInfo < 0 )
      {
        v4 = 0;
        goto LABEL_80;
      }
      v27 = ConvertToEscapedString(v38, v55, v31);
    }
    else
    {
      if ( !v18->vt )
      {
        *(_DWORD *)v54 = 47;
        goto LABEL_28;
      }
      v27 = CEnumQueryMetadataReader::ConvertPropVariantToString(v39, v18, v55, 0x80u);
    }
    NameGuidMappingInfo = v27;
    if ( v27 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_12;
LABEL_65:
      v28 = v27;
LABEL_66:
      DoStackCapture(v28);
LABEL_12:
      v4 = 0;
      goto LABEL_13;
    }
    v27 = StringCchPrintfW(v54, 0x80u, L"/%s:", v55);
    NameGuidMappingInfo = v27;
    if ( v27 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_12;
      goto LABEL_65;
    }
LABEL_28:
    v11 = CEnumQueryMetadataReader::ConvertPropVariantToString(v39, (struct tagPROPVARIANT *)&v10[24 * j], v55, 0x80u);
    v19 = (int)g_doStackCaptures;
    v4 = 0;
    NameGuidMappingInfo = v11;
    if ( v11 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_13;
      goto LABEL_50;
    }
    v11 = StringCchCatW(v54, 0x80u, v55);
    NameGuidMappingInfo = v11;
    if ( v11 < 0 )
    {
      if ( !v19 )
        goto LABEL_13;
      goto LABEL_50;
    }
    v20 = v54;
    v21 = 0x7FFFFFFF;
    do
    {
      if ( !*v20 )
        break;
      ++v20;
      --v21;
    }
    while ( v21 );
    NameGuidMappingInfo = v21 == 0 ? 0x80070057 : 0;
    if ( !v21 && v19 )
      goto LABEL_42;
    v22 = (0x7FFFFFFF - v21) & -(__int64)(v21 != 0);
    if ( !v21 )
      goto LABEL_13;
    v23 = v22 + 1;
    if ( v22 + 1 < v22 || (v38 = 0, !is_mul_ok(v23, 2u)) )
    {
      NameGuidMappingInfo = -2147024362;
      v25 = v19 == 0;
      goto LABEL_41;
    }
    v24 = (unsigned __int16 *)CoTaskMemAlloc(2 * v23);
    v40[j] = v24;
    if ( !v24 )
      break;
    v11 = StringCchCopyW(v24, v23, v54);
    NameGuidMappingInfo = v11;
    if ( v11 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_13;
      goto LABEL_50;
    }
  }
  NameGuidMappingInfo = -2147024882;
LABEL_80:
  v25 = (_DWORD)g_doStackCaptures == 0;
LABEL_41:
  if ( !v25 )
  {
LABEL_42:
    v26 = NameGuidMappingInfo;
    goto LABEL_43;
  }
LABEL_13:
  if ( v35 )
  {
    do
    {
      PropVariantClear((PROPVARIANT *)&v9[24 * v4]);
      PropVariantClear((PROPVARIANT *)&v10[24 * v4++]);
    }
    while ( v4 < v35 );
  }
  if ( NameGuidMappingInfo < 0 )
  {
    if ( v36 )
    {
      v32 = 0;
      if ( v35 )
      {
        v33 = v40;
        do
        {
          v34 = v33[v32];
          if ( v34 )
            CoTaskMemFree(v34);
          ++v32;
        }
        while ( v32 < v35 );
        v8 = v43;
      }
    }
  }
  if ( v37 )
    CMILCOMBase::InternalRelease(v37);
  if ( v8 )
    CMTALock::Leave(v8);
  if ( Block != v45 )
  {
    free(Block);
    Block = 0;
  }
  if ( v49 != v50 )
    free(v49);
  return (unsigned int)NameGuidMappingInfo;
}

```

## disassembly

```asm
0x180062bf0  push    rbp
0x180062bf2  push    rbx
0x180062bf3  push    rsi
0x180062bf4  push    rdi
0x180062bf5  push    r12
0x180062bf7  push    r13
0x180062bf9  push    r14
0x180062bfb  push    r15
0x180062bfd  lea     rbp, [rsp-208h]
0x180062c05  sub     rsp, 308h
0x180062c0c  mov     rax, cs:__security_cookie
0x180062c13  xor     rax, rsp
0x180062c16  mov     [rbp+240h+var_50], rax
0x180062c1d  xor     r12d, r12d
0x180062c20  mov     [rsp+340h+var_2D8], rcx
0x180062c25  mov     r13, rcx
0x180062c28  mov     [rsp+340h+var_2D0], r9
0x180062c2d  lea     rax, [rbp+240h+var_268]
0x180062c31  mov     [rsp+340h+var_2E0], r8
0x180062c36  mov     [rbp+240h+var_288], rax
0x180062c3a  mov     rsi, r8
0x180062c3d  lea     ecx, [r12+1]
0x180062c42  mov     edi, edx
0x180062c44  lea     rax, [rbp+240h+var_268]
0x180062c48  mov     [rbp+240h+var_278], ecx
0x180062c4b  mov     [rbp+240h+var_280], rax
0x180062c4f  lea     rbx, [r13-38h]
0x180062c53  lea     rax, [rbp+240h+var_2A0]
0x180062c57  mov     [rbp+240h+var_274], rcx
0x180062c5b  mov     [rbp+240h+Block], rax
0x180062c5f  mov     r14d, r12d
0x180062c62  lea     rax, [rbp+240h+var_2A0]
0x180062c66  mov     [rbp+240h+var_2B0], ecx
0x180062c69  mov     [rbp+240h+var_2AC], rcx
0x180062c6d  mov     r15d, r12d
0x180062c70  mov     rcx, rbx; this
0x180062c73  mov     [rbp+240h+var_2B8], rax
0x180062c77  mov     [rsp+340h+var_300], r12d
0x180062c7c  mov     [rsp+340h+var_2F8], r12
0x180062c81  mov     [rsp+340h+var_2FC], r12d
0x180062c86  mov     [rsp+340h+var_2C8], rbx
0x180062c8b  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180062c90  test    rsi, rsi
0x180062c93  jz      loc_180062FBB
0x180062c99  mov     r8d, edi
0x180062c9c  xor     edx, edx; Val
0x180062c9e  shl     r8, 3; Size
0x180062ca2  mov     rcx, rsi; void *
0x180062ca5  call    memset_0
0x180062caa  lea     rax, [r13-48h]
0x180062cae  mov     rcx, rax; this
0x180062cb1  mov     [rsp+340h+var_2E8], rax
0x180062cb6  call    ?EnsureInitialized@CEnumQueryMetadataReader@@MEAAJXZ; CEnumQueryMetadataReader::EnsureInitialized(void)
0x180062cbb  mov     esi, eax
0x180062cbd  test    eax, eax
0x180062cbf  js      loc_180062FF7
0x180062cc5  xor     r9d, r9d
0x180062cc8  mov     [rsp+340h+var_320], r12
0x180062ccd  mov     r8d, edi
0x180062cd0  lea     edx, [r12+18h]
0x180062cd5  lea     rcx, [rbp+240h+var_288]
0x180062cd9  call    ?Grow@?$DynArrayImpl@$0A@@@IEAAJIIHPEAPEBX@Z; DynArrayImpl<0>::Grow(uint,uint,int,void const * *)
0x180062cde  mov     esi, eax
0x180062ce0  test    eax, eax
0x180062ce2  js      loc_180062FD8
0x180062ce8  mov     ecx, dword ptr [rbp+240h+var_274+4]
0x180062ceb  lea     r14d, [rcx+rcx*2]
0x180062cef  shl     r14d, 3
0x180062cf3  add     r14, [rbp+240h+var_288]
0x180062cf7  add     ecx, edi
0x180062cf9  mov     dword ptr [rbp+240h+var_274+4], ecx
0x180062cfc  xor     r9d, r9d
0x180062cff  mov     [rsp+340h+var_320], r12
0x180062d04  mov     r8d, edi
0x180062d07  lea     edx, [r12+18h]
0x180062d0c  lea     rcx, [rbp+240h+Block]
0x180062d10  call    ?Grow@?$DynArrayImpl@$0A@@@IEAAJIIHPEAPEBX@Z; DynArrayImpl<0>::Grow(uint,uint,int,void const * *)
0x180062d15  mov     esi, eax
0x180062d17  test    eax, eax
0x180062d19  js      loc_180062FD8
0x180062d1f  mov     ecx, dword ptr [rbp+240h+var_2AC+4]
0x180062d22  lea     r15d, [rcx+rcx*2]
0x180062d26  shl     r15d, 3
0x180062d2a  add     r15, [rbp+240h+Block]
0x180062d2e  add     ecx, edi
0x180062d30  mov     dword ptr [rbp+240h+var_2AC+4], ecx
0x180062d33  mov     r8d, r12d
0x180062d36  test    edi, edi
0x180062d38  jz      short loc_180062D62
0x180062d3a  mov     eax, r8d
0x180062d3d  xorps   xmm0, xmm0
0x180062d40  inc     r8d
0x180062d43  lea     rcx, [rax+rax*2]
0x180062d47  xor     eax, eax
0x180062d49  movups  xmmword ptr [r14+rcx*8], xmm0
0x180062d4e  mov     [r14+rcx*8+10h], rax
0x180062d53  movups  xmmword ptr [r15+rcx*8], xmm0
0x180062d58  mov     [r15+rcx*8+10h], rax
0x180062d5d  cmp     r8d, edi
0x180062d60  jb      short loc_180062D3A
0x180062d62  mov     rcx, [r13+20h]
0x180062d66  lea     r8, [rsp+340h+var_300]
0x180062d6b  mov     [rsp+340h+var_318], r8
0x180062d70  mov     r9, r15
0x180062d73  mov     r8, r14
0x180062d76  mov     [rsp+340h+var_320], r12
0x180062d7b  mov     edx, edi
0x180062d7d  mov     rax, [rcx]
0x180062d80  mov     rax, [rax+18h]
0x180062d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d89  mov     esi, eax
0x180062d8b  test    eax, eax
0x180062d8d  js      loc_180063008
0x180062d93  mov     [rsp+340h+var_2FC], 1
0x180062d9b  mov     r13d, r12d
0x180062d9e  cmp     r13d, [rsp+340h+var_300]
0x180062da3  jb      loc_180062E76
0x180062da9  mov     r12, [rsp+340h+var_2D0]
0x180062dae  test    r12, r12
0x180062db1  jz      short loc_180062DBB
0x180062db3  mov     eax, [rsp+340h+var_300]
0x180062db7  mov     [r12], eax
0x180062dbb  xor     r12d, r12d
0x180062dbe  xor     r13d, r13d
0x180062dc1  cmp     [rsp+340h+var_300], r13d
0x180062dc6  jbe     short loc_180062DF9
0x180062dc8  mov     eax, r12d
0x180062dcb  lea     rdi, [rax+rax*2]
0x180062dcf  lea     rcx, [r14+rdi*8]; pvar
0x180062dd3  call    cs:__imp_PropVariantClear
0x180062dda  nop     dword ptr [rax+rax+00h]
0x180062ddf  lea     rcx, [r15+rdi*8]; pvar
0x180062de3  call    cs:__imp_PropVariantClear
0x180062dea  nop     dword ptr [rax+rax+00h]
0x180062def  inc     r12d
0x180062df2  cmp     r12d, [rsp+340h+var_300]
0x180062df7  jb      short loc_180062DC8
0x180062df9  test    esi, esi
0x180062dfb  js      loc_180063160
0x180062e01  mov     rax, [rsp+340h+var_2F8]
0x180062e06  test    rax, rax
0x180062e09  jz      short loc_180062E13
0x180062e0b  mov     rcx, rax; this
0x180062e0e  call    ?InternalRelease@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalRelease(void)
0x180062e13  test    rbx, rbx
0x180062e16  jz      short loc_180062E20
0x180062e18  mov     rcx, rbx; this
0x180062e1b  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x180062e20  mov     rcx, [rbp+240h+Block]; Block
0x180062e24  cmp     rcx, [rbp+240h+var_2B8]
0x180062e28  jz      short loc_180062E3A
0x180062e2a  call    cs:__imp_free
0x180062e31  nop     dword ptr [rax+rax+00h]
0x180062e36  mov     [rbp+240h+Block], r13
0x180062e3a  mov     rcx, [rbp+240h+var_288]; Block
0x180062e3e  cmp     rcx, [rbp+240h+var_280]
0x180062e42  jz      short loc_180062E50
0x180062e44  call    cs:__imp_free
0x180062e4b  nop     dword ptr [rax+rax+00h]
0x180062e50  mov     eax, esi
0x180062e52  mov     rcx, [rbp+240h+var_50]
0x180062e59  xor     rcx, rsp; StackCookie
0x180062e5c  call    __security_check_cookie
0x180062e61  add     rsp, 308h
0x180062e68  pop     r15
0x180062e6a  pop     r14
0x180062e6c  pop     r13
0x180062e6e  pop     r12
0x180062e70  pop     rdi
0x180062e71  pop     rsi
0x180062e72  pop     rbx
0x180062e73  pop     rbp
0x180062e74  retn
0x180062e76  mov     eax, r13d
0x180062e79  lea     r12, [rax+rax*2]
0x180062e7d  lea     rdx, [r14+r12*8]; struct tagPROPVARIANT *
0x180062e81  cmp     word ptr [rdx], 1Fh
0x180062e85  jz      loc_1800630D8
0x180062e8b  xor     edi, edi
0x180062e8d  cmp     [rdx], di
0x180062e90  jnz     loc_180063056
0x180062e96  mov     dword ptr [rbp+240h+var_250], 2Fh ; '/'
0x180062e9d  mov     rcx, [rsp+340h+var_2E8]; this
0x180062ea2  lea     rdx, [r15+r12*8]; struct tagPROPVARIANT *
0x180062ea6  mov     r9d, 80h; unsigned int
0x180062eac  lea     r8, [rbp+240h+var_150]; unsigned __int16 *
0x180062eb3  call    ?ConvertPropVariantToString@CEnumQueryMetadataReader@@MEAAJPEAUtagPROPVARIANT@@PEAGI@Z; CEnumQueryMetadataReader::ConvertPropVariantToString(tagPROPVARIANT *,ushort *,uint)
0x180062eb8  mov     edi, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180062ebe  xor     r12d, r12d
0x180062ec1  mov     esi, eax
0x180062ec3  test    eax, eax
0x180062ec5  js      loc_18006301E
0x180062ecb  lea     r8, [rbp+240h+var_150]; unsigned __int16 *
0x180062ed2  mov     edx, 80h; unsigned __int64
0x180062ed7  lea     rcx, [rbp+240h+var_250]; unsigned __int16 *
0x180062edb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180062ee0  mov     esi, eax
0x180062ee2  test    eax, eax
0x180062ee4  js      loc_18006302F
0x180062eea  mov     ecx, 7FFFFFFFh
0x180062eef  lea     rax, [rbp+240h+var_250]
0x180062ef3  mov     edx, ecx
0x180062ef5  cmp     [rax], r12w
0x180062ef9  jz      short loc_180062F05
0x180062efb  add     rax, 2
0x180062eff  sub     rdx, 1
0x180062f03  jnz     short loc_180062EF5
0x180062f05  mov     rax, rdx
0x180062f08  neg     rax
0x180062f0b  mov     rax, rdx
0x180062f0e  sbb     esi, esi
0x180062f10  sub     rcx, rdx
0x180062f13  not     esi
0x180062f15  and     esi, 80070057h
0x180062f1b  neg     rax
0x180062f1e  sbb     r8, r8
0x180062f21  and     r8, rcx
0x180062f24  test    rdx, rdx
0x180062f27  jz      loc_1800630CB
0x180062f2d  mov     rax, rdx
0x180062f30  neg     rax
0x180062f33  sbb     rcx, rcx
0x180062f36  and     rcx, r8
0x180062f39  test    rdx, rdx
0x180062f3c  jz      loc_180062DBE
0x180062f42  lea     rsi, [rcx+1]
0x180062f46  cmp     rsi, rcx
0x180062f49  jb      short loc_180062FA2
0x180062f4b  mov     eax, 2
0x180062f50  mov     [rsp+340h+var_2F0], r12
0x180062f55  mul     rsi
0x180062f58  test    rdx, rdx
0x180062f5b  jnz     short loc_180062FA2
0x180062f5d  mov     rcx, rax; cb
0x180062f60  call    cs:__imp_CoTaskMemAlloc
0x180062f67  nop     dword ptr [rax+rax+00h]
0x180062f6c  mov     rdx, [rsp+340h+var_2E0]
0x180062f71  mov     ecx, r13d
0x180062f74  mov     [rdx+rcx*8], rax
0x180062f78  test    rax, rax
0x180062f7b  jz      loc_18006314F
0x180062f81  lea     r8, [rbp+240h+var_250]; unsigned __int16 *
0x180062f85  mov     rdx, rsi; unsigned __int64
0x180062f88  mov     rcx, rax; unsigned __int16 *
0x180062f8b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180062f90  mov     esi, eax
0x180062f92  test    eax, eax
0x180062f94  js      loc_180063040
0x180062f9a  inc     r13d
0x180062f9d  jmp     loc_180062D9E
0x180062fa2  mov     esi, 80070216h
0x180062fa7  test    edi, edi
0x180062fa9  jz      loc_180062DBE
0x180062faf  mov     ecx, esi; int
0x180062fb1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180062fb6  jmp     loc_180062DBE
0x180062fbb  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180062fc2  jz      short loc_180062FCE
0x180062fc4  mov     ecx, 80070057h; int
0x180062fc9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180062fce  mov     esi, 80070057h
0x180062fd3  jmp     loc_180062DBE
0x180062fd8  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180062fde  test    eax, eax
0x180062fe0  jz      loc_180062DBE
0x180062fe6  mov     ecx, esi; int
0x180062fe8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180062fed  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180062ff3  test    eax, eax
0x180062ff5  jmp     short loc_180062FA9
0x180062ff7  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180062ffe  jz      loc_180062DBE
0x180063004  mov     ecx, eax
0x180063006  jmp     short loc_180062FB1
0x180063008  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18006300f  jnz     short loc_180063004
0x180063011  test    eax, eax
0x180063013  jns     loc_180062D93
0x180063019  jmp     loc_180062DBE
0x18006301e  test    edi, edi
0x180063020  jnz     short loc_180063004
0x180063022  test    eax, eax
0x180063024  jns     loc_180062ECB
0x18006302a  jmp     loc_180062DBE
0x18006302f  test    edi, edi
0x180063031  jnz     short loc_180063004
0x180063033  test    eax, eax
0x180063035  jns     loc_180062EEA
0x18006303b  jmp     loc_180062DBE
0x180063040  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180063047  jnz     short loc_180063004
0x180063049  test    eax, eax
0x18006304b  jns     loc_180062F9A
0x180063051  jmp     loc_180062DBE
0x180063056  mov     rcx, [rsp+340h+var_2E8]; this
0x18006305b  lea     r8, [rbp+240h+var_150]; unsigned __int16 *
0x180063062  mov     r9d, 80h; unsigned int
0x180063068  call    ?ConvertPropVariantToString@CEnumQueryMetadataReader@@MEAAJPEAUtagPROPVARIANT@@PEAGI@Z; CEnumQueryMetadataReader::ConvertPropVariantToString(tagPROPVARIANT *,ushort *,uint)
0x18006306d  mov     esi, eax
0x18006306f  test    eax, eax
  ... truncated ...
```
