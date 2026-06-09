# WriteHints

- ea: `0x180050e84`
- end: `0x1800511e6`
- name: `WriteHints`
- size: `866`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18004ff08`
- `0x18005017c`

## callees

- `0x180001ee0`
- `0x18004e048`
- `0x18004eff8`
- `0x180050620`
- `0x180050e84`
- `0x180052ed8`
- `0x180052f30`

## pseudocode

```c
__int64 __fastcall WriteHints(__int64 a1, int a2, unsigned int a3)
{
  unsigned __int8 v4; // cl
  unsigned __int8 v5; // r12
  unsigned __int8 v6; // r14
  unsigned __int8 v7; // r15
  unsigned __int16 v8; // r13
  __int64 result; // rax
  unsigned int v11; // edi
  unsigned __int8 *v12; // rax
  __int64 v13; // xmm1_8
  __int64 v14; // rcx
  __int64 v15; // xmm1_8
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rdx
  unsigned int v19; // r14d
  _DWORD *v20; // r8
  _DWORD *v21; // rdx
  _DWORD *v22; // r8
  _DWORD *v23; // rdx
  unsigned __int8 v24; // [rsp+20h] [rbp-A9h]
  int v25; // [rsp+24h] [rbp-A5h]
  _DWORD *v26; // [rsp+30h] [rbp-99h]
  _DWORD *v27; // [rsp+38h] [rbp-91h]
  __int64 v28; // [rsp+40h] [rbp-89h]
  _DWORD *v29; // [rsp+48h] [rbp-81h]
  _DWORD *v30; // [rsp+50h] [rbp-79h]
  _DWORD *v31; // [rsp+60h] [rbp-69h]
  _DWORD *v32; // [rsp+68h] [rbp-61h]
  _DWORD *v33; // [rsp+80h] [rbp-49h]
  _DWORD *v34; // [rsp+88h] [rbp-41h]
  __int64 v35; // [rsp+90h] [rbp-39h]
  _DWORD *v36; // [rsp+98h] [rbp-31h]
  _DWORD *v37; // [rsp+A0h] [rbp-29h]
  _DWORD *v38; // [rsp+B0h] [rbp-19h]
  _DWORD *v39; // [rsp+B8h] [rbp-11h]

  v25 = a2;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v24 = 0;
  v7 = 0;
  v8 = 0;
  result = 0;
  if ( !*(_WORD *)(a1 + 25816) )
    return result;
  v11 = 1;
  do
  {
    if ( a2 )
      goto LABEL_50;
    if ( !v5 )
    {
      v12 = *(unsigned __int8 **)(a1 + 14160);
      v5 = 0x80;
      v4 = *v12;
      result = (__int64)(v12 + 1);
      *(_QWORD *)(a1 + 14160) = result;
      v24 = v4;
    }
    if ( (v5 & v4) != 0 )
    {
LABEL_50:
      if ( !*(_DWORD *)(a1 + 24LL * v8 + 22764) || *(_DWORD *)(a1 + 26036) )
      {
        v17 = *(_QWORD *)(a1 + 24LL * v8 + 22752);
        v18 = *(_QWORD *)(a1 + 24LL * v8 + 22744);
        if ( *(_WORD *)(a1 + 24LL * v8 + 22760) == 1 )
          result = HStem(a1, v18, v17, a3);
        else
          result = VStem(a1, v18, v17, a3);
      }
      else if ( *(_WORD *)(a1 + 24LL * v8 + 22760) == 1 )
      {
        if ( v6 >= 3u )
          goto LABEL_47;
        result = v6++;
        v13 = *(_QWORD *)(a1 + 24LL * v8 + 22760);
        v14 = 3 * result;
        *(_OWORD *)&(&v26)[v14] = *(_OWORD *)(a1 + 24LL * v8 + 22744);
        *(&v28 + v14) = v13;
      }
      else
      {
        if ( v7 >= 3u )
          goto LABEL_47;
        result = v7++;
        v15 = *(_QWORD *)(a1 + 24LL * v8 + 22760);
        v16 = 3 * result;
        *(_OWORD *)&(&v33)[v16] = *(_OWORD *)(a1 + 24LL * v8 + 22744);
        *(&v35 + v16) = v15;
      }
      a2 = v25;
      v4 = v24;
    }
    v5 >>= 1;
    ++v8;
  }
  while ( v8 < *(_WORD *)(a1 + 25816) );
  switch ( v6 )
  {
    case 3u:
      v19 = (*(_BYTE *)(a1 + 15000) & 1) == 0 && !*(_DWORD *)(a1 + 21940) && *(_DWORD *)(a1 + 21924) == 2 || a3;
      XC_WriteT1PStackValue(a1, v26, v19);
      XC_WriteT1PStackValue(a1, v27, v19);
      XC_WriteT1PStackValue(a1, v29, v19);
      XC_WriteT1PStackValue(a1, v30, v19);
      XC_WriteT1PStackValue(a1, v31, v19);
      XC_WriteT1PStackValue(a1, v32, v19);
      result = XC_WriteT1OpCode(a1, 3074, v19);
      *(_DWORD *)(a1 + 21932) = 0;
      goto LABEL_33;
    case 1u:
      v20 = v27;
      v21 = v26;
LABEL_31:
      result = HStem(a1, v21, v20, a3);
      goto LABEL_33;
    case 2u:
      HStem(a1, v26, v27, a3);
      v20 = v30;
      v21 = v29;
      goto LABEL_31;
  }
  if ( v6 > 3u )
    goto LABEL_47;
LABEL_33:
  if ( v7 != 3 )
  {
    if ( v7 == 1 )
    {
      v22 = v34;
      v23 = v33;
      return VStem(a1, v23, v22, a3);
    }
    if ( v7 == 2 )
    {
      VStem(a1, v33, v34, a3);
      v22 = v37;
      v23 = v36;
      return VStem(a1, v23, v22, a3);
    }
    if ( v7 <= 3u )
      return result;
LABEL_47:
    XCF_FatalErrorHandler(a1, 14);
  }
  if ( ((*(_BYTE *)(a1 + 15000) & 1) != 0 || *(_DWORD *)(a1 + 21940) || *(_DWORD *)(a1 + 21924) != 2) && !a3 )
    v11 = 0;
  XC_WriteT1PStackValue(a1, v33, v11);
  XC_WriteT1PStackValue(a1, v34, v11);
  XC_WriteT1PStackValue(a1, v36, v11);
  XC_WriteT1PStackValue(a1, v37, v11);
  XC_WriteT1PStackValue(a1, v38, v11);
  XC_WriteT1PStackValue(a1, v39, v11);
  result = XC_WriteT1OpCode(a1, 3073, v11);
  *(_DWORD *)(a1 + 21932) = 0;
  return result;
}

```

## disassembly

```asm
0x180050e84  push    rbp
0x180050e86  push    rbx
0x180050e87  push    rsi
0x180050e88  push    rdi
0x180050e89  push    r12
0x180050e8b  push    r13
0x180050e8d  push    r14
0x180050e8f  push    r15
0x180050e91  lea     rbp, [rsp-1Fh]
0x180050e96  sub     rsp, 0E8h
0x180050e9d  mov     rax, cs:__security_cookie
0x180050ea4  xor     rax, rsp
0x180050ea7  mov     [rbp+57h+var_50], rax
0x180050eab  mov     rbx, rcx
0x180050eae  mov     [rsp+120h+var_FC], edx
0x180050eb2  xor     cl, cl
0x180050eb4  xor     r12b, r12b
0x180050eb7  xor     r14b, r14b
0x180050eba  mov     [rsp+120h+var_100], cl
0x180050ebe  xor     r15b, r15b
0x180050ec1  xor     r13d, r13d
0x180050ec4  xor     eax, eax
0x180050ec6  mov     esi, r8d
0x180050ec9  cmp     ax, [rbx+64D8h]
0x180050ed0  jnb     loc_180051175
0x180050ed6  lea     edi, [rax+1]
0x180050ed9  test    edx, edx
0x180050edb  jnz     short loc_180050F05
0x180050edd  test    r12b, r12b
0x180050ee0  jnz     short loc_180050EFC
0x180050ee2  mov     rax, [rbx+3750h]
0x180050ee9  mov     r12b, 80h
0x180050eec  mov     cl, [rax]
0x180050eee  inc     rax
0x180050ef1  mov     [rbx+3750h], rax
0x180050ef8  mov     [rsp+120h+var_100], cl
0x180050efc  test    cl, r12b
0x180050eff  jz      loc_180050FCB
0x180050f05  movzx   eax, r13w
0x180050f09  lea     rdx, [rax+rax*2]
0x180050f0d  cmp     dword ptr [rbx+rdx*8+58ECh], 0
0x180050f15  jz      short loc_180050F90
0x180050f17  cmp     dword ptr [rbx+65B4h], 0
0x180050f1e  jnz     short loc_180050F90
0x180050f20  cmp     [rbx+rdx*8+58E8h], di
0x180050f28  jnz     short loc_180050F5D
0x180050f2a  cmp     r14b, 3
0x180050f2e  jnb     loc_1800511D8
0x180050f34  movups  xmm0, xmmword ptr [rbx+rdx*8+58D8h]
0x180050f3c  movzx   eax, r14b
0x180050f40  add     r14b, dil
0x180050f43  movsd   xmm1, qword ptr [rbx+rdx*8+58E8h]
0x180050f4c  lea     rcx, [rax+rax*2]
0x180050f50  movups  [rsp+rcx*8+120h+var_F0], xmm0
0x180050f55  movsd   [rsp+rcx*8+120h+var_E0], xmm1
0x180050f5b  jmp     short loc_180050FC3
0x180050f5d  cmp     r15b, 3
0x180050f61  jnb     loc_1800511D8
0x180050f67  movups  xmm0, xmmword ptr [rbx+rdx*8+58D8h]
0x180050f6f  movzx   eax, r15b
0x180050f73  add     r15b, dil
0x180050f76  movsd   xmm1, qword ptr [rbx+rdx*8+58E8h]
0x180050f7f  lea     rcx, [rax+rax*2]
0x180050f83  movups  [rbp+rcx*8+57h+var_A0], xmm0
0x180050f88  movsd   [rbp+rcx*8+57h+var_90], xmm1
0x180050f8e  jmp     short loc_180050FC3
0x180050f90  cmp     [rbx+rdx*8+58E8h], di
0x180050f98  lea     rax, [rax+rax*2]
0x180050f9c  mov     r8, [rbx+rax*8+58E0h]
0x180050fa4  mov     r9d, esi
0x180050fa7  mov     rax, [rbx+rdx*8+58D8h]
0x180050faf  mov     rcx, rbx
0x180050fb2  mov     rdx, rax
0x180050fb5  jnz     short loc_180050FBE
0x180050fb7  call    HStem
0x180050fbc  jmp     short loc_180050FC3
0x180050fbe  call    VStem
0x180050fc3  mov     edx, [rsp+120h+var_FC]
0x180050fc7  mov     cl, [rsp+120h+var_100]
0x180050fcb  shr     r12b, 1
0x180050fce  add     r13w, di
0x180050fd2  cmp     r13w, [rbx+64D8h]
0x180050fda  jb      loc_180050ED9
0x180050fe0  cmp     r14b, 3
0x180050fe4  jnz     loc_18005108A
0x180050fea  test    [rbx+3A98h], dil
0x180050ff1  jnz     short loc_180051005
0x180050ff3  cmp     dword ptr [rbx+55B4h], 0
0x180050ffa  jnz     short loc_180051005
0x180050ffc  cmp     dword ptr [rbx+55A4h], 2
0x180051003  jz      short loc_18005100E
0x180051005  test    esi, esi
0x180051007  jnz     short loc_18005100E
0x180051009  xor     r14d, r14d
0x18005100c  jmp     short loc_180051011
0x18005100e  mov     r14d, edi
0x180051011  mov     rdx, qword ptr [rsp+120h+var_F0]
0x180051016  mov     r8d, r14d
0x180051019  mov     rcx, rbx
0x18005101c  call    XC_WriteT1PStackValue
0x180051021  mov     rdx, qword ptr [rsp+120h+var_F0+8]
0x180051026  mov     r8d, r14d
0x180051029  mov     rcx, rbx
0x18005102c  call    XC_WriteT1PStackValue
0x180051031  mov     rdx, [rsp+120h+var_D8]
0x180051036  mov     r8d, r14d
0x180051039  mov     rcx, rbx
0x18005103c  call    XC_WriteT1PStackValue
0x180051041  mov     rdx, [rbp+57h+var_D0]
0x180051045  mov     r8d, r14d
0x180051048  mov     rcx, rbx
0x18005104b  call    XC_WriteT1PStackValue
0x180051050  mov     rdx, [rbp+57h+var_C0]
0x180051054  mov     r8d, r14d
0x180051057  mov     rcx, rbx
0x18005105a  call    XC_WriteT1PStackValue
0x18005105f  mov     rdx, [rbp+57h+var_B8]
0x180051063  mov     r8d, r14d
0x180051066  mov     rcx, rbx
0x180051069  call    XC_WriteT1PStackValue
0x18005106e  mov     edx, 0C02h
0x180051073  mov     r8d, r14d
0x180051076  mov     rcx, rbx
0x180051079  call    XC_WriteT1OpCode
0x18005107e  mov     dword ptr [rbx+55ACh], 0
0x180051088  jmp     short loc_1800510D6
0x18005108a  cmp     r14b, dil
0x18005108d  jnz     short loc_18005109B
0x18005108f  mov     r8, qword ptr [rsp+120h+var_F0+8]
0x180051094  mov     rdx, qword ptr [rsp+120h+var_F0]
0x180051099  jmp     short loc_1800510BF
0x18005109b  cmp     r14b, 2
0x18005109f  jnz     short loc_1800510CC
0x1800510a1  mov     r8, qword ptr [rsp+120h+var_F0+8]
0x1800510a6  mov     r9d, esi
0x1800510a9  mov     rdx, qword ptr [rsp+120h+var_F0]
0x1800510ae  mov     rcx, rbx
0x1800510b1  call    HStem
0x1800510b6  mov     r8, [rbp+57h+var_D0]
0x1800510ba  mov     rdx, [rsp+120h+var_D8]
0x1800510bf  mov     r9d, esi
0x1800510c2  mov     rcx, rbx
0x1800510c5  call    HStem
0x1800510ca  jmp     short loc_1800510D6
0x1800510cc  cmp     r14b, 3
0x1800510d0  ja      loc_1800511D8
0x1800510d6  cmp     r15b, 3
0x1800510da  jnz     loc_180051195
0x1800510e0  test    [rbx+3A98h], dil
0x1800510e7  jnz     short loc_1800510FB
0x1800510e9  cmp     dword ptr [rbx+55B4h], 0
0x1800510f0  jnz     short loc_1800510FB
0x1800510f2  cmp     dword ptr [rbx+55A4h], 2
0x1800510f9  jz      short loc_180051101
0x1800510fb  test    esi, esi
0x1800510fd  jnz     short loc_180051101
0x1800510ff  xor     edi, edi
0x180051101  mov     rdx, qword ptr [rbp+57h+var_A0]
0x180051105  mov     r8d, edi
0x180051108  mov     rcx, rbx
0x18005110b  call    XC_WriteT1PStackValue
0x180051110  mov     rdx, qword ptr [rbp+57h+var_A0+8]
0x180051114  mov     r8d, edi
0x180051117  mov     rcx, rbx
0x18005111a  call    XC_WriteT1PStackValue
0x18005111f  mov     rdx, [rbp+57h+var_88]
0x180051123  mov     r8d, edi
0x180051126  mov     rcx, rbx
0x180051129  call    XC_WriteT1PStackValue
0x18005112e  mov     rdx, [rbp+57h+var_80]
0x180051132  mov     r8d, edi
0x180051135  mov     rcx, rbx
0x180051138  call    XC_WriteT1PStackValue
0x18005113d  mov     rdx, [rbp+57h+var_70]
0x180051141  mov     r8d, edi
0x180051144  mov     rcx, rbx
0x180051147  call    XC_WriteT1PStackValue
0x18005114c  mov     rdx, [rbp+57h+var_68]
0x180051150  mov     r8d, edi
0x180051153  mov     rcx, rbx
0x180051156  call    XC_WriteT1PStackValue
0x18005115b  mov     edx, 0C01h
0x180051160  mov     r8d, edi
0x180051163  mov     rcx, rbx
0x180051166  call    XC_WriteT1OpCode
0x18005116b  mov     dword ptr [rbx+55ACh], 0
0x180051175  mov     rcx, [rbp+57h+var_50]
0x180051179  xor     rcx, rsp; StackCookie
0x18005117c  call    __security_check_cookie
0x180051181  add     rsp, 0E8h
0x180051188  pop     r15
0x18005118a  pop     r14
0x18005118c  pop     r13
0x18005118e  pop     r12
0x180051190  pop     rdi
0x180051191  pop     rsi
0x180051192  pop     rbx
0x180051193  pop     rbp
0x180051194  retn
0x180051195  cmp     r15b, dil
0x180051198  jnz     short loc_1800511A4
0x18005119a  mov     r8, qword ptr [rbp+57h+var_A0+8]
0x18005119e  mov     rdx, qword ptr [rbp+57h+var_A0]
0x1800511a2  jmp     short loc_1800511C5
0x1800511a4  cmp     r15b, 2
0x1800511a8  jnz     short loc_1800511D2
0x1800511aa  mov     r8, qword ptr [rbp+57h+var_A0+8]
0x1800511ae  mov     r9d, esi
0x1800511b1  mov     rdx, qword ptr [rbp+57h+var_A0]
0x1800511b5  mov     rcx, rbx
0x1800511b8  call    VStem
0x1800511bd  mov     r8, [rbp+57h+var_80]
0x1800511c1  mov     rdx, [rbp+57h+var_88]
0x1800511c5  mov     r9d, esi
0x1800511c8  mov     rcx, rbx
0x1800511cb  call    VStem
0x1800511d0  jmp     short loc_180051175
0x1800511d2  cmp     r15b, 3
0x1800511d6  jbe     short loc_180051175
0x1800511d8  mov     edx, 0Eh
0x1800511dd  mov     rcx, rbx
0x1800511e0  call    XCF_FatalErrorHandler
```
