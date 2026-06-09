# CMetadataIPTCReaderWriter::CreateVariantFromVariantAndDesc(tagPROPVARIANT const *,CMetadataIPTCReaderWriter::DataSetDesc const *,tagPROPVARIANT *)

- ea: `0x1800d71ac`
- end: `0x1800d72f7`
- name: `?CreateVariantFromVariantAndDesc@CMetadataIPTCReaderWriter@@AEAAJPEBUtagPROPVARIANT@@PEBUDataSetDesc@1@PEAU2@@Z`
- size: `331`
- prototype: `__int64 __fastcall(CMetadataIPTCReaderWriter *this, const PROPVARIANT *, const struct CMetadataIPTCReaderWriter::DataSetDesc *, PROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800d70a0`

## callees

- `0x180067e88`
- `0x1800bb784`
- `0x1800d71ac`
- `0x1800d7300`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800d726d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800d72d0`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800d726d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800d72d0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800d7230`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800d7230`

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
  HRESULT v9; // eax
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
  v9 = CMetadataIPTCReaderWriter::IPTCCoerceVariantToPWSZSTR(
         v7,
         (const struct tagPROPVARIANT *)a2,
         (struct tagPROPVARIANT *)a4);
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
0x1800d71ac  push    rbx
0x1800d71ae  push    rbp
0x1800d71af  push    rsi
0x1800d71b0  push    rdi
0x1800d71b1  sub     rsp, 28h
0x1800d71b5  xor     eax, eax
0x1800d71b7  xorps   xmm0, xmm0
0x1800d71ba  movups  xmmword ptr [r9], xmm0
0x1800d71be  mov     [r9+10h], rax
0x1800d71c2  or      edi, 0FFFFFFFFh
0x1800d71c5  movzx   eax, word ptr [rdx]
0x1800d71c8  mov     rsi, r9
0x1800d71cb  movzx   ecx, ax
0x1800d71ce  mov     rbp, r8
0x1800d71d1  test    r8, r8
0x1800d71d4  jz      short loc_1800D71DF
0x1800d71d6  movzx   ecx, word ptr [r8+10h]; this
0x1800d71db  mov     edi, [r8+14h]
0x1800d71df  cmp     cx, 1Eh
0x1800d71e3  jnz     short loc_1800D724F
0x1800d71e5  mov     r8, rsi; struct tagPROPVARIANT *
0x1800d71e8  call    ?IPTCCoerceVariantToPWSZSTR@CMetadataIPTCReaderWriter@@AEAAJPEBUtagPROPVARIANT@@PEAU2@@Z; CMetadataIPTCReaderWriter::IPTCCoerceVariantToPWSZSTR(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800d71ed  mov     ebx, eax
0x1800d71ef  test    eax, eax
0x1800d71f1  jns     short loc_1800D7208
0x1800d71f3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d71fa  jnz     loc_1800D72E5
0x1800d7200  test    eax, eax
0x1800d7202  js      loc_1800D72EC
0x1800d7208  cmp     edi, 0FFFFFFFFh
0x1800d720b  jz      loc_1800D72EC
0x1800d7211  mov     rcx, [rsi+8]; unsigned __int16 *
0x1800d7215  lea     eax, [rdi+1]
0x1800d7218  movsxd  rdx, eax; unsigned __int64
0x1800d721b  lea     r8, [rsp+48h+arg_0]; unsigned __int64 *
0x1800d7220  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800d7225  test    eax, eax
0x1800d7227  jns     loc_1800D72EC
0x1800d722d  mov     rcx, rsi; pvar
0x1800d7230  call    cs:__imp_PropVariantClear
0x1800d7236  mov     ebx, 88982F42h
0x1800d723b  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d7242  jz      loc_1800D72EC
0x1800d7248  mov     ecx, ebx
0x1800d724a  jmp     loc_1800D72E7
0x1800d724f  cmp     edi, 0FFFFFFFFh
0x1800d7252  jz      short loc_1800D72A7
0x1800d7254  cmp     edi, 1
0x1800d7257  jg      short loc_1800D72A7
0x1800d7259  sub     ax, 11h
0x1800d725d  cmp     ax, 2
0x1800d7261  jbe     short loc_1800D726A
0x1800d7263  mov     ebx, 88982F8Eh
0x1800d7268  jmp     short loc_1800D723B
0x1800d726a  mov     rcx, rsi; pvarDest
0x1800d726d  call    cs:__imp_PropVariantCopy
0x1800d7273  mov     edx, cs:?g_doStackCaptures@@3HA; pvarSrc
0x1800d7279  mov     ebx, eax
0x1800d727b  test    eax, eax
0x1800d727d  jns     short loc_1800D7287
0x1800d727f  test    edx, edx
0x1800d7281  jnz     short loc_1800D72E5
0x1800d7283  test    eax, eax
0x1800d7285  js      short loc_1800D72EC
0x1800d7287  test    rbp, rbp
0x1800d728a  jz      short loc_1800D72EC
0x1800d728c  movzx   ecx, word ptr [rbp+10h]
0x1800d7290  lea     eax, [rcx-11h]
0x1800d7293  cmp     ax, 2
0x1800d7297  jbe     short loc_1800D72A2
0x1800d7299  mov     ebx, 88982F8Eh
0x1800d729e  test    edx, edx
0x1800d72a0  jmp     short loc_1800D7242
0x1800d72a2  mov     [rsi], cx
0x1800d72a5  jmp     short loc_1800D72EC
0x1800d72a7  or      cx, 1000h
0x1800d72ac  cmp     ax, cx
0x1800d72af  jnz     short loc_1800D7263
0x1800d72b1  cmp     edi, 0FFFFFFFFh
0x1800d72b4  jz      short loc_1800D72BF
0x1800d72b6  cmp     [rdx+8], edi
0x1800d72b9  jnz     loc_1800D7236
0x1800d72bf  mov     ecx, 1011h
0x1800d72c4  sub     ax, cx
0x1800d72c7  cmp     ax, 2
0x1800d72cb  ja      short loc_1800D7263
0x1800d72cd  mov     rcx, rsi; pvarDest
0x1800d72d0  call    cs:__imp_PropVariantCopy
0x1800d72d6  mov     ebx, eax
0x1800d72d8  test    eax, eax
0x1800d72da  jns     short loc_1800D72EC
0x1800d72dc  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d72e3  jz      short loc_1800D72EC
0x1800d72e5  mov     ecx, eax; int
0x1800d72e7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d72ec  mov     eax, ebx
0x1800d72ee  add     rsp, 28h
0x1800d72f2  pop     rdi
0x1800d72f3  pop     rsi
0x1800d72f4  pop     rbp
0x1800d72f5  pop     rbx
0x1800d72f6  retn
```
