# ConvertPropvarToULONG(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x1800203a4`
- end: `0x1800204b9`
- name: `?ConvertPropvarToULONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `277`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b26c`
- `0x18001eef0`
- `0x180021340`

## callees

- `0x18000ea70`
- `0x1800203a4`
- `0x180021580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002044d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002044d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800203c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800203c1`

## pseudocode

```c
__int64 __fastcall ConvertPropvarToULONG(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)
{
  unsigned int v4; // ebx
  HRESULT v5; // eax
  _DWORD *v6; // rdx
  LONG iVal; // eax
  int lVal; // eax

  v4 = -2147024809;
  PropVariantClear(pvarDest);
  switch ( pvarSrc->vt )
  {
    case 2u:
      pvarDest->vt = 19;
      iVal = pvarSrc->iVal;
      goto LABEL_23;
    case 3u:
      lVal = pvarSrc->lVal;
      if ( lVal < 0 )
      {
        pvarDest->lVal = 0;
        return (unsigned int)-2147316575;
      }
      pvarDest->lVal = lVal;
      pvarDest->vt = 19;
      return 0;
    case 0x10u:
      pvarDest->vt = 19;
      iVal = pvarSrc->cVal;
      goto LABEL_23;
    case 0x11u:
      pvarDest->vt = 19;
      iVal = pvarSrc->bVal;
      goto LABEL_23;
    case 0x12u:
      pvarDest->vt = 19;
      iVal = pvarSrc->uiVal;
LABEL_23:
      pvarDest->lVal = iVal;
      return 0;
    case 0x13u:
      return (unsigned int)PropVariantCopy(pvarDest, pvarSrc);
    case 0x14u:
      v5 = LongLongToULong(pvarSrc->hVal.QuadPart, &pvarDest->ulVal);
      goto LABEL_13;
    case 0x15u:
      v5 = ULongLongToULong(pvarSrc->uhVal.QuadPart, &pvarDest->ulVal);
LABEL_13:
      v4 = v5;
      if ( v5 >= 0 )
      {
        pvarDest->vt = 19;
        return v4;
      }
      *v6 = 0;
      return (unsigned int)-2147316575;
  }
  return v4;
}

```

## disassembly

```asm
0x1800203a4  mov     [rsp+arg_0], rbx
0x1800203a9  mov     [rsp+arg_8], rsi
0x1800203ae  push    rdi
0x1800203af  sub     rsp, 20h
0x1800203b3  mov     rsi, rcx
0x1800203b6  mov     rdi, rdx
0x1800203b9  mov     rcx, rdx; pvar
0x1800203bc  mov     ebx, 80070057h
0x1800203c1  call    cs:__imp_PropVariantClear
0x1800203c8  nop     dword ptr [rax+rax+00h]
0x1800203cd  movzx   r8d, word ptr [rsi]
0x1800203d1  sub     r8d, 2
0x1800203d5  jz      loc_180020498
0x1800203db  sub     r8d, 1
0x1800203df  jz      loc_18002047E
0x1800203e5  sub     r8d, 0Dh
0x1800203e9  jz      loc_180020473
0x1800203ef  sub     r8d, 1
0x1800203f3  jz      short loc_180020468
0x1800203f5  sub     r8d, 1
0x1800203f9  jz      short loc_18002045D
0x1800203fb  sub     r8d, 1
0x1800203ff  jz      short loc_180020447
0x180020401  sub     r8d, 1
0x180020405  jz      short loc_18002042D
0x180020407  cmp     r8d, 1
0x18002040b  jnz     loc_1800204A6
0x180020411  mov     rcx, [rsi+8]; ullOperand
0x180020415  lea     rdx, [rdi+8]; pulResult
0x180020419  call    ULongLongToULong
0x18002041e  jmp     short loc_18002043A
0x180020420  mov     dword ptr [rdx], 0
0x180020426  mov     ebx, 80028CA1h
0x18002042b  jmp     short loc_1800204A6
0x18002042d  mov     rcx, [rsi+8]; llOperand
0x180020431  lea     rdx, [rdi+8]; pulResult
0x180020435  call    LongLongToULong
0x18002043a  mov     ebx, eax
0x18002043c  test    eax, eax
0x18002043e  js      short loc_180020420
0x180020440  mov     word ptr [rdi], 13h
0x180020445  jmp     short loc_1800204A6
0x180020447  mov     rdx, rsi; pvarSrc
0x18002044a  mov     rcx, rdi; pvarDest
0x18002044d  call    cs:__imp_PropVariantCopy
0x180020454  nop     dword ptr [rax+rax+00h]
0x180020459  mov     ebx, eax
0x18002045b  jmp     short loc_1800204A6
0x18002045d  mov     word ptr [rdi], 13h
0x180020462  movzx   eax, word ptr [rsi+8]
0x180020466  jmp     short loc_1800204A1
0x180020468  mov     word ptr [rdi], 13h
0x18002046d  movzx   eax, byte ptr [rsi+8]
0x180020471  jmp     short loc_1800204A1
0x180020473  mov     word ptr [rdi], 13h
0x180020478  movsx   eax, byte ptr [rsi+8]
0x18002047c  jmp     short loc_1800204A1
0x18002047e  mov     eax, [rsi+8]
0x180020481  test    eax, eax
0x180020483  js      short loc_18002048F
0x180020485  mov     [rdi+8], eax
0x180020488  mov     word ptr [rdi], 13h
0x18002048d  jmp     short loc_1800204A4
0x18002048f  mov     dword ptr [rdi+8], 0
0x180020496  jmp     short loc_180020426
0x180020498  mov     word ptr [rdi], 13h
0x18002049d  movsx   eax, word ptr [rsi+8]
0x1800204a1  mov     [rdi+8], eax
0x1800204a4  xor     ebx, ebx
0x1800204a6  mov     rsi, [rsp+28h+arg_8]
0x1800204ab  mov     eax, ebx
0x1800204ad  mov     rbx, [rsp+28h+arg_0]
0x1800204b2  add     rsp, 20h
0x1800204b6  pop     rdi
0x1800204b7  retn
```
