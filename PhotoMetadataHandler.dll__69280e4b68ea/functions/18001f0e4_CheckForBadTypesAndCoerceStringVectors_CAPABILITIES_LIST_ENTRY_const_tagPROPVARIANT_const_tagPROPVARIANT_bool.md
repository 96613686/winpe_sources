# CheckForBadTypesAndCoerceStringVectors(CAPABILITIES_LIST_ENTRY const *,tagPROPVARIANT const &,tagPROPVARIANT *,bool *)

- ea: `0x18001f0e4`
- end: `0x18001f1e9`
- name: `?CheckForBadTypesAndCoerceStringVectors@@YAJPEBUCAPABILITIES_LIST_ENTRY@@AEBUtagPROPVARIANT@@PEAU2@PEA_N@Z`
- size: `261`
- prototype: `__int64 __fastcall(const struct CAPABILITIES_LIST_ENTRY *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001ed1c`

## callees

- `0x180008b7c`
- `0x18001eef0`
- `0x18001f0e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001f161`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001f161`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f1a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f1a1`

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
0x18001f0e4  push    rbx
0x18001f0e6  push    rbp
0x18001f0e7  push    rsi
0x18001f0e8  push    rdi
0x18001f0e9  push    r12
0x18001f0eb  push    r14
0x18001f0ed  push    r15
0x18001f0ef  sub     rsp, 40h
0x18001f0f3  xor     eax, eax
0x18001f0f5  xor     r12d, r12d
0x18001f0f8  xorps   xmm0, xmm0
0x18001f0fb  movzx   ebp, r12b
0x18001f0ff  movups  xmmword ptr [r8], xmm0
0x18001f103  mov     [r8+10h], rax
0x18001f107  mov     r15, r9
0x18001f10a  lea     esi, [rax+1]
0x18001f10d  mov     rdi, r8
0x18001f110  mov     r10, rdx
0x18001f113  mov     r14, rcx
0x18001f116  cmp     [rcx+1Ch], esi
0x18001f119  jnz     loc_18001F1BF
0x18001f11f  mov     eax, 101Fh
0x18001f124  cmp     [rdx], ax
0x18001f127  jnz     short loc_18001F15E
0x18001f129  xor     eax, eax
0x18001f12b  mov     dword ptr [rsp+78h+pvarSrc], r12d
0x18001f130  movups  xmmword ptr [rsp+78h+pvarSrc+4], xmm0
0x18001f135  mov     dword ptr [rsp+78h+pvarSrc+14h], eax
0x18001f139  cmp     [rdx+8], r12d
0x18001f13d  jz      short loc_18001F159
0x18001f13f  cmp     [rdx+8], esi
0x18001f142  lea     eax, [rsi+1Eh]
0x18001f145  mov     word ptr [rsp+78h+pvarSrc], ax
0x18001f14a  mov     rax, [rdx+10h]
0x18001f14e  cmova   ebp, esi
0x18001f151  mov     rcx, [rax]
0x18001f154  mov     qword ptr [rsp+78h+pvarSrc+8], rcx
0x18001f159  lea     rdx, [rsp+78h+pvarSrc]; pvarSrc
0x18001f15e  mov     rcx, rdi; pvarDest
0x18001f161  call    cs:__imp_PropVariantCopy
0x18001f168  nop     dword ptr [rax+rax+00h]
0x18001f16d  mov     ebx, eax
0x18001f16f  test    eax, eax
0x18001f171  js      short loc_18001F186
0x18001f173  cmp     [rdi], r12w
0x18001f177  jz      short loc_18001F186
0x18001f179  mov     rdx, rdi; struct tagPROPVARIANT *
0x18001f17c  mov     rcx, r14; struct CAPABILITIES_LIST_ENTRY *
0x18001f17f  call    ?CheckForBadTypes@@YAJPEBUCAPABILITIES_LIST_ENTRY@@PEBUtagPROPVARIANT@@@Z; CheckForBadTypes(CAPABILITIES_LIST_ENTRY const *,tagPROPVARIANT const *)
0x18001f184  mov     ebx, eax
0x18001f186  test    r15, r15
0x18001f189  jz      short loc_18001F19A
0x18001f18b  test    ebx, ebx
0x18001f18d  js      short loc_18001F194
0x18001f18f  test    bpl, bpl
0x18001f192  jnz     short loc_18001F197
0x18001f194  mov     sil, r12b
0x18001f197  mov     [r15], sil
0x18001f19a  test    ebx, ebx
0x18001f19c  jns     short loc_18001F1AD
0x18001f19e  mov     rcx, rdi; pvar
0x18001f1a1  call    cs:__imp_PropVariantClear
0x18001f1a8  nop     dword ptr [rax+rax+00h]
0x18001f1ad  mov     eax, ebx
0x18001f1af  add     rsp, 40h
0x18001f1b3  pop     r15
0x18001f1b5  pop     r14
0x18001f1b7  pop     r12
0x18001f1b9  pop     rdi
0x18001f1ba  pop     rsi
0x18001f1bb  pop     rbp
0x18001f1bc  pop     rbx
0x18001f1bd  retn
0x18001f1bf  cmp     dword ptr [rcx+1Ch], 2
0x18001f1c3  jnz     short loc_18001F15E
0x18001f1c5  mov     eax, 1Fh
0x18001f1ca  cmp     ax, [rdx]
0x18001f1cd  jnz     short loc_18001F15E
0x18001f1cf  mov     rdx, [rcx+38h]; unsigned __int16 *
0x18001f1d3  test    rdx, rdx
0x18001f1d6  jnz     short loc_18001F1DF
0x18001f1d8  mov     ebx, 8000FFFFh
0x18001f1dd  jmp     short loc_18001F186
0x18001f1df  mov     rcx, r10; struct tagPROPVARIANT *
0x18001f1e2  call    ?ConvertDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBGPEAU1@@Z; ConvertDelimitedString(tagPROPVARIANT const *,ushort const *,tagPROPVARIANT *)
0x18001f1e7  jmp     short loc_18001F16D
```
