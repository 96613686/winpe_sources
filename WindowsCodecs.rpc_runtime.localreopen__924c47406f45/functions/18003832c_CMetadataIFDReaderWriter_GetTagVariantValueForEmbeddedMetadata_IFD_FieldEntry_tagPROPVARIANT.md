# CMetadataIFDReaderWriter::GetTagVariantValueForEmbeddedMetadata(IFD::FieldEntry *,tagPROPVARIANT *)

- ea: `0x18003832c`
- end: `0x180038bfa`
- name: `?GetTagVariantValueForEmbeddedMetadata@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z`
- size: `2254`
- prototype: `__int64 __fastcall(CStreamBase **this, PROPVARIANT *, PROPVARIANT *)`
- caller_count: `4`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800374f0`
- `0x180054d54`
- `0x180056f90`
- `0x1800573d0`

## callees

- `0x1800257d0`
- `0x180036cb4`
- `0x18003740c`
- `0x18003832c`
- `0x180039040`
- `0x1800402f4`
- `0x1800554f0`
- `0x180059c2c`
- `0x18009b5c0`
- `0x1800a35e4`
- `0x1800bb784`
- `0x1800e3c04`
- `0x1801a8d68`
- `0x1801a8fe0`
- `0x1801a9458`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18003863f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18003863f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038845`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038af1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038845`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038af1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800386e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800386e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038bef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038bef`

## pseudocode

```c
__int64 __fastcall CMetadataIFDReaderWriter::GetTagVariantValueForEmbeddedMetadata(
        CStreamBase **this,
        PROPVARIANT *a2,
        PROPVARIANT *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rdi
  int *v6; // r14
  int CodecFactory; // eax
  int v9; // esi
  unsigned int v10; // ecx
  __int64 v11; // rbx
  __int64 v12; // r13
  int v13; // eax
  int *v14; // rdi
  unsigned int i; // r14d
  HRESULT v16; // eax
  __int64 (__fastcall ***v17)(void *, GUID *, void **); // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdi
  int v21; // eax
  __int128 v22; // xmm0
  unsigned int v23; // eax
  void *v24; // xmm1_8
  PROPVARIANT *v25; // rax
  int v27; // ecx
  int v28; // ecx
  HRESULT v29; // eax
  void *v30; // rax
  int v31; // edx
  void *v32; // rsi
  union _LARGE_INTEGER v33; // rdx
  CStreamBase *v34; // rcx
  int v35; // ecx
  unsigned __int64 v36; // r9
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  int v39; // ecx
  int v40; // eax
  int v41; // ebx
  int v42; // eax
  int FullBufferFromStream; // eax
  __int64 v44; // rdx
  unsigned int *v45; // r14
  unsigned int v46; // r8d
  int *pv; // [rsp+30h] [rbp-59h]
  __int64 v48; // [rsp+38h] [rbp-51h] BYREF
  __int64 v49; // [rsp+40h] [rbp-49h] BYREF
  struct IStream *v50; // [rsp+48h] [rbp-41h] BYREF
  struct IWICMetadataReader *v51; // [rsp+50h] [rbp-39h] BYREF
  struct IWICMetadataWriter *v52; // [rsp+58h] [rbp-31h] BYREF
  __int64 v53; // [rsp+60h] [rbp-29h] BYREF
  void *v54; // [rsp+68h] [rbp-21h] BYREF
  int v55; // [rsp+70h] [rbp-19h] BYREF
  union _LARGE_INTEGER v56; // [rsp+78h] [rbp-11h]
  PROPVARIANT pvar[2]; // [rsp+80h] [rbp-9h] BYREF
  void *v58; // [rsp+90h] [rbp+7h]
  unsigned int v59; // [rsp+98h] [rbp+Fh]
  int *v60; // [rsp+A0h] [rbp+17h]
  struct IWICComponentFactory *v61; // [rsp+A8h] [rbp+1Fh] BYREF
  int v62; // [rsp+F8h] [rbp+6Fh] BYREF
  PROPVARIANT *pvarDest; // [rsp+100h] [rbp+77h]
  __int64 pulResult; // [rsp+108h] [rbp+7Fh] BYREF

  pvarDest = a3;
  v3 = *((unsigned __int16 *)a2 + 1);
  v4 = 0;
  v56.QuadPart = 0;
  v55 = 0;
  v62 = 0;
  pv = 0;
  v6 = 0;
  v61 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v50 = 0;
  *(_OWORD *)pvar = 0;
  v58 = 0;
  CodecFactory = GetCodecFactory(&v61);
  v9 = CodecFactory;
  if ( CodecFactory < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_38;
    v28 = CodecFactory;
    goto LABEL_71;
  }
  v9 = CMetadataIFDReaderWriter::CreateReaderOrWriter(
         (CMetadataIFDReaderWriter *)this,
         (struct IFD::FieldEntry *)a2,
         &v51,
         &v52,
         &v62);
  if ( v9 < 0 )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v9);
    goto LABEL_38;
  }
  v10 = v3;
  v59 = v3;
  v11 = 0;
  if ( !v62 )
  {
    LODWORD(v12) = 1;
    goto LABEL_7;
  }
  if ( v10 == 1 || v10 == 7 )
  {
    v9 = -2003292317;
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_38;
    v28 = -2003292317;
LABEL_71:
    DoStackCapture(v28);
    goto LABEL_38;
  }
  v12 = *((unsigned int *)a2 + 1);
  if ( (_DWORD)v12 == 1 )
  {
LABEL_7:
    v13 = *((_DWORD *)a2 + 2);
    v14 = &v55;
    v60 = &v55;
    v55 = v13;
    LOWORD(pvar[0]) = 13;
    pvar[1] = 0;
LABEL_8:
    for ( i = 0; ; ++i )
    {
      if ( i >= (unsigned int)v12 )
      {
        v22 = *(_OWORD *)pvar;
        v23 = (_DWORD)a2[2] & 0xFFFFFF4F;
        LOWORD(pvar[0]) = 0;
        v24 = v58;
        *((_DWORD *)a2 + 4) = v23 | 2;
        v25 = pvarDest;
        *((_OWORD *)a2 + 2) = v22;
        a2[6] = v24;
        if ( v25 )
        {
          v16 = PropVariantCopy(v25, a2 + 4);
          v9 = v16;
          if ( v16 < 0 )
          {
            if ( (_DWORD)g_doStackCaptures )
              goto LABEL_57;
          }
        }
        goto LABEL_37;
      }
      if ( *((_DWORD *)this + 40) )
      {
        if ( v52 )
          goto LABEL_12;
      }
      else if ( v51 )
      {
        goto LABEL_12;
      }
      LODWORD(pulResult) = 0;
      v16 = CMetadataIFDReaderWriter::CreateReaderOrWriter(
              (CMetadataIFDReaderWriter *)this,
              (struct IFD::FieldEntry *)a2,
              &v51,
              &v52,
              (int *)&pulResult);
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          goto LABEL_57;
        goto LABEL_37;
      }
LABEL_12:
      if ( *((_DWORD *)this + 40) )
      {
        v16 = ((__int64 (__fastcall *)(struct IWICMetadataWriter *, GUID *, __int64 *))v52->lpVtbl->QueryInterface)(
                v52,
                &IID_IWICPersistStream,
                &v53);
        v9 = v16;
        if ( v16 < 0 )
        {
          if ( (_DWORD)g_doStackCaptures )
            goto LABEL_57;
          goto LABEL_37;
        }
        v17 = (__int64 (__fastcall ***)(void *, GUID *, void **))v52;
      }
      else
      {
        v16 = ((__int64 (__fastcall *)(struct IWICMetadataReader *, GUID *, __int64 *))v51->lpVtbl->QueryInterface)(
                v51,
                &IID_IWICPersistStream,
                &v53);
        v9 = v16;
        if ( v16 < 0 )
        {
          if ( !(_DWORD)g_doStackCaptures )
            goto LABEL_37;
          goto LABEL_57;
        }
        v17 = (__int64 (__fastcall ***)(void *, GUID *, void **))v51;
      }
      v16 = (**v17)(v17, &IID_IUnknown, &v54);
      v19 = (unsigned int)g_doStackCaptures;
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_37;
        goto LABEL_57;
      }
      pulResult = 0;
      v48 = 0;
      if ( v62 )
      {
        v20 = *((unsigned int *)this + 32);
      }
      else
      {
        HIDWORD(pulResult) = 0;
        LODWORD(pulResult) = v14[i];
        v36 = *((unsigned int *)a2 + 1)
            * (unsigned __int64)(unsigned int)IFD::DataSize(v59, v18, (unsigned int)g_doStackCaptures);
        if ( v36 > 0xFFFFFFFF )
        {
          v9 = -2147024362;
          if ( !(_DWORD)v19 )
            goto LABEL_37;
          v27 = -2147024362;
          goto LABEL_58;
        }
        v11 = pulResult;
        v48 = (unsigned int)v36;
        v20 = (unsigned int)v36;
      }
      v21 = ((__int64 (__fastcall *)(struct IWICComponentFactory *, struct IStream **, __int64))v61->lpVtbl->CreateStream)(
              v61,
              &v50,
              v19);
      v9 = v21;
      if ( v21 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_37;
        DoStackCapture(v21);
        v6 = pv;
        goto LABEL_38;
      }
      v16 = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int64, __int64, __int64))(*(_QWORD *)v50 + 136LL))(
              v50,
              ((unsigned __int64)this[15] + 16) & -(__int64)(this[15] != 0),
              v11,
              v20);
      v11 = 0;
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_37;
        goto LABEL_57;
      }
      v16 = CStreamBase::HrCopyRangesToIStream(this[15], v50);
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_37;
        goto LABEL_57;
      }
      v14 = v60;
      if ( v62 )
      {
        v56.HighPart = 0;
        v56.LowPart = v60[i];
        v16 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v50 + 40LL))(
                v50,
                v56.LowPart,
                0,
                0);
        v9 = v16;
        if ( v16 < 0 )
        {
          if ( !(_DWORD)g_doStackCaptures )
            goto LABEL_37;
LABEL_57:
          v27 = v16;
LABEL_58:
          DoStackCapture(v27);
          goto LABEL_37;
        }
      }
      v16 = (*(__int64 (__fastcall **)(__int64, struct IStream *, char *, _QWORD))(*(_QWORD *)v53 + 64LL))(
              v53,
              v50,
              (char *)this + 100,
              *((unsigned int *)this + 33));
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_37;
        goto LABEL_57;
      }
      if ( (_DWORD)v12 == 1 )
      {
        pvar[1] = v54;
      }
      else
      {
        v37 = v58;
        v38 = 3LL * i;
        *((_WORD *)v58 + 4 * v38) = 13;
        v37[v38 + 1] = v54;
      }
      v54 = 0;
      if ( v51 )
      {
        ((void (__fastcall *)(struct IWICMetadataReader *))v51->lpVtbl->Release)(v51);
        v51 = 0;
      }
      if ( v52 )
      {
        ((void (__fastcall *)(struct IWICMetadataWriter *))v52->lpVtbl->Release)(v52);
        v52 = 0;
      }
      if ( v53 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
        v53 = 0;
      }
      if ( v50 )
      {
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v50 + 16LL))(v50);
        v50 = 0;
      }
    }
  }
  v49 = 0;
  LODWORD(v48) = 0;
  v29 = HashSet<unsigned long,IntegerHashSetTraits<unsigned long>>::Init(&v48, 13);
  v9 = v29;
  if ( v29 < 0 )
    goto LABEL_83;
  if ( (unsigned __int64)(24 * v12) > 0xFFFFFFFF )
  {
    v9 = -2147024362;
LABEL_96:
    if ( !(_DWORD)g_doStackCaptures )
    {
LABEL_86:
      if ( v49 )
        win_scope::close_delete_array::close<CArray<unsigned long,IntegerHashSetTraits<unsigned long>,CDefaultAllocator>>(&v49);
      goto LABEL_38;
    }
    v35 = v9;
LABEL_85:
    DoStackCapture(v35);
    goto LABEL_86;
  }
  LODWORD(pulResult) = 24 * v12;
  v30 = CoTaskMemAlloc((unsigned int)(24 * v12));
  v32 = v30;
  if ( !v30 )
  {
    v9 = -2147024882;
    goto LABEL_96;
  }
  if ( (_DWORD)v12 )
  {
    LOBYTE(v31) = 0;
    memset_0(v30, v31, 24 * v12);
  }
  v33.QuadPart = *((unsigned int *)a2 + 2);
  v34 = (CStreamBase *)((char *)this[15] + 16);
  LOWORD(pvar[0]) = 4108;
  LODWORD(pvar[1]) = v12;
  v58 = v32;
  v56 = v33;
  v29 = CStreamBase::Seek(v34, v33, 0, 0);
  v9 = v29;
  if ( v29 < 0 || (v29 = ULongLongToULong(4 * v12, (ULONG *)&pulResult), v9 = v29, v29 < 0) )
  {
LABEL_83:
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_86;
    v35 = v29;
    goto LABEL_85;
  }
  pv = (int *)CoTaskMemAlloc((unsigned int)pulResult);
  v6 = pv;
  if ( !pv )
  {
    v9 = -2147024882;
    goto LABEL_96;
  }
  FullBufferFromStream = ReadFullBufferFromStream(
                           (struct IStream *)(((unsigned __int64)this[15] + 16) & -(__int64)(this[15] != 0)),
                           pv,
                           pulResult);
  v41 = (int)g_doStackCaptures;
  v9 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(FullBufferFromStream);
    goto LABEL_86;
  }
  while ( 1 )
  {
    if ( (unsigned int)v4 >= (unsigned int)v12 )
    {
      v11 = 0;
      v60 = v6;
      v14 = v6;
      if ( v49 )
        win_scope::close_delete_array::close<CArray<unsigned long,IntegerHashSetTraits<unsigned long>,CDefaultAllocator>>(&v49);
      goto LABEL_8;
    }
    v44 = v4;
    if ( (*((_BYTE *)this + 132) & 1) != 0 )
      v6[v44] = HIBYTE(v6[v44]) | ((BYTE2(v6[v44]) | (((v6[v44] << 8) | BYTE1(v6[v44])) << 8)) << 8);
    v45 = (unsigned int *)&v6[v44];
    if ( (unsigned __int8)HashSet<unsigned long,IntegerHashSetTraits<unsigned long>>::SearchBucketForKey(
                            &v48,
                            v45,
                            101 * *v45 % (unsigned __int64)(unsigned int)v48) )
      break;
    v42 = HashSet<unsigned long,IntegerHashSetTraits<unsigned long>>::Insert(&v48, v45);
    v9 = v42;
    if ( v42 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v42);
      goto LABEL_108;
    }
    v46 = 2;
    if ( (_DWORD)v4 != (_DWORD)v12 - 1 )
      v46 = 6;
    v40 = CMetadataIFDReaderWriter::ValidateStreamOffsetRange((CMetadataIFDReaderWriter *)this, *v45, v46);
    v41 = (int)g_doStackCaptures;
    v9 = v40;
    if ( v40 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
      {
        v39 = v40;
        goto LABEL_107;
      }
      goto LABEL_108;
    }
    v6 = pv;
    v4 = (unsigned int)(v4 + 1);
  }
  v9 = -2003292320;
  if ( v41 )
  {
    v39 = -2003292320;
LABEL_107:
    DoStackCapture(v39);
  }
LABEL_108:
  if ( v49 )
    win_scope::close_delete_array::close<CArray<unsigned long,IntegerHashSetTraits<unsigned long>,CDefaultAllocator>>(&v49);
LABEL_37:
  v6 = pv;
LABEL_38:
  if ( v61 )
    ((void (__fastcall *)(struct IWICComponentFactory *))v61->lpVtbl->Release)(v61);
  if ( v51 )
    ((void (__fastcall *)(struct IWICMetadataReader *))v51->lpVtbl->Release)(v51);
  if ( v52 )
    ((void (__fastcall *)(struct IWICMetadataWriter *))v52->lpVtbl->Release)(v52);
  if ( v53 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    v53 = 0;
  }
  if ( v50 )
  {
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
  if ( v54 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
  }
  PropVariantClear(pvar);
  if ( v6 )
    CoTaskMemFree(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003832c  mov     [rsp-8+arg_0], rbx
0x180038331  mov     [rsp-8+pvarDest], r8
0x180038336  push    rbp
0x180038337  push    rsi
0x180038338  push    rdi
0x180038339  push    r12
0x18003833b  push    r13
0x18003833d  push    r14
0x18003833f  push    r15
0x180038341  lea     rbp, [rsp-27h]
0x180038346  sub     rsp, 0B0h
0x18003834d  movzx   ebx, word ptr [rdx+2]
0x180038351  xor     edi, edi
0x180038353  mov     r15, rcx
0x180038356  mov     [rbp+57h+var_68], rdi
0x18003835a  xorps   xmm0, xmm0
0x18003835d  mov     [rbp+57h+var_70], edi
0x180038360  xor     eax, eax
0x180038362  mov     [rbp+57h+arg_8], edi
0x180038365  lea     rcx, [rbp+57h+var_38]; struct IWICComponentFactory **
0x180038369  mov     [rbp+57h+pv], rdi
0x18003836d  mov     r14d, edi
0x180038370  mov     [rbp+57h+var_38], rdi
0x180038374  mov     [rbp+57h+var_90], rdi
0x180038378  mov     r12, rdx
0x18003837b  mov     [rbp+57h+var_88], rdi
0x18003837f  mov     [rbp+57h+var_80], rdi
0x180038383  mov     [rbp+57h+var_78], rdi
0x180038387  mov     [rbp+57h+var_98], rdi
0x18003838b  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18003838f  mov     [rbp+57h+var_50], rax
0x180038393  call    ?GetCodecFactory@@YAJPEAPEAUIWICComponentFactory@@@Z; GetCodecFactory(IWICComponentFactory * *)
0x180038398  mov     esi, eax
0x18003839a  test    eax, eax
0x18003839c  js      loc_1800387C2
0x1800383a2  lea     rax, [rbp+57h+arg_8]
0x1800383a6  mov     rdx, r12; struct IFD::FieldEntry *
0x1800383a9  lea     r9, [rbp+57h+var_88]; struct IWICMetadataWriter **
0x1800383ad  mov     [rsp+0E0h+var_C0], rax; int *
0x1800383b2  lea     r8, [rbp+57h+var_90]; struct IWICMetadataReader **
0x1800383b6  mov     rcx, r15; this
0x1800383b9  call    ?CreateReaderOrWriter@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAPEAUIWICMetadataReader@@PEAPEAUIWICMetadataWriter@@PEAH@Z; CMetadataIFDReaderWriter::CreateReaderOrWriter(IFD::FieldEntry *,IWICMetadataReader * *,IWICMetadataWriter * *,int *)
0x1800383be  mov     esi, eax
0x1800383c0  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800383c6  test    esi, esi
0x1800383c8  js      loc_1800387DC
0x1800383ce  mov     ecx, ebx
0x1800383d0  mov     [rbp+57h+var_48], ebx
0x1800383d3  xor     ebx, ebx
0x1800383d5  mov     edx, 0Dh
0x1800383da  cmp     [rbp+57h+arg_8], ebx
0x1800383dd  jz      loc_18003870D
0x1800383e3  cmp     ecx, 1
0x1800383e6  jz      loc_180038ABE
0x1800383ec  cmp     ecx, 7
0x1800383ef  jz      loc_180038ABE
0x1800383f5  mov     r13d, [r12+4]
0x1800383fa  cmp     r13d, 1
0x1800383fe  jnz     loc_180038809
0x180038404  mov     eax, [r12+8]
0x180038409  lea     rdi, [rbp+57h+var_70]
0x18003840d  mov     [rbp+57h+var_40], rdi
0x180038411  mov     [rbp+57h+var_70], eax
0x180038414  mov     word ptr [rbp+57h+pvar], dx
0x180038418  mov     [rbp+57h+pvar+8], rbx
0x18003841c  mov     r14d, ebx
0x18003841f  cmp     r14d, r13d
0x180038422  jnb     loc_180038607
0x180038428  cmp     [r15+0A0h], ebx
0x18003842f  jnz     loc_180038BDD
0x180038435  cmp     [rbp+57h+var_90], rbx
0x180038439  jz      loc_18003892F
0x18003843f  lea     r8, [rbp+57h+var_80]
0x180038443  lea     rdx, IID_IWICPersistStream
0x18003844a  cmp     [r15+0A0h], ebx
0x180038451  jnz     loc_180038718
0x180038457  mov     rcx, [rbp+57h+var_90]
0x18003845b  mov     rax, [rcx]
0x18003845e  mov     rax, [rax]
0x180038461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038466  mov     esi, eax
0x180038468  test    eax, eax
0x18003846a  js      loc_1800387AD
0x180038470  mov     rcx, [rbp+57h+var_90]
0x180038474  mov     rax, [rcx]
0x180038477  lea     r8, [rbp+57h+var_78]
0x18003847b  lea     rdx, IID_IUnknown
0x180038482  mov     rax, [rax]
0x180038485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003848a  mov     r8d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180038491  mov     esi, eax
0x180038493  test    eax, eax
0x180038495  js      loc_18003879B
0x18003849b  cmp     [rbp+57h+arg_8], 0
0x18003849f  mov     [rbp+57h+pulResult], rbx
0x1800384a3  mov     [rbp+57h+var_A8], 0
0x1800384ab  jz      loc_1800388E8
0x1800384b1  mov     edi, [r15+80h]
0x1800384b8  mov     rcx, [rbp+57h+var_38]
0x1800384bc  lea     rdx, [rbp+57h+var_98]
0x1800384c0  mov     rax, [rcx]
0x1800384c3  mov     rax, [rax+70h]
0x1800384c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384cc  mov     esi, eax
0x1800384ce  test    eax, eax
0x1800384d0  js      loc_180038752
0x1800384d6  mov     rdx, [r15+78h]
0x1800384da  mov     r9, rdi
0x1800384dd  mov     rcx, [rbp+57h+var_98]
0x1800384e1  lea     rax, [rdx+10h]
0x1800384e5  neg     rdx
0x1800384e8  mov     r8, [rcx]
0x1800384eb  sbb     rdx, rdx
0x1800384ee  and     rdx, rax
0x1800384f1  mov     rax, [r8+88h]
0x1800384f8  mov     r8, rbx
0x1800384fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038500  xor     ebx, ebx
0x180038502  mov     esi, eax
0x180038504  test    eax, eax
0x180038506  js      loc_18003873A
0x18003850c  mov     rdx, [rbp+57h+var_98]; struct IStream *
0x180038510  mov     rcx, [r15+78h]; this
0x180038514  call    ?HrCopyRangesToIStream@CStreamBase@@UEAAJPEAUIStream@@@Z; CStreamBase::HrCopyRangesToIStream(IStream *)
0x180038519  mov     esi, eax
0x18003851b  test    eax, eax
0x18003851d  js      loc_180038771
0x180038523  mov     rdi, [rbp+57h+var_40]
0x180038527  cmp     [rbp+57h+arg_8], ebx
0x18003852a  jz      short loc_18003855C
0x18003852c  mov     eax, r14d
0x18003852f  xor     r9d, r9d
0x180038532  mov     dword ptr [rbp+57h+var_68+4], ebx
0x180038535  xor     r8d, r8d
0x180038538  mov     ecx, [rdi+rax*4]
0x18003853b  mov     dword ptr [rbp+57h+var_68], ecx
0x18003853e  mov     rcx, [rbp+57h+var_98]
0x180038542  mov     rdx, [rbp+57h+var_68]
0x180038546  mov     rax, [rcx]
0x180038549  mov     rax, [rax+28h]
0x18003854d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038552  mov     esi, eax
0x180038554  test    eax, eax
0x180038556  js      loc_1800387F0
0x18003855c  mov     rcx, [rbp+57h+var_80]
0x180038560  lea     r8, [r15+64h]
0x180038564  mov     r9d, [r15+84h]
0x18003856b  mov     rdx, [rbp+57h+var_98]
0x18003856f  mov     rax, [rcx]
0x180038572  mov     rax, [rax+40h]
0x180038576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003857b  mov     esi, eax
0x18003857d  test    eax, eax
0x18003857f  js      loc_180038786
0x180038585  cmp     r13d, 1
0x180038589  jnz     loc_18003898B
0x18003858f  mov     rax, [rbp+57h+var_78]
0x180038593  mov     [rbp+57h+pvar+8], rax
0x180038597  mov     rcx, [rbp+57h+var_90]
0x18003859b  mov     [rbp+57h+var_78], rbx
0x18003859f  test    rcx, rcx
0x1800385a2  jz      short loc_1800385B4
0x1800385a4  mov     rax, [rcx]
0x1800385a7  mov     rax, [rax+10h]
0x1800385ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385b0  mov     [rbp+57h+var_90], rbx
0x1800385b4  mov     rcx, [rbp+57h+var_88]
0x1800385b8  test    rcx, rcx
0x1800385bb  jz      short loc_1800385CD
0x1800385bd  mov     rax, [rcx]
0x1800385c0  mov     rax, [rax+10h]
0x1800385c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385c9  mov     [rbp+57h+var_88], rbx
0x1800385cd  mov     rcx, [rbp+57h+var_80]
0x1800385d1  test    rcx, rcx
0x1800385d4  jz      short loc_1800385E6
0x1800385d6  mov     rax, [rcx]
0x1800385d9  mov     rax, [rax+10h]
0x1800385dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385e2  mov     [rbp+57h+var_80], rbx
0x1800385e6  mov     rcx, [rbp+57h+var_98]
0x1800385ea  test    rcx, rcx
0x1800385ed  jz      short loc_1800385FF
0x1800385ef  mov     rax, [rcx]
0x1800385f2  mov     rax, [rax+10h]
0x1800385f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385fb  mov     [rbp+57h+var_98], rbx
0x1800385ff  inc     r14d
0x180038602  jmp     loc_18003841F
0x180038607  mov     eax, [r12+10h]
0x18003860c  lea     rdx, [r12+20h]; pvarSrc
0x180038611  movups  xmm0, xmmword ptr [rbp+57h+pvar]
0x180038615  and     eax, 0FFFFFF4Fh
0x18003861a  mov     word ptr [rbp+57h+pvar], bx
0x18003861e  movsd   xmm1, [rbp+57h+var_50]
0x180038623  or      eax, 2
0x180038626  mov     [r12+10h], eax
0x18003862b  mov     rax, [rbp+57h+pvarDest]
0x18003862f  movups  xmmword ptr [rdx], xmm0
0x180038632  movsd   qword ptr [rdx+10h], xmm1
0x180038637  test    rax, rax
0x18003863a  jz      short loc_18003864F
0x18003863c  mov     rcx, rax; pvarDest
0x18003863f  call    cs:__imp_PropVariantCopy
0x180038645  mov     esi, eax
0x180038647  test    eax, eax
0x180038649  js      loc_1800388D7
0x18003864f  mov     r14, [rbp+57h+pv]
0x180038653  mov     rcx, [rbp+57h+var_38]
0x180038657  test    rcx, rcx
0x18003865a  jz      short loc_180038668
0x18003865c  mov     rax, [rcx]
0x18003865f  mov     rax, [rax+10h]
0x180038663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038668  mov     rcx, [rbp+57h+var_90]
0x18003866c  test    rcx, rcx
0x18003866f  jz      short loc_18003867D
0x180038671  mov     rax, [rcx]
0x180038674  mov     rax, [rax+10h]
0x180038678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003867d  mov     rcx, [rbp+57h+var_88]
0x180038681  test    rcx, rcx
0x180038684  jz      short loc_180038692
0x180038686  mov     rax, [rcx]
0x180038689  mov     rax, [rax+10h]
0x18003868d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038692  mov     rcx, [rbp+57h+var_80]
0x180038696  test    rcx, rcx
0x180038699  jz      short loc_1800386AB
0x18003869b  mov     rax, [rcx]
0x18003869e  mov     rax, [rax+10h]
0x1800386a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386a7  mov     [rbp+57h+var_80], rbx
0x1800386ab  mov     rcx, [rbp+57h+var_98]
0x1800386af  test    rcx, rcx
0x1800386b2  jz      short loc_1800386C4
0x1800386b4  mov     rax, [rcx]
0x1800386b7  mov     rax, [rax+10h]
0x1800386bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386c0  mov     [rbp+57h+var_98], rbx
0x1800386c4  mov     rcx, [rbp+57h+var_78]
0x1800386c8  test    rcx, rcx
0x1800386cb  jz      short loc_1800386DD
0x1800386cd  mov     rax, [rcx]
0x1800386d0  mov     rax, [rax+10h]
0x1800386d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386d9  mov     [rbp+57h+var_78], rbx
0x1800386dd  lea     rcx, [rbp+57h+pvar]; pvar
0x1800386e1  call    cs:__imp_PropVariantClear
0x1800386e7  test    r14, r14
0x1800386ea  jnz     loc_180038BEC
0x1800386f0  mov     rbx, [rsp+0E0h+arg_0]
0x1800386f8  mov     eax, esi
0x1800386fa  add     rsp, 0B0h
0x180038701  pop     r15
0x180038703  pop     r14
0x180038705  pop     r13
0x180038707  pop     r12
0x180038709  pop     rdi
0x18003870a  pop     rsi
0x18003870b  pop     rbp
0x18003870c  retn
0x18003870d  mov     r13d, 1
0x180038713  jmp     loc_180038404
0x180038718  mov     rcx, [rbp+57h+var_88]
0x18003871c  mov     rax, [rcx]
0x18003871f  mov     rax, [rax]
0x180038722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038727  mov     esi, eax
0x180038729  test    eax, eax
0x18003872b  js      loc_1800389E8
0x180038731  mov     rcx, [rbp+57h+var_88]
0x180038735  jmp     loc_180038474
0x18003873a  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x180038740  jz      loc_1800389CE
0x180038746  mov     ecx, eax; int
0x180038748  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18003874d  jmp     loc_18003864F
0x180038752  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180038759  jz      loc_1800389BF
0x18003875f  mov     ecx, eax; int
0x180038761  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180038766  mov     r14, [rbp+57h+pv]
0x18003876a  xor     ebx, ebx
0x18003876c  jmp     loc_180038653
0x180038771  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x180038777  jnz     short loc_180038746
0x180038779  test    eax, eax
0x18003877b  jns     loc_180038523
0x180038781  jmp     loc_18003864F
0x180038786  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x18003878c  jnz     short loc_180038746
0x18003878e  test    eax, eax
0x180038790  jns     loc_180038585
0x180038796  jmp     loc_18003864F
0x18003879b  test    r8d, r8d
0x18003879e  jnz     short loc_180038746
0x1800387a0  test    eax, eax
0x1800387a2  jns     loc_18003849B
0x1800387a8  jmp     loc_18003864F
  ... truncated ...
```
