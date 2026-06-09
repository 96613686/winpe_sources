# _SimpleOpCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,int,int *)

- ea: `0x180038428`
- end: `0x180038528`
- name: `?_SimpleOpCompareValues@@YAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@HPEAH@Z`
- size: `256`
- prototype: `__int64 __fastcall(PROPVARIANT *propvar2, PROPVARIANT *propvar1, enum tagCONDITION_OPERATION, int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002a61c`

## callees

- `0x1800383b8`
- `0x180038428`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180038513`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180038513`
- `PROPSYS!PropVariantCompareEx` at `0x1800384f7`
- `PROPSYS!PropVariantCompareEx` at `0x1800384f7`
- `PROPSYS!PropVariantChangeType` at `0x1800384b7`
- `PROPSYS!PropVariantChangeType` at `0x1800384d7`
- `PROPSYS!PropVariantChangeType` at `0x1800384b7`
- `PROPSYS!PropVariantChangeType` at `0x1800384d7`

## pseudocode

```c
__int64 __fastcall _SimpleOpCompareValues(
        PROPVARIANT *propvar2,
        PROPVARIANT *propvar1,
        enum tagCONDITION_OPERATION a3,
        int a4,
        int *a5)
{
  VARTYPE v7; // r9
  PROPVARIANT *v8; // rbx
  const PROPVARIANT *v9; // r14
  unsigned int v10; // ebx
  HRESULT v11; // eax
  PROPVARIANT *v12; // r8
  int v13; // eax
  PROPVARIANT ppropvarDest[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v16; // [rsp+30h] [rbp-48h]

  v7 = *(_WORD *)propvar2;
  v8 = propvar1;
  v9 = propvar2;
  *a5 = 0;
  if ( v7 == *(_WORD *)propvar1 || v7 && *(_WORD *)propvar1 )
  {
    *(_OWORD *)ppropvarDest = 0;
    v16 = 0;
    if ( v7 != *(_WORD *)propvar1 && v7 != 1 && *(_WORD *)propvar1 != 1 )
    {
      if ( PropVariantChangeType(ppropvarDest, propvar1, 0, v7) < 0 )
      {
        v11 = PropVariantChangeType(ppropvarDest, v9, 0, *(_WORD *)v8);
        v12 = ppropvarDest;
        if ( v11 < 0 )
          v12 = (PROPVARIANT *)v9;
        v9 = v12;
      }
      else
      {
        v8 = ppropvarDest;
      }
    }
    v13 = PropVariantCompareEx(v8, v9, PVCU_DEFAULT, 0);
    v10 = _SimpleOpCompareResult(v13, a3, a4, a5);
    PropVariantClear(ppropvarDest);
  }
  else
  {
    v10 = 0;
    if ( a4 )
    {
      if ( a3 != COP_EQUAL )
        return v10;
      goto LABEL_8;
    }
    if ( a3 == COP_NOTEQUAL )
LABEL_8:
      *a5 = 1;
  }
  return v10;
}

```

## disassembly

```asm
0x180038428  push    rbx
0x18003842a  push    rbp
0x18003842b  push    rsi
0x18003842c  push    rdi
0x18003842d  push    r14
0x18003842f  push    r15
0x180038431  sub     rsp, 48h
0x180038435  mov     rsi, [rsp+78h+arg_20]
0x18003843d  xor     r15d, r15d
0x180038440  mov     ebp, r9d
0x180038443  mov     edi, r8d
0x180038446  movzx   r9d, word ptr [rcx]; vt
0x18003844a  mov     rbx, rdx
0x18003844d  mov     r14, rcx
0x180038450  mov     [rsi], r15d
0x180038453  cmp     r9w, [rdx]
0x180038457  jz      short loc_18003848A
0x180038459  test    r9w, r9w
0x18003845d  jz      short loc_180038465
0x18003845f  cmp     [rdx], r15w
0x180038463  jnz     short loc_18003848A
0x180038465  mov     ebx, r15d
0x180038468  mov     eax, 1
0x18003846d  test    ebp, ebp
0x18003846f  jz      short loc_18003847A
0x180038471  cmp     edi, eax
0x180038473  jz      short loc_180038483
0x180038475  jmp     loc_180038519
0x18003847a  cmp     edi, 2
0x18003847d  jnz     loc_180038519
0x180038483  mov     [rsi], eax
0x180038485  jmp     loc_180038519
0x18003848a  xor     eax, eax
0x18003848c  xorps   xmm0, xmm0
0x18003848f  movups  xmmword ptr [rsp+78h+ppropvarDest], xmm0
0x180038494  mov     [rsp+78h+var_48], rax
0x180038499  cmp     r9w, [rdx]
0x18003849d  jz      short loc_1800384EB
0x18003849f  mov     eax, 1
0x1800384a4  cmp     r9w, ax
0x1800384a8  jz      short loc_1800384EB
0x1800384aa  cmp     [rdx], ax
0x1800384ad  jz      short loc_1800384EB
0x1800384af  xor     r8d, r8d; flags
0x1800384b2  lea     rcx, [rsp+78h+ppropvarDest]; ppropvarDest
0x1800384b7  call    cs:__imp_PropVariantChangeType
0x1800384bd  test    eax, eax
0x1800384bf  js      short loc_1800384C8
0x1800384c1  lea     rbx, [rsp+78h+ppropvarDest]
0x1800384c6  jmp     short loc_1800384EB
0x1800384c8  movzx   r9d, word ptr [rbx]; vt
0x1800384cc  lea     rcx, [rsp+78h+ppropvarDest]; ppropvarDest
0x1800384d1  xor     r8d, r8d; flags
0x1800384d4  mov     rdx, r14; propvarSrc
0x1800384d7  call    cs:__imp_PropVariantChangeType
0x1800384dd  test    eax, eax
0x1800384df  lea     r8, [rsp+78h+ppropvarDest]
0x1800384e4  cmovs   r8, r14
0x1800384e8  mov     r14, r8
0x1800384eb  xor     r9d, r9d; flags
0x1800384ee  xor     r8d, r8d; unit
0x1800384f1  mov     rdx, r14; propvar2
0x1800384f4  mov     rcx, rbx; propvar1
0x1800384f7  call    cs:__imp_PropVariantCompareEx
0x1800384fd  mov     r9, rsi; int *
0x180038500  mov     r8d, ebp; int
0x180038503  mov     ecx, eax; int
0x180038505  mov     edx, edi; enum tagCONDITION_OPERATION
0x180038507  call    ?_SimpleOpCompareResult@@YAJHW4tagCONDITION_OPERATION@@HPEAH@Z; _SimpleOpCompareResult(int,tagCONDITION_OPERATION,int,int *)
0x18003850c  lea     rcx, [rsp+78h+ppropvarDest]; pvar
0x180038511  mov     ebx, eax
0x180038513  call    cs:__imp_PropVariantClear
0x180038519  mov     eax, ebx
0x18003851b  add     rsp, 48h
0x18003851f  pop     r15
0x180038521  pop     r14
0x180038523  pop     rdi
0x180038524  pop     rsi
0x180038525  pop     rbp
0x180038526  pop     rbx
0x180038527  retn
```
