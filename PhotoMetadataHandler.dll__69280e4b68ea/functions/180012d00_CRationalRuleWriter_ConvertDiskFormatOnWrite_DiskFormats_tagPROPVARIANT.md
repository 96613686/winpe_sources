# CRationalRuleWriter::ConvertDiskFormatOnWrite(DiskFormats,tagPROPVARIANT *)

- ea: `0x180012d00`
- end: `0x180012eee`
- name: `?ConvertDiskFormatOnWrite@CRationalRuleWriter@@MEAAJW4DiskFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `494`
- prototype: `int __high(enum DiskFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180008098`
- `0x180008810`
- `0x180009020`
- `0x180009140`
- `0x1800096f0`
- `0x18000f004`
- `0x180012d00`
- `0x1800132dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012dde`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012def`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012e00`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012e11`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012dde`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012def`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012e00`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012e11`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRationalRuleWriter::ConvertDiskFormatOnWrite(__int64 a1, int a2, struct tagPROPVARIANT *a3)
{
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // eax
  PROPVARIANT pvarDest; // [rsp+30h] [rbp-9h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp+Fh] BYREF
  PROPVARIANT v10; // [rsp+60h] [rbp+27h] BYREF
  PROPVARIANT v11; // [rsp+78h] [rbp+3Fh] BYREF

  v4 = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  memset(&v11, 0, sizeof(v11));
  memset(&v10, 0, sizeof(v10));
  memset(&pvar, 0, sizeof(pvar));
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL) != 2 && *(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL) != 3 )
  {
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL) == 5 || *(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL) == 6 )
    {
LABEL_7:
      if ( a3->vt != 31 )
      {
        if ( (unsigned int)a3->vt - 4116 >= 2 )
          goto LABEL_9;
        if ( a2 == 3 )
        {
          v6 = ConvertGpsCoordUI8ToXMP(a3);
        }
        else
        {
          if ( a3->lVal != 4 )
            goto LABEL_19;
          v6 = StripGPSCoordinateReferenceDataFromGPSCoordVector(a3);
        }
        goto LABEL_15;
      }
      if ( a2 != 10 )
        goto LABEL_19;
      v6 = ConvertGPSCoordinateTextToVector(a3, &v11, &v10, &pvar, &pvarDest);
      v4 = v6;
      if ( v6 < 0 )
      {
LABEL_16:
        if ( !g_doStackCaptures )
          goto LABEL_19;
LABEL_17:
        v5 = v6;
        goto LABEL_18;
      }
      v6 = StripGPSCoordinateReferenceDataFromGPSCoordVector(&pvarDest);
LABEL_23:
      v4 = v6;
      if ( v6 >= 0 )
      {
        TransferPropVariant(a3, &pvarDest);
        goto LABEL_19;
      }
      if ( !g_doStackCaptures )
        goto LABEL_19;
      goto LABEL_17;
    }
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL) != 7 )
    {
      if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL) - 8) > 1 )
        goto LABEL_19;
      goto LABEL_7;
    }
  }
  if ( a3->vt == 20 || a3->vt == 21 )
  {
    if ( a2 != 3 )
      goto LABEL_19;
    v6 = ConvertRationalUI8ToXMP(a3);
LABEL_15:
    v4 = v6;
    if ( v6 >= 0 )
      goto LABEL_19;
    goto LABEL_16;
  }
  if ( a3->vt == 31 )
  {
    if ( a2 != 10 )
      goto LABEL_19;
    v6 = ConvertRationalText(a3, 0, 0, 0, &pvarDest, 0);
    goto LABEL_23;
  }
LABEL_9:
  v4 = -2147024809;
  if ( g_doStackCaptures )
  {
    v5 = -2147024809;
LABEL_18:
    DoStackCapture(v5);
  }
LABEL_19:
  PropVariantClear(&pvar);
  PropVariantClear(&v10);
  PropVariantClear(&v11);
  PropVariantClear(&pvarDest);
  return v4;
}

```

## disassembly

```asm
0x180012d00  mov     [rsp-8+arg_0], rbx
0x180012d05  mov     [rsp-8+arg_8], rdi
0x180012d0a  push    rbp
0x180012d0b  lea     rbp, [rsp-57h]
0x180012d10  sub     rsp, 90h
0x180012d17  mov     rdi, r8
0x180012d1a  mov     r8d, edx
0x180012d1d  xor     ebx, ebx
0x180012d1f  xorps   xmm0, xmm0
0x180012d22  xor     eax, eax
0x180012d24  movups  xmmword ptr [rbp+57h+pvarDest], xmm0
0x180012d28  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x180012d2c  movups  xmmword ptr [rbp+57h+var_18], xmm0
0x180012d30  mov     qword ptr [rbp+57h+var_18+10h], rax
0x180012d34  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x180012d38  mov     qword ptr [rbp+57h+var_30+10h], rax
0x180012d3c  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180012d40  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180012d44  mov     rcx, [rcx+20h]
0x180012d48  mov     edx, [rcx+18h]
0x180012d4b  sub     edx, 2
0x180012d4e  jz      loc_180012E97
0x180012d54  sub     edx, 1
0x180012d57  jz      loc_180012E97
0x180012d5d  sub     edx, 2
0x180012d60  jz      short loc_180012D7A
0x180012d62  sub     edx, 1
0x180012d65  jz      short loc_180012D7A
0x180012d67  sub     edx, 1
0x180012d6a  jz      loc_180012E97
0x180012d70  sub     edx, 1
0x180012d73  jz      short loc_180012D7A
0x180012d75  cmp     edx, 1
0x180012d78  jnz     short loc_180012DDA
0x180012d7a  movzx   ecx, word ptr [rdi]
0x180012d7d  sub     ecx, 1Fh
0x180012d80  jz      loc_180012E35
0x180012d86  sub     ecx, 0FF5h
0x180012d8c  jz      short loc_180012DA5
0x180012d8e  cmp     ecx, 1
0x180012d91  jz      short loc_180012DA5
0x180012d93  mov     ebx, 80070057h
0x180012d98  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012d9f  jz      short loc_180012DDA
0x180012da1  mov     ecx, ebx
0x180012da3  jmp     short loc_180012DD4
0x180012da5  cmp     r8d, 3
0x180012da9  jnz     short loc_180012DB5
0x180012dab  mov     rcx, rdi; pvar
0x180012dae  call    ?ConvertGpsCoordUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z; ConvertGpsCoordUI8ToXMP(tagPROPVARIANT *)
0x180012db3  jmp     short loc_180012DC3
0x180012db5  cmp     dword ptr [rdi+8], 4
0x180012db9  jnz     short loc_180012DDA
0x180012dbb  mov     rcx, rdi; pvarDest
0x180012dbe  call    ?StripGPSCoordinateReferenceDataFromGPSCoordVector@@YAJPEAUtagPROPVARIANT@@@Z; StripGPSCoordinateReferenceDataFromGPSCoordVector(tagPROPVARIANT *)
0x180012dc3  mov     ebx, eax
0x180012dc5  test    eax, eax
0x180012dc7  jns     short loc_180012DDA
0x180012dc9  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012dd0  jz      short loc_180012DDA
0x180012dd2  mov     ecx, eax; int
0x180012dd4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012dd9  nop
0x180012dda  lea     rcx, [rbp+57h+pvar]; pvar
0x180012dde  call    cs:__imp_PropVariantClear
0x180012de5  nop     dword ptr [rax+rax+00h]
0x180012dea  nop
0x180012deb  lea     rcx, [rbp+57h+var_30]; pvar
0x180012def  call    cs:__imp_PropVariantClear
0x180012df6  nop     dword ptr [rax+rax+00h]
0x180012dfb  nop
0x180012dfc  lea     rcx, [rbp+57h+var_18]; pvar
0x180012e00  call    cs:__imp_PropVariantClear
0x180012e07  nop     dword ptr [rax+rax+00h]
0x180012e0c  nop
0x180012e0d  lea     rcx, [rbp+57h+pvarDest]; pvar
0x180012e11  call    cs:__imp_PropVariantClear
0x180012e18  nop     dword ptr [rax+rax+00h]
0x180012e1d  mov     eax, ebx
0x180012e1f  lea     r11, [rsp+90h+var_s0]
0x180012e27  mov     rbx, [r11+10h]
0x180012e2b  mov     rdi, [r11+18h]
0x180012e2f  mov     rsp, r11
0x180012e32  pop     rbp
0x180012e33  retn
0x180012e35  cmp     r8d, 0Ah
0x180012e39  jnz     short loc_180012DDA
0x180012e3b  lea     rax, [rbp+57h+pvarDest]
0x180012e3f  mov     [rsp+90h+var_70], rax; PROPVARIANT *
0x180012e44  lea     r9, [rbp+57h+pvar]; PROPVARIANT *
0x180012e48  lea     r8, [rbp+57h+var_30]; PROPVARIANT *
0x180012e4c  lea     rdx, [rbp+57h+var_18]; pvar
0x180012e50  mov     rcx, rdi; pvarSrc
0x180012e53  call    ?ConvertGPSCoordinateTextToVector@@YAJPEBUtagPROPVARIANT@@PEAU1@111@Z; ConvertGPSCoordinateTextToVector(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180012e58  mov     ebx, eax
0x180012e5a  test    eax, eax
0x180012e5c  js      loc_180012DC9
0x180012e62  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x180012e66  call    ?StripGPSCoordinateReferenceDataFromGPSCoordVector@@YAJPEAUtagPROPVARIANT@@@Z; StripGPSCoordinateReferenceDataFromGPSCoordVector(tagPROPVARIANT *)
0x180012e6b  test    eax, eax
0x180012e6d  mov     ebx, eax
0x180012e6f  jns     short loc_180012E86
0x180012e71  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012e78  jnz     loc_180012DD2
0x180012e7e  test    eax, eax
0x180012e80  js      loc_180012DDA
0x180012e86  lea     rdx, [rbp+57h+pvarDest]; struct tagPROPVARIANT *
0x180012e8a  mov     rcx, rdi; struct tagPROPVARIANT *
0x180012e8d  call    ?TransferPropVariant@@YAXPEAUtagPROPVARIANT@@0@Z; TransferPropVariant(tagPROPVARIANT *,tagPROPVARIANT *)
0x180012e92  jmp     loc_180012DDA
0x180012e97  movzx   ecx, word ptr [rdi]
0x180012e9a  sub     ecx, 14h
0x180012e9d  jz      short loc_180012ED6
0x180012e9f  sub     ecx, 1
0x180012ea2  jz      short loc_180012ED6
0x180012ea4  cmp     ecx, 0Ah
0x180012ea7  jnz     loc_180012D93
0x180012ead  cmp     r8d, ecx
0x180012eb0  jnz     loc_180012DDA
0x180012eb6  mov     [rsp+90h+var_68], 0; bool
0x180012ebb  lea     rax, [rbp+57h+pvarDest]
0x180012ebf  mov     [rsp+90h+var_70], rax; struct tagPROPVARIANT *
0x180012ec4  xor     r9d, r9d; struct tagPROPVARIANT *
0x180012ec7  xor     r8d, r8d; struct tagPROPVARIANT *
0x180012eca  xor     edx, edx; struct tagPROPVARIANT *
0x180012ecc  mov     rcx, rdi; struct tagPROPVARIANT *
0x180012ecf  call    ?ConvertRationalText@@YAJPEBUtagPROPVARIANT@@PEAU1@111_N@Z; ConvertRationalText(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,bool)
0x180012ed4  jmp     short loc_180012E6B
0x180012ed6  cmp     r8d, 3
0x180012eda  jnz     loc_180012DDA
0x180012ee0  mov     rcx, rdi; pvar
0x180012ee3  call    ?ConvertRationalUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z; ConvertRationalUI8ToXMP(tagPROPVARIANT *)
0x180012ee8  jmp     loc_180012DC3
```
