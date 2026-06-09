# ConvertPropvarToULONG(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001f474`
- end: `0x18001f57d`
- name: `?ConvertPropvarToULONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `265`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ac88`
- `0x18001e0b0`
- `0x180020344`

## callees

- `0x18000e5a8`
- `0x18001f474`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001f529`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001f529`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f491`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f491`

## pseudocode

```c
__int64 __fastcall ConvertPropvarToULONG(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)
{
  HRESULT v4; // ebx
  LARGE_INTEGER hVal; // rax
  _DWORD *v6; // rdx
  LONG iVal; // eax

  v4 = -2147024809;
  PropVariantClear(pvarDest);
  switch ( pvarSrc->vt )
  {
    case 2u:
      pvarDest->vt = 19;
      iVal = pvarSrc->iVal;
      goto LABEL_23;
    case 3u:
      hVal.LowPart = pvarSrc->ulVal;
      if ( (hVal.LowPart & 0x80000000) == 0 )
        goto LABEL_10;
LABEL_11:
      pvarDest->lVal = 0;
      return (unsigned int)-2147316575;
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
      v4 = LongLongToULong(pvarSrc->hVal.QuadPart, &pvarDest->ulVal);
      if ( v4 >= 0 )
      {
        pvarDest->vt = 19;
        return (unsigned int)v4;
      }
      *v6 = 0;
      return (unsigned int)-2147316575;
    case 0x15u:
      hVal = pvarSrc->hVal;
      if ( hVal.QuadPart <= 0xFFFFFFFFuLL )
      {
LABEL_10:
        pvarDest->lVal = hVal.LowPart;
        pvarDest->vt = 19;
        return 0;
      }
      goto LABEL_11;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001f474  mov     [rsp+arg_0], rbx
0x18001f479  mov     [rsp+arg_8], rsi
0x18001f47e  push    rdi
0x18001f47f  sub     rsp, 20h
0x18001f483  mov     rsi, rcx
0x18001f486  mov     rdi, rdx
0x18001f489  mov     rcx, rdx; pvar
0x18001f48c  mov     ebx, 80070057h
0x18001f491  call    cs:__imp_PropVariantClear
0x18001f497  movzx   r8d, word ptr [rsi]
0x18001f49b  sub     r8d, 2
0x18001f49f  jz      loc_18001F55D
0x18001f4a5  sub     r8d, 1
0x18001f4a9  jz      loc_18001F554
0x18001f4af  sub     r8d, 0Dh
0x18001f4b3  jz      loc_18001F549
0x18001f4b9  sub     r8d, 1
0x18001f4bd  jz      short loc_18001F53E
0x18001f4bf  sub     r8d, 1
0x18001f4c3  jz      short loc_18001F533
0x18001f4c5  sub     r8d, 1
0x18001f4c9  jz      short loc_18001F523
0x18001f4cb  sub     r8d, 1
0x18001f4cf  jz      short loc_18001F501
0x18001f4d1  cmp     r8d, 1
0x18001f4d5  jnz     loc_18001F56B
0x18001f4db  mov     rax, [rsi+8]
0x18001f4df  mov     ecx, 0FFFFFFFFh
0x18001f4e4  cmp     rax, rcx
0x18001f4e7  ja      short loc_18001F4F3
0x18001f4e9  mov     [rdi+8], eax
0x18001f4ec  mov     word ptr [rdi], 13h
0x18001f4f1  jmp     short loc_18001F569
0x18001f4f3  mov     dword ptr [rdi+8], 0
0x18001f4fa  mov     ebx, 80028CA1h
0x18001f4ff  jmp     short loc_18001F56B
0x18001f501  mov     rcx, [rsi+8]; llOperand
0x18001f505  lea     rdx, [rdi+8]; pulResult
0x18001f509  call    LongLongToULong
0x18001f50e  mov     ebx, eax
0x18001f510  test    eax, eax
0x18001f512  js      short loc_18001F51B
0x18001f514  mov     word ptr [rdi], 13h
0x18001f519  jmp     short loc_18001F56B
0x18001f51b  mov     dword ptr [rdx], 0
0x18001f521  jmp     short loc_18001F4FA
0x18001f523  mov     rdx, rsi; pvarSrc
0x18001f526  mov     rcx, rdi; pvarDest
0x18001f529  call    cs:__imp_PropVariantCopy
0x18001f52f  mov     ebx, eax
0x18001f531  jmp     short loc_18001F56B
0x18001f533  mov     word ptr [rdi], 13h
0x18001f538  movzx   eax, word ptr [rsi+8]
0x18001f53c  jmp     short loc_18001F566
0x18001f53e  mov     word ptr [rdi], 13h
0x18001f543  movzx   eax, byte ptr [rsi+8]
0x18001f547  jmp     short loc_18001F566
0x18001f549  mov     word ptr [rdi], 13h
0x18001f54e  movsx   eax, byte ptr [rsi+8]
0x18001f552  jmp     short loc_18001F566
0x18001f554  mov     eax, [rsi+8]
0x18001f557  test    eax, eax
0x18001f559  js      short loc_18001F4F3
0x18001f55b  jmp     short loc_18001F4E9
0x18001f55d  mov     word ptr [rdi], 13h
0x18001f562  movsx   eax, word ptr [rsi+8]
0x18001f566  mov     [rdi+8], eax
0x18001f569  xor     ebx, ebx
0x18001f56b  mov     rsi, [rsp+28h+arg_8]
0x18001f570  mov     eax, ebx
0x18001f572  mov     rbx, [rsp+28h+arg_0]
0x18001f577  add     rsp, 20h
0x18001f57b  pop     rdi
0x18001f57c  retn
```
