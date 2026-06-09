# CMetadataIPTCReaderWriter::CreateVariantFromVariantAndDesc(tagPROPVARIANT const *,CMetadataIPTCReaderWriter::DataSetDesc const *,tagPROPVARIANT *)

- ea: `0x1800d9c9c`
- end: `0x1800d9dfa`
- name: `?CreateVariantFromVariantAndDesc@CMetadataIPTCReaderWriter@@AEAAJPEBUtagPROPVARIANT@@PEBUDataSetDesc@1@PEAU2@@Z`
- size: `350`
- prototype: `int(CMetadataIPTCReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct CMetadataIPTCReaderWriter::DataSetDesc *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800d9b8c`

## callees

- `0x180064b00`
- `0x1800bd9d4`
- `0x1800d9c9c`
- `0x1800d9e00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800d9d63`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800d9dcc`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800d9d63`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800d9dcc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800d9d20`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800d9d20`

## pseudocode

```c
__int64 __fastcall CMetadataIPTCReaderWriter::CreateVariantFromVariantAndDesc(
        CMetadataIPTCReaderWriter *this,
        const PROPVARIANT *a2,
        const struct CMetadataIPTCReaderWriter::DataSetDesc *a3,
        PROPVARIANT *a4)
{
  int v4; // edi
  VARTYPE v5; // ax
  CMetadataIPTCReaderWriter *v7; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  bool v11; // zf
  int v12; // ecx
  VARTYPE v13; // cx
  unsigned __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  *(_OWORD *)a4 = 0;
  a4[2] = 0;
  v4 = -1;
  v5 = *(_WORD *)a2;
  v7 = (CMetadataIPTCReaderWriter *)*(unsigned __int16 *)a2;
  if ( a3 )
  {
    v7 = (CMetadataIPTCReaderWriter *)*((unsigned __int16 *)a3 + 8);
    v4 = *((_DWORD *)a3 + 5);
  }
  if ( (_WORD)v7 != 30 )
  {
    if ( v4 == -1 || v4 > 1 )
    {
      if ( v5 != ((unsigned __int16)v7 | 0x1000) )
        goto LABEL_17;
      if ( v4 != -1 && *((_DWORD *)a2 + 2) != v4 )
        goto LABEL_10;
      if ( (unsigned __int16)(v5 - 4113) > 2u )
      {
LABEL_17:
        v10 = -2003292274;
        goto LABEL_11;
      }
      v9 = PropVariantCopy(a4, a2);
      v10 = v9;
      if ( v9 >= 0 || !(_DWORD)g_doStackCaptures )
        return v10;
    }
    else
    {
      if ( (unsigned __int16)(v5 - 17) > 2u )
        goto LABEL_17;
      v9 = PropVariantCopy(a4, a2);
      v10 = v9;
      if ( v9 >= 0 )
      {
        if ( !a3 )
          return v10;
        v13 = *((_WORD *)a3 + 8);
        if ( (unsigned __int16)(v13 - 17) <= 2u )
        {
          *(_WORD *)a4 = v13;
          return v10;
        }
        v10 = -2003292274;
        v11 = (_DWORD)g_doStackCaptures == 0;
        goto LABEL_12;
      }
      if ( !(_DWORD)g_doStackCaptures )
        return v10;
    }
LABEL_31:
    v12 = v9;
    goto LABEL_32;
  }
  v9 = CMetadataIPTCReaderWriter::IPTCCoerceVariantToPWSZSTR(v7, (const VARIANTARG *)a2, a4, (int)a4);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      return v10;
    goto LABEL_31;
  }
  if ( v4 != -1 && (int)StringCchLengthW((const unsigned __int16 *)a4[1], v4 + 1, &v15) < 0 )
  {
    PropVariantClear(a4);
LABEL_10:
    v10 = -2003292350;
LABEL_11:
    v11 = (_DWORD)g_doStackCaptures == 0;
LABEL_12:
    if ( !v11 )
    {
      v12 = v10;
LABEL_32:
      DoStackCapture(v12);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800d9c9c  push    rbx
0x1800d9c9e  push    rbp
0x1800d9c9f  push    rsi
0x1800d9ca0  push    rdi
0x1800d9ca1  sub     rsp, 28h
0x1800d9ca5  xor     eax, eax
0x1800d9ca7  xorps   xmm0, xmm0
0x1800d9caa  movups  xmmword ptr [r9], xmm0
0x1800d9cae  mov     [r9+10h], rax
0x1800d9cb2  or      edi, 0FFFFFFFFh
0x1800d9cb5  movzx   eax, word ptr [rdx]
0x1800d9cb8  mov     rsi, r9
0x1800d9cbb  movzx   ecx, ax
0x1800d9cbe  mov     rbp, r8
0x1800d9cc1  test    r8, r8
0x1800d9cc4  jz      short loc_1800D9CCF
0x1800d9cc6  movzx   ecx, word ptr [r8+10h]; this
0x1800d9ccb  mov     edi, [r8+14h]
0x1800d9ccf  cmp     cx, 1Eh
0x1800d9cd3  jnz     short loc_1800D9D45
0x1800d9cd5  mov     r8, rsi; struct tagPROPVARIANT *
0x1800d9cd8  call    ?IPTCCoerceVariantToPWSZSTR@CMetadataIPTCReaderWriter@@AEAAJPEBUtagPROPVARIANT@@PEAU2@@Z; CMetadataIPTCReaderWriter::IPTCCoerceVariantToPWSZSTR(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800d9cdd  mov     ebx, eax
0x1800d9cdf  test    eax, eax
0x1800d9ce1  jns     short loc_1800D9CF8
0x1800d9ce3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d9cea  jnz     loc_1800D9DE7
0x1800d9cf0  test    eax, eax
0x1800d9cf2  js      loc_1800D9DEE
0x1800d9cf8  cmp     edi, 0FFFFFFFFh
0x1800d9cfb  jz      loc_1800D9DEE
0x1800d9d01  mov     rcx, [rsi+8]; unsigned __int16 *
0x1800d9d05  lea     eax, [rdi+1]
0x1800d9d08  movsxd  rdx, eax; unsigned __int64
0x1800d9d0b  lea     r8, [rsp+48h+arg_0]; unsigned __int64 *
0x1800d9d10  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800d9d15  test    eax, eax
0x1800d9d17  jns     loc_1800D9DEE
0x1800d9d1d  mov     rcx, rsi; pvar
0x1800d9d20  call    cs:__imp_PropVariantClear
0x1800d9d27  nop     dword ptr [rax+rax+00h]
0x1800d9d2c  mov     ebx, 88982F42h
0x1800d9d31  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d9d38  jz      loc_1800D9DEE
0x1800d9d3e  mov     ecx, ebx
0x1800d9d40  jmp     loc_1800D9DE9
0x1800d9d45  cmp     edi, 0FFFFFFFFh
0x1800d9d48  jz      short loc_1800D9DA3
0x1800d9d4a  cmp     edi, 1
0x1800d9d4d  jg      short loc_1800D9DA3
0x1800d9d4f  sub     ax, 11h
0x1800d9d53  cmp     ax, 2
0x1800d9d57  jbe     short loc_1800D9D60
0x1800d9d59  mov     ebx, 88982F8Eh
0x1800d9d5e  jmp     short loc_1800D9D31
0x1800d9d60  mov     rcx, rsi; pvarDest
0x1800d9d63  call    cs:__imp_PropVariantCopy
0x1800d9d6a  nop     dword ptr [rax+rax+00h]
0x1800d9d6f  mov     edx, cs:?g_doStackCaptures@@3HA; pvarSrc
0x1800d9d75  mov     ebx, eax
0x1800d9d77  test    eax, eax
0x1800d9d79  jns     short loc_1800D9D83
0x1800d9d7b  test    edx, edx
0x1800d9d7d  jnz     short loc_1800D9DE7
0x1800d9d7f  test    eax, eax
0x1800d9d81  js      short loc_1800D9DEE
0x1800d9d83  test    rbp, rbp
0x1800d9d86  jz      short loc_1800D9DEE
0x1800d9d88  movzx   ecx, word ptr [rbp+10h]
0x1800d9d8c  lea     eax, [rcx-11h]
0x1800d9d8f  cmp     ax, 2
0x1800d9d93  jbe     short loc_1800D9D9E
0x1800d9d95  mov     ebx, 88982F8Eh
0x1800d9d9a  test    edx, edx
0x1800d9d9c  jmp     short loc_1800D9D38
0x1800d9d9e  mov     [rsi], cx
0x1800d9da1  jmp     short loc_1800D9DEE
0x1800d9da3  or      cx, 1000h
0x1800d9da8  cmp     ax, cx
0x1800d9dab  jnz     short loc_1800D9D59
0x1800d9dad  cmp     edi, 0FFFFFFFFh
0x1800d9db0  jz      short loc_1800D9DBB
0x1800d9db2  cmp     [rdx+8], edi
0x1800d9db5  jnz     loc_1800D9D2C
0x1800d9dbb  mov     ecx, 1011h
0x1800d9dc0  sub     ax, cx
0x1800d9dc3  cmp     ax, 2
0x1800d9dc7  ja      short loc_1800D9D59
0x1800d9dc9  mov     rcx, rsi; pvarDest
0x1800d9dcc  call    cs:__imp_PropVariantCopy
0x1800d9dd3  nop     dword ptr [rax+rax+00h]
0x1800d9dd8  mov     ebx, eax
0x1800d9dda  test    eax, eax
0x1800d9ddc  jns     short loc_1800D9DEE
0x1800d9dde  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d9de5  jz      short loc_1800D9DEE
0x1800d9de7  mov     ecx, eax; int
0x1800d9de9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d9dee  mov     eax, ebx
0x1800d9df0  add     rsp, 28h
0x1800d9df4  pop     rdi
0x1800d9df5  pop     rsi
0x1800d9df6  pop     rbp
0x1800d9df7  pop     rbx
0x1800d9df8  retn
```
