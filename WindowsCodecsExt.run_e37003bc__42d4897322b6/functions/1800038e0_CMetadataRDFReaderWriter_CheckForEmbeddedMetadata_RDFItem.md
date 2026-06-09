# CMetadataRDFReaderWriter::CheckForEmbeddedMetadata(RDFItem *)

- ea: `0x1800038e0`
- end: `0x180003ffb`
- name: `?CheckForEmbeddedMetadata@CMetadataRDFReaderWriter@@MEAAJPEAVRDFItem@@@Z`
- size: `1819`
- prototype: `int(CMetadataRDFReaderWriter *__hidden this, struct RDFItem *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800038e0`
- `0x180004004`
- `0x1800040e8`
- `0x180004164`
- `0x1800171c4`
- `0x180021a30`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003ec0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003ec0`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180003cf1`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180003cf1`
- `OLEAUT32!__imp_SysStringLen` at `0x180003cad`
- `OLEAUT32!__imp_SysStringLen` at `0x180003dad`
- `OLEAUT32!__imp_SysStringLen` at `0x180003cad`
- `OLEAUT32!__imp_SysStringLen` at `0x180003dad`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003cd5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003cd5`
- `WindowsCodecs!WICMatchMetadataContent` at `0x180003e68`
- `WindowsCodecs!WICMatchMetadataContent` at `0x180003e68`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::CheckForEmbeddedMetadata(
        CMetadataRDFReaderWriter *this,
        struct RDFItem *a2)
{
  __int64 v2; // rdi
  int v5; // r15d
  int CodecFactory; // eax
  struct IWICComponentFactory *v7; // rsi
  int v8; // ebx
  int v10; // eax
  int v11; // eax
  unsigned int i; // r12d
  int v13; // eax
  UINT v14; // eax
  HRESULT v15; // eax
  unsigned __int64 v16; // rdi
  int v17; // eax
  GUID *v18; // rax
  int v19; // ecx
  BSTR bstrString; // [rsp+48h] [rbp-39h] BYREF
  int v21; // [rsp+50h] [rbp-31h]
  __int64 v22; // [rsp+58h] [rbp-29h] BYREF
  struct IWICComponentFactory *v23; // [rsp+60h] [rbp-21h] BYREF
  int v24; // [rsp+68h] [rbp-19h] BYREF
  int v25; // [rsp+6Ch] [rbp-15h] BYREF
  int v26; // [rsp+70h] [rbp-11h] BYREF
  int v27; // [rsp+74h] [rbp-Dh] BYREF
  IStream *pIStream; // [rsp+78h] [rbp-9h] BYREF
  __int64 v29; // [rsp+80h] [rbp-1h] BYREF
  __int64 v30; // [rsp+88h] [rbp+7h] BYREF
  GUID pguidMetadataFormat; // [rsp+90h] [rbp+Fh] BYREF

  v2 = *((_QWORD *)a2 + 2);
  v5 = 0;
  v27 = 0;
  v30 = 0;
  v22 = 0;
  pIStream = 0;
  v23 = 0;
  v29 = 0;
  v25 = 0;
  v24 = 0;
  bstrString = 0;
  pguidMetadataFormat = GUID_NULL;
  CodecFactory = GetCodecFactory(&v23);
  v7 = v23;
  v8 = CodecFactory;
  if ( CodecFactory < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_4;
    goto LABEL_3;
  }
  CodecFactory = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, __int64, const WCHAR *, int *))(*(_QWORD *)this + 256LL))(
                   this,
                   v2,
                   L"Resource",
                   &v24);
  v8 = CodecFactory;
  if ( CodecFactory < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_4;
    goto LABEL_3;
  }
  if ( v24 )
  {
    CodecFactory = RDFItem::SetEmbeddedMetadataGUID(a2, &GUID_MetadataFormatXMPStruct);
    v8 = CodecFactory;
    if ( CodecFactory >= 0 )
    {
      *((_DWORD *)a2 + 2) |= 0x44u;
      goto LABEL_4;
    }
    if ( g_doStackCaptures )
    {
LABEL_3:
      DoStackCapture(CodecFactory);
      goto LABEL_4;
    }
    goto LABEL_4;
  }
  CodecFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 96LL))(v2, &v30);
  v8 = CodecFactory;
  if ( CodecFactory < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_4;
    goto LABEL_3;
  }
  if ( CodecFactory )
  {
    v8 = -2147467259;
    if ( g_doStackCaptures )
      DoStackCapture(-2147467259);
    goto LABEL_4;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 72LL))(v30, &v22);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_4;
    goto LABEL_27;
  }
  if ( v10 == 1 )
  {
    *((_DWORD *)a2 + 2) &= ~4u;
    v5 = 1;
  }
  if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 136LL))(v2, &v29) < 0
    || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 88LL))(v29, &v25) < 0 )
  {
    goto LABEL_51;
  }
  v11 = 0;
  v21 = 0;
  for ( i = 0; (int)i < v25; ++i )
  {
    v23 = 0;
    v26 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IWICComponentFactory **))(*(_QWORD *)v29 + 80LL))(
           v29,
           i,
           &v23);
    v13 = g_doStackCaptures;
    if ( v8 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_4;
      goto LABEL_94;
    }
    if ( v8 )
      goto LABEL_101;
    v10 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, struct IWICComponentFactory *, __int64, _QWORD, int *, _QWORD, _QWORD))(*(_QWORD *)this + 344LL))(
            this,
            v23,
            v2,
            0,
            &v26,
            0,
            0);
    v8 = v10;
    if ( v10 < 0 )
    {
      if ( g_doStackCaptures )
        goto LABEL_27;
      goto LABEL_4;
    }
    v11 = v21;
    if ( v26 )
      v11 = 1;
    v21 = v11;
    if ( v23 )
    {
      ((void (__fastcall *)(struct IWICComponentFactory *))v23->lpVtbl->Release)(v23);
      v11 = v21;
    }
  }
  if ( v5 )
  {
    if ( v11 )
    {
      *((_DWORD *)a2 + 2) |= 4u;
      v10 = RDFItem::SetEmbeddedMetadataGUID(a2, &GUID_MetadataFormatXMPStruct);
      v8 = v10;
      if ( v10 >= 0 )
      {
        *((_DWORD *)a2 + 2) |= 0x44u;
        v8 = 0;
        goto LABEL_4;
      }
      if ( g_doStackCaptures )
      {
LABEL_27:
        DoStackCapture(v10);
        goto LABEL_4;
      }
      goto LABEL_4;
    }
LABEL_51:
    v8 = 0;
    goto LABEL_4;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 80LL))(v22, &v27);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( g_doStackCaptures )
      goto LABEL_27;
    goto LABEL_4;
  }
  if ( v10 || v27 != 1 )
    goto LABEL_50;
  v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v22 + 312LL))(v22, &bstrString);
  v13 = g_doStackCaptures;
  if ( v8 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_4;
    goto LABEL_94;
  }
  if ( v8 )
  {
LABEL_101:
    v8 = -2147467259;
    if ( !v13 )
      goto LABEL_4;
    goto LABEL_94;
  }
  v14 = SysStringLen(bstrString);
  if ( CompareStringW(0x400u, 0, bstrString, v14, L"http://www.w3.org/1999/02/22-rdf-syntax-ns#", 43) != 2 )
  {
LABEL_50:
    *((_DWORD *)a2 + 2) &= ~4u;
    goto LABEL_51;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v22 + 328LL))(v22, &bstrString);
  v8 = v15;
  if ( v15 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_4;
    goto LABEL_84;
  }
  if ( v15 )
  {
    v8 = -2147467259;
    if ( g_doStackCaptures )
      DoStackCapture(-2147467259);
    goto LABEL_4;
  }
  v16 = 2LL * SysStringLen(bstrString);
  if ( v16 > 0xFFFFFFFF )
  {
    v8 = -2147024362;
    if ( g_doStackCaptures )
      DoStackCapture(-2147024362);
    goto LABEL_4;
  }
  v15 = ((__int64 (__fastcall *)(struct IWICComponentFactory *, IStream **))v7->lpVtbl->CreateStream)(v7, &pIStream);
  v8 = v15;
  if ( v15 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_4;
    goto LABEL_84;
  }
  v15 = (*(__int64 (__fastcall **)(IStream *, BSTR, _QWORD))(*(_QWORD *)pIStream + 128LL))(
          pIStream,
          bstrString,
          (unsigned int)v16);
  v8 = v15;
  if ( v15 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_4;
    goto LABEL_84;
  }
  v15 = WICMatchMetadataContent(&GUID_MetadataFormatXMP, 0, pIStream, &pguidMetadataFormat);
  v8 = v15;
  if ( v15 == -2003292336 )
  {
    pguidMetadataFormat = GUID_MetadataFormatUnknown;
  }
  else if ( v15 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_4;
LABEL_84:
    DoStackCapture(v15);
    goto LABEL_4;
  }
  v17 = RDFItem::ClearEmbeddedMetadataGUID(a2);
  v8 = v17;
  if ( v17 < 0 )
  {
    if ( !g_doStackCaptures )
    {
LABEL_93:
      if ( !g_doStackCaptures )
        goto LABEL_4;
LABEL_94:
      DoStackCapture(v8);
      goto LABEL_4;
    }
    v19 = v17;
LABEL_92:
    DoStackCapture(v19);
    goto LABEL_93;
  }
  v18 = (GUID *)malloc(0x10u);
  *((_QWORD *)a2 + 5) = v18;
  if ( v18 )
  {
    *v18 = pguidMetadataFormat;
    *((_DWORD *)a2 + 2) |= 4u;
    v8 = 0;
    goto LABEL_4;
  }
  v8 = -2147024882;
  if ( g_doStackCaptures )
  {
    v19 = -2147024882;
    goto LABEL_92;
  }
LABEL_4:
  if ( v7 )
    ((void (__fastcall *)(struct IWICComponentFactory *))v7->lpVtbl->Release)(v7);
  if ( pIStream )
  {
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)pIStream + 16LL))(pIStream);
    pIStream = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800038e0  mov     r11, rsp
0x1800038e3  push    rbp
0x1800038e4  push    rbx
0x1800038e5  lea     rbp, [r11-5Fh]
0x1800038e9  sub     rsp, 0C8h
0x1800038f0  mov     rax, cs:__security_cookie
0x1800038f7  xor     rax, rsp
0x1800038fa  mov     [rbp+57h+var_38], rax
0x1800038fe  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180003905  mov     [r11+18h], rsi
0x180003909  mov     [r11-18h], rdi
0x18000390d  mov     rdi, [rdx+10h]
0x180003911  mov     [r11-28h], r13
0x180003915  mov     r13, rcx
0x180003918  mov     [r11-30h], r14
0x18000391c  lea     rcx, [rbp+57h+var_78]; struct IWICComponentFactory **
0x180003920  mov     [r11-38h], r15
0x180003924  mov     r14, rdx
0x180003927  xor     r15d, r15d
0x18000392a  mov     [rbp+57h+var_64], r15d
0x18000392e  mov     [rbp+57h+var_50], r15
0x180003932  mov     [rbp+57h+var_80], r15
0x180003936  mov     [rbp+57h+pIStream], r15
0x18000393a  mov     [rbp+57h+var_78], r15
0x18000393e  mov     [rbp+57h+var_58], r15
0x180003942  mov     [rbp+57h+var_6C], r15d
0x180003946  mov     [rbp+57h+var_70], r15d
0x18000394a  mov     [rbp+57h+bstrString], r15
0x18000394e  movups  xmmword ptr [rbp+57h+pguidMetadataFormat.Data1], xmm0
0x180003952  call    ?GetCodecFactory@@YAJPEAPEAUIWICComponentFactory@@@Z; GetCodecFactory(IWICComponentFactory * *)
0x180003957  mov     rsi, [rbp+57h+var_78]
0x18000395b  mov     ebx, eax
0x18000395d  test    eax, eax
0x18000395f  jns     loc_180003A39
0x180003965  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000396c  jnz     loc_180003D8B
0x180003972  mov     r14, [rsp+0D0h+var_28]
0x18000397a  mov     r13, [rsp+0D0h+var_20]
0x180003982  mov     rdi, [rsp+0C0h]
0x18000398a  test    rsi, rsi
0x18000398d  jz      short loc_18000399E
0x18000398f  mov     rax, [rsi]
0x180003992  mov     rcx, rsi
0x180003995  mov     rax, [rax+10h]
0x180003999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000399e  mov     rcx, [rbp+57h+pIStream]
0x1800039a2  mov     rsi, [rsp+0D0h+arg_10]
0x1800039aa  test    rcx, rcx
0x1800039ad  jz      short loc_1800039BF
0x1800039af  mov     rax, [rcx]
0x1800039b2  mov     rax, [rax+10h]
0x1800039b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039bb  mov     [rbp+57h+pIStream], r15
0x1800039bf  mov     rcx, [rbp+57h+var_50]
0x1800039c3  test    rcx, rcx
0x1800039c6  jz      short loc_1800039D8
0x1800039c8  mov     rax, [rcx]
0x1800039cb  mov     rax, [rax+10h]
0x1800039cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d4  mov     [rbp+57h+var_50], r15
0x1800039d8  mov     rcx, [rbp+57h+var_80]
0x1800039dc  test    rcx, rcx
0x1800039df  jz      short loc_1800039F1
0x1800039e1  mov     rax, [rcx]
0x1800039e4  mov     rax, [rax+10h]
0x1800039e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ed  mov     [rbp+57h+var_80], r15
0x1800039f1  mov     rcx, [rbp+57h+var_58]
0x1800039f5  test    rcx, rcx
0x1800039f8  jz      short loc_180003A0A
0x1800039fa  mov     rax, [rcx]
0x1800039fd  mov     rax, [rax+10h]
0x180003a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a06  mov     [rbp+57h+var_58], r15
0x180003a0a  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180003a0e  mov     r15, [rsp+0D0h+var_30]
0x180003a16  test    rcx, rcx
0x180003a19  jz      short loc_180003A21
0x180003a1b  call    cs:__imp_SysFreeString
0x180003a21  mov     eax, ebx
0x180003a23  mov     rcx, [rbp+57h+var_38]
0x180003a27  xor     rcx, rsp; StackCookie
0x180003a2a  call    __security_check_cookie
0x180003a2f  add     rsp, 0C8h
0x180003a36  pop     rbx
0x180003a37  pop     rbp
0x180003a38  retn
0x180003a39  mov     rax, [r13+0]
0x180003a3d  lea     r9, [rbp+57h+var_70]
0x180003a41  lea     r8, aResource; "Resource"
0x180003a48  mov     rdx, rdi
0x180003a4b  mov     rcx, r13
0x180003a4e  mov     rax, [rax+100h]
0x180003a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a5a  mov     ebx, eax
0x180003a5c  test    eax, eax
0x180003a5e  jns     short loc_180003A79
0x180003a60  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180003a67  jz      loc_180003972
0x180003a6d  mov     ecx, eax; int
0x180003a6f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180003a74  jmp     loc_180003972
0x180003a79  cmp     [rbp+57h+var_70], r15d
0x180003a7d  jnz     loc_180003F23
0x180003a83  mov     rax, [rdi]
0x180003a86  lea     rdx, [rbp+57h+var_50]
0x180003a8a  mov     rcx, rdi
0x180003a8d  mov     rax, [rax+60h]
0x180003a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a96  mov     ebx, eax
0x180003a98  test    eax, eax
0x180003a9a  jns     short loc_180003AB5
0x180003a9c  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180003aa3  jz      loc_180003972
0x180003aa9  mov     ecx, eax; int
0x180003aab  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180003ab0  jmp     loc_180003972
0x180003ab5  jnz     loc_180003F86
0x180003abb  mov     rcx, [rbp+57h+var_50]
0x180003abf  lea     rdx, [rbp+57h+var_80]
0x180003ac3  mov     rax, [rcx]
0x180003ac6  mov     rax, [rax+48h]
0x180003aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003acf  mov     ebx, eax
0x180003ad1  test    eax, eax
0x180003ad3  jns     short loc_180003AEE
0x180003ad5  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180003adc  jz      loc_180003972
0x180003ae2  mov     ecx, eax; int
0x180003ae4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180003ae9  jmp     loc_180003972
0x180003aee  cmp     eax, 1
0x180003af1  jnz     short loc_180003AFB
0x180003af3  and     dword ptr [r14+8], 0FFFFFFFBh
0x180003af8  mov     r15d, eax
0x180003afb  mov     rax, [rdi]
0x180003afe  lea     rdx, [rbp+57h+var_58]
0x180003b02  mov     rcx, rdi
0x180003b05  mov     [rsp+0D0h+var_18], r12
0x180003b0d  mov     rax, [rax+88h]
0x180003b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b19  test    eax, eax
0x180003b1b  js      loc_180003C55
0x180003b21  mov     rcx, [rbp+57h+var_58]
0x180003b25  lea     rdx, [rbp+57h+var_6C]
0x180003b29  mov     rax, [rcx]
0x180003b2c  mov     rax, [rax+58h]
0x180003b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b35  test    eax, eax
0x180003b37  js      loc_180003C55
0x180003b3d  xor     eax, eax
0x180003b3f  mov     [rbp+57h+var_88], eax
0x180003b42  xor     r12d, r12d
0x180003b45  cmp     r12d, [rbp+57h+var_6C]
0x180003b49  jl      short loc_180003B87
0x180003b4b  test    r15d, r15d
0x180003b4e  jnz     loc_180003D40
0x180003b54  mov     rcx, [rbp+57h+var_80]
0x180003b58  lea     rdx, [rbp+57h+var_64]
0x180003b5c  mov     rax, [rcx]
0x180003b5f  mov     rax, [rax+50h]
0x180003b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b68  mov     ebx, eax
0x180003b6a  test    eax, eax
0x180003b6c  jns     loc_180003C68
0x180003b72  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180003b79  jnz     loc_180003D97
0x180003b7f  xor     r15d, r15d
0x180003b82  jmp     loc_180003DD7
0x180003b87  mov     rcx, [rbp+57h+var_58]
0x180003b8b  lea     r8, [rbp+57h+var_78]
0x180003b8f  mov     [rbp+57h+var_78], 0
0x180003b97  mov     edx, r12d
0x180003b9a  mov     [rbp+57h+var_68], 0
0x180003ba1  mov     rax, [rcx]
0x180003ba4  mov     rax, [rax+50h]
0x180003ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bad  mov     ebx, eax
0x180003baf  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180003bb5  test    ebx, ebx
0x180003bb7  jns     short loc_180003BC5
0x180003bb9  test    eax, eax
0x180003bbb  jnz     loc_180003F7A
0x180003bc1  test    ebx, ebx
0x180003bc3  js      short loc_180003B7F
0x180003bc5  jnz     loc_180003F6D
0x180003bcb  mov     rax, [r13+0]
0x180003bcf  lea     rcx, [rbp+57h+var_68]
0x180003bd3  mov     rdx, [rbp+57h+var_78]
0x180003bd7  xor     r9d, r9d
0x180003bda  mov     qword ptr [rsp+30h], 0
0x180003be3  mov     r8, rdi
0x180003be6  mov     qword ptr [rsp+0D0h+cchCount2], 0
0x180003bef  mov     rax, [rax+158h]
0x180003bf6  mov     [rsp+0D0h+lpString2], rcx
0x180003bfb  mov     rcx, r13
0x180003bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c03  mov     ebx, eax
0x180003c05  test    eax, eax
0x180003c07  jns     short loc_180003C1E
0x180003c09  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180003c10  jnz     loc_180003D97
0x180003c16  test    eax, eax
0x180003c18  js      loc_180003B7F
0x180003c1e  cmp     [rbp+57h+var_68], 0
0x180003c22  mov     ecx, 1
0x180003c27  mov     eax, [rbp+57h+var_88]
0x180003c2a  cmovnz  eax, ecx
0x180003c2d  mov     rcx, [rbp+57h+var_78]
0x180003c31  mov     [rbp+57h+var_88], eax
0x180003c34  test    rcx, rcx
0x180003c37  jz      short loc_180003C48
0x180003c39  mov     rax, [rcx]
0x180003c3c  mov     rax, [rax+10h]
0x180003c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c45  mov     eax, [rbp+57h+var_88]
0x180003c48  inc     r12d
0x180003c4b  jmp     loc_180003B45
0x180003c50  and     dword ptr [r14+8], 0FFFFFFFBh
0x180003c55  mov     r12, [rsp+0D0h+var_18]
0x180003c5d  xor     r15d, r15d
0x180003c60  mov     ebx, r15d
0x180003c63  jmp     loc_180003972
0x180003c68  jnz     short loc_180003C50
0x180003c6a  cmp     [rbp+57h+var_64], 1
0x180003c6e  jnz     short loc_180003C50
0x180003c70  mov     rcx, [rbp+57h+var_80]
0x180003c74  lea     rdx, [rbp+57h+bstrString]
0x180003c78  mov     rax, [rcx]
0x180003c7b  mov     rax, [rax+138h]
0x180003c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c87  mov     ebx, eax
0x180003c89  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180003c8f  test    ebx, ebx
0x180003c91  jns     short loc_180003CA3
0x180003c93  test    eax, eax
0x180003c95  jnz     loc_180003EEF
0x180003c9b  test    ebx, ebx
0x180003c9d  js      loc_180003B7F
0x180003ca3  jnz     loc_180003F6D
0x180003ca9  mov     rcx, [rbp+57h+bstrString]; pbstr
0x180003cad  call    cs:__imp_SysStringLen
0x180003cb3  mov     r8, [rbp+57h+bstrString]; lpString1
0x180003cb7  lea     rcx, aHttpWwwW3Org19; "http://www.w3.org/1999/02/22-rdf-syntax"...
0x180003cbe  mov     [rsp+0D0h+cchCount2], 2Bh ; '+'; cchCount2
0x180003cc6  mov     r9d, eax; cchCount1
0x180003cc9  mov     [rsp+0D0h+lpString2], rcx; lpString2
0x180003cce  xor     edx, edx; dwCmpFlags
0x180003cd0  mov     ecx, 400h; Locale
0x180003cd5  call    cs:__imp_CompareStringW
0x180003cdb  cmp     eax, 2
0x180003cde  jnz     loc_180003C50
0x180003ce4  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180003ce8  test    rcx, rcx
0x180003ceb  jz      loc_180003FE3
0x180003cf1  call    cs:__imp_SysFreeString
0x180003cf7  xor     r15d, r15d
0x180003cfa  mov     [rbp+57h+bstrString], r15
0x180003cfe  mov     rcx, [rbp+57h+var_80]
0x180003d02  lea     rdx, [rbp+57h+bstrString]
0x180003d06  mov     rax, [rcx]
0x180003d09  mov     rax, [rax+148h]
0x180003d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d15  mov     ebx, eax
0x180003d17  test    eax, eax
0x180003d19  jns     loc_180003DA3
0x180003d1f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180003d26  jz      loc_180003DD7
0x180003d2c  mov     ecx, eax; int
0x180003d2e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180003d33  mov     r12, [rsp+0D0h+var_18]
0x180003d3b  jmp     loc_180003972
0x180003d40  test    eax, eax
0x180003d42  jz      loc_180003F5F
0x180003d48  or      dword ptr [r14+8], 4
0x180003d4d  lea     rdx, GUID_MetadataFormatXMPStruct; struct _GUID *
0x180003d54  mov     rcx, r14; this
0x180003d57  call    ?SetEmbeddedMetadataGUID@RDFItem@@QEAAJAEBU_GUID@@@Z; RDFItem::SetEmbeddedMetadataGUID(_GUID const &)
0x180003d5c  mov     ebx, eax
0x180003d5e  test    eax, eax
0x180003d60  jns     short loc_180003D73
0x180003d62  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180003d69  jnz     short loc_180003D97
0x180003d6b  test    eax, eax
0x180003d6d  js      loc_180003B7F
0x180003d73  or      dword ptr [r14+8], 44h
0x180003d78  mov     r12, [rsp+0D0h+var_18]
0x180003d80  xor     r15d, r15d
0x180003d83  mov     ebx, r15d
0x180003d86  jmp     loc_180003972
0x180003d8b  mov     ecx, eax; int
0x180003d8d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180003d92  jmp     loc_180003972
0x180003d97  mov     ecx, eax; int
0x180003d99  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180003d9e  jmp     loc_180003B7F
0x180003da3  jnz     loc_180003FA4
0x180003da9  mov     rcx, [rbp+57h+bstrString]; pbstr
0x180003dad  call    cs:__imp_SysStringLen
0x180003db3  mov     edi, eax
  ... truncated ...
```
