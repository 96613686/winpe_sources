# CEnumQueryMetadataBlocks::Next(ulong,ushort * *,ulong *)

- ea: `0x180068b50`
- end: `0x1800691fa`
- name: `?Next@CEnumQueryMetadataBlocks@@UEAAJKPEAPEAGPEAK@Z`
- size: `1706`
- prototype: `__int64 __fastcall(CEnumQueryMetadataBlocks *__hidden this, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callees

- `0x180020e7c`
- `0x180032d50`
- `0x180032d70`
- `0x18003b320`
- `0x180041ca8`
- `0x180041dec`
- `0x180067e88`
- `0x180068b50`
- `0x180069200`
- `0x180069234`
- `0x180069298`
- `0x1800693ac`
- `0x18006945c`
- `0x18006a7d0`
- `0x1800bb784`
- `0x1800e2f90`
- `0x1800e37d0`
- `0x1800e3c04`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180068f00`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180068f00`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180069094`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180069094`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068e34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068e34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800691df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800691df`

## pseudocode

```c
__int64 __fastcall CEnumQueryMetadataBlocks::Next(
        CEnumQueryMetadataBlocks *this,
        unsigned int a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  __int64 v5; // r15
  CMTALock *v6; // rbx
  CMILCOMBase *v7; // r13
  char *v8; // rsi
  CEnumQueryMetadataBlocks *v11; // r13
  int NameGuidMappingInfo; // eax
  int v13; // edi
  unsigned int v14; // r10d
  unsigned int i; // r14d
  int v16; // eax
  unsigned __int64 v17; // r8
  unsigned __int16 *v18; // rax
  __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rdi
  unsigned __int16 *v22; // rax
  bool v23; // zf
  int v24; // ecx
  unsigned int j; // r14d
  __int64 v27; // rcx
  int v28; // r11d
  int v29; // r11d
  unsigned int v30; // r9d
  unsigned int v31; // esi
  _QWORD *v32; // r13
  void *v33; // rcx
  CMILCOMBase *v34; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v35; // [rsp+38h] [rbp-C8h] BYREF
  ULONGLONG pullResult; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  int v39; // [rsp+58h] [rbp-A8h]
  void *v40; // [rsp+60h] [rbp-A0h]
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v42; // [rsp+70h] [rbp-90h]
  int v43; // [rsp+78h] [rbp-88h]
  __int64 v44; // [rsp+7Ch] [rbp-84h]
  __int64 v45; // [rsp+88h] [rbp-78h] BYREF
  GUID rguid; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR sz; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v48[254]; // [rsp+A2h] [rbp-5Eh] BYREF
  unsigned __int16 v49[128]; // [rsp+1A0h] [rbp+A0h] BYREF

  v40 = a3;
  v5 = a2;
  v35 = 0;
  Block = &v45;
  v34 = 0;
  v42 = &v45;
  v6 = (CEnumQueryMetadataBlocks *)((char *)this - 56);
  v38 = 0;
  v7 = 0;
  v39 = 0;
  v8 = 0;
  v45 = 0;
  v43 = 1;
  v44 = 1;
  rguid = 0;
  CMTALock::Enter((CEnumQueryMetadataBlocks *)((char *)this - 56));
  if ( !a3 )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147024809);
    v13 = -2147024809;
    v14 = 0;
    goto LABEL_41;
  }
  v11 = (CEnumQueryMetadataBlocks *)((char *)this - 72);
  NameGuidMappingInfo = CEnumQueryMetadataBlocks::EnsureInitialized((CEnumQueryMetadataBlocks *)((char *)this - 72));
  v13 = NameGuidMappingInfo;
  if ( NameGuidMappingInfo < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
    {
LABEL_39:
      v14 = 0;
      goto LABEL_40;
    }
    goto LABEL_37;
  }
  v13 = DynArrayImpl<1>::Grow(&Block, 8u, v5);
  if ( v13 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_39;
    DoStackCapture(v13);
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_39;
LABEL_33:
    v24 = v13;
    goto LABEL_38;
  }
  v8 = (char *)Block + (unsigned int)(8 * HIDWORD(v44));
  HIDWORD(v44) += v5;
  NameGuidMappingInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, unsigned int *))(**((_QWORD **)this + 2)
                                                                                          + 24LL))(
                          *((_QWORD *)this + 2),
                          (unsigned int)v5,
                          v8,
                          &v35);
  v14 = 0;
  v13 = NameGuidMappingInfo;
  if ( NameGuidMappingInfo < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_40;
LABEL_37:
    v24 = NameGuidMappingInfo;
LABEL_38:
    DoStackCapture(v24);
    goto LABEL_39;
  }
  memset_0(v40, 0, 8 * v5);
  v14 = 0;
  v39 = 1;
  for ( i = 0; ; ++i )
  {
    if ( i >= v35 )
    {
      v7 = v34;
      if ( a4 )
        *a4 = v35;
      goto LABEL_41;
    }
    pullResult = 0;
    NameGuidMappingInfo = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v8[8 * i])(
                            *(_QWORD *)&v8[8 * i],
                            &IID_IWICMetadataReader,
                            &v38);
    v14 = 0;
    v13 = NameGuidMappingInfo;
    if ( NameGuidMappingInfo < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_37;
      goto LABEL_40;
    }
    NameGuidMappingInfo = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v38 + 24LL))(v38, &rguid);
    v14 = 0;
    v13 = NameGuidMappingInfo;
    if ( NameGuidMappingInfo < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_37;
      goto LABEL_40;
    }
    if ( v38 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      v38 = 0;
    }
    NameGuidMappingInfo = CCodecFactory::GetNameGuidMappingInfo(&v34);
    v14 = 0;
    v13 = NameGuidMappingInfo;
    if ( NameGuidMappingInfo < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_37;
      goto LABEL_40;
    }
    v16 = CMappingInfo::MapGuidToShortName(v34, &rguid, (const unsigned __int16 **)&pullResult);
    v14 = 0;
    v13 = 0;
    if ( v16 != -2003292352 )
      v13 = v16;
    if ( v13 < 0 )
      goto LABEL_97;
    v37 = 0;
    NameGuidMappingInfo = CEnumQueryMetadataBlocks::GetReaderCount(v11, &rguid, &v37);
    v14 = 0;
    v13 = NameGuidMappingInfo;
    if ( NameGuidMappingInfo < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_37;
      goto LABEL_40;
    }
    if ( !pullResult )
      break;
    NameGuidMappingInfo = ConvertToEscapedString((const unsigned __int16 *)pullResult, &sz, v17);
    v14 = 0;
    v13 = NameGuidMappingInfo;
    if ( NameGuidMappingInfo < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_37;
      goto LABEL_40;
    }
    if ( v37 )
      NameGuidMappingInfo = StringCchPrintfW(v49, 0x80u, L"/[%u]%s");
    else
      NameGuidMappingInfo = StringCchPrintfW(v49, 0x80u, L"/%s", &sz);
LABEL_20:
    v14 = 0;
    v13 = NameGuidMappingInfo;
    if ( NameGuidMappingInfo < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_37;
      goto LABEL_40;
    }
    v18 = v49;
    v19 = 0x7FFFFFFF;
    do
    {
      if ( !*v18 )
        break;
      ++v18;
      --v19;
    }
    while ( v19 );
    v13 = v19 == 0 ? 0x80070057 : 0;
    if ( !v19 && (_DWORD)g_doStackCaptures )
      goto LABEL_33;
    v20 = (0x7FFFFFFF - v19) & -(__int64)(v19 != 0);
    if ( !v19 )
      goto LABEL_40;
    v21 = v20 + 1;
    if ( v20 + 1 < v20 || (pullResult = 0, !is_mul_ok(v21, 2u)) )
    {
      v13 = -2147024362;
      v23 = (_DWORD)g_doStackCaptures == 0;
      goto LABEL_32;
    }
    v22 = (unsigned __int16 *)CoTaskMemAlloc(2 * v21);
    v14 = 0;
    *((_QWORD *)v40 + i) = v22;
    if ( !v22 )
    {
      v13 = -2147024882;
LABEL_97:
      v23 = (_DWORD)g_doStackCaptures == 0;
LABEL_32:
      if ( v23 )
        goto LABEL_40;
      goto LABEL_33;
    }
    NameGuidMappingInfo = StringCchCopyW(v22, v21, v49);
    v14 = 0;
    v13 = NameGuidMappingInfo;
    if ( NameGuidMappingInfo < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_37;
      goto LABEL_40;
    }
  }
  pullResult = 0;
  NameGuidMappingInfo = StringFromGUID2(&rguid, &sz, 128);
  v14 = 0;
  v13 = NameGuidMappingInfo;
  if ( NameGuidMappingInfo < 0 )
  {
    if ( (_DWORD)g_doStackCaptures )
      goto LABEL_37;
    goto LABEL_40;
  }
  NameGuidMappingInfo = StringCchLengthW(&sz, 0x7FFFFFFFu, &pullResult);
  v14 = 0;
  v13 = NameGuidMappingInfo;
  if ( NameGuidMappingInfo < 0 )
  {
    if ( v28 )
      goto LABEL_37;
    goto LABEL_40;
  }
  NameGuidMappingInfo = ULongLongSub(pullResult, 1u, &pullResult);
  v13 = NameGuidMappingInfo;
  if ( NameGuidMappingInfo >= 0 )
  {
    if ( 2 * pullResult >= 0x100 )
      _report_rangecheckfailure();
    v30 = v37;
    *(_WORD *)&v48[2 * pullResult - 2] = v14;
    if ( v30 )
      NameGuidMappingInfo = StringCchPrintfW(v49, 0x80u, L"/[%u]{%s=%s}");
    else
      NameGuidMappingInfo = StringCchPrintfW(v49, 0x80u, L"/{%s=%s}", L"guid", v48);
    goto LABEL_20;
  }
  if ( v29 )
    goto LABEL_37;
LABEL_40:
  v7 = v34;
LABEL_41:
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v14 = 0;
    v38 = 0;
  }
  if ( v8 )
  {
    for ( j = v14; j < v35; ++j )
    {
      v27 = *(_QWORD *)&v8[8 * j];
      if ( v27 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        v14 = 0;
        *(_QWORD *)&v8[8 * j] = 0;
      }
    }
  }
  if ( v13 < 0 && v39 != v14 )
  {
    v31 = v14;
    if ( v35 > v14 )
    {
      v32 = v40;
      do
      {
        v33 = (void *)v32[v31];
        if ( v33 )
          CoTaskMemFree(v33);
        ++v31;
      }
      while ( v31 < v35 );
      v7 = v34;
    }
  }
  if ( v7 )
    CMILCOMBase::InternalRelease(v7);
  if ( v6 )
    CMTALock::Leave(v6);
  if ( Block != v42 )
    free(Block);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180068b50  push    rbp
0x180068b52  push    rbx
0x180068b53  push    rsi
0x180068b54  push    rdi
0x180068b55  push    r12
0x180068b57  push    r13
0x180068b59  push    r14
0x180068b5b  push    r15
0x180068b5d  lea     rbp, [rsp-1B8h]
0x180068b65  sub     rsp, 2B8h
0x180068b6c  mov     rax, cs:__security_cookie
0x180068b73  xor     rax, rsp
0x180068b76  mov     [rbp+1F0h+var_50], rax
0x180068b7d  mov     r14, rcx
0x180068b80  mov     [rsp+2F0h+var_290], r8
0x180068b85  xor     ecx, ecx
0x180068b87  mov     r15d, edx
0x180068b8a  lea     rax, [rbp+1F0h+var_268]
0x180068b8e  mov     [rsp+2F0h+var_2B8], ecx
0x180068b92  mov     [rsp+2F0h+Block], rax
0x180068b97  xorps   xmm0, xmm0
0x180068b9a  lea     rax, [rbp+1F0h+var_268]
0x180068b9e  mov     [rsp+2F0h+var_2C0], rcx
0x180068ba3  mov     [rsp+2F0h+var_280], rax
0x180068ba8  lea     rbx, [r14-38h]
0x180068bac  xor     eax, eax
0x180068bae  mov     [rsp+2F0h+var_2A0], rcx
0x180068bb3  mov     r13d, ecx
0x180068bb6  mov     [rsp+2F0h+var_298], ecx
0x180068bba  mov     esi, ecx
0x180068bbc  mov     [rbp+1F0h+var_268], rax
0x180068bc0  mov     rcx, rbx; this
0x180068bc3  mov     [rsp+2F0h+var_278], 1
0x180068bcb  mov     r12, r9
0x180068bce  mov     [rsp+2F0h+var_274], 1
0x180068bd7  mov     rdi, r8
0x180068bda  movups  xmmword ptr [rbp+1F0h+rguid.Data1], xmm0
0x180068bde  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180068be3  test    rdi, rdi
0x180068be6  jz      loc_180069066
0x180068bec  lea     r13, [r14-48h]
0x180068bf0  mov     rcx, r13; this
0x180068bf3  call    ?EnsureInitialized@CEnumQueryMetadataBlocks@@MEAAJXZ; CEnumQueryMetadataBlocks::EnsureInitialized(void)
0x180068bf8  mov     edi, eax
0x180068bfa  test    eax, eax
0x180068bfc  js      loc_180068E98
0x180068c02  mov     r8d, r15d
0x180068c05  lea     edx, [rsi+8]
0x180068c08  lea     rcx, [rsp+2F0h+Block]
0x180068c0d  call    ?Grow@?$DynArrayImpl@$00@@IEAAJIIHPEAPEBX@Z; DynArrayImpl<1>::Grow(uint,uint,int,void const * *)
0x180068c12  mov     edi, eax
0x180068c14  test    eax, eax
0x180068c16  js      loc_180068FFC
0x180068c1c  mov     edx, dword ptr [rbp+1F0h+var_274+4]
0x180068c1f  lea     esi, ds:0[rdx*8]
0x180068c26  add     rsi, [rsp+2F0h+Block]
0x180068c2b  add     edx, r15d
0x180068c2e  mov     dword ptr [rbp+1F0h+var_274+4], edx
0x180068c31  mov     rcx, [r14+10h]
0x180068c35  lea     r9, [rsp+2F0h+var_2B8]
0x180068c3a  mov     r8, rsi
0x180068c3d  mov     edx, r15d
0x180068c40  mov     rax, [rcx]
0x180068c43  mov     rax, [rax+18h]
0x180068c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068c4c  xor     r10d, r10d
0x180068c4f  mov     edi, eax
0x180068c51  test    eax, eax
0x180068c53  js      loc_180069024
0x180068c59  mov     rcx, [rsp+2F0h+var_290]; void *
0x180068c5e  mov     r8, r15
0x180068c61  shl     r8, 3; Size
0x180068c65  xor     edx, edx; Val
0x180068c67  call    memset_0
0x180068c6c  xor     r10d, r10d
0x180068c6f  mov     [rsp+2F0h+var_298], 1
0x180068c77  mov     r14d, r10d
0x180068c7a  cmp     r14d, [rsp+2F0h+var_2B8]
0x180068c7f  jnb     loc_180068E84
0x180068c85  mov     r15d, r14d
0x180068c88  lea     r8, [rsp+2F0h+var_2A0]
0x180068c8d  lea     rdx, IID_IWICMetadataReader
0x180068c94  mov     [rsp+2F0h+pullResult], r10
0x180068c99  mov     rcx, [rsi+r15*8]
0x180068c9d  mov     rax, [rcx]
0x180068ca0  mov     rax, [rax]
0x180068ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ca8  xor     r10d, r10d
0x180068cab  mov     edi, eax
0x180068cad  test    eax, eax
0x180068caf  js      loc_180068F7A
0x180068cb5  mov     rcx, [rsp+2F0h+var_2A0]
0x180068cba  lea     rdx, [rbp+1F0h+rguid]
0x180068cbe  mov     rax, [rcx]
0x180068cc1  mov     rax, [rax+18h]
0x180068cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068cca  xor     r10d, r10d
0x180068ccd  mov     edi, eax
0x180068ccf  test    eax, eax
0x180068cd1  js      loc_180068F94
0x180068cd7  mov     rcx, [rsp+2F0h+var_2A0]
0x180068cdc  test    rcx, rcx
0x180068cdf  jz      short loc_180068CF6
0x180068ce1  mov     rax, [rcx]
0x180068ce4  mov     rax, [rax+10h]
0x180068ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ced  mov     [rsp+2F0h+var_2A0], 0
0x180068cf6  lea     rcx, [rsp+2F0h+var_2C0]; struct CMappingInfo **
0x180068cfb  call    ?GetNameGuidMappingInfo@CCodecFactory@@SAJPEAPEAVCMappingInfo@@@Z; CCodecFactory::GetNameGuidMappingInfo(CMappingInfo * *)
0x180068d00  xor     r10d, r10d
0x180068d03  mov     edi, eax
0x180068d05  test    eax, eax
0x180068d07  js      loc_180068FAE
0x180068d0d  mov     rcx, [rsp+2F0h+var_2C0]; this
0x180068d12  lea     r8, [rsp+2F0h+pullResult]; unsigned __int16 **
0x180068d17  lea     rdx, [rbp+1F0h+rguid]; struct _GUID *
0x180068d1b  call    ?MapGuidToShortName@CMappingInfo@@QEAAJAEBU_GUID@@PEAPEBG@Z; CMappingInfo::MapGuidToShortName(_GUID const &,ushort const * *)
0x180068d20  xor     r10d, r10d
0x180068d23  cmp     eax, 88982F40h
0x180068d28  mov     edi, r10d
0x180068d2b  cmovnz  edi, eax
0x180068d2e  test    edi, edi
0x180068d30  js      loc_1800691A9
0x180068d36  lea     r8, [rsp+2F0h+var_2A8]; unsigned int *
0x180068d3b  mov     [rsp+2F0h+var_2A8], r10d
0x180068d40  lea     rdx, [rbp+1F0h+rguid]; struct _GUID *
0x180068d44  mov     rcx, r13; this
0x180068d47  call    ?GetReaderCount@CEnumQueryMetadataBlocks@@AEAAJAEBU_GUID@@PEAI@Z; CEnumQueryMetadataBlocks::GetReaderCount(_GUID const &,uint *)
0x180068d4c  xor     r10d, r10d
0x180068d4f  mov     edi, eax
0x180068d51  test    eax, eax
0x180068d53  js      loc_180068FC8
0x180068d59  mov     rcx, [rsp+2F0h+pullResult]; unsigned __int16 *
0x180068d5e  lea     rdx, [rbp+1F0h+sz]; unsigned __int16 *
0x180068d62  test    rcx, rcx
0x180068d65  jz      loc_180069085
0x180068d6b  call    ?ConvertToEscapedString@@YAJPEBGPEAG_K@Z; ConvertToEscapedString(ushort const *,ushort *,unsigned __int64)
0x180068d70  xor     r10d, r10d
0x180068d73  mov     edi, eax
0x180068d75  test    eax, eax
0x180068d77  js      loc_180068FE2
0x180068d7d  mov     r9d, [rsp+2F0h+var_2A8]
0x180068d82  lea     rcx, [rbp+1F0h+var_150]; unsigned __int16 *
0x180068d89  mov     edx, 80h; unsigned __int64
0x180068d8e  test    r9d, r9d
0x180068d91  jnz     loc_180069184
0x180068d97  lea     r9, [rbp+1F0h+sz]
0x180068d9b  lea     r8, aS_0; "/%s"
0x180068da2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180068da7  mov     r8d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180068dae  xor     r10d, r10d
0x180068db1  mov     edi, eax
0x180068db3  test    eax, eax
0x180068db5  js      loc_180068F64
0x180068dbb  mov     ecx, 7FFFFFFFh
0x180068dc0  lea     rax, [rbp+1F0h+var_150]
0x180068dc7  mov     edx, ecx
0x180068dc9  cmp     [rax], r10w
0x180068dcd  jz      short loc_180068DD9
0x180068dcf  add     rax, 2
0x180068dd3  sub     rdx, 1
0x180068dd7  jnz     short loc_180068DC9
0x180068dd9  mov     rax, rdx
0x180068ddc  neg     rax
0x180068ddf  mov     rax, rdx
0x180068de2  sbb     edi, edi
0x180068de4  sub     rcx, rdx
0x180068de7  not     edi
0x180068de9  and     edi, 80070057h
0x180068def  neg     rax
0x180068df2  sbb     r9, r9
0x180068df5  and     r9, rcx
0x180068df8  test    rdx, rdx
0x180068dfb  jz      loc_180069058
0x180068e01  mov     rax, rdx
0x180068e04  neg     rax
0x180068e07  sbb     rcx, rcx
0x180068e0a  and     rcx, r9
0x180068e0d  test    rdx, rdx
0x180068e10  jz      loc_180068EAA
0x180068e16  lea     rdi, [rcx+1]
0x180068e1a  cmp     rdi, rcx
0x180068e1d  jb      short loc_180068E76
0x180068e1f  mov     eax, 2
0x180068e24  mov     [rsp+2F0h+pullResult], r10
0x180068e29  mul     rdi
0x180068e2c  test    rdx, rdx
0x180068e2f  jnz     short loc_180068E76
0x180068e31  mov     rcx, rax; cb
0x180068e34  call    cs:__imp_CoTaskMemAlloc
0x180068e3a  mov     rcx, [rsp+2F0h+var_290]
0x180068e3f  xor     r10d, r10d
0x180068e42  mov     [rcx+r15*8], rax
0x180068e46  test    rax, rax
0x180068e49  jz      loc_1800691A4
0x180068e4f  lea     r8, [rbp+1F0h+var_150]; unsigned __int16 *
0x180068e56  mov     rdx, rdi; unsigned __int64
0x180068e59  mov     rcx, rax; unsigned __int16 *
0x180068e5c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180068e61  xor     r10d, r10d
0x180068e64  mov     edi, eax
0x180068e66  test    eax, eax
0x180068e68  js      loc_18006903E
0x180068e6e  inc     r14d
0x180068e71  jmp     loc_180068C7A
0x180068e76  mov     edi, 80070216h
0x180068e7b  test    r8d, r8d
0x180068e7e  jz      short loc_180068EAA
0x180068e80  mov     ecx, edi
0x180068e82  jmp     short loc_180068EA2
0x180068e84  mov     r13, [rsp+2F0h+var_2C0]
0x180068e89  test    r12, r12
0x180068e8c  jz      short loc_180068EAF
0x180068e8e  mov     eax, [rsp+2F0h+var_2B8]
0x180068e92  mov     [r12], eax
0x180068e96  jmp     short loc_180068EAF
0x180068e98  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180068e9e  jz      short loc_180068EA7
0x180068ea0  mov     ecx, eax; int
0x180068ea2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180068ea7  xor     r10d, r10d
0x180068eaa  mov     r13, [rsp+2F0h+var_2C0]
0x180068eaf  mov     rcx, [rsp+2F0h+var_2A0]
0x180068eb4  test    rcx, rcx
0x180068eb7  jz      short loc_180068ECD
0x180068eb9  mov     rax, [rcx]
0x180068ebc  mov     rax, [rax+10h]
0x180068ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ec5  xor     r10d, r10d
0x180068ec8  mov     [rsp+2F0h+var_2A0], r10
0x180068ecd  test    rsi, rsi
0x180068ed0  jnz     short loc_180068F2B
0x180068ed2  test    edi, edi
0x180068ed4  js      loc_1800691B5
0x180068eda  test    r13, r13
0x180068edd  jz      short loc_180068EE7
0x180068edf  mov     rcx, r13; this
0x180068ee2  call    ?InternalRelease@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalRelease(void)
0x180068ee7  test    rbx, rbx
0x180068eea  jz      short loc_180068EF4
0x180068eec  mov     rcx, rbx; this
0x180068eef  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x180068ef4  mov     rcx, [rsp+2F0h+Block]; Block
0x180068ef9  cmp     rcx, [rsp+2F0h+var_280]
0x180068efe  jz      short loc_180068F06
0x180068f00  call    cs:__imp_free
0x180068f06  mov     eax, edi
0x180068f08  mov     rcx, [rbp+1F0h+var_50]
0x180068f0f  xor     rcx, rsp; StackCookie
0x180068f12  call    __security_check_cookie
0x180068f17  add     rsp, 2B8h
0x180068f1e  pop     r15
0x180068f20  pop     r14
0x180068f22  pop     r13
0x180068f24  pop     r12
0x180068f26  pop     rdi
0x180068f27  pop     rsi
0x180068f28  pop     rbx
0x180068f29  pop     rbp
0x180068f2a  retn
0x180068f2b  mov     r14d, r10d
0x180068f2e  cmp     [rsp+2F0h+var_2B8], r10d
0x180068f33  jbe     short loc_180068ED2
0x180068f35  mov     r15d, r14d
0x180068f38  mov     rcx, [rsi+r15*8]
0x180068f3c  test    rcx, rcx
0x180068f3f  jz      short loc_180068F54
0x180068f41  mov     rax, [rcx]
0x180068f44  mov     rax, [rax+10h]
0x180068f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f4d  xor     r10d, r10d
0x180068f50  mov     [rsi+r15*8], r10
0x180068f54  inc     r14d
0x180068f57  cmp     r14d, [rsp+2F0h+var_2B8]
0x180068f5c  jnb     loc_180068ED2
0x180068f62  jmp     short loc_180068F35
0x180068f64  test    r8d, r8d
0x180068f67  jnz     loc_180068EA0
0x180068f6d  test    eax, eax
0x180068f6f  jns     loc_180068DBB
0x180068f75  jmp     loc_180068EAA
0x180068f7a  cmp     cs:?g_doStackCaptures@@3HA, r10d; int g_doStackCaptures
0x180068f81  jnz     loc_180068EA0
0x180068f87  test    eax, eax
0x180068f89  jns     loc_180068CB5
0x180068f8f  jmp     loc_180068EAA
0x180068f94  cmp     cs:?g_doStackCaptures@@3HA, r10d; int g_doStackCaptures
0x180068f9b  jnz     loc_180068EA0
0x180068fa1  test    eax, eax
0x180068fa3  jns     loc_180068CD7
0x180068fa9  jmp     loc_180068EAA
0x180068fae  cmp     cs:?g_doStackCaptures@@3HA, r10d; int g_doStackCaptures
0x180068fb5  jnz     loc_180068EA0
0x180068fbb  test    eax, eax
0x180068fbd  jns     loc_180068D0D
0x180068fc3  jmp     loc_180068EAA
0x180068fc8  cmp     cs:?g_doStackCaptures@@3HA, r10d; int g_doStackCaptures
0x180068fcf  jnz     loc_180068EA0
0x180068fd5  test    eax, eax
0x180068fd7  jns     loc_180068D59
  ... truncated ...
```
