# _UpdateSignedRationalVectorPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x1800211dc`
- end: `0x180021339`
- name: `?_UpdateSignedRationalVectorPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z`
- size: `349`
- prototype: `int(struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800141ec`

## callees

- `0x180021098`
- `0x18002112c`
- `0x1800211dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800212eb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800212fb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002130b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800212eb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800212fb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002130b`

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
0x1800211dc  mov     [rsp-40h+arg_0], rcx
0x1800211e1  push    rbp
0x1800211e2  push    rbx
0x1800211e3  push    rsi
0x1800211e4  push    rdi
0x1800211e5  push    r12
0x1800211e7  push    r13
0x1800211e9  push    r14
0x1800211eb  push    r15
0x1800211ed  mov     rbp, rsp
0x1800211f0  sub     rsp, 78h
0x1800211f4  xor     r12d, r12d
0x1800211f7  xor     r14d, r14d
0x1800211fa  mov     r15, r8
0x1800211fd  mov     r13, rdx
0x180021200  mov     rax, rcx
0x180021203  mov     ebx, 88982F91h
0x180021208  test    rdx, rdx
0x18002120b  jz      short loc_180021211
0x18002120d  mov     r12d, [rdx+8]
0x180021211  test    r15, r15
0x180021214  jz      short loc_18002121A
0x180021216  mov     r14d, [r8+8]
0x18002121a  cmp     r12d, r14d
0x18002121d  mov     esi, r12d
0x180021220  cmovbe  esi, r14d
0x180021224  cmp     [rcx+8], esi
0x180021227  jb      loc_180021325
0x18002122d  xor     ebx, ebx
0x18002122f  xor     edi, edi
0x180021231  test    esi, esi
0x180021233  jz      loc_180021325
0x180021239  test    ebx, ebx
0x18002123b  js      loc_180021325
0x180021241  mov     rax, [rax+10h]
0x180021245  xor     ecx, ecx
0x180021247  mov     qword ptr [rbp+var_58+10h], rcx
0x18002124b  xorps   xmm0, xmm0
0x18002124e  mov     qword ptr [rbp+var_28+10h], rcx
0x180021252  xorps   xmm1, xmm1
0x180021255  mov     qword ptr [rbp+pvar+10h], rcx
0x180021259  mov     ecx, 14h
0x18002125e  movups  xmmword ptr [rbp+var_58], xmm0
0x180021262  mov     word ptr [rbp+var_58], cx
0x180021266  movups  xmmword ptr [rbp+var_28], xmm1
0x18002126a  movups  xmmword ptr [rbp+pvar], xmm0
0x18002126e  mov     rcx, [rax+rdi*8]
0x180021272  mov     qword ptr [rbp+var_58+8], rcx
0x180021276  cmp     edi, r12d
0x180021279  jnb     short loc_18002128F
0x18002127b  lea     r8, [rbp+var_28]; struct tagPROPVARIANT *
0x18002127f  mov     edx, edi; unsigned int
0x180021281  mov     rcx, r13; struct tagPROPVARIANT *
0x180021284  call    ?_ConstructPropvarFromVectorElement@@YAJPEBUtagPROPVARIANT@@KPEAU1@@Z; _ConstructPropvarFromVectorElement(tagPROPVARIANT const *,ulong,tagPROPVARIANT *)
0x180021289  mov     ebx, eax
0x18002128b  test    eax, eax
0x18002128d  js      short loc_1800212E7
0x18002128f  cmp     edi, r14d
0x180021292  jnb     short loc_1800212A8
0x180021294  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x180021298  mov     edx, edi; unsigned int
0x18002129a  mov     rcx, r15; struct tagPROPVARIANT *
0x18002129d  call    ?_ConstructPropvarFromVectorElement@@YAJPEBUtagPROPVARIANT@@KPEAU1@@Z; _ConstructPropvarFromVectorElement(tagPROPVARIANT const *,ulong,tagPROPVARIANT *)
0x1800212a2  mov     ebx, eax
0x1800212a4  test    eax, eax
0x1800212a6  js      short loc_1800212E7
0x1800212a8  mov     rax, r15
0x1800212ab  lea     rcx, [rbp+var_58]; struct tagPROPVARIANT *
0x1800212af  neg     rax
0x1800212b2  lea     rax, [rbp+pvar]
0x1800212b6  sbb     r8, r8
0x1800212b9  and     r8, rax; struct tagPROPVARIANT *
0x1800212bc  mov     rax, r13
0x1800212bf  neg     rax
0x1800212c2  lea     rax, [rbp+var_28]
0x1800212c6  sbb     rdx, rdx
0x1800212c9  and     rdx, rax; struct tagPROPVARIANT *
0x1800212cc  call    ?_UpdateSignedRationalPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z; _UpdateSignedRationalPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x1800212d1  mov     ebx, eax
0x1800212d3  test    eax, eax
0x1800212d5  js      short loc_1800212E7
0x1800212d7  mov     rcx, [rbp+arg_0]
0x1800212db  mov     rax, qword ptr [rbp+var_58+8]
0x1800212df  mov     rcx, [rcx+10h]
0x1800212e3  mov     [rcx+rdi*8], rax
0x1800212e7  lea     rcx, [rbp+pvar]; pvar
0x1800212eb  call    cs:__imp_PropVariantClear
0x1800212f2  nop     dword ptr [rax+rax+00h]
0x1800212f7  lea     rcx, [rbp+var_28]; pvar
0x1800212fb  call    cs:__imp_PropVariantClear
0x180021302  nop     dword ptr [rax+rax+00h]
0x180021307  lea     rcx, [rbp+var_58]; pvar
0x18002130b  call    cs:__imp_PropVariantClear
0x180021312  nop     dword ptr [rax+rax+00h]
0x180021317  mov     rax, [rbp+arg_0]
0x18002131b  inc     edi
0x18002131d  cmp     edi, esi
0x18002131f  jb      loc_180021239
0x180021325  mov     eax, ebx
0x180021327  add     rsp, 78h
0x18002132b  pop     r15
0x18002132d  pop     r14
0x18002132f  pop     r13
0x180021331  pop     r12
0x180021333  pop     rdi
0x180021334  pop     rsi
0x180021335  pop     rbx
0x180021336  pop     rbp
0x180021337  retn
```
