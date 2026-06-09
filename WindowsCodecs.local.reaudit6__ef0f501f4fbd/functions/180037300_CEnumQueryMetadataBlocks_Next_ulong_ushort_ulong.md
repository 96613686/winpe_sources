# CEnumQueryMetadataBlocks::Next(ulong,ushort * *,ulong *)

- ea: `0x180037300`
- end: `0x1800379c3`
- name: `?Next@CEnumQueryMetadataBlocks@@UEAAJKPEAPEAGPEAK@Z`
- size: `1731`
- prototype: `__int64 __fastcall(CEnumQueryMetadataBlocks *__hidden this, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002ae60`
- `0x1800319d0`
- `0x1800319f0`
- `0x1800355e8`
- `0x18003573c`
- `0x180037300`
- `0x1800379d0`
- `0x180037a04`
- `0x180037a68`
- `0x180037b8c`
- `0x180037c3c`
- `0x180038fe0`
- `0x180046a78`
- `0x180064b00`
- `0x1800bd9d4`
- `0x1800e5e60`
- `0x1800e66a0`
- `0x1800e6af4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800376b6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800376b6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180037851`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180037851`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800375e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800375e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800379a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800379a2`

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
0x180037300  push    rbp
0x180037302  push    rbx
0x180037303  push    rsi
0x180037304  push    rdi
0x180037305  push    r12
0x180037307  push    r13
0x180037309  push    r14
0x18003730b  push    r15
0x18003730d  lea     rbp, [rsp-1B8h]
0x180037315  sub     rsp, 2B8h
0x18003731c  mov     rax, cs:__security_cookie
0x180037323  xor     rax, rsp
0x180037326  mov     [rbp+1F0h+var_50], rax
0x18003732d  mov     r14, rcx
0x180037330  mov     [rsp+2F0h+var_290], r8
0x180037335  xor     ecx, ecx
0x180037337  mov     r15d, edx
0x18003733a  lea     rax, [rbp+1F0h+var_268]
0x18003733e  mov     [rsp+2F0h+var_2B8], ecx
0x180037342  mov     [rsp+2F0h+Block], rax
0x180037347  xorps   xmm0, xmm0
0x18003734a  lea     rax, [rbp+1F0h+var_268]
0x18003734e  mov     [rsp+2F0h+var_2C0], rcx
0x180037353  mov     [rsp+2F0h+var_280], rax
0x180037358  lea     rbx, [r14-38h]
0x18003735c  xor     eax, eax
0x18003735e  mov     [rsp+2F0h+var_2A0], rcx
0x180037363  mov     r13d, ecx
0x180037366  mov     [rsp+2F0h+var_298], ecx
0x18003736a  mov     esi, ecx
0x18003736c  mov     [rbp+1F0h+var_268], rax
0x180037370  mov     rcx, rbx; this
0x180037373  mov     [rsp+2F0h+var_278], 1
0x18003737b  mov     r12, r9
0x18003737e  mov     [rsp+2F0h+var_274], 1
0x180037387  mov     rdi, r8
0x18003738a  movups  xmmword ptr [rbp+1F0h+rguid.Data1], xmm0
0x18003738e  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180037393  test    rdi, rdi
0x180037396  jz      loc_180037823
0x18003739c  lea     r13, [r14-48h]
0x1800373a0  mov     rcx, r13; this
0x1800373a3  call    ?EnsureInitialized@CEnumQueryMetadataBlocks@@MEAAJXZ; CEnumQueryMetadataBlocks::EnsureInitialized(void)
0x1800373a8  mov     edi, eax
0x1800373aa  test    eax, eax
0x1800373ac  js      loc_18003764E
0x1800373b2  mov     r8d, r15d
0x1800373b5  lea     edx, [rsi+8]
0x1800373b8  lea     rcx, [rsp+2F0h+Block]
0x1800373bd  call    ?Grow@?$DynArrayImpl@$00@@IEAAJIIHPEAPEBX@Z; DynArrayImpl<1>::Grow(uint,uint,int,void const * *)
0x1800373c2  mov     edi, eax
0x1800373c4  test    eax, eax
0x1800373c6  js      loc_1800377B9
0x1800373cc  mov     edx, dword ptr [rbp+1F0h+var_274+4]
0x1800373cf  lea     esi, ds:0[rdx*8]
0x1800373d6  add     rsi, [rsp+2F0h+Block]
0x1800373db  add     edx, r15d
0x1800373de  mov     dword ptr [rbp+1F0h+var_274+4], edx
0x1800373e1  mov     rcx, [r14+10h]
0x1800373e5  lea     r9, [rsp+2F0h+var_2B8]
0x1800373ea  mov     r8, rsi
0x1800373ed  mov     edx, r15d
0x1800373f0  mov     rax, [rcx]
0x1800373f3  mov     rax, [rax+18h]
0x1800373f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373fc  xor     r10d, r10d
0x1800373ff  mov     edi, eax
0x180037401  test    eax, eax
0x180037403  js      loc_1800377E1
0x180037409  mov     rcx, [rsp+2F0h+var_290]; void *
0x18003740e  mov     r8, r15
0x180037411  shl     r8, 3; Size
0x180037415  xor     edx, edx; Val
0x180037417  call    memset_0
0x18003741c  xor     r10d, r10d
0x18003741f  mov     [rsp+2F0h+var_298], 1
0x180037427  mov     r14d, r10d
0x18003742a  cmp     r14d, [rsp+2F0h+var_2B8]
0x18003742f  jnb     loc_18003763A
0x180037435  mov     r15d, r14d
0x180037438  lea     r8, [rsp+2F0h+var_2A0]
0x18003743d  lea     rdx, IID_IWICMetadataReader
0x180037444  mov     [rsp+2F0h+pullResult], r10
0x180037449  mov     rcx, [rsi+r15*8]
0x18003744d  mov     rax, [rcx]
0x180037450  mov     rax, [rax]
0x180037453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037458  xor     r10d, r10d
0x18003745b  mov     edi, eax
0x18003745d  test    eax, eax
0x18003745f  js      loc_180037737
0x180037465  mov     rcx, [rsp+2F0h+var_2A0]
0x18003746a  lea     rdx, [rbp+1F0h+rguid]
0x18003746e  mov     rax, [rcx]
0x180037471  mov     rax, [rax+18h]
0x180037475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003747a  xor     r10d, r10d
0x18003747d  mov     edi, eax
0x18003747f  test    eax, eax
0x180037481  js      loc_180037751
0x180037487  mov     rcx, [rsp+2F0h+var_2A0]
0x18003748c  test    rcx, rcx
0x18003748f  jz      short loc_1800374A6
0x180037491  mov     rax, [rcx]
0x180037494  mov     rax, [rax+10h]
0x180037498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003749d  mov     [rsp+2F0h+var_2A0], 0
0x1800374a6  lea     rcx, [rsp+2F0h+var_2C0]; struct CMappingInfo **
0x1800374ab  call    ?GetNameGuidMappingInfo@CCodecFactory@@SAJPEAPEAVCMappingInfo@@@Z; CCodecFactory::GetNameGuidMappingInfo(CMappingInfo * *)
0x1800374b0  xor     r10d, r10d
0x1800374b3  mov     edi, eax
0x1800374b5  test    eax, eax
0x1800374b7  js      loc_18003776B
0x1800374bd  mov     rcx, [rsp+2F0h+var_2C0]; this
0x1800374c2  lea     r8, [rsp+2F0h+pullResult]; unsigned __int16 **
0x1800374c7  lea     rdx, [rbp+1F0h+rguid]; struct _GUID *
0x1800374cb  call    ?MapGuidToShortName@CMappingInfo@@QEAAJAEBU_GUID@@PEAPEBG@Z; CMappingInfo::MapGuidToShortName(_GUID const &,ushort const * *)
0x1800374d0  xor     r10d, r10d
0x1800374d3  cmp     eax, 88982F40h
0x1800374d8  mov     edi, r10d
0x1800374db  cmovnz  edi, eax
0x1800374de  test    edi, edi
0x1800374e0  js      loc_18003796C
0x1800374e6  lea     r8, [rsp+2F0h+var_2A8]; unsigned int *
0x1800374eb  mov     [rsp+2F0h+var_2A8], r10d
0x1800374f0  lea     rdx, [rbp+1F0h+rguid]; struct _GUID *
0x1800374f4  mov     rcx, r13; this
0x1800374f7  call    ?GetReaderCount@CEnumQueryMetadataBlocks@@AEAAJAEBU_GUID@@PEAI@Z; CEnumQueryMetadataBlocks::GetReaderCount(_GUID const &,uint *)
0x1800374fc  xor     r10d, r10d
0x1800374ff  mov     edi, eax
0x180037501  test    eax, eax
0x180037503  js      loc_180037785
0x180037509  mov     rcx, [rsp+2F0h+pullResult]; unsigned __int16 *
0x18003750e  lea     rdx, [rbp+1F0h+sz]; unsigned __int16 *
0x180037512  test    rcx, rcx
0x180037515  jz      loc_180037842
0x18003751b  call    ?ConvertToEscapedString@@YAJPEBGPEAG_K@Z; ConvertToEscapedString(ushort const *,ushort *,unsigned __int64)
0x180037520  xor     r10d, r10d
0x180037523  mov     edi, eax
0x180037525  test    eax, eax
0x180037527  js      loc_18003779F
0x18003752d  mov     r9d, [rsp+2F0h+var_2A8]
0x180037532  lea     rcx, [rbp+1F0h+var_150]; unsigned __int16 *
0x180037539  mov     edx, 80h; unsigned __int64
0x18003753e  test    r9d, r9d
0x180037541  jnz     loc_180037947
0x180037547  lea     r9, [rbp+1F0h+sz]
0x18003754b  lea     r8, aS_0; "/%s"
0x180037552  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037557  mov     r8d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18003755e  xor     r10d, r10d
0x180037561  mov     edi, eax
0x180037563  test    eax, eax
0x180037565  js      loc_180037721
0x18003756b  mov     ecx, 7FFFFFFFh
0x180037570  lea     rax, [rbp+1F0h+var_150]
0x180037577  mov     edx, ecx
0x180037579  cmp     [rax], r10w
0x18003757d  jz      short loc_180037589
0x18003757f  add     rax, 2
0x180037583  sub     rdx, 1
0x180037587  jnz     short loc_180037579
0x180037589  mov     rax, rdx
0x18003758c  neg     rax
0x18003758f  mov     rax, rdx
0x180037592  sbb     edi, edi
0x180037594  sub     rcx, rdx
0x180037597  not     edi
0x180037599  and     edi, 80070057h
0x18003759f  neg     rax
0x1800375a2  sbb     r9, r9
0x1800375a5  and     r9, rcx
0x1800375a8  test    rdx, rdx
0x1800375ab  jz      loc_180037815
0x1800375b1  mov     rax, rdx
0x1800375b4  neg     rax
0x1800375b7  sbb     rcx, rcx
0x1800375ba  and     rcx, r9
0x1800375bd  test    rdx, rdx
0x1800375c0  jz      loc_180037660
0x1800375c6  lea     rdi, [rcx+1]
0x1800375ca  cmp     rdi, rcx
0x1800375cd  jb      short loc_18003762C
0x1800375cf  mov     eax, 2
0x1800375d4  mov     [rsp+2F0h+pullResult], r10
0x1800375d9  mul     rdi
0x1800375dc  test    rdx, rdx
0x1800375df  jnz     short loc_18003762C
0x1800375e1  mov     rcx, rax; cb
0x1800375e4  call    cs:__imp_CoTaskMemAlloc
0x1800375eb  nop     dword ptr [rax+rax+00h]
0x1800375f0  mov     rcx, [rsp+2F0h+var_290]
0x1800375f5  xor     r10d, r10d
0x1800375f8  mov     [rcx+r15*8], rax
0x1800375fc  test    rax, rax
0x1800375ff  jz      loc_180037967
0x180037605  lea     r8, [rbp+1F0h+var_150]; unsigned __int16 *
0x18003760c  mov     rdx, rdi; unsigned __int64
0x18003760f  mov     rcx, rax; unsigned __int16 *
0x180037612  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037617  xor     r10d, r10d
0x18003761a  mov     edi, eax
0x18003761c  test    eax, eax
0x18003761e  js      loc_1800377FB
0x180037624  inc     r14d
0x180037627  jmp     loc_18003742A
0x18003762c  mov     edi, 80070216h
0x180037631  test    r8d, r8d
0x180037634  jz      short loc_180037660
0x180037636  mov     ecx, edi
0x180037638  jmp     short loc_180037658
0x18003763a  mov     r13, [rsp+2F0h+var_2C0]
0x18003763f  test    r12, r12
0x180037642  jz      short loc_180037665
0x180037644  mov     eax, [rsp+2F0h+var_2B8]
0x180037648  mov     [r12], eax
0x18003764c  jmp     short loc_180037665
0x18003764e  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180037654  jz      short loc_18003765D
0x180037656  mov     ecx, eax; int
0x180037658  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18003765d  xor     r10d, r10d
0x180037660  mov     r13, [rsp+2F0h+var_2C0]
0x180037665  mov     rcx, [rsp+2F0h+var_2A0]
0x18003766a  test    rcx, rcx
0x18003766d  jz      short loc_180037683
0x18003766f  mov     rax, [rcx]
0x180037672  mov     rax, [rax+10h]
0x180037676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003767b  xor     r10d, r10d
0x18003767e  mov     [rsp+2F0h+var_2A0], r10
0x180037683  test    rsi, rsi
0x180037686  jnz     short loc_1800376E8
0x180037688  test    edi, edi
0x18003768a  js      loc_180037978
0x180037690  test    r13, r13
0x180037693  jz      short loc_18003769D
0x180037695  mov     rcx, r13; this
0x180037698  call    ?InternalRelease@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalRelease(void)
0x18003769d  test    rbx, rbx
0x1800376a0  jz      short loc_1800376AA
0x1800376a2  mov     rcx, rbx; this
0x1800376a5  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x1800376aa  mov     rcx, [rsp+2F0h+Block]; Block
0x1800376af  cmp     rcx, [rsp+2F0h+var_280]
0x1800376b4  jz      short loc_1800376C2
0x1800376b6  call    cs:__imp_free
0x1800376bd  nop     dword ptr [rax+rax+00h]
0x1800376c2  mov     eax, edi
0x1800376c4  mov     rcx, [rbp+1F0h+var_50]
0x1800376cb  xor     rcx, rsp; StackCookie
0x1800376ce  call    __security_check_cookie
0x1800376d3  add     rsp, 2B8h
0x1800376da  pop     r15
0x1800376dc  pop     r14
0x1800376de  pop     r13
0x1800376e0  pop     r12
0x1800376e2  pop     rdi
0x1800376e3  pop     rsi
0x1800376e4  pop     rbx
0x1800376e5  pop     rbp
0x1800376e6  retn
0x1800376e8  mov     r14d, r10d
0x1800376eb  cmp     [rsp+2F0h+var_2B8], r10d
0x1800376f0  jbe     short loc_180037688
0x1800376f2  mov     r15d, r14d
0x1800376f5  mov     rcx, [rsi+r15*8]
0x1800376f9  test    rcx, rcx
0x1800376fc  jz      short loc_180037711
0x1800376fe  mov     rax, [rcx]
0x180037701  mov     rax, [rax+10h]
0x180037705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003770a  xor     r10d, r10d
0x18003770d  mov     [rsi+r15*8], r10
0x180037711  inc     r14d
0x180037714  cmp     r14d, [rsp+2F0h+var_2B8]
0x180037719  jnb     loc_180037688
0x18003771f  jmp     short loc_1800376F2
0x180037721  test    r8d, r8d
0x180037724  jnz     loc_180037656
0x18003772a  test    eax, eax
0x18003772c  jns     loc_18003756B
0x180037732  jmp     loc_180037660
0x180037737  cmp     cs:?g_doStackCaptures@@3HA, r10d; int g_doStackCaptures
0x18003773e  jnz     loc_180037656
0x180037744  test    eax, eax
0x180037746  jns     loc_180037465
0x18003774c  jmp     loc_180037660
0x180037751  cmp     cs:?g_doStackCaptures@@3HA, r10d; int g_doStackCaptures
0x180037758  jnz     loc_180037656
0x18003775e  test    eax, eax
0x180037760  jns     loc_180037487
0x180037766  jmp     loc_180037660
0x18003776b  cmp     cs:?g_doStackCaptures@@3HA, r10d; int g_doStackCaptures
0x180037772  jnz     loc_180037656
0x180037778  test    eax, eax
0x18003777a  jns     loc_1800374BD
0x180037780  jmp     loc_180037660
0x180037785  cmp     cs:?g_doStackCaptures@@3HA, r10d; int g_doStackCaptures
0x18003778c  jnz     loc_180037656
  ... truncated ...
```
