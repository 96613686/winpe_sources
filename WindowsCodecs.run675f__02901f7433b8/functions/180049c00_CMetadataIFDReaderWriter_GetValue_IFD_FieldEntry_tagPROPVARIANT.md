# CMetadataIFDReaderWriter::GetValue(IFD::FieldEntry *,tagPROPVARIANT *)

- ea: `0x180049c00`
- end: `0x180049eaf`
- name: `?GetValue@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(CMetadataIFDReaderWriter *__hidden this, struct IFD::FieldEntry *, PROPVARIANT *pvarSrc)`
- caller_count: `4`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002cde0`
- `0x18002fdc0`
- `0x180049790`
- `0x18004d880`

## callees

- `0x18002cb08`
- `0x18002dc34`
- `0x180048f40`
- `0x180049c00`
- `0x180049eb8`
- `0x180049f00`
- `0x18004a284`
- `0x18004a828`
- `0x18004c5c0`
- `0x1800bd9d4`
- `0x1800e5e60`
- `0x1801b8a4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180049cbc`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180049cbc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049cef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049cff`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049db5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049cef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049cff`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049db5`

## pseudocode

```c
__int64 __fastcall CMetadataIFDReaderWriter::GetValue(
        CStreamBase **this,
        struct IFD::FieldEntry *a2,
        PROPVARIANT *pvarSrc)
{
  int v4; // ecx
  int v7; // ebx
  _DWORD *v8; // r12
  unsigned int v9; // ecx
  int TagVariantValueForEmbeddedMetadata; // eax
  int v12; // ecx
  void *v13; // xmm1_8
  int v14; // eax
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-59h] BYREF
  void *v16; // [rsp+30h] [rbp-49h]
  _BYTE v17[4]; // [rsp+40h] [rbp-39h] BYREF
  int v18; // [rsp+44h] [rbp-35h]
  _BYTE v19[72]; // [rsp+58h] [rbp-21h] BYREF

  v4 = *((_DWORD *)a2 + 4);
  v16 = 0;
  *(_OWORD *)pvar = 0;
  if ( (v4 & 8) != 0 )
  {
    v7 = -2003292352;
    if ( (_DWORD)g_doStackCaptures )
    {
      v12 = -2003292352;
LABEL_25:
      DoStackCapture(v12);
      goto LABEL_17;
    }
    goto LABEL_17;
  }
  if ( (v4 & 2) != 0 )
  {
    TagVariantValueForEmbeddedMetadata = PropVariantCopy(pvarSrc, (const PROPVARIANT *)a2 + 4);
LABEL_14:
    v7 = TagVariantValueForEmbeddedMetadata;
    if ( TagVariantValueForEmbeddedMetadata >= 0 )
      goto LABEL_15;
    if ( (_DWORD)g_doStackCaptures )
    {
LABEL_24:
      v12 = TagVariantValueForEmbeddedMetadata;
      goto LABEL_25;
    }
LABEL_17:
    PropVariantClear(pvarSrc);
    goto LABEL_18;
  }
  v7 = 0;
  if ( this[15] )
  {
    if ( *(_WORD *)a2 != 0xEA1C )
    {
      if ( *((_QWORD *)a2 + 7) )
      {
        TagVariantValueForEmbeddedMetadata = CMetadataIFDReaderWriter::GetTagVariantValueForEmbeddedMetadata(
                                               this,
                                               (PROPVARIANT *)a2,
                                               pvarSrc);
      }
      else
      {
        if ( (v4 & 0x80u) == 0 )
        {
          v8 = (_DWORD *)((char *)a2 + 20);
          if ( (v4 & 0x10) == 0 )
          {
            v7 = IFD::TagEntry::ComputeTagDataSize(a2, (unsigned int *)a2 + 5);
            if ( v7 < 0 )
            {
              if ( (_DWORD)g_doStackCaptures )
              {
                DoStackCapture(v7);
                if ( (_DWORD)g_doStackCaptures )
                {
                  DoStackCapture(v7);
                  if ( (_DWORD)g_doStackCaptures )
                    DoStackCapture(v7);
                }
              }
              goto LABEL_16;
            }
            *((_DWORD *)a2 + 4) |= 0x10u;
          }
          v9 = *((_DWORD *)a2 + 4) | 0x40;
          if ( *v8 > 4u )
            v9 = *((_DWORD *)a2 + 4) & 0xFFFFFFBF;
          v4 = v9 | 0x80;
          *((_DWORD *)a2 + 4) = v4;
        }
        if ( (v4 & 0x40) != 0 )
          TagVariantValueForEmbeddedMetadata = CMetadataIFDReaderWriter::GetTagVariantValueInline(
                                                 (CMetadataIFDReaderWriter *)this,
                                                 a2,
                                                 pvarSrc);
        else
          TagVariantValueForEmbeddedMetadata = CMetadataIFDReaderWriter::GetTagVariantValueAtOffset(
                                                 (CMetadataIFDReaderWriter *)this,
                                                 a2,
                                                 (struct tagPROPVARIANT *)pvarSrc);
      }
      goto LABEL_14;
    }
    CIFDPaddingManager::CIFDPaddingManager((CIFDPaddingManager *)v17);
    v14 = CIFDPaddingManager::InitializeFromField(
            (CIFDPaddingManager *)v17,
            a2,
            (struct IStream *)(((unsigned __int64)this[15] + 16) & -(__int64)(this[15] != 0)));
    v7 = v14;
    if ( v14 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v14);
      DynArrayImpl<1>::~DynArrayImpl<1>(v19);
      goto LABEL_17;
    }
    *((_DWORD *)pvarSrc + 2) = v18;
    *(_WORD *)pvarSrc = 19;
    DynArrayImpl<1>::~DynArrayImpl<1>(v19);
  }
LABEL_15:
  if ( (unsigned int)IFD::FieldEntry::IsCommentTag(a2) && *(_WORD *)pvarSrc == 65 )
  {
    TagVariantValueForEmbeddedMetadata = ConvertCommentOnRead(pvarSrc, pvar);
    v7 = TagVariantValueForEmbeddedMetadata;
    if ( TagVariantValueForEmbeddedMetadata >= 0 )
    {
      PropVariantClear(pvarSrc);
      v13 = v16;
      *(_OWORD *)pvarSrc = *(_OWORD *)pvar;
      v16 = 0;
      pvarSrc[2] = v13;
      *(_OWORD *)pvar = 0;
      goto LABEL_18;
    }
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_17;
    goto LABEL_24;
  }
LABEL_16:
  if ( v7 < 0 )
    goto LABEL_17;
LABEL_18:
  PropVariantClear(pvar);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180049c00  mov     [rsp-8+arg_18], rbx
0x180049c05  push    rbp
0x180049c06  push    rsi
0x180049c07  push    r12
0x180049c09  push    r14
0x180049c0b  push    r15
0x180049c0d  lea     rbp, [rsp-37h]
0x180049c12  sub     rsp, 0B0h
0x180049c19  mov     rax, cs:__security_cookie
0x180049c20  xor     rax, rsp
0x180049c23  mov     [rbp+57h+var_30], rax
0x180049c27  xor     eax, eax
0x180049c29  mov     r15, rcx
0x180049c2c  mov     ecx, [rdx+10h]
0x180049c2f  xorps   xmm0, xmm0
0x180049c32  mov     [rbp+57h+var_A0], rax
0x180049c36  mov     r14, r8
0x180049c39  mov     rsi, rdx
0x180049c3c  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180049c40  test    cl, 8
0x180049c43  jnz     loc_180049D32
0x180049c49  test    cl, 2
0x180049c4c  jnz     short loc_180049CB5
0x180049c4e  xor     ebx, ebx
0x180049c50  cmp     [r15+78h], rax
0x180049c54  jz      short loc_180049CD2
0x180049c56  mov     eax, 0EA1Ch
0x180049c5b  cmp     [rdx], ax
0x180049c5e  jz      loc_180049E62
0x180049c64  cmp     [rdx+38h], rbx
0x180049c68  jnz     loc_180049D84
0x180049c6e  test    cl, cl
0x180049c70  js      short loc_180049C9B
0x180049c72  lea     r12, [rdx+14h]
0x180049c76  test    cl, 10h
0x180049c79  jz      loc_180049D43
0x180049c7f  mov     ecx, [rsi+10h]
0x180049c82  mov     eax, ecx
0x180049c84  mov     edx, [r12]
0x180049c88  and     eax, 0FFFFFFBFh
0x180049c8b  or      ecx, 40h
0x180049c8e  cmp     edx, 4
0x180049c91  cmova   ecx, eax
0x180049c94  bts     ecx, 7
0x180049c98  mov     [rsi+10h], ecx
0x180049c9b  bt      ecx, 6
0x180049c9f  mov     r8, r14; struct tagPROPVARIANT *
0x180049ca2  mov     rdx, rsi; struct IFD::FieldEntry *
0x180049ca5  mov     rcx, r15; this
0x180049ca8  jnb     loc_180049D7A
0x180049cae  call    ?GetTagVariantValueInline@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z; CMetadataIFDReaderWriter::GetTagVariantValueInline(IFD::FieldEntry *,tagPROPVARIANT *)
0x180049cb3  jmp     short loc_180049CC8
0x180049cb5  add     rdx, 20h ; ' '; pvarSrc
0x180049cb9  mov     rcx, r14; pvarDest
0x180049cbc  call    cs:__imp_PropVariantCopy
0x180049cc3  nop     dword ptr [rax+rax+00h]
0x180049cc8  mov     ebx, eax
0x180049cca  test    eax, eax
0x180049ccc  js      loc_180049D61
0x180049cd2  mov     rcx, rsi; this
0x180049cd5  call    ?IsCommentTag@FieldEntry@IFD@@QEAAHXZ; IFD::FieldEntry::IsCommentTag(void)
0x180049cda  test    eax, eax
0x180049cdc  jnz     loc_180049D91
0x180049ce2  test    ebx, ebx
0x180049ce4  jns     short loc_180049CFB
0x180049ce6  jmp     short loc_180049CEC
0x180049ce8  test    eax, eax
0x180049cea  jns     short loc_180049CD2
0x180049cec  mov     rcx, r14; pvar
0x180049cef  call    cs:__imp_PropVariantClear
0x180049cf6  nop     dword ptr [rax+rax+00h]
0x180049cfb  lea     rcx, [rbp+57h+pvar]; pvar
0x180049cff  call    cs:__imp_PropVariantClear
0x180049d06  nop     dword ptr [rax+rax+00h]
0x180049d0b  mov     eax, ebx
0x180049d0d  mov     rcx, [rbp+57h+var_30]
0x180049d11  xor     rcx, rsp; StackCookie
0x180049d14  call    __security_check_cookie
0x180049d19  mov     rbx, [rsp+0D0h+arg_18]
0x180049d21  add     rsp, 0B0h
0x180049d28  pop     r15
0x180049d2a  pop     r14
0x180049d2c  pop     r12
0x180049d2e  pop     rsi
0x180049d2f  pop     rbp
0x180049d30  retn
0x180049d32  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x180049d38  mov     ebx, 88982F40h
0x180049d3d  jz      short loc_180049CEC
0x180049d3f  mov     ecx, ebx
0x180049d41  jmp     short loc_180049D70
0x180049d43  mov     rdx, r12; unsigned int *
0x180049d46  mov     rcx, rsi; this
0x180049d49  call    ?ComputeTagDataSize@TagEntry@IFD@@IEAAJPEAK@Z; IFD::TagEntry::ComputeTagDataSize(ulong *)
0x180049d4e  mov     ebx, eax
0x180049d50  test    eax, eax
0x180049d52  js      loc_180049DE6
0x180049d58  or      dword ptr [rsi+10h], 10h
0x180049d5c  jmp     loc_180049C7F
0x180049d61  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180049d68  jz      loc_180049CE8
0x180049d6e  mov     ecx, eax; int
0x180049d70  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180049d75  jmp     loc_180049CEC
0x180049d7a  call    ?GetTagVariantValueAtOffset@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z; CMetadataIFDReaderWriter::GetTagVariantValueAtOffset(IFD::FieldEntry *,tagPROPVARIANT *)
0x180049d7f  jmp     loc_180049CC8
0x180049d84  mov     rcx, r15; this
0x180049d87  call    ?GetTagVariantValueForEmbeddedMetadata@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z; CMetadataIFDReaderWriter::GetTagVariantValueForEmbeddedMetadata(IFD::FieldEntry *,tagPROPVARIANT *)
0x180049d8c  jmp     loc_180049CC8
0x180049d91  mov     eax, 41h ; 'A'
0x180049d96  cmp     ax, [r14]
0x180049d9a  jnz     loc_180049CE2
0x180049da0  lea     rdx, [rbp+57h+pvar]; pvarDest
0x180049da4  mov     rcx, r14; pvarSrc
0x180049da7  call    ?ConvertCommentOnRead@@YAJPEAUtagPROPVARIANT@@0@Z; ConvertCommentOnRead(tagPROPVARIANT *,tagPROPVARIANT *)
0x180049dac  mov     ebx, eax
0x180049dae  test    eax, eax
0x180049db0  js      short loc_180049E2A
0x180049db2  mov     rcx, r14; pvar
0x180049db5  call    cs:__imp_PropVariantClear
0x180049dbc  nop     dword ptr [rax+rax+00h]
0x180049dc1  movups  xmm0, xmmword ptr [rbp+57h+pvar]
0x180049dc5  xor     eax, eax
0x180049dc7  movsd   xmm1, [rbp+57h+var_A0]
0x180049dcc  movups  xmmword ptr [r14], xmm0
0x180049dd0  mov     [rbp+57h+var_A0], rax
0x180049dd4  xorps   xmm0, xmm0
0x180049dd7  movsd   qword ptr [r14+10h], xmm1
0x180049ddd  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180049de1  jmp     loc_180049CFB
0x180049de6  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180049dec  test    eax, eax
0x180049dee  jz      loc_180049CE2
0x180049df4  mov     ecx, ebx; int
0x180049df6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180049dfb  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180049e01  test    eax, eax
0x180049e03  jz      loc_180049CE2
0x180049e09  mov     ecx, ebx; int
0x180049e0b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180049e10  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180049e16  test    eax, eax
0x180049e18  jz      loc_180049CE2
0x180049e1e  mov     ecx, ebx; int
0x180049e20  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180049e25  jmp     loc_180049CE2
0x180049e2a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180049e31  jnz     loc_180049D6E
0x180049e37  test    eax, eax
0x180049e39  js      loc_180049CEC
0x180049e3f  jmp     loc_180049DB2
0x180049e44  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180049e4b  jz      short loc_180049E90
0x180049e4d  mov     ecx, eax; int
0x180049e4f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180049e54  lea     rcx, [rbp+57h+var_78]
0x180049e58  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x180049e5d  jmp     loc_180049CEC
0x180049e62  lea     rcx, [rbp+57h+var_90]; this
0x180049e66  call    ??0CIFDPaddingManager@@QEAA@XZ; CIFDPaddingManager::CIFDPaddingManager(void)
0x180049e6b  mov     rax, [r15+78h]
0x180049e6f  mov     rdx, rsi; struct IFD::FieldEntry *
0x180049e72  lea     rcx, [rax+10h]
0x180049e76  neg     rax
0x180049e79  sbb     r8, r8
0x180049e7c  and     r8, rcx; struct IStream *
0x180049e7f  lea     rcx, [rbp+57h+var_90]; this
0x180049e83  call    ?InitializeFromField@CIFDPaddingManager@@QEAAJPEAVFieldEntry@IFD@@PEAUIStream@@@Z; CIFDPaddingManager::InitializeFromField(IFD::FieldEntry *,IStream *)
0x180049e88  mov     ebx, eax
0x180049e8a  test    eax, eax
0x180049e8c  jns     short loc_180049E94
0x180049e8e  jmp     short loc_180049E44
0x180049e90  test    eax, eax
0x180049e92  js      short loc_180049E54
0x180049e94  mov     eax, [rbp+57h+var_8C]
0x180049e97  lea     rcx, [rbp+57h+var_78]
0x180049e9b  mov     [r14+8], eax
0x180049e9f  mov     word ptr [r14], 13h
0x180049ea5  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x180049eaa  jmp     loc_180049CD2
```
