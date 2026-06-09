# ConvertPropvarToUSHORT(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x1800204c0`
- end: `0x1800205a0`
- name: `?ConvertPropvarToUSHORT@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `224`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b26c`
- `0x18001eef0`
- `0x18001ff78`

## callees

- `0x1800204c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180020563`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180020563`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800204dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800204dd`

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
0x1800204c0  mov     [rsp+arg_0], rbx
0x1800204c5  mov     [rsp+arg_8], rsi
0x1800204ca  push    rdi
0x1800204cb  sub     rsp, 20h
0x1800204cf  mov     rsi, rcx
0x1800204d2  mov     rdi, rdx
0x1800204d5  mov     rcx, rdx; pvar
0x1800204d8  mov     ebx, 80070057h
0x1800204dd  call    cs:__imp_PropVariantClear
0x1800204e4  nop     dword ptr [rax+rax+00h]
0x1800204e9  movzx   r8d, word ptr [rsi]
0x1800204ed  sub     r8d, 2
0x1800204f1  jz      loc_18002058A
0x1800204f7  sub     r8d, 1
0x1800204fb  jz      short loc_180020551
0x1800204fd  sub     r8d, 8
0x180020501  jz      short loc_180020579
0x180020503  sub     r8d, 5
0x180020507  jz      short loc_180020573
0x180020509  sub     r8d, 1
0x18002050d  jz      short loc_180020579
0x18002050f  sub     r8d, 1
0x180020513  jz      short loc_18002055D
0x180020515  sub     r8d, 1
0x180020519  jz      short loc_180020551
0x18002051b  sub     r8d, 1
0x18002051f  jz      short loc_180020527
0x180020521  cmp     r8d, 1
0x180020525  jnz     short loc_18002053E
0x180020527  mov     rax, [rsi+8]
0x18002052b  xor     ebx, ebx
0x18002052d  cmp     rax, 0FFFFh
0x180020533  jbe     short loc_180020595
0x180020535  mov     [rdi+8], bx
0x180020539  mov     ebx, 80028CA1h
0x18002053e  mov     rsi, [rsp+28h+arg_8]
0x180020543  mov     eax, ebx
0x180020545  mov     rbx, [rsp+28h+arg_0]
0x18002054a  add     rsp, 20h
0x18002054e  pop     rdi
0x18002054f  retn
0x180020551  mov     eax, [rsi+8]
0x180020554  xor     ebx, ebx
0x180020556  cmp     eax, 0FFFFh
0x18002055b  jmp     short loc_180020533
0x18002055d  mov     rdx, rsi; pvarSrc
0x180020560  mov     rcx, rdi; pvarDest
0x180020563  call    cs:__imp_PropVariantCopy
0x18002056a  nop     dword ptr [rax+rax+00h]
0x18002056f  mov     ebx, eax
0x180020571  jmp     short loc_18002053E
0x180020573  movsx   eax, byte ptr [rsi+8]
0x180020577  jmp     short loc_18002058E
0x180020579  mov     word ptr [rdi], 12h
0x18002057e  xor     ebx, ebx
0x180020580  movzx   eax, byte ptr [rsi+8]
0x180020584  mov     [rdi+8], ax
0x180020588  jmp     short loc_18002053E
0x18002058a  movzx   eax, word ptr [rsi+8]
0x18002058e  xor     ebx, ebx
0x180020590  test    ax, ax
0x180020593  js      short loc_180020535
0x180020595  mov     [rdi+8], ax
0x180020599  mov     word ptr [rdi], 12h
0x18002059e  jmp     short loc_18002053E
```
