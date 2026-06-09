# ConvertPropvarToBYTE(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x1800200c0`
- end: `0x180020195`
- name: `?ConvertPropvarToBYTE@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `213`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ff78`

## callees

- `0x1800200c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180020141`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180020141`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800200dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800200dd`

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
0x1800200c0  mov     [rsp+arg_0], rbx
0x1800200c5  mov     [rsp+arg_8], rsi
0x1800200ca  push    rdi
0x1800200cb  sub     rsp, 20h
0x1800200cf  mov     rsi, rcx
0x1800200d2  mov     rdi, rdx
0x1800200d5  mov     rcx, rdx; pvar
0x1800200d8  mov     ebx, 80070057h
0x1800200dd  call    cs:__imp_PropVariantClear
0x1800200e4  nop     dword ptr [rax+rax+00h]
0x1800200e9  movzx   r8d, word ptr [rsi]
0x1800200ed  sub     r8d, 2
0x1800200f1  jz      short loc_180020160
0x1800200f3  sub     r8d, 1
0x1800200f7  jz      short loc_18002012D
0x1800200f9  sub     r8d, 0Dh
0x1800200fd  jz      short loc_180020151
0x1800200ff  sub     r8d, 1
0x180020103  jz      short loc_18002013B
0x180020105  sub     r8d, 1
0x180020109  jz      short loc_180020160
0x18002010b  sub     r8d, 1
0x18002010f  jz      short loc_18002012D
0x180020111  sub     r8d, 1
0x180020115  jz      short loc_18002011D
0x180020117  cmp     r8d, 1
0x18002011b  jnz     short loc_180020182
0x18002011d  mov     rcx, [rsi+8]
0x180020121  mov     eax, 0FFh
0x180020126  xor     ebx, ebx
0x180020128  cmp     rcx, rax
0x18002012b  jmp     short loc_18002016E
0x18002012d  mov     ecx, [rsi+8]
0x180020130  mov     eax, 0FFh
0x180020135  xor     ebx, ebx
0x180020137  cmp     ecx, eax
0x180020139  jmp     short loc_18002016E
0x18002013b  mov     rdx, rsi; pvarSrc
0x18002013e  mov     rcx, rdi; pvarDest
0x180020141  call    cs:__imp_PropVariantCopy
0x180020148  nop     dword ptr [rax+rax+00h]
0x18002014d  mov     ebx, eax
0x18002014f  jmp     short loc_180020182
0x180020151  mov     word ptr [rdi], 11h
0x180020156  xor     ebx, ebx
0x180020158  mov     al, [rsi+8]
0x18002015b  mov     [rdi+8], al
0x18002015e  jmp     short loc_180020182
0x180020160  movzx   ecx, word ptr [rsi+8]
0x180020164  mov     eax, 0FFh
0x180020169  xor     ebx, ebx
0x18002016b  cmp     cx, ax
0x18002016e  ja      short loc_18002017A
0x180020170  mov     [rdi+8], cl
0x180020173  mov     word ptr [rdi], 11h
0x180020178  jmp     short loc_180020182
0x18002017a  mov     [rdi+8], bl
0x18002017d  mov     ebx, 80028CA1h
0x180020182  mov     rsi, [rsp+28h+arg_8]
0x180020187  mov     eax, ebx
0x180020189  mov     rbx, [rsp+28h+arg_0]
0x18002018e  add     rsp, 20h
0x180020192  pop     rdi
0x180020193  retn
```
