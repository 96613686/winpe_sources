# BuildObjectArray(tagVARIANT,tagSAFEARRAY * *,ulong *)

- ea: `0x180014b3c`
- end: `0x180014d25`
- name: `?BuildObjectArray@@YAJUtagVARIANT@@PEAPEAUtagSAFEARRAY@@PEAK@Z`
- size: `489`
- prototype: `__int64 __fastcall(struct tagVARIANT *__struct_ptr, struct tagSAFEARRAY **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014d2c`

## callees

- `0x180014b3c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180014c7c`
- `msvcrt!_wcsicmp` at `0x180014c7c`
- `OLEAUT32!__imp_VariantInit` at `0x180014c44`
- `OLEAUT32!__imp_VariantInit` at `0x180014c44`
- `OLEAUT32!__imp_VariantClear` at `0x180014c99`
- `OLEAUT32!__imp_VariantClear` at `0x180014cc7`
- `OLEAUT32!__imp_VariantClear` at `0x180014c99`
- `OLEAUT32!__imp_VariantClear` at `0x180014cc7`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180014c15`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180014c15`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180014cf0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180014cf0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180014bee`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180014bee`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180014bd8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180014bd8`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180014c56`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180014c56`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180014caa`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180014caa`

## pseudocode

```c
__int64 __fastcall BuildObjectArray(struct tagVARIANT *a1, struct tagSAFEARRAY **a2, unsigned int *a3)
{
  VARTYPE vt; // ax
  unsigned int *v5; // r14
  SAFEARRAY *parray; // rcx
  HRESULT LBound; // ebx
  __int64 result; // rax
  SAFEARRAY *v10; // rdi
  const wchar_t *bstrVal; // r13
  unsigned int i; // ebx
  __int64 v13; // r12
  LONG plUbound; // [rsp+20h] [rbp-30h] BYREF
  LONG plLbound; // [rsp+24h] [rbp-2Ch] BYREF
  int pv; // [rsp+28h] [rbp-28h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  LONG v19; // [rsp+90h] [rbp+40h] BYREF
  unsigned int *v20; // [rsp+A0h] [rbp+50h]
  LONG rgIndices; // [rsp+A8h] [rbp+58h] BYREF

  v20 = a3;
  vt = a1->vt;
  v19 = 0;
  plLbound = 0;
  plUbound = 0;
  v5 = a3;
  rgIndices = 0;
  rgsabound = 0;
  pv = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( (vt & 0xFFF) != 0xC || (a1->vt & 0x2000) == 0 )
    return 2147500037LL;
  parray = a1->parray;
  if ( parray->cDims != 1 || !parray->rgsabound[0].cElements )
  {
    LBound = -2147467259;
LABEL_5:
    *a2 = 0;
    result = (unsigned int)LBound;
    *v5 = 0;
    return result;
  }
  LBound = SafeArrayGetLBound(parray, 1u, &plLbound);
  if ( LBound < 0 )
    goto LABEL_5;
  LBound = SafeArrayGetUBound(a1->parray, 1u, &plUbound);
  if ( LBound < 0 )
    goto LABEL_5;
  rgsabound.lLbound = plLbound;
  rgsabound.cElements = plUbound - plLbound + 1;
  v10 = SafeArrayCreate(3u, 1u, &rgsabound);
  if ( !v10 )
  {
    LBound = -2147024882;
    goto LABEL_5;
  }
  rgIndices = plLbound;
  if ( plLbound <= plUbound )
  {
    do
    {
      VariantInit(&pvarg);
      if ( SafeArrayGetElement(a1->parray, &rgIndices, &pvarg) >= 0 )
      {
        bstrVal = pvarg.bstrVal;
        for ( i = 0; ; ++i )
        {
          if ( i >= 0x10 )
          {
            pv = 0;
            VariantClear(&pvarg);
            goto LABEL_20;
          }
          v13 = 524LL * i;
          if ( !_wcsicmp(bstrVal, (const wchar_t *)((char *)&Filters + v13)) )
            break;
        }
        pv = *(_DWORD *)((char *)&Filters + v13 + 520);
        VariantClear(&pvarg);
        if ( SafeArrayPutElement(v10, &v19, &pv) >= 0 )
          ++v19;
      }
LABEL_20:
      ++rgIndices;
    }
    while ( rgIndices <= plUbound );
    v5 = v20;
  }
  if ( !v19 )
  {
    LBound = -2147467259;
    SafeArrayDestroy(v10);
    goto LABEL_5;
  }
  *v5 = v19;
  result = 0;
  *a2 = v10;
  return result;
}

```

## disassembly

```asm
0x180014b3c  mov     [rsp-38h+arg_8], rbx
0x180014b41  mov     [rsp-38h+arg_10], r8
0x180014b46  push    rbp
0x180014b47  push    rsi
0x180014b48  push    rdi
0x180014b49  push    r12
0x180014b4b  push    r13
0x180014b4d  push    r14
0x180014b4f  push    r15
0x180014b51  mov     rbp, rsp
0x180014b54  sub     rsp, 50h
0x180014b58  xor     r12d, r12d
0x180014b5b  xor     eax, eax
0x180014b5d  mov     qword ptr [rbp+pvarg+10h], rax
0x180014b61  mov     rsi, rcx
0x180014b64  movzx   eax, word ptr [rcx]
0x180014b67  xorps   xmm0, xmm0
0x180014b6a  mov     ecx, 0FFFh
0x180014b6f  mov     [rbp+arg_0], r12d
0x180014b73  and     ax, cx
0x180014b76  mov     [rbp+plLbound], r12d
0x180014b7a  mov     [rbp+plUbound], r12d
0x180014b7e  mov     r14, r8
0x180014b81  mov     [rbp+rgIndices], r12d
0x180014b85  mov     r15, rdx
0x180014b88  mov     qword ptr [rbp+rgsabound.cElements], r12
0x180014b8c  mov     [rbp+pv], r12d
0x180014b90  movups  xmmword ptr [rbp+pvarg], xmm0
0x180014b94  cmp     ax, 0Ch
0x180014b98  jnz     loc_180014D08
0x180014b9e  mov     eax, 2000h
0x180014ba3  test    [rsi], ax
0x180014ba6  jz      loc_180014D08
0x180014bac  mov     rcx, [rsi+8]; psa
0x180014bb0  lea     edi, [r12+1]
0x180014bb5  cmp     [rcx], di
0x180014bb8  jz      short loc_180014BCC
0x180014bba  mov     ebx, 80004005h
0x180014bbf  mov     [r15], r12
0x180014bc2  mov     eax, ebx
0x180014bc4  mov     [r14], r12d
0x180014bc7  jmp     loc_180014D0D
0x180014bcc  cmp     [rcx+18h], r12d
0x180014bd0  jz      short loc_180014BBA
0x180014bd2  lea     r8, [rbp+plLbound]; plLbound
0x180014bd6  mov     edx, edi; nDim
0x180014bd8  call    cs:__imp_SafeArrayGetLBound
0x180014bde  mov     ebx, eax
0x180014be0  test    eax, eax
0x180014be2  js      short loc_180014BBF
0x180014be4  mov     rcx, [rsi+8]; psa
0x180014be8  lea     r8, [rbp+plUbound]; plUbound
0x180014bec  mov     edx, edi; nDim
0x180014bee  call    cs:__imp_SafeArrayGetUBound
0x180014bf4  mov     ebx, eax
0x180014bf6  test    eax, eax
0x180014bf8  js      short loc_180014BBF
0x180014bfa  mov     eax, [rbp+plLbound]
0x180014bfd  lea     r8, [rbp+rgsabound]; rgsabound
0x180014c01  mov     ecx, [rbp+plUbound]
0x180014c04  mov     edx, edi; cDims
0x180014c06  sub     ecx, eax
0x180014c08  mov     [rbp+rgsabound.lLbound], eax
0x180014c0b  add     ecx, edi
0x180014c0d  mov     [rbp+rgsabound.cElements], ecx
0x180014c10  mov     ecx, 3; vt
0x180014c15  call    cs:__imp_SafeArrayCreate
0x180014c1b  mov     rdi, rax
0x180014c1e  test    rax, rax
0x180014c21  jnz     short loc_180014C2A
0x180014c23  mov     ebx, 8007000Eh
0x180014c28  jmp     short loc_180014BBF
0x180014c2a  mov     eax, [rbp+plLbound]
0x180014c2d  mov     [rbp+rgIndices], eax
0x180014c30  cmp     eax, [rbp+plUbound]
0x180014c33  jg      loc_180014CE2
0x180014c39  lea     r14, ?Filters@@3PAU_filters@@A; "user"
0x180014c40  lea     rcx, [rbp+pvarg]; pvarg
0x180014c44  call    cs:__imp_VariantInit
0x180014c4a  mov     rcx, [rsi+8]; psa
0x180014c4e  lea     r8, [rbp+pvarg]; pv
0x180014c52  lea     rdx, [rbp+rgIndices]; rgIndices
0x180014c56  call    cs:__imp_SafeArrayGetElement
0x180014c5c  test    eax, eax
0x180014c5e  js      short loc_180014CCD
0x180014c60  mov     r13, qword ptr [rbp+pvarg+8]
0x180014c64  mov     ebx, r12d
0x180014c67  cmp     ebx, 10h
0x180014c6a  jnb     short loc_180014CBC
0x180014c6c  mov     eax, ebx
0x180014c6e  mov     rcx, r13; String1
0x180014c71  imul    r12, rax, 20Ch
0x180014c78  lea     rdx, [r12+r14]; String2
0x180014c7c  call    cs:__imp__wcsicmp
0x180014c82  test    eax, eax
0x180014c84  jz      short loc_180014C8A
0x180014c86  inc     ebx
0x180014c88  jmp     short loc_180014C67
0x180014c8a  mov     eax, [r12+r14+208h]
0x180014c92  lea     rcx, [rbp+pvarg]; pvarg
0x180014c96  mov     [rbp+pv], eax
0x180014c99  call    cs:__imp_VariantClear
0x180014c9f  lea     r8, [rbp+pv]; pv
0x180014ca3  mov     rcx, rdi; psa
0x180014ca6  lea     rdx, [rbp+arg_0]; rgIndices
0x180014caa  call    cs:__imp_SafeArrayPutElement
0x180014cb0  xor     r12d, r12d
0x180014cb3  test    eax, eax
0x180014cb5  js      short loc_180014CCD
0x180014cb7  inc     [rbp+arg_0]
0x180014cba  jmp     short loc_180014CCD
0x180014cbc  xor     r12d, r12d
0x180014cbf  lea     rcx, [rbp+pvarg]; pvarg
0x180014cc3  mov     [rbp+pv], r12d
0x180014cc7  call    cs:__imp_VariantClear
0x180014ccd  mov     eax, [rbp+rgIndices]
0x180014cd0  inc     eax
0x180014cd2  mov     [rbp+rgIndices], eax
0x180014cd5  cmp     eax, [rbp+plUbound]
0x180014cd8  jle     loc_180014C40
0x180014cde  mov     r14, [rbp+arg_10]
0x180014ce2  cmp     [rbp+arg_0], r12d
0x180014ce6  jnz     short loc_180014CFB
0x180014ce8  mov     ebx, 80004005h
0x180014ced  mov     rcx, rdi; psa
0x180014cf0  call    cs:__imp_SafeArrayDestroy
0x180014cf6  jmp     loc_180014BBF
0x180014cfb  mov     eax, [rbp+arg_0]
0x180014cfe  mov     [r14], eax
0x180014d01  xor     eax, eax
0x180014d03  mov     [r15], rdi
0x180014d06  jmp     short loc_180014D0D
0x180014d08  mov     eax, 80004005h
0x180014d0d  mov     rbx, [rsp+50h+arg_8]
0x180014d15  add     rsp, 50h
0x180014d19  pop     r15
0x180014d1b  pop     r14
0x180014d1d  pop     r13
0x180014d1f  pop     r12
0x180014d21  pop     rdi
0x180014d22  pop     rsi
0x180014d23  pop     rbp
0x180014d24  retn
```
