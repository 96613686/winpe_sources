# _UpdateSignedRationalPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180020150`
- end: `0x1800201ed`
- name: `?_UpdateSignedRationalPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z`
- size: `157`
- prototype: `int(struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001384c`
- `0x1800201f4`

## callees

- `0x18000adb0`
- `0x180020150`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002019b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800201d0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002019b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800201d0`

## pseudocode

```c
__int64 __fastcall _UpdateSignedRationalPropvar(
        struct tagPROPVARIANT *a1,
        struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3)
{
  LONG lVal; // ebp
  int v4; // ebx
  LONG HighPart; // esi
  PROPVARIANT pvar; // [rsp+20h] [rbp-48h] BYREF

  lVal = a1->lVal;
  v4 = 0;
  HighPart = a1->hVal.HighPart;
  if ( a2 )
  {
    memset(&pvar, 0, sizeof(pvar));
    v4 = ConvertPropvarToLONG(a2, &pvar);
    if ( v4 >= 0 )
      lVal = pvar.lVal;
    PropVariantClear(&pvar);
  }
  if ( a3 )
  {
    memset(&pvar, 0, sizeof(pvar));
    v4 = ConvertPropvarToLONG(a3, &pvar);
    if ( v4 >= 0 )
      HighPart = pvar.lVal;
    PropVariantClear(&pvar);
  }
  if ( v4 >= 0 )
  {
    a1->lVal = lVal;
    a1->hVal.HighPart = HighPart;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180020150  push    rbx
0x180020152  push    rbp
0x180020153  push    rsi
0x180020154  push    rdi
0x180020155  push    r14
0x180020157  sub     rsp, 40h
0x18002015b  mov     ebp, [rcx+8]
0x18002015e  xor     ebx, ebx
0x180020160  mov     esi, [rcx+0Ch]
0x180020163  mov     r14, r8
0x180020166  mov     rax, rdx
0x180020169  mov     rdi, rcx
0x18002016c  test    rdx, rdx
0x18002016f  jz      short loc_1800201A1
0x180020171  xor     ecx, ecx
0x180020173  lea     rdx, [rsp+68h+pvar]; pvarDest
0x180020178  mov     qword ptr [rsp+68h+pvar+10h], rcx
0x18002017d  xorps   xmm0, xmm0
0x180020180  mov     rcx, rax; pvarSrc
0x180020183  movups  xmmword ptr [rsp+68h+pvar], xmm0
0x180020188  call    ?ConvertPropvarToLONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToLONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18002018d  test    eax, eax
0x18002018f  lea     rcx, [rsp+68h+pvar]; pvar
0x180020194  mov     ebx, eax
0x180020196  cmovns  ebp, dword ptr [rsp+68h+pvar+8]
0x18002019b  call    cs:__imp_PropVariantClear
0x1800201a1  test    r14, r14
0x1800201a4  jz      short loc_1800201D6
0x1800201a6  xorps   xmm0, xmm0
0x1800201a9  lea     rdx, [rsp+68h+pvar]; pvarDest
0x1800201ae  xor     eax, eax
0x1800201b0  mov     rcx, r14; pvarSrc
0x1800201b3  movups  xmmword ptr [rsp+68h+pvar], xmm0
0x1800201b8  mov     qword ptr [rsp+68h+pvar+10h], rax
0x1800201bd  call    ?ConvertPropvarToLONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToLONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800201c2  test    eax, eax
0x1800201c4  lea     rcx, [rsp+68h+pvar]; pvar
0x1800201c9  mov     ebx, eax
0x1800201cb  cmovns  esi, dword ptr [rsp+68h+pvar+8]
0x1800201d0  call    cs:__imp_PropVariantClear
0x1800201d6  test    ebx, ebx
0x1800201d8  js      short loc_1800201E0
0x1800201da  mov     [rdi+8], ebp
0x1800201dd  mov     [rdi+0Ch], esi
0x1800201e0  mov     eax, ebx
0x1800201e2  add     rsp, 40h
0x1800201e6  pop     r14
0x1800201e8  pop     rdi
0x1800201e9  pop     rsi
0x1800201ea  pop     rbp
0x1800201eb  pop     rbx
0x1800201ec  retn
```
