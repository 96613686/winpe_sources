# _UpdateUnsignedRationalPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180021340`
- end: `0x1800213ea`
- name: `?_UpdateUnsignedRationalPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z`
- size: `170`
- prototype: `int(struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800141ec`
- `0x1800213f0`

## callees

- `0x1800203a4`
- `0x180021340`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002138b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800213c6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002138b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800213c6`

## pseudocode

```c
__int64 __fastcall _UpdateUnsignedRationalPropvar(
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
    v4 = ConvertPropvarToULONG(a2, &pvar);
    if ( v4 >= 0 )
      lVal = pvar.lVal;
    PropVariantClear(&pvar);
  }
  if ( a3 )
  {
    memset(&pvar, 0, sizeof(pvar));
    v4 = ConvertPropvarToULONG(a3, &pvar);
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
0x180021340  push    rbx
0x180021342  push    rbp
0x180021343  push    rsi
0x180021344  push    rdi
0x180021345  push    r14
0x180021347  sub     rsp, 40h
0x18002134b  mov     ebp, [rcx+8]
0x18002134e  xor     ebx, ebx
0x180021350  mov     esi, [rcx+0Ch]
0x180021353  mov     r14, r8
0x180021356  mov     rax, rdx
0x180021359  mov     rdi, rcx
0x18002135c  test    rdx, rdx
0x18002135f  jz      short loc_180021397
0x180021361  xor     ecx, ecx
0x180021363  lea     rdx, [rsp+68h+pvar]; pvarDest
0x180021368  mov     qword ptr [rsp+68h+pvar+10h], rcx
0x18002136d  xorps   xmm0, xmm0
0x180021370  mov     rcx, rax; pvarSrc
0x180021373  movups  xmmword ptr [rsp+68h+pvar], xmm0
0x180021378  call    ?ConvertPropvarToULONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToULONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18002137d  test    eax, eax
0x18002137f  lea     rcx, [rsp+68h+pvar]; pvar
0x180021384  mov     ebx, eax
0x180021386  cmovns  ebp, dword ptr [rsp+68h+pvar+8]
0x18002138b  call    cs:__imp_PropVariantClear
0x180021392  nop     dword ptr [rax+rax+00h]
0x180021397  test    r14, r14
0x18002139a  jz      short loc_1800213D2
0x18002139c  xorps   xmm0, xmm0
0x18002139f  lea     rdx, [rsp+68h+pvar]; pvarDest
0x1800213a4  xor     eax, eax
0x1800213a6  mov     rcx, r14; pvarSrc
0x1800213a9  movups  xmmword ptr [rsp+68h+pvar], xmm0
0x1800213ae  mov     qword ptr [rsp+68h+pvar+10h], rax
0x1800213b3  call    ?ConvertPropvarToULONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToULONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800213b8  test    eax, eax
0x1800213ba  lea     rcx, [rsp+68h+pvar]; pvar
0x1800213bf  mov     ebx, eax
0x1800213c1  cmovns  esi, dword ptr [rsp+68h+pvar+8]
0x1800213c6  call    cs:__imp_PropVariantClear
0x1800213cd  nop     dword ptr [rax+rax+00h]
0x1800213d2  test    ebx, ebx
0x1800213d4  js      short loc_1800213DC
0x1800213d6  mov     [rdi+8], ebp
0x1800213d9  mov     [rdi+0Ch], esi
0x1800213dc  mov     eax, ebx
0x1800213de  add     rsp, 40h
0x1800213e2  pop     r14
0x1800213e4  pop     rdi
0x1800213e5  pop     rsi
0x1800213e6  pop     rbp
0x1800213e7  pop     rbx
0x1800213e8  retn
```
