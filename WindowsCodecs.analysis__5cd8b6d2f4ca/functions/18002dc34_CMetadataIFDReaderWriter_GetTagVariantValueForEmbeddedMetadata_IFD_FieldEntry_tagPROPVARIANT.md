# CMetadataIFDReaderWriter::GetTagVariantValueForEmbeddedMetadata(IFD::FieldEntry *,tagPROPVARIANT *)

- ea: `0x18002dc34`
- end: `0x18002e521`
- name: `?GetTagVariantValueForEmbeddedMetadata@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z`
- size: `2285`
- prototype: `__int64 __fastcall(CStreamBase **this, PROPVARIANT *, PROPVARIANT *)`
- caller_count: `4`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002cde0`
- `0x180049c00`
- `0x18004b590`
- `0x18004b9d0`

## callees

- `0x180028930`
- `0x18002dc34`
- `0x180031b78`
- `0x18004a800`
- `0x18004c8fc`
- `0x18004dbd4`
- `0x1800542e8`
- `0x180055880`
- `0x18009cad0`
- `0x1800a4eb0`
- `0x1800bd9d4`
- `0x1800e6af4`
- `0x1801ac218`
- `0x1801ac4a4`
- `0x1801ac930`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002df47`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002df47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e15a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e40c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e15a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e40c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e510`

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
0x18002dc34  mov     [rsp-8+arg_0], rbx
0x18002dc39  mov     [rsp-8+pvarDest], r8
0x18002dc3e  push    rbp
0x18002dc3f  push    rsi
0x18002dc40  push    rdi
0x18002dc41  push    r12
0x18002dc43  push    r13
0x18002dc45  push    r14
0x18002dc47  push    r15
0x18002dc49  lea     rbp, [rsp-27h]
0x18002dc4e  sub     rsp, 0B0h
0x18002dc55  movzx   ebx, word ptr [rdx+2]
0x18002dc59  xor     edi, edi
0x18002dc5b  mov     r15, rcx
0x18002dc5e  mov     [rbp+57h+var_68], rdi
0x18002dc62  xorps   xmm0, xmm0
0x18002dc65  mov     [rbp+57h+var_70], edi
0x18002dc68  xor     eax, eax
0x18002dc6a  mov     [rbp+57h+arg_8], edi
0x18002dc6d  lea     rcx, [rbp+57h+var_38]; struct IWICComponentFactory **
0x18002dc71  mov     [rbp+57h+pv], rdi
0x18002dc75  mov     r14d, edi
0x18002dc78  mov     [rbp+57h+var_38], rdi
0x18002dc7c  mov     [rbp+57h+var_90], rdi
0x18002dc80  mov     r12, rdx
0x18002dc83  mov     [rbp+57h+var_88], rdi
0x18002dc87  mov     [rbp+57h+var_80], rdi
0x18002dc8b  mov     [rbp+57h+var_78], rdi
0x18002dc8f  mov     [rbp+57h+var_98], rdi
0x18002dc93  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18002dc97  mov     [rbp+57h+var_50], rax
0x18002dc9b  call    ?GetCodecFactory@@YAJPEAPEAUIWICComponentFactory@@@Z; GetCodecFactory(IWICComponentFactory * *)
0x18002dca0  mov     esi, eax
0x18002dca2  test    eax, eax
0x18002dca4  js      loc_18002E0D7
0x18002dcaa  lea     rax, [rbp+57h+arg_8]
0x18002dcae  mov     rdx, r12; struct IFD::FieldEntry *
0x18002dcb1  lea     r9, [rbp+57h+var_88]; struct IWICMetadataWriter **
0x18002dcb5  mov     [rsp+0E0h+var_C0], rax; int *
0x18002dcba  lea     r8, [rbp+57h+var_90]; struct IWICMetadataReader **
0x18002dcbe  mov     rcx, r15; this
0x18002dcc1  call    ?CreateReaderOrWriter@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAPEAUIWICMetadataReader@@PEAPEAUIWICMetadataWriter@@PEAH@Z; CMetadataIFDReaderWriter::CreateReaderOrWriter(IFD::FieldEntry *,IWICMetadataReader * *,IWICMetadataWriter * *,int *)
0x18002dcc6  mov     esi, eax
0x18002dcc8  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18002dcce  test    esi, esi
0x18002dcd0  js      loc_18002E0F1
0x18002dcd6  mov     ecx, ebx
0x18002dcd8  mov     [rbp+57h+var_48], ebx
0x18002dcdb  xor     ebx, ebx
0x18002dcdd  mov     edx, 0Dh
0x18002dce2  cmp     [rbp+57h+arg_8], ebx
0x18002dce5  jz      loc_18002E022
0x18002dceb  cmp     ecx, 1
0x18002dcee  jz      loc_18002E3D9
0x18002dcf4  cmp     ecx, 7
0x18002dcf7  jz      loc_18002E3D9
0x18002dcfd  mov     r13d, [r12+4]
0x18002dd02  cmp     r13d, 1
0x18002dd06  jnz     loc_18002E11E
0x18002dd0c  mov     eax, [r12+8]
0x18002dd11  lea     rdi, [rbp+57h+var_70]
0x18002dd15  mov     [rbp+57h+var_40], rdi
0x18002dd19  mov     [rbp+57h+var_70], eax
0x18002dd1c  mov     word ptr [rbp+57h+pvar], dx
0x18002dd20  mov     [rbp+57h+pvar+8], rbx
0x18002dd24  mov     r14d, ebx
0x18002dd27  cmp     r14d, r13d
0x18002dd2a  jnb     loc_18002DF0F
0x18002dd30  cmp     [r15+0A0h], ebx
0x18002dd37  jnz     loc_18002E4FE
0x18002dd3d  cmp     [rbp+57h+var_90], rbx
0x18002dd41  jz      loc_18002E24A
0x18002dd47  lea     r8, [rbp+57h+var_80]
0x18002dd4b  lea     rdx, IID_IWICPersistStream
0x18002dd52  cmp     [r15+0A0h], ebx
0x18002dd59  jnz     loc_18002E02D
0x18002dd5f  mov     rcx, [rbp+57h+var_90]
0x18002dd63  mov     rax, [rcx]
0x18002dd66  mov     rax, [rax]
0x18002dd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd6e  mov     esi, eax
0x18002dd70  test    eax, eax
0x18002dd72  js      loc_18002E0C2
0x18002dd78  mov     rcx, [rbp+57h+var_90]
0x18002dd7c  mov     rax, [rcx]
0x18002dd7f  lea     r8, [rbp+57h+var_78]
0x18002dd83  lea     rdx, IID_IUnknown
0x18002dd8a  mov     rax, [rax]
0x18002dd8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd92  mov     r8d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18002dd99  mov     esi, eax
0x18002dd9b  test    eax, eax
0x18002dd9d  js      loc_18002E0B0
0x18002dda3  cmp     [rbp+57h+arg_8], 0
0x18002dda7  mov     [rbp+57h+pulResult], rbx
0x18002ddab  mov     [rbp+57h+var_A8], 0
0x18002ddb3  jz      loc_18002E203
0x18002ddb9  mov     edi, [r15+80h]
0x18002ddc0  mov     rcx, [rbp+57h+var_38]
0x18002ddc4  lea     rdx, [rbp+57h+var_98]
0x18002ddc8  mov     rax, [rcx]
0x18002ddcb  mov     rax, [rax+70h]
0x18002ddcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddd4  mov     esi, eax
0x18002ddd6  test    eax, eax
0x18002ddd8  js      loc_18002E067
0x18002ddde  mov     rdx, [r15+78h]
0x18002dde2  mov     r9, rdi
0x18002dde5  mov     rcx, [rbp+57h+var_98]
0x18002dde9  lea     rax, [rdx+10h]
0x18002dded  neg     rdx
0x18002ddf0  mov     r8, [rcx]
0x18002ddf3  sbb     rdx, rdx
0x18002ddf6  and     rdx, rax
0x18002ddf9  mov     rax, [r8+88h]
0x18002de00  mov     r8, rbx
0x18002de03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de08  xor     ebx, ebx
0x18002de0a  mov     esi, eax
0x18002de0c  test    eax, eax
0x18002de0e  js      loc_18002E04F
0x18002de14  mov     rdx, [rbp+57h+var_98]; struct IStream *
0x18002de18  mov     rcx, [r15+78h]; this
0x18002de1c  call    ?HrCopyRangesToIStream@CStreamBase@@UEAAJPEAUIStream@@@Z; CStreamBase::HrCopyRangesToIStream(IStream *)
0x18002de21  mov     esi, eax
0x18002de23  test    eax, eax
0x18002de25  js      loc_18002E086
0x18002de2b  mov     rdi, [rbp+57h+var_40]
0x18002de2f  cmp     [rbp+57h+arg_8], ebx
0x18002de32  jz      short loc_18002DE64
0x18002de34  mov     eax, r14d
0x18002de37  xor     r9d, r9d
0x18002de3a  mov     dword ptr [rbp+57h+var_68+4], ebx
0x18002de3d  xor     r8d, r8d
0x18002de40  mov     ecx, [rdi+rax*4]
0x18002de43  mov     dword ptr [rbp+57h+var_68], ecx
0x18002de46  mov     rcx, [rbp+57h+var_98]
0x18002de4a  mov     rdx, [rbp+57h+var_68]
0x18002de4e  mov     rax, [rcx]
0x18002de51  mov     rax, [rax+28h]
0x18002de55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de5a  mov     esi, eax
0x18002de5c  test    eax, eax
0x18002de5e  js      loc_18002E105
0x18002de64  mov     rcx, [rbp+57h+var_80]
0x18002de68  lea     r8, [r15+64h]
0x18002de6c  mov     r9d, [r15+84h]
0x18002de73  mov     rdx, [rbp+57h+var_98]
0x18002de77  mov     rax, [rcx]
0x18002de7a  mov     rax, [rax+40h]
0x18002de7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de83  mov     esi, eax
0x18002de85  test    eax, eax
0x18002de87  js      loc_18002E09B
0x18002de8d  cmp     r13d, 1
0x18002de91  jnz     loc_18002E2A6
0x18002de97  mov     rax, [rbp+57h+var_78]
0x18002de9b  mov     [rbp+57h+pvar+8], rax
0x18002de9f  mov     rcx, [rbp+57h+var_90]
0x18002dea3  mov     [rbp+57h+var_78], rbx
0x18002dea7  test    rcx, rcx
0x18002deaa  jz      short loc_18002DEBC
0x18002deac  mov     rax, [rcx]
0x18002deaf  mov     rax, [rax+10h]
0x18002deb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002deb8  mov     [rbp+57h+var_90], rbx
0x18002debc  mov     rcx, [rbp+57h+var_88]
0x18002dec0  test    rcx, rcx
0x18002dec3  jz      short loc_18002DED5
0x18002dec5  mov     rax, [rcx]
0x18002dec8  mov     rax, [rax+10h]
0x18002decc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ded1  mov     [rbp+57h+var_88], rbx
0x18002ded5  mov     rcx, [rbp+57h+var_80]
0x18002ded9  test    rcx, rcx
0x18002dedc  jz      short loc_18002DEEE
0x18002dede  mov     rax, [rcx]
0x18002dee1  mov     rax, [rax+10h]
0x18002dee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002deea  mov     [rbp+57h+var_80], rbx
0x18002deee  mov     rcx, [rbp+57h+var_98]
0x18002def2  test    rcx, rcx
0x18002def5  jz      short loc_18002DF07
0x18002def7  mov     rax, [rcx]
0x18002defa  mov     rax, [rax+10h]
0x18002defe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df03  mov     [rbp+57h+var_98], rbx
0x18002df07  inc     r14d
0x18002df0a  jmp     loc_18002DD27
0x18002df0f  mov     eax, [r12+10h]
0x18002df14  lea     rdx, [r12+20h]; pvarSrc
0x18002df19  movups  xmm0, xmmword ptr [rbp+57h+pvar]
0x18002df1d  and     eax, 0FFFFFF4Fh
0x18002df22  mov     word ptr [rbp+57h+pvar], bx
0x18002df26  movsd   xmm1, [rbp+57h+var_50]
0x18002df2b  or      eax, 2
0x18002df2e  mov     [r12+10h], eax
0x18002df33  mov     rax, [rbp+57h+pvarDest]
0x18002df37  movups  xmmword ptr [rdx], xmm0
0x18002df3a  movsd   qword ptr [rdx+10h], xmm1
0x18002df3f  test    rax, rax
0x18002df42  jz      short loc_18002DF5D
0x18002df44  mov     rcx, rax; pvarDest
0x18002df47  call    cs:__imp_PropVariantCopy
0x18002df4e  nop     dword ptr [rax+rax+00h]
0x18002df53  mov     esi, eax
0x18002df55  test    eax, eax
0x18002df57  js      loc_18002E1F2
0x18002df5d  mov     r14, [rbp+57h+pv]
0x18002df61  mov     rcx, [rbp+57h+var_38]
0x18002df65  test    rcx, rcx
0x18002df68  jz      short loc_18002DF76
0x18002df6a  mov     rax, [rcx]
0x18002df6d  mov     rax, [rax+10h]
0x18002df71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df76  mov     rcx, [rbp+57h+var_90]
0x18002df7a  test    rcx, rcx
0x18002df7d  jz      short loc_18002DF8B
0x18002df7f  mov     rax, [rcx]
0x18002df82  mov     rax, [rax+10h]
0x18002df86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df8b  mov     rcx, [rbp+57h+var_88]
0x18002df8f  test    rcx, rcx
0x18002df92  jz      short loc_18002DFA0
0x18002df94  mov     rax, [rcx]
0x18002df97  mov     rax, [rax+10h]
0x18002df9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfa0  mov     rcx, [rbp+57h+var_80]
0x18002dfa4  test    rcx, rcx
0x18002dfa7  jz      short loc_18002DFB9
0x18002dfa9  mov     rax, [rcx]
0x18002dfac  mov     rax, [rax+10h]
0x18002dfb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfb5  mov     [rbp+57h+var_80], rbx
0x18002dfb9  mov     rcx, [rbp+57h+var_98]
0x18002dfbd  test    rcx, rcx
0x18002dfc0  jz      short loc_18002DFD2
0x18002dfc2  mov     rax, [rcx]
0x18002dfc5  mov     rax, [rax+10h]
0x18002dfc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfce  mov     [rbp+57h+var_98], rbx
0x18002dfd2  mov     rcx, [rbp+57h+var_78]
0x18002dfd6  test    rcx, rcx
0x18002dfd9  jz      short loc_18002DFEB
0x18002dfdb  mov     rax, [rcx]
0x18002dfde  mov     rax, [rax+10h]
0x18002dfe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfe7  mov     [rbp+57h+var_78], rbx
0x18002dfeb  lea     rcx, [rbp+57h+pvar]; pvar
0x18002dfef  call    cs:__imp_PropVariantClear
0x18002dff6  nop     dword ptr [rax+rax+00h]
0x18002dffb  test    r14, r14
0x18002dffe  jnz     loc_18002E50D
0x18002e004  mov     rbx, [rsp+0E0h+arg_0]
0x18002e00c  mov     eax, esi
0x18002e00e  add     rsp, 0B0h
0x18002e015  pop     r15
0x18002e017  pop     r14
0x18002e019  pop     r13
0x18002e01b  pop     r12
0x18002e01d  pop     rdi
0x18002e01e  pop     rsi
0x18002e01f  pop     rbp
0x18002e020  retn
0x18002e022  mov     r13d, 1
0x18002e028  jmp     loc_18002DD0C
0x18002e02d  mov     rcx, [rbp+57h+var_88]
0x18002e031  mov     rax, [rcx]
0x18002e034  mov     rax, [rax]
0x18002e037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e03c  mov     esi, eax
0x18002e03e  test    eax, eax
0x18002e040  js      loc_18002E303
0x18002e046  mov     rcx, [rbp+57h+var_88]
0x18002e04a  jmp     loc_18002DD7C
0x18002e04f  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x18002e055  jz      loc_18002E2E9
0x18002e05b  mov     ecx, eax; int
0x18002e05d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002e062  jmp     loc_18002DF5D
0x18002e067  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002e06e  jz      loc_18002E2DA
0x18002e074  mov     ecx, eax; int
0x18002e076  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002e07b  mov     r14, [rbp+57h+pv]
0x18002e07f  xor     ebx, ebx
0x18002e081  jmp     loc_18002DF61
0x18002e086  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x18002e08c  jnz     short loc_18002E05B
0x18002e08e  test    eax, eax
0x18002e090  jns     loc_18002DE2B
0x18002e096  jmp     loc_18002DF5D
0x18002e09b  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x18002e0a1  jnz     short loc_18002E05B
0x18002e0a3  test    eax, eax
0x18002e0a5  jns     loc_18002DE8D
0x18002e0ab  jmp     loc_18002DF5D
0x18002e0b0  test    r8d, r8d
0x18002e0b3  jnz     short loc_18002E05B
0x18002e0b5  test    eax, eax
  ... truncated ...
```
