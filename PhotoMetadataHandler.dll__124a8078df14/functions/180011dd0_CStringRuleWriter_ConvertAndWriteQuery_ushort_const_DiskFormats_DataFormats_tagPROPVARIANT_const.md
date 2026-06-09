# CStringRuleWriter::ConvertAndWriteQuery(ushort const *,DiskFormats,DataFormats,tagPROPVARIANT const *)

- ea: `0x180011dd0`
- end: `0x180011e73`
- name: `?ConvertAndWriteQuery@CStringRuleWriter@@MEAAJPEBGW4DiskFormats@@W4DataFormats@@PEBUtagPROPVARIANT@@@Z`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180011dd0`
- `0x180011e80`
- `0x1800129d8`
- `0x180013624`
- `0x1800136c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011e4a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011e4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStringRuleWriter::ConvertAndWriteQuery(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        struct tagPROPVARIANT *a5)
{
  unsigned int v5; // ebx
  int v6; // ecx
  int v7; // eax
  PROPVARIANT pvar; // [rsp+30h] [rbp-28h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  if ( ((a5->vt - 31) & 0xEFFF) != 0 )
  {
    v5 = -2147024809;
    if ( g_doStackCaptures )
    {
      v6 = -2147024809;
LABEL_10:
      DoStackCapture(v6);
    }
  }
  else
  {
    if ( a4 - 13 <= 1 )
    {
      v7 = WriteOutXMPSequence(*(struct IWICMetadataQueryWriter **)(a1 + 40), a2, a5);
    }
    else if ( a4 == 15 )
    {
      v7 = WriteOutXMPLangAlt(*(struct IWICMetadataQueryWriter **)(a1 + 40), a2, a5);
    }
    else
    {
      v7 = CRuleWriter::ConvertAndWriteQuery((_QWORD **)a1, (__int64)a2, a3, a4, a5);
    }
    v5 = v7;
    if ( v7 < 0 && g_doStackCaptures )
    {
      v6 = v7;
      goto LABEL_10;
    }
  }
  PropVariantClear(&pvar);
  return v5;
}

```

## disassembly

```asm
0x180011dd0  push    rbx
0x180011dd2  sub     rsp, 50h
0x180011dd6  mov     r10d, r8d
0x180011dd9  xorps   xmm0, xmm0
0x180011ddc  xor     eax, eax
0x180011dde  movups  xmmword ptr [rsp+58h+pvar], xmm0
0x180011de3  mov     qword ptr [rsp+58h+pvar+10h], rax
0x180011de8  mov     r8, [rsp+58h+arg_20]; struct tagPROPVARIANT *
0x180011df0  movzx   eax, word ptr [r8]
0x180011df4  sub     ax, 1Fh
0x180011df8  mov     r11d, 0EFFFh
0x180011dfe  test    r11w, ax
0x180011e02  jz      short loc_180011E16
0x180011e04  mov     ebx, 80070057h
0x180011e09  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180011e10  jz      short loc_180011E45
0x180011e12  mov     ecx, ebx
0x180011e14  jmp     short loc_180011E3F
0x180011e16  lea     eax, [r9-0Dh]
0x180011e1a  cmp     eax, 1
0x180011e1d  jbe     short loc_180011E67
0x180011e1f  cmp     r9d, 0Fh
0x180011e23  jnz     short loc_180011E58
0x180011e25  mov     rcx, [rcx+28h]; struct IWICMetadataQueryWriter *
0x180011e29  call    ?WriteOutXMPLangAlt@@YAJPEAUIWICMetadataQueryWriter@@PEBGPEBUtagPROPVARIANT@@@Z; WriteOutXMPLangAlt(IWICMetadataQueryWriter *,ushort const *,tagPROPVARIANT const *)
0x180011e2e  mov     ebx, eax
0x180011e30  test    eax, eax
0x180011e32  jns     short loc_180011E45
0x180011e34  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180011e3b  jz      short loc_180011E45
0x180011e3d  mov     ecx, eax; int
0x180011e3f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180011e44  nop
0x180011e45  lea     rcx, [rsp+58h+pvar]; pvar
0x180011e4a  call    cs:__imp_PropVariantClear
0x180011e50  mov     eax, ebx
0x180011e52  add     rsp, 50h
0x180011e56  pop     rbx
0x180011e57  retn
0x180011e58  mov     [rsp+58h+var_38], r8
0x180011e5d  mov     r8d, r10d
0x180011e60  call    ?ConvertAndWriteQuery@CRuleWriter@@MEAAJPEBGW4DiskFormats@@W4DataFormats@@PEBUtagPROPVARIANT@@@Z; CRuleWriter::ConvertAndWriteQuery(ushort const *,DiskFormats,DataFormats,tagPROPVARIANT const *)
0x180011e65  jmp     short loc_180011E2E
0x180011e67  mov     rcx, [rcx+28h]; struct IWICMetadataQueryWriter *
0x180011e6b  call    ?WriteOutXMPSequence@@YAJPEAUIWICMetadataQueryWriter@@PEBGPEBUtagPROPVARIANT@@@Z; WriteOutXMPSequence(IWICMetadataQueryWriter *,ushort const *,tagPROPVARIANT const *)
0x180011e70  jmp     short loc_180011E2E
```
