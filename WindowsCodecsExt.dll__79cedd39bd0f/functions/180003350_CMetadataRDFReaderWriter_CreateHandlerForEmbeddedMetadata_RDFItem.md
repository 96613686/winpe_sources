# CMetadataRDFReaderWriter::CreateHandlerForEmbeddedMetadata(RDFItem *)

- ea: `0x180003350`
- end: `0x1800038cf`
- name: `?CreateHandlerForEmbeddedMetadata@CMetadataRDFReaderWriter@@MEAAJPEAVRDFItem@@@Z`
- size: `1407`
- prototype: `int(CMetadataRDFReaderWriter *__hidden this, struct RDFItem *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002920`
- `0x180003350`
- `0x180004004`
- `0x180004194`
- `0x180004280`
- `0x1800171c4`
- `0x1800215e8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180003462`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180003462`
- `OLEAUT32!__imp_SysFreeString` at `0x180003471`
- `OLEAUT32!__imp_SysFreeString` at `0x180003471`
- `OLEAUT32!__imp_SysStringLen` at `0x18000364d`
- `OLEAUT32!__imp_SysStringLen` at `0x18000364d`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::CreateHandlerForEmbeddedMetadata(
        CMetadataRDFReaderWriter *this,
        struct RDFItem *a2)
{
  CPrefixedStream *v3; // rdi
  int CodecFactory; // eax
  struct IWICComponentFactory *v6; // r12
  unsigned int v7; // ebx
  char *v8; // r8
  __int64 v9; // rax
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  int v12; // ecx
  __int64 v13; // rbx
  unsigned __int64 v14; // r14
  CPrefixedStream *v15; // rax
  struct IStream *v16; // rdx
  __int64 v17; // [rsp+40h] [rbp-39h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-31h] BYREF
  __int64 *v19; // [rsp+50h] [rbp-29h] BYREF
  struct IStream *v20; // [rsp+58h] [rbp-21h] BYREF
  __int64 v21; // [rsp+60h] [rbp-19h] BYREF
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-11h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-9h] BYREF
  CMetadataRDFReaderWriter *v24; // [rsp+78h] [rbp-1h] BYREF
  struct IWICComponentFactory *v25; // [rsp+80h] [rbp+7h] BYREF
  struct tagPROPVARIANT pvar[3]; // [rsp+88h] [rbp+Fh] BYREF
  int v27; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v28; // [rsp+F8h] [rbp+7Fh] BYREF

  bstrString = 0;
  v27 = 0;
  v21 = 0;
  v28 = 0;
  v3 = 0;
  v22 = 0;
  v23 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v25 = 0;
  v24 = 0;
  memset(pvar, 0, 24);
  CodecFactory = GetCodecFactory(&v25);
  v6 = v25;
  v7 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_7;
  CodecFactory = ((__int64 (__fastcall *)(struct IWICComponentFactory *, GUID *, __int64 **))v25->lpVtbl->QueryInterface)(
                   v25,
                   &IID_IWICComponentFactory,
                   &v19);
  v7 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_7;
  v8 = (char *)this + 100;
  v9 = *v19;
  if ( *((_DWORD *)this + 42) )
  {
    CodecFactory = (*(__int64 (__fastcall **)(__int64 *, _QWORD, char *, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v9 + 240))(
                     v19,
                     *((_QWORD *)a2 + 5),
                     v8,
                     0x10000,
                     &v23);
    v7 = CodecFactory;
    if ( CodecFactory < 0 )
      goto LABEL_7;
    v10 = v23;
  }
  else
  {
    CodecFactory = (*(__int64 (__fastcall **)(__int64 *, _QWORD, char *, __int64, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v9 + 224))(
                     v19,
                     *((_QWORD *)a2 + 5),
                     v8,
                     0x10000,
                     0,
                     &v22);
    v7 = CodecFactory;
    if ( CodecFactory < 0 )
      goto LABEL_7;
    v10 = v22;
  }
  CodecFactory = (**v10)(v10, &IID_IWICPersistStream, &v17);
  v7 = CodecFactory;
  if ( CodecFactory < 0
    || v17
    && (**(int (__fastcall ***)(__int64, GUID *, CMetadataRDFReaderWriter **))v17)(v17, &IID_IXMPCMetadataRDF, &v24) >= 0
    && (CodecFactory = CMetadataRDFReaderWriter::SetDepth(v24, *((_DWORD *)this + 50) + 1),
        v7 = CodecFactory,
        CodecFactory < 0) )
  {
LABEL_7:
    if ( !g_doStackCaptures )
      goto LABEL_8;
    goto LABEL_31;
  }
  v13 = *((_QWORD *)a2 + 2);
  if ( (*((_BYTE *)a2 + 8) & 0x40) == 0 )
  {
    CodecFactory = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v13 + 96LL))(*((_QWORD *)a2 + 2), &v21);
    v7 = CodecFactory;
    if ( CodecFactory >= 0 )
    {
      if ( CodecFactory )
      {
LABEL_72:
        v7 = -2147467259;
LABEL_47:
        if ( g_doStackCaptures )
        {
          v12 = v7;
          goto LABEL_32;
        }
        goto LABEL_8;
      }
      CodecFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 72LL))(v21, &v28);
      v7 = CodecFactory;
      if ( CodecFactory >= 0 )
      {
        if ( CodecFactory == 1 )
          goto LABEL_56;
        CodecFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 80LL))(v28, &v27);
        v7 = CodecFactory;
        if ( CodecFactory < 0 )
          goto LABEL_7;
        if ( CodecFactory == 1 || v27 != 1 )
        {
LABEL_56:
          v7 = -2003292271;
          goto LABEL_47;
        }
        goto LABEL_42;
      }
    }
    goto LABEL_7;
  }
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  v28 = v13;
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
LABEL_42:
    v13 = v28;
  }
  CodecFactory = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v13 + 272LL))(v13, &bstrString);
  v7 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_7;
  if ( CodecFactory )
    goto LABEL_72;
  v14 = 2LL * SysStringLen(bstrString);
  if ( v14 > 0xFFFFFFFF )
  {
    v7 = -2147024362;
    goto LABEL_47;
  }
  CodecFactory = ((__int64 (__fastcall *)(struct IWICComponentFactory *, struct IStream **))v6->lpVtbl->CreateStream)(
                   v6,
                   &v20);
  v7 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_7;
  CodecFactory = (*(__int64 (__fastcall **)(struct IStream *, BSTR, _QWORD))(*(_QWORD *)v20 + 128LL))(
                   v20,
                   bstrString,
                   (unsigned int)v14);
  v7 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_7;
  v15 = (CPrefixedStream *)operator new(0x50u);
  v3 = v15;
  if ( !v15 )
  {
    v7 = -2147024882;
    if ( g_doStackCaptures )
      DoStackCapture(-2147024882);
    v3 = 0;
    goto LABEL_8;
  }
  *((_DWORD *)v15 + 2) = 0;
  *(_QWORD *)v15 = &CMILCOMBase::`vftable';
  _InterlockedIncrement(&g_cActiveObjects);
  *((_QWORD *)v15 + 3) = 0;
  *((_QWORD *)v15 + 7) = 0;
  *((_QWORD *)v15 + 2) = &CBOMStream::`vftable'{for `IStream'};
  *((_QWORD *)v15 + 6) = 0;
  *((_QWORD *)v15 + 4) = 0;
  *((_DWORD *)v15 + 10) = 0;
  *(_QWORD *)v15 = &CBOMStream::`vftable'{for `CMILCOMBase'};
  CMILCOMBase::InternalAddRef(v15);
  v16 = v20;
  *((_BYTE *)v3 + 68) = 0;
  CodecFactory = CPrefixedStream::Initialize(v3, v16, 2u);
  v7 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_7;
  CodecFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, _QWORD))(*(_QWORD *)v17 + 64LL))(
                   v17,
                   ((unsigned __int64)v3 + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)v3 >> 64),
                   (char *)this + 100,
                   *((_DWORD *)this + 33) | 4u);
  v7 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_7;
  CodecFactory = (**(__int64 (__fastcall ***)(__int64, GUID *, ULONG *))v17)(v17, &IID_IUnknown, &pvar[0].ulVal);
  v7 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_7;
  pvar[0].vt = 13;
  CodecFactory = RDFItem::SetPropVariantValue(a2, pvar);
  v7 = CodecFactory;
  if ( CodecFactory >= 0 )
  {
    *((_DWORD *)a2 + 2) |= 8u;
    goto LABEL_8;
  }
  if ( g_doStackCaptures )
  {
LABEL_31:
    v12 = CodecFactory;
LABEL_32:
    DoStackCapture(v12);
  }
LABEL_8:
  PropVariantClear((PROPVARIANT *)pvar);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v6 )
    ((void (__fastcall *)(struct IWICComponentFactory *))v6->lpVtbl->Release)(v6);
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
    v19 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v22 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v22)[2])(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v23)[2])(v23);
    v23 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(CMetadataRDFReaderWriter *))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v3 )
    (*(void (__fastcall **)(CPrefixedStream *))(*(_QWORD *)v3 + 16LL))(v3);
  return v7;
}

```

## disassembly

```asm
0x180003350  mov     [rsp-8+arg_0], rbx
0x180003355  push    rbp
0x180003356  push    rsi
0x180003357  push    rdi
0x180003358  push    r12
0x18000335a  push    r13
0x18000335c  push    r14
0x18000335e  push    r15
0x180003360  lea     rbp, [rsp-27h]
0x180003365  sub     rsp, 0A0h
0x18000336c  xor     r14d, r14d
0x18000336f  mov     r15, rcx
0x180003372  xorps   xmm0, xmm0
0x180003375  mov     [rbp+57h+bstrString], r14
0x180003379  xor     eax, eax
0x18000337b  mov     [rbp+57h+arg_10], r14d
0x18000337f  lea     rcx, [rbp+57h+var_50]; struct IWICComponentFactory **
0x180003383  mov     [rbp+57h+var_70], r14
0x180003387  mov     [rbp+57h+arg_18], r14
0x18000338b  mov     edi, r14d
0x18000338e  mov     [rbp+57h+var_68], r14
0x180003392  mov     rsi, rdx
0x180003395  mov     [rbp+57h+var_60], r14
0x180003399  mov     [rbp+57h+var_90], r14
0x18000339d  mov     [rbp+57h+var_80], r14
0x1800033a1  mov     [rbp+57h+var_78], r14
0x1800033a5  mov     [rbp+57h+var_50], r14
0x1800033a9  mov     [rbp+57h+var_58], r14
0x1800033ad  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800033b1  mov     [rbp+57h+var_38], rax
0x1800033b5  call    ?GetCodecFactory@@YAJPEAPEAUIWICComponentFactory@@@Z; GetCodecFactory(IWICComponentFactory * *)
0x1800033ba  mov     r12, [rbp+57h+var_50]
0x1800033be  mov     ebx, eax
0x1800033c0  test    eax, eax
0x1800033c2  js      loc_180003451
0x1800033c8  mov     rax, [r12]
0x1800033cc  lea     r8, [rbp+57h+var_80]
0x1800033d0  lea     rdx, IID_IWICComponentFactory
0x1800033d7  mov     rcx, r12
0x1800033da  mov     rax, [rax]
0x1800033dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e2  mov     ebx, eax
0x1800033e4  test    eax, eax
0x1800033e6  js      short loc_180003451
0x1800033e8  lea     r13, [r15+64h]
0x1800033ec  mov     rcx, [rbp+57h+var_80]
0x1800033f0  mov     r9d, 10000h
0x1800033f6  mov     r8, r13
0x1800033f9  mov     rax, [rcx]
0x1800033fc  cmp     [r15+0A8h], r14d
0x180003403  jnz     loc_180003884
0x180003409  mov     rax, [rax+0E0h]
0x180003410  lea     rdx, [rbp+57h+var_68]
0x180003414  mov     [rsp+0D0h+var_A8], rdx
0x180003419  mov     rdx, [rsi+28h]
0x18000341d  mov     [rsp+0D0h+var_B0], r14
0x180003422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003427  mov     ebx, eax
0x180003429  test    eax, eax
0x18000342b  js      short loc_180003451
0x18000342d  mov     rcx, [rbp+57h+var_68]
0x180003431  mov     rax, [rcx]
0x180003434  lea     r8, [rbp+57h+var_90]
0x180003438  lea     rdx, IID_IWICPersistStream
0x18000343f  mov     rax, [rax]
0x180003442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003447  mov     ebx, eax
0x180003449  test    eax, eax
0x18000344b  jns     loc_180003589
0x180003451  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180003458  jnz     loc_18000357D
0x18000345e  lea     rcx, [rbp+57h+pvar]; pvar
0x180003462  call    cs:__imp_PropVariantClear
0x180003468  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000346c  test    rcx, rcx
0x18000346f  jz      short loc_18000347B
0x180003471  call    cs:__imp_SysFreeString
0x180003477  mov     [rbp+57h+bstrString], r14
0x18000347b  test    r12, r12
0x18000347e  jz      short loc_180003490
0x180003480  mov     rax, [r12]
0x180003484  mov     rcx, r12
0x180003487  mov     rax, [rax+10h]
0x18000348b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003490  mov     rcx, [rbp+57h+var_80]
0x180003494  test    rcx, rcx
0x180003497  jz      short loc_1800034A9
0x180003499  mov     rax, [rcx]
0x18000349c  mov     rax, [rax+10h]
0x1800034a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034a5  mov     [rbp+57h+var_80], r14
0x1800034a9  mov     rcx, [rbp+57h+var_78]
0x1800034ad  test    rcx, rcx
0x1800034b0  jz      short loc_1800034C2
0x1800034b2  mov     rax, [rcx]
0x1800034b5  mov     rax, [rax+10h]
0x1800034b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034be  mov     [rbp+57h+var_78], r14
0x1800034c2  mov     rcx, [rbp+57h+var_70]
0x1800034c6  test    rcx, rcx
0x1800034c9  jz      short loc_1800034DB
0x1800034cb  mov     rax, [rcx]
0x1800034ce  mov     rax, [rax+10h]
0x1800034d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d7  mov     [rbp+57h+var_70], r14
0x1800034db  mov     rcx, [rbp+57h+arg_18]
0x1800034df  test    rcx, rcx
0x1800034e2  jz      short loc_1800034F4
0x1800034e4  mov     rax, [rcx]
0x1800034e7  mov     rax, [rax+10h]
0x1800034eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034f0  mov     [rbp+57h+arg_18], r14
0x1800034f4  mov     rcx, [rbp+57h+var_68]
0x1800034f8  test    rcx, rcx
0x1800034fb  jz      short loc_18000350D
0x1800034fd  mov     rax, [rcx]
0x180003500  mov     rax, [rax+10h]
0x180003504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003509  mov     [rbp+57h+var_68], r14
0x18000350d  mov     rcx, [rbp+57h+var_60]
0x180003511  test    rcx, rcx
0x180003514  jnz     loc_1800038BA
0x18000351a  mov     rcx, [rbp+57h+var_90]
0x18000351e  test    rcx, rcx
0x180003521  jz      short loc_180003533
0x180003523  mov     rax, [rcx]
0x180003526  mov     rax, [rax+10h]
0x18000352a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000352f  mov     [rbp+57h+var_90], r14
0x180003533  mov     rcx, [rbp+57h+var_58]
0x180003537  test    rcx, rcx
0x18000353a  jz      short loc_18000354C
0x18000353c  mov     rax, [rcx]
0x18000353f  mov     rax, [rax+10h]
0x180003543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003548  mov     [rbp+57h+var_58], r14
0x18000354c  test    rdi, rdi
0x18000354f  jz      short loc_180003560
0x180003551  mov     rdx, [rdi]
0x180003554  mov     rcx, rdi
0x180003557  mov     rax, [rdx+10h]
0x18000355b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003560  mov     eax, ebx
0x180003562  mov     rbx, [rsp+0D0h+arg_0]
0x18000356a  add     rsp, 0A0h
0x180003571  pop     r15
0x180003573  pop     r14
0x180003575  pop     r13
0x180003577  pop     r12
0x180003579  pop     rdi
0x18000357a  pop     rsi
0x18000357b  pop     rbp
0x18000357c  retn
0x18000357d  mov     ecx, eax; int
0x18000357f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180003584  jmp     loc_18000345E
0x180003589  mov     rcx, [rbp+57h+var_90]
0x18000358d  test    rcx, rcx
0x180003590  jnz     loc_180003683
0x180003596  test    byte ptr [rsi+8], 40h
0x18000359a  mov     rbx, [rsi+10h]
0x18000359e  jnz     loc_1800036C2
0x1800035a4  mov     rax, [rbx]
0x1800035a7  lea     rdx, [rbp+57h+var_70]
0x1800035ab  mov     rcx, rbx
0x1800035ae  mov     rax, [rax+60h]
0x1800035b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035b7  mov     ebx, eax
0x1800035b9  test    eax, eax
0x1800035bb  js      loc_180003451
0x1800035c1  jnz     loc_1800038B0
0x1800035c7  mov     rcx, [rbp+57h+var_70]
0x1800035cb  lea     rdx, [rbp+57h+arg_18]
0x1800035cf  mov     rax, [rcx]
0x1800035d2  mov     rax, [rax+48h]
0x1800035d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035db  mov     ebx, eax
0x1800035dd  test    eax, eax
0x1800035df  js      loc_180003451
0x1800035e5  cmp     eax, 1
0x1800035e8  jz      loc_1800036F0
0x1800035ee  mov     rcx, [rbp+57h+arg_18]
0x1800035f2  lea     rdx, [rbp+57h+arg_10]
0x1800035f6  mov     rax, [rcx]
0x1800035f9  mov     rax, [rax+50h]
0x1800035fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003602  mov     ebx, eax
0x180003604  test    eax, eax
0x180003606  js      loc_180003451
0x18000360c  cmp     eax, 1
0x18000360f  jz      loc_1800036F0
0x180003615  cmp     [rbp+57h+arg_10], 1
0x180003619  jnz     loc_1800036F0
0x18000361f  mov     rbx, [rbp+57h+arg_18]
0x180003623  mov     rax, [rbx]
0x180003626  lea     rdx, [rbp+57h+bstrString]
0x18000362a  mov     rcx, rbx
0x18000362d  mov     rax, [rax+110h]
0x180003634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003639  mov     ebx, eax
0x18000363b  test    eax, eax
0x18000363d  js      loc_180003451
0x180003643  jnz     loc_1800038B0
0x180003649  mov     rcx, [rbp+57h+bstrString]; pbstr
0x18000364d  call    cs:__imp_SysStringLen
0x180003653  mov     r14d, eax
0x180003656  mov     eax, 0FFFFFFFFh
0x18000365b  add     r14, r14
0x18000365e  cmp     r14, rax
0x180003661  jbe     loc_1800036FA
0x180003667  mov     ebx, 80070216h
0x18000366c  xor     r14d, r14d
0x18000366f  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180003676  jz      loc_18000345E
0x18000367c  mov     ecx, ebx
0x18000367e  jmp     loc_18000357F
0x180003683  mov     rax, [rcx]
0x180003686  lea     r8, [rbp+57h+var_58]
0x18000368a  lea     rdx, IID_IXMPCMetadataRDF
0x180003691  mov     rax, [rax]
0x180003694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003699  test    eax, eax
0x18000369b  js      loc_180003596
0x1800036a1  mov     edx, [r15+0C8h]
0x1800036a8  mov     rcx, [rbp+57h+var_58]; this
0x1800036ac  inc     edx; unsigned int
0x1800036ae  call    ?SetDepth@CMetadataRDFReaderWriter@@QEAAJI@Z; CMetadataRDFReaderWriter::SetDepth(uint)
0x1800036b3  mov     ebx, eax
0x1800036b5  test    eax, eax
0x1800036b7  js      loc_180003451
0x1800036bd  jmp     loc_180003596
0x1800036c2  mov     rcx, [rbp+57h+arg_18]
0x1800036c6  test    rcx, rcx
0x1800036c9  jnz     loc_18000386A
0x1800036cf  mov     [rbp+57h+arg_18], rbx
0x1800036d3  test    rbx, rbx
0x1800036d6  jz      loc_180003623
0x1800036dc  mov     rax, [rbx]
0x1800036df  mov     rcx, rbx
0x1800036e2  mov     rax, [rax+8]
0x1800036e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036eb  jmp     loc_18000361F
0x1800036f0  mov     ebx, 88982F91h
0x1800036f5  jmp     loc_18000366F
0x1800036fa  mov     rax, [r12]
0x1800036fe  lea     rdx, [rbp+57h+var_78]
0x180003702  mov     rcx, r12
0x180003705  mov     rax, [rax+70h]
0x180003709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370e  mov     ebx, eax
0x180003710  test    eax, eax
0x180003712  jns     short loc_18000371C
0x180003714  xor     r14d, r14d
0x180003717  jmp     loc_180003451
0x18000371c  mov     rcx, [rbp+57h+var_78]
0x180003720  mov     r8d, r14d
0x180003723  mov     rdx, [rbp+57h+bstrString]
0x180003727  mov     rax, [rcx]
0x18000372a  mov     rax, [rax+80h]
0x180003731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003736  xor     r14d, r14d
0x180003739  mov     ebx, eax
0x18000373b  test    eax, eax
0x18000373d  js      loc_180003451
0x180003743  lea     ecx, [r14+50h]; Size
0x180003747  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000374c  mov     rdi, rax
0x18000374f  test    rax, rax
0x180003752  jz      loc_180003854
0x180003758  lea     rax, ??_7CMILCOMBase@@6B@; const CMILCOMBase::`vftable'
0x18000375f  mov     [rdi+8], r14d
0x180003763  mov     [rdi], rax
0x180003766  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18000376d  lea     rdx, ??_7CBOMStream@@6BCMILCOMBase@@@; const CBOMStream::`vftable'{for `CMILCOMBase'}
0x180003774  mov     [rdi+18h], r14
0x180003778  lea     rax, ??_7CBOMStream@@6BIStream@@@; const CBOMStream::`vftable'{for `IStream'}
0x18000377f  mov     [rdi+38h], r14
0x180003783  mov     [rdi+10h], rax
0x180003787  mov     rcx, rdi
0x18000378a  mov     rax, [rdx+8]
0x18000378e  mov     [rdi+30h], r14
0x180003792  mov     [rdi+20h], r14
0x180003796  mov     [rdi+28h], r14d
0x18000379a  mov     [rdi], rdx
0x18000379d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037a2  mov     rdx, [rbp+57h+var_78]; struct IStream *
0x1800037a6  lea     r8d, [r14+2]; unsigned int
0x1800037aa  mov     rcx, rdi; this
0x1800037ad  mov     [rdi+44h], r14b
0x1800037b1  call    ?Initialize@CPrefixedStream@@QEAAJPEAUIStream@@K@Z; CPrefixedStream::Initialize(IStream *,ulong)
0x1800037b6  mov     ebx, eax
0x1800037b8  test    eax, eax
0x1800037ba  js      loc_180003451
0x1800037c0  mov     rcx, [rbp+57h+var_90]
0x1800037c4  lea     r10, [rdi+10h]
0x1800037c8  mov     r9d, [r15+84h]
0x1800037cf  mov     rax, rdi
0x1800037d2  or      r9d, 4
0x1800037d6  mov     r8, r13
0x1800037d9  neg     rax
  ... truncated ...
```
