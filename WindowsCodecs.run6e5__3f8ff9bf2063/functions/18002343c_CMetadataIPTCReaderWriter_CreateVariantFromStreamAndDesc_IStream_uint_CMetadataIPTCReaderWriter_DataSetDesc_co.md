# CMetadataIPTCReaderWriter::CreateVariantFromStreamAndDesc(IStream *,uint,CMetadataIPTCReaderWriter::DataSetDesc const *,tagPROPVARIANT *)

- ea: `0x18002343c`
- end: `0x18002363f`
- name: `?CreateVariantFromStreamAndDesc@CMetadataIPTCReaderWriter@@AEAAJPEAUIStream@@IPEBUDataSetDesc@1@PEAUtagPROPVARIANT@@@Z`
- size: `515`
- prototype: `int(CMetadataIPTCReaderWriter *__hidden this, struct IStream *, unsigned int, const struct CMetadataIPTCReaderWriter::DataSetDesc *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023648`

## callees

- `0x18002343c`
- `0x180036cb4`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002356b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002356b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002352b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002352b`

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
0x18002343c  push    rbx
0x18002343e  push    rbp
0x18002343f  push    rsi
0x180023440  push    rdi
0x180023441  push    r12
0x180023443  push    r13
0x180023445  push    r14
0x180023447  push    r15
0x180023449  sub     rsp, 28h
0x18002344d  mov     r12, [rsp+68h+arg_20]
0x180023455  or      esi, 0FFFFFFFFh
0x180023458  xor     eax, eax
0x18002345a  mov     ebp, 1011h
0x18002345f  mov     r11d, r8d
0x180023462  xorps   xmm0, xmm0
0x180023465  xor     r8d, r8d
0x180023468  mov     r13, rdx
0x18002346b  lea     edi, [rsi+2]
0x18002346e  mov     ebx, r8d
0x180023471  lea     edx, [rbp-11h]
0x180023474  mov     r14d, r8d
0x180023477  mov     r10d, r8d
0x18002347a  mov     r15d, r8d
0x18002347d  movups  xmmword ptr [r12], xmm0
0x180023482  mov     [r12+10h], rax
0x180023487  test    r9, r9
0x18002348a  jz      short loc_1800234AF
0x18002348c  movzx   eax, word ptr [r9+10h]
0x180023491  movzx   ebp, ax
0x180023494  cmp     ax, 1Eh
0x180023498  jz      short loc_1800234AF
0x18002349a  mov     esi, [r9+14h]
0x18002349e  cmp     esi, edi
0x1800234a0  jg      loc_1800235CD
0x1800234a6  cmp     esi, 0FFFFFFFFh
0x1800234a9  jz      loc_1800235CD
0x1800234af  movzx   ecx, bp
0x1800234b2  btr     ecx, 0Ch
0x1800234b6  sub     ecx, 11h
0x1800234b9  jnz     loc_1800235A1
0x1800234bf  test    dx, bp
0x1800234c2  jz      loc_18002361F
0x1800234c8  lea     r14, [r12+10h]
0x1800234cd  lea     r15, [r12+8]
0x1800234d2  cmp     esi, 0FFFFFFFFh
0x1800234d5  jnz     short loc_1800234E0
0x1800234d7  xor     edx, edx
0x1800234d9  mov     eax, r11d
0x1800234dc  div     edi
0x1800234de  mov     esi, eax
0x1800234e0  mov     eax, edi
0x1800234e2  imul    eax, esi
0x1800234e5  cmp     eax, r11d
0x1800234e8  ja      loc_180023629
0x1800234ee  test    esi, esi
0x1800234f0  jle     short loc_18002355C
0x1800234f2  test    r14, r14
0x1800234f5  jz      short loc_180023533
0x1800234f7  cmp     bp, 1Eh
0x1800234fb  jz      short loc_180023563
0x1800234fd  mov     ecx, edi
0x1800234ff  imul    ecx, esi; cb
0x180023502  call    cs:__imp_CoTaskMemAlloc
0x180023508  xor     r9d, r9d
0x18002350b  mov     [r14], rax
0x18002350e  test    rax, rax
0x180023511  jnz     short loc_180023580
0x180023513  cmp     cs:?g_doStackCaptures@@3HA, r9d; int g_doStackCaptures
0x18002351a  mov     ebx, 8007000Eh
0x18002351f  jz      short loc_180023528
0x180023521  mov     ecx, ebx; int
0x180023523  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180023528  mov     rcx, [r14]; pv
0x18002352b  call    cs:__imp_CoTaskMemFree
0x180023531  jmp     short loc_18002358E
0x180023533  test    r10, r10
0x180023536  mov     rdx, r8
0x180023539  cmovnz  rdx, r10; void *
0x18002353d  imul    edi, esi
0x180023540  mov     rcx, r13; struct IStream *
0x180023543  mov     r8d, edi; unsigned int
0x180023546  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x18002354b  xor     edi, edi
0x18002354d  mov     ebx, eax
0x18002354f  test    eax, eax
0x180023551  js      short loc_1800235BC
0x180023553  test    r15, r15
0x180023556  jnz     loc_180023637
0x18002355c  mov     [r12], bp
0x180023561  jmp     short loc_18002358E
0x180023563  mov     ebx, edi
0x180023565  imul    ebx, esi
0x180023568  lea     ecx, [rbx+1]; cb
0x18002356b  call    cs:__imp_CoTaskMemAlloc
0x180023571  xor     r9d, r9d
0x180023574  mov     [r14], rax
0x180023577  test    rax, rax
0x18002357a  jz      short loc_180023513
0x18002357c  mov     [rbx+rax], r9b
0x180023580  mov     rdx, [r14]
0x180023583  jmp     short loc_18002353D
0x180023585  test    eax, eax
0x180023587  jns     short loc_180023553
0x180023589  test    r14, r14
0x18002358c  jnz     short loc_180023528
0x18002358e  mov     eax, ebx
0x180023590  add     rsp, 28h
0x180023594  pop     r15
0x180023596  pop     r14
0x180023598  pop     r13
0x18002359a  pop     r12
0x18002359c  pop     rdi
0x18002359d  pop     rsi
0x18002359e  pop     rbp
0x18002359f  pop     rbx
0x1800235a0  retn
0x1800235a1  sub     ecx, edi
0x1800235a3  jz      short loc_1800235DF
0x1800235a5  sub     ecx, edi
0x1800235a7  jz      short loc_1800235D8
0x1800235a9  cmp     ecx, 0Bh
0x1800235ac  jnz     loc_1800234D2
0x1800235b2  lea     r14, [r12+8]
0x1800235b7  jmp     loc_1800234D2
0x1800235bc  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800235c2  jz      short loc_180023585
0x1800235c4  mov     ecx, eax; int
0x1800235c6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800235cb  jmp     short loc_180023589
0x1800235cd  or      ax, dx
0x1800235d0  movzx   ebp, ax
0x1800235d3  jmp     loc_1800234AF
0x1800235d8  mov     edi, 4
0x1800235dd  jmp     short loc_1800235E4
0x1800235df  mov     edi, 2
0x1800235e4  lea     r8, [r12+8]
0x1800235e9  mov     eax, 1000h
0x1800235ee  lea     rcx, [r8+8]
0x1800235f2  movzx   edx, bp
0x1800235f5  and     dx, ax
0x1800235f8  movzx   eax, dx
0x1800235fb  neg     ax
0x1800235fe  sbb     r14, r14
0x180023601  xor     r9d, r9d
0x180023604  and     r14, rcx
0x180023607  test    dx, dx
0x18002360a  cmovz   r10, r8
0x18002360e  neg     dx
0x180023611  sbb     r15, r15
0x180023614  and     r15, r8
0x180023617  xor     r8d, r8d
0x18002361a  jmp     loc_1800234D2
0x18002361f  lea     r10, [r12+8]
0x180023624  jmp     loc_1800234D2
0x180023629  xor     edx, edx
0x18002362b  mov     eax, r11d
0x18002362e  div     edi
0x180023630  mov     esi, eax
0x180023632  jmp     loc_1800234EE
0x180023637  mov     [r15], esi
0x18002363a  jmp     loc_18002355C
```
