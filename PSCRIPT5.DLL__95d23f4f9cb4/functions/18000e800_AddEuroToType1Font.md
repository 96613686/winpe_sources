# AddEuroToType1Font

- ea: `0x18000e800`
- end: `0x18000ee38`
- name: `AddEuroToType1Font`
- size: `1592`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18000bd5c`
- `0x18000ee40`

## callees

- `0x18000e800`
- `0x18000f4a8`
- `0x18000ff24`
- `0x180015f84`
- `0x180016310`
- `0x180016940`
- `0x180016bdc`
- `0x180016ea8`
- `0x18001a6fc`
- `0x18001a98c`
- `0x18001e3bc`
- `0x18001e434`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000edc8`
- `KERNEL32!LocalFree` at `0x18000edd6`
- `KERNEL32!LocalFree` at `0x18000eddf`
- `KERNEL32!LocalFree` at `0x18000edf0`
- `KERNEL32!LocalFree` at `0x18000edfe`
- `KERNEL32!LocalFree` at `0x18000ee0c`
- `KERNEL32!LocalFree` at `0x18000ee1a`
- `KERNEL32!LocalFree` at `0x18000edc8`
- `KERNEL32!LocalFree` at `0x18000edd6`
- `KERNEL32!LocalFree` at `0x18000eddf`
- `KERNEL32!LocalFree` at `0x18000edf0`
- `KERNEL32!LocalFree` at `0x18000edfe`
- `KERNEL32!LocalFree` at `0x18000ee0c`
- `KERNEL32!LocalFree` at `0x18000ee1a`
- `GDI32!FONTOBJ_pifi` at `0x18000e8b4`
- `GDI32!FONTOBJ_pifi` at `0x18000e8b4`

## string_xrefs

- `0x18000ed5f`: `-Copy BuildNewFont`

## pseudocode

```c
char __fastcall AddEuroToType1Font(__int64 a1, void *a2, _BYTE *a3, int a4)
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
  __int64 v15; // rdi
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // r8
  unsigned __int16 v19; // di
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned __int16 v22; // di
  char *v23; // r12
  int v24; // esi
  __int64 v25; // rdx
  char *v26; // rdx
  IFIMETRICS *v28; // [rsp+20h] [rbp-30h]
  int v29; // [rsp+20h] [rbp-30h]
  HLOCAL hMem; // [rsp+28h] [rbp-28h] BYREF
  HLOCAL v31; // [rsp+30h] [rbp-20h] BYREF
  HLOCAL v32; // [rsp+38h] [rbp-18h] BYREF
  char *v33; // [rsp+40h] [rbp-10h]
  int v34; // [rsp+90h] [rbp+40h]
  HLOCAL v35; // [rsp+98h] [rbp+48h] BYREF
  _BYTE *v36; // [rsp+A0h] [rbp+50h]

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
            v10 = BSearchNameIndex(*(_QWORD *)(a1 + 3712), a3, a3, (unsigned int)(*(_DWORD *)(a1 + 3720) - 1));
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
                  PSProcsetSend(a1, 38);
                  v15 = (unsigned int)(v11 / 2);
                  v17 = BSearchNameIndex(hMem, *((_QWORD *)&v28->cjThis + v10), v16, v15);
                  if ( v17 >= 0 && v17 < (int)v15 )
                    v9 = BSearchNameIndex(
                           *(_QWORD *)(a1 + 3712),
                           *((_QWORD *)hMem + (int)v15 + v17),
                           v18,
                           (unsigned int)(*(_DWORD *)(a1 + 3720) - 1));
                  v29 = *(_DWORD *)(a1 + 2236) & 1;
                  if ( v29 )
                    VMCheck(a1, 20);
                  OPRawPortWrite(a1, "/", 1);
                  OPSendStringA(a1, v36);
                  OPRawPortWrite(a1, " FontHasEuro not", 16);
                  OPRawPortWrite(a1, "\r\n", 2);
                  OPRawPortWrite(a1, "{", 1);
                  OPRawPortWrite(a1, "\r\n", 2);
                  OPRawPortWrite(a1, "/", 1);
                  OPRawPortWrite(a1, "Euro.", 5);
                  OPSendStringA(a1, v36);
                  OPRawPortWrite(a1, "\r\n", 2);
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
                      OPRawPortWrite(a1, "/", 1);
                      OPSendStringA(a1, v36);
                      OPRawPortWrite(a1, " UseObliqueEuro {", 17);
                      OPRawPortWrite(a1, "\r\n", 2);
                    }
                    OPRawPortWrite(a1, " [", 2);
                    v23 = v33;
                    v24 = 6;
                    do
                    {
                      v25 = (unsigned int)*(__int16 *)v23;
                      v23 += 2;
                      OPSendInt(a1, v25);
                      --v24;
                    }
                    while ( v24 );
                    v12 = (char *)v31;
                    v13 = v32;
                    OPRawPortWrite(a1, "] ", 2);
                    OPRawPortWrite(a1, "\r\n", 2);
                    OPRawPortWrite(a1, "<", 1);
                    v26 = &v14[(unsigned __int16)v35];
                    *(_DWORD *)(a1 + 2892) = 0;
                    BSendBitmapAscii7(a1, v26, v22);
                    OPRawPortWrite(a1, ">", 1);
                    OPRawPortWrite(a1, "\r\n", 2);
                    if ( v9 < 0 )
                      break;
                    if ( !v34 )
                    {
                      OPRawPortWrite(a1, "} ifelse", 8);
                      OPRawPortWrite(a1, "\r\n", 2);
                      break;
                    }
                    OPRawPortWrite(a1, "} {", 3);
                    OPRawPortWrite(a1, "\r\n", 2);
                    v10 = v9;
                    v34 = 0;
                  }
                  OPRawPortWrite(a1, "AddEuroGlyph", 12);
                  OPRawPortWrite(a1, "\r\n", 2);
                  OPRawPortWrite(a1, "/", 1);
                  OPRawPortWrite(a1, "Euro ", 5);
                  OPRawPortWrite(a1, "/", 1);
                  OPSendStringA(a1, v36);
                  OPRawPortWrite(a1, " ", 1);
                  OPRawPortWrite(a1, "/", 1);
                  OPSendStringA(a1, v36);
                  OPRawPortWrite(a1, "-Copy BuildNewFont", 18);
                  OPRawPortWrite(a1, "\r\n", 2);
                  OPRawPortWrite(a1, "} if", 4);
                  OPRawPortWrite(a1, "\r\n", 2);
                  if ( v29 )
                    VMUse(a1, 20, 5000, 0);
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
0x18000e800  mov     [rsp-38h+arg_18], rbx
0x18000e805  mov     [rsp-38h+arg_10], r8
0x18000e80a  mov     [rsp-38h+arg_8], rdx
0x18000e80f  push    rbp
0x18000e810  push    rsi
0x18000e811  push    rdi
0x18000e812  push    r12
0x18000e814  push    r13
0x18000e816  push    r14
0x18000e818  push    r15
0x18000e81a  mov     rbp, rsp
0x18000e81d  sub     rsp, 50h
0x18000e821  xor     r14d, r14d
0x18000e824  mov     rbx, rcx
0x18000e827  test    dword ptr [rcx+84h], 400h
0x18000e831  mov     [rbp+var_20], r14
0x18000e835  mov     [rbp+var_18], r14
0x18000e839  mov     [rbp+arg_8], r14
0x18000e83d  mov     [rbp+hMem], r14
0x18000e841  jz      short loc_18000E850
0x18000e843  mov     rax, [rcx+60h]
0x18000e847  cmp     dword ptr [rax+8Ch], 2
0x18000e84e  jge     short loc_18000E86B
0x18000e850  mov     rax, [rcx+60h]
0x18000e854  cmp     [rax+7Ch], r14d
0x18000e858  jz      loc_18000EE20
0x18000e85e  cmp     dword ptr [rax+8Ch], 2
0x18000e865  jl      loc_18000EE20
0x18000e86b  mov     rax, [rcx+0E80h]
0x18000e872  mov     [rbp+var_30], rax
0x18000e876  test    rax, rax
0x18000e879  jz      loc_18000EE20
0x18000e87f  cmp     [r8], r14b
0x18000e882  jz      loc_18000EE20
0x18000e888  test    dword ptr [rcx+0DECh], 500000h
0x18000e892  jnz     loc_18000EE20
0x18000e898  test    r9d, r9d
0x18000e89b  jz      loc_18000EE20
0x18000e8a1  mov     rdi, [rcx+0DD8h]
0x18000e8a8  test    rdi, rdi
0x18000e8ab  jnz     short loc_18000E8D1
0x18000e8ad  mov     rcx, [rcx+0DD0h]; pfo
0x18000e8b4  call    cs:__imp_FONTOBJ_pifi
0x18000e8ba  mov     [rbx+0DD8h], rax
0x18000e8c1  mov     rdi, rax
0x18000e8c4  test    rax, rax
0x18000e8c7  jz      loc_18000EE20
0x18000e8cd  mov     r8, [rbp+arg_10]
0x18000e8d1  mov     al, [rdi+2Ch]
0x18000e8d4  sub     al, 80h
0x18000e8d6  cmp     al, 8
0x18000e8d8  ja      short loc_18000E8E8
0x18000e8da  mov     ecx, 147h
0x18000e8df  bt      ecx, eax
0x18000e8e2  jb      loc_18000EE20
0x18000e8e8  cmp     byte ptr [rdi+2Ch], 2
0x18000e8ec  jz      loc_18000EE20
0x18000e8f2  mov     r9d, [rbx+0E88h]
0x18000e8f9  mov     r15d, 1
0x18000e8ff  mov     rcx, [rbx+0E80h]
0x18000e906  sub     r9d, r15d
0x18000e909  mov     rdx, r8
0x18000e90c  call    BSearchNameIndex
0x18000e911  or      r13d, 0FFFFFFFFh
0x18000e915  mov     esi, eax
0x18000e917  cmp     eax, r13d
0x18000e91a  jnz     short loc_18000E944
0x18000e91c  movzx   r8d, word ptr [rdi+34h]
0x18000e921  mov     rcx, rbx
0x18000e924  mov     dl, [rdi+2Dh]
0x18000e927  movzx   r9d, r8w
0x18000e92b  and     r9w, r15w
0x18000e92f  and     r8w, 20h
0x18000e934  call    FindSubstituteEuro
0x18000e939  mov     esi, eax
0x18000e93b  cmp     eax, r13d
0x18000e93e  jz      loc_18000EE20
0x18000e944  mov     r15d, 109h
0x18000e94a  lea     r9, [rbp+hMem]
0x18000e94e  mov     r8d, r15d
0x18000e951  mov     rcx, rbx
0x18000e954  lea     edx, [r15+8]
0x18000e958  call    LoadNameListFromResource
0x18000e95d  mov     edi, eax
0x18000e95f  test    eax, eax
0x18000e961  jz      loc_18000EE20
0x18000e967  lea     r9, [rbp+var_20]
0x18000e96b  mov     r8d, r15d
0x18000e96e  lea     edx, [r15+5]
0x18000e972  mov     rcx, rbx
0x18000e975  call    LoadIntArrayFromResource
0x18000e97a  lea     r14d, [r15+4]
0x18000e97e  mov     rcx, rbx
0x18000e981  mov     r8d, r14d
0x18000e984  lea     r9, [rbp+var_18]
0x18000e988  lea     edx, [r15+3]
0x18000e98c  call    LoadIntArrayFromResource
0x18000e991  lea     r9, [rbp+arg_8]
0x18000e995  mov     r8d, r14d
0x18000e998  lea     edx, [r15+2]
0x18000e99c  mov     rcx, rbx
0x18000e99f  call    LoadIntArrayFromResource
0x18000e9a4  mov     r15, [rbp+var_20]
0x18000e9a8  mov     r12, [rbp+var_18]
0x18000e9ac  mov     r14, [rbp+arg_8]
0x18000e9b0  test    r15, r15
0x18000e9b3  jz      loc_18000EDE7
0x18000e9b9  test    r12, r12
0x18000e9bc  jz      loc_18000EDE7
0x18000e9c2  test    r14, r14
0x18000e9c5  jz      loc_18000EDE7
0x18000e9cb  mov     edx, 26h ; '&'
0x18000e9d0  mov     [rbp+arg_0], 1
0x18000e9d7  mov     rcx, rbx
0x18000e9da  call    PSProcsetSend
0x18000e9df  mov     rcx, [rbp+hMem]
0x18000e9e3  mov     eax, edi
0x18000e9e5  cdq
0x18000e9e6  sub     eax, edx
0x18000e9e8  movsxd  rdx, esi
0x18000e9eb  sar     eax, 1
0x18000e9ed  mov     edi, eax
0x18000e9ef  mov     r9d, eax
0x18000e9f2  mov     rax, [rbp+var_30]
0x18000e9f6  mov     rdx, [rax+rdx*8]
0x18000e9fa  call    BSearchNameIndex
0x18000e9ff  test    eax, eax
0x18000ea01  js      short loc_18000EA2D
0x18000ea03  cmp     eax, edi
0x18000ea05  jge     short loc_18000EA2D
0x18000ea07  mov     r9d, [rbx+0E88h]
0x18000ea0e  add     eax, edi
0x18000ea10  mov     rcx, [rbx+0E80h]
0x18000ea17  dec     r9d
0x18000ea1a  movsxd  rdx, eax
0x18000ea1d  mov     rax, [rbp+hMem]
0x18000ea21  mov     rdx, [rax+rdx*8]
0x18000ea25  call    BSearchNameIndex
0x18000ea2a  mov     r13d, eax
0x18000ea2d  mov     eax, [rbx+8BCh]
0x18000ea33  mov     edi, 1
0x18000ea38  and     eax, edi
0x18000ea3a  mov     dword ptr [rbp+var_30], eax
0x18000ea3d  jz      short loc_18000EA50
0x18000ea3f  lea     edx, [rdi+13h]
0x18000ea42  mov     r8d, 1388h
0x18000ea48  mov     rcx, rbx
0x18000ea4b  call    VMCheck
0x18000ea50  mov     r8d, edi
0x18000ea53  lea     rdx, PSFRAG_slash; "/"
0x18000ea5a  mov     rcx, rbx
0x18000ea5d  call    OPRawPortWrite
0x18000ea62  mov     rdx, [rbp+arg_10]
0x18000ea66  mov     rcx, rbx
0x18000ea69  call    OPSendStringA
0x18000ea6e  mov     r8d, 10h
0x18000ea74  lea     rdx, aFonthaseuroNot; " FontHasEuro not"
0x18000ea7b  mov     rcx, rbx
0x18000ea7e  call    OPRawPortWrite
0x18000ea83  mov     r8d, 2
0x18000ea89  lea     rdx, gstrCRLF; "\r\n"
0x18000ea90  mov     rcx, rbx
0x18000ea93  call    OPRawPortWrite
0x18000ea98  mov     r8d, edi
0x18000ea9b  lea     rdx, PSFRAG_beginFunction; "{"
0x18000eaa2  mov     rcx, rbx
0x18000eaa5  call    OPRawPortWrite
0x18000eaaa  mov     r8d, 2
0x18000eab0  lea     rdx, gstrCRLF; "\r\n"
0x18000eab7  mov     rcx, rbx
0x18000eaba  call    OPRawPortWrite
0x18000eabf  mov     r8d, edi
0x18000eac2  lea     rdx, PSFRAG_slash; "/"
0x18000eac9  mov     rcx, rbx
0x18000eacc  call    OPRawPortWrite
0x18000ead1  mov     r8d, 5
0x18000ead7  lea     rdx, aEuro; "Euro."
0x18000eade  mov     rcx, rbx
0x18000eae1  call    OPRawPortWrite
0x18000eae6  mov     rdx, [rbp+arg_10]
0x18000eaea  mov     rcx, rbx
0x18000eaed  call    OPSendStringA
0x18000eaf2  mov     r8d, 2
0x18000eaf8  lea     rdx, gstrCRLF; "\r\n"
0x18000eaff  mov     rcx, rbx
0x18000eb02  call    OPRawPortWrite
0x18000eb07  lea     eax, [rsi+rsi*2]
0x18000eb0a  mov     edx, 1
0x18000eb0f  add     eax, eax
0x18000eb11  cdqe
0x18000eb13  lea     rcx, [r15+rax*2]
0x18000eb17  movsxd  rax, esi
0x18000eb1a  mov     [rbp+var_10], rcx
0x18000eb1e  movzx   eax, word ptr [r12+rax*2]
0x18000eb23  mov     word ptr [rbp+arg_8], ax
0x18000eb27  movzx   edi, ax
0x18000eb2a  movzx   ecx, ax
0x18000eb2d  movzx   eax, di
0x18000eb30  add     di, dx
0x18000eb33  cmp     byte ptr [rax+r14], 9
0x18000eb38  jnz     short loc_18000EB2D
0x18000eb3a  movzx   eax, di
0x18000eb3d  add     di, dx
0x18000eb40  cmp     byte ptr [rax+r14], 0Eh
0x18000eb45  jnz     short loc_18000EB2D
0x18000eb47  sub     di, cx
0x18000eb4a  test    r13d, r13d
0x18000eb4d  js      short loc_18000EB9D
0x18000eb4f  cmp     [rbp+arg_0], 0
0x18000eb53  jz      short loc_18000EB9D
0x18000eb55  mov     r8d, edx
0x18000eb58  mov     rcx, rbx
0x18000eb5b  lea     rdx, PSFRAG_slash; "/"
0x18000eb62  call    OPRawPortWrite
0x18000eb67  mov     rdx, [rbp+arg_10]
0x18000eb6b  mov     rcx, rbx
0x18000eb6e  call    OPSendStringA
0x18000eb73  mov     r8d, 11h
0x18000eb79  lea     rdx, aUseobliqueeuro; " UseObliqueEuro {"
0x18000eb80  mov     rcx, rbx
0x18000eb83  call    OPRawPortWrite
0x18000eb88  mov     r8d, 2
0x18000eb8e  lea     rdx, gstrCRLF; "\r\n"
0x18000eb95  mov     rcx, rbx
0x18000eb98  call    OPRawPortWrite
0x18000eb9d  mov     r8d, 2
0x18000eba3  lea     rdx, asc_1800630EC; " ["
0x18000ebaa  mov     rcx, rbx
0x18000ebad  call    OPRawPortWrite
0x18000ebb2  mov     r12, [rbp+var_10]
0x18000ebb6  mov     esi, 6
0x18000ebbb  movsx   edx, word ptr [r12]
0x18000ebc0  mov     rcx, rbx
0x18000ebc3  lea     r12, [r12+2]
0x18000ebc8  call    OPSendInt
0x18000ebcd  sub     esi, 1
0x18000ebd0  jnz     short loc_18000EBBB
0x18000ebd2  mov     r15, [rbp+var_20]
0x18000ebd6  lea     r8d, [rsi+2]
0x18000ebda  mov     r12, [rbp+var_18]
0x18000ebde  lea     rdx, asc_1800630F0; "] "
0x18000ebe5  mov     rcx, rbx
0x18000ebe8  call    OPRawPortWrite
0x18000ebed  lea     r8d, [rsi+2]
0x18000ebf1  mov     rcx, rbx
0x18000ebf4  lea     rdx, gstrCRLF; "\r\n"
0x18000ebfb  call    OPRawPortWrite
0x18000ec00  lea     r8d, [rsi+1]
0x18000ec04  mov     rcx, rbx
0x18000ec07  lea     rdx, PSFRAG_leftcaret; "<"
0x18000ec0e  call    OPRawPortWrite
0x18000ec13  movzx   edx, word ptr [rbp+arg_8]
0x18000ec17  xor     esi, esi
0x18000ec19  add     rdx, r14
0x18000ec1c  movzx   r8d, di
0x18000ec20  mov     rcx, rbx
0x18000ec23  mov     [rbx+0B4Ch], esi
0x18000ec29  call    BSendBitmapAscii7
0x18000ec2e  lea     r8d, [rsi+1]
0x18000ec32  mov     rcx, rbx
0x18000ec35  lea     rdx, PSFRAG_rightcaret; ">"
0x18000ec3c  call    OPRawPortWrite
0x18000ec41  lea     edi, [rsi+2]
0x18000ec44  mov     rcx, rbx
0x18000ec47  mov     r8d, edi
0x18000ec4a  lea     rdx, gstrCRLF; "\r\n"
0x18000ec51  call    OPRawPortWrite
0x18000ec56  test    r13d, r13d
0x18000ec59  js      short loc_18000ECB8
0x18000ec5b  mov     rcx, rbx
0x18000ec5e  cmp     [rbp+arg_0], esi
0x18000ec61  jz      short loc_18000EC94
0x18000ec63  lea     r8d, [rsi+3]
0x18000ec67  lea     rdx, asc_1800630F4; "} {"
0x18000ec6e  call    OPRawPortWrite
0x18000ec73  mov     r8d, edi
0x18000ec76  lea     rdx, gstrCRLF; "\r\n"
0x18000ec7d  mov     rcx, rbx
0x18000ec80  call    OPRawPortWrite
0x18000ec85  mov     esi, r13d
0x18000ec88  mov     [rbp+arg_0], 0
0x18000ec8f  jmp     loc_18000EB07
0x18000ec94  mov     r8d, 8
0x18000ec9a  lea     rdx, aIfelse; "} ifelse"
0x18000eca1  call    OPRawPortWrite
0x18000eca6  mov     r8d, edi
0x18000eca9  lea     rdx, gstrCRLF; "\r\n"
0x18000ecb0  mov     rcx, rbx
0x18000ecb3  call    OPRawPortWrite
0x18000ecb8  mov     r8d, 0Ch
0x18000ecbe  lea     rdx, aAddeuroglyph; "AddEuroGlyph"
0x18000ecc5  mov     rcx, rbx
0x18000ecc8  call    OPRawPortWrite
0x18000eccd  mov     r8d, edi
0x18000ecd0  lea     rdx, gstrCRLF; "\r\n"
0x18000ecd7  mov     rcx, rbx
0x18000ecda  call    OPRawPortWrite
0x18000ecdf  mov     r13d, 1
0x18000ece5  lea     rdx, PSFRAG_slash; "/"
0x18000ecec  mov     r8d, r13d
  ... truncated ...
```
