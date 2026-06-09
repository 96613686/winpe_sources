# VBSAttestationSerializeIdentityHeader

- ea: `0x140038160`
- end: `0x1400384d7`
- name: `VBSAttestationSerializeIdentityHeader`
- size: `887`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140037edc`

## callees

- `0x140003ad6`
- `0x140037b10`
- `0x140037e90`
- `0x140038074`
- `0x140038160`
- `0x1400384e0`

## string_xrefs

- `0x1400382d8`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\serialization.cxx`
- `0x140038492`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\serialization.cxx`
- `0x1400384b1`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\serialization.cxx`

## pseudocode

```c
__int64 __fastcall VBSAttestationSerializeIdentityHeader(unsigned int *a1, __int64 a2, unsigned int *a3)
{
  _DWORD *v6; // r14
  unsigned int v7; // eax
  unsigned int v8; // ecx
  __int64 v9; // r8
  unsigned int v10; // ebx
  __int64 v11; // rcx
  unsigned int *v12; // r15
  unsigned int v13; // eax
  unsigned int v14; // edx
  unsigned int *v15; // r13
  unsigned int v16; // eax
  unsigned int v17; // ecx
  unsigned int v18; // eax
  unsigned int *v19; // r12
  int v20; // eax
  unsigned int v21; // r8d
  unsigned int v22; // edx
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // rsi
  __int64 v26; // rax
  char *v27; // rsi
  char *v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rax
  char *v31; // rsi
  char *v32; // r14
  __int64 v33; // rax
  char *v34; // rbx
  char *v35; // rdi
  __int64 v37; // [rsp+20h] [rbp-20h]
  unsigned int *v38; // [rsp+28h] [rbp-18h]
  _DWORD *v39; // [rsp+30h] [rbp-10h]
  unsigned int *v40; // [rsp+38h] [rbp-8h]
  unsigned int v41; // [rsp+80h] [rbp+40h] BYREF
  __int64 v42; // [rsp+88h] [rbp+48h] BYREF
  unsigned int v43; // [rsp+98h] [rbp+58h] BYREF

  v42 = a2;
  v41 = 0;
  v43 = 0;
  if ( !a1 || !a3 )
  {
    v10 = -2146893819;
    v9 = 186;
    v11 = 2148073477LL;
    goto LABEL_54;
  }
  v6 = a1 + 3;
  v7 = a1[3];
  v8 = v7 + 32;
  if ( v7 + 32 < v7 )
  {
    v9 = 198;
LABEL_5:
    v10 = -1073741675;
    v11 = 3221225621LL;
LABEL_54:
    VBS_ATTEST_TRACE_ERROR_IN(
      v11,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\serialization.cxx",
      v9);
    return v10;
  }
  v12 = a1 + 4;
  v13 = a1[4];
  v14 = v13 + v8;
  if ( v13 + v8 < v13 )
  {
    v9 = 204;
    goto LABEL_5;
  }
  v15 = a1 + 6;
  v16 = a1[6];
  v17 = v16 + v14;
  if ( v16 + v14 < v16 )
  {
    v9 = 210;
    goto LABEL_5;
  }
  v18 = a1[7];
  v40 = a1 + 7;
  if ( v18 + v17 < v18 )
  {
    *a3 = -1;
    v23 = 216;
    goto LABEL_52;
  }
  *a3 = v18 + v17;
  v19 = a1 + 8;
  v38 = a1 + 2;
  v37 = (__int64)a1 + *v12 + *v6 + a1[2] + 32;
  if ( a2 )
  {
    if ( (int)CopyULONGAdvanceDest(&v42, a1) >= 0 )
    {
      if ( (int)CopyULONGAdvanceDest(&v42, a1 + 1) >= 0 )
      {
        if ( (int)CopyULONGAdvanceDest(&v42, a1 + 2) >= 0 )
        {
          if ( (int)CopyULONGAdvanceDest(&v42, v6) >= 0 )
          {
            if ( (int)CopyULONGAdvanceDest(&v42, a1 + 4) >= 0 )
            {
              v39 = a1 + 5;
              if ( (int)CopyULONGAdvanceDest(&v42, a1 + 5) >= 0 )
              {
                if ( (int)CopyULONGAdvanceDest(&v42, a1 + 6) >= 0 )
                {
                  if ( (int)CopyULONGAdvanceDest(&v42, a1 + 7) >= 0 )
                  {
                    v25 = v42;
                    v20 = VBSAttestationSerializeClaimAttributes(v19, v42, &v41);
                    v10 = v20;
                    if ( v20 < 0 )
                    {
                      v9 = 314;
                      goto LABEL_14;
                    }
                    v26 = v41;
                    *a3 += v41;
                    v27 = (char *)(v26 + v25);
                    v28 = (char *)v19 + *v38;
                    if ( *v6 )
                    {
                      memcpy_0(v27, (char *)v19 + *v38, (unsigned int)*v6);
                      v29 = (unsigned int)*v6;
                      v28 += v29;
                      v27 += v29;
                    }
                    memcpy_0(v27, v28, *v12);
                    v30 = *v12;
                    v31 = &v27[v30];
                    v32 = &v28[v30];
                    if ( *v39 )
                    {
                      v20 = VBSAttestationSerializePadding(v37, v31, &v43);
                      v10 = v20;
                      if ( v20 < 0 )
                      {
                        v9 = 349;
                        goto LABEL_14;
                      }
                      v33 = v43;
                      *a3 += v43;
                      v34 = &v32[*v39];
                      v35 = &v31[v33];
                    }
                    else
                    {
                      v34 = &v28[v30];
                      v35 = v31;
                    }
                    memcpy_0(v35, v34, *v15);
                    memcpy_0(&v35[*v15], &v34[*v15], *v40);
                    return 0;
                  }
                  v24 = 301;
                }
                else
                {
                  v24 = 296;
                }
              }
              else
              {
                v24 = 291;
              }
            }
            else
            {
              v24 = 286;
            }
          }
          else
          {
            v24 = 281;
          }
        }
        else
        {
          v24 = 276;
        }
      }
      else
      {
        v24 = 271;
      }
    }
    else
    {
      v24 = 266;
    }
    VBS_ATTEST_TRACE_ERROR_IN(
      3221225701LL,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\serialization.cxx",
      v24);
    return 0;
  }
  v20 = VBSAttestationSerializeClaimAttributes(a1 + 8, 0, &v41);
  v10 = v20;
  if ( v20 < 0 )
  {
    v9 = 232;
LABEL_14:
    v11 = (unsigned int)v20;
    goto LABEL_54;
  }
  v21 = v41 + *a3;
  if ( v21 < v41 )
  {
    *a3 = -1;
    v23 = 238;
    goto LABEL_52;
  }
  v10 = 0;
  *a3 = v21;
  if ( a1[5] )
  {
    v20 = VBSAttestationSerializePadding(v37, 0, &v43);
    v10 = v20;
    if ( v20 < 0 )
    {
      v9 = 250;
      goto LABEL_14;
    }
    v22 = v43 + *a3;
    if ( v22 >= v43 )
    {
      *a3 = v22;
      return 0;
    }
    *a3 = -1;
    v23 = 256;
LABEL_52:
    VBS_ATTEST_TRACE_ERROR_IN(
      3221225621LL,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\serialization.cxx",
      v23);
    return (unsigned int)-1073741675;
  }
  return v10;
}

```

## disassembly

```asm
0x140038160  mov     [rsp-38h+arg_10], rbx
0x140038165  mov     [rsp-38h+arg_8], rdx
0x14003816a  push    rbp
0x14003816b  push    rsi
0x14003816c  push    rdi
0x14003816d  push    r12
0x14003816f  push    r13
0x140038171  push    r14
0x140038173  push    r15
0x140038175  mov     rbp, rsp
0x140038178  sub     rsp, 40h
0x14003817c  mov     [rbp+arg_0], 0
0x140038183  mov     rdi, r8
0x140038186  mov     [rbp+arg_18], 0
0x14003818d  mov     r9, rdx
0x140038190  mov     rsi, rcx
0x140038193  test    rcx, rcx
0x140038196  jz      loc_1400384A4
0x14003819c  test    r8, r8
0x14003819f  jz      loc_1400384A4
0x1400381a5  lea     r14, [rcx+0Ch]
0x1400381a9  mov     eax, [r14]
0x1400381ac  lea     ecx, [rax+20h]
0x1400381af  cmp     ecx, eax
0x1400381b1  jnb     short loc_1400381C7
0x1400381b3  mov     r8d, 0C6h
0x1400381b9  mov     edi, 0C0000095h
0x1400381be  mov     ebx, edi
0x1400381c0  mov     ecx, edi
0x1400381c2  jmp     loc_1400384B1
0x1400381c7  lea     r15, [rsi+10h]
0x1400381cb  mov     eax, [r15]
0x1400381ce  lea     edx, [rax+rcx]
0x1400381d1  cmp     edx, eax
0x1400381d3  jnb     short loc_1400381DD
0x1400381d5  mov     r8d, 0CCh
0x1400381db  jmp     short loc_1400381B9
0x1400381dd  lea     r13, [rsi+18h]
0x1400381e1  mov     eax, [r13+0]
0x1400381e5  lea     ecx, [rax+rdx]
0x1400381e8  cmp     ecx, eax
0x1400381ea  jnb     short loc_1400381F4
0x1400381ec  mov     r8d, 0D2h
0x1400381f2  jmp     short loc_1400381B9
0x1400381f4  lea     rbx, [rsi+1Ch]
0x1400381f8  mov     eax, [rbx]
0x1400381fa  mov     [rbp+var_8], rbx
0x1400381fe  lea     edx, [rax+rcx]
0x140038201  cmp     edx, eax
0x140038203  jb      loc_140038480
0x140038209  mov     [r8], edx
0x14003820c  lea     rax, [rsi+8]
0x140038210  mov     r8d, [r15]
0x140038213  lea     r12, [rsi+20h]
0x140038217  mov     edx, [r14]
0x14003821a  add     r8, r12
0x14003821d  mov     [rbp+var_18], rax
0x140038221  add     r8, rdx
0x140038224  mov     eax, [rax]
0x140038226  add     rax, r8
0x140038229  mov     [rbp+var_20], rax
0x14003822d  test    r9, r9
0x140038230  jnz     loc_1400382C2
0x140038236  lea     r8, [rbp+arg_0]
0x14003823a  xor     edx, edx
0x14003823c  mov     rcx, r12
0x14003823f  call    VBSAttestationSerializeClaimAttributes
0x140038244  mov     ebx, eax
0x140038246  test    eax, eax
0x140038248  jns     short loc_140038257
0x14003824a  mov     r8d, 0E8h
0x140038250  mov     ecx, eax
0x140038252  jmp     loc_1400384B1
0x140038257  mov     r8d, [rdi]
0x14003825a  add     r8d, [rbp+arg_0]
0x14003825e  cmp     r8d, [rbp+arg_0]
0x140038262  jb      short loc_1400382B1
0x140038264  xor     ebx, ebx
0x140038266  mov     [rdi], r8d
0x140038269  cmp     [rsi+14h], ebx
0x14003826c  jbe     loc_1400384BD
0x140038272  mov     rcx, [rbp+var_20]
0x140038276  lea     r8, [rbp+arg_18]
0x14003827a  xor     edx, edx
0x14003827c  call    VBSAttestationSerializePadding
0x140038281  mov     ebx, eax
0x140038283  test    eax, eax
0x140038285  jns     short loc_14003828F
0x140038287  mov     r8d, 0FAh
0x14003828d  jmp     short loc_140038250
0x14003828f  mov     edx, [rdi]
0x140038291  add     edx, [rbp+arg_18]
0x140038294  cmp     edx, [rbp+arg_18]
0x140038297  jb      short loc_1400382A0
0x140038299  mov     [rdi], edx
0x14003829b  jmp     loc_14003847C
0x1400382a0  mov     dword ptr [rdi], 0FFFFFFFFh
0x1400382a6  mov     r8d, 100h
0x1400382ac  jmp     loc_14003848D
0x1400382b1  mov     dword ptr [rdi], 0FFFFFFFFh
0x1400382b7  mov     r8d, 0EEh
0x1400382bd  jmp     loc_14003848D
0x1400382c2  mov     rdx, rsi
0x1400382c5  lea     rcx, [rbp+arg_8]
0x1400382c9  call    CopyULONGAdvanceDest
0x1400382ce  test    eax, eax
0x1400382d0  jns     short loc_1400382EE
0x1400382d2  mov     r8d, 10Ah
0x1400382d8  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1400382df  mov     ecx, 0C00000E5h
0x1400382e4  call    VBS_ATTEST_TRACE_ERROR_IN
0x1400382e9  jmp     loc_14003847C
0x1400382ee  lea     rdx, [rsi+4]
0x1400382f2  lea     rcx, [rbp+arg_8]
0x1400382f6  call    CopyULONGAdvanceDest
0x1400382fb  test    eax, eax
0x1400382fd  jns     short loc_140038307
0x1400382ff  mov     r8d, 10Fh
0x140038305  jmp     short loc_1400382D8
0x140038307  lea     rdx, [rsi+8]
0x14003830b  lea     rcx, [rbp+arg_8]
0x14003830f  call    CopyULONGAdvanceDest
0x140038314  test    eax, eax
0x140038316  jns     short loc_140038320
0x140038318  mov     r8d, 114h
0x14003831e  jmp     short loc_1400382D8
0x140038320  mov     rdx, r14
0x140038323  lea     rcx, [rbp+arg_8]
0x140038327  call    CopyULONGAdvanceDest
0x14003832c  test    eax, eax
0x14003832e  jns     short loc_140038338
0x140038330  mov     r8d, 119h
0x140038336  jmp     short loc_1400382D8
0x140038338  mov     rdx, r15
0x14003833b  lea     rcx, [rbp+arg_8]
0x14003833f  call    CopyULONGAdvanceDest
0x140038344  test    eax, eax
0x140038346  jns     short loc_140038350
0x140038348  mov     r8d, 11Eh
0x14003834e  jmp     short loc_1400382D8
0x140038350  lea     rax, [rsi+14h]
0x140038354  mov     rdx, rax
0x140038357  mov     [rbp+var_10], rax
0x14003835b  lea     rcx, [rbp+arg_8]
0x14003835f  call    CopyULONGAdvanceDest
0x140038364  test    eax, eax
0x140038366  jns     short loc_140038373
0x140038368  mov     r8d, 123h
0x14003836e  jmp     loc_1400382D8
0x140038373  mov     rdx, r13
0x140038376  lea     rcx, [rbp+arg_8]
0x14003837a  call    CopyULONGAdvanceDest
0x14003837f  test    eax, eax
0x140038381  jns     short loc_14003838E
0x140038383  mov     r8d, 128h
0x140038389  jmp     loc_1400382D8
0x14003838e  mov     rdx, rbx
0x140038391  lea     rcx, [rbp+arg_8]
0x140038395  call    CopyULONGAdvanceDest
0x14003839a  test    eax, eax
0x14003839c  jns     short loc_1400383A9
0x14003839e  mov     r8d, 12Dh
0x1400383a4  jmp     loc_1400382D8
0x1400383a9  mov     rsi, [rbp+arg_8]
0x1400383ad  lea     r8, [rbp+arg_0]
0x1400383b1  mov     rdx, rsi
0x1400383b4  mov     rcx, r12
0x1400383b7  call    VBSAttestationSerializeClaimAttributes
0x1400383bc  mov     ebx, eax
0x1400383be  test    eax, eax
0x1400383c0  jns     short loc_1400383CD
0x1400383c2  mov     r8d, 13Ah
0x1400383c8  jmp     loc_140038250
0x1400383cd  mov     eax, [rbp+arg_0]
0x1400383d0  add     [rdi], eax
0x1400383d2  add     rsi, rax
0x1400383d5  mov     rax, [rbp+var_18]
0x1400383d9  mov     ebx, [rax]
0x1400383db  add     rbx, r12
0x1400383de  cmp     dword ptr [r14], 0
0x1400383e2  jbe     short loc_1400383FB
0x1400383e4  mov     r8d, [r14]; Size
0x1400383e7  mov     rdx, rbx; Src
0x1400383ea  mov     rcx, rsi; void *
0x1400383ed  call    memcpy_0
0x1400383f2  mov     eax, [r14]
0x1400383f5  add     rbx, rax
0x1400383f8  add     rsi, rax
0x1400383fb  mov     r8d, [r15]; Size
0x1400383fe  mov     rdx, rbx; Src
0x140038401  mov     rcx, rsi; void *
0x140038404  call    memcpy_0
0x140038409  mov     eax, [r15]
0x14003840c  mov     r15, [rbp+var_10]
0x140038410  add     rsi, rax
0x140038413  lea     r14, [rax+rbx]
0x140038417  cmp     dword ptr [r15], 0
0x14003841b  jbe     short loc_14003844F
0x14003841d  mov     rcx, [rbp+var_20]
0x140038421  lea     r8, [rbp+arg_18]
0x140038425  mov     rdx, rsi
0x140038428  call    VBSAttestationSerializePadding
0x14003842d  mov     ebx, eax
0x14003842f  test    eax, eax
0x140038431  jns     short loc_14003843E
0x140038433  mov     r8d, 15Dh
0x140038439  jmp     loc_140038250
0x14003843e  mov     eax, [rbp+arg_18]
0x140038441  add     [rdi], eax
0x140038443  mov     ebx, [r15]
0x140038446  add     rbx, r14
0x140038449  lea     rdi, [rsi+rax]
0x14003844d  jmp     short loc_140038455
0x14003844f  mov     rbx, r14
0x140038452  mov     rdi, rsi
0x140038455  mov     r8d, [r13+0]; Size
0x140038459  mov     rdx, rbx; Src
0x14003845c  mov     rcx, rdi; void *
0x14003845f  call    memcpy_0
0x140038464  mov     eax, [r13+0]
0x140038468  mov     rcx, [rbp+var_8]
0x14003846c  lea     rdx, [rax+rbx]; Src
0x140038470  mov     r8d, [rcx]; Size
0x140038473  lea     rcx, [rax+rdi]; void *
0x140038477  call    memcpy_0
0x14003847c  xor     ebx, ebx
0x14003847e  jmp     short loc_1400384BD
0x140038480  mov     dword ptr [r8], 0FFFFFFFFh
0x140038487  mov     r8d, 0D8h
0x14003848d  mov     edi, 0C0000095h
0x140038492  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140038499  mov     ecx, edi
0x14003849b  call    VBS_ATTEST_TRACE_ERROR_IN
0x1400384a0  mov     ebx, edi
0x1400384a2  jmp     short loc_1400384BD
0x1400384a4  mov     ebx, 80090005h
0x1400384a9  mov     r8d, 0BAh
0x1400384af  mov     ecx, ebx
0x1400384b1  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1400384b8  call    VBS_ATTEST_TRACE_ERROR_IN
0x1400384bd  mov     eax, ebx
0x1400384bf  mov     rbx, [rsp+40h+arg_10]
0x1400384c7  add     rsp, 40h
0x1400384cb  pop     r15
0x1400384cd  pop     r14
0x1400384cf  pop     r13
0x1400384d1  pop     r12
0x1400384d3  pop     rdi
0x1400384d4  pop     rsi
0x1400384d5  pop     rbp
0x1400384d6  retn
```
