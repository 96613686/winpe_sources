# _UpdateUnsignedRationalVectorPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x1800213f0`
- end: `0x18002154d`
- name: `?_UpdateUnsignedRationalVectorPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z`
- size: `349`
- prototype: `int(struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800141ec`

## callees

- `0x180021098`
- `0x180021340`
- `0x1800213f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800214ff`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002150f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002151f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800214ff`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002150f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002151f`

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
0x1800213f0  mov     [rsp-40h+arg_0], rcx
0x1800213f5  push    rbp
0x1800213f6  push    rbx
0x1800213f7  push    rsi
0x1800213f8  push    rdi
0x1800213f9  push    r12
0x1800213fb  push    r13
0x1800213fd  push    r14
0x1800213ff  push    r15
0x180021401  mov     rbp, rsp
0x180021404  sub     rsp, 78h
0x180021408  xor     r12d, r12d
0x18002140b  xor     r14d, r14d
0x18002140e  mov     r15, r8
0x180021411  mov     r13, rdx
0x180021414  mov     rax, rcx
0x180021417  mov     ebx, 88982F91h
0x18002141c  test    rdx, rdx
0x18002141f  jz      short loc_180021425
0x180021421  mov     r12d, [rdx+8]
0x180021425  test    r15, r15
0x180021428  jz      short loc_18002142E
0x18002142a  mov     r14d, [r8+8]
0x18002142e  cmp     r12d, r14d
0x180021431  mov     esi, r12d
0x180021434  cmovbe  esi, r14d
0x180021438  cmp     [rcx+8], esi
0x18002143b  jb      loc_180021539
0x180021441  xor     ebx, ebx
0x180021443  xor     edi, edi
0x180021445  test    esi, esi
0x180021447  jz      loc_180021539
0x18002144d  test    ebx, ebx
0x18002144f  js      loc_180021539
0x180021455  mov     rax, [rax+10h]
0x180021459  xor     ecx, ecx
0x18002145b  mov     qword ptr [rbp+var_58+10h], rcx
0x18002145f  xorps   xmm0, xmm0
0x180021462  mov     qword ptr [rbp+var_28+10h], rcx
0x180021466  xorps   xmm1, xmm1
0x180021469  mov     qword ptr [rbp+pvar+10h], rcx
0x18002146d  mov     ecx, 14h
0x180021472  movups  xmmword ptr [rbp+var_58], xmm0
0x180021476  mov     word ptr [rbp+var_58], cx
0x18002147a  movups  xmmword ptr [rbp+var_28], xmm1
0x18002147e  movups  xmmword ptr [rbp+pvar], xmm0
0x180021482  mov     rcx, [rax+rdi*8]
0x180021486  mov     qword ptr [rbp+var_58+8], rcx
0x18002148a  cmp     edi, r12d
0x18002148d  jnb     short loc_1800214A3
0x18002148f  lea     r8, [rbp+var_28]; struct tagPROPVARIANT *
0x180021493  mov     edx, edi; unsigned int
0x180021495  mov     rcx, r13; struct tagPROPVARIANT *
0x180021498  call    ?_ConstructPropvarFromVectorElement@@YAJPEBUtagPROPVARIANT@@KPEAU1@@Z; _ConstructPropvarFromVectorElement(tagPROPVARIANT const *,ulong,tagPROPVARIANT *)
0x18002149d  mov     ebx, eax
0x18002149f  test    eax, eax
0x1800214a1  js      short loc_1800214FB
0x1800214a3  cmp     edi, r14d
0x1800214a6  jnb     short loc_1800214BC
0x1800214a8  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x1800214ac  mov     edx, edi; unsigned int
0x1800214ae  mov     rcx, r15; struct tagPROPVARIANT *
0x1800214b1  call    ?_ConstructPropvarFromVectorElement@@YAJPEBUtagPROPVARIANT@@KPEAU1@@Z; _ConstructPropvarFromVectorElement(tagPROPVARIANT const *,ulong,tagPROPVARIANT *)
0x1800214b6  mov     ebx, eax
0x1800214b8  test    eax, eax
0x1800214ba  js      short loc_1800214FB
0x1800214bc  mov     rax, r15
0x1800214bf  lea     rcx, [rbp+var_58]; struct tagPROPVARIANT *
0x1800214c3  neg     rax
0x1800214c6  lea     rax, [rbp+pvar]
0x1800214ca  sbb     r8, r8
0x1800214cd  and     r8, rax; struct tagPROPVARIANT *
0x1800214d0  mov     rax, r13
0x1800214d3  neg     rax
0x1800214d6  lea     rax, [rbp+var_28]
0x1800214da  sbb     rdx, rdx
0x1800214dd  and     rdx, rax; struct tagPROPVARIANT *
0x1800214e0  call    ?_UpdateUnsignedRationalPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z; _UpdateUnsignedRationalPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x1800214e5  mov     ebx, eax
0x1800214e7  test    eax, eax
0x1800214e9  js      short loc_1800214FB
0x1800214eb  mov     rcx, [rbp+arg_0]
0x1800214ef  mov     rax, qword ptr [rbp+var_58+8]
0x1800214f3  mov     rcx, [rcx+10h]
0x1800214f7  mov     [rcx+rdi*8], rax
0x1800214fb  lea     rcx, [rbp+pvar]; pvar
0x1800214ff  call    cs:__imp_PropVariantClear
0x180021506  nop     dword ptr [rax+rax+00h]
0x18002150b  lea     rcx, [rbp+var_28]; pvar
0x18002150f  call    cs:__imp_PropVariantClear
0x180021516  nop     dword ptr [rax+rax+00h]
0x18002151b  lea     rcx, [rbp+var_58]; pvar
0x18002151f  call    cs:__imp_PropVariantClear
0x180021526  nop     dword ptr [rax+rax+00h]
0x18002152b  mov     rax, [rbp+arg_0]
0x18002152f  inc     edi
0x180021531  cmp     edi, esi
0x180021533  jb      loc_18002144D
0x180021539  mov     eax, ebx
0x18002153b  add     rsp, 78h
0x18002153f  pop     r15
0x180021541  pop     r14
0x180021543  pop     r13
0x180021545  pop     r12
0x180021547  pop     rdi
0x180021548  pop     rsi
0x180021549  pop     rbx
0x18002154a  pop     rbp
0x18002154b  retn
```
