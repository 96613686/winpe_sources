# CJpegTurboFrameEncode::AssignThumbnailWriter(IWICMetadataWriter *,uchar *,uint,uint,uint)

- ea: `0x1801b8690`
- end: `0x1801b8a9d`
- name: `?AssignThumbnailWriter@CJpegTurboFrameEncode@@EEAAJPEAUIWICMetadataWriter@@PEAEIII@Z`
- size: `1037`
- prototype: `int(CJpegTurboFrameEncode *__hidden this, struct IWICMetadataWriter *, unsigned __int8 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001fd00`

## callees

- `0x1800402f4`
- `0x1800bb784`
- `0x1800e2f90`
- `0x18017b528`
- `0x18017b540`
- `0x1801b8690`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b884a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b884a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b8800`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b88ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b88fe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b895a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b89b6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b8a33`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b8800`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b88ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b88fe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b895a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b89b6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b8a33`

## pseudocode

```c
__int64 __fastcall CJpegTurboFrameEncode::AssignThumbnailWriter(
        CJpegTurboFrameEncode *this,
        struct IWICMetadataWriter *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  SIZE_T v6; // r12
  int CodecFactory; // eax
  __int64 v11; // rsi
  unsigned int v12; // ebx
  int v13; // ecx
  char v14; // di
  void *v15; // rax
  void *v16; // rbx
  struct IWICMetadataWriterVtbl *lpVtbl; // rax
  __int64 v19; // [rsp+30h] [rbp-59h] BYREF
  PROPVARIANT pvar[2]; // [rsp+38h] [rbp-51h] BYREF
  void *v21; // [rsp+48h] [rbp-41h]
  __int128 v22; // [rsp+50h] [rbp-39h] BYREF
  __int64 v23; // [rsp+60h] [rbp-29h]
  void *v24; // [rsp+68h] [rbp-21h] BYREF
  __int128 Buf2; // [rsp+70h] [rbp-19h] BYREF

  v6 = a4;
  *(_QWORD *)&Buf2 = 0;
  v19 = 0;
  v24 = 0;
  v23 = 0;
  v21 = 0;
  v22 = 0;
  *(_OWORD *)pvar = 0;
  CodecFactory = GetCodecFactory((struct IWICComponentFactory **)&Buf2);
  v11 = Buf2;
  v12 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_26;
  LOWORD(v22) = 18;
  WORD4(v22) = 1;
  if ( ((int (__fastcall *)(struct IWICMetadataWriter *, _QWORD, __int128 *, PROPVARIANT *))a2->lpVtbl->GetValue)(
         a2,
         0,
         &v22,
         pvar) < 0 )
  {
    CodecFactory = (*(__int64 (__fastcall **)(__int64, GUID *, char *, __int64, __int64 *))(*(_QWORD *)v11 + 240LL))(
                     v11,
                     &GUID_MetadataFormatThumbnail,
                     (char *)this + 172,
                     0x10000,
                     &v19);
    v12 = CodecFactory;
    if ( CodecFactory < 0 )
      goto LABEL_26;
    v14 = 1;
  }
  else
  {
    if ( LOWORD(pvar[0]) != 13 || !pvar[1] )
      goto LABEL_8;
    Buf2 = 0;
    CodecFactory = (**(__int64 (__fastcall ***)(PROPVARIANT, GUID *, __int64 *))pvar[1])(
                     pvar[1],
                     &IID_IWICMetadataWriter,
                     &v19);
    v12 = CodecFactory;
    if ( CodecFactory < 0 )
      goto LABEL_26;
    CodecFactory = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v19 + 24LL))(v19, &Buf2);
    v12 = CodecFactory;
    if ( CodecFactory < 0 )
      goto LABEL_26;
    if ( memcmp_0(&GUID_MetadataFormatThumbnail, &Buf2, 0x10u) )
    {
LABEL_8:
      v12 = -2003292287;
LABEL_9:
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_29;
      v13 = v12;
      goto LABEL_28;
    }
    v14 = 0;
  }
  PropVariantClear(pvar);
  LOWORD(v22) = 18;
  WORD4(v22) = 259;
  LOWORD(pvar[0]) = 18;
  LOWORD(pvar[1]) = 6;
  CodecFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, PROPVARIANT *))(*(_QWORD *)v19 + 72LL))(
                   v19,
                   0,
                   &v22,
                   pvar);
  v12 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_26;
  v15 = CoTaskMemAlloc(v6);
  v16 = v15;
  if ( !v15 )
  {
    v12 = -2147024882;
    goto LABEL_9;
  }
  memcpy_0(v15, a3, v6);
  LOWORD(v22) = 0;
  LOWORD(pvar[0]) = 65;
  LODWORD(pvar[1]) = v6;
  v21 = v16;
  CodecFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, PROPVARIANT *))(*(_QWORD *)v19 + 72LL))(
                   v19,
                   0,
                   &v22,
                   pvar);
  v12 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_26;
  PropVariantClear(pvar);
  LOWORD(v22) = 18;
  WORD4(v22) = 296;
  LOWORD(pvar[0]) = 18;
  LOWORD(pvar[1]) = 2;
  CodecFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, PROPVARIANT *))(*(_QWORD *)v19 + 72LL))(
                   v19,
                   0,
                   &v22,
                   pvar);
  v12 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_26;
  PropVariantClear(pvar);
  *(_QWORD *)&Buf2 = a5 | 0x100000000LL;
  LOWORD(v22) = 18;
  WORD4(v22) = 282;
  LOWORD(pvar[0]) = 21;
  pvar[1] = (PROPVARIANT)Buf2;
  CodecFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, PROPVARIANT *))(*(_QWORD *)v19 + 72LL))(
                   v19,
                   0,
                   &v22,
                   pvar);
  v12 = CodecFactory;
  if ( CodecFactory < 0 )
    goto LABEL_26;
  PropVariantClear(pvar);
  LODWORD(Buf2) = a6;
  LOWORD(v22) = 18;
  WORD4(v22) = 283;
  LOWORD(pvar[0]) = 21;
  pvar[1] = (PROPVARIANT)Buf2;
  CodecFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, PROPVARIANT *))(*(_QWORD *)v19 + 72LL))(
                   v19,
                   0,
                   &v22,
                   pvar);
  v12 = CodecFactory;
  if ( CodecFactory < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_29;
LABEL_27:
    v13 = CodecFactory;
LABEL_28:
    DoStackCapture(v13);
    goto LABEL_29;
  }
  PropVariantClear(pvar);
  if ( v14 )
  {
    CodecFactory = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v19)(v19, &IID_IUnknown, &v24);
    v12 = CodecFactory;
    if ( CodecFactory < 0 )
      goto LABEL_26;
    LOWORD(v22) = 18;
    LOWORD(pvar[0]) = 13;
    pvar[1] = v24;
    lpVtbl = a2->lpVtbl;
    WORD4(v22) = 1;
    v24 = 0;
    CodecFactory = ((__int64 (__fastcall *)(struct IWICMetadataWriter *, _QWORD, __int128 *, PROPVARIANT *))lpVtbl->SetValue)(
                     a2,
                     0,
                     &v22,
                     pvar);
    v12 = CodecFactory;
    if ( CodecFactory < 0 )
    {
LABEL_26:
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_29;
      goto LABEL_27;
    }
  }
LABEL_29:
  PropVariantClear(pvar);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v24 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
  return v12;
}

```

## disassembly

```asm
0x1801b8690  push    rbp
0x1801b8692  push    rbx
0x1801b8693  push    rsi
0x1801b8694  push    rdi
0x1801b8695  push    r12
0x1801b8697  push    r13
0x1801b8699  push    r14
0x1801b869b  push    r15
0x1801b869d  lea     rbp, [rsp-0Fh]
0x1801b86a2  sub     rsp, 98h
0x1801b86a9  mov     rax, cs:__security_cookie
0x1801b86b0  xor     rax, rsp
0x1801b86b3  mov     [rbp+47h+var_50], rax
0x1801b86b7  xor     r14d, r14d
0x1801b86ba  mov     r12d, r9d
0x1801b86bd  xor     eax, eax
0x1801b86bf  mov     qword ptr [rbp+47h+Buf2], r14
0x1801b86c3  mov     rdi, rcx
0x1801b86c6  mov     [rbp+47h+var_A0], r14
0x1801b86ca  xorps   xmm0, xmm0
0x1801b86cd  mov     [rbp+47h+var_68], r14
0x1801b86d1  xorps   xmm1, xmm1
0x1801b86d4  mov     [rbp+47h+var_70], rax
0x1801b86d8  lea     rcx, [rbp+47h+Buf2]; struct IWICComponentFactory **
0x1801b86dc  mov     [rbp+47h+var_88], rax
0x1801b86e0  movups  [rbp+47h+var_80], xmm0
0x1801b86e4  mov     r13, r8
0x1801b86e7  mov     r15, rdx
0x1801b86ea  movups  xmmword ptr [rbp+47h+pvar], xmm1
0x1801b86ee  call    ?GetCodecFactory@@YAJPEAPEAUIWICComponentFactory@@@Z; GetCodecFactory(IWICComponentFactory * *)
0x1801b86f3  mov     rsi, qword ptr [rbp+47h+Buf2]
0x1801b86f7  mov     ebx, eax
0x1801b86f9  test    eax, eax
0x1801b86fb  js      loc_1801B8A1F
0x1801b8701  lea     eax, [r14+12h]
0x1801b8705  xor     edx, edx
0x1801b8707  mov     word ptr [rbp+47h+var_80], ax
0x1801b870b  lea     r9, [rbp+47h+pvar]
0x1801b870f  lea     eax, [r14+1]
0x1801b8713  mov     rcx, r15
0x1801b8716  mov     word ptr [rbp+47h+var_80+8], ax
0x1801b871a  lea     r8, [rbp+47h+var_80]
0x1801b871e  mov     rax, [r15]
0x1801b8721  mov     rax, [rax+38h]
0x1801b8725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b872a  lea     ecx, [r14+0Dh]
0x1801b872e  test    eax, eax
0x1801b8730  js      loc_1801B87C0
0x1801b8736  cmp     cx, word ptr [rbp+47h+pvar]
0x1801b873a  jnz     short loc_1801B87A2
0x1801b873c  mov     rcx, [rbp+47h+pvar+8]
0x1801b8740  test    rcx, rcx
0x1801b8743  jz      short loc_1801B87A2
0x1801b8745  xorps   xmm0, xmm0
0x1801b8748  lea     r8, [rbp+47h+var_A0]
0x1801b874c  movups  [rbp+47h+Buf2], xmm0
0x1801b8750  mov     rax, [rcx]
0x1801b8753  lea     rdx, IID_IWICMetadataWriter
0x1801b875a  mov     rax, [rax]
0x1801b875d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8762  mov     ebx, eax
0x1801b8764  test    eax, eax
0x1801b8766  js      loc_1801B8A1F
0x1801b876c  mov     rcx, [rbp+47h+var_A0]
0x1801b8770  lea     rdx, [rbp+47h+Buf2]
0x1801b8774  mov     rax, [rcx]
0x1801b8777  mov     rax, [rax+18h]
0x1801b877b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8780  mov     ebx, eax
0x1801b8782  test    eax, eax
0x1801b8784  js      loc_1801B8A1F
0x1801b878a  lea     r8d, [r14+10h]; Size
0x1801b878e  lea     rdx, [rbp+47h+Buf2]; Buf2
0x1801b8792  lea     rcx, GUID_MetadataFormatThumbnail; Buf1
0x1801b8799  call    memcmp_0
0x1801b879e  test    eax, eax
0x1801b87a0  jz      short loc_1801B87BB
0x1801b87a2  mov     ebx, 88982F81h
0x1801b87a7  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1801b87ae  jz      loc_1801B8A2F
0x1801b87b4  mov     ecx, ebx
0x1801b87b6  jmp     loc_1801B8A2A
0x1801b87bb  mov     dil, r14b
0x1801b87be  jmp     short loc_1801B87FC
0x1801b87c0  mov     rax, [rsi]
0x1801b87c3  lea     rcx, [rbp+47h+var_A0]
0x1801b87c7  mov     [rsp+0D0h+var_B0], rcx
0x1801b87cc  lea     r8, [rdi+0ACh]
0x1801b87d3  mov     r9d, 10000h
0x1801b87d9  lea     rdx, GUID_MetadataFormatThumbnail
0x1801b87e0  mov     rcx, rsi
0x1801b87e3  mov     rax, [rax+0F0h]
0x1801b87ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b87ef  mov     ebx, eax
0x1801b87f1  test    eax, eax
0x1801b87f3  js      loc_1801B8A1F
0x1801b87f9  mov     dil, 1
0x1801b87fc  lea     rcx, [rbp+47h+pvar]; pvar
0x1801b8800  call    cs:__imp_PropVariantClear
0x1801b8806  mov     ecx, 12h
0x1801b880b  lea     r9, [rbp+47h+pvar]
0x1801b880f  mov     eax, 103h
0x1801b8814  mov     word ptr [rbp+47h+var_80], cx
0x1801b8818  mov     word ptr [rbp+47h+var_80+8], ax
0x1801b881c  lea     r8, [rbp+47h+var_80]
0x1801b8820  mov     word ptr [rbp+47h+pvar], cx
0x1801b8824  xor     edx, edx
0x1801b8826  lea     eax, [rcx-0Ch]
0x1801b8829  mov     rcx, [rbp+47h+var_A0]
0x1801b882d  mov     word ptr [rbp+47h+pvar+8], ax
0x1801b8831  mov     rax, [rcx]
0x1801b8834  mov     rax, [rax+48h]
0x1801b8838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b883d  mov     ebx, eax
0x1801b883f  test    eax, eax
0x1801b8841  js      loc_1801B8A1F
0x1801b8847  mov     rcx, r12; cb
0x1801b884a  call    cs:__imp_CoTaskMemAlloc
0x1801b8850  mov     rbx, rax
0x1801b8853  test    rax, rax
0x1801b8856  jnz     short loc_1801B8862
0x1801b8858  mov     ebx, 8007000Eh
0x1801b885d  jmp     loc_1801B87A7
0x1801b8862  mov     r8, r12; Size
0x1801b8865  mov     rdx, r13; Src
0x1801b8868  mov     rcx, rbx; void *
0x1801b886b  call    memcpy_0
0x1801b8870  mov     rcx, [rbp+47h+var_A0]
0x1801b8874  lea     r9, [rbp+47h+pvar]
0x1801b8878  mov     eax, 41h ; 'A'
0x1801b887d  mov     word ptr [rbp+47h+var_80], r14w
0x1801b8882  mov     word ptr [rbp+47h+pvar], ax
0x1801b8886  lea     r8, [rbp+47h+var_80]
0x1801b888a  mov     dword ptr [rbp+47h+pvar+8], r12d
0x1801b888e  xor     edx, edx
0x1801b8890  mov     [rbp+47h+var_88], rbx
0x1801b8894  mov     rax, [rcx]
0x1801b8897  mov     rax, [rax+48h]
0x1801b889b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b88a0  mov     ebx, eax
0x1801b88a2  test    eax, eax
0x1801b88a4  js      loc_1801B8A1F
0x1801b88aa  lea     rcx, [rbp+47h+pvar]; pvar
0x1801b88ae  call    cs:__imp_PropVariantClear
0x1801b88b4  mov     rcx, [rbp+47h+var_A0]
0x1801b88b8  lea     r9, [rbp+47h+pvar]
0x1801b88bc  mov     r12d, 12h
0x1801b88c2  lea     r8, [rbp+47h+var_80]
0x1801b88c6  mov     eax, 128h
0x1801b88cb  mov     word ptr [rbp+47h+var_80], r12w
0x1801b88d0  mov     word ptr [rbp+47h+var_80+8], ax
0x1801b88d4  xor     edx, edx
0x1801b88d6  mov     word ptr [rbp+47h+pvar], r12w
0x1801b88db  lea     eax, [r12-10h]
0x1801b88e0  mov     word ptr [rbp+47h+pvar+8], ax
0x1801b88e4  mov     rax, [rcx]
0x1801b88e7  mov     rax, [rax+48h]
0x1801b88eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b88f0  mov     ebx, eax
0x1801b88f2  test    eax, eax
0x1801b88f4  js      loc_1801B8A1F
0x1801b88fa  lea     rcx, [rbp+47h+pvar]; pvar
0x1801b88fe  call    cs:__imp_PropVariantClear
0x1801b8904  mov     eax, [rbp+47h+arg_20]
0x1801b8907  lea     r13d, [r12-11h]
0x1801b890c  mov     rcx, [rbp+47h+var_A0]
0x1801b8910  lea     r9, [rbp+47h+pvar]
0x1801b8914  mov     dword ptr [rbp+47h+Buf2], eax
0x1801b8917  lea     r8, [rbp+47h+var_80]
0x1801b891b  mov     eax, 11Ah
0x1801b8920  mov     word ptr [rbp+47h+var_80], r12w
0x1801b8925  mov     word ptr [rbp+47h+var_80+8], ax
0x1801b8929  xor     edx, edx
0x1801b892b  lea     eax, [r12+3]
0x1801b8930  mov     dword ptr [rbp+47h+Buf2+4], r13d
0x1801b8934  mov     word ptr [rbp+47h+pvar], ax
0x1801b8938  mov     rax, qword ptr [rbp+47h+Buf2]
0x1801b893c  mov     [rbp+47h+pvar+8], rax
0x1801b8940  mov     rax, [rcx]
0x1801b8943  mov     rax, [rax+48h]
0x1801b8947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b894c  mov     ebx, eax
0x1801b894e  test    eax, eax
0x1801b8950  js      loc_1801B8A1F
0x1801b8956  lea     rcx, [rbp+47h+pvar]; pvar
0x1801b895a  call    cs:__imp_PropVariantClear
0x1801b8960  mov     eax, [rbp+47h+arg_28]
0x1801b8963  lea     r9, [rbp+47h+pvar]
0x1801b8967  mov     rcx, [rbp+47h+var_A0]
0x1801b896b  lea     r8, [rbp+47h+var_80]
0x1801b896f  mov     dword ptr [rbp+47h+Buf2], eax
0x1801b8972  xor     edx, edx
0x1801b8974  mov     eax, 11Bh
0x1801b8979  mov     word ptr [rbp+47h+var_80], r12w
0x1801b897e  mov     word ptr [rbp+47h+var_80+8], ax
0x1801b8982  lea     eax, [r12+3]
0x1801b8987  mov     word ptr [rbp+47h+pvar], ax
0x1801b898b  mov     rax, qword ptr [rbp+47h+Buf2]
0x1801b898f  mov     [rbp+47h+pvar+8], rax
0x1801b8993  mov     rax, [rcx]
0x1801b8996  mov     rax, [rax+48h]
0x1801b899a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b899f  mov     ebx, eax
0x1801b89a1  test    eax, eax
0x1801b89a3  jns     short loc_1801B89B2
0x1801b89a5  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1801b89ac  jnz     short loc_1801B8A28
0x1801b89ae  test    eax, eax
0x1801b89b0  js      short loc_1801B8A2F
0x1801b89b2  lea     rcx, [rbp+47h+pvar]; pvar
0x1801b89b6  call    cs:__imp_PropVariantClear
0x1801b89bc  test    dil, dil
0x1801b89bf  jz      short loc_1801B8A2F
0x1801b89c1  mov     rcx, [rbp+47h+var_A0]
0x1801b89c5  lea     r8, [rbp+47h+var_68]
0x1801b89c9  lea     rdx, IID_IUnknown
0x1801b89d0  mov     rax, [rcx]
0x1801b89d3  mov     rax, [rax]
0x1801b89d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b89db  mov     ebx, eax
0x1801b89dd  test    eax, eax
0x1801b89df  js      short loc_1801B8A1F
0x1801b89e1  mov     eax, 0Dh
0x1801b89e6  mov     word ptr [rbp+47h+var_80], r12w
0x1801b89eb  mov     word ptr [rbp+47h+pvar], ax
0x1801b89ef  lea     r9, [rbp+47h+pvar]
0x1801b89f3  mov     rax, [rbp+47h+var_68]
0x1801b89f7  lea     r8, [rbp+47h+var_80]
0x1801b89fb  mov     [rbp+47h+pvar+8], rax
0x1801b89ff  xor     edx, edx
0x1801b8a01  mov     rax, [r15]
0x1801b8a04  mov     rcx, r15
0x1801b8a07  mov     word ptr [rbp+47h+var_80+8], r13w
0x1801b8a0c  mov     [rbp+47h+var_68], r14
0x1801b8a10  mov     rax, [rax+48h]
0x1801b8a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8a19  mov     ebx, eax
0x1801b8a1b  test    eax, eax
0x1801b8a1d  jns     short loc_1801B8A2F
0x1801b8a1f  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1801b8a26  jz      short loc_1801B8A2F
0x1801b8a28  mov     ecx, eax; int
0x1801b8a2a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b8a2f  lea     rcx, [rbp+47h+pvar]; pvar
0x1801b8a33  call    cs:__imp_PropVariantClear
0x1801b8a39  test    rsi, rsi
0x1801b8a3c  jz      short loc_1801B8A4D
0x1801b8a3e  mov     rax, [rsi]
0x1801b8a41  mov     rcx, rsi
0x1801b8a44  mov     rax, [rax+10h]
0x1801b8a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8a4d  mov     rcx, [rbp+47h+var_A0]
0x1801b8a51  test    rcx, rcx
0x1801b8a54  jz      short loc_1801B8A66
0x1801b8a56  mov     rax, [rcx]
0x1801b8a59  mov     rax, [rax+10h]
0x1801b8a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8a62  mov     [rbp+47h+var_A0], r14
0x1801b8a66  mov     rcx, [rbp+47h+var_68]
0x1801b8a6a  test    rcx, rcx
0x1801b8a6d  jz      short loc_1801B8A7B
0x1801b8a6f  mov     rdx, [rcx]
0x1801b8a72  mov     rax, [rdx+10h]
0x1801b8a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8a7b  mov     eax, ebx
0x1801b8a7d  mov     rcx, [rbp+47h+var_50]
0x1801b8a81  xor     rcx, rsp; StackCookie
0x1801b8a84  call    __security_check_cookie
0x1801b8a89  add     rsp, 98h
0x1801b8a90  pop     r15
0x1801b8a92  pop     r14
0x1801b8a94  pop     r13
0x1801b8a96  pop     r12
0x1801b8a98  pop     rdi
0x1801b8a99  pop     rsi
0x1801b8a9a  pop     rbx
0x1801b8a9b  pop     rbp
0x1801b8a9c  retn
```
