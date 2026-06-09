# CBinaryWriter::WriteVariantValue(tagPROPVARIANT const *)

- ea: `0x18005343c`
- end: `0x1800537ea`
- name: `?WriteVariantValue@CBinaryWriter@@QEAAJPEBUtagPROPVARIANT@@@Z`
- size: `942`
- prototype: `__int64 __fastcall(CBinaryWriter *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800533dc`

## callees

- `0x1800533dc`
- `0x18005343c`
- `0x18005a010`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x1800534df`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800534df`

## pseudocode

```c
__int64 __fastcall CBinaryWriter::WriteVariantValue(CBinaryWriter *this, const struct tagPROPVARIANT *a2)
{
  unsigned int vt; // r9d
  CBinaryWriter *v4; // rdi
  __int64 ulVal; // r8
  unsigned int v6; // r9d
  unsigned int v7; // r9d
  unsigned int v8; // r9d
  unsigned int v9; // r9d
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  unsigned int v12; // r9d
  unsigned int v13; // r9d
  void (__fastcall **v14)(CBinaryWriter *, void *, __int64); // rax
  void *pData; // rdx
  void (__fastcall **v16)(CBinaryWriter *, UINT *, __int64); // rax
  unsigned int v17; // r9d
  unsigned int v18; // r9d
  unsigned int v19; // r9d
  unsigned int v20; // r9d
  unsigned int v21; // r9d
  unsigned int v22; // r9d
  unsigned int v23; // r9d
  unsigned int v24; // r9d
  __int64 v25; // rbx
  UINT v26; // eax
  __int64 v27; // rbx
  unsigned int v28; // r9d
  unsigned int v29; // r9d
  unsigned int v30; // r9d
  unsigned int v31; // r9d
  unsigned int v32; // r9d
  unsigned int v33; // r9d
  LARGE_INTEGER *v34; // r14
  DWORD k; // ebx
  LARGE_INTEGER *v36; // rdx
  unsigned int LowPart; // ebx
  unsigned int v38; // r9d
  unsigned int v39; // r9d
  unsigned int v40; // r9d
  unsigned int v41; // r9d
  unsigned int v42; // r9d
  unsigned int v43; // r9d
  LARGE_INTEGER *p_hVal; // r14
  DWORD i; // r15d
  BYTE *v46; // rbx
  LARGE_INTEGER *v47; // r14
  DWORD j; // r15d
  __int64 v49; // r12
  __int64 v50; // rax
  UINT v52; // [rsp+78h] [rbp+50h] BYREF

  vt = a2->vt;
  v52 = 0;
  v4 = this;
  if ( vt > 0x40 )
  {
    if ( vt > 0x1010 )
    {
      v38 = vt - 4113;
      if ( v38 )
      {
        v39 = v38 - 1;
        if ( v39 )
        {
          v40 = v39 - 1;
          if ( v40 )
          {
            v41 = v40 - 1;
            if ( v41 )
            {
              v42 = v41 - 1;
              if ( v42 )
              {
                v43 = v42 - 10;
                if ( v43 )
                {
                  if ( v43 == 34 )
                  {
                    p_hVal = &a2->hVal;
                    (**(void (__fastcall ***)(CBinaryWriter *, ULONG *, __int64))this)(this, &a2->ulVal, 4);
                    for ( i = 0; i < p_hVal->LowPart; ++i )
                    {
                      v46 = &a2->bstrblobVal.pData[16 * i];
                      (**(void (__fastcall ***)(CBinaryWriter *, BYTE *, __int64))v4)(v4, v46, 4);
                      (**(void (__fastcall ***)(CBinaryWriter *, _QWORD, _QWORD))v4)(
                        v4,
                        *((_QWORD *)v46 + 1),
                        *(unsigned int *)v46);
                    }
                  }
                }
                else
                {
                  v47 = &a2->hVal;
                  (**(void (__fastcall ***)(CBinaryWriter *, ULONG *, __int64))this)(this, &a2->ulVal, 4);
                  for ( j = 0; j < v47->LowPart; ++j )
                  {
                    v49 = *(_QWORD *)&a2->bstrblobVal.pData[8 * j];
                    v50 = -1;
                    do
                      ++v50;
                    while ( *(_WORD *)(v49 + 2 * v50) );
                    v52 = 2 * v50 + 2;
                    (**(void (__fastcall ***)(CBinaryWriter *, UINT *, __int64))v4)(v4, &v52, 4);
                    (**(void (__fastcall ***)(CBinaryWriter *, __int64, _QWORD))v4)(v4, v49, v52);
                  }
                }
                return 0;
              }
            }
            goto LABEL_48;
          }
LABEL_49:
          v36 = &a2->hVal;
          LowPart = 4 * v36->LowPart;
          goto LABEL_69;
        }
LABEL_50:
        v36 = &a2->hVal;
        LowPart = 2 * v36->LowPart;
        goto LABEL_69;
      }
    }
    else if ( vt != 4112 )
    {
      v28 = vt - 65;
      if ( !v28 )
      {
        (**(void (__fastcall ***)(CBinaryWriter *, ULONG *, __int64))this)(this, &a2->ulVal, 4);
        ulVal = a2->ulVal;
LABEL_70:
        pData = a2->bstrblobVal.pData;
        goto LABEL_71;
      }
      v29 = v28 - 7;
      if ( !v29 )
      {
        v14 = *(void (__fastcall ***)(CBinaryWriter *, void *, __int64))this;
        ulVal = 16;
        pData = a2->puuid;
        goto LABEL_72;
      }
      v30 = v29 - 4026;
      if ( v30 )
      {
        v31 = v30 - 1;
        if ( v31 )
        {
          v32 = v31 - 1;
          if ( v32 )
          {
            v33 = v32 - 1;
            if ( v33 )
            {
              if ( v33 == 7 )
              {
                v34 = &a2->hVal;
                (**(void (__fastcall ***)(CBinaryWriter *, ULONG *, __int64))this)(this, &a2->ulVal, 4);
                for ( k = 0; v34->LowPart > k; ++k )
                  CBinaryWriter::WriteVariant(v4, (const struct tagPROPVARIANT *)&a2->bstrblobVal.pData[24 * k]);
              }
              return 0;
            }
LABEL_48:
            v36 = &a2->hVal;
            LowPart = 8 * v36->LowPart;
LABEL_69:
            (**(void (__fastcall ***)(CBinaryWriter *, LARGE_INTEGER *, __int64))this)(this, v36, 4);
            ulVal = LowPart;
            goto LABEL_70;
          }
        }
        goto LABEL_49;
      }
      goto LABEL_50;
    }
    v36 = &a2->hVal;
    LowPart = v36->LowPart;
    goto LABEL_69;
  }
  if ( vt == 64 )
    goto LABEL_18;
  ulVal = 2;
  if ( vt > 0x10 )
  {
    v17 = vt - 17;
    if ( !v17 )
      goto LABEL_35;
    v18 = v17 - 1;
    if ( !v18 )
      goto LABEL_14;
    v19 = v18 - 1;
    if ( !v19 )
      goto LABEL_15;
    v20 = v19 - 1;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( !v22 )
          goto LABEL_15;
        v23 = v22 - 1;
        if ( !v23 )
          goto LABEL_15;
        v24 = v23 - 7;
        if ( v24 )
        {
          if ( v24 != 1 )
            return 0;
          v25 = -1;
          do
            ++v25;
          while ( *(_WORD *)(a2->hVal.QuadPart + 2 * v25) );
          v26 = 2 * v25 + 2;
        }
        else
        {
          v27 = -1;
          do
            ++v27;
          while ( *(_BYTE *)(a2->hVal.QuadPart + v27) );
          v26 = v27 + 1;
        }
        v52 = v26;
        v16 = *(void (__fastcall ***)(CBinaryWriter *, UINT *, __int64))this;
        goto LABEL_17;
      }
    }
LABEL_18:
    v14 = *(void (__fastcall ***)(CBinaryWriter *, void *, __int64))this;
    pData = &a2->decVal.8;
    ulVal = 8;
    goto LABEL_72;
  }
  if ( vt == 16 )
  {
LABEL_35:
    v14 = *(void (__fastcall ***)(CBinaryWriter *, void *, __int64))this;
    pData = &a2->decVal.8;
    ulVal = 1;
    goto LABEL_72;
  }
  v6 = vt - 2;
  if ( !v6 )
  {
LABEL_14:
    v14 = *(void (__fastcall ***)(CBinaryWriter *, void *, __int64))this;
    pData = &a2->decVal.8;
LABEL_72:
    (*v14)(this, pData, ulVal);
    return 0;
  }
  v7 = v6 - 1;
  if ( !v7 || (v8 = v7 - 1) == 0 )
  {
LABEL_15:
    v14 = *(void (__fastcall ***)(CBinaryWriter *, void *, __int64))this;
    pData = &a2->decVal.8;
    ulVal = 4;
    goto LABEL_72;
  }
  v9 = v8 - 1;
  if ( !v9 )
    goto LABEL_18;
  v10 = v9 - 1;
  if ( !v10 )
    goto LABEL_18;
  v11 = v10 - 1;
  if ( !v11 )
    goto LABEL_18;
  v12 = v11 - 1;
  if ( !v12 )
  {
    v52 = SysStringByteLen(a2->bstrVal);
    this = v4;
    v16 = *(void (__fastcall ***)(CBinaryWriter *, UINT *, __int64))v4;
LABEL_17:
    (*v16)(this, &v52, 4);
    ulVal = v52;
    pData = a2->puuid;
LABEL_71:
    v14 = *(void (__fastcall ***)(CBinaryWriter *, void *, __int64))v4;
    this = v4;
    goto LABEL_72;
  }
  v13 = v12 - 2;
  if ( !v13 )
    goto LABEL_15;
  if ( v13 == 1 )
    goto LABEL_14;
  return 0;
}

```

## disassembly

```asm
0x18005343c  push    rbp
0x18005343e  push    rbx
0x18005343f  push    rsi
0x180053440  push    rdi
0x180053441  push    r12
0x180053443  push    r13
0x180053445  push    r14
0x180053447  push    r15
0x180053449  mov     rbp, rsp
0x18005344c  sub     rsp, 28h
0x180053450  movzx   r9d, word ptr [rdx]
0x180053454  xor     r13d, r13d
0x180053457  mov     [rbp+arg_8], r13d
0x18005345b  mov     rsi, rdx
0x18005345e  mov     rdi, rcx
0x180053461  cmp     r9d, 40h ; '@'
0x180053465  ja      loc_1800535A5
0x18005346b  jz      loc_18005350D
0x180053471  lea     r8d, [r13+2]
0x180053475  cmp     r9d, 10h
0x180053479  ja      loc_18005351F
0x18005347f  jz      loc_180053593
0x180053485  sub     r9d, r8d
0x180053488  jz      short loc_1800534BD
0x18005348a  sub     r9d, 1
0x18005348e  jz      short loc_1800534C9
0x180053490  sub     r9d, 1
0x180053494  jz      short loc_1800534C9
0x180053496  sub     r9d, 1
0x18005349a  jz      short loc_18005350D
0x18005349c  sub     r9d, 1
0x1800534a0  jz      short loc_18005350D
0x1800534a2  sub     r9d, 1
0x1800534a6  jz      short loc_18005350D
0x1800534a8  sub     r9d, 1
0x1800534ac  jz      short loc_1800534DB
0x1800534ae  sub     r9d, r8d
0x1800534b1  jz      short loc_1800534C9
0x1800534b3  cmp     r9d, 1
0x1800534b7  jnz     loc_1800537D7
0x1800534bd  mov     rax, [rcx]
0x1800534c0  add     rdx, 8
0x1800534c4  jmp     loc_1800537CF
0x1800534c9  mov     rax, [rcx]
0x1800534cc  add     rdx, 8
0x1800534d0  mov     r8d, 4
0x1800534d6  jmp     loc_1800537CF
0x1800534db  mov     rcx, [rdx+8]; bstr
0x1800534df  call    cs:__imp_SysStringByteLen
0x1800534e5  mov     [rbp+arg_8], eax
0x1800534e8  mov     rcx, rdi
0x1800534eb  mov     rax, [rdi]
0x1800534ee  mov     rax, [rax]
0x1800534f1  lea     rdx, [rbp+arg_8]
0x1800534f5  mov     r8d, 4
0x1800534fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053500  mov     r8d, [rbp+arg_8]
0x180053504  mov     rdx, [rsi+8]
0x180053508  jmp     loc_1800537C9
0x18005350d  mov     rax, [rcx]
0x180053510  add     rdx, 8
0x180053514  mov     r8d, 8
0x18005351a  jmp     loc_1800537CF
0x18005351f  sub     r9d, 11h
0x180053523  jz      short loc_180053593
0x180053525  sub     r9d, 1
0x180053529  jz      short loc_1800534BD
0x18005352b  sub     r9d, 1
0x18005352f  jz      short loc_1800534C9
0x180053531  sub     r9d, 1
0x180053535  jz      short loc_18005350D
0x180053537  sub     r9d, 1
0x18005353b  jz      short loc_18005350D
0x18005353d  sub     r9d, 1
0x180053541  jz      short loc_1800534C9
0x180053543  sub     r9d, 1
0x180053547  jz      short loc_1800534C9
0x180053549  sub     r9d, 7
0x18005354d  jz      short loc_18005357D
0x18005354f  cmp     r9d, 1
0x180053553  jnz     loc_1800537D7
0x180053559  mov     rax, [rdx+8]
0x18005355d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180053561  inc     rbx
0x180053564  cmp     [rax+rbx*2], r13w
0x180053569  jnz     short loc_180053561
0x18005356b  lea     eax, ds:2[rbx*2]
0x180053572  mov     [rbp+arg_8], eax
0x180053575  mov     rax, [rcx]
0x180053578  jmp     loc_1800534EE
0x18005357d  mov     rax, [rdx+8]
0x180053581  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180053585  inc     rbx
0x180053588  cmp     [rax+rbx], r13b
0x18005358c  jnz     short loc_180053585
0x18005358e  lea     eax, [rbx+1]
0x180053591  jmp     short loc_180053572
0x180053593  mov     rax, [rcx]
0x180053596  add     rdx, 8
0x18005359a  mov     r8d, 1
0x1800535a0  jmp     loc_1800537CF
0x1800535a5  mov     eax, 1010h
0x1800535aa  cmp     r9d, eax
0x1800535ad  ja      loc_18005368F
0x1800535b3  jz      loc_1800537AB
0x1800535b9  sub     r9d, 41h ; 'A'
0x1800535bd  jz      loc_180053671
0x1800535c3  sub     r9d, 7
0x1800535c7  jz      loc_18005365F
0x1800535cd  sub     r9d, 0FBAh
0x1800535d4  jz      short loc_180053652
0x1800535d6  sub     r9d, 1
0x1800535da  jz      short loc_180053644
0x1800535dc  sub     r9d, 1
0x1800535e0  jz      short loc_180053644
0x1800535e2  sub     r9d, 1
0x1800535e6  jz      short loc_180053636
0x1800535e8  cmp     r9d, 7
0x1800535ec  jnz     loc_1800537D7
0x1800535f2  mov     rax, [rcx]
0x1800535f5  lea     r14, [rdx+8]
0x1800535f9  lea     r8d, [r9-3]
0x1800535fd  mov     rdx, r14
0x180053600  mov     rax, [rax]
0x180053603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053608  mov     ebx, r13d
0x18005360b  cmp     [r14], r13d
0x18005360e  jbe     loc_1800537D7
0x180053614  mov     eax, ebx
0x180053616  lea     rcx, [rax+rax*2]
0x18005361a  mov     rax, [rsi+10h]
0x18005361e  lea     rdx, [rax+rcx*8]; struct tagPROPVARIANT *
0x180053622  mov     rcx, rdi; this
0x180053625  call    ?WriteVariant@CBinaryWriter@@QEAAJPEBUtagPROPVARIANT@@@Z; CBinaryWriter::WriteVariant(tagPROPVARIANT const *)
0x18005362a  inc     ebx
0x18005362c  cmp     [r14], ebx
0x18005362f  ja      short loc_180053614
0x180053631  jmp     loc_1800537D7
0x180053636  add     rdx, 8
0x18005363a  mov     ebx, [rdx]
0x18005363c  shl     ebx, 3
0x18005363f  jmp     loc_1800537B1
0x180053644  add     rdx, 8
0x180053648  mov     ebx, [rdx]
0x18005364a  shl     ebx, 2
0x18005364d  jmp     loc_1800537B1
0x180053652  add     rdx, 8
0x180053656  mov     ebx, [rdx]
0x180053658  add     ebx, ebx
0x18005365a  jmp     loc_1800537B1
0x18005365f  mov     rax, [rcx]
0x180053662  mov     r8d, 10h
0x180053668  mov     rdx, [rdx+8]
0x18005366c  jmp     loc_1800537CF
0x180053671  mov     rax, [rcx]
0x180053674  mov     r8d, 4
0x18005367a  add     rdx, 8
0x18005367e  mov     rax, [rax]
0x180053681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053686  mov     r8d, [rsi+8]
0x18005368a  jmp     loc_1800537C5
0x18005368f  sub     r9d, 1011h
0x180053696  jz      loc_1800537AB
0x18005369c  sub     r9d, 1
0x1800536a0  jz      short loc_180053652
0x1800536a2  sub     r9d, 1
0x1800536a6  jz      short loc_180053644
0x1800536a8  sub     r9d, 1
0x1800536ac  jz      short loc_180053636
0x1800536ae  sub     r9d, 1
0x1800536b2  jz      short loc_180053636
0x1800536b4  sub     r9d, 0Ah
0x1800536b8  jz      short loc_18005372A
0x1800536ba  cmp     r9d, 22h ; '"'
0x1800536be  jnz     loc_1800537D7
0x1800536c4  mov     rax, [rcx]
0x1800536c7  lea     r14, [rdx+8]
0x1800536cb  lea     r8d, [r9-1Eh]
0x1800536cf  mov     rdx, r14
0x1800536d2  mov     rax, [rax]
0x1800536d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536da  mov     r15d, r13d
0x1800536dd  cmp     [r14], r13d
0x1800536e0  jbe     loc_1800537D7
0x1800536e6  mov     rax, [rdi]
0x1800536e9  mov     r8d, 4
0x1800536ef  mov     ebx, r15d
0x1800536f2  mov     rcx, rdi
0x1800536f5  shl     rbx, 4
0x1800536f9  add     rbx, [rsi+10h]
0x1800536fd  mov     rax, [rax]
0x180053700  mov     rdx, rbx
0x180053703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053708  mov     rax, [rdi]
0x18005370b  mov     rcx, rdi
0x18005370e  mov     r8d, [rbx]
0x180053711  mov     rdx, [rbx+8]
0x180053715  mov     rax, [rax]
0x180053718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005371d  inc     r15d
0x180053720  cmp     r15d, [r14]
0x180053723  jb      short loc_1800536E6
0x180053725  jmp     loc_1800537D7
0x18005372a  mov     rax, [rcx]
0x18005372d  lea     r14, [rdx+8]
0x180053731  mov     r8d, 4
0x180053737  mov     rdx, r14
0x18005373a  mov     rax, [rax]
0x18005373d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053742  mov     r15d, r13d
0x180053745  cmp     [r14], r13d
0x180053748  jbe     loc_1800537D7
0x18005374e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180053752  mov     rax, [rsi+10h]
0x180053756  mov     ecx, r15d
0x180053759  mov     r12, [rax+rcx*8]
0x18005375d  mov     rax, rbx
0x180053760  inc     rax
0x180053763  cmp     [r12+rax*2], r13w
0x180053768  jnz     short loc_180053760
0x18005376a  lea     eax, ds:2[rax*2]
0x180053771  mov     r8d, 4
0x180053777  mov     [rbp+arg_8], eax
0x18005377a  lea     rdx, [rbp+arg_8]
0x18005377e  mov     rax, [rdi]
0x180053781  mov     rcx, rdi
0x180053784  mov     rax, [rax]
0x180053787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005378c  mov     rax, [rdi]
0x18005378f  mov     rdx, r12
0x180053792  mov     r8d, [rbp+arg_8]
0x180053796  mov     rcx, rdi
0x180053799  mov     rax, [rax]
0x18005379c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537a1  inc     r15d
0x1800537a4  cmp     r15d, [r14]
0x1800537a7  jb      short loc_180053752
0x1800537a9  jmp     short loc_1800537D7
0x1800537ab  add     rdx, 8
0x1800537af  mov     ebx, [rdx]
0x1800537b1  mov     rax, [rcx]
0x1800537b4  mov     r8d, 4
0x1800537ba  mov     rax, [rax]
0x1800537bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537c2  mov     r8d, ebx
0x1800537c5  mov     rdx, [rsi+10h]
0x1800537c9  mov     rax, [rdi]
0x1800537cc  mov     rcx, rdi
0x1800537cf  mov     rax, [rax]
0x1800537d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537d7  xor     eax, eax
0x1800537d9  add     rsp, 28h
0x1800537dd  pop     r15
0x1800537df  pop     r14
0x1800537e1  pop     r13
0x1800537e3  pop     r12
0x1800537e5  pop     rdi
0x1800537e6  pop     rsi
0x1800537e7  pop     rbx
0x1800537e8  pop     rbp
0x1800537e9  retn
```
