# CMetadataRDFReaderWriter::HrSetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180001630`
- end: `0x18000179a`
- name: `?HrSetValue@CMetadataRDFReaderWriter@@MEAAJPEBUtagPROPVARIANT@@00@Z`
- size: `362`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001440`
- `0x1800230a0`
- `0x180024ad0`

## callees

- `0x180001630`
- `0x180001df0`
- `0x18000285c`
- `0x180002aa0`
- `0x1800171c4`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::HrSetValue(
        CMetadataRDFReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4)
{
  const struct tagPROPVARIANT *v5; // r14
  const struct tagPROPVARIANT *v6; // rbp
  unsigned int v8; // r12d
  unsigned int v9; // ebx
  __int64 i; // rdi
  struct RDFItem *v11; // rcx
  int v12; // eax
  int ItemPositionByGuidAndIndex; // eax
  int v15; // ecx
  int v16[22]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v17; // [rsp+A0h] [rbp+18h] BYREF

  v17 = 0;
  v16[0] = 0;
  v5 = a3;
  v6 = a2;
  if ( a3->vt == 72 )
  {
    ItemPositionByGuidAndIndex = CMetadataRDFReaderWriter::FindItemPositionByGuidAndIndex(this, a2, a3, v16, &v17);
    v9 = ItemPositionByGuidAndIndex;
    if ( ItemPositionByGuidAndIndex >= 0 )
    {
      LODWORD(i) = v17;
      v6 = 0;
      v5 = 0;
LABEL_18:
      ItemPositionByGuidAndIndex = CMetadataRDFReaderWriter::SetItemByPosition(this, i, v6, v5, a4);
      v9 = ItemPositionByGuidAndIndex;
      if ( ItemPositionByGuidAndIndex >= 0 )
        return v9;
    }
    if ( !g_doStackCaptures )
      return v9;
    v15 = ItemPositionByGuidAndIndex;
LABEL_21:
    DoStackCapture(v15);
    return v9;
  }
  if ( a3->vt == 31 )
  {
    v8 = *((_DWORD *)this + 58);
    v9 = 0;
    for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
    {
      v11 = *(struct RDFItem **)(*((_QWORD *)this + 26) + 8 * i);
      if ( (*((_BYTE *)v11 + 8) & 2) == 0 )
      {
        v17 = 1;
        v12 = CMetadataRDFReaderWriter::CompareItemSchemaAndValue(v11, v6, v5, (int *)&v17);
        v9 = v12;
        if ( v12 < 0 )
        {
          if ( g_doStackCaptures )
            DoStackCapture(v12);
          goto LABEL_13;
        }
        if ( v17 )
          goto LABEL_18;
      }
    }
    if ( (v9 & 0x80000000) == 0 )
      goto LABEL_18;
  }
  else
  {
    v9 = -2147024809;
  }
LABEL_13:
  if ( g_doStackCaptures )
  {
    v15 = v9;
    goto LABEL_21;
  }
  return v9;
}

```

## disassembly

```asm
0x180001630  mov     rax, rsp
0x180001633  push    rbx
0x180001634  push    rbp
0x180001635  push    rsi
0x180001636  push    rdi
0x180001637  push    r12
0x180001639  push    r13
0x18000163b  push    r14
0x18000163d  push    r15
0x18000163f  sub     rsp, 48h
0x180001643  mov     dword ptr [rax+18h], 0
0x18000164a  mov     r13, r9
0x18000164d  mov     dword ptr [rax-58h], 0
0x180001654  mov     r14, r8
0x180001657  mov     eax, 48h ; 'H'
0x18000165c  mov     rbp, rdx
0x18000165f  mov     r15, rcx
0x180001662  cmp     ax, [r8]
0x180001666  jz      loc_18000170E
0x18000166c  mov     eax, 1Fh
0x180001671  cmp     ax, [r8]
0x180001675  jnz     loc_180001790
0x18000167b  mov     r12d, [rcx+0E8h]
0x180001682  xor     ebx, ebx
0x180001684  xor     esi, esi
0x180001686  xor     edi, edi
0x180001688  cmp     edi, r12d
0x18000168b  jnb     short loc_1800016E6
0x18000168d  mov     rax, [r15+0D0h]
0x180001694  mov     rcx, [rax+rdi*8]; struct RDFItem *
0x180001698  test    byte ptr [rcx+8], 2
0x18000169c  jnz     short loc_1800016D9
0x18000169e  lea     r9, [rsp+88h+arg_10]; int *
0x1800016a6  mov     [rsp+88h+arg_10], 1
0x1800016b1  mov     r8, r14; struct tagPROPVARIANT *
0x1800016b4  mov     rdx, rbp; struct tagPROPVARIANT *
0x1800016b7  call    ?CompareItemSchemaAndValue@CMetadataRDFReaderWriter@@KAJPEAVRDFItem@@PEBUtagPROPVARIANT@@1PEAH@Z; CMetadataRDFReaderWriter::CompareItemSchemaAndValue(RDFItem *,tagPROPVARIANT const *,tagPROPVARIANT const *,int *)
0x1800016bc  mov     ebx, eax
0x1800016be  test    eax, eax
0x1800016c0  jns     short loc_1800016CF
0x1800016c2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800016c9  jnz     short loc_1800016DD
0x1800016cb  test    eax, eax
0x1800016cd  js      short loc_1800016F2
0x1800016cf  cmp     [rsp+88h+arg_10], 0
0x1800016d7  jnz     short loc_180001738
0x1800016d9  inc     edi
0x1800016db  jmp     short loc_180001688
0x1800016dd  mov     ecx, eax; int
0x1800016df  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800016e4  jmp     short loc_1800016F2
0x1800016e6  test    esi, esi
0x1800016e8  jnz     loc_180001777
0x1800016ee  test    ebx, ebx
0x1800016f0  jns     short loc_18000173C
0x1800016f2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800016f9  jnz     short loc_180001759
0x1800016fb  mov     eax, ebx
0x1800016fd  add     rsp, 48h
0x180001701  pop     r15
0x180001703  pop     r14
0x180001705  pop     r13
0x180001707  pop     r12
0x180001709  pop     rdi
0x18000170a  pop     rsi
0x18000170b  pop     rbp
0x18000170c  pop     rbx
0x18000170d  retn
0x18000170e  lea     rax, [rsp+88h+arg_10]
0x180001716  lea     r9, [rsp+88h+var_58]; int *
0x18000171b  mov     [rsp+88h+var_68], rax; unsigned int *
0x180001720  call    ?FindItemPositionByGuidAndIndex@CMetadataRDFReaderWriter@@IEAAJPEBUtagPROPVARIANT@@0PEAHPEAI@Z; CMetadataRDFReaderWriter::FindItemPositionByGuidAndIndex(tagPROPVARIANT const *,tagPROPVARIANT const *,int *,uint *)
0x180001725  mov     ebx, eax
0x180001727  test    eax, eax
0x180001729  jns     short loc_180001762
0x18000172b  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001732  jz      short loc_1800016FB
0x180001734  mov     ecx, eax
0x180001736  jmp     short loc_18000175B
0x180001738  test    esi, esi
0x18000173a  jnz     short loc_180001770
0x18000173c  mov     r9, r14; struct tagPROPVARIANT *
0x18000173f  mov     [rsp+88h+var_68], r13; struct tagPROPVARIANT *
0x180001744  mov     r8, rbp; struct tagPROPVARIANT *
0x180001747  mov     edx, edi; unsigned int
0x180001749  mov     rcx, r15; this
0x18000174c  call    ?SetItemByPosition@CMetadataRDFReaderWriter@@IEAAJIPEBUtagPROPVARIANT@@00@Z; CMetadataRDFReaderWriter::SetItemByPosition(uint,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x180001751  mov     ebx, eax
0x180001753  test    eax, eax
0x180001755  jns     short loc_1800016FB
0x180001757  jmp     short loc_18000172B
0x180001759  mov     ecx, ebx; int
0x18000175b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001760  jmp     short loc_1800016FB
0x180001762  mov     edi, [rsp+88h+arg_10]
0x180001769  xor     ebp, ebp
0x18000176b  xor     r14d, r14d
0x18000176e  jmp     short loc_18000173C
0x180001770  inc     esi
0x180001772  jmp     loc_1800016D9
0x180001777  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000177e  mov     ebx, 88982F40h
0x180001783  jz      loc_1800016FB
0x180001789  mov     ecx, ebx
0x18000178b  jmp     loc_1800016DF
0x180001790  mov     ebx, 80070057h
0x180001795  jmp     loc_1800016F2
```
