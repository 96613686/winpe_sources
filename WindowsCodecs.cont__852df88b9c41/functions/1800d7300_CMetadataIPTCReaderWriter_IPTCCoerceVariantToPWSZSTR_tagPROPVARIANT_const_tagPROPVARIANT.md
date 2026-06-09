# CMetadataIPTCReaderWriter::IPTCCoerceVariantToPWSZSTR(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x1800d7300`
- end: `0x1800d7417`
- name: `?IPTCCoerceVariantToPWSZSTR@CMetadataIPTCReaderWriter@@AEAAJPEBUtagPROPVARIANT@@PEAU2@@Z`
- size: `279`
- prototype: `int(CMetadataIPTCReaderWriter *__hidden this, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d71ac`

## callees

- `0x180087780`
- `0x1800bb784`
- `0x1800d7300`
- `0x18017b528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800d732e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800d732e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d73c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d73c9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800d7406`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800d7406`
- `OLEAUT32!__imp_SysStringLen` at `0x1800d73b8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800d73b8`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800d7396`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800d7396`

## pseudocode

```c
__int64 __fastcall CMetadataIPTCReaderWriter::IPTCCoerceVariantToPWSZSTR(
        CMetadataIPTCReaderWriter *this,
        const VARIANTARG *a2,
        PROPVARIANT *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  const CHAR *pcVal; // rcx
  int v7; // ecx
  SIZE_T v8; // rsi
  void *v9; // rax
  VARIANTARG pvargDest; // [rsp+20h] [rbp-48h] BYREF

  *(_OWORD *)a3 = 0;
  a3[2] = 0;
  memset(&pvargDest, 0, sizeof(pvargDest));
  if ( a2->vt != 31 )
  {
    if ( a2->vt == 30 )
    {
      pcVal = a2->pcVal;
      v5 = 0;
      if ( pcVal )
      {
        v4 = CoerceAnsiStrToWideStr(pcVal, (unsigned __int16 **)a3 + 1);
        v5 = v4;
        if ( v4 < 0 )
        {
          if ( !(_DWORD)g_doStackCaptures )
            goto LABEL_20;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v4 = VariantChangeType(&pvargDest, a2, 0, 8u);
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_20;
        goto LABEL_12;
      }
      v8 = 2 * SysStringLen(pvargDest.bstrVal) + 2;
      v9 = CoTaskMemAlloc(v8);
      a3[1] = v9;
      if ( !v9 )
      {
        v5 = -2147024882;
        if ( (_DWORD)g_doStackCaptures )
        {
          v7 = -2147024882;
          goto LABEL_17;
        }
        goto LABEL_20;
      }
      memcpy_0(v9, pvargDest.bstrVal, v8);
    }
    *(_WORD *)a3 = 31;
    goto LABEL_20;
  }
  v4 = PropVariantCopy(a3, (const PROPVARIANT *)a2);
  v5 = v4;
  if ( v4 < 0 && (_DWORD)g_doStackCaptures )
  {
LABEL_12:
    v7 = v4;
LABEL_17:
    DoStackCapture(v7);
  }
LABEL_20:
  PropVariantClear((PROPVARIANT *)&pvargDest);
  return v5;
}

```

## disassembly

```asm
0x1800d7300  push    rbx
0x1800d7302  push    rbp
0x1800d7303  push    rsi
0x1800d7304  push    rdi
0x1800d7305  sub     rsp, 48h
0x1800d7309  xor     eax, eax
0x1800d730b  xorps   xmm0, xmm0
0x1800d730e  movups  xmmword ptr [r8], xmm0
0x1800d7312  mov     [r8+10h], rax
0x1800d7316  mov     rdi, r8
0x1800d7319  movups  xmmword ptr [rsp+68h+pvargDest], xmm0
0x1800d731e  lea     ebp, [rax+1Fh]
0x1800d7321  mov     qword ptr [rsp+68h+pvargDest+10h], rax
0x1800d7326  cmp     bp, [rdx]
0x1800d7329  jnz     short loc_1800D734D
0x1800d732b  mov     rcx, r8; pvarDest
0x1800d732e  call    cs:__imp_PropVariantCopy
0x1800d7334  mov     ebx, eax
0x1800d7336  test    eax, eax
0x1800d7338  jns     loc_1800D7401
0x1800d733e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d7345  jz      loc_1800D7401
0x1800d734b  jmp     short loc_1800D73AB
0x1800d734d  mov     eax, 1Eh
0x1800d7352  cmp     ax, [rdx]
0x1800d7355  jnz     short loc_1800D7388
0x1800d7357  mov     rcx, [rdx+8]; lpMultiByteStr
0x1800d735b  xor     ebx, ebx
0x1800d735d  test    rcx, rcx
0x1800d7360  jz      loc_1800D73FE
0x1800d7366  lea     rdx, [r8+8]; unsigned __int16 **
0x1800d736a  call    ?CoerceAnsiStrToWideStr@@YAJPEBDPEAPEAGIH@Z; CoerceAnsiStrToWideStr(char const *,ushort * *,uint,int)
0x1800d736f  mov     ebx, eax
0x1800d7371  test    eax, eax
0x1800d7373  jns     loc_1800D73FE
0x1800d7379  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d7380  jnz     short loc_1800D73AB
0x1800d7382  test    eax, eax
0x1800d7384  js      short loc_1800D7401
0x1800d7386  jmp     short loc_1800D73FE
0x1800d7388  mov     r9d, 8; vt
0x1800d738e  lea     rcx, [rsp+68h+pvargDest]; pvargDest
0x1800d7393  xor     r8d, r8d; wFlags
0x1800d7396  call    cs:__imp_VariantChangeType
0x1800d739c  mov     ebx, eax
0x1800d739e  test    eax, eax
0x1800d73a0  jns     short loc_1800D73B3
0x1800d73a2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d73a9  jz      short loc_1800D73AF
0x1800d73ab  mov     ecx, eax
0x1800d73ad  jmp     short loc_1800D73E7
0x1800d73af  test    eax, eax
0x1800d73b1  js      short loc_1800D7401
0x1800d73b3  mov     rcx, qword ptr [rsp+68h+pvargDest+8]; pbstr
0x1800d73b8  call    cs:__imp_SysStringLen
0x1800d73be  lea     eax, ds:2[rax*2]
0x1800d73c5  mov     ecx, eax; cb
0x1800d73c7  mov     esi, eax
0x1800d73c9  call    cs:__imp_CoTaskMemAlloc
0x1800d73cf  mov     [rdi+8], rax
0x1800d73d3  test    rax, rax
0x1800d73d6  jnz     short loc_1800D73EE
0x1800d73d8  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d73de  mov     ebx, 8007000Eh
0x1800d73e3  jz      short loc_1800D7401
0x1800d73e5  mov     ecx, ebx; int
0x1800d73e7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d73ec  jmp     short loc_1800D7401
0x1800d73ee  mov     rdx, qword ptr [rsp+68h+pvargDest+8]; Src
0x1800d73f3  mov     r8, rsi; Size
0x1800d73f6  mov     rcx, rax; void *
0x1800d73f9  call    memcpy_0
0x1800d73fe  mov     [rdi], bp
0x1800d7401  lea     rcx, [rsp+68h+pvargDest]; pvar
0x1800d7406  call    cs:__imp_PropVariantClear
0x1800d740c  mov     eax, ebx
0x1800d740e  add     rsp, 48h
0x1800d7412  pop     rdi
0x1800d7413  pop     rsi
0x1800d7414  pop     rbp
0x1800d7415  pop     rbx
0x1800d7416  retn
```
