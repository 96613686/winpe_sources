# CMetadataIPTCReaderWriter::CreateVariantFromStreamAndDesc(IStream *,uint,CMetadataIPTCReaderWriter::DataSetDesc const *,tagPROPVARIANT *)

- ea: `0x18004f678`
- end: `0x18004f88e`
- name: `?CreateVariantFromStreamAndDesc@CMetadataIPTCReaderWriter@@AEAAJPEAUIStream@@IPEBUDataSetDesc@1@PEAUtagPROPVARIANT@@@Z`
- size: `534`
- prototype: `int(CMetadataIPTCReaderWriter *__hidden this, struct IStream *, unsigned int, const struct CMetadataIPTCReaderWriter::DataSetDesc *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004f390`

## callees

- `0x18004f678`
- `0x1800542e8`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f73e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f73e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f76d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f76d`

## pseudocode

```c
__int64 __fastcall CMetadataIPTCReaderWriter::CreateVariantFromStreamAndDesc(
        CMetadataIPTCReaderWriter *this,
        struct IStream *a2,
        unsigned int a3,
        const struct CMetadataIPTCReaderWriter::DataSetDesc *a4,
        struct tagPROPVARIANT *a5)
{
  int v5; // esi
  VARTYPE v6; // bp
  unsigned int v8; // edi
  unsigned int v9; // ebx
  LPVOID *p_pData; // r14
  LARGE_INTEGER *p_hVal; // r10
  _DWORD *p_lVal; // r15
  VARTYPE v13; // ax
  LPVOID v14; // rax
  void *v15; // rdx
  int FullBufferFromStream; // eax
  __int64 v17; // rbx
  LPVOID v18; // rax

  v5 = -1;
  v6 = 4113;
  v8 = 1;
  v9 = 0;
  p_pData = 0;
  p_hVal = 0;
  p_lVal = 0;
  *(_OWORD *)&a5->vt = 0;
  a5->bstrblobVal.pData = 0;
  if ( a4 )
  {
    v13 = *((_WORD *)a4 + 8);
    v6 = v13;
    if ( v13 != 30 )
    {
      v5 = *((_DWORD *)a4 + 5);
      if ( v5 > 1 || v5 == -1 )
        v6 = v13 | 0x1000;
    }
  }
  if ( (v6 & 0xEFFF) == 0x11 )
  {
    if ( (v6 & 0x1000) != 0 )
    {
      p_pData = (LPVOID *)&a5->bstrblobVal.pData;
      p_lVal = &a5->lVal;
    }
    else
    {
      p_hVal = &a5->hVal;
    }
    goto LABEL_8;
  }
  if ( (v6 & 0xEFFF) == 0x12 )
  {
    v8 = 2;
  }
  else
  {
    if ( (v6 & 0xEFFF) != 0x13 )
    {
      if ( (v6 & 0xEFFF) == 0x1E )
        p_pData = (LPVOID *)&a5->puuid;
      goto LABEL_8;
    }
    v8 = 4;
  }
  p_pData = (LPVOID *)((unsigned __int64)&a5->bstrblobVal.pData & -(__int64)((v6 & 0x1000) != 0));
  if ( (v6 & 0x1000) == 0 )
    p_hVal = &a5->hVal;
  p_lVal = (_DWORD *)((unsigned __int64)&a5->uhVal.QuadPart & -(__int64)((v6 & 0x1000) != 0));
LABEL_8:
  if ( v5 == -1 )
    v5 = a3 / v8;
  if ( v5 * v8 > a3 )
    v5 = a3 / v8;
  if ( v5 <= 0 )
    goto LABEL_24;
  if ( p_pData )
  {
    if ( v6 == 30 )
    {
      v17 = v5 * v8;
      v18 = CoTaskMemAlloc((unsigned int)(v17 + 1));
      *p_pData = v18;
      if ( !v18 )
      {
LABEL_16:
        v9 = -2147024882;
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(-2147024882);
LABEL_18:
        CoTaskMemFree(*p_pData);
        return v9;
      }
      *((_BYTE *)v18 + v17) = 0;
    }
    else
    {
      v14 = CoTaskMemAlloc(v5 * v8);
      *p_pData = v14;
      if ( !v14 )
        goto LABEL_16;
    }
    v15 = *p_pData;
  }
  else
  {
    v15 = 0;
    if ( p_hVal )
      v15 = p_hVal;
  }
  FullBufferFromStream = ReadFullBufferFromStream(a2, v15, v5 * v8);
  v9 = FullBufferFromStream;
  if ( FullBufferFromStream >= 0 )
  {
    if ( p_lVal )
      *p_lVal = v5;
LABEL_24:
    a5->vt = v6;
    return v9;
  }
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(FullBufferFromStream);
  if ( p_pData )
    goto LABEL_18;
  return v9;
}

```

## disassembly

```asm
0x18004f678  push    rbx
0x18004f67a  push    rbp
0x18004f67b  push    rsi
0x18004f67c  push    rdi
0x18004f67d  push    r12
0x18004f67f  push    r13
0x18004f681  push    r14
0x18004f683  push    r15
0x18004f685  sub     rsp, 28h
0x18004f689  mov     r12, [rsp+68h+arg_20]
0x18004f691  or      esi, 0FFFFFFFFh
0x18004f694  xor     eax, eax
0x18004f696  mov     ebp, 1011h
0x18004f69b  mov     r11d, r8d
0x18004f69e  xorps   xmm0, xmm0
0x18004f6a1  xor     r8d, r8d
0x18004f6a4  mov     r13, rdx
0x18004f6a7  lea     edi, [rsi+2]
0x18004f6aa  mov     ebx, r8d
0x18004f6ad  lea     edx, [rbp-11h]
0x18004f6b0  mov     r14d, r8d
0x18004f6b3  mov     r10d, r8d
0x18004f6b6  mov     r15d, r8d
0x18004f6b9  movups  xmmword ptr [r12], xmm0
0x18004f6be  mov     [r12+10h], rax
0x18004f6c3  test    r9, r9
0x18004f6c6  jz      short loc_18004F6EB
0x18004f6c8  movzx   eax, word ptr [r9+10h]
0x18004f6cd  movzx   ebp, ax
0x18004f6d0  cmp     ax, 1Eh
0x18004f6d4  jz      short loc_18004F6EB
0x18004f6d6  mov     esi, [r9+14h]
0x18004f6da  cmp     esi, edi
0x18004f6dc  jg      loc_18004F81C
0x18004f6e2  cmp     esi, 0FFFFFFFFh
0x18004f6e5  jz      loc_18004F81C
0x18004f6eb  movzx   ecx, bp
0x18004f6ee  btr     ecx, 0Ch
0x18004f6f2  sub     ecx, 11h
0x18004f6f5  jnz     loc_18004F7F0
0x18004f6fb  test    dx, bp
0x18004f6fe  jz      loc_18004F86E
0x18004f704  lea     r14, [r12+10h]
0x18004f709  lea     r15, [r12+8]
0x18004f70e  cmp     esi, 0FFFFFFFFh
0x18004f711  jnz     short loc_18004F71C
0x18004f713  xor     edx, edx
0x18004f715  mov     eax, r11d
0x18004f718  div     edi
0x18004f71a  mov     esi, eax
0x18004f71c  mov     eax, edi
0x18004f71e  imul    eax, esi
0x18004f721  cmp     eax, r11d
0x18004f724  ja      loc_18004F878
0x18004f72a  test    esi, esi
0x18004f72c  jle     short loc_18004F7A4
0x18004f72e  test    r14, r14
0x18004f731  jz      short loc_18004F77B
0x18004f733  cmp     bp, 1Eh
0x18004f737  jz      short loc_18004F7AB
0x18004f739  mov     ecx, edi
0x18004f73b  imul    ecx, esi; cb
0x18004f73e  call    cs:__imp_CoTaskMemAlloc
0x18004f745  nop     dword ptr [rax+rax+00h]
0x18004f74a  xor     r9d, r9d
0x18004f74d  mov     [r14], rax
0x18004f750  test    rax, rax
0x18004f753  jnz     short loc_18004F7CE
0x18004f755  cmp     cs:?g_doStackCaptures@@3HA, r9d; int g_doStackCaptures
0x18004f75c  mov     ebx, 8007000Eh
0x18004f761  jz      short loc_18004F76A
0x18004f763  mov     ecx, ebx; int
0x18004f765  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004f76a  mov     rcx, [r14]; pv
0x18004f76d  call    cs:__imp_CoTaskMemFree
0x18004f774  nop     dword ptr [rax+rax+00h]
0x18004f779  jmp     short loc_18004F7DC
0x18004f77b  test    r10, r10
0x18004f77e  mov     rdx, r8
0x18004f781  cmovnz  rdx, r10; void *
0x18004f785  imul    edi, esi
0x18004f788  mov     rcx, r13; struct IStream *
0x18004f78b  mov     r8d, edi; unsigned int
0x18004f78e  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x18004f793  xor     edi, edi
0x18004f795  mov     ebx, eax
0x18004f797  test    eax, eax
0x18004f799  js      short loc_18004F80B
0x18004f79b  test    r15, r15
0x18004f79e  jnz     loc_18004F886
0x18004f7a4  mov     [r12], bp
0x18004f7a9  jmp     short loc_18004F7DC
0x18004f7ab  mov     ebx, edi
0x18004f7ad  imul    ebx, esi
0x18004f7b0  lea     ecx, [rbx+1]; cb
0x18004f7b3  call    cs:__imp_CoTaskMemAlloc
0x18004f7ba  nop     dword ptr [rax+rax+00h]
0x18004f7bf  xor     r9d, r9d
0x18004f7c2  mov     [r14], rax
0x18004f7c5  test    rax, rax
0x18004f7c8  jz      short loc_18004F755
0x18004f7ca  mov     [rbx+rax], r9b
0x18004f7ce  mov     rdx, [r14]
0x18004f7d1  jmp     short loc_18004F785
0x18004f7d3  test    eax, eax
0x18004f7d5  jns     short loc_18004F79B
0x18004f7d7  test    r14, r14
0x18004f7da  jnz     short loc_18004F76A
0x18004f7dc  mov     eax, ebx
0x18004f7de  add     rsp, 28h
0x18004f7e2  pop     r15
0x18004f7e4  pop     r14
0x18004f7e6  pop     r13
0x18004f7e8  pop     r12
0x18004f7ea  pop     rdi
0x18004f7eb  pop     rsi
0x18004f7ec  pop     rbp
0x18004f7ed  pop     rbx
0x18004f7ee  retn
0x18004f7f0  sub     ecx, edi
0x18004f7f2  jz      short loc_18004F82E
0x18004f7f4  sub     ecx, edi
0x18004f7f6  jz      short loc_18004F827
0x18004f7f8  cmp     ecx, 0Bh
0x18004f7fb  jnz     loc_18004F70E
0x18004f801  lea     r14, [r12+8]
0x18004f806  jmp     loc_18004F70E
0x18004f80b  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18004f811  jz      short loc_18004F7D3
0x18004f813  mov     ecx, eax; int
0x18004f815  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004f81a  jmp     short loc_18004F7D7
0x18004f81c  or      ax, dx
0x18004f81f  movzx   ebp, ax
0x18004f822  jmp     loc_18004F6EB
0x18004f827  mov     edi, 4
0x18004f82c  jmp     short loc_18004F833
0x18004f82e  mov     edi, 2
0x18004f833  lea     r8, [r12+8]
0x18004f838  mov     eax, 1000h
0x18004f83d  lea     rcx, [r8+8]
0x18004f841  movzx   edx, bp
0x18004f844  and     dx, ax
0x18004f847  movzx   eax, dx
0x18004f84a  neg     ax
0x18004f84d  sbb     r14, r14
0x18004f850  xor     r9d, r9d
0x18004f853  and     r14, rcx
0x18004f856  test    dx, dx
0x18004f859  cmovz   r10, r8
0x18004f85d  neg     dx
0x18004f860  sbb     r15, r15
0x18004f863  and     r15, r8
0x18004f866  xor     r8d, r8d
0x18004f869  jmp     loc_18004F70E
0x18004f86e  lea     r10, [r12+8]
0x18004f873  jmp     loc_18004F70E
0x18004f878  xor     edx, edx
0x18004f87a  mov     eax, r11d
0x18004f87d  div     edi
0x18004f87f  mov     esi, eax
0x18004f881  jmp     loc_18004F72A
0x18004f886  mov     [r15], esi
0x18004f889  jmp     loc_18004F7A4
```
