# CMetadataRDFReaderWriter::HrGetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x180001b50`
- end: `0x180001ddd`
- name: `?HrGetValue@CMetadataRDFReaderWriter@@MEAAJPEBUtagPROPVARIANT@@0PEAU2@@Z`
- size: `653`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001540`
- `0x180002710`

## callees

- `0x180001b50`
- `0x180001df0`
- `0x180002484`
- `0x18000285c`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180001d1f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180001d1f`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::HrGetValue(
        CMetadataRDFReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        PROPVARIANT *a4)
{
  int v4; // r12d
  PROPVARIANT *v6; // rsi
  unsigned int v9; // esi
  unsigned int v10; // edi
  __int64 i; // rbx
  struct RDFItem *v12; // rcx
  int v13; // eax
  RDFItem *v15; // rbx
  int v16; // eax
  int PropVariantValue; // eax
  int ItemPositionByGuidAndIndex; // eax
  unsigned int v19; // ebx
  int v20[18]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v21; // [rsp+90h] [rbp+18h] BYREF
  PROPVARIANT *pvar; // [rsp+98h] [rbp+20h]

  pvar = a4;
  v4 = 0;
  v21 = 0;
  v20[0] = 0;
  v6 = a4;
  if ( a3->vt == 72 )
  {
    ItemPositionByGuidAndIndex = CMetadataRDFReaderWriter::FindItemPositionByGuidAndIndex(this, a2, a3, v20, &v21);
    v19 = ItemPositionByGuidAndIndex;
    if ( ItemPositionByGuidAndIndex < 0 )
    {
      if ( g_doStackCaptures )
        DoStackCapture(ItemPositionByGuidAndIndex);
      return v19;
    }
    LODWORD(i) = v21;
    v4 = v20[0];
LABEL_17:
    if ( v4 )
    {
      v10 = -2003292352;
      if ( g_doStackCaptures )
      {
        DoStackCapture(-2003292352);
        return 2291674944LL;
      }
      return v10;
    }
    v10 = 0;
    if ( !v6 )
      return v10;
    v15 = *(RDFItem **)(*((_QWORD *)this + 26) + 8LL * (unsigned int)i);
    v16 = *((_DWORD *)v15 + 2);
    if ( (v16 & 4) == 0
      || (v16 & 8) != 0
      || (PropVariantValue = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, RDFItem *))(*(_QWORD *)this + 224LL))(
                               this,
                               v15),
          v10 = PropVariantValue,
          PropVariantValue >= 0) )
    {
      PropVariantValue = RDFItem::GetPropVariantValue(v15, (struct tagPROPVARIANT *)v6);
      v10 = PropVariantValue;
      if ( PropVariantValue >= 0 )
        return v10;
      if ( !g_doStackCaptures )
      {
LABEL_33:
        PropVariantClear(v6);
        if ( g_doStackCaptures )
          DoStackCapture(v10);
        return v10;
      }
    }
    else if ( !g_doStackCaptures )
    {
      goto LABEL_33;
    }
    DoStackCapture(PropVariantValue);
    goto LABEL_33;
  }
  if ( a3->vt != 31 )
  {
    if ( g_doStackCaptures )
      DoStackCapture(-2147024809);
    return 2147942487LL;
  }
  if ( (*(unsigned int (__fastcall **)(CMetadataRDFReaderWriter *))(*(_QWORD *)this + 272LL))(this) )
  {
    v10 = -2003292352;
    if ( g_doStackCaptures )
    {
      DoStackCapture(-2003292352);
      return 2291674944LL;
    }
    return v10;
  }
  v9 = *((_DWORD *)this + 58);
  v10 = 0;
  for ( i = 0; (unsigned int)i < v9; i = (unsigned int)(i + 1) )
  {
    v12 = *(struct RDFItem **)(*((_QWORD *)this + 26) + 8 * i);
    if ( (*((_BYTE *)v12 + 8) & 2) == 0 )
    {
      v21 = 1;
      v13 = CMetadataRDFReaderWriter::CompareItemSchemaAndValue(v12, a2, a3, (int *)&v21);
      v10 = v13;
      if ( v13 < 0 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(v13);
        goto LABEL_14;
      }
      if ( v21 )
        goto LABEL_16;
    }
  }
  v4 = 1;
  if ( (v10 & 0x80000000) == 0 )
  {
LABEL_16:
    v6 = pvar;
    goto LABEL_17;
  }
LABEL_14:
  if ( !g_doStackCaptures )
    return v10;
  DoStackCapture(v10);
  return v10;
}

```

## disassembly

```asm
0x180001b50  mov     rax, rsp
0x180001b53  mov     [rax+8], rbx
0x180001b57  mov     [rax+20h], r9
0x180001b5b  push    rbp
0x180001b5c  push    rsi
0x180001b5d  push    rdi
0x180001b5e  push    r12
0x180001b60  push    r13
0x180001b62  push    r14
0x180001b64  push    r15
0x180001b66  sub     rsp, 40h
0x180001b6a  xor     r12d, r12d
0x180001b6d  mov     dword ptr [rax+18h], 0
0x180001b74  mov     [rax-48h], r12d
0x180001b78  mov     r14, rcx
0x180001b7b  movzx   eax, word ptr [r8]
0x180001b7f  mov     ecx, 48h ; 'H'
0x180001b84  mov     rsi, r9
0x180001b87  mov     r15, r8
0x180001b8a  mov     rbp, rdx
0x180001b8d  cmp     cx, ax
0x180001b90  jz      loc_180001D5C
0x180001b96  mov     ecx, 1Fh
0x180001b9b  cmp     cx, ax
0x180001b9e  jnz     loc_180001CE1
0x180001ba4  mov     rax, [r14]
0x180001ba7  mov     rcx, r14
0x180001baa  mov     rax, [rax+110h]
0x180001bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bb6  test    eax, eax
0x180001bb8  jnz     loc_180001DBD
0x180001bbe  mov     esi, [r14+0E8h]
0x180001bc5  xor     edi, edi
0x180001bc7  xor     r13d, r13d
0x180001bca  xor     ebx, ebx
0x180001bcc  nop     dword ptr [rax+00h]
0x180001bd0  cmp     ebx, esi
0x180001bd2  jnb     short loc_180001C2D
0x180001bd4  mov     rcx, [r14+0D0h]
0x180001bdb  mov     rcx, [rcx+rbx*8]; struct RDFItem *
0x180001bdf  test    byte ptr [rcx+8], 2
0x180001be3  jnz     short loc_180001C20
0x180001be5  lea     r9, [rsp+78h+arg_10]; int *
0x180001bed  mov     [rsp+78h+arg_10], 1
0x180001bf8  mov     r8, r15; struct tagPROPVARIANT *
0x180001bfb  mov     rdx, rbp; struct tagPROPVARIANT *
0x180001bfe  call    ?CompareItemSchemaAndValue@CMetadataRDFReaderWriter@@KAJPEAVRDFItem@@PEBUtagPROPVARIANT@@1PEAH@Z; CMetadataRDFReaderWriter::CompareItemSchemaAndValue(RDFItem *,tagPROPVARIANT const *,tagPROPVARIANT const *,int *)
0x180001c03  mov     edi, eax
0x180001c05  test    eax, eax
0x180001c07  jns     short loc_180001C16
0x180001c09  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180001c10  jnz     short loc_180001C24
0x180001c12  test    eax, eax
0x180001c14  js      short loc_180001C40
0x180001c16  cmp     [rsp+78h+arg_10], r12d
0x180001c1e  jnz     short loc_180001C63
0x180001c20  inc     ebx
0x180001c22  jmp     short loc_180001BD0
0x180001c24  mov     ecx, eax; int
0x180001c26  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001c2b  jmp     short loc_180001C40
0x180001c2d  test    r13d, r13d
0x180001c30  jnz     loc_180001DA4
0x180001c36  mov     r12d, 1
0x180001c3c  test    edi, edi
0x180001c3e  jns     short loc_180001C68
0x180001c40  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001c47  jnz     short loc_180001C8E
0x180001c49  mov     eax, edi
0x180001c4b  mov     rbx, [rsp+78h+arg_0]
0x180001c53  add     rsp, 40h
0x180001c57  pop     r15
0x180001c59  pop     r14
0x180001c5b  pop     r13
0x180001c5d  pop     r12
0x180001c5f  pop     rdi
0x180001c60  pop     rsi
0x180001c61  pop     rbp
0x180001c62  retn
0x180001c63  test    r13d, r13d
0x180001c66  jnz     short loc_180001C99
0x180001c68  mov     rsi, [rsp+78h+pvar]
0x180001c70  test    r12d, r12d
0x180001c73  jz      short loc_180001C9E
0x180001c75  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001c7c  mov     edi, 88982F40h
0x180001c81  jz      short loc_180001C49
0x180001c83  mov     ecx, edi; int
0x180001c85  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001c8a  mov     eax, edi
0x180001c8c  jmp     short loc_180001C4B
0x180001c8e  mov     ecx, edi; int
0x180001c90  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001c95  mov     eax, edi
0x180001c97  jmp     short loc_180001C4B
0x180001c99  inc     r13d
0x180001c9c  jmp     short loc_180001C20
0x180001c9e  xor     edi, edi
0x180001ca0  test    rsi, rsi
0x180001ca3  jz      short loc_180001C49
0x180001ca5  mov     rax, [r14+0D0h]
0x180001cac  mov     ecx, ebx
0x180001cae  mov     rbx, [rax+rcx*8]
0x180001cb2  mov     eax, [rbx+8]
0x180001cb5  test    al, 4
0x180001cb7  jnz     short loc_180001CF4
0x180001cb9  mov     rdx, rsi; struct tagPROPVARIANT *
0x180001cbc  mov     rcx, rbx; this
0x180001cbf  call    ?GetPropVariantValue@RDFItem@@QEAAJPEAUtagPROPVARIANT@@@Z; RDFItem::GetPropVariantValue(tagPROPVARIANT *)
0x180001cc4  mov     edi, eax
0x180001cc6  test    eax, eax
0x180001cc8  jns     loc_180001C49
0x180001cce  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001cd5  jnz     short loc_180001D3E
0x180001cd7  test    eax, eax
0x180001cd9  jns     loc_180001C49
0x180001cdf  jmp     short loc_180001D1C
0x180001ce1  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180001ce8  jnz     short loc_180001D47
0x180001cea  mov     eax, 80070057h
0x180001cef  jmp     loc_180001C4B
0x180001cf4  test    al, 8
0x180001cf6  jnz     short loc_180001CB9
0x180001cf8  mov     rax, [r14]
0x180001cfb  mov     rdx, rbx
0x180001cfe  mov     rcx, r14
0x180001d01  mov     rax, [rax+0E0h]
0x180001d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d0d  mov     edi, eax
0x180001d0f  test    eax, eax
0x180001d11  jns     short loc_180001CB9
0x180001d13  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001d1a  jnz     short loc_180001D53
0x180001d1c  mov     rcx, rsi; pvar
0x180001d1f  call    cs:__imp_PropVariantClear
0x180001d25  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001d2c  jz      loc_180001C49
0x180001d32  mov     ecx, edi; int
0x180001d34  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001d39  jmp     loc_180001C49
0x180001d3e  mov     ecx, eax; int
0x180001d40  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001d45  jmp     short loc_180001D1C
0x180001d47  mov     ecx, 80070057h; int
0x180001d4c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001d51  jmp     short loc_180001CEA
0x180001d53  mov     ecx, eax; int
0x180001d55  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001d5a  jmp     short loc_180001D1C
0x180001d5c  lea     rax, [rsp+78h+arg_10]
0x180001d64  mov     rcx, r14; this
0x180001d67  lea     r9, [rsp+78h+var_48]; int *
0x180001d6c  mov     [rsp+78h+var_58], rax; unsigned int *
0x180001d71  call    ?FindItemPositionByGuidAndIndex@CMetadataRDFReaderWriter@@IEAAJPEBUtagPROPVARIANT@@0PEAHPEAI@Z; CMetadataRDFReaderWriter::FindItemPositionByGuidAndIndex(tagPROPVARIANT const *,tagPROPVARIANT const *,int *,uint *)
0x180001d76  mov     ebx, eax
0x180001d78  test    eax, eax
0x180001d7a  jns     short loc_180001D93
0x180001d7c  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180001d83  jz      short loc_180001D8C
0x180001d85  mov     ecx, eax; int
0x180001d87  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001d8c  mov     eax, ebx
0x180001d8e  jmp     loc_180001C4B
0x180001d93  mov     ebx, [rsp+78h+arg_10]
0x180001d9a  mov     r12d, [rsp+78h+var_48]
0x180001d9f  jmp     loc_180001C70
0x180001da4  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180001dab  mov     edi, 88982F40h
0x180001db0  jz      loc_180001C40
0x180001db6  mov     ecx, edi
0x180001db8  jmp     loc_180001C26
0x180001dbd  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180001dc4  mov     edi, 88982F40h
0x180001dc9  jz      loc_180001C49
0x180001dcf  mov     ecx, edi; int
0x180001dd1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001dd6  mov     eax, edi
0x180001dd8  jmp     loc_180001C4B
```
