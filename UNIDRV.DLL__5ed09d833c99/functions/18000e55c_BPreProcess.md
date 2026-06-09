# BPreProcess

- ea: `0x18000e55c`
- end: `0x18000e94a`
- name: `BPreProcess`
- size: `1006`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000d218`

## callees

- `0x180007150`
- `0x180008bf0`
- `0x18000e55c`
- `0x18000e950`
- `0x180045984`
- `0x180046ebc`
- `0x180074d94`
- `0x180074dc0`
- `0x180074e18`

## string_xrefs

- `0x18000e816`: `syntax error - attempting to undefine a symbol that isn't defined !`

## pseudocode

```c
__int64 __fastcall BPreProcess(__int64 a1)
{
  __int64 v1; // r8
  __int64 v2; // r9
  unsigned int v4; // edx
  int v5; // ecx
  __int64 v6; // r8
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  int v19; // edx
  __int64 v20; // rdi
  __int64 v21; // rsi
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rsi
  int v25; // r14d
  int v26; // eax
  int v28; // eax
  __int128 v29; // [rsp+20h] [rbp-20h] BYREF
  char *v30; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v31; // [rsp+38h] [rbp-8h]
  int v32; // [rsp+3Ch] [rbp-4h]

  v1 = *(_QWORD *)(a1 + 456);
  v2 = (unsigned int)(*(_DWORD *)(a1 + 468) - 1);
  v32 = 0;
  v2 *= 32;
  v29 = 0;
  v4 = *(_DWORD *)(v2 + v1 + 8);
  v30 = (char *)(*(_QWORD *)(v2 + v1) + v4);
  v31 = *(_DWORD *)(v2 + v1 + 12) - v4;
  while ( 1 )
  {
    v5 = ParseDirective(&v30, (__int64)&v29, a1);
    if ( v5 == 1 )
      return 1;
    v7 = v5 - 2;
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
                v13 = v12 - 1;
                if ( v13 )
                {
                  if ( v13 != 1 )
                  {
                    WriteDbgTraceErrorGpd(
                      (__int64)"BPreProcess",
                      "internal consistency error - no such preprocessor directive!");
                    v28 = BytesToEOL((__int64 *)&v30);
                    WriteDbgTraceErrorGpd((__int64)"BPreProcess", "%.*s", v28, v30);
                    *(_DWORD *)(a1 + 2224) = 4;
                    goto LABEL_39;
                  }
                  v14 = *(unsigned int *)(a1 + 708);
                  if ( !*(_DWORD *)(*(_QWORD *)(a1 + 696) + 8 * v14) )
                  {
                    WriteDbgTraceErrorGpd(
                      (__int64)"BPreProcess",
                      "syntax error - #Endif directive must be preceeded by #Ifdef or #Elseifdef or #Else !");
                    goto LABEL_38;
                  }
                  *(_DWORD *)(a1 + 708) = v14 - 1;
                }
                else
                {
                  v15 = *(unsigned int *)(a1 + 708);
                  v16 = *(_QWORD *)(a1 + 696);
                  if ( !*(_DWORD *)(v16 + 8 * v15) )
                  {
                    WriteDbgTraceErrorGpd(
                      (__int64)"BPreProcess",
                      "syntax error - #Else directive must be preceeded by #Ifdef or #Elseifdef !");
                    goto LABEL_38;
                  }
                  if ( *(_DWORD *)(v16 + 8 * v15) == 2 )
                  {
                    WriteDbgTraceErrorGpd(
                      (__int64)"BPreProcess",
                      "syntax error - #Else directive cannot follow #Else !");
                    goto LABEL_38;
                  }
                  *(_DWORD *)(v16 + 8 * v15) = 2;
                  v17 = *(unsigned int *)(a1 + 708);
                  v18 = *(_QWORD *)(a1 + 696);
                  v19 = *(_DWORD *)(v18 + 8 * v17 + 4);
                  if ( v19 )
                  {
                    if ( v19 == 1 )
                      *(_DWORD *)(v18 + 8 * v17 + 4) = 0;
                  }
                  else
                  {
                    *(_DWORD *)(v18 + 8 * v17 + 4) = 2;
                  }
                }
              }
              else
              {
                v20 = *(unsigned int *)(a1 + 708);
                v21 = *(_QWORD *)(a1 + 696);
                if ( !*(_DWORD *)(v21 + 8 * v20) )
                {
                  WriteDbgTraceErrorGpd(
                    (__int64)"BPreProcess",
                    "syntax error - #Elseifdef directive must be preceeded by #Ifdef !");
LABEL_38:
                  *(_DWORD *)(a1 + 2224) = 1;
LABEL_39:
                  *(_DWORD *)(a1 + 2220) = 3;
                  return 0;
                }
                if ( *(_DWORD *)(v21 + 8 * v20) == 2 )
                {
                  WriteDbgTraceErrorGpd(
                    (__int64)"BPreProcess",
                    "syntax error - #Elseifdef directive cannot follow #Else !");
                  goto LABEL_38;
                }
                v22 = *(_DWORD *)(v21 + 8 * v20 + 4);
                if ( v22 )
                {
                  if ( v22 == 1
                    && (unsigned int)DWsearchSymbolListForAAR(
                                       (__int64)&v29,
                                       *(_DWORD *)(*(_QWORD *)(a1 + 384) + 28LL),
                                       a1) != -1 )
                  {
                    *(_DWORD *)(v21 + 8 * v20 + 4) = 0;
                  }
                }
                else
                {
                  *(_DWORD *)(v21 + 8 * v20 + 4) = 2;
                }
              }
            }
            else
            {
              v23 = *(unsigned int *)(a1 + 708);
              v24 = *(_QWORD *)(a1 + 696);
              v25 = *(_DWORD *)(v24 + 8 * v23 + 4);
              *(_DWORD *)(a1 + 708) = v23 + 1;
              if ( (unsigned int)(v23 + 1) >= *(_DWORD *)(a1 + 704) )
              {
                if ( *(int *)(a1 + 2220) < 2 )
                {
                  *(_DWORD *)(a1 + 2224) = 2;
                  *(_DWORD *)(a1 + 2220) = 2;
                  *(_DWORD *)(a1 + 2216) = 29;
                }
                return 0;
              }
              *(_DWORD *)(v24 + 8LL * (unsigned int)(v23 + 1) + 4) = DWsearchSymbolListForAAR(
                                                                       (__int64)&v29,
                                                                       *(_DWORD *)(*(_QWORD *)(a1 + 384) + 28LL),
                                                                       a1) == -1;
              if ( v25 )
                *(_DWORD *)(*(_QWORD *)(a1 + 696) + 8LL * *(unsigned int *)(a1 + 708) + 4) = 2;
              *(_DWORD *)(*(_QWORD *)(a1 + 696) + 8LL * *(unsigned int *)(a1 + 708)) = 1;
            }
          }
          else if ( !*(_DWORD *)(*(_QWORD *)(a1 + 696) + 8LL * *(unsigned int *)(a1 + 708) + 4) )
          {
            SetPPPrefix((__int64)&v29, a1);
          }
        }
        else
        {
          if ( !*(_DWORD *)(*(_QWORD *)(a1 + 696) + 8LL * *(unsigned int *)(a1 + 708) + 4) )
            return 1;
          deleteToEOL((__int64)&v30);
        }
      }
      else if ( !*(_DWORD *)(*(_QWORD *)(a1 + 696) + 8LL * *(unsigned int *)(a1 + 708) + 4)
             && !(unsigned int)SymbolTableRemove((__int64)&v29, a1)
             && *(_DWORD *)(a1 + 2220) != 3 )
      {
        WriteDbgTraceErrorGpd(
          (__int64)"BPreProcess",
          "syntax error - attempting to undefine a symbol that isn't defined !");
        v26 = BytesToEOL((__int64 *)&v29);
        WriteDbgTraceErrorGpd((__int64)"BPreProcess", "%.*s", v26, (const char *)v29);
        goto LABEL_38;
      }
    }
    else if ( !*(_DWORD *)(*(_QWORD *)(a1 + 696) + 8LL * *(unsigned int *)(a1 + 708) + 4)
           && !SymbolTableAdd((__int64)&v29, a1, v6) )
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18000e55c  push    rbp
0x18000e55e  push    rbx
0x18000e55f  push    rsi
0x18000e560  push    rdi
0x18000e561  push    r13
0x18000e563  push    r14
0x18000e565  push    r15
0x18000e567  mov     rbp, rsp
0x18000e56a  sub     rsp, 40h
0x18000e56e  mov     r8, [rcx+1C8h]
0x18000e575  mov     r15d, 1
0x18000e57b  mov     r9d, [rcx+1D4h]
0x18000e582  xorps   xmm0, xmm0
0x18000e585  sub     r9d, r15d
0x18000e588  mov     [rbp+var_4], 0
0x18000e58f  shl     r9, 5
0x18000e593  mov     rbx, rcx
0x18000e596  movups  [rbp+var_20], xmm0
0x18000e59a  lea     r13d, [r15+1]
0x18000e59e  mov     edx, [r9+r8+8]
0x18000e5a3  mov     eax, edx
0x18000e5a5  add     rax, [r9+r8]
0x18000e5a9  mov     [rbp+var_10], rax
0x18000e5ad  mov     eax, [r9+r8+0Ch]
0x18000e5b2  sub     eax, edx
0x18000e5b4  mov     [rbp+var_8], eax
0x18000e5b7  mov     r14d, 3
0x18000e5bd  mov     r8, rbx
0x18000e5c0  lea     rdx, [rbp+var_20]
0x18000e5c4  lea     rcx, [rbp+var_10]
0x18000e5c8  call    ParseDirective
0x18000e5cd  mov     ecx, eax
0x18000e5cf  cmp     eax, r15d
0x18000e5d2  jz      loc_18000E937
0x18000e5d8  sub     ecx, r13d
0x18000e5db  jz      loc_18000E861
0x18000e5e1  sub     ecx, r15d
0x18000e5e4  jz      loc_18000E7DD
0x18000e5ea  sub     ecx, r15d
0x18000e5ed  jz      loc_18000E7B7
0x18000e5f3  sub     ecx, r15d
0x18000e5f6  jz      loc_18000E78E
0x18000e5fc  sub     ecx, r15d
0x18000e5ff  jz      loc_18000E703
0x18000e605  sub     ecx, r15d
0x18000e608  jz      loc_18000E69B
0x18000e60e  sub     ecx, r15d
0x18000e611  jz      short loc_18000E641
0x18000e613  cmp     ecx, r15d
0x18000e616  jnz     loc_18000E8A4
0x18000e61c  mov     ecx, [rbx+2C4h]
0x18000e622  mov     rax, [rbx+2B8h]
0x18000e629  cmp     dword ptr [rax+rcx*8], 0
0x18000e62d  jz      loc_18000E88F
0x18000e633  lea     eax, [rcx-1]
0x18000e636  mov     [rbx+2C4h], eax
0x18000e63c  jmp     loc_18000E5BD
0x18000e641  mov     eax, [rbx+2C4h]
0x18000e647  mov     rcx, [rbx+2B8h]
0x18000e64e  cmp     dword ptr [rcx+rax*8], 0
0x18000e652  jz      loc_18000E8F2
0x18000e658  cmp     [rcx+rax*8], r13d
0x18000e65c  jz      loc_18000E8E9
0x18000e662  mov     [rcx+rax*8], r13d
0x18000e666  mov     eax, [rbx+2C4h]
0x18000e66c  mov     rcx, [rbx+2B8h]
0x18000e673  mov     edx, [rcx+rax*8+4]
0x18000e677  test    edx, edx
0x18000e679  jnz     short loc_18000E685
0x18000e67b  mov     [rcx+rax*8+4], r13d
0x18000e680  jmp     loc_18000E5BD
0x18000e685  cmp     edx, r15d
0x18000e688  jnz     loc_18000E5BD
0x18000e68e  mov     dword ptr [rcx+rax*8+4], 0
0x18000e696  jmp     loc_18000E5BD
0x18000e69b  mov     edi, [rbx+2C4h]
0x18000e6a1  mov     rsi, [rbx+2B8h]
0x18000e6a8  cmp     dword ptr [rsi+rdi*8], 0
0x18000e6ac  jz      loc_18000E904
0x18000e6b2  cmp     [rsi+rdi*8], r13d
0x18000e6b6  jz      loc_18000E8FB
0x18000e6bc  mov     eax, [rsi+rdi*8+4]
0x18000e6c0  test    eax, eax
0x18000e6c2  jnz     short loc_18000E6CE
0x18000e6c4  mov     [rsi+rdi*8+4], r13d
0x18000e6c9  jmp     loc_18000E5BD
0x18000e6ce  cmp     eax, r15d
0x18000e6d1  jnz     loc_18000E5BD
0x18000e6d7  mov     rdx, [rbx+180h]
0x18000e6de  lea     rcx, [rbp+var_20]
0x18000e6e2  mov     r8, rbx
0x18000e6e5  mov     edx, [rdx+1Ch]
0x18000e6e8  call    DWsearchSymbolListForAAR
0x18000e6ed  cmp     eax, 0FFFFFFFFh
0x18000e6f0  jz      loc_18000E5BD
0x18000e6f6  mov     dword ptr [rsi+rdi*8+4], 0
0x18000e6fe  jmp     loc_18000E5BD
0x18000e703  mov     eax, [rbx+2C4h]
0x18000e709  mov     rsi, [rbx+2B8h]
0x18000e710  lea     edi, [rax+1]
0x18000e713  mov     r14d, [rsi+rax*8+4]
0x18000e718  mov     [rbx+2C4h], edi
0x18000e71e  cmp     edi, [rbx+2C0h]
0x18000e724  jnb     loc_18000E90D
0x18000e72a  mov     rdx, [rbx+180h]
0x18000e731  lea     rcx, [rbp+var_20]
0x18000e735  mov     r8, rbx
0x18000e738  mov     edx, [rdx+1Ch]
0x18000e73b  call    DWsearchSymbolListForAAR
0x18000e740  mov     edx, 4
0x18000e745  lea     r8d, [rdx+4]
0x18000e749  cmp     eax, 0FFFFFFFFh
0x18000e74c  jnz     short loc_18000E753
0x18000e74e  mov     ecx, r15d
0x18000e751  jmp     short loc_18000E755
0x18000e753  xor     ecx, ecx
0x18000e755  mov     eax, edi
0x18000e757  imul    rax, r8
0x18000e75b  add     rax, rsi
0x18000e75e  mov     [rax+rdx], ecx
0x18000e761  test    r14d, r14d
0x18000e764  jz      short loc_18000E778
0x18000e766  mov     ecx, [rbx+2C4h]
0x18000e76c  mov     rax, [rbx+2B8h]
0x18000e773  mov     [rax+rcx*8+4], r13d
0x18000e778  mov     ecx, [rbx+2C4h]
0x18000e77e  mov     rax, [rbx+2B8h]
0x18000e785  mov     [rax+rcx*8], r15d
0x18000e789  jmp     loc_18000E5B7
0x18000e78e  mov     ecx, [rbx+2C4h]
0x18000e794  mov     rax, [rbx+2B8h]
0x18000e79b  cmp     dword ptr [rax+rcx*8+4], 0
0x18000e7a0  jnz     loc_18000E5BD
0x18000e7a6  mov     rdx, rbx
0x18000e7a9  lea     rcx, [rbp+var_20]
0x18000e7ad  call    SetPPPrefix
0x18000e7b2  jmp     loc_18000E5BD
0x18000e7b7  mov     ecx, [rbx+2C4h]
0x18000e7bd  mov     rax, [rbx+2B8h]
0x18000e7c4  cmp     dword ptr [rax+rcx*8+4], 0
0x18000e7c9  jz      loc_18000E937
0x18000e7cf  lea     rcx, [rbp+var_10]
0x18000e7d3  call    deleteToEOL
0x18000e7d8  jmp     loc_18000E5BD
0x18000e7dd  mov     ecx, [rbx+2C4h]
0x18000e7e3  mov     rax, [rbx+2B8h]
0x18000e7ea  cmp     dword ptr [rax+rcx*8+4], 0
0x18000e7ef  jnz     loc_18000E5BD
0x18000e7f5  mov     rdx, rbx
0x18000e7f8  lea     rcx, [rbp+var_20]
0x18000e7fc  call    SymbolTableRemove
0x18000e801  test    eax, eax
0x18000e803  jnz     loc_18000E5BD
0x18000e809  cmp     [rbx+8ACh], r14d
0x18000e810  jz      loc_18000E5BD
0x18000e816  lea     rdx, aSyntaxErrorAtt_0; "syntax error - attempting to undefine a"...
0x18000e81d  lea     rcx, aBpreprocess; "BPreProcess"
0x18000e824  call    WriteDbgTraceErrorGpd
0x18000e829  lea     rcx, [rbp+var_20]
0x18000e82d  call    BytesToEOL
0x18000e832  mov     r9, qword ptr [rbp+var_20]
0x18000e836  lea     rdx, aS; "%.*s"
0x18000e83d  mov     r8d, eax
0x18000e840  lea     rcx, aBpreprocess; "BPreProcess"
0x18000e847  call    WriteDbgTraceErrorGpd
0x18000e84c  mov     [rbx+8B0h], r15d
0x18000e853  mov     [rbx+8ACh], r14d
0x18000e85a  xor     eax, eax
0x18000e85c  jmp     loc_18000E93A
0x18000e861  mov     ecx, [rbx+2C4h]
0x18000e867  mov     rax, [rbx+2B8h]
0x18000e86e  cmp     dword ptr [rax+rcx*8+4], 0
0x18000e873  jnz     loc_18000E5BD
0x18000e879  mov     rdx, rbx
0x18000e87c  lea     rcx, [rbp+var_20]
0x18000e880  call    SymbolTableAdd
0x18000e885  test    eax, eax
0x18000e887  jnz     loc_18000E5BD
0x18000e88d  jmp     short loc_18000E85A
0x18000e88f  lea     rdx, aSyntaxErrorEnd; "syntax error - #Endif directive must be"...
0x18000e896  lea     rcx, aBpreprocess; "BPreProcess"
0x18000e89d  call    WriteDbgTraceErrorGpd
0x18000e8a2  jmp     short loc_18000E84C
0x18000e8a4  lea     rdx, aInternalConsis_0; "internal consistency error - no such pr"...
0x18000e8ab  lea     rcx, aBpreprocess; "BPreProcess"
0x18000e8b2  call    WriteDbgTraceErrorGpd
0x18000e8b7  lea     rcx, [rbp+var_10]
0x18000e8bb  call    BytesToEOL
0x18000e8c0  mov     r9, [rbp+var_10]
0x18000e8c4  lea     rdx, aS; "%.*s"
0x18000e8cb  mov     r8d, eax
0x18000e8ce  lea     rcx, aBpreprocess; "BPreProcess"
0x18000e8d5  call    WriteDbgTraceErrorGpd
0x18000e8da  mov     dword ptr [rbx+8B0h], 4
0x18000e8e4  jmp     loc_18000E853
0x18000e8e9  lea     rdx, aSyntaxErrorEls_2; "syntax error - #Else directive cannot f"...
0x18000e8f0  jmp     short loc_18000E896
0x18000e8f2  lea     rdx, aSyntaxErrorEls_0; "syntax error - #Else directive must be "...
0x18000e8f9  jmp     short loc_18000E896
0x18000e8fb  lea     rdx, aSyntaxErrorEls; "syntax error - #Elseifdef directive can"...
0x18000e902  jmp     short loc_18000E896
0x18000e904  lea     rdx, aSyntaxErrorEls_1; "syntax error - #Elseifdef directive mus"...
0x18000e90b  jmp     short loc_18000E896
0x18000e90d  cmp     [rbx+8ACh], r13d
0x18000e914  jge     loc_18000E85A
0x18000e91a  mov     [rbx+8B0h], r13d
0x18000e921  mov     [rbx+8ACh], r13d
0x18000e928  mov     dword ptr [rbx+8A8h], 1Dh
0x18000e932  jmp     loc_18000E85A
0x18000e937  mov     eax, r15d
0x18000e93a  add     rsp, 40h
0x18000e93e  pop     r15
0x18000e940  pop     r14
0x18000e942  pop     r13
0x18000e944  pop     rdi
0x18000e945  pop     rsi
0x18000e946  pop     rbx
0x18000e947  pop     rbp
0x18000e948  retn
```
