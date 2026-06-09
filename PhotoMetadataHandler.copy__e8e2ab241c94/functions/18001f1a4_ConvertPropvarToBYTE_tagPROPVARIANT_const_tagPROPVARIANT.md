# ConvertPropvarToBYTE(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001f1a4`
- end: `0x18001f26c`
- name: `?ConvertPropvarToBYTE@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `200`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001f074`

## callees

- `0x18001f1a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001f21f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001f21f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f1c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f1c1`

## pseudocode

```c
__int64 __fastcall ConvertPropvarToBYTE(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)
{
  unsigned int v4; // ebx
  LARGE_INTEGER hVal; // rcx
  bool v6; // cc

  v4 = -2147024809;
  PropVariantClear(pvarDest);
  switch ( pvarSrc->vt )
  {
    case 2u:
      goto LABEL_12;
    case 3u:
LABEL_9:
      hVal.LowPart = pvarSrc->ulVal;
      v4 = 0;
      v6 = hVal.LowPart <= 0xFF;
      goto LABEL_13;
    case 0x10u:
      pvarDest->vt = 17;
      v4 = 0;
      pvarDest->cVal = pvarSrc->cVal;
      return v4;
    case 0x11u:
      return (unsigned int)PropVariantCopy(pvarDest, pvarSrc);
    case 0x12u:
LABEL_12:
      LOWORD(hVal.LowPart) = pvarSrc->iVal;
      v4 = 0;
      v6 = LOWORD(hVal.LowPart) <= 0xFFu;
      goto LABEL_13;
    case 0x13u:
      goto LABEL_9;
  }
  if ( (unsigned int)pvarSrc->vt - 20 > 1 )
    return v4;
  hVal = pvarSrc->hVal;
  v4 = 0;
  v6 = hVal.QuadPart <= 0xFFuLL;
LABEL_13:
  if ( v6 )
  {
    pvarDest->cVal = hVal.LowPart;
    pvarDest->vt = 17;
  }
  else
  {
    pvarDest->cVal = 0;
    return (unsigned int)-2147316575;
  }
  return v4;
}

```

## disassembly

```asm
0x18001f1a4  mov     [rsp+arg_0], rbx
0x18001f1a9  mov     [rsp+arg_8], rsi
0x18001f1ae  push    rdi
0x18001f1af  sub     rsp, 20h
0x18001f1b3  mov     rsi, rcx
0x18001f1b6  mov     rdi, rdx
0x18001f1b9  mov     rcx, rdx; pvar
0x18001f1bc  mov     ebx, 80070057h
0x18001f1c1  call    cs:__imp_PropVariantClear
0x18001f1c7  movzx   r8d, word ptr [rsi]
0x18001f1cb  sub     r8d, 2
0x18001f1cf  jz      short loc_18001F238
0x18001f1d1  sub     r8d, 1
0x18001f1d5  jz      short loc_18001F20B
0x18001f1d7  sub     r8d, 0Dh
0x18001f1db  jz      short loc_18001F229
0x18001f1dd  sub     r8d, 1
0x18001f1e1  jz      short loc_18001F219
0x18001f1e3  sub     r8d, 1
0x18001f1e7  jz      short loc_18001F238
0x18001f1e9  sub     r8d, 1
0x18001f1ed  jz      short loc_18001F20B
0x18001f1ef  sub     r8d, 1
0x18001f1f3  jz      short loc_18001F1FB
0x18001f1f5  cmp     r8d, 1
0x18001f1f9  jnz     short loc_18001F25A
0x18001f1fb  mov     rcx, [rsi+8]
0x18001f1ff  mov     eax, 0FFh
0x18001f204  xor     ebx, ebx
0x18001f206  cmp     rcx, rax
0x18001f209  jmp     short loc_18001F246
0x18001f20b  mov     ecx, [rsi+8]
0x18001f20e  mov     eax, 0FFh
0x18001f213  xor     ebx, ebx
0x18001f215  cmp     ecx, eax
0x18001f217  jmp     short loc_18001F246
0x18001f219  mov     rdx, rsi; pvarSrc
0x18001f21c  mov     rcx, rdi; pvarDest
0x18001f21f  call    cs:__imp_PropVariantCopy
0x18001f225  mov     ebx, eax
0x18001f227  jmp     short loc_18001F25A
0x18001f229  mov     word ptr [rdi], 11h
0x18001f22e  xor     ebx, ebx
0x18001f230  mov     al, [rsi+8]
0x18001f233  mov     [rdi+8], al
0x18001f236  jmp     short loc_18001F25A
0x18001f238  movzx   ecx, word ptr [rsi+8]
0x18001f23c  mov     eax, 0FFh
0x18001f241  xor     ebx, ebx
0x18001f243  cmp     cx, ax
0x18001f246  ja      short loc_18001F252
0x18001f248  mov     [rdi+8], cl
0x18001f24b  mov     word ptr [rdi], 11h
0x18001f250  jmp     short loc_18001F25A
0x18001f252  mov     [rdi+8], bl
0x18001f255  mov     ebx, 80028CA1h
0x18001f25a  mov     rsi, [rsp+28h+arg_8]
0x18001f25f  mov     eax, ebx
0x18001f261  mov     rbx, [rsp+28h+arg_0]
0x18001f266  add     rsp, 20h
0x18001f26a  pop     rdi
0x18001f26b  retn
```
