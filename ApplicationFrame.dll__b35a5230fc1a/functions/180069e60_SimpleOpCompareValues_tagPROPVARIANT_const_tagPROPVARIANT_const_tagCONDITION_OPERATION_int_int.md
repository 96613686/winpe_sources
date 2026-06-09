# _SimpleOpCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,int,int *)

- ea: `0x180069e60`
- end: `0x180069f60`
- name: `?_SimpleOpCompareValues@@YAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@HPEAH@Z`
- size: `256`
- prototype: `__int64 __fastcall(PROPVARIANT *propvar2, PROPVARIANT *propvar1, enum tagCONDITION_OPERATION, int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180064250`

## callees

- `0x180069df0`
- `0x180069e60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180069f4b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180069f4b`
- `PROPSYS!PropVariantChangeType` at `0x180069eef`
- `PROPSYS!PropVariantChangeType` at `0x180069f0f`
- `PROPSYS!PropVariantChangeType` at `0x180069eef`
- `PROPSYS!PropVariantChangeType` at `0x180069f0f`
- `PROPSYS!PropVariantCompareEx` at `0x180069f2f`
- `PROPSYS!PropVariantCompareEx` at `0x180069f2f`

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
0x180069e60  push    rbx
0x180069e62  push    rbp
0x180069e63  push    rsi
0x180069e64  push    rdi
0x180069e65  push    r14
0x180069e67  push    r15
0x180069e69  sub     rsp, 48h
0x180069e6d  mov     rsi, [rsp+78h+arg_20]
0x180069e75  xor     r15d, r15d
0x180069e78  mov     ebp, r9d
0x180069e7b  mov     edi, r8d
0x180069e7e  movzx   r9d, word ptr [rcx]; vt
0x180069e82  mov     rbx, rdx
0x180069e85  mov     r14, rcx
0x180069e88  mov     [rsi], r15d
0x180069e8b  cmp     r9w, [rdx]
0x180069e8f  jz      short loc_180069EC2
0x180069e91  test    r9w, r9w
0x180069e95  jz      short loc_180069E9D
0x180069e97  cmp     [rdx], r15w
0x180069e9b  jnz     short loc_180069EC2
0x180069e9d  mov     ebx, r15d
0x180069ea0  mov     eax, 1
0x180069ea5  test    ebp, ebp
0x180069ea7  jz      short loc_180069EB2
0x180069ea9  cmp     edi, eax
0x180069eab  jz      short loc_180069EBB
0x180069ead  jmp     loc_180069F51
0x180069eb2  cmp     edi, 2
0x180069eb5  jnz     loc_180069F51
0x180069ebb  mov     [rsi], eax
0x180069ebd  jmp     loc_180069F51
0x180069ec2  xor     eax, eax
0x180069ec4  xorps   xmm0, xmm0
0x180069ec7  movups  xmmword ptr [rsp+78h+ppropvarDest], xmm0
0x180069ecc  mov     [rsp+78h+var_48], rax
0x180069ed1  cmp     r9w, [rdx]
0x180069ed5  jz      short loc_180069F23
0x180069ed7  mov     eax, 1
0x180069edc  cmp     r9w, ax
0x180069ee0  jz      short loc_180069F23
0x180069ee2  cmp     [rdx], ax
0x180069ee5  jz      short loc_180069F23
0x180069ee7  xor     r8d, r8d; flags
0x180069eea  lea     rcx, [rsp+78h+ppropvarDest]; ppropvarDest
0x180069eef  call    cs:__imp_PropVariantChangeType
0x180069ef5  test    eax, eax
0x180069ef7  js      short loc_180069F00
0x180069ef9  lea     rbx, [rsp+78h+ppropvarDest]
0x180069efe  jmp     short loc_180069F23
0x180069f00  movzx   r9d, word ptr [rbx]; vt
0x180069f04  lea     rcx, [rsp+78h+ppropvarDest]; ppropvarDest
0x180069f09  xor     r8d, r8d; flags
0x180069f0c  mov     rdx, r14; propvarSrc
0x180069f0f  call    cs:__imp_PropVariantChangeType
0x180069f15  test    eax, eax
0x180069f17  lea     r8, [rsp+78h+ppropvarDest]
0x180069f1c  cmovs   r8, r14
0x180069f20  mov     r14, r8
0x180069f23  xor     r9d, r9d; flags
0x180069f26  xor     r8d, r8d; unit
0x180069f29  mov     rdx, r14; propvar2
0x180069f2c  mov     rcx, rbx; propvar1
0x180069f2f  call    cs:__imp_PropVariantCompareEx
0x180069f35  mov     r9, rsi; int *
0x180069f38  mov     r8d, ebp; int
0x180069f3b  mov     ecx, eax; int
0x180069f3d  mov     edx, edi; enum tagCONDITION_OPERATION
0x180069f3f  call    ?_SimpleOpCompareResult@@YAJHW4tagCONDITION_OPERATION@@HPEAH@Z; _SimpleOpCompareResult(int,tagCONDITION_OPERATION,int,int *)
0x180069f44  lea     rcx, [rsp+78h+ppropvarDest]; pvar
0x180069f49  mov     ebx, eax
0x180069f4b  call    cs:__imp_PropVariantClear
0x180069f51  mov     eax, ebx
0x180069f53  add     rsp, 48h
0x180069f57  pop     r15
0x180069f59  pop     r14
0x180069f5b  pop     rdi
0x180069f5c  pop     rsi
0x180069f5d  pop     rbp
0x180069f5e  pop     rbx
0x180069f5f  retn
```
