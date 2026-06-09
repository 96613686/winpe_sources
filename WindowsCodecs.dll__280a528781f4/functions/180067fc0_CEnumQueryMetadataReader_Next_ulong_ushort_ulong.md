# CEnumQueryMetadataReader::Next(ulong,ushort * *,ulong *)

- ea: `0x180067fc0`
- end: `0x180068552`
- name: `?Next@CEnumQueryMetadataReader@@UEAAJKPEAPEAGPEAK@Z`
- size: `1426`
- prototype: `__int64 __fastcall(CEnumQueryMetadataReader *this, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002f6fc`
- `0x180032d50`
- `0x180032d70`
- `0x18003b320`
- `0x180041dec`
- `0x180052ac8`
- `0x180067fc0`
- `0x180068560`
- `0x1800685a0`
- `0x180069234`
- `0x1800693ac`
- `0x18006a7d0`
- `0x18006a85c`
- `0x1800bb784`
- `0x1800e2f90`
- `0x1800e3c04`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800681ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180068202`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800681ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180068202`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068317`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068317`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800681a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800681ad`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800681a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800681ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006853a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006853a`

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
  NameGuidMappingInfo = DynArrayImpl<0>::Grow(&v49, 0x18u, a2, 0, 0);
  if ( NameGuidMappingInfo < 0
    || (v9 = (char *)v49 + (unsigned int)(24 * HIDWORD(v52)),
        HIDWORD(v52) += a2,
        NameGuidMappingInfo = DynArrayImpl<0>::Grow(&Block, 0x18u, a2, 0, 0),
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
0x180067fc0  push    rbp
0x180067fc2  push    rbx
0x180067fc3  push    rsi
0x180067fc4  push    rdi
0x180067fc5  push    r12
0x180067fc7  push    r13
0x180067fc9  push    r14
0x180067fcb  push    r15
0x180067fcd  lea     rbp, [rsp-208h]
0x180067fd5  sub     rsp, 308h
0x180067fdc  mov     rax, cs:__security_cookie
0x180067fe3  xor     rax, rsp
0x180067fe6  mov     [rbp+240h+var_50], rax
0x180067fed  xor     r12d, r12d
0x180067ff0  mov     [rsp+340h+var_2D8], rcx
0x180067ff5  mov     r13, rcx
0x180067ff8  mov     [rsp+340h+var_2D0], r9
0x180067ffd  lea     rax, [rbp+240h+var_268]
0x180068001  mov     [rsp+340h+var_2E0], r8
0x180068006  mov     [rbp+240h+var_288], rax
0x18006800a  mov     rsi, r8
0x18006800d  lea     ecx, [r12+1]
0x180068012  mov     edi, edx
0x180068014  lea     rax, [rbp+240h+var_268]
0x180068018  mov     [rbp+240h+var_278], ecx
0x18006801b  mov     [rbp+240h+var_280], rax
0x18006801f  lea     rbx, [r13-38h]
0x180068023  lea     rax, [rbp+240h+var_2A0]
0x180068027  mov     [rbp+240h+var_274], rcx
0x18006802b  mov     [rbp+240h+Block], rax
0x18006802f  mov     r14d, r12d
0x180068032  lea     rax, [rbp+240h+var_2A0]
0x180068036  mov     [rbp+240h+var_2B0], ecx
0x180068039  mov     [rbp+240h+var_2AC], rcx
0x18006803d  mov     r15d, r12d
0x180068040  mov     rcx, rbx; this
0x180068043  mov     [rbp+240h+var_2B8], rax
0x180068047  mov     [rsp+340h+var_300], r12d
0x18006804c  mov     [rsp+340h+var_2F8], r12
0x180068051  mov     [rsp+340h+var_2FC], r12d
0x180068056  mov     [rsp+340h+var_2C8], rbx
0x18006805b  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180068060  test    rsi, rsi
0x180068063  jz      loc_18006836C
0x180068069  mov     r8d, edi
0x18006806c  xor     edx, edx; Val
0x18006806e  shl     r8, 3; Size
0x180068072  mov     rcx, rsi; void *
0x180068075  call    memset_0
0x18006807a  lea     rax, [r13-48h]
0x18006807e  mov     rcx, rax; this
0x180068081  mov     [rsp+340h+var_2E8], rax
0x180068086  call    ?EnsureInitialized@CEnumQueryMetadataReader@@MEAAJXZ; CEnumQueryMetadataReader::EnsureInitialized(void)
0x18006808b  mov     esi, eax
0x18006808d  test    eax, eax
0x18006808f  js      loc_1800683A8
0x180068095  xor     r9d, r9d
0x180068098  mov     [rsp+340h+var_320], r12
0x18006809d  mov     r8d, edi
0x1800680a0  lea     edx, [r12+18h]
0x1800680a5  lea     rcx, [rbp+240h+var_288]
0x1800680a9  call    ?Grow@?$DynArrayImpl@$0A@@@IEAAJIIHPEAPEBX@Z; DynArrayImpl<0>::Grow(uint,uint,int,void const * *)
0x1800680ae  mov     esi, eax
0x1800680b0  test    eax, eax
0x1800680b2  js      loc_180068389
0x1800680b8  mov     ecx, dword ptr [rbp+240h+var_274+4]
0x1800680bb  lea     r14d, [rcx+rcx*2]
0x1800680bf  shl     r14d, 3
0x1800680c3  add     r14, [rbp+240h+var_288]
0x1800680c7  add     ecx, edi
0x1800680c9  mov     dword ptr [rbp+240h+var_274+4], ecx
0x1800680cc  xor     r9d, r9d
0x1800680cf  mov     [rsp+340h+var_320], r12
0x1800680d4  mov     r8d, edi
0x1800680d7  lea     edx, [r12+18h]
0x1800680dc  lea     rcx, [rbp+240h+Block]
0x1800680e0  call    ?Grow@?$DynArrayImpl@$0A@@@IEAAJIIHPEAPEBX@Z; DynArrayImpl<0>::Grow(uint,uint,int,void const * *)
0x1800680e5  mov     esi, eax
0x1800680e7  test    eax, eax
0x1800680e9  js      loc_180068389
0x1800680ef  mov     ecx, dword ptr [rbp+240h+var_2AC+4]
0x1800680f2  lea     r15d, [rcx+rcx*2]
0x1800680f6  shl     r15d, 3
0x1800680fa  add     r15, [rbp+240h+Block]
0x1800680fe  add     ecx, edi
0x180068100  mov     dword ptr [rbp+240h+var_2AC+4], ecx
0x180068103  mov     r8d, r12d
0x180068106  test    edi, edi
0x180068108  jz      short loc_180068132
0x18006810a  mov     eax, r8d
0x18006810d  xorps   xmm0, xmm0
0x180068110  inc     r8d
0x180068113  lea     rcx, [rax+rax*2]
0x180068117  xor     eax, eax
0x180068119  movups  xmmword ptr [r14+rcx*8], xmm0
0x18006811e  mov     [r14+rcx*8+10h], rax
0x180068123  movups  xmmword ptr [r15+rcx*8], xmm0
0x180068128  mov     [r15+rcx*8+10h], rax
0x18006812d  cmp     r8d, edi
0x180068130  jb      short loc_18006810A
0x180068132  mov     rcx, [r13+20h]
0x180068136  lea     r8, [rsp+340h+var_300]
0x18006813b  mov     [rsp+340h+var_318], r8
0x180068140  mov     r9, r15
0x180068143  mov     r8, r14
0x180068146  mov     [rsp+340h+var_320], r12
0x18006814b  mov     edx, edi
0x18006814d  mov     rax, [rcx]
0x180068150  mov     rax, [rax+18h]
0x180068154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068159  mov     esi, eax
0x18006815b  test    eax, eax
0x18006815d  js      loc_1800683B9
0x180068163  mov     [rsp+340h+var_2FC], 1
0x18006816b  mov     r13d, r12d
0x18006816e  cmp     r13d, [rsp+340h+var_300]
0x180068173  jb      loc_18006822D
0x180068179  mov     r12, [rsp+340h+var_2D0]
0x18006817e  test    r12, r12
0x180068181  jz      short loc_18006818B
0x180068183  mov     eax, [rsp+340h+var_300]
0x180068187  mov     [r12], eax
0x18006818b  xor     r12d, r12d
0x18006818e  xor     r13d, r13d
0x180068191  cmp     [rsp+340h+var_300], r13d
0x180068196  jbe     short loc_1800681BD
0x180068198  mov     eax, r12d
0x18006819b  lea     rdi, [rax+rax*2]
0x18006819f  lea     rcx, [r14+rdi*8]; pvar
0x1800681a3  call    cs:__imp_PropVariantClear
0x1800681a9  lea     rcx, [r15+rdi*8]; pvar
0x1800681ad  call    cs:__imp_PropVariantClear
0x1800681b3  inc     r12d
0x1800681b6  cmp     r12d, [rsp+340h+var_300]
0x1800681bb  jb      short loc_180068198
0x1800681bd  test    esi, esi
0x1800681bf  js      loc_180068511
0x1800681c5  mov     rax, [rsp+340h+var_2F8]
0x1800681ca  test    rax, rax
0x1800681cd  jz      short loc_1800681D7
0x1800681cf  mov     rcx, rax; this
0x1800681d2  call    ?InternalRelease@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalRelease(void)
0x1800681d7  test    rbx, rbx
0x1800681da  jz      short loc_1800681E4
0x1800681dc  mov     rcx, rbx; this
0x1800681df  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x1800681e4  mov     rcx, [rbp+240h+Block]; Block
0x1800681e8  cmp     rcx, [rbp+240h+var_2B8]
0x1800681ec  jz      short loc_1800681F8
0x1800681ee  call    cs:__imp_free
0x1800681f4  mov     [rbp+240h+Block], r13
0x1800681f8  mov     rcx, [rbp+240h+var_288]; Block
0x1800681fc  cmp     rcx, [rbp+240h+var_280]
0x180068200  jz      short loc_180068208
0x180068202  call    cs:__imp_free
0x180068208  mov     eax, esi
0x18006820a  mov     rcx, [rbp+240h+var_50]
0x180068211  xor     rcx, rsp; StackCookie
0x180068214  call    __security_check_cookie
0x180068219  add     rsp, 308h
0x180068220  pop     r15
0x180068222  pop     r14
0x180068224  pop     r13
0x180068226  pop     r12
0x180068228  pop     rdi
0x180068229  pop     rsi
0x18006822a  pop     rbx
0x18006822b  pop     rbp
0x18006822c  retn
0x18006822d  mov     eax, r13d
0x180068230  lea     r12, [rax+rax*2]
0x180068234  lea     rdx, [r14+r12*8]; struct tagPROPVARIANT *
0x180068238  cmp     word ptr [rdx], 1Fh
0x18006823c  jz      loc_180068489
0x180068242  xor     edi, edi
0x180068244  cmp     [rdx], di
0x180068247  jnz     loc_180068407
0x18006824d  mov     dword ptr [rbp+240h+var_250], 2Fh ; '/'
0x180068254  mov     rcx, [rsp+340h+var_2E8]; this
0x180068259  lea     rdx, [r15+r12*8]; struct tagPROPVARIANT *
0x18006825d  mov     r9d, 80h; unsigned int
0x180068263  lea     r8, [rbp+240h+var_150]; unsigned __int16 *
0x18006826a  call    ?ConvertPropVariantToString@CEnumQueryMetadataReader@@MEAAJPEAUtagPROPVARIANT@@PEAGI@Z; CEnumQueryMetadataReader::ConvertPropVariantToString(tagPROPVARIANT *,ushort *,uint)
0x18006826f  mov     edi, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180068275  xor     r12d, r12d
0x180068278  mov     esi, eax
0x18006827a  test    eax, eax
0x18006827c  js      loc_1800683CF
0x180068282  lea     r8, [rbp+240h+var_150]; unsigned __int16 *
0x180068289  mov     edx, 80h; unsigned __int64
0x18006828e  lea     rcx, [rbp+240h+var_250]; unsigned __int16 *
0x180068292  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180068297  mov     esi, eax
0x180068299  test    eax, eax
0x18006829b  js      loc_1800683E0
0x1800682a1  mov     ecx, 7FFFFFFFh
0x1800682a6  lea     rax, [rbp+240h+var_250]
0x1800682aa  mov     edx, ecx
0x1800682ac  cmp     [rax], r12w
0x1800682b0  jz      short loc_1800682BC
0x1800682b2  add     rax, 2
0x1800682b6  sub     rdx, 1
0x1800682ba  jnz     short loc_1800682AC
0x1800682bc  mov     rax, rdx
0x1800682bf  neg     rax
0x1800682c2  mov     rax, rdx
0x1800682c5  sbb     esi, esi
0x1800682c7  sub     rcx, rdx
0x1800682ca  not     esi
0x1800682cc  and     esi, 80070057h
0x1800682d2  neg     rax
0x1800682d5  sbb     r8, r8
0x1800682d8  and     r8, rcx
0x1800682db  test    rdx, rdx
0x1800682de  jz      loc_18006847C
0x1800682e4  mov     rax, rdx
0x1800682e7  neg     rax
0x1800682ea  sbb     rcx, rcx
0x1800682ed  and     rcx, r8
0x1800682f0  test    rdx, rdx
0x1800682f3  jz      loc_18006818E
0x1800682f9  lea     rsi, [rcx+1]
0x1800682fd  cmp     rsi, rcx
0x180068300  jb      short loc_180068353
0x180068302  mov     eax, 2
0x180068307  mov     [rsp+340h+var_2F0], r12
0x18006830c  mul     rsi
0x18006830f  test    rdx, rdx
0x180068312  jnz     short loc_180068353
0x180068314  mov     rcx, rax; cb
0x180068317  call    cs:__imp_CoTaskMemAlloc
0x18006831d  mov     rdx, [rsp+340h+var_2E0]
0x180068322  mov     ecx, r13d
0x180068325  mov     [rdx+rcx*8], rax
0x180068329  test    rax, rax
0x18006832c  jz      loc_180068500
0x180068332  lea     r8, [rbp+240h+var_250]; unsigned __int16 *
0x180068336  mov     rdx, rsi; unsigned __int64
0x180068339  mov     rcx, rax; unsigned __int16 *
0x18006833c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180068341  mov     esi, eax
0x180068343  test    eax, eax
0x180068345  js      loc_1800683F1
0x18006834b  inc     r13d
0x18006834e  jmp     loc_18006816E
0x180068353  mov     esi, 80070216h
0x180068358  test    edi, edi
0x18006835a  jz      loc_18006818E
0x180068360  mov     ecx, esi; int
0x180068362  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180068367  jmp     loc_18006818E
0x18006836c  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180068373  jz      short loc_18006837F
0x180068375  mov     ecx, 80070057h; int
0x18006837a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18006837f  mov     esi, 80070057h
0x180068384  jmp     loc_18006818E
0x180068389  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18006838f  test    eax, eax
0x180068391  jz      loc_18006818E
0x180068397  mov     ecx, esi; int
0x180068399  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18006839e  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800683a4  test    eax, eax
0x1800683a6  jmp     short loc_18006835A
0x1800683a8  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800683af  jz      loc_18006818E
0x1800683b5  mov     ecx, eax
0x1800683b7  jmp     short loc_180068362
0x1800683b9  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800683c0  jnz     short loc_1800683B5
0x1800683c2  test    eax, eax
0x1800683c4  jns     loc_180068163
0x1800683ca  jmp     loc_18006818E
0x1800683cf  test    edi, edi
0x1800683d1  jnz     short loc_1800683B5
0x1800683d3  test    eax, eax
0x1800683d5  jns     loc_180068282
0x1800683db  jmp     loc_18006818E
0x1800683e0  test    edi, edi
0x1800683e2  jnz     short loc_1800683B5
0x1800683e4  test    eax, eax
0x1800683e6  jns     loc_1800682A1
0x1800683ec  jmp     loc_18006818E
0x1800683f1  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800683f8  jnz     short loc_1800683B5
0x1800683fa  test    eax, eax
0x1800683fc  jns     loc_18006834B
0x180068402  jmp     loc_18006818E
0x180068407  mov     rcx, [rsp+340h+var_2E8]; this
0x18006840c  lea     r8, [rbp+240h+var_150]; unsigned __int16 *
0x180068413  mov     r9d, 80h; unsigned int
0x180068419  call    ?ConvertPropVariantToString@CEnumQueryMetadataReader@@MEAAJPEAUtagPROPVARIANT@@PEAGI@Z; CEnumQueryMetadataReader::ConvertPropVariantToString(tagPROPVARIANT *,ushort *,uint)
0x18006841e  mov     esi, eax
0x180068420  test    eax, eax
0x180068422  js      short loc_18006845F
0x180068424  lea     r9, [rbp+240h+var_150]
0x18006842b  mov     edx, 80h; unsigned __int64
0x180068430  lea     r8, aS_2; "/%s:"
0x180068437  lea     rcx, [rbp+240h+var_250]; unsigned __int16 *
  ... truncated ...
```
