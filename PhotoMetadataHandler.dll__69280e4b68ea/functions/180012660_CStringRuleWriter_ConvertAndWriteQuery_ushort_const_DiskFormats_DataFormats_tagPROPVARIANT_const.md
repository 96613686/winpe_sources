# CStringRuleWriter::ConvertAndWriteQuery(ushort const *,DiskFormats,DataFormats,tagPROPVARIANT const *)

- ea: `0x180012660`
- end: `0x18001270a`
- name: `?ConvertAndWriteQuery@CStringRuleWriter@@MEAAJPEBGW4DiskFormats@@W4DataFormats@@PEBUtagPROPVARIANT@@@Z`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180012660`
- `0x180012710`
- `0x1800132dc`
- `0x180013fc0`
- `0x18001405c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800126da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800126da`

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
0x180012660  push    rbx
0x180012662  sub     rsp, 50h
0x180012666  mov     r10d, r8d
0x180012669  xorps   xmm0, xmm0
0x18001266c  xor     eax, eax
0x18001266e  movups  xmmword ptr [rsp+58h+pvar], xmm0
0x180012673  mov     qword ptr [rsp+58h+pvar+10h], rax
0x180012678  mov     r8, [rsp+58h+arg_20]; struct tagPROPVARIANT *
0x180012680  movzx   eax, word ptr [r8]
0x180012684  sub     ax, 1Fh
0x180012688  mov     r11d, 0EFFFh
0x18001268e  test    r11w, ax
0x180012692  jz      short loc_1800126A6
0x180012694  mov     ebx, 80070057h
0x180012699  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800126a0  jz      short loc_1800126D5
0x1800126a2  mov     ecx, ebx
0x1800126a4  jmp     short loc_1800126CF
0x1800126a6  lea     eax, [r9-0Dh]
0x1800126aa  cmp     eax, 1
0x1800126ad  jbe     short loc_1800126FE
0x1800126af  cmp     r9d, 0Fh
0x1800126b3  jnz     short loc_1800126EF
0x1800126b5  mov     rcx, [rcx+28h]; struct IWICMetadataQueryWriter *
0x1800126b9  call    ?WriteOutXMPLangAlt@@YAJPEAUIWICMetadataQueryWriter@@PEBGPEBUtagPROPVARIANT@@@Z; WriteOutXMPLangAlt(IWICMetadataQueryWriter *,ushort const *,tagPROPVARIANT const *)
0x1800126be  mov     ebx, eax
0x1800126c0  test    eax, eax
0x1800126c2  jns     short loc_1800126D5
0x1800126c4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800126cb  jz      short loc_1800126D5
0x1800126cd  mov     ecx, eax; int
0x1800126cf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800126d4  nop
0x1800126d5  lea     rcx, [rsp+58h+pvar]; pvar
0x1800126da  call    cs:__imp_PropVariantClear
0x1800126e1  nop     dword ptr [rax+rax+00h]
0x1800126e6  mov     eax, ebx
0x1800126e8  add     rsp, 50h
0x1800126ec  pop     rbx
0x1800126ed  retn
0x1800126ef  mov     [rsp+58h+var_38], r8
0x1800126f4  mov     r8d, r10d
0x1800126f7  call    ?ConvertAndWriteQuery@CRuleWriter@@MEAAJPEBGW4DiskFormats@@W4DataFormats@@PEBUtagPROPVARIANT@@@Z; CRuleWriter::ConvertAndWriteQuery(ushort const *,DiskFormats,DataFormats,tagPROPVARIANT const *)
0x1800126fc  jmp     short loc_1800126BE
0x1800126fe  mov     rcx, [rcx+28h]; struct IWICMetadataQueryWriter *
0x180012702  call    ?WriteOutXMPSequence@@YAJPEAUIWICMetadataQueryWriter@@PEBGPEBUtagPROPVARIANT@@@Z; WriteOutXMPSequence(IWICMetadataQueryWriter *,ushort const *,tagPROPVARIANT const *)
0x180012707  jmp     short loc_1800126BE
```
