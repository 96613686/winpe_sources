# _UpdateUnsignedRationalPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180020344`
- end: `0x1800203e1`
- name: `?_UpdateUnsignedRationalPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z`
- size: `157`
- prototype: `int(struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001384c`
- `0x1800203e8`

## callees

- `0x18001f474`
- `0x180020344`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002038f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800203c4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002038f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800203c4`

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
0x180020344  push    rbx
0x180020346  push    rbp
0x180020347  push    rsi
0x180020348  push    rdi
0x180020349  push    r14
0x18002034b  sub     rsp, 40h
0x18002034f  mov     ebp, [rcx+8]
0x180020352  xor     ebx, ebx
0x180020354  mov     esi, [rcx+0Ch]
0x180020357  mov     r14, r8
0x18002035a  mov     rax, rdx
0x18002035d  mov     rdi, rcx
0x180020360  test    rdx, rdx
0x180020363  jz      short loc_180020395
0x180020365  xor     ecx, ecx
0x180020367  lea     rdx, [rsp+68h+pvar]; pvarDest
0x18002036c  mov     qword ptr [rsp+68h+pvar+10h], rcx
0x180020371  xorps   xmm0, xmm0
0x180020374  mov     rcx, rax; pvarSrc
0x180020377  movups  xmmword ptr [rsp+68h+pvar], xmm0
0x18002037c  call    ?ConvertPropvarToULONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToULONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180020381  test    eax, eax
0x180020383  lea     rcx, [rsp+68h+pvar]; pvar
0x180020388  mov     ebx, eax
0x18002038a  cmovns  ebp, dword ptr [rsp+68h+pvar+8]
0x18002038f  call    cs:__imp_PropVariantClear
0x180020395  test    r14, r14
0x180020398  jz      short loc_1800203CA
0x18002039a  xorps   xmm0, xmm0
0x18002039d  lea     rdx, [rsp+68h+pvar]; pvarDest
0x1800203a2  xor     eax, eax
0x1800203a4  mov     rcx, r14; pvarSrc
0x1800203a7  movups  xmmword ptr [rsp+68h+pvar], xmm0
0x1800203ac  mov     qword ptr [rsp+68h+pvar+10h], rax
0x1800203b1  call    ?ConvertPropvarToULONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToULONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800203b6  test    eax, eax
0x1800203b8  lea     rcx, [rsp+68h+pvar]; pvar
0x1800203bd  mov     ebx, eax
0x1800203bf  cmovns  esi, dword ptr [rsp+68h+pvar+8]
0x1800203c4  call    cs:__imp_PropVariantClear
0x1800203ca  test    ebx, ebx
0x1800203cc  js      short loc_1800203D4
0x1800203ce  mov     [rdi+8], ebp
0x1800203d1  mov     [rdi+0Ch], esi
0x1800203d4  mov     eax, ebx
0x1800203d6  add     rsp, 40h
0x1800203da  pop     r14
0x1800203dc  pop     rdi
0x1800203dd  pop     rsi
0x1800203de  pop     rbp
0x1800203df  pop     rbx
0x1800203e0  retn
```
