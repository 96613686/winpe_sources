# _UpdateSignedRationalPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x18002112c`
- end: `0x1800211d6`
- name: `?_UpdateSignedRationalPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z`
- size: `170`
- prototype: `int(struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800141ec`
- `0x1800211dc`

## callees

- `0x18000b3b0`
- `0x18002112c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021177`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800211b2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021177`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800211b2`

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
0x18002112c  push    rbx
0x18002112e  push    rbp
0x18002112f  push    rsi
0x180021130  push    rdi
0x180021131  push    r14
0x180021133  sub     rsp, 40h
0x180021137  mov     ebp, [rcx+8]
0x18002113a  xor     ebx, ebx
0x18002113c  mov     esi, [rcx+0Ch]
0x18002113f  mov     r14, r8
0x180021142  mov     rax, rdx
0x180021145  mov     rdi, rcx
0x180021148  test    rdx, rdx
0x18002114b  jz      short loc_180021183
0x18002114d  xor     ecx, ecx
0x18002114f  lea     rdx, [rsp+68h+pvar]; pvarDest
0x180021154  mov     qword ptr [rsp+68h+pvar+10h], rcx
0x180021159  xorps   xmm0, xmm0
0x18002115c  mov     rcx, rax; pvarSrc
0x18002115f  movups  xmmword ptr [rsp+68h+pvar], xmm0
0x180021164  call    ?ConvertPropvarToLONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToLONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180021169  test    eax, eax
0x18002116b  lea     rcx, [rsp+68h+pvar]; pvar
0x180021170  mov     ebx, eax
0x180021172  cmovns  ebp, dword ptr [rsp+68h+pvar+8]
0x180021177  call    cs:__imp_PropVariantClear
0x18002117e  nop     dword ptr [rax+rax+00h]
0x180021183  test    r14, r14
0x180021186  jz      short loc_1800211BE
0x180021188  xorps   xmm0, xmm0
0x18002118b  lea     rdx, [rsp+68h+pvar]; pvarDest
0x180021190  xor     eax, eax
0x180021192  mov     rcx, r14; pvarSrc
0x180021195  movups  xmmword ptr [rsp+68h+pvar], xmm0
0x18002119a  mov     qword ptr [rsp+68h+pvar+10h], rax
0x18002119f  call    ?ConvertPropvarToLONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToLONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800211a4  test    eax, eax
0x1800211a6  lea     rcx, [rsp+68h+pvar]; pvar
0x1800211ab  mov     ebx, eax
0x1800211ad  cmovns  esi, dword ptr [rsp+68h+pvar+8]
0x1800211b2  call    cs:__imp_PropVariantClear
0x1800211b9  nop     dword ptr [rax+rax+00h]
0x1800211be  test    ebx, ebx
0x1800211c0  js      short loc_1800211C8
0x1800211c2  mov     [rdi+8], ebp
0x1800211c5  mov     [rdi+0Ch], esi
0x1800211c8  mov     eax, ebx
0x1800211ca  add     rsp, 40h
0x1800211ce  pop     r14
0x1800211d0  pop     rdi
0x1800211d1  pop     rsi
0x1800211d2  pop     rbp
0x1800211d3  pop     rbx
0x1800211d4  retn
```
