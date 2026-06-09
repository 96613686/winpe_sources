# StructuredQuery1::Interval::GetLimits(tagINTERVAL_LIMIT_KIND *,tagPROPVARIANT *,tagINTERVAL_LIMIT_KIND *,tagPROPVARIANT *)

- ea: `0x180054d70`
- end: `0x180054e33`
- name: `?GetLimits@Interval@StructuredQuery1@@UEAAJPEAW4tagINTERVAL_LIMIT_KIND@@PEAUtagPROPVARIANT@@01@Z`
- size: `195`
- prototype: `int(StructuredQuery1::Interval *__hidden this, enum tagINTERVAL_LIMIT_KIND *, struct tagPROPVARIANT *, enum tagINTERVAL_LIMIT_KIND *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180054d70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180054dea`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180054dfd`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180054dea`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180054dfd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054e1a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054e1a`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::Interval::GetLimits(
        const PROPVARIANT *this,
        enum tagINTERVAL_LIMIT_KIND *a2,
        PROPVARIANT *a3,
        enum tagINTERVAL_LIMIT_KIND *a4,
        PROPVARIANT *pvarDest)
{
  HRESULT v9; // ebx

  if ( a3 )
  {
    v9 = 0;
    *(_OWORD *)a3 = 0;
    a3[2] = 0;
  }
  else
  {
    v9 = -2147467261;
  }
  if ( pvarDest )
  {
    *(_OWORD *)pvarDest = 0;
    pvarDest[2] = 0;
  }
  else
  {
    v9 = -2147467261;
  }
  if ( a2 )
    *a2 = ILK_NEGATIVE_INFINITY;
  else
    v9 = -2147467261;
  if ( a4 )
  {
    *a4 = ILK_POSITIVE_INFINITY;
    if ( v9 >= 0 )
    {
      v9 = PropVariantCopy(a3, this + 3);
      if ( v9 >= 0 )
      {
        v9 = PropVariantCopy(pvarDest, this + 7);
        if ( v9 < 0 )
        {
          PropVariantClear(a3);
        }
        else
        {
          *a2 = *((enum tagINTERVAL_LIMIT_KIND *)this + 4);
          *a4 = *((enum tagINTERVAL_LIMIT_KIND *)this + 12);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180054d70  push    rbx
0x180054d72  push    rbp
0x180054d73  push    rsi
0x180054d74  push    rdi
0x180054d75  push    r14
0x180054d77  push    r15
0x180054d79  sub     rsp, 28h
0x180054d7d  mov     rsi, rcx
0x180054d80  mov     ecx, 80004003h
0x180054d85  mov     r14, r9
0x180054d88  mov     rdi, r8
0x180054d8b  mov     r15, rdx
0x180054d8e  test    r8, r8
0x180054d91  jz      short loc_180054DA4
0x180054d93  xor     ebx, ebx
0x180054d95  xorps   xmm0, xmm0
0x180054d98  xor     eax, eax
0x180054d9a  movups  xmmword ptr [r8], xmm0
0x180054d9e  mov     [r8+10h], rax
0x180054da2  jmp     short loc_180054DA6
0x180054da4  mov     ebx, ecx
0x180054da6  mov     rbp, [rsp+58h+pvarDest]
0x180054dae  test    rbp, rbp
0x180054db1  jz      short loc_180054DC2
0x180054db3  xorps   xmm0, xmm0
0x180054db6  xor     eax, eax
0x180054db8  movups  xmmword ptr [rbp+0], xmm0
0x180054dbc  mov     [rbp+10h], rax
0x180054dc0  jmp     short loc_180054DC4
0x180054dc2  mov     ebx, ecx
0x180054dc4  test    r15, r15
0x180054dc7  jz      short loc_180054DD1
0x180054dc9  mov     dword ptr [rdx], 2
0x180054dcf  jmp     short loc_180054DD3
0x180054dd1  mov     ebx, ecx
0x180054dd3  test    r14, r14
0x180054dd6  jz      short loc_180054E22
0x180054dd8  mov     dword ptr [r9], 3
0x180054ddf  test    ebx, ebx
0x180054de1  js      short loc_180054E24
0x180054de3  lea     rdx, [rsi+18h]; pvarSrc
0x180054de7  mov     rcx, rdi; pvarDest
0x180054dea  call    cs:__imp_PropVariantCopy
0x180054df0  mov     ebx, eax
0x180054df2  test    eax, eax
0x180054df4  js      short loc_180054E24
0x180054df6  lea     rdx, [rsi+38h]; pvarSrc
0x180054dfa  mov     rcx, rbp; pvarDest
0x180054dfd  call    cs:__imp_PropVariantCopy
0x180054e03  mov     ebx, eax
0x180054e05  test    eax, eax
0x180054e07  js      short loc_180054E17
0x180054e09  mov     eax, [rsi+10h]
0x180054e0c  mov     [r15], eax
0x180054e0f  mov     eax, [rsi+30h]
0x180054e12  mov     [r14], eax
0x180054e15  jmp     short loc_180054E24
0x180054e17  mov     rcx, rdi; pvar
0x180054e1a  call    cs:__imp_PropVariantClear
0x180054e20  jmp     short loc_180054E24
0x180054e22  mov     ebx, ecx
0x180054e24  mov     eax, ebx
0x180054e26  add     rsp, 28h
0x180054e2a  pop     r15
0x180054e2c  pop     r14
0x180054e2e  pop     rdi
0x180054e2f  pop     rsi
0x180054e30  pop     rbp
0x180054e31  pop     rbx
0x180054e32  retn
```
