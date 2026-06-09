# CMetadataIFDReaderWriter::GetTagVariantValueInline(IFD::FieldEntry *,tagPROPVARIANT *)

- ea: `0x180049f00`
- end: `0x18004a186`
- name: `?GetTagVariantValueInline@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(CMetadataIFDReaderWriter *__hidden this, struct IFD::FieldEntry *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049c00`

## callees

- `0x180049f00`
- `0x18004a284`
- `0x18004a3d0`
- `0x1800bd9d4`
- `0x18017e438`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a011`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a0bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a011`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a0bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a105`

## pseudocode

```c
__int64 __fastcall CMetadataIFDReaderWriter::GetTagVariantValueInline(
        CMetadataIFDReaderWriter *this,
        struct IFD::FieldEntry *a2,
        struct tagPROPVARIANT *a3)
{
  unsigned int *v3; // r14
  unsigned int v7; // ebx
  unsigned int v8; // edx
  unsigned int v9; // r14d
  VARTYPE v10; // ax
  int ValueAsciiTag; // eax
  int v13; // ecx
  void *v14; // r15
  bool v15; // zf
  unsigned int v16; // r15d
  void *v17; // r14
  unsigned int v18; // r15d
  void *v19; // rax
  int Src; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int8 *p_Src; // [rsp+78h] [rbp+20h] BYREF

  v3 = (unsigned int *)((char *)a2 + 20);
  if ( (*((_BYTE *)a2 + 16) & 0x10) != 0 )
  {
    v7 = 0;
  }
  else
  {
    v7 = IFD::TagEntry::ComputeTagDataSize(a2, (unsigned int *)a2 + 5);
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        return v7;
      DoStackCapture(v7);
      v15 = (_DWORD)g_doStackCaptures == 0;
      goto LABEL_29;
    }
    *((_DWORD *)a2 + 4) |= 0x10u;
  }
  v8 = *((unsigned __int16 *)a2 + 1);
  v9 = *v3;
  if ( v8 > 7 )
  {
    switch ( v8 )
    {
      case 8u:
        goto LABEL_5;
      case 9u:
        a3->vt = 3;
        goto LABEL_18;
      case 0xBu:
        a3->vt = 4;
        goto LABEL_18;
    }
    goto LABEL_45;
  }
  if ( v8 == 7 )
  {
    if ( v9 )
    {
      v14 = CoTaskMemAlloc(v9);
      if ( !v14 )
      {
LABEL_40:
        v7 = -2147024882;
LABEL_41:
        v15 = (_DWORD)g_doStackCaptures == 0;
LABEL_29:
        if ( v15 )
          return v7;
        v13 = v7;
LABEL_31:
        DoStackCapture(v13);
        return v7;
      }
      Src = *((_DWORD *)a2 + 2);
      memcpy_0(v14, &Src, v9);
    }
    else
    {
      v14 = 0;
    }
    a3->vt = 65;
    a3->lVal = v9;
    a3->bstrblobVal.pData = (BYTE *)v14;
    return v7;
  }
  if ( v8 == 1 )
  {
LABEL_33:
    a3->vt = 17 - (v8 != 1);
    if ( *((_DWORD *)a2 + 1) <= 1u )
    {
      a3->cVal = *((_BYTE *)a2 + 8);
      return v7;
    }
    v16 = v9;
    v17 = CoTaskMemAlloc(v9);
    if ( v17 )
    {
      Src = *((_DWORD *)a2 + 2);
      memcpy_0(v17, &Src, v16);
      a3->vt |= 0x1000u;
      a3->lVal = *((_DWORD *)a2 + 1);
LABEL_37:
      a3->bstrblobVal.pData = (BYTE *)v17;
      return v7;
    }
    goto LABEL_40;
  }
  if ( v8 != 2 )
  {
    if ( v8 == 3 )
    {
LABEL_5:
      v10 = 18;
      if ( v8 != 3 )
        v10 = 2;
      a3->vt = v10;
      if ( *((_DWORD *)a2 + 1) <= 1u )
      {
        a3->iVal = *((_WORD *)a2 + 4);
        return v7;
      }
      v18 = v9;
      v19 = CoTaskMemAlloc(v9);
      v17 = v19;
      if ( v19 )
      {
        Src = *((_DWORD *)a2 + 2);
        memcpy_0(v19, &Src, v18);
        a3->vt |= 0x1000u;
        a3->lVal = *((_DWORD *)a2 + 1);
        goto LABEL_37;
      }
      goto LABEL_40;
    }
    if ( v8 == 4 )
    {
      a3->vt = 19;
LABEL_18:
      a3->lVal = *((_DWORD *)a2 + 2);
      return v7;
    }
    if ( v8 != 6 )
    {
LABEL_45:
      if ( !v9 )
        return v7;
      v7 = -2147418113;
      goto LABEL_41;
    }
    goto LABEL_33;
  }
  Src = *((_DWORD *)a2 + 2);
  p_Src = (unsigned __int8 *)&Src;
  ValueAsciiTag = CMetadataIFDReaderWriter::GetValueAsciiTag(this, v9, &p_Src, 0, a3);
  v7 = ValueAsciiTag;
  if ( ValueAsciiTag < 0 && (_DWORD)g_doStackCaptures )
  {
    v13 = ValueAsciiTag;
    goto LABEL_31;
  }
  return v7;
}

```

## disassembly

```asm
0x180049f00  mov     [rsp+arg_0], rbx
0x180049f05  push    rbp
0x180049f06  push    rsi
0x180049f07  push    r12
0x180049f09  push    r14
0x180049f0b  push    r15
0x180049f0d  sub     rsp, 30h
0x180049f11  test    byte ptr [rdx+10h], 10h
0x180049f15  lea     r14, [rdx+14h]
0x180049f19  mov     rsi, r8
0x180049f1c  mov     rbp, rdx
0x180049f1f  mov     r15, rcx
0x180049f22  jz      short loc_180049F7A
0x180049f24  xor     ebx, ebx
0x180049f26  movzx   edx, word ptr [rbp+2]
0x180049f2a  mov     r14d, [r14]
0x180049f2d  cmp     edx, 7
0x180049f30  jbe     short loc_180049F95
0x180049f32  mov     ecx, edx
0x180049f34  sub     ecx, 8
0x180049f37  jnz     loc_18004A158
0x180049f3d  mov     eax, 12h
0x180049f42  lea     ecx, [rax-0Fh]
0x180049f45  cmp     edx, ecx
0x180049f47  lea     r8d, [rax-10h]
0x180049f4b  cmovnz  ax, r8w
0x180049f50  mov     [rsi], ax
0x180049f53  cmp     dword ptr [rbp+4], 1
0x180049f57  ja      loc_18004A0FF
0x180049f5d  movzx   eax, word ptr [rbp+8]
0x180049f61  mov     [rsi+8], ax
0x180049f65  mov     eax, ebx
0x180049f67  mov     rbx, [rsp+58h+arg_0]
0x180049f6c  add     rsp, 30h
0x180049f70  pop     r15
0x180049f72  pop     r14
0x180049f74  pop     r12
0x180049f76  pop     rsi
0x180049f77  pop     rbp
0x180049f78  retn
0x180049f7a  mov     rdx, r14; unsigned int *
0x180049f7d  mov     rcx, rbp; this
0x180049f80  call    ?ComputeTagDataSize@TagEntry@IFD@@IEAAJPEAK@Z; IFD::TagEntry::ComputeTagDataSize(ulong *)
0x180049f85  mov     ebx, eax
0x180049f87  test    eax, eax
0x180049f89  js      loc_18004A057
0x180049f8f  or      dword ptr [rbp+10h], 10h
0x180049f93  jmp     short loc_180049F26
0x180049f95  jz      short loc_18004A006
0x180049f97  mov     ecx, edx
0x180049f99  sub     ecx, 1
0x180049f9c  jz      loc_18004A098
0x180049fa2  sub     ecx, 1
0x180049fa5  jz      short loc_180049FC2
0x180049fa7  sub     ecx, 1
0x180049faa  jz      short loc_180049F3D
0x180049fac  sub     ecx, 1
0x180049faf  jnz     loc_18004A086
0x180049fb5  mov     word ptr [rsi], 13h
0x180049fba  mov     eax, [rbp+8]
0x180049fbd  mov     [rsi+8], eax
0x180049fc0  jmp     short loc_180049F65
0x180049fc2  mov     eax, [rbp+8]
0x180049fc5  lea     r8, [rsp+58h+arg_18]; unsigned __int8 **
0x180049fca  mov     [rsp+58h+Src], eax
0x180049fce  xor     r9d, r9d; int
0x180049fd1  lea     rax, [rsp+58h+Src]
0x180049fd6  mov     [rsp+58h+var_38], rsi; struct tagPROPVARIANT *
0x180049fdb  mov     edx, r14d; unsigned int
0x180049fde  mov     [rsp+58h+arg_18], rax
0x180049fe3  mov     rcx, r15; this
0x180049fe6  call    ?GetValueAsciiTag@CMetadataIFDReaderWriter@@IEAAJKPEAPEAEHPEAUtagPROPVARIANT@@@Z; CMetadataIFDReaderWriter::GetValueAsciiTag(ulong,uchar * *,int,tagPROPVARIANT *)
0x180049feb  mov     ebx, eax
0x180049fed  test    eax, eax
0x180049fef  jns     loc_180049F65
0x180049ff5  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180049ffc  jz      loc_180049F65
0x18004a002  mov     ecx, eax
0x18004a004  jmp     short loc_18004A07C
0x18004a006  test    r14d, r14d
0x18004a009  jz      short loc_18004A052
0x18004a00b  mov     ecx, r14d; cb
0x18004a00e  mov     r12d, r14d
0x18004a011  call    cs:__imp_CoTaskMemAlloc
0x18004a018  nop     dword ptr [rax+rax+00h]
0x18004a01d  mov     r15, rax
0x18004a020  test    rax, rax
0x18004a023  jz      loc_18004A140
0x18004a029  mov     eax, [rbp+8]
0x18004a02c  lea     rdx, [rsp+58h+Src]; Src
0x18004a031  mov     r8d, r12d; Size
0x18004a034  mov     [rsp+58h+Src], eax
0x18004a038  mov     rcx, r15; void *
0x18004a03b  call    memcpy_0
0x18004a040  mov     word ptr [rsi], 41h ; 'A'
0x18004a045  mov     [rsi+8], r14d
0x18004a049  mov     [rsi+10h], r15
0x18004a04d  jmp     loc_180049F65
0x18004a052  xor     r15d, r15d
0x18004a055  jmp     short loc_18004A040
0x18004a057  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18004a05d  test    eax, eax
0x18004a05f  jz      loc_180049F65
0x18004a065  mov     ecx, ebx; int
0x18004a067  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004a06c  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18004a072  test    eax, eax
0x18004a074  jz      loc_180049F65
0x18004a07a  mov     ecx, ebx; int
0x18004a07c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004a081  jmp     loc_180049F65
0x18004a086  sub     ecx, 1
0x18004a089  jz      loc_18004A171
0x18004a08f  cmp     ecx, 1
0x18004a092  jnz     loc_18004A171
0x18004a098  dec     edx
0x18004a09a  neg     edx
0x18004a09c  sbb     ax, ax
0x18004a09f  add     ax, 11h
0x18004a0a3  mov     [rsi], ax
0x18004a0a6  cmp     dword ptr [rbp+4], 1
0x18004a0aa  ja      short loc_18004A0B7
0x18004a0ac  mov     al, [rbp+8]
0x18004a0af  mov     [rsi+8], al
0x18004a0b2  jmp     loc_180049F65
0x18004a0b7  mov     ecx, r14d; cb
0x18004a0ba  mov     r15d, r14d
0x18004a0bd  call    cs:__imp_CoTaskMemAlloc
0x18004a0c4  nop     dword ptr [rax+rax+00h]
0x18004a0c9  mov     r14, rax
0x18004a0cc  test    rax, rax
0x18004a0cf  jz      short loc_18004A140
0x18004a0d1  mov     eax, [rbp+8]
0x18004a0d4  lea     rdx, [rsp+58h+Src]; Src
0x18004a0d9  mov     r8d, r15d; Size
0x18004a0dc  mov     [rsp+58h+Src], eax
0x18004a0e0  mov     rcx, r14; void *
0x18004a0e3  call    memcpy_0
0x18004a0e8  mov     eax, 1000h
0x18004a0ed  or      [rsi], ax
0x18004a0f0  mov     eax, [rbp+4]
0x18004a0f3  mov     [rsi+8], eax
0x18004a0f6  mov     [rsi+10h], r14
0x18004a0fa  jmp     loc_180049F65
0x18004a0ff  mov     ecx, r14d; cb
0x18004a102  mov     r15d, r14d
0x18004a105  call    cs:__imp_CoTaskMemAlloc
0x18004a10c  nop     dword ptr [rax+rax+00h]
0x18004a111  mov     r14, rax
0x18004a114  test    rax, rax
0x18004a117  jz      short loc_18004A140
0x18004a119  mov     ecx, [rbp+8]
0x18004a11c  lea     rdx, [rsp+58h+Src]; Src
0x18004a121  mov     [rsp+58h+Src], ecx
0x18004a125  mov     r8d, r15d; Size
0x18004a128  mov     rcx, rax; void *
0x18004a12b  call    memcpy_0
0x18004a130  mov     eax, 1000h
0x18004a135  or      [rsi], ax
0x18004a138  mov     ecx, [rbp+4]
0x18004a13b  mov     [rsi+8], ecx
0x18004a13e  jmp     short loc_18004A0F6
0x18004a140  mov     ebx, 8007000Eh
0x18004a145  jmp     short loc_18004A14C
0x18004a147  mov     ebx, 8000FFFFh
0x18004a14c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18004a153  jmp     loc_18004A074
0x18004a158  sub     ecx, 1
0x18004a15b  jz      short loc_18004A17C
0x18004a15d  sub     ecx, 1
0x18004a160  jz      short loc_18004A171
0x18004a162  sub     ecx, 1
0x18004a165  jnz     short loc_18004A171
0x18004a167  mov     word ptr [rsi], 4
0x18004a16c  jmp     loc_180049FBA
0x18004a171  test    r14d, r14d
0x18004a174  jz      loc_180049F65
0x18004a17a  jmp     short loc_18004A147
0x18004a17c  mov     word ptr [rsi], 3
0x18004a181  jmp     loc_180049FBA
```
