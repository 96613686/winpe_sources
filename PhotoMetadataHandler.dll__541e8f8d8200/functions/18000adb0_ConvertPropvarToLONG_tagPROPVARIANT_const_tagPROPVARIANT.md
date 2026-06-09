# ConvertPropvarToLONG(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18000adb0`
- end: `0x18000aee8`
- name: `?ConvertPropvarToLONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `312`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ac88`
- `0x18001e0b0`
- `0x18001f074`
- `0x180020150`

## callees

- `0x18000adb0`
- `0x180020538`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000ae2a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000ae2a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000adc3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000adc3`

## pseudocode

```c
int __fastcall ConvertPropvarToLONG(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)
{
  LONG uiVal; // eax
  int result; // eax
  _DWORD *v6; // rdx
  LARGE_INTEGER hVal; // rax

  PropVariantClear(pvarDest);
  if ( pvarSrc->vt == 18 )
  {
    pvarDest->vt = 3;
    uiVal = pvarSrc->uiVal;
LABEL_3:
    pvarDest->lVal = uiVal;
    return 0;
  }
  else
  {
    result = -2147024809;
    switch ( pvarSrc->vt )
    {
      case 2u:
        pvarDest->vt = 3;
        uiVal = pvarSrc->iVal;
        goto LABEL_3;
      case 3u:
        return PropVariantCopy(pvarDest, pvarSrc);
      case 0x10u:
        pvarDest->vt = 3;
        uiVal = pvarSrc->cVal;
        goto LABEL_3;
      case 0x11u:
        pvarDest->vt = 3;
        uiVal = pvarSrc->bVal;
        goto LABEL_3;
      case 0x13u:
        hVal.LowPart = pvarSrc->ulVal;
        if ( hVal.LowPart <= 0x7FFFFFFF )
          goto LABEL_14;
        goto LABEL_15;
      case 0x14u:
        result = LongLongToLong(pvarSrc->hVal.QuadPart, &pvarDest->lVal);
        if ( result < 0 )
        {
          *v6 = 0;
          return -2147316575;
        }
        else
        {
          pvarDest->vt = 3;
        }
        return result;
      case 0x15u:
        hVal = pvarSrc->hVal;
        if ( hVal.QuadPart <= 0x7FFFFFFFuLL )
        {
LABEL_14:
          pvarDest->lVal = hVal.LowPart;
          pvarDest->vt = 3;
          return 0;
        }
LABEL_15:
        pvarDest->lVal = 0;
        result = -2147316575;
        break;
      default:
        return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000adb0  mov     [rsp+arg_0], rbx
0x18000adb5  push    rdi
0x18000adb6  sub     rsp, 20h
0x18000adba  mov     rdi, rcx
0x18000adbd  mov     rbx, rdx
0x18000adc0  mov     rcx, rdx; pvar
0x18000adc3  call    cs:__imp_PropVariantClear
0x18000adc9  movzx   edx, word ptr [rdi]
0x18000adcc  cmp     edx, 12h
0x18000adcf  jnz     short loc_18000ADEA
0x18000add1  mov     word ptr [rbx], 3
0x18000add6  movzx   eax, word ptr [rdi+8]
0x18000adda  mov     [rbx+8], eax
0x18000addd  xor     eax, eax
0x18000addf  mov     rbx, [rsp+28h+arg_0]; jumptable 000000018000AE0C default case, cases 4-15,18
0x18000ade4  add     rsp, 20h
0x18000ade8  pop     rdi
0x18000ade9  retn
0x18000adea  add     edx, 0FFFFFFFEh; switch 20 cases
0x18000aded  mov     eax, 80070057h
0x18000adf2  cmp     edx, 13h
0x18000adf5  ja      short def_18000AE0C; jumptable 000000018000AE0C default case, cases 4-15,18
0x18000adf7  movsxd  r8, edx
0x18000adfa  lea     rdx, __ImageBase
0x18000ae01  mov     ecx, ds:(jpt_18000AE0C - 180000000h)[rdx+r8*4]
0x18000ae09  add     rcx, rdx
0x18000ae0c  jmp     rcx; switch jump
0x18000ae0e  mov     word ptr [rbx], 3; jumptable 000000018000AE0C case 16
0x18000ae13  movsx   eax, byte ptr [rdi+8]
0x18000ae17  jmp     short loc_18000ADDA
0x18000ae19  mov     word ptr [rbx], 3; jumptable 000000018000AE0C case 2
0x18000ae1e  movsx   eax, word ptr [rdi+8]
0x18000ae22  jmp     short loc_18000ADDA
0x18000ae24  mov     rdx, rdi; jumptable 000000018000AE0C case 3
0x18000ae27  mov     rcx, rbx; pvarDest
0x18000ae2a  call    cs:__imp_PropVariantCopy
0x18000ae30  jmp     short def_18000AE0C; jumptable 000000018000AE0C default case, cases 4-15,18
0x18000ae32  mov     rcx, [rdi+8]; jumptable 000000018000AE0C case 20
0x18000ae36  lea     rdx, [rbx+8]; plResult
0x18000ae3a  call    LongLongToLong
0x18000ae3f  test    eax, eax
0x18000ae41  js      short loc_18000AE4A
0x18000ae43  mov     word ptr [rbx], 3
0x18000ae48  jmp     short def_18000AE0C; jumptable 000000018000AE0C default case, cases 4-15,18
0x18000ae4a  xor     eax, eax
0x18000ae4c  mov     [rdx], eax
0x18000ae4e  mov     eax, 80028CA1h
0x18000ae53  jmp     short def_18000AE0C; jumptable 000000018000AE0C default case, cases 4-15,18
0x18000ae55  mov     word ptr [rbx], 3; jumptable 000000018000AE0C case 17
0x18000ae5a  movzx   eax, byte ptr [rdi+8]
0x18000ae5e  jmp     loc_18000ADDA
0x18000ae63  mov     eax, [rdi+8]; jumptable 000000018000AE0C case 19
0x18000ae66  cmp     eax, 7FFFFFFFh
0x18000ae6b  ja      short loc_18000AE7A
0x18000ae6d  mov     [rbx+8], eax
0x18000ae70  mov     word ptr [rbx], 3
0x18000ae75  jmp     loc_18000ADDD
0x18000ae7a  xor     eax, eax
0x18000ae7c  mov     [rbx+8], eax
0x18000ae7f  mov     eax, 80028CA1h
0x18000ae84  jmp     def_18000AE0C; jumptable 000000018000AE0C default case, cases 4-15,18
0x18000ae89  mov     rax, [rdi+8]; jumptable 000000018000AE0C case 21
0x18000ae8d  cmp     rax, 7FFFFFFFh
0x18000ae93  ja      short loc_18000AE7A
0x18000ae95  jmp     short loc_18000AE6D
```
