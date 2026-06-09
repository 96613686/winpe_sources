# CheckForBadTypesAndCoerceStringVectors(CAPABILITIES_LIST_ENTRY const *,tagPROPVARIANT const &,tagPROPVARIANT *,bool *)

- ea: `0x18001e2a0`
- end: `0x18001e398`
- name: `?CheckForBadTypesAndCoerceStringVectors@@YAJPEBUCAPABILITIES_LIST_ENTRY@@AEBUtagPROPVARIANT@@PEAU2@PEA_N@Z`
- size: `248`
- prototype: `__int64 __fastcall(const struct CAPABILITIES_LIST_ENTRY *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001defc`

## callees

- `0x180007828`
- `0x18001e0b0`
- `0x18001e2a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001e31d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001e31d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e357`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e357`

## pseudocode

```c
__int64 __fastcall CheckForBadTypesAndCoerceStringVectors(
        const struct CAPABILITIES_LIST_ENTRY *a1,
        const struct tagPROPVARIANT *p_pvarSrc,
        struct tagPROPVARIANT *a3,
        bool *a4)
{
  bool v4; // bp
  bool v6; // si
  const struct tagPROPVARIANT *v8; // r10
  bool v10; // zf
  int v11; // eax
  int v12; // ebx
  wchar_t *v14; // rdx
  PROPVARIANT pvarSrc; // [rsp+20h] [rbp-58h] BYREF

  v4 = 0;
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v6 = 1;
  v8 = p_pvarSrc;
  if ( *((_DWORD *)a1 + 7) == 1 )
  {
    if ( p_pvarSrc->vt == 4127 )
    {
      memset(&pvarSrc, 0, sizeof(pvarSrc));
      if ( p_pvarSrc->lVal )
      {
        v10 = p_pvarSrc->lVal == 1;
        pvarSrc.vt = 31;
        v4 = !v10;
        pvarSrc.hVal.QuadPart = (LONGLONG)*p_pvarSrc->cabstr.pElems;
      }
      p_pvarSrc = &pvarSrc;
    }
    goto LABEL_6;
  }
  if ( *((_DWORD *)a1 + 7) != 2 || p_pvarSrc->vt != 31 )
  {
LABEL_6:
    v11 = PropVariantCopy(a3, p_pvarSrc);
    goto LABEL_7;
  }
  v14 = (wchar_t *)*((_QWORD *)a1 + 7);
  if ( !v14 )
  {
    v12 = -2147418113;
    goto LABEL_10;
  }
  v11 = ConvertDelimitedString(v8, v14, a3);
LABEL_7:
  v12 = v11;
  if ( v11 >= 0 && a3->vt )
    v12 = CheckForBadTypes(a1, a3);
LABEL_10:
  if ( a4 )
  {
    if ( v12 < 0 || !v4 )
      v6 = 0;
    *a4 = v6;
  }
  if ( v12 < 0 )
    PropVariantClear(a3);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001e2a0  push    rbx
0x18001e2a2  push    rbp
0x18001e2a3  push    rsi
0x18001e2a4  push    rdi
0x18001e2a5  push    r12
0x18001e2a7  push    r14
0x18001e2a9  push    r15
0x18001e2ab  sub     rsp, 40h
0x18001e2af  xor     eax, eax
0x18001e2b1  xor     r12d, r12d
0x18001e2b4  xorps   xmm0, xmm0
0x18001e2b7  movzx   ebp, r12b
0x18001e2bb  movups  xmmword ptr [r8], xmm0
0x18001e2bf  mov     [r8+10h], rax
0x18001e2c3  mov     r15, r9
0x18001e2c6  lea     esi, [rax+1]
0x18001e2c9  mov     rdi, r8
0x18001e2cc  mov     r10, rdx
0x18001e2cf  mov     r14, rcx
0x18001e2d2  cmp     [rcx+1Ch], esi
0x18001e2d5  jnz     loc_18001E36E
0x18001e2db  mov     eax, 101Fh
0x18001e2e0  cmp     [rdx], ax
0x18001e2e3  jnz     short loc_18001E31A
0x18001e2e5  xor     eax, eax
0x18001e2e7  mov     dword ptr [rsp+78h+pvarSrc], r12d
0x18001e2ec  movups  xmmword ptr [rsp+78h+pvarSrc+4], xmm0
0x18001e2f1  mov     dword ptr [rsp+78h+pvarSrc+14h], eax
0x18001e2f5  cmp     [rdx+8], r12d
0x18001e2f9  jz      short loc_18001E315
0x18001e2fb  cmp     [rdx+8], esi
0x18001e2fe  lea     eax, [rsi+1Eh]
0x18001e301  mov     word ptr [rsp+78h+pvarSrc], ax
0x18001e306  mov     rax, [rdx+10h]
0x18001e30a  cmova   ebp, esi
0x18001e30d  mov     rcx, [rax]
0x18001e310  mov     qword ptr [rsp+78h+pvarSrc+8], rcx
0x18001e315  lea     rdx, [rsp+78h+pvarSrc]; pvarSrc
0x18001e31a  mov     rcx, rdi; pvarDest
0x18001e31d  call    cs:__imp_PropVariantCopy
0x18001e323  mov     ebx, eax
0x18001e325  test    eax, eax
0x18001e327  js      short loc_18001E33C
0x18001e329  cmp     [rdi], r12w
0x18001e32d  jz      short loc_18001E33C
0x18001e32f  mov     rdx, rdi; struct tagPROPVARIANT *
0x18001e332  mov     rcx, r14; struct CAPABILITIES_LIST_ENTRY *
0x18001e335  call    ?CheckForBadTypes@@YAJPEBUCAPABILITIES_LIST_ENTRY@@PEBUtagPROPVARIANT@@@Z; CheckForBadTypes(CAPABILITIES_LIST_ENTRY const *,tagPROPVARIANT const *)
0x18001e33a  mov     ebx, eax
0x18001e33c  test    r15, r15
0x18001e33f  jz      short loc_18001E350
0x18001e341  test    ebx, ebx
0x18001e343  js      short loc_18001E34A
0x18001e345  test    bpl, bpl
0x18001e348  jnz     short loc_18001E34D
0x18001e34a  mov     sil, r12b
0x18001e34d  mov     [r15], sil
0x18001e350  test    ebx, ebx
0x18001e352  jns     short loc_18001E35D
0x18001e354  mov     rcx, rdi; pvar
0x18001e357  call    cs:__imp_PropVariantClear
0x18001e35d  mov     eax, ebx
0x18001e35f  add     rsp, 40h
0x18001e363  pop     r15
0x18001e365  pop     r14
0x18001e367  pop     r12
0x18001e369  pop     rdi
0x18001e36a  pop     rsi
0x18001e36b  pop     rbp
0x18001e36c  pop     rbx
0x18001e36d  retn
0x18001e36e  cmp     dword ptr [rcx+1Ch], 2
0x18001e372  jnz     short loc_18001E31A
0x18001e374  mov     eax, 1Fh
0x18001e379  cmp     ax, [rdx]
0x18001e37c  jnz     short loc_18001E31A
0x18001e37e  mov     rdx, [rcx+38h]; unsigned __int16 *
0x18001e382  test    rdx, rdx
0x18001e385  jnz     short loc_18001E38E
0x18001e387  mov     ebx, 8000FFFFh
0x18001e38c  jmp     short loc_18001E33C
0x18001e38e  mov     rcx, r10; struct tagPROPVARIANT *
0x18001e391  call    ?ConvertDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBGPEAU1@@Z; ConvertDelimitedString(tagPROPVARIANT const *,ushort const *,tagPROPVARIANT *)
0x18001e396  jmp     short loc_18001E323
```
