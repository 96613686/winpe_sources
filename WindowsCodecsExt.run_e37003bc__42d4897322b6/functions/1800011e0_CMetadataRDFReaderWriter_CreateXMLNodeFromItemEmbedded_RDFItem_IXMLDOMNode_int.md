# CMetadataRDFReaderWriter::CreateXMLNodeFromItemEmbedded(RDFItem *,IXMLDOMNode * *,int)

- ea: `0x1800011e0`
- end: `0x18000142c`
- name: `?CreateXMLNodeFromItemEmbedded@CMetadataRDFReaderWriter@@MEAAJPEAVRDFItem@@PEAPEAUIXMLDOMNode@@H@Z`
- size: `588`
- prototype: `int(CMetadataRDFReaderWriter *__hidden this, struct RDFItem *, struct IXMLDOMNode **, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800011e0`
- `0x180002484`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180001262`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180001262`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180001323`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180001323`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::CreateXMLNodeFromItemEmbedded(
        CMetadataRDFReaderWriter *this,
        struct RDFItem *a2,
        struct IXMLDOMNode **a3,
        unsigned int a4)
{
  HRESULT PropVariantValue; // eax
  int v9; // ebx
  HRESULT v10; // eax
  int v12; // ecx
  bool v13; // zf
  LPSTREAM ppstm; // [rsp+30h] [rbp-49h] BYREF
  __int64 v15; // [rsp+38h] [rbp-41h] BYREF
  __int64 v16; // [rsp+40h] [rbp-39h] BYREF
  __int64 v17; // [rsp+48h] [rbp-31h]
  struct tagPROPVARIANT pvar; // [rsp+50h] [rbp-29h] BYREF
  __int128 v19; // [rsp+70h] [rbp-9h] BYREF
  __int64 v20; // [rsp+80h] [rbp+7h]
  __int16 v21; // [rsp+E8h] [rbp+6Fh] BYREF

  ppstm = 0;
  v15 = 0;
  v13 = (*((_BYTE *)a2 + 8) & 8) == 0;
  v16 = 0;
  v17 = 0;
  v21 = 0;
  v19 = 0;
  memset(&pvar, 0, sizeof(pvar));
  if ( v13 )
  {
    PropVariantValue = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *))(*(_QWORD *)this + 224LL))(this);
    v9 = PropVariantValue;
    if ( PropVariantValue < 0 )
      goto LABEL_3;
  }
  PropVariantValue = RDFItem::GetPropVariantValue(a2, &pvar);
  v9 = PropVariantValue;
  if ( PropVariantValue < 0 )
    goto LABEL_3;
  PropVariantValue = (**(__int64 (__fastcall ***)(LARGE_INTEGER, GUID *, __int64 *))pvar.hVal.QuadPart)(
                       pvar.hVal,
                       &IID_IWICPersistStream,
                       &v15);
  v9 = PropVariantValue;
  if ( PropVariantValue < 0 )
    goto LABEL_3;
  PropVariantValue = CreateStreamOnHGlobal(0, 1, &ppstm);
  v9 = PropVariantValue;
  if ( PropVariantValue < 0 )
    goto LABEL_3;
  PropVariantValue = (*(__int64 (__fastcall **)(__int64, LPSTREAM, _QWORD, _QWORD))(*(_QWORD *)v15 + 72LL))(
                       v15,
                       ppstm,
                       *((unsigned int *)this + 33),
                       a4);
  v9 = PropVariantValue;
  if ( PropVariantValue < 0 )
    goto LABEL_3;
  PropVariantValue = (*(__int64 (__fastcall **)(LPSTREAM, __int64, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(
                       ppstm,
                       v17,
                       0,
                       0);
  v9 = PropVariantValue;
  if ( PropVariantValue < 0
    || (PropVariantValue = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, __int64 *))(*(_QWORD *)this + 264LL))(
                             this,
                             &v16),
        v9 = PropVariantValue,
        PropVariantValue < 0)
    || (v20 = 0,
        LOWORD(v19) = 13,
        *((_QWORD *)&v19 + 1) = ppstm,
        PropVariantValue = (*(__int64 (__fastcall **)(__int64, __int128 *, __int16 *))(*(_QWORD *)v16 + 464LL))(
                             v16,
                             &v19,
                             &v21),
        v9 = PropVariantValue,
        PropVariantValue < 0) )
  {
LABEL_3:
    if ( !g_doStackCaptures )
      goto LABEL_4;
    v12 = PropVariantValue;
    goto LABEL_16;
  }
  if ( PropVariantValue )
  {
    v13 = g_doStackCaptures == 0;
    goto LABEL_25;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNode **))(*(_QWORD *)v16 + 104LL))(v16, a3);
  if ( v9 < 0 && g_doStackCaptures )
    goto LABEL_26;
  if ( v9 >= 1 )
  {
    v13 = g_doStackCaptures == 0;
LABEL_25:
    v9 = -2147467259;
    if ( !v13 )
    {
LABEL_26:
      v12 = v9;
LABEL_16:
      DoStackCapture(v12);
    }
  }
LABEL_4:
  v10 = PropVariantClear((PROPVARIANT *)&pvar);
  if ( v9 >= 0 )
    v9 = v10;
  if ( ppstm )
  {
    (*(void (**)(void))(*(_QWORD *)ppstm + 16LL))();
    ppstm = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800011e0  push    rbp
0x1800011e2  push    rbx
0x1800011e3  push    rsi
0x1800011e4  push    rdi
0x1800011e5  push    r12
0x1800011e7  push    r13
0x1800011e9  push    r14
0x1800011eb  push    r15
0x1800011ed  lea     rbp, [rsp-1Fh]
0x1800011f2  sub     rsp, 98h
0x1800011f9  xor     r12d, r12d
0x1800011fc  xor     eax, eax
0x1800011fe  xorps   xmm0, xmm0
0x180001201  mov     [rbp+57h+ppstm], r12
0x180001205  xor     r13d, r13d
0x180001208  mov     [rbp+57h+var_98], r12
0x18000120c  test    byte ptr [rdx+8], 8
0x180001210  mov     r14d, r9d
0x180001213  mov     r15, r8
0x180001216  mov     [rbp+57h+var_90], r12
0x18000121a  mov     rsi, rdx
0x18000121d  mov     [rbp+57h+var_88], r12
0x180001221  mov     rdi, rcx
0x180001224  mov     [rbp+57h+arg_8], r12w
0x180001229  movups  [rbp+57h+var_60], xmm0
0x18000122d  mov     [rbp+57h+var_70], rax
0x180001231  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180001235  jz      loc_1800012CA
0x18000123b  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18000123f  mov     rcx, rsi; this
0x180001242  call    ?GetPropVariantValue@RDFItem@@QEAAJPEAUtagPROPVARIANT@@@Z; RDFItem::GetPropVariantValue(tagPROPVARIANT *)
0x180001247  mov     ebx, eax
0x180001249  test    eax, eax
0x18000124b  jns     loc_1800012F4
0x180001251  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180001258  jnz     loc_1800012E8
0x18000125e  lea     rcx, [rbp+57h+pvar]; pvar
0x180001262  call    cs:__imp_PropVariantClear
0x180001268  mov     rcx, [rbp+57h+ppstm]
0x18000126c  test    ebx, ebx
0x18000126e  cmovns  ebx, eax
0x180001271  test    rcx, rcx
0x180001274  jz      short loc_180001286
0x180001276  mov     rax, [rcx]
0x180001279  mov     rax, [rax+10h]
0x18000127d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001282  mov     [rbp+57h+ppstm], r12
0x180001286  mov     rcx, [rbp+57h+var_98]
0x18000128a  test    rcx, rcx
0x18000128d  jz      short loc_18000129F
0x18000128f  mov     rax, [rcx]
0x180001292  mov     rax, [rax+10h]
0x180001296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000129b  mov     [rbp+57h+var_98], r12
0x18000129f  mov     rcx, [rbp+57h+var_90]
0x1800012a3  test    rcx, rcx
0x1800012a6  jz      short loc_1800012B4
0x1800012a8  mov     rdx, [rcx]
0x1800012ab  mov     rax, [rdx+10h]
0x1800012af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012b4  mov     eax, ebx
0x1800012b6  add     rsp, 98h
0x1800012bd  pop     r15
0x1800012bf  pop     r14
0x1800012c1  pop     r13
0x1800012c3  pop     r12
0x1800012c5  pop     rdi
0x1800012c6  pop     rsi
0x1800012c7  pop     rbx
0x1800012c8  pop     rbp
0x1800012c9  retn
0x1800012ca  mov     rax, [rcx]
0x1800012cd  mov     rax, [rax+0E0h]
0x1800012d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012d9  mov     ebx, eax
0x1800012db  test    eax, eax
0x1800012dd  jns     loc_18000123B
0x1800012e3  jmp     loc_180001251
0x1800012e8  mov     ecx, eax; int
0x1800012ea  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800012ef  jmp     loc_18000125E
0x1800012f4  mov     rcx, [rbp+57h+pvar+8]
0x1800012f8  lea     r8, [rbp+57h+var_98]
0x1800012fc  lea     rdx, IID_IWICPersistStream
0x180001303  mov     rax, [rcx]
0x180001306  mov     rax, [rax]
0x180001309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000130e  mov     ebx, eax
0x180001310  test    eax, eax
0x180001312  js      loc_180001251
0x180001318  lea     r8, [rbp+57h+ppstm]; ppstm
0x18000131c  mov     edx, 1; fDeleteOnRelease
0x180001321  xor     ecx, ecx; hGlobal
0x180001323  call    cs:__imp_CreateStreamOnHGlobal
0x180001329  mov     ebx, eax
0x18000132b  test    eax, eax
0x18000132d  js      loc_180001251
0x180001333  mov     rcx, [rbp+57h+var_98]
0x180001337  mov     r9d, r14d
0x18000133a  mov     r8d, [rdi+84h]
0x180001341  mov     rdx, [rbp+57h+ppstm]
0x180001345  mov     rax, [rcx]
0x180001348  mov     rax, [rax+48h]
0x18000134c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001351  mov     ebx, eax
0x180001353  test    eax, eax
0x180001355  js      loc_180001251
0x18000135b  mov     rcx, [rbp+57h+ppstm]
0x18000135f  xor     r9d, r9d
0x180001362  mov     rdx, [rbp+57h+var_88]
0x180001366  xor     r8d, r8d
0x180001369  mov     rax, [rcx]
0x18000136c  mov     rax, [rax+28h]
0x180001370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001375  mov     ebx, eax
0x180001377  test    eax, eax
0x180001379  js      loc_180001251
0x18000137f  mov     rax, [rdi]
0x180001382  lea     rdx, [rbp+57h+var_90]
0x180001386  mov     rcx, rdi
0x180001389  mov     rax, [rax+108h]
0x180001390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001395  mov     ebx, eax
0x180001397  test    eax, eax
0x180001399  js      loc_180001251
0x18000139f  mov     rcx, [rbp+57h+var_90]
0x1800013a3  lea     r8, [rbp+57h+arg_8]
0x1800013a7  mov     eax, 0Dh
0x1800013ac  mov     [rbp+57h+var_50], r13
0x1800013b0  mov     word ptr [rbp+57h+var_60], ax
0x1800013b4  lea     rdx, [rbp+57h+var_60]
0x1800013b8  mov     rax, [rbp+57h+ppstm]
0x1800013bc  mov     qword ptr [rbp+57h+var_60+8], rax
0x1800013c0  mov     rax, [rcx]
0x1800013c3  movups  xmm0, [rbp+57h+var_60]
0x1800013c7  mov     rax, [rax+1D0h]
0x1800013ce  movaps  [rbp+57h+var_60], xmm0
0x1800013d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013d7  mov     ebx, eax
0x1800013d9  test    eax, eax
0x1800013db  js      loc_180001251
0x1800013e1  jz      short loc_1800013FC
0x1800013e3  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800013ea  mov     ebx, 80004005h
0x1800013ef  jz      loc_18000125E
0x1800013f5  mov     ecx, ebx
0x1800013f7  jmp     loc_1800012EA
0x1800013fc  mov     rcx, [rbp+57h+var_90]
0x180001400  mov     rdx, r15
0x180001403  mov     rax, [rcx]
0x180001406  mov     rax, [rax+68h]
0x18000140a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000140f  mov     ebx, eax
0x180001411  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180001417  test    ebx, ebx
0x180001419  jns     short loc_18000141F
0x18000141b  test    eax, eax
0x18000141d  jnz     short loc_1800013F5
0x18000141f  cmp     ebx, 1
0x180001422  jl      loc_18000125E
0x180001428  test    eax, eax
0x18000142a  jmp     short loc_1800013EA
```
