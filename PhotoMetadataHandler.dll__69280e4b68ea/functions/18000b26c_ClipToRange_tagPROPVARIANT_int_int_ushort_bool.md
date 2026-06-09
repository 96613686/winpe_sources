# ClipToRange(tagPROPVARIANT *,int,int,ushort,bool *)

- ea: `0x18000b26c`
- end: `0x18000b39d`
- name: `?ClipToRange@@YAJPEAUtagPROPVARIANT@@HHGPEA_N@Z`
- size: `305`
- prototype: `__int64 __usercall@<rax>(PROPVARIANT *pvarDest@<rcx>, int@<edx>, int@<r8d>, unsigned __int16@<r9w>, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ac10`
- `0x18001ed1c`

## callees

- `0x18000b26c`
- `0x18000b3b0`
- `0x1800203a4`
- `0x1800204c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b343`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b343`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b32a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b355`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b37d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b32a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b355`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b37d`

## pseudocode

```c
__int64 __fastcall ClipToRange(PROPVARIANT *pvarDest, LONG a2, LONG a3, unsigned __int16 a4, bool *a5)
{
  int v6; // r13d
  char v9; // si
  HRESULT v10; // ebx
  bool v11; // di
  int v12; // eax
  PROPVARIANT pvar; // [rsp+20h] [rbp-38h] BYREF
  PROPVARIANT pvarSrc; // [rsp+38h] [rbp-20h] BYREF

  v6 = a4;
  memset(&pvar, 0, sizeof(pvar));
  v9 = 0;
  v10 = ConvertPropvarToLONG(pvarDest, &pvar);
  v11 = 1;
  if ( v10 >= 0 )
  {
    if ( pvar.lVal >= a2 )
    {
      if ( pvar.lVal <= a3 )
        goto LABEL_17;
      pvar.lVal = a3;
    }
    else
    {
      pvar.lVal = a2;
    }
    v9 = 1;
    memset(&pvarSrc, 0, sizeof(pvarSrc));
    switch ( v6 )
    {
      case 3:
        v12 = ConvertPropvarToLONG(&pvar, &pvarSrc);
        break;
      case 18:
        v12 = ConvertPropvarToUSHORT(&pvar, &pvarSrc);
        break;
      case 19:
        v12 = ConvertPropvarToULONG(&pvar, &pvarSrc);
        break;
      default:
        v10 = -2147316575;
LABEL_16:
        PropVariantClear(&pvarSrc);
        goto LABEL_17;
    }
    v10 = v12;
    if ( v12 >= 0 )
    {
      v10 = PropVariantClear(pvarDest);
      if ( v10 >= 0 )
        v10 = PropVariantCopy(pvarDest, &pvarSrc);
    }
    goto LABEL_16;
  }
LABEL_17:
  if ( a5 )
  {
    if ( v10 < 0 || !v9 )
      v11 = 0;
    *a5 = v11;
  }
  PropVariantClear(&pvar);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000b26c  push    rbp
0x18000b26e  push    rbx
0x18000b26f  push    rsi
0x18000b270  push    rdi
0x18000b271  push    r12
0x18000b273  push    r13
0x18000b275  push    r14
0x18000b277  push    r15
0x18000b279  mov     rbp, rsp
0x18000b27c  sub     rsp, 58h
0x18000b280  mov     r14d, edx
0x18000b283  movzx   r13d, r9w
0x18000b287  xorps   xmm0, xmm0
0x18000b28a  lea     rdx, [rbp+pvar]; pvarDest
0x18000b28e  xor     eax, eax
0x18000b290  mov     r15d, r8d
0x18000b293  movups  xmmword ptr [rbp+pvar], xmm0
0x18000b297  mov     qword ptr [rbp+pvar+10h], rax
0x18000b29b  mov     r12, rcx
0x18000b29e  xor     sil, sil
0x18000b2a1  call    ?ConvertPropvarToLONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToLONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000b2a6  mov     ebx, eax
0x18000b2a8  mov     dil, 1
0x18000b2ab  test    eax, eax
0x18000b2ad  js      loc_18000B361
0x18000b2b3  cmp     dword ptr [rbp+pvar+8], r14d
0x18000b2b7  jge     short loc_18000B2BF
0x18000b2b9  mov     dword ptr [rbp+pvar+8], r14d
0x18000b2bd  jmp     short loc_18000B2CD
0x18000b2bf  cmp     dword ptr [rbp+pvar+8], r15d
0x18000b2c3  jle     loc_18000B361
0x18000b2c9  mov     dword ptr [rbp+pvar+8], r15d
0x18000b2cd  xor     eax, eax
0x18000b2cf  mov     ecx, r13d
0x18000b2d2  mov     qword ptr [rbp+pvarSrc+10h], rax
0x18000b2d6  xorps   xmm0, xmm0
0x18000b2d9  mov     sil, dil
0x18000b2dc  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x18000b2e0  sub     ecx, 3
0x18000b2e3  jz      short loc_18000B314
0x18000b2e5  sub     ecx, 0Fh
0x18000b2e8  jz      short loc_18000B305
0x18000b2ea  cmp     ecx, 1
0x18000b2ed  jz      short loc_18000B2F6
0x18000b2ef  mov     ebx, 80028CA1h
0x18000b2f4  jmp     short loc_18000B351
0x18000b2f6  lea     rdx, [rbp+pvarSrc]; pvarDest
0x18000b2fa  lea     rcx, [rbp+pvar]; pvarSrc
0x18000b2fe  call    ?ConvertPropvarToULONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToULONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000b303  jmp     short loc_18000B321
0x18000b305  lea     rdx, [rbp+pvarSrc]; pvarDest
0x18000b309  lea     rcx, [rbp+pvar]; pvarSrc
0x18000b30d  call    ?ConvertPropvarToUSHORT@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToUSHORT(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000b312  jmp     short loc_18000B321
0x18000b314  lea     rdx, [rbp+pvarSrc]; pvarDest
0x18000b318  lea     rcx, [rbp+pvar]; pvarSrc
0x18000b31c  call    ?ConvertPropvarToLONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToLONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000b321  mov     ebx, eax
0x18000b323  test    eax, eax
0x18000b325  js      short loc_18000B351
0x18000b327  mov     rcx, r12; pvar
0x18000b32a  call    cs:__imp_PropVariantClear
0x18000b331  nop     dword ptr [rax+rax+00h]
0x18000b336  mov     ebx, eax
0x18000b338  test    eax, eax
0x18000b33a  js      short loc_18000B351
0x18000b33c  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x18000b340  mov     rcx, r12; pvarDest
0x18000b343  call    cs:__imp_PropVariantCopy
0x18000b34a  nop     dword ptr [rax+rax+00h]
0x18000b34f  mov     ebx, eax
0x18000b351  lea     rcx, [rbp+pvarSrc]; pvar
0x18000b355  call    cs:__imp_PropVariantClear
0x18000b35c  nop     dword ptr [rax+rax+00h]
0x18000b361  mov     rax, [rbp+arg_20]
0x18000b365  test    rax, rax
0x18000b368  jz      short loc_18000B379
0x18000b36a  test    ebx, ebx
0x18000b36c  js      short loc_18000B373
0x18000b36e  test    sil, sil
0x18000b371  jnz     short loc_18000B376
0x18000b373  xor     dil, dil
0x18000b376  mov     [rax], dil
0x18000b379  lea     rcx, [rbp+pvar]; pvar
0x18000b37d  call    cs:__imp_PropVariantClear
0x18000b384  nop     dword ptr [rax+rax+00h]
0x18000b389  mov     eax, ebx
0x18000b38b  add     rsp, 58h
0x18000b38f  pop     r15
0x18000b391  pop     r14
0x18000b393  pop     r13
0x18000b395  pop     r12
0x18000b397  pop     rdi
0x18000b398  pop     rsi
0x18000b399  pop     rbx
0x18000b39a  pop     rbp
0x18000b39b  retn
```
