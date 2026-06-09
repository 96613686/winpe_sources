# _UpdateSignedRationalVectorPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x1800201f4`
- end: `0x18002033e`
- name: `?_UpdateSignedRationalVectorPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z`
- size: `330`
- prototype: `int(struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001384c`

## callees

- `0x1800200bc`
- `0x180020150`
- `0x1800201f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020303`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002030d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020317`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020303`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002030d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020317`

## pseudocode

```c
__int64 __fastcall _UpdateSignedRationalVectorPropvar(
        struct tagPROPVARIANT *a1,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3)
{
  unsigned int ulVal; // r12d
  unsigned int v4; // r14d
  struct tagPROPVARIANT *v7; // rax
  int updated; // ebx
  unsigned int v9; // esi
  __int64 v10; // rdi
  BYTE *pData; // rax
  PROPVARIANT v13; // [rsp+20h] [rbp-58h] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-40h] BYREF
  PROPVARIANT v15; // [rsp+50h] [rbp-28h] BYREF

  ulVal = 0;
  v4 = 0;
  v7 = a1;
  updated = -2003292271;
  if ( a2 )
    ulVal = a2->ulVal;
  if ( a3 )
    v4 = a3->ulVal;
  v9 = ulVal;
  if ( ulVal <= v4 )
    v9 = v4;
  if ( a1->lVal >= v9 )
  {
    updated = 0;
    v10 = 0;
    while ( (unsigned int)v10 < v9 )
    {
      if ( updated < 0 )
        break;
      pData = v7->bstrblobVal.pData;
      memset(&v13, 0, sizeof(v13));
      v13.vt = 20;
      memset(&v15, 0, sizeof(v15));
      memset(&pvar, 0, sizeof(pvar));
      v13.hVal.QuadPart = *(_QWORD *)&pData[8 * v10];
      if ( (unsigned int)v10 < ulVal )
      {
        updated = _ConstructPropvarFromVectorElement(a2, v10, &v15);
        if ( updated < 0 )
          continue;
      }
      if ( (unsigned int)v10 >= v4 || (updated = _ConstructPropvarFromVectorElement(a3, v10, &pvar), updated >= 0) )
      {
        updated = _UpdateSignedRationalPropvar(
                    &v13,
                    (const struct tagPROPVARIANT *)((unsigned __int64)&v15 & -(__int64)(a2 != 0)),
                    (const struct tagPROPVARIANT *)((unsigned __int64)&pvar & -(__int64)(a3 != 0)));
        if ( updated >= 0 )
          *(_QWORD *)&a1->bstrblobVal.pData[8 * v10] = v13.hVal.QuadPart;
      }
      PropVariantClear(&pvar);
      PropVariantClear(&v15);
      PropVariantClear(&v13);
      v7 = a1;
      v10 = (unsigned int)(v10 + 1);
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800201f4  mov     [rsp-40h+arg_0], rcx
0x1800201f9  push    rbp
0x1800201fa  push    rbx
0x1800201fb  push    rsi
0x1800201fc  push    rdi
0x1800201fd  push    r12
0x1800201ff  push    r13
0x180020201  push    r14
0x180020203  push    r15
0x180020205  mov     rbp, rsp
0x180020208  sub     rsp, 78h
0x18002020c  xor     r12d, r12d
0x18002020f  xor     r14d, r14d
0x180020212  mov     r15, r8
0x180020215  mov     r13, rdx
0x180020218  mov     rax, rcx
0x18002021b  mov     ebx, 88982F91h
0x180020220  test    rdx, rdx
0x180020223  jz      short loc_180020229
0x180020225  mov     r12d, [rdx+8]
0x180020229  test    r15, r15
0x18002022c  jz      short loc_180020232
0x18002022e  mov     r14d, [r8+8]
0x180020232  cmp     r12d, r14d
0x180020235  mov     esi, r12d
0x180020238  cmovbe  esi, r14d
0x18002023c  cmp     [rcx+8], esi
0x18002023f  jb      loc_18002032B
0x180020245  xor     ebx, ebx
0x180020247  xor     edi, edi
0x180020249  test    esi, esi
0x18002024b  jz      loc_18002032B
0x180020251  test    ebx, ebx
0x180020253  js      loc_18002032B
0x180020259  mov     rax, [rax+10h]
0x18002025d  xor     ecx, ecx
0x18002025f  mov     qword ptr [rbp+var_58+10h], rcx
0x180020263  xorps   xmm0, xmm0
0x180020266  mov     qword ptr [rbp+var_28+10h], rcx
0x18002026a  xorps   xmm1, xmm1
0x18002026d  mov     qword ptr [rbp+pvar+10h], rcx
0x180020271  mov     ecx, 14h
0x180020276  movups  xmmword ptr [rbp+var_58], xmm0
0x18002027a  mov     word ptr [rbp+var_58], cx
0x18002027e  movups  xmmword ptr [rbp+var_28], xmm1
0x180020282  movups  xmmword ptr [rbp+pvar], xmm0
0x180020286  mov     rcx, [rax+rdi*8]
0x18002028a  mov     qword ptr [rbp+var_58+8], rcx
0x18002028e  cmp     edi, r12d
0x180020291  jnb     short loc_1800202A7
0x180020293  lea     r8, [rbp+var_28]; struct tagPROPVARIANT *
0x180020297  mov     edx, edi; unsigned int
0x180020299  mov     rcx, r13; struct tagPROPVARIANT *
0x18002029c  call    ?_ConstructPropvarFromVectorElement@@YAJPEBUtagPROPVARIANT@@KPEAU1@@Z; _ConstructPropvarFromVectorElement(tagPROPVARIANT const *,ulong,tagPROPVARIANT *)
0x1800202a1  mov     ebx, eax
0x1800202a3  test    eax, eax
0x1800202a5  js      short loc_1800202FF
0x1800202a7  cmp     edi, r14d
0x1800202aa  jnb     short loc_1800202C0
0x1800202ac  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x1800202b0  mov     edx, edi; unsigned int
0x1800202b2  mov     rcx, r15; struct tagPROPVARIANT *
0x1800202b5  call    ?_ConstructPropvarFromVectorElement@@YAJPEBUtagPROPVARIANT@@KPEAU1@@Z; _ConstructPropvarFromVectorElement(tagPROPVARIANT const *,ulong,tagPROPVARIANT *)
0x1800202ba  mov     ebx, eax
0x1800202bc  test    eax, eax
0x1800202be  js      short loc_1800202FF
0x1800202c0  mov     rax, r15
0x1800202c3  lea     rcx, [rbp+var_58]; struct tagPROPVARIANT *
0x1800202c7  neg     rax
0x1800202ca  lea     rax, [rbp+pvar]
0x1800202ce  sbb     r8, r8
0x1800202d1  and     r8, rax; struct tagPROPVARIANT *
0x1800202d4  mov     rax, r13
0x1800202d7  neg     rax
0x1800202da  lea     rax, [rbp+var_28]
0x1800202de  sbb     rdx, rdx
0x1800202e1  and     rdx, rax; struct tagPROPVARIANT *
0x1800202e4  call    ?_UpdateSignedRationalPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z; _UpdateSignedRationalPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x1800202e9  mov     ebx, eax
0x1800202eb  test    eax, eax
0x1800202ed  js      short loc_1800202FF
0x1800202ef  mov     rcx, [rbp+arg_0]
0x1800202f3  mov     rax, qword ptr [rbp+var_58+8]
0x1800202f7  mov     rcx, [rcx+10h]
0x1800202fb  mov     [rcx+rdi*8], rax
0x1800202ff  lea     rcx, [rbp+pvar]; pvar
0x180020303  call    cs:__imp_PropVariantClear
0x180020309  lea     rcx, [rbp+var_28]; pvar
0x18002030d  call    cs:__imp_PropVariantClear
0x180020313  lea     rcx, [rbp+var_58]; pvar
0x180020317  call    cs:__imp_PropVariantClear
0x18002031d  mov     rax, [rbp+arg_0]
0x180020321  inc     edi
0x180020323  cmp     edi, esi
0x180020325  jb      loc_180020251
0x18002032b  mov     eax, ebx
0x18002032d  add     rsp, 78h
0x180020331  pop     r15
0x180020333  pop     r14
0x180020335  pop     r13
0x180020337  pop     r12
0x180020339  pop     rdi
0x18002033a  pop     rsi
0x18002033b  pop     rbx
0x18002033c  pop     rbp
0x18002033d  retn
```
