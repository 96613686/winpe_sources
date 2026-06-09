# CJpegTurboFrameEncode::AssignThumbnailWriter(IWICMetadataWriter *,uchar *,uint,uint,uint)

- ea: `0x1801bbec0`
- end: `0x1801bc300`
- name: `?AssignThumbnailWriter@CJpegTurboFrameEncode@@EEAAJPEAUIWICMetadataWriter@@PEAEIII@Z`
- size: `1088`
- prototype: `int(CJpegTurboFrameEncode *__hidden this, struct IWICMetadataWriter *, unsigned __int8 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180042d00`

## callees

- `0x180031b78`
- `0x1800bd9d4`
- `0x1800e5e60`
- `0x18017e438`
- `0x18017e450`
- `0x1801bbec0`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801bc080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801bc080`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801bc030`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801bc0ea`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801bc140`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801bc1a2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801bc20c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801bc28f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801bc030`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801bc0ea`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801bc140`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801bc1a2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801bc20c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801bc28f`

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
0x1801bbec0  push    rbp
0x1801bbec2  push    rbx
0x1801bbec3  push    rsi
0x1801bbec4  push    rdi
0x1801bbec5  push    r12
0x1801bbec7  push    r13
0x1801bbec9  push    r14
0x1801bbecb  push    r15
0x1801bbecd  lea     rbp, [rsp-0Fh]
0x1801bbed2  sub     rsp, 98h
0x1801bbed9  mov     rax, cs:__security_cookie
0x1801bbee0  xor     rax, rsp
0x1801bbee3  mov     [rbp+47h+var_50], rax
0x1801bbee7  xor     r14d, r14d
0x1801bbeea  mov     r12d, r9d
0x1801bbeed  xor     eax, eax
0x1801bbeef  mov     qword ptr [rbp+47h+Buf2], r14
0x1801bbef3  mov     rdi, rcx
0x1801bbef6  mov     [rbp+47h+var_A0], r14
0x1801bbefa  xorps   xmm0, xmm0
0x1801bbefd  mov     [rbp+47h+var_68], r14
0x1801bbf01  xorps   xmm1, xmm1
0x1801bbf04  mov     [rbp+47h+var_70], rax
0x1801bbf08  lea     rcx, [rbp+47h+Buf2]; struct IWICComponentFactory **
0x1801bbf0c  mov     [rbp+47h+var_88], rax
0x1801bbf10  movups  [rbp+47h+var_80], xmm0
0x1801bbf14  mov     r13, r8
0x1801bbf17  mov     r15, rdx
0x1801bbf1a  movups  xmmword ptr [rbp+47h+pvar], xmm1
0x1801bbf1e  call    ?GetCodecFactory@@YAJPEAPEAUIWICComponentFactory@@@Z; GetCodecFactory(IWICComponentFactory * *)
0x1801bbf23  mov     rsi, qword ptr [rbp+47h+Buf2]
0x1801bbf27  mov     ebx, eax
0x1801bbf29  test    eax, eax
0x1801bbf2b  js      loc_1801BC27B
0x1801bbf31  lea     eax, [r14+12h]
0x1801bbf35  xor     edx, edx
0x1801bbf37  mov     word ptr [rbp+47h+var_80], ax
0x1801bbf3b  lea     r9, [rbp+47h+pvar]
0x1801bbf3f  lea     eax, [r14+1]
0x1801bbf43  mov     rcx, r15
0x1801bbf46  mov     word ptr [rbp+47h+var_80+8], ax
0x1801bbf4a  lea     r8, [rbp+47h+var_80]
0x1801bbf4e  mov     rax, [r15]
0x1801bbf51  mov     rax, [rax+38h]
0x1801bbf55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bbf5a  lea     ecx, [r14+0Dh]
0x1801bbf5e  test    eax, eax
0x1801bbf60  js      loc_1801BBFF0
0x1801bbf66  cmp     cx, word ptr [rbp+47h+pvar]
0x1801bbf6a  jnz     short loc_1801BBFD2
0x1801bbf6c  mov     rcx, [rbp+47h+pvar+8]
0x1801bbf70  test    rcx, rcx
0x1801bbf73  jz      short loc_1801BBFD2
0x1801bbf75  xorps   xmm0, xmm0
0x1801bbf78  lea     r8, [rbp+47h+var_A0]
0x1801bbf7c  movups  [rbp+47h+Buf2], xmm0
0x1801bbf80  mov     rax, [rcx]
0x1801bbf83  lea     rdx, IID_IWICMetadataWriter
0x1801bbf8a  mov     rax, [rax]
0x1801bbf8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bbf92  mov     ebx, eax
0x1801bbf94  test    eax, eax
0x1801bbf96  js      loc_1801BC27B
0x1801bbf9c  mov     rcx, [rbp+47h+var_A0]
0x1801bbfa0  lea     rdx, [rbp+47h+Buf2]
0x1801bbfa4  mov     rax, [rcx]
0x1801bbfa7  mov     rax, [rax+18h]
0x1801bbfab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bbfb0  mov     ebx, eax
0x1801bbfb2  test    eax, eax
0x1801bbfb4  js      loc_1801BC27B
0x1801bbfba  lea     r8d, [r14+10h]; Size
0x1801bbfbe  lea     rdx, [rbp+47h+Buf2]; Buf2
0x1801bbfc2  lea     rcx, GUID_MetadataFormatThumbnail; Buf1
0x1801bbfc9  call    memcmp_0
0x1801bbfce  test    eax, eax
0x1801bbfd0  jz      short loc_1801BBFEB
0x1801bbfd2  mov     ebx, 88982F81h
0x1801bbfd7  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1801bbfde  jz      loc_1801BC28B
0x1801bbfe4  mov     ecx, ebx
0x1801bbfe6  jmp     loc_1801BC286
0x1801bbfeb  mov     dil, r14b
0x1801bbfee  jmp     short loc_1801BC02C
0x1801bbff0  mov     rax, [rsi]
0x1801bbff3  lea     rcx, [rbp+47h+var_A0]
0x1801bbff7  mov     [rsp+0D0h+var_B0], rcx
0x1801bbffc  lea     r8, [rdi+0ACh]
0x1801bc003  mov     r9d, 10000h
0x1801bc009  lea     rdx, GUID_MetadataFormatThumbnail
0x1801bc010  mov     rcx, rsi
0x1801bc013  mov     rax, [rax+0F0h]
0x1801bc01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc01f  mov     ebx, eax
0x1801bc021  test    eax, eax
0x1801bc023  js      loc_1801BC27B
0x1801bc029  mov     dil, 1
0x1801bc02c  lea     rcx, [rbp+47h+pvar]; pvar
0x1801bc030  call    cs:__imp_PropVariantClear
0x1801bc037  nop     dword ptr [rax+rax+00h]
0x1801bc03c  mov     ecx, 12h
0x1801bc041  lea     r9, [rbp+47h+pvar]
0x1801bc045  mov     eax, 103h
0x1801bc04a  mov     word ptr [rbp+47h+var_80], cx
0x1801bc04e  mov     word ptr [rbp+47h+var_80+8], ax
0x1801bc052  lea     r8, [rbp+47h+var_80]
0x1801bc056  mov     word ptr [rbp+47h+pvar], cx
0x1801bc05a  xor     edx, edx
0x1801bc05c  lea     eax, [rcx-0Ch]
0x1801bc05f  mov     rcx, [rbp+47h+var_A0]
0x1801bc063  mov     word ptr [rbp+47h+pvar+8], ax
0x1801bc067  mov     rax, [rcx]
0x1801bc06a  mov     rax, [rax+48h]
0x1801bc06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc073  mov     ebx, eax
0x1801bc075  test    eax, eax
0x1801bc077  js      loc_1801BC27B
0x1801bc07d  mov     rcx, r12; cb
0x1801bc080  call    cs:__imp_CoTaskMemAlloc
0x1801bc087  nop     dword ptr [rax+rax+00h]
0x1801bc08c  mov     rbx, rax
0x1801bc08f  test    rax, rax
0x1801bc092  jnz     short loc_1801BC09E
0x1801bc094  mov     ebx, 8007000Eh
0x1801bc099  jmp     loc_1801BBFD7
0x1801bc09e  mov     r8, r12; Size
0x1801bc0a1  mov     rdx, r13; Src
0x1801bc0a4  mov     rcx, rbx; void *
0x1801bc0a7  call    memcpy_0
0x1801bc0ac  mov     rcx, [rbp+47h+var_A0]
0x1801bc0b0  lea     r9, [rbp+47h+pvar]
0x1801bc0b4  mov     eax, 41h ; 'A'
0x1801bc0b9  mov     word ptr [rbp+47h+var_80], r14w
0x1801bc0be  mov     word ptr [rbp+47h+pvar], ax
0x1801bc0c2  lea     r8, [rbp+47h+var_80]
0x1801bc0c6  mov     dword ptr [rbp+47h+pvar+8], r12d
0x1801bc0ca  xor     edx, edx
0x1801bc0cc  mov     [rbp+47h+var_88], rbx
0x1801bc0d0  mov     rax, [rcx]
0x1801bc0d3  mov     rax, [rax+48h]
0x1801bc0d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc0dc  mov     ebx, eax
0x1801bc0de  test    eax, eax
0x1801bc0e0  js      loc_1801BC27B
0x1801bc0e6  lea     rcx, [rbp+47h+pvar]; pvar
0x1801bc0ea  call    cs:__imp_PropVariantClear
0x1801bc0f1  nop     dword ptr [rax+rax+00h]
0x1801bc0f6  mov     rcx, [rbp+47h+var_A0]
0x1801bc0fa  lea     r9, [rbp+47h+pvar]
0x1801bc0fe  mov     r12d, 12h
0x1801bc104  lea     r8, [rbp+47h+var_80]
0x1801bc108  mov     eax, 128h
0x1801bc10d  mov     word ptr [rbp+47h+var_80], r12w
0x1801bc112  mov     word ptr [rbp+47h+var_80+8], ax
0x1801bc116  xor     edx, edx
0x1801bc118  mov     word ptr [rbp+47h+pvar], r12w
0x1801bc11d  lea     eax, [r12-10h]
0x1801bc122  mov     word ptr [rbp+47h+pvar+8], ax
0x1801bc126  mov     rax, [rcx]
0x1801bc129  mov     rax, [rax+48h]
0x1801bc12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc132  mov     ebx, eax
0x1801bc134  test    eax, eax
0x1801bc136  js      loc_1801BC27B
0x1801bc13c  lea     rcx, [rbp+47h+pvar]; pvar
0x1801bc140  call    cs:__imp_PropVariantClear
0x1801bc147  nop     dword ptr [rax+rax+00h]
0x1801bc14c  mov     eax, [rbp+47h+arg_20]
0x1801bc14f  lea     r13d, [r12-11h]
0x1801bc154  mov     rcx, [rbp+47h+var_A0]
0x1801bc158  lea     r9, [rbp+47h+pvar]
0x1801bc15c  mov     dword ptr [rbp+47h+Buf2], eax
0x1801bc15f  lea     r8, [rbp+47h+var_80]
0x1801bc163  mov     eax, 11Ah
0x1801bc168  mov     word ptr [rbp+47h+var_80], r12w
0x1801bc16d  mov     word ptr [rbp+47h+var_80+8], ax
0x1801bc171  xor     edx, edx
0x1801bc173  lea     eax, [r12+3]
0x1801bc178  mov     dword ptr [rbp+47h+Buf2+4], r13d
0x1801bc17c  mov     word ptr [rbp+47h+pvar], ax
0x1801bc180  mov     rax, qword ptr [rbp+47h+Buf2]
0x1801bc184  mov     [rbp+47h+pvar+8], rax
0x1801bc188  mov     rax, [rcx]
0x1801bc18b  mov     rax, [rax+48h]
0x1801bc18f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc194  mov     ebx, eax
0x1801bc196  test    eax, eax
0x1801bc198  js      loc_1801BC27B
0x1801bc19e  lea     rcx, [rbp+47h+pvar]; pvar
0x1801bc1a2  call    cs:__imp_PropVariantClear
0x1801bc1a9  nop     dword ptr [rax+rax+00h]
0x1801bc1ae  mov     eax, [rbp+47h+arg_28]
0x1801bc1b1  lea     r9, [rbp+47h+pvar]
0x1801bc1b5  mov     rcx, [rbp+47h+var_A0]
0x1801bc1b9  lea     r8, [rbp+47h+var_80]
0x1801bc1bd  mov     dword ptr [rbp+47h+Buf2], eax
0x1801bc1c0  xor     edx, edx
0x1801bc1c2  mov     eax, 11Bh
0x1801bc1c7  mov     word ptr [rbp+47h+var_80], r12w
0x1801bc1cc  mov     word ptr [rbp+47h+var_80+8], ax
0x1801bc1d0  lea     eax, [r12+3]
0x1801bc1d5  mov     word ptr [rbp+47h+pvar], ax
0x1801bc1d9  mov     rax, qword ptr [rbp+47h+Buf2]
0x1801bc1dd  mov     [rbp+47h+pvar+8], rax
0x1801bc1e1  mov     rax, [rcx]
0x1801bc1e4  mov     rax, [rax+48h]
0x1801bc1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc1ed  mov     ebx, eax
0x1801bc1ef  test    eax, eax
0x1801bc1f1  jns     short loc_1801BC208
0x1801bc1f3  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1801bc1fa  jnz     loc_1801BC284
0x1801bc200  test    eax, eax
0x1801bc202  js      loc_1801BC28B
0x1801bc208  lea     rcx, [rbp+47h+pvar]; pvar
0x1801bc20c  call    cs:__imp_PropVariantClear
0x1801bc213  nop     dword ptr [rax+rax+00h]
0x1801bc218  test    dil, dil
0x1801bc21b  jz      short loc_1801BC28B
0x1801bc21d  mov     rcx, [rbp+47h+var_A0]
0x1801bc221  lea     r8, [rbp+47h+var_68]
0x1801bc225  lea     rdx, IID_IUnknown
0x1801bc22c  mov     rax, [rcx]
0x1801bc22f  mov     rax, [rax]
0x1801bc232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc237  mov     ebx, eax
0x1801bc239  test    eax, eax
0x1801bc23b  js      short loc_1801BC27B
0x1801bc23d  mov     eax, 0Dh
0x1801bc242  mov     word ptr [rbp+47h+var_80], r12w
0x1801bc247  mov     word ptr [rbp+47h+pvar], ax
0x1801bc24b  lea     r9, [rbp+47h+pvar]
0x1801bc24f  mov     rax, [rbp+47h+var_68]
0x1801bc253  lea     r8, [rbp+47h+var_80]
0x1801bc257  mov     [rbp+47h+pvar+8], rax
0x1801bc25b  xor     edx, edx
0x1801bc25d  mov     rax, [r15]
0x1801bc260  mov     rcx, r15
0x1801bc263  mov     word ptr [rbp+47h+var_80+8], r13w
0x1801bc268  mov     [rbp+47h+var_68], r14
0x1801bc26c  mov     rax, [rax+48h]
0x1801bc270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc275  mov     ebx, eax
0x1801bc277  test    eax, eax
0x1801bc279  jns     short loc_1801BC28B
0x1801bc27b  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1801bc282  jz      short loc_1801BC28B
0x1801bc284  mov     ecx, eax; int
0x1801bc286  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801bc28b  lea     rcx, [rbp+47h+pvar]; pvar
0x1801bc28f  call    cs:__imp_PropVariantClear
0x1801bc296  nop     dword ptr [rax+rax+00h]
0x1801bc29b  test    rsi, rsi
0x1801bc29e  jz      short loc_1801BC2AF
0x1801bc2a0  mov     rax, [rsi]
0x1801bc2a3  mov     rcx, rsi
0x1801bc2a6  mov     rax, [rax+10h]
0x1801bc2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc2af  mov     rcx, [rbp+47h+var_A0]
0x1801bc2b3  test    rcx, rcx
0x1801bc2b6  jz      short loc_1801BC2C8
0x1801bc2b8  mov     rax, [rcx]
0x1801bc2bb  mov     rax, [rax+10h]
0x1801bc2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc2c4  mov     [rbp+47h+var_A0], r14
0x1801bc2c8  mov     rcx, [rbp+47h+var_68]
0x1801bc2cc  test    rcx, rcx
0x1801bc2cf  jz      short loc_1801BC2DD
0x1801bc2d1  mov     rdx, [rcx]
0x1801bc2d4  mov     rax, [rdx+10h]
0x1801bc2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc2dd  mov     eax, ebx
0x1801bc2df  mov     rcx, [rbp+47h+var_50]
0x1801bc2e3  xor     rcx, rsp; StackCookie
0x1801bc2e6  call    __security_check_cookie
0x1801bc2eb  add     rsp, 98h
0x1801bc2f2  pop     r15
0x1801bc2f4  pop     r14
0x1801bc2f6  pop     r13
0x1801bc2f8  pop     r12
0x1801bc2fa  pop     rdi
0x1801bc2fb  pop     rsi
0x1801bc2fc  pop     rbx
0x1801bc2fd  pop     rbp
0x1801bc2fe  retn
```
