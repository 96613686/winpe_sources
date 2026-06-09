# px_ipps_createTabDftBase_32f

- ea: `0x18004aad4`
- end: `0x18004ad2e`
- name: `px_ipps_createTabDftBase_32f`
- size: `602`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180047f10`
- `0x180048120`
- `0x180048d70`
- `0x180048f80`
- `0x180049b00`
- `0x180049d10`
- `0x18005372c`
- `0x180055e5c`
- `0x1800589cc`

## callees

- `0x18000b6f4`
- `0x18000b748`
- `0x180011040`
- `0x18004aad4`

## pseudocode

```c
__int64 __fastcall px_ipps_createTabDftBase_32f(int a1)
{
  __int64 v1; // rdi
  __int64 result; // rax
  int v3; // esi
  __int64 v4; // rbx
  double v5; // xmm7_8
  __int64 v6; // rbp
  float *v7; // r14
  double v8; // xmm6_8
  float v9; // xmm1_4
  float v10; // xmm0_4
  __int64 v11; // rbp
  float *v12; // r14
  double v13; // xmm6_8
  float v14; // xmm1_4
  float v15; // xmm0_4
  int v16; // ebp
  float *v17; // r14
  double v18; // xmm6_8
  float v19; // xmm1_4
  float v20; // xmm0_4
  __int64 v21; // rcx
  int *v22; // rdx
  int v23; // xmm1_4
  __int64 v24; // rcx
  int *v25; // rdx
  int v26; // xmm0_4
  __int64 v27; // rcx
  int *v28; // rdx
  int v29; // eax

  v1 = a1;
  result = px_ippsMalloc_8u((unsigned int)(8 * a1));
  v3 = 0;
  v4 = result;
  if ( result )
  {
    v5 = 6.283185307179586 / (double)(int)v1;
    if ( (v1 & 1) != 0 )
    {
      LODWORD(v6) = (int)v1 / 2;
      if ( (int)v1 / 2 >= 0 )
      {
        v7 = (float *)result;
        do
        {
          v8 = (double)v3 * v5;
          v9 = cos(v8);
          *v7 = v9;
          ++v3;
          v7 += 2;
          v10 = COERCE_DOUBLE(COERCE_UNSIGNED_INT64(o_sin_0(v8)) ^ _xmm);
          *(v7 - 1) = v10;
        }
        while ( v3 <= (int)v6 );
      }
    }
    else
    {
      if ( (v1 & 2) != 0 )
      {
        LODWORD(v11) = (int)v1 / 4;
        if ( (int)v1 / 4 >= 0 )
        {
          v12 = (float *)result;
          do
          {
            v13 = (double)v3 * v5;
            v14 = cos(v13);
            *v12 = v14;
            ++v3;
            v12 += 2;
            v15 = COERCE_DOUBLE(COERCE_UNSIGNED_INT64(o_sin_0(v13)) ^ _xmm);
            *(v12 - 1) = v15;
          }
          while ( v3 <= (int)v11 );
        }
      }
      else
      {
        v16 = (int)v1 / 8;
        if ( (int)v1 / 8 >= 0 )
        {
          v17 = (float *)result;
          do
          {
            v18 = (double)v3 * v5;
            v19 = cos(v18);
            *v17 = v19;
            ++v3;
            v17 += 2;
            v20 = COERCE_DOUBLE(COERCE_UNSIGNED_INT64(o_sin_0(v18)) ^ _xmm);
            *(v17 - 1) = v20;
          }
          while ( v3 <= v16 );
        }
        v21 = v16 + 1;
        v11 = (int)v1 / 4;
        if ( v21 <= v11 )
        {
          v22 = (int *)(v4 + 8 * (v11 - v21));
          do
          {
            *(_DWORD *)(v4 + 8 * v21) = v22[1] ^ _xmm;
            v23 = *v22;
            ++v21;
            v22 -= 2;
            *(_DWORD *)(v4 + 8 * v21 - 4) = v23 ^ _xmm;
          }
          while ( v21 <= v11 );
        }
      }
      v24 = (int)v11 + 1;
      v6 = (int)v1 / 2;
      if ( v24 <= v6 )
      {
        v25 = (int *)(v4 + 8 * (v6 - v24));
        do
        {
          v26 = *v25;
          v25 -= 2;
          *(_DWORD *)(v4 + 8 * v24++) = v26 ^ _xmm;
          *(_DWORD *)(v4 + 8 * v24 - 4) = v25[3];
        }
        while ( v24 <= v6 );
      }
    }
    v27 = (int)v6 + 1;
    if ( v27 < v1 )
    {
      v28 = (int *)(v4 + 8 * (v1 - v27));
      do
      {
        v29 = *v28;
        v28 -= 2;
        *(_DWORD *)(v4 + 8 * v27++) = v29;
        *(_DWORD *)(v4 + 8 * v27 - 4) = v28[3] ^ _xmm;
      }
      while ( v27 < v1 );
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18004aad4  mov     rax, rsp
0x18004aad7  mov     [rax+8], rbx
0x18004aadb  mov     [rax+10h], rbp
0x18004aadf  mov     [rax+18h], rsi
0x18004aae3  mov     [rax+20h], rdi
0x18004aae7  push    r14
0x18004aae9  sub     rsp, 40h
0x18004aaed  movsxd  rdi, ecx
0x18004aaf0  movaps  xmmword ptr [rax-18h], xmm6
0x18004aaf4  movaps  xmmword ptr [rax-28h], xmm7
0x18004aaf8  mov     ecx, edi
0x18004aafa  shl     ecx, 3
0x18004aafd  call    px_ippsMalloc_8u
0x18004ab02  xor     esi, esi
0x18004ab04  mov     rbx, rax
0x18004ab07  test    rax, rax
0x18004ab0a  jz      loc_18004AD09
0x18004ab10  movsd   xmm7, cs:__real@401921fb54442d18
0x18004ab18  movd    xmm0, edi
0x18004ab1c  mov     eax, edi
0x18004ab1e  cdq
0x18004ab1f  cvtdq2pd xmm0, xmm0
0x18004ab23  divsd   xmm7, xmm0
0x18004ab27  test    dil, 1
0x18004ab2b  jz      short loc_18004AB84
0x18004ab2d  sub     eax, edx
0x18004ab2f  sar     eax, 1
0x18004ab31  mov     ebp, eax
0x18004ab33  js      loc_18004ACCE
0x18004ab39  mov     r14, rbx
0x18004ab3c  movd    xmm6, esi
0x18004ab40  cvtdq2pd xmm6, xmm6
0x18004ab44  mulsd   xmm6, xmm7
0x18004ab48  movaps  xmm0, xmm6; X
0x18004ab4b  call    cos
0x18004ab50  xorps   xmm1, xmm1
0x18004ab53  cvtsd2ss xmm1, xmm0
0x18004ab57  movaps  xmm0, xmm6; X
0x18004ab5a  movss   dword ptr [r14], xmm1
0x18004ab5f  call    _o_sin_0
0x18004ab64  inc     esi
0x18004ab66  lea     r14, [r14+8]
0x18004ab6a  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x18004ab71  cvtsd2ss xmm0, xmm0
0x18004ab75  movss   dword ptr [r14-4], xmm0
0x18004ab7b  cmp     esi, ebp
0x18004ab7d  jle     short loc_18004AB3C
0x18004ab7f  jmp     loc_18004ACCE
0x18004ab84  test    dil, 2
0x18004ab88  jz      short loc_18004ABE7
0x18004ab8a  and     edx, 3
0x18004ab8d  add     eax, edx
0x18004ab8f  sar     eax, 2
0x18004ab92  mov     ebp, eax
0x18004ab94  test    eax, eax
0x18004ab96  js      loc_18004AC8C
0x18004ab9c  mov     r14, rbx
0x18004ab9f  movd    xmm6, esi
0x18004aba3  cvtdq2pd xmm6, xmm6
0x18004aba7  mulsd   xmm6, xmm7
0x18004abab  movaps  xmm0, xmm6; X
0x18004abae  call    cos
0x18004abb3  xorps   xmm1, xmm1
0x18004abb6  cvtsd2ss xmm1, xmm0
0x18004abba  movaps  xmm0, xmm6; X
0x18004abbd  movss   dword ptr [r14], xmm1
0x18004abc2  call    _o_sin_0
0x18004abc7  inc     esi
0x18004abc9  lea     r14, [r14+8]
0x18004abcd  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x18004abd4  cvtsd2ss xmm0, xmm0
0x18004abd8  movss   dword ptr [r14-4], xmm0
0x18004abde  cmp     esi, ebp
0x18004abe0  jle     short loc_18004AB9F
0x18004abe2  jmp     loc_18004AC8C
0x18004abe7  and     edx, 7
0x18004abea  add     eax, edx
0x18004abec  sar     eax, 3
0x18004abef  mov     ebp, eax
0x18004abf1  test    eax, eax
0x18004abf3  js      short loc_18004AC3B
0x18004abf5  mov     r14, rbx
0x18004abf8  movd    xmm6, esi
0x18004abfc  cvtdq2pd xmm6, xmm6
0x18004ac00  mulsd   xmm6, xmm7
0x18004ac04  movaps  xmm0, xmm6; X
0x18004ac07  call    cos
0x18004ac0c  xorps   xmm1, xmm1
0x18004ac0f  cvtsd2ss xmm1, xmm0
0x18004ac13  movaps  xmm0, xmm6; X
0x18004ac16  movss   dword ptr [r14], xmm1
0x18004ac1b  call    _o_sin_0
0x18004ac20  inc     esi
0x18004ac22  lea     r14, [r14+8]
0x18004ac26  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x18004ac2d  cvtsd2ss xmm0, xmm0
0x18004ac31  movss   dword ptr [r14-4], xmm0
0x18004ac37  cmp     esi, ebp
0x18004ac39  jle     short loc_18004ABF8
0x18004ac3b  lea     eax, [rbp+1]
0x18004ac3e  movsxd  rcx, eax
0x18004ac41  mov     eax, edi
0x18004ac43  cdq
0x18004ac44  and     edx, 3
0x18004ac47  add     eax, edx
0x18004ac49  sar     eax, 2
0x18004ac4c  movsxd  rbp, eax
0x18004ac4f  cmp     rcx, rbp
0x18004ac52  jg      short loc_18004AC8C
0x18004ac54  mov     rax, rbp
0x18004ac57  sub     rax, rcx
0x18004ac5a  lea     rdx, [rbx+rax*8]
0x18004ac5e  movss   xmm0, dword ptr [rdx+4]
0x18004ac63  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x18004ac6a  movss   dword ptr [rbx+rcx*8], xmm0
0x18004ac6f  movss   xmm1, dword ptr [rdx]
0x18004ac73  inc     rcx
0x18004ac76  lea     rdx, [rdx-8]
0x18004ac7a  xorps   xmm1, cs:__xmm@80000000800000008000000080000000
0x18004ac81  movss   dword ptr [rbx+rcx*8-4], xmm1
0x18004ac87  cmp     rcx, rbp
0x18004ac8a  jle     short loc_18004AC5E
0x18004ac8c  lea     eax, [rbp+1]
0x18004ac8f  movsxd  rcx, eax
0x18004ac92  mov     eax, edi
0x18004ac94  cdq
0x18004ac95  sub     eax, edx
0x18004ac97  sar     eax, 1
0x18004ac99  movsxd  rbp, eax
0x18004ac9c  cmp     rcx, rbp
0x18004ac9f  jg      short loc_18004ACCE
0x18004aca1  mov     rax, rbp
0x18004aca4  sub     rax, rcx
0x18004aca7  lea     rdx, [rbx+rax*8]
0x18004acab  movss   xmm0, dword ptr [rdx]
0x18004acaf  lea     rdx, [rdx-8]
0x18004acb3  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x18004acba  movss   dword ptr [rbx+rcx*8], xmm0
0x18004acbf  mov     eax, [rdx+0Ch]
0x18004acc2  inc     rcx
0x18004acc5  mov     [rbx+rcx*8-4], eax
0x18004acc9  cmp     rcx, rbp
0x18004accc  jle     short loc_18004ACAB
0x18004acce  lea     eax, [rbp+1]
0x18004acd1  movsxd  rcx, eax
0x18004acd4  cmp     rcx, rdi
0x18004acd7  jge     short loc_18004AD06
0x18004acd9  mov     rax, rdi
0x18004acdc  sub     rax, rcx
0x18004acdf  lea     rdx, [rbx+rax*8]
0x18004ace3  mov     eax, [rdx]
0x18004ace5  lea     rdx, [rdx-8]
0x18004ace9  mov     [rbx+rcx*8], eax
0x18004acec  inc     rcx
0x18004acef  movss   xmm0, dword ptr [rdx+0Ch]
0x18004acf4  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x18004acfb  movss   dword ptr [rbx+rcx*8-4], xmm0
0x18004ad01  cmp     rcx, rdi
0x18004ad04  jl      short loc_18004ACE3
0x18004ad06  mov     rax, rbx
0x18004ad09  mov     rbx, [rsp+48h+arg_0]
0x18004ad0e  mov     rbp, [rsp+48h+arg_8]
0x18004ad13  mov     rsi, [rsp+48h+arg_10]
0x18004ad18  movaps  xmm6, [rsp+48h+var_18]
0x18004ad1d  movaps  xmm7, [rsp+48h+var_28]
0x18004ad22  mov     rdi, [rsp+48h+arg_18]
0x18004ad27  add     rsp, 40h
0x18004ad2b  pop     r14
0x18004ad2d  retn
```
