# ConvertPropvarToLONG(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18000b3b0`
- end: `0x18000b4fc`
- name: `?ConvertPropvarToLONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `332`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b26c`
- `0x18001eef0`
- `0x18001ff78`
- `0x18002112c`

## callees

- `0x18000b3b0`
- `0x180021554`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b435`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b435`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b3c3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b3c3`

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
0x18000b3b0  mov     [rsp+arg_0], rbx
0x18000b3b5  push    rdi
0x18000b3b6  sub     rsp, 20h
0x18000b3ba  mov     rdi, rcx
0x18000b3bd  mov     rbx, rdx
0x18000b3c0  mov     rcx, rdx; pvar
0x18000b3c3  call    cs:__imp_PropVariantClear
0x18000b3ca  nop     dword ptr [rax+rax+00h]
0x18000b3cf  movzx   edx, word ptr [rdi]
0x18000b3d2  cmp     edx, 12h
0x18000b3d5  jnz     short loc_18000B3F1
0x18000b3d7  mov     word ptr [rbx], 3
0x18000b3dc  movzx   eax, word ptr [rdi+8]
0x18000b3e0  mov     [rbx+8], eax
0x18000b3e3  xor     eax, eax
0x18000b3e5  mov     rbx, [rsp+28h+arg_0]; jumptable 000000018000B413 default case, cases 4-15,18
0x18000b3ea  add     rsp, 20h
0x18000b3ee  pop     rdi
0x18000b3ef  retn
0x18000b3f1  add     edx, 0FFFFFFFEh; switch 20 cases
0x18000b3f4  mov     eax, 80070057h
0x18000b3f9  cmp     edx, 13h
0x18000b3fc  ja      short def_18000B413; jumptable 000000018000B413 default case, cases 4-15,18
0x18000b3fe  movsxd  r8, edx
0x18000b401  lea     rdx, __ImageBase
0x18000b408  mov     ecx, ds:(jpt_18000B413 - 180000000h)[rdx+r8*4]
0x18000b410  add     rcx, rdx
0x18000b413  jmp     rcx; switch jump
0x18000b419  mov     word ptr [rbx], 3; jumptable 000000018000B413 case 16
0x18000b41e  movsx   eax, byte ptr [rdi+8]
0x18000b422  jmp     short loc_18000B3E0
0x18000b424  mov     word ptr [rbx], 3; jumptable 000000018000B413 case 2
0x18000b429  movsx   eax, word ptr [rdi+8]
0x18000b42d  jmp     short loc_18000B3E0
0x18000b42f  mov     rdx, rdi; jumptable 000000018000B413 case 3
0x18000b432  mov     rcx, rbx; pvarDest
0x18000b435  call    cs:__imp_PropVariantCopy
0x18000b43c  nop     dword ptr [rax+rax+00h]
0x18000b441  jmp     short def_18000B413; jumptable 000000018000B413 default case, cases 4-15,18
0x18000b443  mov     rcx, [rdi+8]; jumptable 000000018000B413 case 20
0x18000b447  lea     rdx, [rbx+8]; plResult
0x18000b44b  call    LongLongToLong
0x18000b450  test    eax, eax
0x18000b452  js      short loc_18000B45B
0x18000b454  mov     word ptr [rbx], 3
0x18000b459  jmp     short def_18000B413; jumptable 000000018000B413 default case, cases 4-15,18
0x18000b45b  xor     eax, eax
0x18000b45d  mov     [rdx], eax
0x18000b45f  mov     eax, 80028CA1h
0x18000b464  jmp     def_18000B413; jumptable 000000018000B413 default case, cases 4-15,18
0x18000b469  mov     word ptr [rbx], 3; jumptable 000000018000B413 case 17
0x18000b46e  movzx   eax, byte ptr [rdi+8]
0x18000b472  jmp     loc_18000B3E0
0x18000b477  mov     eax, [rdi+8]; jumptable 000000018000B413 case 19
0x18000b47a  cmp     eax, 7FFFFFFFh
0x18000b47f  ja      short loc_18000B48E
0x18000b481  mov     [rbx+8], eax
0x18000b484  mov     word ptr [rbx], 3
0x18000b489  jmp     loc_18000B3E3
0x18000b48e  xor     eax, eax
0x18000b490  mov     [rbx+8], eax
0x18000b493  mov     eax, 80028CA1h
0x18000b498  jmp     def_18000B413; jumptable 000000018000B413 default case, cases 4-15,18
0x18000b49d  mov     rax, [rdi+8]; jumptable 000000018000B413 case 21
0x18000b4a1  cmp     rax, 7FFFFFFFh
0x18000b4a7  ja      short loc_18000B48E
0x18000b4a9  jmp     short loc_18000B481
```
