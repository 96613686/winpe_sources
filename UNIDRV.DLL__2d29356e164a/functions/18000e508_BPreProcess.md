# BPreProcess

- ea: `0x18000e508`
- end: `0x18000e8f5`
- name: `BPreProcess`
- size: `1005`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000d1d8`

## callees

- `0x180007220`
- `0x180008c80`
- `0x18000e508`
- `0x18000e900`
- `0x1800447b0`
- `0x180045b04`
- `0x180072d04`
- `0x180072d30`
- `0x180072d88`

## string_xrefs

- `0x18000e7c2`: `syntax error - attempting to undefine a symbol that isn't defined !`

## pseudocode

```c
__int64 __fastcall BPreProcess(__int64 a1)
{
  __int64 v1; // r8
  __int64 v2; // r9
  unsigned int v4; // edx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // edx
  __int64 v19; // rdi
  __int64 v20; // rsi
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rsi
  int v24; // r14d
  int v25; // eax
  int v27; // eax
  __int128 v28; // [rsp+20h] [rbp-20h] BYREF
  const char *v29; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v30; // [rsp+38h] [rbp-8h]
  int v31; // [rsp+3Ch] [rbp-4h]

  v1 = *(_QWORD *)(a1 + 456);
  v2 = (unsigned int)(*(_DWORD *)(a1 + 468) - 1);
  v31 = 0;
  v2 *= 32;
  v28 = 0;
  v4 = *(_DWORD *)(v2 + v1 + 8);
  v29 = (const char *)(*(_QWORD *)(v2 + v1) + v4);
  v30 = *(_DWORD *)(v2 + v1 + 12) - v4;
  while ( 1 )
  {
    v5 = ParseDirective(&v29, &v28, a1);
    if ( v5 == 1 )
      return 1;
    v6 = v5 - 2;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 )
            {
              v11 = v10 - 1;
              if ( v11 )
              {
                v12 = v11 - 1;
                if ( v12 )
                {
                  if ( v12 != 1 )
                  {
                    WriteDbgTraceErrorGpd("BPreProcess", "internal consistency error - no such preprocessor directive!");
                    v27 = BytesToEOL(&v29);
                    WriteDbgTraceErrorGpd("BPreProcess", "%.*s", v27, v29);
                    *(_DWORD *)(a1 + 2224) = 4;
                    goto LABEL_39;
                  }
                  v13 = *(unsigned int *)(a1 + 708);
                  if ( !*(_DWORD *)(*(_QWORD *)(a1 + 696) + 8 * v13) )
                  {
                    WriteDbgTraceErrorGpd(
                      "BPreProcess",
                      "syntax error - #Endif directive must be preceeded by #Ifdef or #Elseifdef or #Else !");
                    goto LABEL_38;
                  }
                  *(_DWORD *)(a1 + 708) = v13 - 1;
                }
                else
                {
                  v14 = *(unsigned int *)(a1 + 708);
                  v15 = *(_QWORD *)(a1 + 696);
                  if ( !*(_DWORD *)(v15 + 8 * v14) )
                  {
                    WriteDbgTraceErrorGpd(
                      "BPreProcess",
                      "syntax error - #Else directive must be preceeded by #Ifdef or #Elseifdef !");
                    goto LABEL_38;
                  }
                  if ( *(_DWORD *)(v15 + 8 * v14) == 2 )
                  {
                    WriteDbgTraceErrorGpd("BPreProcess", "syntax error - #Else directive cannot follow #Else !");
                    goto LABEL_38;
                  }
                  *(_DWORD *)(v15 + 8 * v14) = 2;
                  v16 = *(unsigned int *)(a1 + 708);
                  v17 = *(_QWORD *)(a1 + 696);
                  v18 = *(_DWORD *)(v17 + 8 * v16 + 4);
                  if ( v18 )
                  {
                    if ( v18 == 1 )
                      *(_DWORD *)(v17 + 8 * v16 + 4) = 0;
                  }
                  else
                  {
                    *(_DWORD *)(v17 + 8 * v16 + 4) = 2;
                  }
                }
              }
              else
              {
                v19 = *(unsigned int *)(a1 + 708);
                v20 = *(_QWORD *)(a1 + 696);
                if ( !*(_DWORD *)(v20 + 8 * v19) )
                {
                  WriteDbgTraceErrorGpd(
                    "BPreProcess",
                    "syntax error - #Elseifdef directive must be preceeded by #Ifdef !");
LABEL_38:
                  *(_DWORD *)(a1 + 2224) = 1;
LABEL_39:
                  *(_DWORD *)(a1 + 2220) = 3;
                  return 0;
                }
                if ( *(_DWORD *)(v20 + 8 * v19) == 2 )
                {
                  WriteDbgTraceErrorGpd("BPreProcess", "syntax error - #Elseifdef directive cannot follow #Else !");
                  goto LABEL_38;
                }
                v21 = *(_DWORD *)(v20 + 8 * v19 + 4);
                if ( v21 )
                {
                  if ( v21 == 1
                    && (unsigned int)DWsearchSymbolListForAAR(&v28, *(unsigned int *)(*(_QWORD *)(a1 + 384) + 28LL), a1) != -1 )
                  {
                    *(_DWORD *)(v20 + 8 * v19 + 4) = 0;
                  }
                }
                else
                {
                  *(_DWORD *)(v20 + 8 * v19 + 4) = 2;
                }
              }
            }
            else
            {
              v22 = *(unsigned int *)(a1 + 708);
              v23 = *(_QWORD *)(a1 + 696);
              v24 = *(_DWORD *)(v23 + 8 * v22 + 4);
              *(_DWORD *)(a1 + 708) = v22 + 1;
              if ( (unsigned int)(v22 + 1) >= *(_DWORD *)(a1 + 704) )
              {
                if ( *(int *)(a1 + 2220) < 2 )
                {
                  *(_DWORD *)(a1 + 2224) = 2;
                  *(_DWORD *)(a1 + 2220) = 2;
                  *(_DWORD *)(a1 + 2216) = 29;
                }
                return 0;
              }
              *(_DWORD *)(v23 + 8LL * (unsigned int)(v22 + 1) + 4) = DWsearchSymbolListForAAR(
                                                                       &v28,
                                                                       *(unsigned int *)(*(_QWORD *)(a1 + 384) + 28LL),
                                                                       a1) == -1;
              if ( v24 )
                *(_DWORD *)(*(_QWORD *)(a1 + 696) + 8LL * *(unsigned int *)(a1 + 708) + 4) = 2;
              *(_DWORD *)(*(_QWORD *)(a1 + 696) + 8LL * *(unsigned int *)(a1 + 708)) = 1;
            }
          }
          else if ( !*(_DWORD *)(*(_QWORD *)(a1 + 696) + 8LL * *(unsigned int *)(a1 + 708) + 4) )
          {
            SetPPPrefix(&v28, a1);
          }
        }
        else
        {
          if ( !*(_DWORD *)(*(_QWORD *)(a1 + 696) + 8LL * *(unsigned int *)(a1 + 708) + 4) )
            return 1;
          deleteToEOL(&v29);
        }
      }
      else if ( !*(_DWORD *)(*(_QWORD *)(a1 + 696) + 8LL * *(unsigned int *)(a1 + 708) + 4)
             && !(unsigned int)SymbolTableRemove((__int64)&v28, a1)
             && *(_DWORD *)(a1 + 2220) != 3 )
      {
        WriteDbgTraceErrorGpd("BPreProcess", "syntax error - attempting to undefine a symbol that isn't defined !");
        v25 = BytesToEOL(&v28);
        WriteDbgTraceErrorGpd("BPreProcess", "%.*s", v25, (const char *)v28);
        goto LABEL_38;
      }
    }
    else if ( !*(_DWORD *)(*(_QWORD *)(a1 + 696) + 8LL * *(unsigned int *)(a1 + 708) + 4)
           && !(unsigned int)SymbolTableAdd(&v28, a1) )
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18000e508  push    rbp
0x18000e50a  push    rbx
0x18000e50b  push    rsi
0x18000e50c  push    rdi
0x18000e50d  push    r13
0x18000e50f  push    r14
0x18000e511  push    r15
0x18000e513  mov     rbp, rsp
0x18000e516  sub     rsp, 40h
0x18000e51a  mov     r8, [rcx+1C8h]
0x18000e521  mov     r15d, 1
0x18000e527  mov     r9d, [rcx+1D4h]
0x18000e52e  xorps   xmm0, xmm0
0x18000e531  sub     r9d, r15d
0x18000e534  mov     [rbp+var_4], 0
0x18000e53b  shl     r9, 5
0x18000e53f  mov     rbx, rcx
0x18000e542  movups  [rbp+var_20], xmm0
0x18000e546  lea     r13d, [r15+1]
0x18000e54a  mov     edx, [r9+r8+8]
0x18000e54f  mov     eax, edx
0x18000e551  add     rax, [r9+r8]
0x18000e555  mov     [rbp+var_10], rax
0x18000e559  mov     eax, [r9+r8+0Ch]
0x18000e55e  sub     eax, edx
0x18000e560  mov     [rbp+var_8], eax
0x18000e563  mov     r14d, 3
0x18000e569  mov     r8, rbx
0x18000e56c  lea     rdx, [rbp+var_20]
0x18000e570  lea     rcx, [rbp+var_10]
0x18000e574  call    ParseDirective
0x18000e579  mov     ecx, eax
0x18000e57b  cmp     eax, r15d
0x18000e57e  jz      loc_18000E8E3
0x18000e584  sub     ecx, r13d
0x18000e587  jz      loc_18000E80D
0x18000e58d  sub     ecx, r15d
0x18000e590  jz      loc_18000E789
0x18000e596  sub     ecx, r15d
0x18000e599  jz      loc_18000E763
0x18000e59f  sub     ecx, r15d
0x18000e5a2  jz      loc_18000E73A
0x18000e5a8  sub     ecx, r15d
0x18000e5ab  jz      loc_18000E6AF
0x18000e5b1  sub     ecx, r15d
0x18000e5b4  jz      loc_18000E647
0x18000e5ba  sub     ecx, r15d
0x18000e5bd  jz      short loc_18000E5ED
0x18000e5bf  cmp     ecx, r15d
0x18000e5c2  jnz     loc_18000E850
0x18000e5c8  mov     ecx, [rbx+2C4h]
0x18000e5ce  mov     rax, [rbx+2B8h]
0x18000e5d5  cmp     dword ptr [rax+rcx*8], 0
0x18000e5d9  jz      loc_18000E83B
0x18000e5df  lea     eax, [rcx-1]
0x18000e5e2  mov     [rbx+2C4h], eax
0x18000e5e8  jmp     loc_18000E569
0x18000e5ed  mov     eax, [rbx+2C4h]
0x18000e5f3  mov     rcx, [rbx+2B8h]
0x18000e5fa  cmp     dword ptr [rcx+rax*8], 0
0x18000e5fe  jz      loc_18000E89E
0x18000e604  cmp     [rcx+rax*8], r13d
0x18000e608  jz      loc_18000E895
0x18000e60e  mov     [rcx+rax*8], r13d
0x18000e612  mov     eax, [rbx+2C4h]
0x18000e618  mov     rcx, [rbx+2B8h]
0x18000e61f  mov     edx, [rcx+rax*8+4]
0x18000e623  test    edx, edx
0x18000e625  jnz     short loc_18000E631
0x18000e627  mov     [rcx+rax*8+4], r13d
0x18000e62c  jmp     loc_18000E569
0x18000e631  cmp     edx, r15d
0x18000e634  jnz     loc_18000E569
0x18000e63a  mov     dword ptr [rcx+rax*8+4], 0
0x18000e642  jmp     loc_18000E569
0x18000e647  mov     edi, [rbx+2C4h]
0x18000e64d  mov     rsi, [rbx+2B8h]
0x18000e654  cmp     dword ptr [rsi+rdi*8], 0
0x18000e658  jz      loc_18000E8B0
0x18000e65e  cmp     [rsi+rdi*8], r13d
0x18000e662  jz      loc_18000E8A7
0x18000e668  mov     eax, [rsi+rdi*8+4]
0x18000e66c  test    eax, eax
0x18000e66e  jnz     short loc_18000E67A
0x18000e670  mov     [rsi+rdi*8+4], r13d
0x18000e675  jmp     loc_18000E569
0x18000e67a  cmp     eax, r15d
0x18000e67d  jnz     loc_18000E569
0x18000e683  mov     rdx, [rbx+180h]
0x18000e68a  lea     rcx, [rbp+var_20]
0x18000e68e  mov     r8, rbx
0x18000e691  mov     edx, [rdx+1Ch]
0x18000e694  call    DWsearchSymbolListForAAR
0x18000e699  cmp     eax, 0FFFFFFFFh
0x18000e69c  jz      loc_18000E569
0x18000e6a2  mov     dword ptr [rsi+rdi*8+4], 0
0x18000e6aa  jmp     loc_18000E569
0x18000e6af  mov     eax, [rbx+2C4h]
0x18000e6b5  mov     rsi, [rbx+2B8h]
0x18000e6bc  lea     edi, [rax+1]
0x18000e6bf  mov     r14d, [rsi+rax*8+4]
0x18000e6c4  mov     [rbx+2C4h], edi
0x18000e6ca  cmp     edi, [rbx+2C0h]
0x18000e6d0  jnb     loc_18000E8B9
0x18000e6d6  mov     rdx, [rbx+180h]
0x18000e6dd  lea     rcx, [rbp+var_20]
0x18000e6e1  mov     r8, rbx
0x18000e6e4  mov     edx, [rdx+1Ch]
0x18000e6e7  call    DWsearchSymbolListForAAR
0x18000e6ec  mov     edx, 4
0x18000e6f1  lea     r8d, [rdx+4]
0x18000e6f5  cmp     eax, 0FFFFFFFFh
0x18000e6f8  jnz     short loc_18000E6FF
0x18000e6fa  mov     ecx, r15d
0x18000e6fd  jmp     short loc_18000E701
0x18000e6ff  xor     ecx, ecx
0x18000e701  mov     eax, edi
0x18000e703  imul    rax, r8
0x18000e707  add     rax, rsi
0x18000e70a  mov     [rax+rdx], ecx
0x18000e70d  test    r14d, r14d
0x18000e710  jz      short loc_18000E724
0x18000e712  mov     ecx, [rbx+2C4h]
0x18000e718  mov     rax, [rbx+2B8h]
0x18000e71f  mov     [rax+rcx*8+4], r13d
0x18000e724  mov     ecx, [rbx+2C4h]
0x18000e72a  mov     rax, [rbx+2B8h]
0x18000e731  mov     [rax+rcx*8], r15d
0x18000e735  jmp     loc_18000E563
0x18000e73a  mov     ecx, [rbx+2C4h]
0x18000e740  mov     rax, [rbx+2B8h]
0x18000e747  cmp     dword ptr [rax+rcx*8+4], 0
0x18000e74c  jnz     loc_18000E569
0x18000e752  mov     rdx, rbx
0x18000e755  lea     rcx, [rbp+var_20]
0x18000e759  call    SetPPPrefix
0x18000e75e  jmp     loc_18000E569
0x18000e763  mov     ecx, [rbx+2C4h]
0x18000e769  mov     rax, [rbx+2B8h]
0x18000e770  cmp     dword ptr [rax+rcx*8+4], 0
0x18000e775  jz      loc_18000E8E3
0x18000e77b  lea     rcx, [rbp+var_10]
0x18000e77f  call    deleteToEOL
0x18000e784  jmp     loc_18000E569
0x18000e789  mov     ecx, [rbx+2C4h]
0x18000e78f  mov     rax, [rbx+2B8h]
0x18000e796  cmp     dword ptr [rax+rcx*8+4], 0
0x18000e79b  jnz     loc_18000E569
0x18000e7a1  mov     rdx, rbx
0x18000e7a4  lea     rcx, [rbp+var_20]
0x18000e7a8  call    SymbolTableRemove
0x18000e7ad  test    eax, eax
0x18000e7af  jnz     loc_18000E569
0x18000e7b5  cmp     [rbx+8ACh], r14d
0x18000e7bc  jz      loc_18000E569
0x18000e7c2  lea     rdx, aSyntaxErrorAtt_0; "syntax error - attempting to undefine a"...
0x18000e7c9  lea     rcx, aBpreprocess; "BPreProcess"
0x18000e7d0  call    WriteDbgTraceErrorGpd
0x18000e7d5  lea     rcx, [rbp+var_20]
0x18000e7d9  call    BytesToEOL
0x18000e7de  mov     r9, qword ptr [rbp+var_20]
0x18000e7e2  lea     rdx, aS; "%.*s"
0x18000e7e9  mov     r8d, eax
0x18000e7ec  lea     rcx, aBpreprocess; "BPreProcess"
0x18000e7f3  call    WriteDbgTraceErrorGpd
0x18000e7f8  mov     [rbx+8B0h], r15d
0x18000e7ff  mov     [rbx+8ACh], r14d
0x18000e806  xor     eax, eax
0x18000e808  jmp     loc_18000E8E6
0x18000e80d  mov     ecx, [rbx+2C4h]
0x18000e813  mov     rax, [rbx+2B8h]
0x18000e81a  cmp     dword ptr [rax+rcx*8+4], 0
0x18000e81f  jnz     loc_18000E569
0x18000e825  mov     rdx, rbx
0x18000e828  lea     rcx, [rbp+var_20]
0x18000e82c  call    SymbolTableAdd
0x18000e831  test    eax, eax
0x18000e833  jnz     loc_18000E569
0x18000e839  jmp     short loc_18000E806
0x18000e83b  lea     rdx, aSyntaxErrorEnd; "syntax error - #Endif directive must be"...
0x18000e842  lea     rcx, aBpreprocess; "BPreProcess"
0x18000e849  call    WriteDbgTraceErrorGpd
0x18000e84e  jmp     short loc_18000E7F8
0x18000e850  lea     rdx, aInternalConsis_0; "internal consistency error - no such pr"...
0x18000e857  lea     rcx, aBpreprocess; "BPreProcess"
0x18000e85e  call    WriteDbgTraceErrorGpd
0x18000e863  lea     rcx, [rbp+var_10]
0x18000e867  call    BytesToEOL
0x18000e86c  mov     r9, [rbp+var_10]
0x18000e870  lea     rdx, aS; "%.*s"
0x18000e877  mov     r8d, eax
0x18000e87a  lea     rcx, aBpreprocess; "BPreProcess"
0x18000e881  call    WriteDbgTraceErrorGpd
0x18000e886  mov     dword ptr [rbx+8B0h], 4
0x18000e890  jmp     loc_18000E7FF
0x18000e895  lea     rdx, aSyntaxErrorEls_2; "syntax error - #Else directive cannot f"...
0x18000e89c  jmp     short loc_18000E842
0x18000e89e  lea     rdx, aSyntaxErrorEls_0; "syntax error - #Else directive must be "...
0x18000e8a5  jmp     short loc_18000E842
0x18000e8a7  lea     rdx, aSyntaxErrorEls; "syntax error - #Elseifdef directive can"...
0x18000e8ae  jmp     short loc_18000E842
0x18000e8b0  lea     rdx, aSyntaxErrorEls_1; "syntax error - #Elseifdef directive mus"...
0x18000e8b7  jmp     short loc_18000E842
0x18000e8b9  cmp     [rbx+8ACh], r13d
0x18000e8c0  jge     loc_18000E806
0x18000e8c6  mov     [rbx+8B0h], r13d
0x18000e8cd  mov     [rbx+8ACh], r13d
0x18000e8d4  mov     dword ptr [rbx+8A8h], 1Dh
0x18000e8de  jmp     loc_18000E806
0x18000e8e3  mov     eax, r15d
0x18000e8e6  add     rsp, 40h
0x18000e8ea  pop     r15
0x18000e8ec  pop     r14
0x18000e8ee  pop     r13
0x18000e8f0  pop     rdi
0x18000e8f1  pop     rsi
0x18000e8f2  pop     rbx
0x18000e8f3  pop     rbp
0x18000e8f4  retn
```
