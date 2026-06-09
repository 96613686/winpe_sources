# CMetadataRDFReaderWriter::SetItemByPosition(uint,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180002aa0`
- end: `0x180002fd3`
- name: `?SetItemByPosition@CMetadataRDFReaderWriter@@IEAAJIPEBUtagPROPVARIANT@@00@Z`
- size: `1331`
- prototype: `__int64 __usercall@<rax>(CMetadataRDFReaderWriter *__hidden this@<rcx>, unsigned int@<edx>, const struct tagPROPVARIANT *@<r8>, const struct tagPROPVARIANT *@<r9>, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180001630`
- `0x1800214e0`

## callees

- `0x180002aa0`
- `0x1800040e8`
- `0x180004164`
- `0x180004280`
- `0x18000e82c`
- `0x1800156a8`
- `0x180015c60`
- `0x1800171c4`
- `0x18001d838`
- `0x180021a30`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::SetItemByPosition(
        CMetadataRDFReaderWriter *this,
        unsigned int a2,
        const struct tagPROPVARIANT *a3,
        const struct tagPROPVARIANT *a4,
        struct tagPROPVARIANT *a5)
{
  __int64 v7; // r12
  int v9; // eax
  unsigned int v10; // ebx
  int v12; // ecx
  int v13; // edx
  int v14; // eax
  unsigned int v15; // eax
  int v16; // esi
  int v17; // r15d
  __int64 *v18; // rsi
  __int64 v19; // rax
  __int64 *v20; // r14
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  unsigned int v24; // edx
  bool v25; // zf
  struct tagPROPVARIANT *v26; // rcx
  RDFItem *v27; // r13
  __int64 v28; // r15
  __int64 v29; // rcx
  RDFItem *v30; // r13
  __int64 v31; // r15
  __int64 v32; // rcx
  void (__fastcall ***v33)(_QWORD, __int64); // rcx
  RDFItem *v34; // [rsp+20h] [rbp-48h] BYREF
  int v35; // [rsp+28h] [rbp-40h] BYREF
  struct tagPROPVARIANT *v36; // [rsp+30h] [rbp-38h] BYREF
  struct tagPROPVARIANT *v37; // [rsp+38h] [rbp-30h]
  struct _GUID v38; // [rsp+40h] [rbp-28h] BYREF

  v7 = a2;
  v37 = a5;
  v36 = a5;
  v34 = 0;
  v35 = 0;
  v38 = 0;
  v9 = CMetadataRDFReaderWriter::CheckValidItemValue(this, (const struct tagPROPVARIANT **)&v36, &v38, &v35);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_2;
  v9 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, RDFItem **))(*(_QWORD *)this + 384LL))(this, &v34);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_2;
  v9 = RDFItem::SetPropVariantValue(v34, a5);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_2;
  v13 = v35;
  v14 = *((_DWORD *)v34 + 2);
  if ( v35 )
    v15 = v14 | 4;
  else
    v15 = v14 & 0xFFFFFFFB;
  *((_DWORD *)v34 + 2) = v15;
  *((_DWORD *)v34 + 2) |= 8u;
  *((_DWORD *)v34 + 2) |= 1u;
  if ( v13 )
    v9 = RDFItem::SetEmbeddedMetadataGUID(v34, &v38);
  else
    v9 = RDFItem::ClearEmbeddedMetadataGUID(v34);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_3;
    goto LABEL_6;
  }
  v16 = 0;
  v17 = 0;
  if ( !a4 || a4->vt != 31 || !a4->hVal.QuadPart )
    goto LABEL_19;
  v9 = (*(__int64 (__fastcall **)(RDFItem *))(*(_QWORD *)v34 + 40LL))(v34);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_3;
LABEL_6:
    v12 = v9;
    goto LABEL_7;
  }
  v16 = 1;
  if ( !a3 || a3->vt != 31 )
  {
LABEL_19:
    if ( !(*(unsigned int (__fastcall **)(CMetadataRDFReaderWriter *))(*(_QWORD *)this + 272LL))(this) )
    {
      if ( (unsigned int)v7 < *((_DWORD *)this + 58) )
      {
        _mm_lfence();
        if ( (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 26) + 8 * v7) + 8LL) & 2) == 0 )
        {
          _mm_lfence();
          v20 = *(__int64 **)(*((_QWORD *)this + 26) + 8 * v7);
          if ( !v16 )
          {
            v22 = *v20;
            v36 = 0;
            v9 = (*(__int64 (__fastcall **)(__int64 *, struct tagPROPVARIANT **))(v22 + 24))(v20, &v36);
            v10 = v9;
            if ( v9 < 0 )
              goto LABEL_2;
            v9 = (*(__int64 (__fastcall **)(RDFItem *, struct tagPROPVARIANT *))(*(_QWORD *)v34 + 40LL))(v34, v36);
            v10 = v9;
            if ( v9 < 0 )
            {
              if ( g_doStackCaptures )
                goto LABEL_6;
              goto LABEL_3;
            }
            v16 = 1;
          }
          if ( v17 )
            goto LABEL_20;
          v21 = *v20;
          v36 = 0;
          v9 = (*(__int64 (__fastcall **)(__int64 *, struct tagPROPVARIANT **))(v21 + 48))(v20, &v36);
          v10 = v9;
          if ( v9 < 0 )
            goto LABEL_2;
          v9 = (*(__int64 (__fastcall **)(RDFItem *, struct tagPROPVARIANT *))(*(_QWORD *)v34 + 64LL))(v34, v36);
          v10 = v9;
          if ( v9 < 0 )
          {
            if ( g_doStackCaptures )
              goto LABEL_6;
            goto LABEL_3;
          }
        }
      }
      if ( !v16 )
      {
        v10 = -2147024809;
        goto LABEL_32;
      }
    }
LABEL_20:
    v18 = (__int64 *)((char *)this + 208);
    if ( (_DWORD)v7 == *((_DWORD *)this + 58) )
    {
      if ( (*(unsigned int (__fastcall **)(CMetadataRDFReaderWriter *))(*(_QWORD *)this + 280LL))(this) )
      {
LABEL_22:
        if ( v35 )
        {
          if ( *((_QWORD *)v34 + 2) )
            goto LABEL_25;
          v9 = CMetadataRDFReaderWriter::AddPlaceholderNodeToDOM(this, v34);
        }
        else
        {
          v9 = CMetadataRDFReaderWriter::ApplyItemToDOM(this, v34, 1);
        }
        v10 = v9;
        if ( v9 >= 0 )
        {
LABEL_25:
          v9 = CMILObjectArray<RDFItem *>::Add((char *)this + 208, &v34);
          v10 = v9;
          if ( v9 < 0 )
          {
            if ( !g_doStackCaptures )
              goto LABEL_3;
            goto LABEL_6;
          }
          ++*((_DWORD *)this + 43);
          goto LABEL_27;
        }
LABEL_2:
        if ( !g_doStackCaptures )
          goto LABEL_3;
        goto LABEL_6;
      }
      if ( v37->vt != 13 )
      {
        *((_DWORD *)v34 + 2) |= 0x10u;
        goto LABEL_22;
      }
    }
    else
    {
      v23 = *v18;
      if ( (*(_BYTE *)(*(_QWORD *)(*v18 + 8 * v7) + 8LL) & 2) != 0 )
        ++*((_DWORD *)this + 43);
      v24 = *((_DWORD *)v34 + 2) | 0x10;
      v25 = (*(_DWORD *)(*(_QWORD *)(v23 + 8 * v7) + 8LL) & 0x10) == 0;
      v26 = v37;
      if ( v25 )
        v24 = *((_DWORD *)v34 + 2) & 0xFFFFFFEF;
      *((_DWORD *)v34 + 2) = v24;
      if ( v26->vt != 13 || (*((_BYTE *)v34 + 8) & 0x10) == 0 )
      {
        v27 = v34;
        v28 = *(_QWORD *)(*(_QWORD *)(*v18 + 8 * v7) + 16LL);
        v29 = *((_QWORD *)v34 + 2);
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        *((_QWORD *)v27 + 2) = v28;
        if ( v28 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
        v30 = v34;
        v31 = *(_QWORD *)(*(_QWORD *)(*v18 + 8 * v7) + 24LL);
        v32 = *((_QWORD *)v34 + 3);
        if ( v32 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        *((_QWORD *)v30 + 3) = v31;
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
        if ( !v35 )
        {
          v9 = CMetadataRDFReaderWriter::ApplyItemToDOM(this, v34, 1);
          v10 = v9;
          if ( v9 < 0 )
          {
            if ( g_doStackCaptures )
              goto LABEL_6;
            goto LABEL_3;
          }
        }
        v33 = *(void (__fastcall ****)(_QWORD, __int64))(*v18 + 8 * v7);
        if ( v33 )
          (**v33)(v33, 1);
        *(_QWORD *)(*v18 + 8 * v7) = v34;
LABEL_27:
        v19 = *(_QWORD *)this;
        v34 = 0;
        (*(void (__fastcall **)(CMetadataRDFReaderWriter *, __int64))(v19 + 128))(this, 1);
        goto LABEL_3;
      }
    }
    v10 = -2003292287;
LABEL_32:
    if ( !g_doStackCaptures )
      goto LABEL_3;
    v12 = v10;
LABEL_7:
    DoStackCapture(v12);
    goto LABEL_3;
  }
  v9 = (*(__int64 (__fastcall **)(RDFItem *, LARGE_INTEGER))(*(_QWORD *)v34 + 64LL))(v34, a3->hVal);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v17 = 1;
    goto LABEL_19;
  }
  if ( g_doStackCaptures )
    goto LABEL_6;
LABEL_3:
  if ( v34 )
    (**(void (__fastcall ***)(RDFItem *, __int64))v34)(v34, 1);
  return v10;
}

```

## disassembly

```asm
0x180002aa0  push    rbp
0x180002aa2  push    rbx
0x180002aa3  push    rsi
0x180002aa4  push    rdi
0x180002aa5  push    r12
0x180002aa7  push    r13
0x180002aa9  push    r14
0x180002aab  push    r15
0x180002aad  mov     rbp, rsp
0x180002ab0  sub     rsp, 68h
0x180002ab4  mov     rax, cs:__security_cookie
0x180002abb  xor     rax, rsp
0x180002abe  mov     [rbp+var_18], rax
0x180002ac2  mov     rsi, [rbp+arg_20]
0x180002ac6  mov     r14, r9
0x180002ac9  mov     r13, r8
0x180002acc  mov     r12d, edx
0x180002acf  xorps   xmm0, xmm0
0x180002ad2  mov     [rbp+var_30], rsi
0x180002ad6  lea     r9, [rbp+var_40]; int *
0x180002ada  mov     [rbp+var_38], rsi
0x180002ade  lea     r8, [rbp+var_28]; struct _GUID *
0x180002ae2  mov     [rbp+var_48], 0
0x180002aea  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT **
0x180002aee  mov     [rbp+var_40], 0
0x180002af5  movups  xmmword ptr [rbp+var_28.Data1], xmm0
0x180002af9  mov     rdi, rcx
0x180002afc  call    ?CheckValidItemValue@CMetadataRDFReaderWriter@@IEAAJPEAPEBUtagPROPVARIANT@@PEAU_GUID@@PEAH@Z; CMetadataRDFReaderWriter::CheckValidItemValue(tagPROPVARIANT const * *,_GUID *,int *)
0x180002b01  mov     ebx, eax
0x180002b03  test    eax, eax
0x180002b05  jns     short loc_180002B45
0x180002b07  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180002b0e  jnz     short loc_180002B3C
0x180002b10  mov     rcx, [rbp+var_48]
0x180002b14  test    rcx, rcx
0x180002b17  jnz     loc_180002FBE
0x180002b1d  mov     eax, ebx
0x180002b1f  mov     rcx, [rbp+var_18]
0x180002b23  xor     rcx, rsp; StackCookie
0x180002b26  call    __security_check_cookie
0x180002b2b  add     rsp, 68h
0x180002b2f  pop     r15
0x180002b31  pop     r14
0x180002b33  pop     r13
0x180002b35  pop     r12
0x180002b37  pop     rdi
0x180002b38  pop     rsi
0x180002b39  pop     rbx
0x180002b3a  pop     rbp
0x180002b3b  retn
0x180002b3c  mov     ecx, eax; int
0x180002b3e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180002b43  jmp     short loc_180002B10
0x180002b45  mov     rax, [rdi]
0x180002b48  lea     rdx, [rbp+var_48]
0x180002b4c  mov     rcx, rdi
0x180002b4f  mov     rax, [rax+180h]
0x180002b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b5b  mov     ebx, eax
0x180002b5d  test    eax, eax
0x180002b5f  js      short loc_180002B07
0x180002b61  mov     rcx, [rbp+var_48]; this
0x180002b65  mov     rdx, rsi; struct tagPROPVARIANT *
0x180002b68  call    ?SetPropVariantValue@RDFItem@@QEAAJPEBUtagPROPVARIANT@@@Z; RDFItem::SetPropVariantValue(tagPROPVARIANT const *)
0x180002b6d  mov     ebx, eax
0x180002b6f  test    eax, eax
0x180002b71  js      short loc_180002B07
0x180002b73  mov     rcx, [rbp+var_48]
0x180002b77  mov     edx, [rbp+var_40]
0x180002b7a  mov     eax, [rcx+8]
0x180002b7d  test    edx, edx
0x180002b7f  jz      loc_180002C85
0x180002b85  or      eax, 4
0x180002b88  mov     [rcx+8], eax
0x180002b8b  mov     rax, [rbp+var_48]
0x180002b8f  or      dword ptr [rax+8], 8
0x180002b93  mov     rax, [rbp+var_48]
0x180002b97  or      dword ptr [rax+8], 1
0x180002b9b  mov     rcx, [rbp+var_48]; this
0x180002b9f  test    edx, edx
0x180002ba1  jz      loc_180002C8D
0x180002ba7  lea     rdx, [rbp+var_28]; struct _GUID *
0x180002bab  call    ?SetEmbeddedMetadataGUID@RDFItem@@QEAAJAEBU_GUID@@@Z; RDFItem::SetEmbeddedMetadataGUID(_GUID const &)
0x180002bb0  mov     ebx, eax
0x180002bb2  test    eax, eax
0x180002bb4  jns     short loc_180002BCB
0x180002bb6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180002bbd  jnz     loc_180002B3C
0x180002bc3  test    eax, eax
0x180002bc5  js      loc_180002B10
0x180002bcb  xor     esi, esi
0x180002bcd  xor     r15d, r15d
0x180002bd0  test    r14, r14
0x180002bd3  jz      short loc_180002BE2
0x180002bd5  lea     eax, [rsi+1Fh]
0x180002bd8  cmp     [r14], ax
0x180002bdc  jz      loc_180002F75
0x180002be2  mov     rax, [rdi]
0x180002be5  mov     rcx, rdi
0x180002be8  mov     rax, [rax+110h]
0x180002bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf4  test    eax, eax
0x180002bf6  jz      loc_180002F87
0x180002bfc  lea     rsi, [rdi+0D0h]
0x180002c03  cmp     r12d, [rsi+18h]
0x180002c07  jnz     loc_180002E4E
0x180002c0d  mov     rax, [rdi]
0x180002c10  mov     rcx, rdi
0x180002c13  mov     rax, [rax+118h]
0x180002c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c1f  test    eax, eax
0x180002c21  jz      short loc_180002C97
0x180002c23  cmp     [rbp+var_40], 0
0x180002c27  mov     rdx, [rbp+var_48]; struct RDFItem *
0x180002c2b  jnz     loc_180002FA6
0x180002c31  mov     r8d, 1; int
0x180002c37  mov     rcx, rdi; this
0x180002c3a  call    ?ApplyItemToDOM@CMetadataRDFReaderWriter@@IEAAJPEAVRDFItem@@H@Z; CMetadataRDFReaderWriter::ApplyItemToDOM(RDFItem *,int)
0x180002c3f  mov     ebx, eax
0x180002c41  test    eax, eax
0x180002c43  js      loc_180002B07
0x180002c49  lea     rdx, [rbp+var_48]
0x180002c4d  mov     rcx, rsi
0x180002c50  call    ?Add@?$CMILObjectArray@PEAVRDFItem@@@@QEAAJAEAPEAVRDFItem@@@Z; CMILObjectArray<RDFItem *>::Add(RDFItem * &)
0x180002c55  mov     ebx, eax
0x180002c57  test    eax, eax
0x180002c59  js      short loc_180002CC2
0x180002c5b  inc     dword ptr [rdi+0ACh]
0x180002c61  mov     rax, [rdi]
0x180002c64  mov     edx, 1
0x180002c69  mov     rcx, rdi
0x180002c6c  mov     [rbp+var_48], 0
0x180002c74  mov     rax, [rax+80h]
0x180002c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c80  jmp     loc_180002B10
0x180002c85  and     eax, 0FFFFFFFBh
0x180002c88  jmp     loc_180002B88
0x180002c8d  call    ?ClearEmbeddedMetadataGUID@RDFItem@@QEAAJXZ; RDFItem::ClearEmbeddedMetadataGUID(void)
0x180002c92  jmp     loc_180002BB0
0x180002c97  mov     rcx, [rbp+var_30]
0x180002c9b  mov     eax, 0Dh
0x180002ca0  cmp     ax, [rcx]
0x180002ca3  jnz     loc_180002F99
0x180002ca9  mov     ebx, 88982F81h
0x180002cae  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180002cb5  jz      loc_180002B10
0x180002cbb  mov     ecx, ebx
0x180002cbd  jmp     loc_180002B3E
0x180002cc2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180002cc9  jnz     loc_180002B3C
0x180002ccf  test    eax, eax
0x180002cd1  js      loc_180002B10
0x180002cd7  jmp     short loc_180002C5B
0x180002cd9  mov     rcx, [rbp+var_48]
0x180002cdd  mov     rax, [rcx]
0x180002ce0  mov     rax, [rax+28h]
0x180002ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ce9  mov     ebx, eax
0x180002ceb  test    eax, eax
0x180002ced  jns     short loc_180002D03
0x180002cef  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180002cf5  jnz     loc_180002B3C
0x180002cfb  test    eax, eax
0x180002cfd  js      loc_180002B10
0x180002d03  mov     r14d, 1
0x180002d09  mov     esi, r14d
0x180002d0c  test    r13, r13
0x180002d0f  jz      loc_180002BE2
0x180002d15  lea     eax, [r14+1Eh]
0x180002d19  cmp     ax, [r13+0]
0x180002d1e  jnz     loc_180002BE2
0x180002d24  mov     rcx, [rbp+var_48]
0x180002d28  mov     rdx, [r13+8]
0x180002d2c  mov     rax, [rcx]
0x180002d2f  mov     rax, [rax+40h]
0x180002d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d38  mov     ebx, eax
0x180002d3a  test    eax, eax
0x180002d3c  jns     short loc_180002D53
0x180002d3e  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180002d45  jnz     loc_180002B3C
0x180002d4b  test    eax, eax
0x180002d4d  js      loc_180002B10
0x180002d53  mov     r15d, r14d
0x180002d56  jmp     loc_180002BE2
0x180002d5b  lfence
0x180002d5e  mov     rax, [rdi+0D0h]
0x180002d65  mov     rcx, [rax+r12*8]
0x180002d69  test    byte ptr [rcx+8], 2
0x180002d6d  jnz     short loc_180002DDE
0x180002d6f  lfence
0x180002d72  mov     rax, [rdi+0D0h]
0x180002d79  mov     r14, [rax+r12*8]
0x180002d7d  test    esi, esi
0x180002d7f  jz      short loc_180002DF0
0x180002d81  test    r15d, r15d
0x180002d84  jnz     loc_180002BFC
0x180002d8a  mov     rax, [r14]
0x180002d8d  lea     rdx, [rbp+var_38]
0x180002d91  mov     rcx, r14
0x180002d94  mov     [rbp+var_38], 0
0x180002d9c  mov     rax, [rax+30h]
0x180002da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da5  mov     ebx, eax
0x180002da7  test    eax, eax
0x180002da9  js      loc_180002B07
0x180002daf  mov     rcx, [rbp+var_48]
0x180002db3  mov     rdx, [rbp+var_38]
0x180002db7  mov     rax, [rcx]
0x180002dba  mov     rax, [rax+40h]
0x180002dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dc3  mov     ebx, eax
0x180002dc5  test    eax, eax
0x180002dc7  jns     short loc_180002DDE
0x180002dc9  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180002dd0  jnz     loc_180002B3C
0x180002dd6  test    eax, eax
0x180002dd8  js      loc_180002B10
0x180002dde  test    esi, esi
0x180002de0  jnz     loc_180002BFC
0x180002de6  mov     ebx, 80070057h
0x180002deb  jmp     loc_180002CAE
0x180002df0  mov     rax, [r14]
0x180002df3  lea     rdx, [rbp+var_38]
0x180002df7  mov     rcx, r14
0x180002dfa  mov     [rbp+var_38], 0
0x180002e02  mov     rax, [rax+18h]
0x180002e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e0b  mov     ebx, eax
0x180002e0d  test    eax, eax
0x180002e0f  js      loc_180002B07
0x180002e15  mov     rcx, [rbp+var_48]
0x180002e19  mov     rdx, [rbp+var_38]
0x180002e1d  mov     rax, [rcx]
0x180002e20  mov     rax, [rax+28h]
0x180002e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e29  mov     ebx, eax
0x180002e2b  test    eax, eax
0x180002e2d  jns     short loc_180002E44
0x180002e2f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180002e36  jnz     loc_180002B3C
0x180002e3c  test    eax, eax
0x180002e3e  js      loc_180002B10
0x180002e44  mov     esi, 1
0x180002e49  jmp     loc_180002D81
0x180002e4e  mov     rcx, [rsi]
0x180002e51  mov     rax, [rcx+r12*8]
0x180002e55  test    byte ptr [rax+8], 2
0x180002e59  jz      short loc_180002E61
0x180002e5b  inc     dword ptr [rdi+0ACh]
0x180002e61  mov     rax, [rcx+r12*8]
0x180002e65  mov     r8, [rbp+var_48]
0x180002e69  mov     ecx, [rax+8]
0x180002e6c  mov     edx, [r8+8]
0x180002e70  mov     eax, edx
0x180002e72  and     eax, 0FFFFFFEFh
0x180002e75  or      edx, 10h
0x180002e78  test    cl, 10h
0x180002e7b  mov     rcx, [rbp+var_30]
0x180002e7f  cmovz   edx, eax
0x180002e82  mov     eax, 0Dh
0x180002e87  mov     [r8+8], edx
0x180002e8b  cmp     ax, [rcx]
0x180002e8e  jnz     short loc_180002E9E
0x180002e90  mov     rax, [rbp+var_48]
0x180002e94  test    byte ptr [rax+8], 10h
0x180002e98  jnz     loc_180002CA9
0x180002e9e  mov     rax, [rsi]
0x180002ea1  mov     r13, [rbp+var_48]
0x180002ea5  mov     rcx, [rax+r12*8]
0x180002ea9  mov     r15, [rcx+10h]
0x180002ead  mov     rcx, [r13+10h]
0x180002eb1  test    rcx, rcx
0x180002eb4  jz      short loc_180002EC2
0x180002eb6  mov     rax, [rcx]
0x180002eb9  mov     rax, [rax+10h]
0x180002ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ec2  mov     [r13+10h], r15
0x180002ec6  test    r15, r15
0x180002ec9  jz      short loc_180002EDA
0x180002ecb  mov     rax, [r15]
0x180002ece  mov     rcx, r15
0x180002ed1  mov     rax, [rax+8]
0x180002ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eda  mov     rax, [rsi]
0x180002edd  mov     r13, [rbp+var_48]
0x180002ee1  mov     rcx, [rax+r12*8]
0x180002ee5  mov     r15, [rcx+18h]
0x180002ee9  mov     rcx, [r13+18h]
0x180002eed  test    rcx, rcx
0x180002ef0  jz      short loc_180002EFE
0x180002ef2  mov     rax, [rcx]
0x180002ef5  mov     rax, [rax+10h]
0x180002ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002efe  mov     [r13+18h], r15
0x180002f02  test    r15, r15
0x180002f05  jz      short loc_180002F16
0x180002f07  mov     rax, [r15]
0x180002f0a  mov     rcx, r15
0x180002f0d  mov     rax, [rax+8]
  ... truncated ...
```
