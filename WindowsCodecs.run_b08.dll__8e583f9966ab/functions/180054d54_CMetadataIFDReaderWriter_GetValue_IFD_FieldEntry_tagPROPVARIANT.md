# CMetadataIFDReaderWriter::GetValue(IFD::FieldEntry *,tagPROPVARIANT *)

- ea: `0x180054d54`
- end: `0x180054fe3`
- name: `?GetValue@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(CMetadataIFDReaderWriter *__hidden this, struct IFD::FieldEntry *, PROPVARIANT *pvarSrc)`
- caller_count: `4`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031900`
- `0x1800374f0`
- `0x180054930`
- `0x1800598f0`

## callees

- `0x180035678`
- `0x18003832c`
- `0x180054104`
- `0x180054d54`
- `0x180054fec`
- `0x180055030`
- `0x1800553a4`
- `0x1800555a0`
- `0x180057fb0`
- `0x1800bb784`
- `0x1800e2f90`
- `0x1801b52fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180054e10`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180054e10`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054e3d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054e47`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054eef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054e3d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054e47`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054eef`

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
                                                 pvarSrc);
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
0x180054d54  mov     [rsp-8+arg_18], rbx
0x180054d59  push    rbp
0x180054d5a  push    rsi
0x180054d5b  push    r12
0x180054d5d  push    r14
0x180054d5f  push    r15
0x180054d61  lea     rbp, [rsp-37h]
0x180054d66  sub     rsp, 0B0h
0x180054d6d  mov     rax, cs:__security_cookie
0x180054d74  xor     rax, rsp
0x180054d77  mov     [rbp+57h+var_30], rax
0x180054d7b  xor     eax, eax
0x180054d7d  mov     r15, rcx
0x180054d80  mov     ecx, [rdx+10h]
0x180054d83  xorps   xmm0, xmm0
0x180054d86  mov     [rbp+57h+var_A0], rax
0x180054d8a  mov     r14, r8
0x180054d8d  mov     rsi, rdx
0x180054d90  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180054d94  test    cl, 8
0x180054d97  jnz     loc_180054E73
0x180054d9d  test    cl, 2
0x180054da0  jnz     short loc_180054E09
0x180054da2  xor     ebx, ebx
0x180054da4  cmp     [r15+78h], rax
0x180054da8  jz      short loc_180054E20
0x180054daa  mov     eax, 0EA1Ch
0x180054daf  cmp     [rdx], ax
0x180054db2  jz      loc_180054F96
0x180054db8  cmp     [rdx+38h], rbx
0x180054dbc  jnz     loc_180054EBE
0x180054dc2  test    cl, cl
0x180054dc4  js      short loc_180054DEF
0x180054dc6  lea     r12, [rdx+14h]
0x180054dca  test    cl, 10h
0x180054dcd  jz      loc_180054E84
0x180054dd3  mov     ecx, [rsi+10h]
0x180054dd6  mov     eax, ecx
0x180054dd8  mov     edx, [r12]
0x180054ddc  and     eax, 0FFFFFFBFh
0x180054ddf  or      ecx, 40h
0x180054de2  cmp     edx, 4
0x180054de5  cmova   ecx, eax
0x180054de8  bts     ecx, 7
0x180054dec  mov     [rsi+10h], ecx
0x180054def  bt      ecx, 6
0x180054df3  mov     r8, r14; struct tagPROPVARIANT *
0x180054df6  mov     rdx, rsi; struct IFD::FieldEntry *
0x180054df9  mov     rcx, r15; this
0x180054dfc  jnb     loc_180054EB4
0x180054e02  call    ?GetTagVariantValueInline@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z; CMetadataIFDReaderWriter::GetTagVariantValueInline(IFD::FieldEntry *,tagPROPVARIANT *)
0x180054e07  jmp     short loc_180054E16
0x180054e09  add     rdx, 20h ; ' '; pvarSrc
0x180054e0d  mov     rcx, r14; pvarDest
0x180054e10  call    cs:__imp_PropVariantCopy
0x180054e16  mov     ebx, eax
0x180054e18  test    eax, eax
0x180054e1a  js      loc_180054EA2
0x180054e20  mov     rcx, rsi; this
0x180054e23  call    ?IsCommentTag@FieldEntry@IFD@@QEAAHXZ; IFD::FieldEntry::IsCommentTag(void)
0x180054e28  test    eax, eax
0x180054e2a  jnz     loc_180054ECB
0x180054e30  test    ebx, ebx
0x180054e32  jns     short loc_180054E43
0x180054e34  jmp     short loc_180054E3A
0x180054e36  test    eax, eax
0x180054e38  jns     short loc_180054E20
0x180054e3a  mov     rcx, r14; pvar
0x180054e3d  call    cs:__imp_PropVariantClear
0x180054e43  lea     rcx, [rbp+57h+pvar]; pvar
0x180054e47  call    cs:__imp_PropVariantClear
0x180054e4d  mov     eax, ebx
0x180054e4f  mov     rcx, [rbp+57h+var_30]
0x180054e53  xor     rcx, rsp; StackCookie
0x180054e56  call    __security_check_cookie
0x180054e5b  mov     rbx, [rsp+0D0h+arg_18]
0x180054e63  add     rsp, 0B0h
0x180054e6a  pop     r15
0x180054e6c  pop     r14
0x180054e6e  pop     r12
0x180054e70  pop     rsi
0x180054e71  pop     rbp
0x180054e72  retn
0x180054e73  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x180054e79  mov     ebx, 88982F40h
0x180054e7e  jz      short loc_180054E3A
0x180054e80  mov     ecx, ebx
0x180054e82  jmp     short loc_180054EAD
0x180054e84  mov     rdx, r12; unsigned int *
0x180054e87  mov     rcx, rsi; this
0x180054e8a  call    ?ComputeTagDataSize@TagEntry@IFD@@IEAAJPEAK@Z; IFD::TagEntry::ComputeTagDataSize(ulong *)
0x180054e8f  mov     ebx, eax
0x180054e91  test    eax, eax
0x180054e93  js      loc_180054F1A
0x180054e99  or      dword ptr [rsi+10h], 10h
0x180054e9d  jmp     loc_180054DD3
0x180054ea2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180054ea9  jz      short loc_180054E36
0x180054eab  mov     ecx, eax; int
0x180054ead  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180054eb2  jmp     short loc_180054E3A
0x180054eb4  call    ?GetTagVariantValueAtOffset@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z; CMetadataIFDReaderWriter::GetTagVariantValueAtOffset(IFD::FieldEntry *,tagPROPVARIANT *)
0x180054eb9  jmp     loc_180054E16
0x180054ebe  mov     rcx, r15; this
0x180054ec1  call    ?GetTagVariantValueForEmbeddedMetadata@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z; CMetadataIFDReaderWriter::GetTagVariantValueForEmbeddedMetadata(IFD::FieldEntry *,tagPROPVARIANT *)
0x180054ec6  jmp     loc_180054E16
0x180054ecb  mov     eax, 41h ; 'A'
0x180054ed0  cmp     ax, [r14]
0x180054ed4  jnz     loc_180054E30
0x180054eda  lea     rdx, [rbp+57h+pvar]; pvarDest
0x180054ede  mov     rcx, r14; pvarSrc
0x180054ee1  call    ?ConvertCommentOnRead@@YAJPEAUtagPROPVARIANT@@0@Z; ConvertCommentOnRead(tagPROPVARIANT *,tagPROPVARIANT *)
0x180054ee6  mov     ebx, eax
0x180054ee8  test    eax, eax
0x180054eea  js      short loc_180054F5E
0x180054eec  mov     rcx, r14; pvar
0x180054eef  call    cs:__imp_PropVariantClear
0x180054ef5  movups  xmm0, xmmword ptr [rbp+57h+pvar]
0x180054ef9  xor     eax, eax
0x180054efb  movsd   xmm1, [rbp+57h+var_A0]
0x180054f00  movups  xmmword ptr [r14], xmm0
0x180054f04  mov     [rbp+57h+var_A0], rax
0x180054f08  xorps   xmm0, xmm0
0x180054f0b  movsd   qword ptr [r14+10h], xmm1
0x180054f11  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180054f15  jmp     loc_180054E43
0x180054f1a  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180054f20  test    eax, eax
0x180054f22  jz      loc_180054E30
0x180054f28  mov     ecx, ebx; int
0x180054f2a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180054f2f  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180054f35  test    eax, eax
0x180054f37  jz      loc_180054E30
0x180054f3d  mov     ecx, ebx; int
0x180054f3f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180054f44  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180054f4a  test    eax, eax
0x180054f4c  jz      loc_180054E30
0x180054f52  mov     ecx, ebx; int
0x180054f54  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180054f59  jmp     loc_180054E30
0x180054f5e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180054f65  jnz     loc_180054EAB
0x180054f6b  test    eax, eax
0x180054f6d  js      loc_180054E3A
0x180054f73  jmp     loc_180054EEC
0x180054f78  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180054f7f  jz      short loc_180054FC4
0x180054f81  mov     ecx, eax; int
0x180054f83  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180054f88  lea     rcx, [rbp+57h+var_78]
0x180054f8c  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x180054f91  jmp     loc_180054E3A
0x180054f96  lea     rcx, [rbp+57h+var_90]; this
0x180054f9a  call    ??0CIFDPaddingManager@@QEAA@XZ; CIFDPaddingManager::CIFDPaddingManager(void)
0x180054f9f  mov     rax, [r15+78h]
0x180054fa3  mov     rdx, rsi; struct IFD::FieldEntry *
0x180054fa6  lea     rcx, [rax+10h]
0x180054faa  neg     rax
0x180054fad  sbb     r8, r8
0x180054fb0  and     r8, rcx; struct IStream *
0x180054fb3  lea     rcx, [rbp+57h+var_90]; this
0x180054fb7  call    ?InitializeFromField@CIFDPaddingManager@@QEAAJPEAVFieldEntry@IFD@@PEAUIStream@@@Z; CIFDPaddingManager::InitializeFromField(IFD::FieldEntry *,IStream *)
0x180054fbc  mov     ebx, eax
0x180054fbe  test    eax, eax
0x180054fc0  jns     short loc_180054FC8
0x180054fc2  jmp     short loc_180054F78
0x180054fc4  test    eax, eax
0x180054fc6  js      short loc_180054F88
0x180054fc8  mov     eax, [rbp+57h+var_8C]
0x180054fcb  lea     rcx, [rbp+57h+var_78]
0x180054fcf  mov     [r14+8], eax
0x180054fd3  mov     word ptr [r14], 13h
0x180054fd9  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x180054fde  jmp     loc_180054E20
```
