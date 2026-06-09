# WriteHints

- ea: `0x1800527fc`
- end: `0x180052b5f`
- name: `WriteHints`
- size: `867`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180051880`
- `0x180051af4`

## callees

- `0x180001f20`
- `0x18004f8e4`
- `0x180050960`
- `0x180051f98`
- `0x1800527fc`
- `0x180054864`
- `0x1800548bc`

## pseudocode

```c
void __fastcall WriteHints(__int64 a1, int a2, int a3)
{
  unsigned __int8 v4; // cl
  unsigned __int8 v5; // r12
  unsigned __int8 v6; // r14
  unsigned __int8 v7; // r15
  unsigned __int16 v8; // r13
  unsigned int v10; // edi
  unsigned __int8 *v11; // rax
  __int64 v12; // rax
  __int64 v13; // xmm1_8
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // xmm1_8
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rdx
  BOOL v20; // r14d
  _DWORD *v21; // r8
  _DWORD *v22; // rdx
  _DWORD *v23; // r8
  _DWORD *v24; // rdx
  unsigned __int8 v25; // [rsp+20h] [rbp-A9h]
  int v26; // [rsp+24h] [rbp-A5h]
  _DWORD *v27; // [rsp+30h] [rbp-99h]
  _DWORD *v28; // [rsp+38h] [rbp-91h]
  __int64 v29; // [rsp+40h] [rbp-89h]
  _DWORD *v30; // [rsp+48h] [rbp-81h]
  _DWORD *v31; // [rsp+50h] [rbp-79h]
  _DWORD *v32; // [rsp+60h] [rbp-69h]
  _DWORD *v33; // [rsp+68h] [rbp-61h]
  _DWORD *v34; // [rsp+80h] [rbp-49h]
  _DWORD *v35; // [rsp+88h] [rbp-41h]
  __int64 v36; // [rsp+90h] [rbp-39h]
  _DWORD *v37; // [rsp+98h] [rbp-31h]
  _DWORD *v38; // [rsp+A0h] [rbp-29h]
  _DWORD *v39; // [rsp+B0h] [rbp-19h]
  _DWORD *v40; // [rsp+B8h] [rbp-11h]

  v26 = a2;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v25 = 0;
  v7 = 0;
  v8 = 0;
  if ( !*(_WORD *)(a1 + 25816) )
    return;
  v10 = 1;
  do
  {
    if ( a2 )
      goto LABEL_50;
    if ( !v5 )
    {
      v11 = *(unsigned __int8 **)(a1 + 14160);
      v5 = 0x80;
      v4 = *v11;
      *(_QWORD *)(a1 + 14160) = v11 + 1;
      v25 = v4;
    }
    if ( (v5 & v4) != 0 )
    {
LABEL_50:
      if ( !*(_DWORD *)(a1 + 24LL * v8 + 22764) || *(_DWORD *)(a1 + 26036) )
      {
        v18 = *(_QWORD *)(a1 + 24LL * v8 + 22752);
        v19 = *(_QWORD *)(a1 + 24LL * v8 + 22744);
        if ( *(_WORD *)(a1 + 24LL * v8 + 22760) == 1 )
          HStem(a1, v19, v18, a3);
        else
          VStem(a1, v19, v18, a3);
      }
      else if ( *(_WORD *)(a1 + 24LL * v8 + 22760) == 1 )
      {
        if ( v6 >= 3u )
          goto LABEL_47;
        v12 = v6++;
        v13 = *(_QWORD *)(a1 + 24LL * v8 + 22760);
        v14 = 3 * v12;
        *(_OWORD *)&(&v27)[v14] = *(_OWORD *)(a1 + 24LL * v8 + 22744);
        *(&v29 + v14) = v13;
      }
      else
      {
        if ( v7 >= 3u )
          goto LABEL_47;
        v15 = v7++;
        v16 = *(_QWORD *)(a1 + 24LL * v8 + 22760);
        v17 = 3 * v15;
        *(_OWORD *)&(&v34)[v17] = *(_OWORD *)(a1 + 24LL * v8 + 22744);
        *(&v36 + v17) = v16;
      }
      a2 = v26;
      v4 = v25;
    }
    v5 >>= 1;
    ++v8;
  }
  while ( v8 < *(_WORD *)(a1 + 25816) );
  switch ( v6 )
  {
    case 3u:
      v20 = (*(_BYTE *)(a1 + 15000) & 1) == 0 && !*(_DWORD *)(a1 + 21940) && *(_DWORD *)(a1 + 21924) == 2 || a3;
      XC_WriteT1PStackValue(a1, v27, v20);
      XC_WriteT1PStackValue(a1, v28, v20);
      XC_WriteT1PStackValue(a1, v30, v20);
      XC_WriteT1PStackValue(a1, v31, v20);
      XC_WriteT1PStackValue(a1, v32, v20);
      XC_WriteT1PStackValue(a1, v33, v20);
      XC_WriteT1OpCode(a1, 3074, v20);
      *(_DWORD *)(a1 + 21932) = 0;
      goto LABEL_33;
    case 1u:
      v21 = v28;
      v22 = v27;
LABEL_31:
      HStem(a1, (__int64)v22, (__int64)v21, a3);
      goto LABEL_33;
    case 2u:
      HStem(a1, (__int64)v27, (__int64)v28, a3);
      v21 = v31;
      v22 = v30;
      goto LABEL_31;
  }
  if ( v6 > 3u )
    goto LABEL_47;
LABEL_33:
  if ( v7 != 3 )
  {
    if ( v7 == 1 )
    {
      v23 = v35;
      v24 = v34;
LABEL_45:
      VStem(a1, (__int64)v24, (__int64)v23, a3);
      return;
    }
    if ( v7 == 2 )
    {
      VStem(a1, (__int64)v34, (__int64)v35, a3);
      v23 = v38;
      v24 = v37;
      goto LABEL_45;
    }
    if ( v7 <= 3u )
      return;
LABEL_47:
    XCF_FatalErrorHandler((_JBTYPE *)a1, 14);
  }
  if ( ((*(_BYTE *)(a1 + 15000) & 1) != 0 || *(_DWORD *)(a1 + 21940) || *(_DWORD *)(a1 + 21924) != 2) && !a3 )
    v10 = 0;
  XC_WriteT1PStackValue(a1, v34, v10);
  XC_WriteT1PStackValue(a1, v35, v10);
  XC_WriteT1PStackValue(a1, v37, v10);
  XC_WriteT1PStackValue(a1, v38, v10);
  XC_WriteT1PStackValue(a1, v39, v10);
  XC_WriteT1PStackValue(a1, v40, v10);
  XC_WriteT1OpCode(a1, 3073, v10);
  *(_DWORD *)(a1 + 21932) = 0;
}

```

## disassembly

```asm
0x1800527fc  push    rbp
0x1800527fe  push    rbx
0x1800527ff  push    rsi
0x180052800  push    rdi
0x180052801  push    r12
0x180052803  push    r13
0x180052805  push    r14
0x180052807  push    r15
0x180052809  lea     rbp, [rsp-1Fh]
0x18005280e  sub     rsp, 0E8h
0x180052815  mov     rax, cs:__security_cookie
0x18005281c  xor     rax, rsp
0x18005281f  mov     [rbp+57h+var_50], rax
0x180052823  mov     rbx, rcx
0x180052826  mov     [rsp+120h+var_FC], edx
0x18005282a  xor     cl, cl
0x18005282c  xor     r12b, r12b
0x18005282f  xor     r14b, r14b
0x180052832  mov     [rsp+120h+var_100], cl
0x180052836  xor     r15b, r15b
0x180052839  xor     r13d, r13d
0x18005283c  xor     eax, eax
0x18005283e  mov     esi, r8d
0x180052841  cmp     ax, [rbx+64D8h]
0x180052848  jnb     loc_180052AED
0x18005284e  lea     edi, [rax+1]
0x180052851  test    edx, edx
0x180052853  jnz     short loc_18005287D
0x180052855  test    r12b, r12b
0x180052858  jnz     short loc_180052874
0x18005285a  mov     rax, [rbx+3750h]
0x180052861  mov     r12b, 80h
0x180052864  mov     cl, [rax]
0x180052866  inc     rax
0x180052869  mov     [rbx+3750h], rax
0x180052870  mov     [rsp+120h+var_100], cl
0x180052874  test    cl, r12b
0x180052877  jz      loc_180052943
0x18005287d  movzx   eax, r13w
0x180052881  lea     rdx, [rax+rax*2]
0x180052885  cmp     dword ptr [rbx+rdx*8+58ECh], 0
0x18005288d  jz      short loc_180052908
0x18005288f  cmp     dword ptr [rbx+65B4h], 0
0x180052896  jnz     short loc_180052908
0x180052898  cmp     [rbx+rdx*8+58E8h], di
0x1800528a0  jnz     short loc_1800528D5
0x1800528a2  cmp     r14b, 3
0x1800528a6  jnb     loc_180052B51
0x1800528ac  movups  xmm0, xmmword ptr [rbx+rdx*8+58D8h]
0x1800528b4  movzx   eax, r14b
0x1800528b8  add     r14b, dil
0x1800528bb  movsd   xmm1, qword ptr [rbx+rdx*8+58E8h]
0x1800528c4  lea     rcx, [rax+rax*2]
0x1800528c8  movups  [rsp+rcx*8+120h+var_F0], xmm0
0x1800528cd  movsd   [rsp+rcx*8+120h+var_E0], xmm1
0x1800528d3  jmp     short loc_18005293B
0x1800528d5  cmp     r15b, 3
0x1800528d9  jnb     loc_180052B51
0x1800528df  movups  xmm0, xmmword ptr [rbx+rdx*8+58D8h]
0x1800528e7  movzx   eax, r15b
0x1800528eb  add     r15b, dil
0x1800528ee  movsd   xmm1, qword ptr [rbx+rdx*8+58E8h]
0x1800528f7  lea     rcx, [rax+rax*2]
0x1800528fb  movups  [rbp+rcx*8+57h+var_A0], xmm0
0x180052900  movsd   [rbp+rcx*8+57h+var_90], xmm1
0x180052906  jmp     short loc_18005293B
0x180052908  cmp     [rbx+rdx*8+58E8h], di
0x180052910  lea     rax, [rax+rax*2]
0x180052914  mov     r8, [rbx+rax*8+58E0h]
0x18005291c  mov     r9d, esi
0x18005291f  mov     rax, [rbx+rdx*8+58D8h]
0x180052927  mov     rcx, rbx
0x18005292a  mov     rdx, rax
0x18005292d  jnz     short loc_180052936
0x18005292f  call    HStem
0x180052934  jmp     short loc_18005293B
0x180052936  call    VStem
0x18005293b  mov     edx, [rsp+120h+var_FC]
0x18005293f  mov     cl, [rsp+120h+var_100]
0x180052943  shr     r12b, 1
0x180052946  add     r13w, di
0x18005294a  cmp     r13w, [rbx+64D8h]
0x180052952  jb      loc_180052851
0x180052958  cmp     r14b, 3
0x18005295c  jnz     loc_180052A02
0x180052962  test    [rbx+3A98h], dil
0x180052969  jnz     short loc_18005297D
0x18005296b  cmp     dword ptr [rbx+55B4h], 0
0x180052972  jnz     short loc_18005297D
0x180052974  cmp     dword ptr [rbx+55A4h], 2
0x18005297b  jz      short loc_180052986
0x18005297d  test    esi, esi
0x18005297f  jnz     short loc_180052986
0x180052981  xor     r14d, r14d
0x180052984  jmp     short loc_180052989
0x180052986  mov     r14d, edi
0x180052989  mov     rdx, qword ptr [rsp+120h+var_F0]
0x18005298e  mov     r8d, r14d
0x180052991  mov     rcx, rbx
0x180052994  call    XC_WriteT1PStackValue
0x180052999  mov     rdx, qword ptr [rsp+120h+var_F0+8]
0x18005299e  mov     r8d, r14d
0x1800529a1  mov     rcx, rbx
0x1800529a4  call    XC_WriteT1PStackValue
0x1800529a9  mov     rdx, [rsp+120h+var_D8]
0x1800529ae  mov     r8d, r14d
0x1800529b1  mov     rcx, rbx
0x1800529b4  call    XC_WriteT1PStackValue
0x1800529b9  mov     rdx, [rbp+57h+var_D0]
0x1800529bd  mov     r8d, r14d
0x1800529c0  mov     rcx, rbx
0x1800529c3  call    XC_WriteT1PStackValue
0x1800529c8  mov     rdx, [rbp+57h+var_C0]
0x1800529cc  mov     r8d, r14d
0x1800529cf  mov     rcx, rbx
0x1800529d2  call    XC_WriteT1PStackValue
0x1800529d7  mov     rdx, [rbp+57h+var_B8]
0x1800529db  mov     r8d, r14d
0x1800529de  mov     rcx, rbx
0x1800529e1  call    XC_WriteT1PStackValue
0x1800529e6  mov     edx, 0C02h
0x1800529eb  mov     r8d, r14d
0x1800529ee  mov     rcx, rbx
0x1800529f1  call    XC_WriteT1OpCode
0x1800529f6  mov     dword ptr [rbx+55ACh], 0
0x180052a00  jmp     short loc_180052A4E
0x180052a02  cmp     r14b, dil
0x180052a05  jnz     short loc_180052A13
0x180052a07  mov     r8, qword ptr [rsp+120h+var_F0+8]
0x180052a0c  mov     rdx, qword ptr [rsp+120h+var_F0]
0x180052a11  jmp     short loc_180052A37
0x180052a13  cmp     r14b, 2
0x180052a17  jnz     short loc_180052A44
0x180052a19  mov     r8, qword ptr [rsp+120h+var_F0+8]
0x180052a1e  mov     r9d, esi
0x180052a21  mov     rdx, qword ptr [rsp+120h+var_F0]
0x180052a26  mov     rcx, rbx
0x180052a29  call    HStem
0x180052a2e  mov     r8, [rbp+57h+var_D0]
0x180052a32  mov     rdx, [rsp+120h+var_D8]
0x180052a37  mov     r9d, esi
0x180052a3a  mov     rcx, rbx
0x180052a3d  call    HStem
0x180052a42  jmp     short loc_180052A4E
0x180052a44  cmp     r14b, 3
0x180052a48  ja      loc_180052B51
0x180052a4e  cmp     r15b, 3
0x180052a52  jnz     loc_180052B0E
0x180052a58  test    [rbx+3A98h], dil
0x180052a5f  jnz     short loc_180052A73
0x180052a61  cmp     dword ptr [rbx+55B4h], 0
0x180052a68  jnz     short loc_180052A73
0x180052a6a  cmp     dword ptr [rbx+55A4h], 2
0x180052a71  jz      short loc_180052A79
0x180052a73  test    esi, esi
0x180052a75  jnz     short loc_180052A79
0x180052a77  xor     edi, edi
0x180052a79  mov     rdx, qword ptr [rbp+57h+var_A0]
0x180052a7d  mov     r8d, edi
0x180052a80  mov     rcx, rbx
0x180052a83  call    XC_WriteT1PStackValue
0x180052a88  mov     rdx, qword ptr [rbp+57h+var_A0+8]
0x180052a8c  mov     r8d, edi
0x180052a8f  mov     rcx, rbx
0x180052a92  call    XC_WriteT1PStackValue
0x180052a97  mov     rdx, [rbp+57h+var_88]
0x180052a9b  mov     r8d, edi
0x180052a9e  mov     rcx, rbx
0x180052aa1  call    XC_WriteT1PStackValue
0x180052aa6  mov     rdx, [rbp+57h+var_80]
0x180052aaa  mov     r8d, edi
0x180052aad  mov     rcx, rbx
0x180052ab0  call    XC_WriteT1PStackValue
0x180052ab5  mov     rdx, [rbp+57h+var_70]
0x180052ab9  mov     r8d, edi
0x180052abc  mov     rcx, rbx
0x180052abf  call    XC_WriteT1PStackValue
0x180052ac4  mov     rdx, [rbp+57h+var_68]
0x180052ac8  mov     r8d, edi
0x180052acb  mov     rcx, rbx
0x180052ace  call    XC_WriteT1PStackValue
0x180052ad3  mov     edx, 0C01h
0x180052ad8  mov     r8d, edi
0x180052adb  mov     rcx, rbx
0x180052ade  call    XC_WriteT1OpCode
0x180052ae3  mov     dword ptr [rbx+55ACh], 0
0x180052aed  mov     rcx, [rbp+57h+var_50]
0x180052af1  xor     rcx, rsp; StackCookie
0x180052af4  call    __security_check_cookie
0x180052af9  add     rsp, 0E8h
0x180052b00  pop     r15
0x180052b02  pop     r14
0x180052b04  pop     r13
0x180052b06  pop     r12
0x180052b08  pop     rdi
0x180052b09  pop     rsi
0x180052b0a  pop     rbx
0x180052b0b  pop     rbp
0x180052b0c  retn
0x180052b0e  cmp     r15b, dil
0x180052b11  jnz     short loc_180052B1D
0x180052b13  mov     r8, qword ptr [rbp+57h+var_A0+8]
0x180052b17  mov     rdx, qword ptr [rbp+57h+var_A0]
0x180052b1b  jmp     short loc_180052B3E
0x180052b1d  cmp     r15b, 2
0x180052b21  jnz     short loc_180052B4B
0x180052b23  mov     r8, qword ptr [rbp+57h+var_A0+8]
0x180052b27  mov     r9d, esi
0x180052b2a  mov     rdx, qword ptr [rbp+57h+var_A0]
0x180052b2e  mov     rcx, rbx
0x180052b31  call    VStem
0x180052b36  mov     r8, [rbp+57h+var_80]
0x180052b3a  mov     rdx, [rbp+57h+var_88]
0x180052b3e  mov     r9d, esi
0x180052b41  mov     rcx, rbx
0x180052b44  call    VStem
0x180052b49  jmp     short loc_180052AED
0x180052b4b  cmp     r15b, 3
0x180052b4f  jbe     short loc_180052AED
0x180052b51  mov     edx, 0Eh
0x180052b56  mov     rcx, rbx
0x180052b59  call    XCF_FatalErrorHandler
```
