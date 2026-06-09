# CheckRange(tagPROPVARIANT const *,int,int)

- ea: `0x18000ab24`
- end: `0x18000ac7f`
- name: `?CheckRange@@YAJPEBUtagPROPVARIANT@@HH@Z`
- size: `347`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a680`
- `0x18001defc`

## callees

- `0x18000ab24`
- `0x180020538`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000ac60`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000ac60`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ab51`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000aba9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ab51`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000aba9`

## pseudocode

```c
__int64 __fastcall CheckRange(PROPVARIANT *pvarSrc, LONG a2, LONG a3)
{
  HRESULT v6; // ebx
  LONG iVal; // eax
  LARGE_INTEGER hVal; // rax
  bool v10; // cc
  PROPVARIANT pvar; // [rsp+20h] [rbp-20h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  v6 = -2147024809;
  PropVariantClear(&pvar);
  switch ( pvarSrc->vt )
  {
    case 2u:
      pvar.vt = 3;
      iVal = pvarSrc->iVal;
      goto LABEL_7;
    case 3u:
      v6 = PropVariantCopy(&pvar, pvarSrc);
      break;
    case 0x10u:
      pvar.vt = 3;
      iVal = pvarSrc->cVal;
      goto LABEL_7;
    case 0x11u:
      pvar.vt = 3;
      iVal = pvarSrc->bVal;
      goto LABEL_7;
    case 0x12u:
      pvar.vt = 3;
      iVal = pvarSrc->uiVal;
LABEL_7:
      pvar.lVal = iVal;
LABEL_8:
      v6 = 0;
      goto LABEL_9;
    case 0x13u:
      hVal.LowPart = pvarSrc->ulVal;
      v10 = hVal.LowPart <= 0x7FFFFFFF;
      goto LABEL_19;
    case 0x14u:
      v6 = LongLongToLong(pvarSrc->hVal.QuadPart, &pvar.lVal);
      if ( v6 >= 0 )
      {
        pvar.vt = 3;
        goto LABEL_9;
      }
      pvar.lVal = 0;
      v6 = -2147316575;
      break;
    case 0x15u:
      hVal = pvarSrc->hVal;
      v10 = hVal.QuadPart <= 0x7FFFFFFFuLL;
LABEL_19:
      if ( !v10 )
      {
        pvar.lVal = 0;
LABEL_22:
        v6 = -2147316575;
        goto LABEL_11;
      }
      pvar.lVal = hVal.LowPart;
      pvar.vt = 3;
      goto LABEL_8;
  }
  if ( v6 < 0 )
    goto LABEL_11;
LABEL_9:
  if ( pvar.lVal < a2 || pvar.lVal > a3 )
    goto LABEL_22;
LABEL_11:
  PropVariantClear(&pvar);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ab24  push    rbp
0x18000ab26  push    rbx
0x18000ab27  push    rsi
0x18000ab28  push    rdi
0x18000ab29  push    r14
0x18000ab2b  mov     rbp, rsp
0x18000ab2e  sub     rsp, 40h
0x18000ab32  mov     rdi, rcx
0x18000ab35  xorps   xmm0, xmm0
0x18000ab38  xor     eax, eax
0x18000ab3a  lea     rcx, [rbp+pvar]; pvar
0x18000ab3e  movups  xmmword ptr [rbp+pvar], xmm0
0x18000ab42  mov     qword ptr [rbp+pvar+10h], rax
0x18000ab46  mov     esi, r8d
0x18000ab49  mov     r14d, edx
0x18000ab4c  mov     ebx, 80070057h
0x18000ab51  call    cs:__imp_PropVariantClear
0x18000ab57  movzx   r9d, word ptr [rdi]
0x18000ab5b  sub     r9d, 2
0x18000ab5f  jz      loc_18000AC6D
0x18000ab65  sub     r9d, 1
0x18000ab69  jz      loc_18000AC59
0x18000ab6f  sub     r9d, 0Dh
0x18000ab73  jz      loc_18000AC47
0x18000ab79  sub     r9d, 1
0x18000ab7d  jz      loc_18000AC35
0x18000ab83  sub     r9d, 1
0x18000ab87  jnz     short loc_18000ABBC
0x18000ab89  lea     eax, [r9+3]
0x18000ab8d  mov     word ptr [rbp+pvar], ax
0x18000ab91  movzx   eax, word ptr [rdi+8]
0x18000ab95  mov     dword ptr [rbp+pvar+8], eax
0x18000ab98  xor     ebx, ebx
0x18000ab9a  cmp     dword ptr [rbp+pvar+8], r14d
0x18000ab9e  jl      short loc_18000ABFF
0x18000aba0  cmp     dword ptr [rbp+pvar+8], esi
0x18000aba3  jg      short loc_18000ABFF
0x18000aba5  lea     rcx, [rbp+pvar]; pvar
0x18000aba9  call    cs:__imp_PropVariantClear
0x18000abaf  mov     eax, ebx
0x18000abb1  add     rsp, 40h
0x18000abb5  pop     r14
0x18000abb7  pop     rdi
0x18000abb8  pop     rsi
0x18000abb9  pop     rbx
0x18000abba  pop     rbp
0x18000abbb  retn
0x18000abbc  sub     r9d, 1
0x18000abc0  jz      short loc_18000ABE0
0x18000abc2  sub     r9d, 1
0x18000abc6  jz      short loc_18000AC06
0x18000abc8  cmp     r9d, 1
0x18000abcc  jz      short loc_18000ABD4
0x18000abce  test    ebx, ebx
0x18000abd0  js      short loc_18000ABA5
0x18000abd2  jmp     short loc_18000AB9A
0x18000abd4  mov     rax, [rdi+8]
0x18000abd8  cmp     rax, 7FFFFFFFh
0x18000abde  jmp     short loc_18000ABE8
0x18000abe0  mov     eax, [rdi+8]
0x18000abe3  cmp     eax, 7FFFFFFFh
0x18000abe8  ja      short loc_18000ABF8
0x18000abea  mov     dword ptr [rbp+pvar+8], eax
0x18000abed  mov     eax, 3
0x18000abf2  mov     word ptr [rbp+pvar], ax
0x18000abf6  jmp     short loc_18000AB98
0x18000abf8  mov     dword ptr [rbp+pvar+8], 0
0x18000abff  mov     ebx, 80028CA1h
0x18000ac04  jmp     short loc_18000ABA5
0x18000ac06  mov     rcx, [rdi+8]; llOperand
0x18000ac0a  lea     rdx, [rbp+pvar+8]; plResult
0x18000ac0e  call    LongLongToLong
0x18000ac13  mov     ebx, eax
0x18000ac15  test    eax, eax
0x18000ac17  js      short loc_18000AC27
0x18000ac19  mov     eax, 3
0x18000ac1e  mov     word ptr [rbp+pvar], ax
0x18000ac22  jmp     loc_18000AB9A
0x18000ac27  mov     dword ptr [rbp+pvar+8], 0
0x18000ac2e  mov     ebx, 80028CA1h
0x18000ac33  jmp     short loc_18000ABCE
0x18000ac35  mov     eax, 3
0x18000ac3a  mov     word ptr [rbp+pvar], ax
0x18000ac3e  movzx   eax, byte ptr [rdi+8]
0x18000ac42  jmp     loc_18000AB95
0x18000ac47  mov     eax, 3
0x18000ac4c  mov     word ptr [rbp+pvar], ax
0x18000ac50  movsx   eax, byte ptr [rdi+8]
0x18000ac54  jmp     loc_18000AB95
0x18000ac59  mov     rdx, rdi; pvarSrc
0x18000ac5c  lea     rcx, [rbp+pvar]; pvarDest
0x18000ac60  call    cs:__imp_PropVariantCopy
0x18000ac66  mov     ebx, eax
0x18000ac68  jmp     loc_18000ABCE
0x18000ac6d  mov     eax, 3
0x18000ac72  mov     word ptr [rbp+pvar], ax
0x18000ac76  movsx   eax, word ptr [rdi+8]
0x18000ac7a  jmp     loc_18000AB95
```
