# GPDCombineOptionArray

- ea: `0x180005020`
- end: `0x180005415`
- name: `GPDCombineOptionArray`
- size: `1013`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000414c`
- `0x180004420`
- `0x180025a1c`
- `0x180034208`
- `0x18003fb40`

## callees

- `0x1800046c0`
- `0x180005020`
- `0x1800068a0`
- `0x180007150`

## import_xrefs

- `KERNEL32!GetSystemDefaultLCID` at `0x180005239`
- `KERNEL32!GetSystemDefaultLCID` at `0x180005239`

## string_xrefs

- `0x180005202`: `GPDCombineOptionArray`
- `0x1800052f8`: `GPDCombineOptionArray`
- `0x1800052f1`: `CombineOptionArray: EextractValueFromTree failed.`

## pseudocode

```c
__int64 __fastcall GPDCombineOptionArray(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5)
{
  unsigned int v7; // ecx
  unsigned int v10; // edx
  unsigned int v11; // ecx
  __int64 v12; // r13
  unsigned int v13; // r10d
  unsigned int v14; // ebx
  __int64 v15; // rax
  int *v16; // rsi
  __int64 v17; // rdi
  unsigned int v18; // edx
  __int64 v19; // rax
  _BYTE *v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rbx
  int v23; // ecx
  __int64 v24; // rcx
  LCID SystemDefaultLCID; // eax
  unsigned __int64 v27; // rdx
  __int64 v28; // r9
  bool v29; // zf
  unsigned int j; // r8d
  unsigned int v31; // r10d
  unsigned int i; // edx
  __int64 v33; // r9
  _BYTE *v34; // rdx
  int v35; // [rsp+50h] [rbp-48h] BYREF
  int v36; // [rsp+54h] [rbp-44h] BYREF
  int v37; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v38; // [rsp+B0h] [rbp+18h] BYREF
  unsigned int v39; // [rsp+B8h] [rbp+20h] BYREF

  v7 = *(_DWORD *)(a1 + 20);
  if ( a4 )
  {
    v31 = v7;
    for ( i = 0; i < v31; ++i )
    {
      if ( *(_BYTE *)(a4 + 2LL * i + 1) )
      {
        do
          ++v7;
        while ( *(_BYTE *)(a4 + 2LL * *(unsigned __int8 *)(a4 + 2LL * i + 1) + 1) );
      }
    }
  }
  v10 = *(_DWORD *)(a1 + 24);
  v11 = v10 + v7;
  v12 = a5;
  if ( a5 )
  {
    for ( j = 0; j < v10; ++j )
    {
      if ( *(_BYTE *)(a5 + 2LL * j + 1) )
      {
        do
          ++v11;
        while ( *(_BYTE *)(a5 + 2LL * *(unsigned __int8 *)(a5 + 2LL * j + 1) + 1) );
      }
    }
  }
  if ( !a3 )
    return 0;
  if ( v11 > a3 )
    return 0;
  v13 = *(_DWORD *)(a1 + 120);
  v38 = v13;
  if ( v13 > a3 )
    return 0;
  v36 = 0;
  v14 = 0;
  v37 = 0;
  while ( 1 )
  {
    if ( v14 >= *(_DWORD *)(a1 + 120) || v14 >= a3 )
    {
      v38 = -1;
      if ( !(unsigned int)BgetLocFeaIndex(a1, &v38) )
        return 0;
      v22 = v38;
      v23 = -1;
      if ( v38 != -1 && v38 < *(_DWORD *)(a1 + 120) )
      {
        SystemDefaultLCID = GetSystemDefaultLCID();
        if ( SystemDefaultLCID )
        {
          v27 = *(unsigned int *)(396 * v22 + *(_QWORD *)(a1 + 112) + 360);
          if ( (_DWORD)v27 != 0x7FFFFFFF )
          {
            if ( (v27 & 0x80000000) != 0LL )
            {
LABEL_34:
              WriteDbgTraceErrorGpd(
                (__int64)"BgetLocFeaOptIndex",
                "OptionID for Feature Locale cannot be determined",
                SystemDefaultLCID);
            }
            else
            {
              v28 = *(_QWORD *)(a1 + 144);
              if ( *(_DWORD *)(v28 + 20 * v27) != -1 )
                goto LABEL_30;
              if ( *(_DWORD *)(v28 + 20 * v27 + 8) != -1 )
              {
                _mm_lfence();
                v28 = *(_QWORD *)(a1 + 144);
                LODWORD(v27) = *(_DWORD *)(v28 + 20 * v27 + 8);
LABEL_30:
                while ( (_DWORD)v27 != -1 )
                {
                  v29 = *(_DWORD *)(v28 + 20LL * (unsigned int)v27 + 16) == 1;
                  v27 = v28 + 20LL * (unsigned int)v27;
                  if ( !v29 )
                    goto LABEL_34;
                  if ( *(_DWORD *)(*(unsigned int *)(v27 + 12) + *(_QWORD *)(a1 + 128)) == SystemDefaultLCID )
                  {
                    v23 = *(_DWORD *)(v27 + 4);
                    goto LABEL_20;
                  }
                  LODWORD(v27) = *(_DWORD *)(v27 + 8);
                }
              }
            }
          }
        }
        else
        {
          WriteDbgTraceErrorGpd((__int64)"BgetLocFeaOptIndex", "Cannot determine System locale\n", 0);
        }
        v23 = -1;
      }
LABEL_20:
      if ( (_DWORD)v22 == -1 )
        return 1;
      if ( v23 == -1 )
      {
        v24 = *(unsigned int *)(396 * v22 + *(_QWORD *)(a1 + 112) + 8);
        if ( (int)v24 >= 0 )
          goto LABEL_23;
        LODWORD(v24) = v24 & 0x7FFFFFFF;
        v23 = *(_DWORD *)(v24 + *(_QWORD *)(a1 + 128));
      }
      if ( (unsigned int)v22 < a3 )
      {
        *(_BYTE *)(a2 + 2 * v22) = v23;
        *(_BYTE *)(a2 + 2 * v22 + 1) = 0;
        return 1;
      }
LABEL_23:
      WriteDbgTraceErrorGpd(
        (__int64)"GPDCombineOptionArray",
        "Error in processing Default Option for Feature Locale. Continuing....");
      return 1;
    }
    v15 = *(_QWORD *)(a1 + 96);
    v16 = &v37;
    LODWORD(a5) = 0;
    v17 = v12;
    v35 = 0;
    if ( v14 < *(_DWORD *)(v15 + 136) )
      break;
LABEL_13:
    v20 = (_BYTE *)(a2 + 2LL * v14);
    if ( v17 )
    {
      v21 = (unsigned int)*v16;
      *v20 = *(_BYTE *)(v17 + 2 * v21);
      if ( *(_BYTE *)(v17 + 2 * v21 + 1) )
      {
        v20[1] = v13;
        LODWORD(v33) = v21;
        if ( v13 >= a3 )
          return 0;
        while ( 1 )
        {
          v33 = *(unsigned __int8 *)(v17 + 2LL * (unsigned int)v33 + 1);
          if ( !(_DWORD)v33 )
            break;
          if ( v13 >= a3 )
            return 0;
          v34 = (_BYTE *)(a2 + 2LL * v13);
          *v34 = *(_BYTE *)(v17 + 2 * v33);
          v34[1] = ++v13;
          v38 = v13;
        }
        *(_BYTE *)(a2 + 2LL * (v13 - 1) + 1) = 0;
      }
      else
      {
        v20[1] = 0;
      }
      ++v14;
      *v16 = v21 + 1;
    }
    else
    {
      *(_WORD *)v20 = 255;
      ++v14;
    }
  }
  v18 = *(_DWORD *)(a1 + 208);
  v19 = *(_QWORD *)(a1 + 112);
  v39 = 0;
  if ( (unsigned int)EextractValueFromTree(
                       (_QWORD *)a1,
                       v18,
                       (int *)&a5,
                       4,
                       &v35,
                       *(_DWORD *)(396LL * v14 + v19),
                       a2,
                       0,
                       &v39) == 1 )
  {
    v13 = v38;
    if ( (_DWORD)a5 != 2 )
    {
      v17 = a4;
      v16 = &v36;
    }
    goto LABEL_13;
  }
  WriteDbgTraceErrorGpd((__int64)"GPDCombineOptionArray", "CombineOptionArray: EextractValueFromTree failed.");
  return 0;
}

```

## disassembly

```asm
0x180005020  push    rbp
0x180005022  push    r12
0x180005024  push    r13
0x180005026  push    r14
0x180005028  push    r15
0x18000502a  sub     rsp, 70h
0x18000502e  mov     r12, r9
0x180005031  mov     rbp, rcx
0x180005034  mov     ecx, [rcx+14h]
0x180005037  xor     r9d, r9d
0x18000503a  mov     r14d, r8d
0x18000503d  mov     r15, rdx
0x180005040  test    r12, r12
0x180005043  jnz     loc_18000535F
0x180005049  mov     edx, [rbp+18h]
0x18000504c  add     ecx, edx
0x18000504e  mov     r13, [rsp+98h+arg_20]
0x180005056  test    r13, r13
0x180005059  jnz     loc_180005336
0x18000505f  mov     [rsp+98h+arg_8], rbx
0x180005067  mov     [rsp+98h+var_30], rsi
0x18000506c  mov     [rsp+98h+var_38], rdi
0x180005071  test    r14d, r14d
0x180005074  jz      loc_180005304
0x18000507a  cmp     ecx, r14d
0x18000507d  ja      loc_180005304
0x180005083  mov     r10d, [rbp+78h]
0x180005087  mov     [rsp+98h+arg_10], r10d
0x18000508f  cmp     r10d, r14d
0x180005092  ja      loc_180005304
0x180005098  mov     [rsp+98h+var_44], r9d
0x18000509d  mov     ebx, r9d
0x1800050a0  mov     [rsp+98h+arg_0], r9d
0x1800050a8  nop     dword ptr [rax+rax+00000000h]
0x1800050b0  cmp     ebx, [rbp+78h]
0x1800050b3  jnb     loc_1800051A3
0x1800050b9  cmp     ebx, r14d
0x1800050bc  jnb     loc_1800051A3
0x1800050c2  mov     rax, [rbp+60h]
0x1800050c6  lea     rsi, [rsp+98h+arg_0]
0x1800050ce  mov     dword ptr [rsp+98h+arg_20], r9d
0x1800050d6  mov     rdi, r13
0x1800050d9  mov     [rsp+98h+var_48], r9d
0x1800050de  cmp     ebx, [rax+88h]
0x1800050e4  jnb     short loc_180005165
0x1800050e6  lea     rdx, [rsp+98h+arg_18]
0x1800050ee  mov     eax, ebx
0x1800050f0  mov     [rsp+98h+var_58], rdx
0x1800050f5  lea     r8, [rsp+98h+arg_20]
0x1800050fd  mov     edx, [rbp+0D0h]
0x180005103  imul    rcx, rax, 18Ch
0x18000510a  mov     rax, [rbp+70h]
0x18000510e  mov     [rsp+98h+var_60], r9d
0x180005113  mov     [rsp+98h+var_68], r15
0x180005118  mov     [rsp+98h+arg_18], r9d
0x180005120  mov     r9d, 4
0x180005126  mov     eax, [rcx+rax]
0x180005129  mov     rcx, rbp
0x18000512c  mov     [rsp+98h+var_70], eax
0x180005130  lea     rax, [rsp+98h+var_48]
0x180005135  mov     [rsp+98h+var_78], rax
0x18000513a  call    EextractValueFromTree
0x18000513f  cmp     eax, 1
0x180005142  jnz     loc_1800052F1
0x180005148  mov     r10d, [rsp+98h+arg_10]
0x180005150  xor     r9d, r9d
0x180005153  cmp     dword ptr [rsp+98h+arg_20], 2
0x18000515b  jz      short loc_180005165
0x18000515d  mov     rdi, r12
0x180005160  lea     rsi, [rsp+98h+var_44]
0x180005165  mov     eax, ebx
0x180005167  lea     rcx, [r15+rax*2]
0x18000516b  test    rdi, rdi
0x18000516e  jz      short loc_180005197
0x180005170  mov     r8d, [rsi]
0x180005173  movzx   eax, byte ptr [rdi+r8*2]
0x180005178  mov     [rcx], al
0x18000517a  cmp     byte ptr [rdi+r8*2+1], 0
0x180005180  jnz     loc_1800053A7
0x180005186  mov     byte ptr [rcx+1], 0
0x18000518a  lea     eax, [r8+1]
0x18000518e  inc     ebx
0x180005190  mov     [rsi], eax
0x180005192  jmp     loc_1800050B0
0x180005197  mov     word ptr [rcx], 0FFh
0x18000519c  inc     ebx
0x18000519e  jmp     loc_1800050B0
0x1800051a3  lea     rdx, [rsp+98h+arg_10]
0x1800051ab  mov     [rsp+98h+arg_10], 0FFFFFFFFh
0x1800051b6  mov     rcx, rbp
0x1800051b9  call    BgetLocFeaIndex
0x1800051be  test    eax, eax
0x1800051c0  jz      loc_180005304
0x1800051c6  mov     ebx, [rsp+98h+arg_10]
0x1800051cd  mov     ecx, 0FFFFFFFFh
0x1800051d2  cmp     ebx, ecx
0x1800051d4  jnz     short loc_180005234
0x1800051d6  cmp     ebx, 0FFFFFFFFh
0x1800051d9  jz      short loc_18000520E
0x1800051db  cmp     ecx, 0FFFFFFFFh
0x1800051de  jnz     loc_1800052D9
0x1800051e4  mov     rax, [rbp+70h]
0x1800051e8  imul    rcx, rbx, 18Ch
0x1800051ef  mov     ecx, [rcx+rax+8]
0x1800051f3  test    ecx, ecx
0x1800051f5  js      loc_180005402
0x1800051fb  lea     rdx, aErrorInProcess; "Error in processing Default Option for "...
0x180005202  lea     rcx, aGpdcombineopti; "GPDCombineOptionArray"
0x180005209  call    WriteDbgTraceErrorGpd
0x18000520e  mov     eax, 1
0x180005213  mov     rdi, [rsp+98h+var_38]
0x180005218  mov     rsi, [rsp+98h+var_30]
0x18000521d  mov     rbx, [rsp+98h+arg_8]
0x180005225  add     rsp, 70h
0x180005229  pop     r15
0x18000522b  pop     r14
0x18000522d  pop     r13
0x18000522f  pop     r12
0x180005231  pop     rbp
0x180005232  retn
0x180005234  cmp     ebx, [rbp+78h]
0x180005237  jnb     short loc_1800051D6
0x180005239  call    cs:__imp_GetSystemDefaultLCID
0x180005240  nop     dword ptr [rax+rax+00h]
0x180005245  mov     r8d, eax
0x180005248  test    eax, eax
0x18000524a  jz      loc_18000532D
0x180005250  mov     rax, [rbp+70h]
0x180005254  imul    rcx, rbx, 18Ch
0x18000525b  mov     edx, [rcx+rax+168h]
0x180005262  cmp     edx, 7FFFFFFFh
0x180005268  jz      short loc_1800052CF
0x18000526a  test    edx, edx
0x18000526c  js      short loc_1800052BC
0x18000526e  mov     r9, [rbp+90h]
0x180005275  lea     rcx, [rdx+rdx*4]
0x180005279  lea     rcx, ds:0[rcx*4]
0x180005281  cmp     dword ptr [r9+rcx], 0FFFFFFFFh
0x180005286  lea     rax, [r9+rcx]
0x18000528a  jz      loc_180005313
0x180005290  cmp     edx, 0FFFFFFFFh
0x180005293  jz      short loc_1800052CF
0x180005295  mov     eax, edx
0x180005297  lea     rcx, [rax+rax*4]
0x18000529b  cmp     dword ptr [r9+rcx*4+10h], 1
0x1800052a1  lea     rdx, [r9+rcx*4]
0x1800052a5  jnz     short loc_1800052BC
0x1800052a7  mov     ecx, [rdx+0Ch]
0x1800052aa  mov     rax, [rbp+80h]
0x1800052b1  cmp     [rcx+rax], r8d
0x1800052b5  jz      short loc_18000530B
0x1800052b7  mov     edx, [rdx+8]
0x1800052ba  jmp     short loc_180005290
0x1800052bc  lea     rdx, aOptionidForFea; "OptionID for Feature Locale cannot be d"...
0x1800052c3  lea     rcx, aBgetlocfeaopti; "BgetLocFeaOptIndex"
0x1800052ca  call    WriteDbgTraceErrorGpd
0x1800052cf  mov     ecx, 0FFFFFFFFh
0x1800052d4  jmp     loc_1800051D6
0x1800052d9  cmp     ebx, r14d
0x1800052dc  jnb     loc_1800051FB
0x1800052e2  mov     [r15+rbx*2], cl
0x1800052e6  mov     byte ptr [r15+rbx*2+1], 0
0x1800052ec  jmp     loc_18000520E
0x1800052f1  lea     rdx, aCombineoptiona; "CombineOptionArray: EextractValueFromTr"...
0x1800052f8  lea     rcx, aGpdcombineopti; "GPDCombineOptionArray"
0x1800052ff  call    WriteDbgTraceErrorGpd
0x180005304  xor     eax, eax
0x180005306  jmp     loc_180005213
0x18000530b  mov     ecx, [rdx+4]
0x18000530e  jmp     loc_1800051D6
0x180005313  cmp     dword ptr [rax+8], 0FFFFFFFFh
0x180005317  jz      short loc_1800052CF
0x180005319  lfence
0x18000531c  mov     r9, [rbp+90h]
0x180005323  mov     edx, [r9+rcx+8]
0x180005328  jmp     loc_180005290
0x18000532d  lea     rdx, aCannotDetermin; "Cannot determine System locale\n"
0x180005334  jmp     short loc_1800052C3
0x180005336  mov     r8d, r9d
0x180005339  test    edx, edx
0x18000533b  jz      loc_18000505F
0x180005341  mov     eax, r8d
0x180005344  movzx   r9d, byte ptr [r13+rax*2+1]
0x18000534a  test    r9d, r9d
0x18000534d  jnz     short loc_180005398
0x18000534f  inc     r8d
0x180005352  cmp     r8d, edx
0x180005355  jb      short loc_180005341
0x180005357  xor     r9d, r9d
0x18000535a  jmp     loc_18000505F
0x18000535f  mov     r10d, ecx
0x180005362  mov     edx, r9d
0x180005365  test    ecx, ecx
0x180005367  jz      loc_180005049
0x18000536d  nop     dword ptr [rax]
0x180005370  mov     eax, edx
0x180005372  movzx   r8d, byte ptr [r12+rax*2+1]
0x180005378  test    r8d, r8d
0x18000537b  jnz     short loc_180005389
0x18000537d  inc     edx
0x18000537f  cmp     edx, r10d
0x180005382  jb      short loc_180005370
0x180005384  jmp     loc_180005049
0x180005389  movzx   r8d, byte ptr [r12+r8*2+1]
0x18000538f  inc     ecx
0x180005391  test    r8d, r8d
0x180005394  jnz     short loc_180005389
0x180005396  jmp     short loc_18000537D
0x180005398  movzx   r9d, byte ptr [r13+r9*2+1]
0x18000539e  inc     ecx
0x1800053a0  test    r9d, r9d
0x1800053a3  jnz     short loc_180005398
0x1800053a5  jmp     short loc_18000534F
0x1800053a7  mov     [rcx+1], r10b
0x1800053ab  mov     r9d, r8d
0x1800053ae  cmp     r10d, r14d
0x1800053b1  jnb     loc_180005304
0x1800053b7  mov     eax, r9d
0x1800053ba  movzx   r9d, byte ptr [rdi+rax*2+1]
0x1800053c0  test    r9d, r9d
0x1800053c3  jz      short loc_1800053F0
0x1800053c5  cmp     r10d, r14d
0x1800053c8  jnb     loc_180005304
0x1800053ce  movzx   ecx, byte ptr [rdi+r9*2]
0x1800053d3  mov     eax, r10d
0x1800053d6  lea     rdx, [r15+rax*2]
0x1800053da  lea     eax, [r10+1]
0x1800053de  mov     [rdx], cl
0x1800053e0  inc     r10d
0x1800053e3  mov     [rdx+1], al
0x1800053e6  mov     [rsp+98h+arg_10], r10d
0x1800053ee  jmp     short loc_1800053B7
0x1800053f0  lea     eax, [r10-1]
0x1800053f4  xor     r9d, r9d
0x1800053f7  mov     byte ptr [r15+rax*2+1], 0
0x1800053fd  jmp     loc_18000518A
0x180005402  mov     rax, [rbp+80h]
0x180005409  btr     ecx, 1Fh
0x18000540d  mov     ecx, [rcx+rax]
0x180005410  jmp     loc_1800052D9
```
