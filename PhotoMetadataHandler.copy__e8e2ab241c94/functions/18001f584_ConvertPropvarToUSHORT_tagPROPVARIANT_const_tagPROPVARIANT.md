# ConvertPropvarToUSHORT(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001f584`
- end: `0x18001f657`
- name: `?ConvertPropvarToUSHORT@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `211`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ac88`
- `0x18001e0b0`
- `0x18001f074`

## callees

- `0x18001f584`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001f620`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001f620`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f5a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f5a1`

## pseudocode

```c
__int64 __fastcall ConvertPropvarToUSHORT(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)
{
  unsigned int v4; // ebx
  LARGE_INTEGER hVal; // rax
  bool v6; // cc

  v4 = -2147024809;
  PropVariantClear(pvarDest);
  switch ( pvarSrc->vt )
  {
    case 2u:
      LOWORD(hVal.LowPart) = pvarSrc->iVal;
LABEL_18:
      v4 = 0;
      if ( SLOWORD(hVal.QuadPart) < 0 )
        goto LABEL_11;
      goto LABEL_19;
    case 3u:
LABEL_13:
      hVal.LowPart = pvarSrc->ulVal;
      v4 = 0;
      v6 = hVal.LowPart <= 0xFFFF;
LABEL_10:
      if ( !v6 )
      {
LABEL_11:
        pvarDest->iVal = 0;
        return (unsigned int)-2147316575;
      }
LABEL_19:
      pvarDest->iVal = hVal.LowPart;
      pvarDest->vt = 18;
      return v4;
    case 0xBu:
LABEL_16:
      pvarDest->vt = 18;
      v4 = 0;
      pvarDest->iVal = pvarSrc->bVal;
      return v4;
    case 0x10u:
      LOWORD(hVal.LowPart) = pvarSrc->cVal;
      goto LABEL_18;
    case 0x11u:
      goto LABEL_16;
    case 0x12u:
      return (unsigned int)PropVariantCopy(pvarDest, pvarSrc);
    case 0x13u:
      goto LABEL_13;
  }
  if ( (unsigned int)pvarSrc->vt - 20 <= 1 )
  {
    hVal = pvarSrc->hVal;
    v4 = 0;
    v6 = hVal.QuadPart <= 0xFFFFuLL;
    goto LABEL_10;
  }
  return v4;
}

```

## disassembly

```asm
0x18001f584  mov     [rsp+arg_0], rbx
0x18001f589  mov     [rsp+arg_8], rsi
0x18001f58e  push    rdi
0x18001f58f  sub     rsp, 20h
0x18001f593  mov     rsi, rcx
0x18001f596  mov     rdi, rdx
0x18001f599  mov     rcx, rdx; pvar
0x18001f59c  mov     ebx, 80070057h
0x18001f5a1  call    cs:__imp_PropVariantClear
0x18001f5a7  movzx   r8d, word ptr [rsi]
0x18001f5ab  sub     r8d, 2
0x18001f5af  jz      loc_18001F641
0x18001f5b5  sub     r8d, 1
0x18001f5b9  jz      short loc_18001F60E
0x18001f5bb  sub     r8d, 8
0x18001f5bf  jz      short loc_18001F630
0x18001f5c1  sub     r8d, 5
0x18001f5c5  jz      short loc_18001F62A
0x18001f5c7  sub     r8d, 1
0x18001f5cb  jz      short loc_18001F630
0x18001f5cd  sub     r8d, 1
0x18001f5d1  jz      short loc_18001F61A
0x18001f5d3  sub     r8d, 1
0x18001f5d7  jz      short loc_18001F60E
0x18001f5d9  sub     r8d, 1
0x18001f5dd  jz      short loc_18001F5E5
0x18001f5df  cmp     r8d, 1
0x18001f5e3  jnz     short loc_18001F5FC
0x18001f5e5  mov     rax, [rsi+8]
0x18001f5e9  xor     ebx, ebx
0x18001f5eb  cmp     rax, 0FFFFh
0x18001f5f1  jbe     short loc_18001F64C
0x18001f5f3  mov     [rdi+8], bx
0x18001f5f7  mov     ebx, 80028CA1h
0x18001f5fc  mov     rsi, [rsp+28h+arg_8]
0x18001f601  mov     eax, ebx
0x18001f603  mov     rbx, [rsp+28h+arg_0]
0x18001f608  add     rsp, 20h
0x18001f60c  pop     rdi
0x18001f60d  retn
0x18001f60e  mov     eax, [rsi+8]
0x18001f611  xor     ebx, ebx
0x18001f613  cmp     eax, 0FFFFh
0x18001f618  jmp     short loc_18001F5F1
0x18001f61a  mov     rdx, rsi; pvarSrc
0x18001f61d  mov     rcx, rdi; pvarDest
0x18001f620  call    cs:__imp_PropVariantCopy
0x18001f626  mov     ebx, eax
0x18001f628  jmp     short loc_18001F5FC
0x18001f62a  movsx   eax, byte ptr [rsi+8]
0x18001f62e  jmp     short loc_18001F645
0x18001f630  mov     word ptr [rdi], 12h
0x18001f635  xor     ebx, ebx
0x18001f637  movzx   eax, byte ptr [rsi+8]
0x18001f63b  mov     [rdi+8], ax
0x18001f63f  jmp     short loc_18001F5FC
0x18001f641  movzx   eax, word ptr [rsi+8]
0x18001f645  xor     ebx, ebx
0x18001f647  test    ax, ax
0x18001f64a  js      short loc_18001F5F3
0x18001f64c  mov     [rdi+8], ax
0x18001f650  mov     word ptr [rdi], 12h
0x18001f655  jmp     short loc_18001F5FC
```
