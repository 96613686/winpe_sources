# _SimpleOpCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,int,int *)

- ea: `0x18004b350`
- end: `0x18004b450`
- name: `?_SimpleOpCompareValues@@YAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@HPEAH@Z`
- size: `256`
- prototype: `__int64 __fastcall(PROPVARIANT *propvar2, PROPVARIANT *propvar1, enum tagCONDITION_OPERATION, int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180045360`

## callees

- `0x18004b2e0`
- `0x18004b350`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004b43b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004b43b`
- `PROPSYS!PropVariantChangeType` at `0x18004b3df`
- `PROPSYS!PropVariantChangeType` at `0x18004b3ff`
- `PROPSYS!PropVariantChangeType` at `0x18004b3df`
- `PROPSYS!PropVariantChangeType` at `0x18004b3ff`
- `PROPSYS!PropVariantCompareEx` at `0x18004b41f`
- `PROPSYS!PropVariantCompareEx` at `0x18004b41f`

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
0x18004b350  push    rbx
0x18004b352  push    rbp
0x18004b353  push    rsi
0x18004b354  push    rdi
0x18004b355  push    r14
0x18004b357  push    r15
0x18004b359  sub     rsp, 48h
0x18004b35d  mov     rsi, [rsp+78h+arg_20]
0x18004b365  xor     r15d, r15d
0x18004b368  mov     ebp, r9d
0x18004b36b  mov     edi, r8d
0x18004b36e  movzx   r9d, word ptr [rcx]; vt
0x18004b372  mov     rbx, rdx
0x18004b375  mov     r14, rcx
0x18004b378  mov     [rsi], r15d
0x18004b37b  cmp     r9w, [rdx]
0x18004b37f  jz      short loc_18004B3B2
0x18004b381  test    r9w, r9w
0x18004b385  jz      short loc_18004B38D
0x18004b387  cmp     [rdx], r15w
0x18004b38b  jnz     short loc_18004B3B2
0x18004b38d  mov     ebx, r15d
0x18004b390  mov     eax, 1
0x18004b395  test    ebp, ebp
0x18004b397  jz      short loc_18004B3A2
0x18004b399  cmp     edi, eax
0x18004b39b  jz      short loc_18004B3AB
0x18004b39d  jmp     loc_18004B441
0x18004b3a2  cmp     edi, 2
0x18004b3a5  jnz     loc_18004B441
0x18004b3ab  mov     [rsi], eax
0x18004b3ad  jmp     loc_18004B441
0x18004b3b2  xor     eax, eax
0x18004b3b4  xorps   xmm0, xmm0
0x18004b3b7  movups  xmmword ptr [rsp+78h+ppropvarDest], xmm0
0x18004b3bc  mov     [rsp+78h+var_48], rax
0x18004b3c1  cmp     r9w, [rdx]
0x18004b3c5  jz      short loc_18004B413
0x18004b3c7  mov     eax, 1
0x18004b3cc  cmp     r9w, ax
0x18004b3d0  jz      short loc_18004B413
0x18004b3d2  cmp     [rdx], ax
0x18004b3d5  jz      short loc_18004B413
0x18004b3d7  xor     r8d, r8d; flags
0x18004b3da  lea     rcx, [rsp+78h+ppropvarDest]; ppropvarDest
0x18004b3df  call    cs:__imp_PropVariantChangeType
0x18004b3e5  test    eax, eax
0x18004b3e7  js      short loc_18004B3F0
0x18004b3e9  lea     rbx, [rsp+78h+ppropvarDest]
0x18004b3ee  jmp     short loc_18004B413
0x18004b3f0  movzx   r9d, word ptr [rbx]; vt
0x18004b3f4  lea     rcx, [rsp+78h+ppropvarDest]; ppropvarDest
0x18004b3f9  xor     r8d, r8d; flags
0x18004b3fc  mov     rdx, r14; propvarSrc
0x18004b3ff  call    cs:__imp_PropVariantChangeType
0x18004b405  test    eax, eax
0x18004b407  lea     r8, [rsp+78h+ppropvarDest]
0x18004b40c  cmovs   r8, r14
0x18004b410  mov     r14, r8
0x18004b413  xor     r9d, r9d; flags
0x18004b416  xor     r8d, r8d; unit
0x18004b419  mov     rdx, r14; propvar2
0x18004b41c  mov     rcx, rbx; propvar1
0x18004b41f  call    cs:__imp_PropVariantCompareEx
0x18004b425  mov     r9, rsi; int *
0x18004b428  mov     r8d, ebp; int
0x18004b42b  mov     ecx, eax; int
0x18004b42d  mov     edx, edi; enum tagCONDITION_OPERATION
0x18004b42f  call    ?_SimpleOpCompareResult@@YAJHW4tagCONDITION_OPERATION@@HPEAH@Z; _SimpleOpCompareResult(int,tagCONDITION_OPERATION,int,int *)
0x18004b434  lea     rcx, [rsp+78h+ppropvarDest]; pvar
0x18004b439  mov     ebx, eax
0x18004b43b  call    cs:__imp_PropVariantClear
0x18004b441  mov     eax, ebx
0x18004b443  add     rsp, 48h
0x18004b447  pop     r15
0x18004b449  pop     r14
0x18004b44b  pop     rdi
0x18004b44c  pop     rsi
0x18004b44d  pop     rbp
0x18004b44e  pop     rbx
0x18004b44f  retn
```
