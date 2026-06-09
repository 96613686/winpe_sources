# _UpdateUnsignedRationalVectorPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x1800203e8`
- end: `0x180020532`
- name: `?_UpdateUnsignedRationalVectorPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z`
- size: `330`
- prototype: `int(struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001384c`

## callees

- `0x1800200bc`
- `0x180020344`
- `0x1800203e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800204f7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020501`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002050b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800204f7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020501`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002050b`

## pseudocode

```c
__int64 __fastcall _UpdateUnsignedRationalVectorPropvar(
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
        updated = _UpdateUnsignedRationalPropvar(
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
0x1800203e8  mov     [rsp-40h+arg_0], rcx
0x1800203ed  push    rbp
0x1800203ee  push    rbx
0x1800203ef  push    rsi
0x1800203f0  push    rdi
0x1800203f1  push    r12
0x1800203f3  push    r13
0x1800203f5  push    r14
0x1800203f7  push    r15
0x1800203f9  mov     rbp, rsp
0x1800203fc  sub     rsp, 78h
0x180020400  xor     r12d, r12d
0x180020403  xor     r14d, r14d
0x180020406  mov     r15, r8
0x180020409  mov     r13, rdx
0x18002040c  mov     rax, rcx
0x18002040f  mov     ebx, 88982F91h
0x180020414  test    rdx, rdx
0x180020417  jz      short loc_18002041D
0x180020419  mov     r12d, [rdx+8]
0x18002041d  test    r15, r15
0x180020420  jz      short loc_180020426
0x180020422  mov     r14d, [r8+8]
0x180020426  cmp     r12d, r14d
0x180020429  mov     esi, r12d
0x18002042c  cmovbe  esi, r14d
0x180020430  cmp     [rcx+8], esi
0x180020433  jb      loc_18002051F
0x180020439  xor     ebx, ebx
0x18002043b  xor     edi, edi
0x18002043d  test    esi, esi
0x18002043f  jz      loc_18002051F
0x180020445  test    ebx, ebx
0x180020447  js      loc_18002051F
0x18002044d  mov     rax, [rax+10h]
0x180020451  xor     ecx, ecx
0x180020453  mov     qword ptr [rbp+var_58+10h], rcx
0x180020457  xorps   xmm0, xmm0
0x18002045a  mov     qword ptr [rbp+var_28+10h], rcx
0x18002045e  xorps   xmm1, xmm1
0x180020461  mov     qword ptr [rbp+pvar+10h], rcx
0x180020465  mov     ecx, 14h
0x18002046a  movups  xmmword ptr [rbp+var_58], xmm0
0x18002046e  mov     word ptr [rbp+var_58], cx
0x180020472  movups  xmmword ptr [rbp+var_28], xmm1
0x180020476  movups  xmmword ptr [rbp+pvar], xmm0
0x18002047a  mov     rcx, [rax+rdi*8]
0x18002047e  mov     qword ptr [rbp+var_58+8], rcx
0x180020482  cmp     edi, r12d
0x180020485  jnb     short loc_18002049B
0x180020487  lea     r8, [rbp+var_28]; struct tagPROPVARIANT *
0x18002048b  mov     edx, edi; unsigned int
0x18002048d  mov     rcx, r13; struct tagPROPVARIANT *
0x180020490  call    ?_ConstructPropvarFromVectorElement@@YAJPEBUtagPROPVARIANT@@KPEAU1@@Z; _ConstructPropvarFromVectorElement(tagPROPVARIANT const *,ulong,tagPROPVARIANT *)
0x180020495  mov     ebx, eax
0x180020497  test    eax, eax
0x180020499  js      short loc_1800204F3
0x18002049b  cmp     edi, r14d
0x18002049e  jnb     short loc_1800204B4
0x1800204a0  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x1800204a4  mov     edx, edi; unsigned int
0x1800204a6  mov     rcx, r15; struct tagPROPVARIANT *
0x1800204a9  call    ?_ConstructPropvarFromVectorElement@@YAJPEBUtagPROPVARIANT@@KPEAU1@@Z; _ConstructPropvarFromVectorElement(tagPROPVARIANT const *,ulong,tagPROPVARIANT *)
0x1800204ae  mov     ebx, eax
0x1800204b0  test    eax, eax
0x1800204b2  js      short loc_1800204F3
0x1800204b4  mov     rax, r15
0x1800204b7  lea     rcx, [rbp+var_58]; struct tagPROPVARIANT *
0x1800204bb  neg     rax
0x1800204be  lea     rax, [rbp+pvar]
0x1800204c2  sbb     r8, r8
0x1800204c5  and     r8, rax; struct tagPROPVARIANT *
0x1800204c8  mov     rax, r13
0x1800204cb  neg     rax
0x1800204ce  lea     rax, [rbp+var_28]
0x1800204d2  sbb     rdx, rdx
0x1800204d5  and     rdx, rax; struct tagPROPVARIANT *
0x1800204d8  call    ?_UpdateUnsignedRationalPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z; _UpdateUnsignedRationalPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x1800204dd  mov     ebx, eax
0x1800204df  test    eax, eax
0x1800204e1  js      short loc_1800204F3
0x1800204e3  mov     rcx, [rbp+arg_0]
0x1800204e7  mov     rax, qword ptr [rbp+var_58+8]
0x1800204eb  mov     rcx, [rcx+10h]
0x1800204ef  mov     [rcx+rdi*8], rax
0x1800204f3  lea     rcx, [rbp+pvar]; pvar
0x1800204f7  call    cs:__imp_PropVariantClear
0x1800204fd  lea     rcx, [rbp+var_28]; pvar
0x180020501  call    cs:__imp_PropVariantClear
0x180020507  lea     rcx, [rbp+var_58]; pvar
0x18002050b  call    cs:__imp_PropVariantClear
0x180020511  mov     rax, [rbp+arg_0]
0x180020515  inc     edi
0x180020517  cmp     edi, esi
0x180020519  jb      loc_180020445
0x18002051f  mov     eax, ebx
0x180020521  add     rsp, 78h
0x180020525  pop     r15
0x180020527  pop     r14
0x180020529  pop     r13
0x18002052b  pop     r12
0x18002052d  pop     rdi
0x18002052e  pop     rsi
0x18002052f  pop     rbx
0x180020530  pop     rbp
0x180020531  retn
```
