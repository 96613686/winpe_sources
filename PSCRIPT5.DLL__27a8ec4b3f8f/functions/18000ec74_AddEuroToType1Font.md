# AddEuroToType1Font

- ea: `0x18000ec74`
- end: `0x18000f2dd`
- name: `AddEuroToType1Font`
- size: `1641`
- prototype: `char __fastcall(__int64, void *, _BYTE *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18000c180`
- `0x18000f2e4`

## callees

- `0x18000ec74`
- `0x18000f960`
- `0x180010400`
- `0x1800166c0`
- `0x180016a50`
- `0x1800170a0`
- `0x180017340`
- `0x180017610`
- `0x18001b034`
- `0x18001b2cc`
- `0x18001eea4`
- `0x18001ef28`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000f242`
- `KERNEL32!LocalFree` at `0x18000f256`
- `KERNEL32!LocalFree` at `0x18000f265`
- `KERNEL32!LocalFree` at `0x18000f27c`
- `KERNEL32!LocalFree` at `0x18000f290`
- `KERNEL32!LocalFree` at `0x18000f2a4`
- `KERNEL32!LocalFree` at `0x18000f2b8`
- `KERNEL32!LocalFree` at `0x18000f242`
- `KERNEL32!LocalFree` at `0x18000f256`
- `KERNEL32!LocalFree` at `0x18000f265`
- `KERNEL32!LocalFree` at `0x18000f27c`
- `KERNEL32!LocalFree` at `0x18000f290`
- `KERNEL32!LocalFree` at `0x18000f2a4`
- `KERNEL32!LocalFree` at `0x18000f2b8`
- `GDI32!FONTOBJ_pifi` at `0x18000ed28`
- `GDI32!FONTOBJ_pifi` at `0x18000ed28`

## string_xrefs

- `0x18000f1d9`: `-Copy BuildNewFont`

## pseudocode

```c
char __fastcall AddEuroToType1Font(__int64 a1, void *a2, const char *a3, int a4)
{
  bool v5; // zf
  IFIMETRICS *v6; // rax
  IFIMETRICS *v7; // rdi
  int v8; // ecx
  int v9; // r13d
  int v10; // esi
  int v11; // edi
  char *v12; // r15
  _WORD *v13; // r12
  _BYTE *v14; // r14
  int v15; // edi
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // r8
  unsigned __int16 v19; // di
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned __int16 v22; // di
  char *v23; // r12
  int v24; // esi
  int v25; // edx
  unsigned __int8 *v26; // rdx
  IFIMETRICS *v28; // [rsp+20h] [rbp-30h]
  int v29; // [rsp+20h] [rbp-30h]
  HLOCAL hMem; // [rsp+28h] [rbp-28h] BYREF
  HLOCAL v31; // [rsp+30h] [rbp-20h] BYREF
  HLOCAL v32; // [rsp+38h] [rbp-18h] BYREF
  char *v33; // [rsp+40h] [rbp-10h]
  int v34; // [rsp+90h] [rbp+40h]
  HLOCAL v35; // [rsp+98h] [rbp+48h] BYREF
  const char *v36; // [rsp+A0h] [rbp+50h]

  v36 = a3;
  v35 = a2;
  v5 = (*(_DWORD *)(a1 + 132) & 0x400) == 0;
  v31 = 0;
  v32 = 0;
  v35 = 0;
  hMem = 0;
  if ( !v5 && *(int *)(*(_QWORD *)(a1 + 96) + 140LL) >= 2
    || (v6 = *(IFIMETRICS **)(a1 + 96), v6->ptlBaseline.y) && v6->ptlCaret.y >= 2 )
  {
    v6 = *(IFIMETRICS **)(a1 + 3712);
    v28 = v6;
    if ( v6 )
    {
      if ( *a3 && (*(_DWORD *)(a1 + 3564) & 0x500000) == 0 && a4 )
      {
        v7 = *(IFIMETRICS **)(a1 + 3544);
        if ( !v7 )
        {
          v6 = FONTOBJ_pifi(*(FONTOBJ **)(a1 + 3536));
          *(_QWORD *)(a1 + 3544) = v6;
          v7 = v6;
          if ( !v6 )
            return (char)v6;
          a3 = v36;
        }
        LOBYTE(v6) = v7->jWinCharSet + 0x80;
        if ( (unsigned __int8)v6 > 8u || (v8 = 327, !_bittest(&v8, (unsigned int)v6)) )
        {
          if ( v7->jWinCharSet != 2 )
          {
            v9 = -1;
            v10 = BSearchNameIndex(*(_QWORD *)(a1 + 3712), a3, (__int64)a3, *(_DWORD *)(a1 + 3720) - 1);
            if ( v10 != -1
              || (LODWORD(v6) = FindSubstituteEuro(
                                  a1,
                                  v7->jWinPitchAndFamily,
                                  v7->fsSelection & 0x20,
                                  v7->fsSelection & 1),
                  v10 = (int)v6,
                  (_DWORD)v6 != -1) )
            {
              LODWORD(v6) = LoadNameListFromResource(a1, 273, 265, &hMem);
              v11 = (int)v6;
              if ( (_DWORD)v6 )
              {
                LoadIntArrayFromResource(a1, 270, 265, &v31);
                LoadIntArrayFromResource(a1, 268, 269, &v32);
                LOBYTE(v6) = LoadIntArrayFromResource(a1, 267, 269, &v35);
                v12 = (char *)v31;
                v13 = v32;
                v14 = v35;
                if ( v31 && v32 && v35 )
                {
                  v34 = 1;
                  PSProcsetSend((_DWORD *)a1, 38);
                  v15 = v11 / 2;
                  v17 = BSearchNameIndex((__int64)hMem, *((const char **)&v28->cjThis + v10), v16, v15);
                  if ( v17 >= 0 && v17 < v15 )
                    v9 = BSearchNameIndex(
                           *(_QWORD *)(a1 + 3712),
                           *((const char **)hMem + v15 + v17),
                           v18,
                           *(_DWORD *)(a1 + 3720) - 1);
                  v29 = *(_DWORD *)(a1 + 2236) & 1;
                  if ( v29 )
                    VMCheck(a1, 0x14u, 5000);
                  OPRawPortWrite(a1, "/", 1u);
                  OPSendStringA(a1, v36);
                  OPRawPortWrite(a1, " FontHasEuro not", 0x10u);
                  OPRawPortWrite(a1, "\r\n", 2u);
                  OPRawPortWrite(a1, "{", 1u);
                  OPRawPortWrite(a1, "\r\n", 2u);
                  OPRawPortWrite(a1, "/", 1u);
                  OPRawPortWrite(a1, "Euro.", 5u);
                  OPSendStringA(a1, v36);
                  OPRawPortWrite(a1, "\r\n", 2u);
                  while ( 1 )
                  {
                    v33 = &v12[12 * v10];
                    LOWORD(v35) = v13[v10];
                    v19 = (unsigned __int16)v35;
                    do
                    {
                      do
                        v20 = v19++;
                      while ( v14[v20] != 9 );
                      v21 = v19++;
                    }
                    while ( v14[v21] != 14 );
                    v22 = v19 - (_WORD)v35;
                    if ( v9 >= 0 && v34 )
                    {
                      OPRawPortWrite(a1, "/", 1u);
                      OPSendStringA(a1, v36);
                      OPRawPortWrite(a1, " UseObliqueEuro {", 0x11u);
                      OPRawPortWrite(a1, "\r\n", 2u);
                    }
                    OPRawPortWrite(a1, " [", 2u);
                    v23 = v33;
                    v24 = 6;
                    do
                    {
                      v25 = *(__int16 *)v23;
                      v23 += 2;
                      OPSendInt(a1, v25);
                      --v24;
                    }
                    while ( v24 );
                    v12 = (char *)v31;
                    v13 = v32;
                    OPRawPortWrite(a1, "] ", 2u);
                    OPRawPortWrite(a1, "\r\n", 2u);
                    OPRawPortWrite(a1, "<", 1u);
                    v26 = &v14[(unsigned __int16)v35];
                    *(_DWORD *)(a1 + 2892) = 0;
                    BSendBitmapAscii7(a1, v26, v22);
                    OPRawPortWrite(a1, ">", 1u);
                    OPRawPortWrite(a1, "\r\n", 2u);
                    if ( v9 < 0 )
                      break;
                    if ( !v34 )
                    {
                      OPRawPortWrite(a1, "} ifelse", 8u);
                      OPRawPortWrite(a1, "\r\n", 2u);
                      break;
                    }
                    OPRawPortWrite(a1, "} {", 3u);
                    OPRawPortWrite(a1, "\r\n", 2u);
                    v10 = v9;
                    v34 = 0;
                  }
                  OPRawPortWrite(a1, "AddEuroGlyph", 0xCu);
                  OPRawPortWrite(a1, "\r\n", 2u);
                  OPRawPortWrite(a1, "/", 1u);
                  OPRawPortWrite(a1, "Euro ", 5u);
                  OPRawPortWrite(a1, "/", 1u);
                  OPSendStringA(a1, v36);
                  OPRawPortWrite(a1, " ", 1u);
                  OPRawPortWrite(a1, "/", 1u);
                  OPSendStringA(a1, v36);
                  OPRawPortWrite(a1, "-Copy BuildNewFont", 0x12u);
                  OPRawPortWrite(a1, "\r\n", 2u);
                  OPRawPortWrite(a1, "} if", 4u);
                  OPRawPortWrite(a1, "\r\n", 2u);
                  if ( v29 )
                    VMUse((_DWORD *)a1, 0x14u, 5000, 0);
                  if ( hMem )
                    LocalFree(hMem);
                  if ( v12 )
                    LocalFree(v12);
                  LocalFree(v13);
                  goto LABEL_53;
                }
                if ( hMem )
                  LOBYTE(v6) = (unsigned __int8)LocalFree(hMem);
                if ( v12 )
                  LOBYTE(v6) = (unsigned __int8)LocalFree(v12);
                if ( v13 )
                  LOBYTE(v6) = (unsigned __int8)LocalFree(v13);
                if ( v14 )
LABEL_53:
                  LOBYTE(v6) = (unsigned __int8)LocalFree(v14);
              }
            }
          }
        }
      }
    }
  }
  return (char)v6;
}

```

## disassembly

```asm
0x18000ec74  mov     [rsp-38h+arg_18], rbx
0x18000ec79  mov     [rsp-38h+arg_10], r8
0x18000ec7e  mov     [rsp-38h+arg_8], rdx
0x18000ec83  push    rbp
0x18000ec84  push    rsi
0x18000ec85  push    rdi
0x18000ec86  push    r12
0x18000ec88  push    r13
0x18000ec8a  push    r14
0x18000ec8c  push    r15
0x18000ec8e  mov     rbp, rsp
0x18000ec91  sub     rsp, 50h
0x18000ec95  xor     r14d, r14d
0x18000ec98  mov     rbx, rcx
0x18000ec9b  test    dword ptr [rcx+84h], 400h
0x18000eca5  mov     [rbp+var_20], r14
0x18000eca9  mov     [rbp+var_18], r14
0x18000ecad  mov     [rbp+arg_8], r14
0x18000ecb1  mov     [rbp+hMem], r14
0x18000ecb5  jz      short loc_18000ECC4
0x18000ecb7  mov     rax, [rcx+60h]
0x18000ecbb  cmp     dword ptr [rax+8Ch], 2
0x18000ecc2  jge     short loc_18000ECDF
0x18000ecc4  mov     rax, [rcx+60h]
0x18000ecc8  cmp     [rax+7Ch], r14d
0x18000eccc  jz      loc_18000F2C4
0x18000ecd2  cmp     dword ptr [rax+8Ch], 2
0x18000ecd9  jl      loc_18000F2C4
0x18000ecdf  mov     rax, [rcx+0E80h]
0x18000ece6  mov     [rbp+var_30], rax
0x18000ecea  test    rax, rax
0x18000eced  jz      loc_18000F2C4
0x18000ecf3  cmp     [r8], r14b
0x18000ecf6  jz      loc_18000F2C4
0x18000ecfc  test    dword ptr [rcx+0DECh], 500000h
0x18000ed06  jnz     loc_18000F2C4
0x18000ed0c  test    r9d, r9d
0x18000ed0f  jz      loc_18000F2C4
0x18000ed15  mov     rdi, [rcx+0DD8h]
0x18000ed1c  test    rdi, rdi
0x18000ed1f  jnz     short loc_18000ED4B
0x18000ed21  mov     rcx, [rcx+0DD0h]; pfo
0x18000ed28  call    cs:__imp_FONTOBJ_pifi
0x18000ed2f  nop     dword ptr [rax+rax+00h]
0x18000ed34  mov     [rbx+0DD8h], rax
0x18000ed3b  mov     rdi, rax
0x18000ed3e  test    rax, rax
0x18000ed41  jz      loc_18000F2C4
0x18000ed47  mov     r8, [rbp+arg_10]
0x18000ed4b  mov     al, [rdi+2Ch]
0x18000ed4e  sub     al, 80h
0x18000ed50  cmp     al, 8
0x18000ed52  ja      short loc_18000ED62
0x18000ed54  mov     ecx, 147h
0x18000ed59  bt      ecx, eax
0x18000ed5c  jb      loc_18000F2C4
0x18000ed62  cmp     byte ptr [rdi+2Ch], 2
0x18000ed66  jz      loc_18000F2C4
0x18000ed6c  mov     r9d, [rbx+0E88h]
0x18000ed73  mov     r15d, 1
0x18000ed79  mov     rcx, [rbx+0E80h]
0x18000ed80  sub     r9d, r15d
0x18000ed83  mov     rdx, r8
0x18000ed86  call    BSearchNameIndex
0x18000ed8b  or      r13d, 0FFFFFFFFh
0x18000ed8f  mov     esi, eax
0x18000ed91  cmp     eax, r13d
0x18000ed94  jnz     short loc_18000EDBE
0x18000ed96  movzx   r8d, word ptr [rdi+34h]
0x18000ed9b  mov     rcx, rbx
0x18000ed9e  mov     dl, [rdi+2Dh]
0x18000eda1  movzx   r9d, r8w
0x18000eda5  and     r9w, r15w
0x18000eda9  and     r8w, 20h
0x18000edae  call    FindSubstituteEuro
0x18000edb3  mov     esi, eax
0x18000edb5  cmp     eax, r13d
0x18000edb8  jz      loc_18000F2C4
0x18000edbe  mov     r15d, 109h
0x18000edc4  lea     r9, [rbp+hMem]
0x18000edc8  mov     r8d, r15d
0x18000edcb  mov     rcx, rbx
0x18000edce  lea     edx, [r15+8]
0x18000edd2  call    LoadNameListFromResource
0x18000edd7  mov     edi, eax
0x18000edd9  test    eax, eax
0x18000eddb  jz      loc_18000F2C4
0x18000ede1  lea     r9, [rbp+var_20]
0x18000ede5  mov     r8d, r15d
0x18000ede8  lea     edx, [r15+5]
0x18000edec  mov     rcx, rbx
0x18000edef  call    LoadIntArrayFromResource
0x18000edf4  lea     r14d, [r15+4]
0x18000edf8  mov     rcx, rbx
0x18000edfb  mov     r8d, r14d
0x18000edfe  lea     r9, [rbp+var_18]
0x18000ee02  lea     edx, [r15+3]
0x18000ee06  call    LoadIntArrayFromResource
0x18000ee0b  lea     r9, [rbp+arg_8]
0x18000ee0f  mov     r8d, r14d
0x18000ee12  lea     edx, [r15+2]
0x18000ee16  mov     rcx, rbx
0x18000ee19  call    LoadIntArrayFromResource
0x18000ee1e  mov     r15, [rbp+var_20]
0x18000ee22  mov     r12, [rbp+var_18]
0x18000ee26  mov     r14, [rbp+arg_8]
0x18000ee2a  test    r15, r15
0x18000ee2d  jz      loc_18000F273
0x18000ee33  test    r12, r12
0x18000ee36  jz      loc_18000F273
0x18000ee3c  test    r14, r14
0x18000ee3f  jz      loc_18000F273
0x18000ee45  mov     edx, 26h ; '&'
0x18000ee4a  mov     [rbp+arg_0], 1
0x18000ee51  mov     rcx, rbx
0x18000ee54  call    PSProcsetSend
0x18000ee59  mov     rcx, [rbp+hMem]
0x18000ee5d  mov     eax, edi
0x18000ee5f  cdq
0x18000ee60  sub     eax, edx
0x18000ee62  movsxd  rdx, esi
0x18000ee65  sar     eax, 1
0x18000ee67  mov     edi, eax
0x18000ee69  mov     r9d, eax
0x18000ee6c  mov     rax, [rbp+var_30]
0x18000ee70  mov     rdx, [rax+rdx*8]
0x18000ee74  call    BSearchNameIndex
0x18000ee79  test    eax, eax
0x18000ee7b  js      short loc_18000EEA7
0x18000ee7d  cmp     eax, edi
0x18000ee7f  jge     short loc_18000EEA7
0x18000ee81  mov     r9d, [rbx+0E88h]
0x18000ee88  add     eax, edi
0x18000ee8a  mov     rcx, [rbx+0E80h]
0x18000ee91  dec     r9d
0x18000ee94  movsxd  rdx, eax
0x18000ee97  mov     rax, [rbp+hMem]
0x18000ee9b  mov     rdx, [rax+rdx*8]
0x18000ee9f  call    BSearchNameIndex
0x18000eea4  mov     r13d, eax
0x18000eea7  mov     eax, [rbx+8BCh]
0x18000eead  mov     edi, 1
0x18000eeb2  and     eax, edi
0x18000eeb4  mov     dword ptr [rbp+var_30], eax
0x18000eeb7  jz      short loc_18000EECA
0x18000eeb9  lea     edx, [rdi+13h]
0x18000eebc  mov     r8d, 1388h
0x18000eec2  mov     rcx, rbx
0x18000eec5  call    VMCheck
0x18000eeca  mov     r8d, edi
0x18000eecd  lea     rdx, PSFRAG_slash; "/"
0x18000eed4  mov     rcx, rbx
0x18000eed7  call    OPRawPortWrite
0x18000eedc  mov     rdx, [rbp+arg_10]
0x18000eee0  mov     rcx, rbx
0x18000eee3  call    OPSendStringA
0x18000eee8  mov     r8d, 10h
0x18000eeee  lea     rdx, aFonthaseuroNot; " FontHasEuro not"
0x18000eef5  mov     rcx, rbx
0x18000eef8  call    OPRawPortWrite
0x18000eefd  mov     r8d, 2
0x18000ef03  lea     rdx, gstrCRLF; "\r\n"
0x18000ef0a  mov     rcx, rbx
0x18000ef0d  call    OPRawPortWrite
0x18000ef12  mov     r8d, edi
0x18000ef15  lea     rdx, PSFRAG_beginFunction; "{"
0x18000ef1c  mov     rcx, rbx
0x18000ef1f  call    OPRawPortWrite
0x18000ef24  mov     r8d, 2
0x18000ef2a  lea     rdx, gstrCRLF; "\r\n"
0x18000ef31  mov     rcx, rbx
0x18000ef34  call    OPRawPortWrite
0x18000ef39  mov     r8d, edi
0x18000ef3c  lea     rdx, PSFRAG_slash; "/"
0x18000ef43  mov     rcx, rbx
0x18000ef46  call    OPRawPortWrite
0x18000ef4b  mov     r8d, 5
0x18000ef51  lea     rdx, aEuro; "Euro."
0x18000ef58  mov     rcx, rbx
0x18000ef5b  call    OPRawPortWrite
0x18000ef60  mov     rdx, [rbp+arg_10]
0x18000ef64  mov     rcx, rbx
0x18000ef67  call    OPSendStringA
0x18000ef6c  mov     r8d, 2
0x18000ef72  lea     rdx, gstrCRLF; "\r\n"
0x18000ef79  mov     rcx, rbx
0x18000ef7c  call    OPRawPortWrite
0x18000ef81  lea     eax, [rsi+rsi*2]
0x18000ef84  mov     edx, 1
0x18000ef89  add     eax, eax
0x18000ef8b  cdqe
0x18000ef8d  lea     rcx, [r15+rax*2]
0x18000ef91  movsxd  rax, esi
0x18000ef94  mov     [rbp+var_10], rcx
0x18000ef98  movzx   eax, word ptr [r12+rax*2]
0x18000ef9d  mov     word ptr [rbp+arg_8], ax
0x18000efa1  movzx   edi, ax
0x18000efa4  movzx   ecx, ax
0x18000efa7  movzx   eax, di
0x18000efaa  add     di, dx
0x18000efad  cmp     byte ptr [rax+r14], 9
0x18000efb2  jnz     short loc_18000EFA7
0x18000efb4  movzx   eax, di
0x18000efb7  add     di, dx
0x18000efba  cmp     byte ptr [rax+r14], 0Eh
0x18000efbf  jnz     short loc_18000EFA7
0x18000efc1  sub     di, cx
0x18000efc4  test    r13d, r13d
0x18000efc7  js      short loc_18000F017
0x18000efc9  cmp     [rbp+arg_0], 0
0x18000efcd  jz      short loc_18000F017
0x18000efcf  mov     r8d, edx
0x18000efd2  mov     rcx, rbx
0x18000efd5  lea     rdx, PSFRAG_slash; "/"
0x18000efdc  call    OPRawPortWrite
0x18000efe1  mov     rdx, [rbp+arg_10]
0x18000efe5  mov     rcx, rbx
0x18000efe8  call    OPSendStringA
0x18000efed  mov     r8d, 11h
0x18000eff3  lea     rdx, aUseobliqueeuro; " UseObliqueEuro {"
0x18000effa  mov     rcx, rbx
0x18000effd  call    OPRawPortWrite
0x18000f002  mov     r8d, 2
0x18000f008  lea     rdx, gstrCRLF; "\r\n"
0x18000f00f  mov     rcx, rbx
0x18000f012  call    OPRawPortWrite
0x18000f017  mov     r8d, 2
0x18000f01d  lea     rdx, asc_1800650DC; " ["
0x18000f024  mov     rcx, rbx
0x18000f027  call    OPRawPortWrite
0x18000f02c  mov     r12, [rbp+var_10]
0x18000f030  mov     esi, 6
0x18000f035  movsx   edx, word ptr [r12]
0x18000f03a  mov     rcx, rbx
0x18000f03d  lea     r12, [r12+2]
0x18000f042  call    OPSendInt
0x18000f047  sub     esi, 1
0x18000f04a  jnz     short loc_18000F035
0x18000f04c  mov     r15, [rbp+var_20]
0x18000f050  lea     r8d, [rsi+2]
0x18000f054  mov     r12, [rbp+var_18]
0x18000f058  lea     rdx, asc_1800650E0; "] "
0x18000f05f  mov     rcx, rbx
0x18000f062  call    OPRawPortWrite
0x18000f067  lea     r8d, [rsi+2]
0x18000f06b  mov     rcx, rbx
0x18000f06e  lea     rdx, gstrCRLF; "\r\n"
0x18000f075  call    OPRawPortWrite
0x18000f07a  lea     r8d, [rsi+1]
0x18000f07e  mov     rcx, rbx
0x18000f081  lea     rdx, PSFRAG_leftcaret; "<"
0x18000f088  call    OPRawPortWrite
0x18000f08d  movzx   edx, word ptr [rbp+arg_8]
0x18000f091  xor     esi, esi
0x18000f093  add     rdx, r14
0x18000f096  movzx   r8d, di
0x18000f09a  mov     rcx, rbx
0x18000f09d  mov     [rbx+0B4Ch], esi
0x18000f0a3  call    BSendBitmapAscii7
0x18000f0a8  lea     r8d, [rsi+1]
0x18000f0ac  mov     rcx, rbx
0x18000f0af  lea     rdx, PSFRAG_rightcaret; ">"
0x18000f0b6  call    OPRawPortWrite
0x18000f0bb  lea     edi, [rsi+2]
0x18000f0be  mov     rcx, rbx
0x18000f0c1  mov     r8d, edi
0x18000f0c4  lea     rdx, gstrCRLF; "\r\n"
0x18000f0cb  call    OPRawPortWrite
0x18000f0d0  test    r13d, r13d
0x18000f0d3  js      short loc_18000F132
0x18000f0d5  mov     rcx, rbx
0x18000f0d8  cmp     [rbp+arg_0], esi
0x18000f0db  jz      short loc_18000F10E
0x18000f0dd  lea     r8d, [rsi+3]
0x18000f0e1  lea     rdx, asc_1800650E4; "} {"
0x18000f0e8  call    OPRawPortWrite
0x18000f0ed  mov     r8d, edi
0x18000f0f0  lea     rdx, gstrCRLF; "\r\n"
0x18000f0f7  mov     rcx, rbx
0x18000f0fa  call    OPRawPortWrite
0x18000f0ff  mov     esi, r13d
0x18000f102  mov     [rbp+arg_0], 0
0x18000f109  jmp     loc_18000EF81
0x18000f10e  mov     r8d, 8
0x18000f114  lea     rdx, aIfelse; "} ifelse"
0x18000f11b  call    OPRawPortWrite
0x18000f120  mov     r8d, edi
0x18000f123  lea     rdx, gstrCRLF; "\r\n"
0x18000f12a  mov     rcx, rbx
0x18000f12d  call    OPRawPortWrite
0x18000f132  mov     r8d, 0Ch
0x18000f138  lea     rdx, aAddeuroglyph; "AddEuroGlyph"
0x18000f13f  mov     rcx, rbx
0x18000f142  call    OPRawPortWrite
0x18000f147  mov     r8d, edi
0x18000f14a  lea     rdx, gstrCRLF; "\r\n"
0x18000f151  mov     rcx, rbx
0x18000f154  call    OPRawPortWrite
0x18000f159  mov     r13d, 1
0x18000f15f  lea     rdx, PSFRAG_slash; "/"
  ... truncated ...
```
