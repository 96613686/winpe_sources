# CheckRange(tagPROPVARIANT const *,int,int)

- ea: `0x18000b0f8`
- end: `0x18000b266`
- name: `?CheckRange@@YAJPEBUtagPROPVARIANT@@HH@Z`
- size: `366`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ac10`
- `0x18001ed1c`

## callees

- `0x18000b0f8`
- `0x180021554`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b241`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b241`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b125`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b183`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b125`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b183`

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
0x18000b0f8  push    rbp
0x18000b0fa  push    rbx
0x18000b0fb  push    rsi
0x18000b0fc  push    rdi
0x18000b0fd  push    r14
0x18000b0ff  mov     rbp, rsp
0x18000b102  sub     rsp, 40h
0x18000b106  mov     rdi, rcx
0x18000b109  xorps   xmm0, xmm0
0x18000b10c  xor     eax, eax
0x18000b10e  lea     rcx, [rbp+pvar]; pvar
0x18000b112  movups  xmmword ptr [rbp+pvar], xmm0
0x18000b116  mov     qword ptr [rbp+pvar+10h], rax
0x18000b11a  mov     esi, r8d
0x18000b11d  mov     r14d, edx
0x18000b120  mov     ebx, 80070057h
0x18000b125  call    cs:__imp_PropVariantClear
0x18000b12c  nop     dword ptr [rax+rax+00h]
0x18000b131  movzx   r9d, word ptr [rdi]
0x18000b135  sub     r9d, 2
0x18000b139  jz      loc_18000B254
0x18000b13f  sub     r9d, 1
0x18000b143  jz      loc_18000B23A
0x18000b149  sub     r9d, 0Dh
0x18000b14d  jz      loc_18000B228
0x18000b153  sub     r9d, 1
0x18000b157  jz      loc_18000B216
0x18000b15d  sub     r9d, 1
0x18000b161  jnz     short loc_18000B19D
0x18000b163  lea     eax, [r9+3]
0x18000b167  mov     word ptr [rbp+pvar], ax
0x18000b16b  movzx   eax, word ptr [rdi+8]
0x18000b16f  mov     dword ptr [rbp+pvar+8], eax
0x18000b172  xor     ebx, ebx
0x18000b174  cmp     dword ptr [rbp+pvar+8], r14d
0x18000b178  jl      short loc_18000B1E0
0x18000b17a  cmp     dword ptr [rbp+pvar+8], esi
0x18000b17d  jg      short loc_18000B1E0
0x18000b17f  lea     rcx, [rbp+pvar]; pvar
0x18000b183  call    cs:__imp_PropVariantClear
0x18000b18a  nop     dword ptr [rax+rax+00h]
0x18000b18f  mov     eax, ebx
0x18000b191  add     rsp, 40h
0x18000b195  pop     r14
0x18000b197  pop     rdi
0x18000b198  pop     rsi
0x18000b199  pop     rbx
0x18000b19a  pop     rbp
0x18000b19b  retn
0x18000b19d  sub     r9d, 1
0x18000b1a1  jz      short loc_18000B1C1
0x18000b1a3  sub     r9d, 1
0x18000b1a7  jz      short loc_18000B1E7
0x18000b1a9  cmp     r9d, 1
0x18000b1ad  jz      short loc_18000B1B5
0x18000b1af  test    ebx, ebx
0x18000b1b1  js      short loc_18000B17F
0x18000b1b3  jmp     short loc_18000B174
0x18000b1b5  mov     rax, [rdi+8]
0x18000b1b9  cmp     rax, 7FFFFFFFh
0x18000b1bf  jmp     short loc_18000B1C9
0x18000b1c1  mov     eax, [rdi+8]
0x18000b1c4  cmp     eax, 7FFFFFFFh
0x18000b1c9  ja      short loc_18000B1D9
0x18000b1cb  mov     dword ptr [rbp+pvar+8], eax
0x18000b1ce  mov     eax, 3
0x18000b1d3  mov     word ptr [rbp+pvar], ax
0x18000b1d7  jmp     short loc_18000B172
0x18000b1d9  mov     dword ptr [rbp+pvar+8], 0
0x18000b1e0  mov     ebx, 80028CA1h
0x18000b1e5  jmp     short loc_18000B17F
0x18000b1e7  mov     rcx, [rdi+8]; llOperand
0x18000b1eb  lea     rdx, [rbp+pvar+8]; plResult
0x18000b1ef  call    LongLongToLong
0x18000b1f4  mov     ebx, eax
0x18000b1f6  test    eax, eax
0x18000b1f8  js      short loc_18000B208
0x18000b1fa  mov     eax, 3
0x18000b1ff  mov     word ptr [rbp+pvar], ax
0x18000b203  jmp     loc_18000B174
0x18000b208  mov     dword ptr [rbp+pvar+8], 0
0x18000b20f  mov     ebx, 80028CA1h
0x18000b214  jmp     short loc_18000B1AF
0x18000b216  mov     eax, 3
0x18000b21b  mov     word ptr [rbp+pvar], ax
0x18000b21f  movzx   eax, byte ptr [rdi+8]
0x18000b223  jmp     loc_18000B16F
0x18000b228  mov     eax, 3
0x18000b22d  mov     word ptr [rbp+pvar], ax
0x18000b231  movsx   eax, byte ptr [rdi+8]
0x18000b235  jmp     loc_18000B16F
0x18000b23a  mov     rdx, rdi; pvarSrc
0x18000b23d  lea     rcx, [rbp+pvar]; pvarDest
0x18000b241  call    cs:__imp_PropVariantCopy
0x18000b248  nop     dword ptr [rax+rax+00h]
0x18000b24d  mov     ebx, eax
0x18000b24f  jmp     loc_18000B1AF
0x18000b254  mov     eax, 3
0x18000b259  mov     word ptr [rbp+pvar], ax
0x18000b25d  movsx   eax, word ptr [rdi+8]
0x18000b261  jmp     loc_18000B16F
```
