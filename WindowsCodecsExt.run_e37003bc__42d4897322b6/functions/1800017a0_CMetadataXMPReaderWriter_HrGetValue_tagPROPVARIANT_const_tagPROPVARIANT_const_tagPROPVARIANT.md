# CMetadataXMPReaderWriter::HrGetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x1800017a0`
- end: `0x180001b46`
- name: `?HrGetValue@CMetadataXMPReaderWriter@@UEAAJPEBUtagPROPVARIANT@@0PEAU2@@Z`
- size: `934`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a0`
- `0x180001df0`
- `0x180002484`
- `0x18000285c`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800017eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180001964`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800017eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180001964`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180001a5b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180001a5b`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::HrGetValue(
        CMetadataXMPReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        PROPVARIANT *a4)
{
  PROPVARIANT *v4; // rdi
  LARGE_INTEGER hVal; // rcx
  VARTYPE vt; // ax
  unsigned int v10; // r12d
  int v11; // r13d
  unsigned int v12; // esi
  unsigned int v13; // edx
  int v14; // edi
  unsigned int i; // ebx
  struct RDFItem *v16; // rcx
  int v17; // eax
  RDFItem *v19; // rbx
  int v20; // eax
  int PropVariantValue; // eax
  int ItemPositionByGuidAndIndex; // eax
  unsigned int v23; // ebx
  int v24[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v25; // [rsp+88h] [rbp+10h] BYREF
  PROPVARIANT *pvar; // [rsp+98h] [rbp+20h]

  pvar = a4;
  v4 = a4;
  if ( !a2
    || a2->vt != 31
    || !a3
    || a3->vt != 31
    || (hVal = a2->hVal, !hVal.QuadPart)
    || !a3->hVal.QuadPart
    || (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))_o__wcsicmp)(
                       (LARGE_INTEGER)hVal.QuadPart,
                       L"PaddingSchema")
    || (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))_o__wcsicmp)((LARGE_INTEGER)a3->hVal.QuadPart, L"padding") )
  {
    vt = a3->vt;
    v10 = 0;
    v11 = 0;
    v25 = 0;
    v24[0] = 0;
    if ( vt != 72 )
    {
      if ( vt == 31 )
      {
        if ( (*(unsigned int (__fastcall **)(CMetadataXMPReaderWriter *))(*(_QWORD *)this + 272LL))(this) )
        {
          v10 = -2003292352;
          if ( g_doStackCaptures )
            DoStackCapture(-2003292352);
          goto LABEL_24;
        }
        v12 = *((_DWORD *)this + 58);
        v13 = 0;
        v25 = 0;
        v14 = 0;
        for ( i = 0; i < v12; ++i )
        {
          v16 = *(struct RDFItem **)(*((_QWORD *)this + 26) + 8LL * i);
          if ( (*((_BYTE *)v16 + 8) & 2) == 0 )
          {
            v24[0] = 1;
            v17 = CMetadataRDFReaderWriter::CompareItemSchemaAndValue(v16, a2, a3, v24);
            v14 = v17;
            if ( v17 < 0 )
            {
              if ( g_doStackCaptures )
                DoStackCapture(v17);
              goto LABEL_20;
            }
            v13 = v25;
            if ( v24[0] )
            {
              if ( !v25 )
                goto LABEL_31;
              v13 = ++v25;
            }
          }
        }
        if ( v13 )
        {
          if ( g_doStackCaptures )
            DoStackCapture(-2003292352);
          v14 = -2003292352;
        }
        else
        {
          v11 = 1;
          if ( v14 >= 0 )
          {
LABEL_31:
            v4 = pvar;
            goto LABEL_32;
          }
        }
LABEL_20:
        if ( g_doStackCaptures )
          DoStackCapture(v14);
        v10 = v14;
        goto LABEL_23;
      }
      v10 = -2147024809;
      if ( !g_doStackCaptures )
        goto LABEL_24;
LABEL_34:
      DoStackCapture(v10);
      goto LABEL_24;
    }
    ItemPositionByGuidAndIndex = CMetadataRDFReaderWriter::FindItemPositionByGuidAndIndex(this, a2, a3, v24, &v25);
    v23 = ItemPositionByGuidAndIndex;
    if ( ItemPositionByGuidAndIndex < 0 )
    {
      if ( g_doStackCaptures )
        DoStackCapture(ItemPositionByGuidAndIndex);
      v10 = v23;
      goto LABEL_24;
    }
    i = v25;
    v11 = v24[0];
LABEL_32:
    if ( v11 )
    {
      v10 = -2003292352;
      if ( !g_doStackCaptures )
        return v10;
      goto LABEL_34;
    }
    if ( !v4 )
    {
LABEL_23:
      if ( (v10 & 0x80000000) == 0 )
        return v10;
LABEL_24:
      if ( g_doStackCaptures )
        DoStackCapture(v10);
      return v10;
    }
    v19 = *(RDFItem **)(*((_QWORD *)this + 26) + 8LL * i);
    v20 = *((_DWORD *)v19 + 2);
    if ( (v20 & 4) == 0
      || (v20 & 8) != 0
      || (PropVariantValue = (*(__int64 (__fastcall **)(CMetadataXMPReaderWriter *, RDFItem *))(*(_QWORD *)this + 224LL))(
                               this,
                               v19),
          v10 = PropVariantValue,
          PropVariantValue >= 0) )
    {
      PropVariantValue = RDFItem::GetPropVariantValue(v19, (struct tagPROPVARIANT *)v4);
      v10 = PropVariantValue;
      if ( PropVariantValue >= 0 )
        goto LABEL_23;
      if ( !g_doStackCaptures )
        goto LABEL_51;
    }
    else if ( !g_doStackCaptures )
    {
      goto LABEL_51;
    }
    DoStackCapture(PropVariantValue);
LABEL_51:
    PropVariantClear(v4);
    if ( g_doStackCaptures )
      DoStackCapture(v10);
    goto LABEL_23;
  }
  if ( *((_DWORD *)this + 65) )
  {
    v10 = 0;
    if ( v4 )
    {
      *(_WORD *)v4 = 19;
      *((_DWORD *)v4 + 2) = *((_DWORD *)this + 64);
      return 0;
    }
    return v10;
  }
  v10 = -2003292352;
  if ( !g_doStackCaptures )
    return v10;
  DoStackCapture(-2003292352);
  return 2291674944LL;
}

```

## disassembly

```asm
0x1800017a0  mov     [rsp+pvar], r9
0x1800017a5  push    rbp
0x1800017a6  push    rdi
0x1800017a7  push    r12
0x1800017a9  push    r14
0x1800017ab  push    r15
0x1800017ad  sub     rsp, 50h
0x1800017b1  mov     rdi, r9
0x1800017b4  mov     r15, r8
0x1800017b7  mov     rbp, rdx
0x1800017ba  mov     r14, rcx
0x1800017bd  test    rdx, rdx
0x1800017c0  jz      short loc_1800017F9
0x1800017c2  cmp     word ptr [rdx], 1Fh
0x1800017c6  jnz     short loc_1800017F9
0x1800017c8  test    r8, r8
0x1800017cb  jz      short loc_1800017F9
0x1800017cd  cmp     word ptr [r8], 1Fh
0x1800017d2  jnz     short loc_1800017F9
0x1800017d4  mov     rcx, [rdx+8]
0x1800017d8  test    rcx, rcx
0x1800017db  jz      short loc_1800017F9
0x1800017dd  cmp     qword ptr [r8+8], 0
0x1800017e2  jz      short loc_1800017F9
0x1800017e4  lea     rdx, aPaddingschema; "PaddingSchema"
0x1800017eb  call    cs:__imp__o__wcsicmp
0x1800017f1  test    eax, eax
0x1800017f3  jz      loc_180001959
0x1800017f9  movzx   eax, word ptr [r15]
0x1800017fd  xor     r12d, r12d
0x180001800  mov     [rsp+78h+arg_0], rbx
0x180001808  mov     ecx, 48h ; 'H'
0x18000180d  mov     [rsp+78h+var_30], rsi
0x180001812  mov     [rsp+78h+var_38], r13
0x180001817  mov     r13d, r12d
0x18000181a  mov     [rsp+78h+arg_8], r12d
0x180001822  mov     [rsp+78h+var_48], r12d
0x180001827  cmp     cx, ax
0x18000182a  jz      loc_180001AB8
0x180001830  mov     ecx, 1Fh
0x180001835  cmp     cx, ax
0x180001838  jnz     loc_180001A17
0x18000183e  mov     rax, [r14]
0x180001841  mov     rcx, r14
0x180001844  mov     rax, [rax+110h]
0x18000184b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001850  test    eax, eax
0x180001852  jnz     loc_180001B26
0x180001858  mov     esi, [r14+0E8h]
0x18000185f  mov     edx, r12d
0x180001862  mov     [rsp+78h+arg_8], edx
0x180001869  mov     edi, r12d
0x18000186c  mov     ebx, r12d
0x18000186f  nop
0x180001870  cmp     ebx, esi
0x180001872  jnb     loc_180001913
0x180001878  mov     rcx, [r14+0D0h]
0x18000187f  mov     eax, ebx
0x180001881  mov     rcx, [rcx+rax*8]; struct RDFItem *
0x180001885  test    byte ptr [rcx+8], 2
0x180001889  jnz     short loc_1800018C4
0x18000188b  lea     r9, [rsp+78h+var_48]; int *
0x180001890  mov     [rsp+78h+var_48], 1
0x180001898  mov     r8, r15; struct tagPROPVARIANT *
0x18000189b  mov     rdx, rbp; struct tagPROPVARIANT *
0x18000189e  call    ?CompareItemSchemaAndValue@CMetadataRDFReaderWriter@@KAJPEAVRDFItem@@PEBUtagPROPVARIANT@@1PEAH@Z; CMetadataRDFReaderWriter::CompareItemSchemaAndValue(RDFItem *,tagPROPVARIANT const *,tagPROPVARIANT const *,int *)
0x1800018a3  mov     edi, eax
0x1800018a5  test    eax, eax
0x1800018a7  jns     short loc_1800018B6
0x1800018a9  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800018b0  jnz     short loc_1800018C8
0x1800018b2  test    eax, eax
0x1800018b4  js      short loc_1800018CF
0x1800018b6  mov     edx, [rsp+78h+arg_8]
0x1800018bd  cmp     [rsp+78h+var_48], r12d
0x1800018c2  jnz     short loc_180001927
0x1800018c4  inc     ebx
0x1800018c6  jmp     short loc_180001870
0x1800018c8  mov     ecx, eax; int
0x1800018ca  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800018cf  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800018d6  jnz     loc_1800019B7
0x1800018dc  mov     r12d, edi
0x1800018df  test    r12d, r12d
0x1800018e2  jns     short loc_1800018F1
0x1800018e4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800018eb  jnz     loc_1800019AA
0x1800018f1  mov     rsi, [rsp+78h+var_30]
0x1800018f6  mov     rbx, [rsp+78h+arg_0]
0x1800018fe  mov     r13, [rsp+78h+var_38]
0x180001903  mov     eax, r12d
0x180001906  add     rsp, 50h
0x18000190a  pop     r15
0x18000190c  pop     r14
0x18000190e  pop     r12
0x180001910  pop     rdi
0x180001911  pop     rbp
0x180001912  retn
0x180001913  test    edx, edx
0x180001915  jnz     loc_180001B07
0x18000191b  mov     r13d, 1
0x180001921  test    edi, edi
0x180001923  js      short loc_1800018CF
0x180001925  jmp     short loc_18000192F
0x180001927  test    edx, edx
0x180001929  jnz     loc_1800019C3
0x18000192f  mov     rdi, [rsp+78h+pvar]
0x180001937  test    r13d, r13d
0x18000193a  jz      loc_1800019D1
0x180001940  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001947  mov     r12d, 88982F40h
0x18000194d  jz      short loc_1800018F1
0x18000194f  mov     ecx, r12d; int
0x180001952  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001957  jmp     short loc_1800018E4
0x180001959  mov     rcx, [r15+8]
0x18000195d  lea     rdx, aPadding; "padding"
0x180001964  call    cs:__imp__o__wcsicmp
0x18000196a  test    eax, eax
0x18000196c  jnz     loc_1800017F9
0x180001972  cmp     [r14+104h], eax
0x180001979  jz      loc_180001A8D
0x18000197f  xor     r12d, r12d
0x180001982  test    rdi, rdi
0x180001985  jz      loc_180001903
0x18000198b  mov     word ptr [rdi], 13h
0x180001990  mov     eax, [r14+100h]
0x180001997  mov     [rdi+8], eax
0x18000199a  mov     eax, r12d
0x18000199d  add     rsp, 50h
0x1800019a1  pop     r15
0x1800019a3  pop     r14
0x1800019a5  pop     r12
0x1800019a7  pop     rdi
0x1800019a8  pop     rbp
0x1800019a9  retn
0x1800019aa  mov     ecx, r12d; int
0x1800019ad  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800019b2  jmp     loc_1800018F1
0x1800019b7  mov     ecx, edi; int
0x1800019b9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800019be  jmp     loc_1800018DC
0x1800019c3  inc     edx
0x1800019c5  mov     [rsp+78h+arg_8], edx
0x1800019cc  jmp     loc_1800018C4
0x1800019d1  test    rdi, rdi
0x1800019d4  jz      loc_1800018DF
0x1800019da  mov     rax, [r14+0D0h]
0x1800019e1  mov     ecx, ebx
0x1800019e3  mov     rbx, [rax+rcx*8]
0x1800019e7  mov     eax, [rbx+8]
0x1800019ea  test    al, 4
0x1800019ec  jnz     short loc_180001A2F
0x1800019ee  mov     rdx, rdi; struct tagPROPVARIANT *
0x1800019f1  mov     rcx, rbx; this
0x1800019f4  call    ?GetPropVariantValue@RDFItem@@QEAAJPEAUtagPROPVARIANT@@@Z; RDFItem::GetPropVariantValue(tagPROPVARIANT *)
0x1800019f9  mov     r12d, eax
0x1800019fc  test    eax, eax
0x1800019fe  jns     loc_1800018DF
0x180001a04  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001a0b  jnz     short loc_180001A7B
0x180001a0d  test    eax, eax
0x180001a0f  jns     loc_1800018DF
0x180001a15  jmp     short loc_180001A58
0x180001a17  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180001a1e  mov     r12d, 80070057h
0x180001a24  jz      loc_1800018E4
0x180001a2a  jmp     loc_18000194F
0x180001a2f  test    al, 8
0x180001a31  jnz     short loc_1800019EE
0x180001a33  mov     rax, [r14]
0x180001a36  mov     rdx, rbx
0x180001a39  mov     rcx, r14
0x180001a3c  mov     rax, [rax+0E0h]
0x180001a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a48  mov     r12d, eax
0x180001a4b  test    eax, eax
0x180001a4d  jns     short loc_1800019EE
0x180001a4f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001a56  jnz     short loc_180001A84
0x180001a58  mov     rcx, rdi; pvar
0x180001a5b  call    cs:__imp_PropVariantClear
0x180001a61  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001a68  jz      loc_1800018DF
0x180001a6e  mov     ecx, r12d; int
0x180001a71  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001a76  jmp     loc_1800018DF
0x180001a7b  mov     ecx, eax; int
0x180001a7d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001a82  jmp     short loc_180001A58
0x180001a84  mov     ecx, eax; int
0x180001a86  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001a8b  jmp     short loc_180001A58
0x180001a8d  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001a94  mov     r12d, 88982F40h
0x180001a9a  jz      loc_180001903
0x180001aa0  mov     ecx, r12d; int
0x180001aa3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001aa8  mov     eax, r12d
0x180001aab  add     rsp, 50h
0x180001aaf  pop     r15
0x180001ab1  pop     r14
0x180001ab3  pop     r12
0x180001ab5  pop     rdi
0x180001ab6  pop     rbp
0x180001ab7  retn
0x180001ab8  lea     rax, [rsp+78h+arg_8]
0x180001ac0  mov     r8, r15; struct tagPROPVARIANT *
0x180001ac3  lea     r9, [rsp+78h+var_48]; int *
0x180001ac8  mov     [rsp+78h+var_58], rax; unsigned int *
0x180001acd  mov     rdx, rbp; struct tagPROPVARIANT *
0x180001ad0  mov     rcx, r14; this
0x180001ad3  call    ?FindItemPositionByGuidAndIndex@CMetadataRDFReaderWriter@@IEAAJPEBUtagPROPVARIANT@@0PEAHPEAI@Z; CMetadataRDFReaderWriter::FindItemPositionByGuidAndIndex(tagPROPVARIANT const *,tagPROPVARIANT const *,int *,uint *)
0x180001ad8  mov     ebx, eax
0x180001ada  test    eax, eax
0x180001adc  jns     short loc_180001AF6
0x180001ade  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180001ae5  jz      short loc_180001AEE
0x180001ae7  mov     ecx, eax; int
0x180001ae9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001aee  mov     r12d, ebx
0x180001af1  jmp     loc_1800018E4
0x180001af6  mov     ebx, [rsp+78h+arg_8]
0x180001afd  mov     r13d, [rsp+78h+var_48]
0x180001b02  jmp     loc_180001937
0x180001b07  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180001b0e  mov     r12d, 88982F40h
0x180001b14  jz      short loc_180001B1E
0x180001b16  mov     ecx, r12d; int
0x180001b19  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001b1e  mov     edi, r12d
0x180001b21  jmp     loc_1800018CF
0x180001b26  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180001b2d  mov     r12d, 88982F40h
0x180001b33  jz      loc_1800018E4
0x180001b39  mov     ecx, r12d; int
0x180001b3c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180001b41  jmp     loc_1800018E4
```
