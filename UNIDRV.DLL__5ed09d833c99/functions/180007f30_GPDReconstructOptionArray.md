# GPDReconstructOptionArray

- ea: `0x180007f30`
- end: `0x180008202`
- name: `GPDReconstructOptionArray`
- size: `722`
- prototype: `__int64 __fastcall(__int64, _BYTE *, unsigned int, int, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003304`
- `0x180007320`
- `0x180008208`

## callees

- `0x180007150`
- `0x180007f30`
- `0x180049d00`
- `0x180076660`

## string_xrefs

- `0x180008122`: `ReconstructOptionArray: exceeded limit of combined options array.`

## pseudocode

```c
__int64 __fastcall GPDReconstructOptionArray(
        __int64 a1,
        _BYTE *a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        unsigned int a6)
{
  unsigned int v7; // ebp
  unsigned int v10; // r9d
  __int64 v11; // rax
  unsigned int v12; // r14d
  unsigned __int64 v13; // r8
  __int64 v14; // rcx
  unsigned int v15; // r11d
  unsigned int v16; // edx
  __int64 v17; // r10
  bool v19; // zf
  __int64 v20; // rdx
  __int64 v21; // rdx
  _BYTE Src[1024]; // [rsp+20h] [rbp-438h] BYREF

  v7 = a3;
  if ( a3 > 0x200 )
  {
    WriteDbgTraceErrorGpd(
      (__int64)"GPDReconstructOptionArray",
      "ReconstructOptionArray: caller-supplied array exceeds supported size.  Continuiing, but some options may be ignored.");
    v7 = 512;
  }
  if ( !a2 )
  {
    WriteDbgTraceErrorGpd(
      (__int64)"GPDReconstructOptionArray",
      "ReconstructOptionArray: caller passed in invalid pOptions.");
    return 0;
  }
  v10 = *(_DWORD *)(a1 + 20) + *(_DWORD *)(a1 + 24);
  if ( v10 > 0x200 )
  {
    WriteDbgTraceErrorGpd(
      (__int64)"GPDReconstructOptionArray",
      "ReconstructOptionArray: GPD contains too many features.  Aborting.");
    return 0;
  }
  if ( v10 > v7 )
  {
    WriteDbgTraceErrorGpd((__int64)"GPDReconstructOptionArray", "ReconstructOptionArray: Too many features in GPD.");
    return 0;
  }
  v11 = 0;
  v12 = *(_DWORD *)(a1 + 20) + *(_DWORD *)(a1 + 24);
  while ( (unsigned int)v11 < v10 )
  {
    v13 = (unsigned int)v11;
    if ( (_DWORD)v11 == a4 )
    {
      v15 = *(_DWORD *)(396LL * (unsigned int)v11 + *(_QWORD *)(a1 + 112) + 392);
      if ( v15 > a6 )
      {
        WriteDbgTraceErrorGpd(
          (__int64)"GPDReconstructOptionArray",
          "ReconstructOptionArray: Selected options has too few elements for current feature.",
          (unsigned int)v11);
        return 0;
      }
      v16 = 0;
      if ( !v15 )
      {
LABEL_16:
        WriteDbgTraceErrorGpd(
          (__int64)"GPDReconstructOptionArray",
          "ReconstructOptionArray: caller passed in invalid option selection.",
          (unsigned int)v11);
        return 0;
      }
      while ( 1 )
      {
        v17 = v16 + 1;
        if ( *(_DWORD *)(a5 + 4LL * v16) )
          break;
        ++v16;
        if ( (unsigned int)v17 >= v15 )
          goto LABEL_16;
      }
      Src[2 * v11] = v16;
      Src[2 * v11 + 1] = 0;
      v19 = (_DWORD)v17 == v15;
      if ( (unsigned int)v17 >= v15 )
      {
LABEL_24:
        if ( v19 )
          goto LABEL_11;
      }
      else
      {
        while ( !*(_DWORD *)(a5 + 4 * v17) )
        {
          v17 = (unsigned int)(v17 + 1);
          v19 = (_DWORD)v17 == v15;
          if ( (unsigned int)v17 >= v15 )
            goto LABEL_24;
        }
      }
      Src[2 * v11 + 1] = v12;
      while ( (unsigned int)v17 < v15 )
      {
        if ( v12 >= v7 )
        {
          WriteDbgTraceErrorGpd(
            (__int64)"GPDReconstructOptionArray",
            "ReconstructOptionArray: exceeded limit of option array.",
            (unsigned int)v11);
          return 0;
        }
        v20 = 2LL * v12;
        Src[v20] = v17;
        v17 = (unsigned int)(v17 + 1);
        Src[v20 + 1] = ++v12;
        if ( (unsigned int)v17 >= v15 )
          break;
        do
        {
          if ( *(_DWORD *)(a5 + 4 * v17) )
            break;
          v17 = (unsigned int)(v17 + 1);
        }
        while ( (unsigned int)v17 < v15 );
      }
    }
    else
    {
      Src[2 * v11] = a2[2 * v11];
      v14 = (unsigned __int8)a2[2 * v11 + 1];
      if ( !a2[2 * v11 + 1] )
      {
        Src[2 * v11 + 1] = v14;
        goto LABEL_11;
      }
      Src[2 * v11 + 1] = v12;
      while ( (_DWORD)v14 )
      {
        if ( v12 >= v7 )
        {
          WriteDbgTraceErrorGpd(
            (__int64)"GPDReconstructOptionArray",
            "ReconstructOptionArray: exceeded max supported options.",
            v13);
          return 0;
        }
        v13 = (unsigned __int64)&a2[2 * v14];
        v21 = 2LL * v12;
        Src[v21] = *(_BYTE *)v13;
        Src[v21 + 1] = ++v12;
        v14 = *(unsigned __int8 *)(v13 + 1);
      }
    }
    Src[2 * v12 - 1] = 0;
LABEL_11:
    v11 = (unsigned int)(v11 + 1);
  }
  if ( v12 > v7 )
  {
    WriteDbgTraceErrorGpd(
      (__int64)"GPDReconstructOptionArray",
      "ReconstructOptionArray: exceeded limit of combined options array.");
    return 0;
  }
  else
  {
    if ( v12 )
      memcpy_0(a2, Src, 2LL * v12);
    return 1;
  }
}

```

## disassembly

```asm
0x180007f30  push    rbx
0x180007f32  push    rbp
0x180007f33  push    rsi
0x180007f34  push    rdi
0x180007f35  sub     rsp, 438h
0x180007f3c  mov     rax, cs:__security_cookie
0x180007f43  xor     rax, rsp
0x180007f46  mov     [rsp+458h+var_38], rax
0x180007f4e  mov     ebx, r9d
0x180007f51  mov     ebp, r8d
0x180007f54  mov     rdi, rdx
0x180007f57  mov     rsi, rcx
0x180007f5a  cmp     r8d, 200h
0x180007f61  ja      loc_18000813C
0x180007f67  test    rdi, rdi
0x180007f6a  jz      loc_180008108
0x180007f70  mov     r9d, [rsi+18h]
0x180007f74  add     r9d, [rsi+14h]
0x180007f78  cmp     r9d, 200h
0x180007f7f  ja      loc_180008159
0x180007f85  cmp     r9d, ebp
0x180007f88  ja      loc_180008173
0x180007f8e  mov     [rsp+458h+arg_10], r14
0x180007f96  xor     eax, eax
0x180007f98  mov     [rsp+458h+var_28], r15
0x180007fa0  mov     r14d, r9d
0x180007fa3  mov     r15, [rsp+458h+arg_20]
0x180007fab  nop     dword ptr [rax+rax+00h]
0x180007fb0  cmp     eax, r9d
0x180007fb3  jnb     short loc_18000802D
0x180007fb5  mov     r8d, eax
0x180007fb8  cmp     eax, ebx
0x180007fba  jz      short loc_180007FD9
0x180007fbc  movzx   ecx, byte ptr [rdi+rax*2]
0x180007fc0  mov     [rsp+rax*2+458h+Src], cl
0x180007fc4  movzx   ecx, byte ptr [rdi+rax*2+1]
0x180007fc9  test    ecx, ecx
0x180007fcb  jnz     loc_18000818D
0x180007fd1  mov     [rsp+rax*2+458h+var_437], cl
0x180007fd5  inc     eax
0x180007fd7  jmp     short loc_180007FB0
0x180007fd9  mov     rcx, [rsi+70h]
0x180007fdd  imul    rdx, r8, 18Ch
0x180007fe4  mov     r11d, [rdx+rcx+188h]
0x180007fec  cmp     r11d, [rsp+458h+arg_28]
0x180007ff4  ja      loc_1800080EE
0x180007ffa  xor     edx, edx
0x180007ffc  test    r11d, r11d
0x180007fff  jz      short loc_180008016
0x180008001  mov     ecx, edx
0x180008003  lea     r10d, [rdx+1]
0x180008007  cmp     dword ptr [r15+rcx*4], 0
0x18000800c  jnz     short loc_180008080
0x18000800e  mov     edx, r10d
0x180008011  cmp     r10d, r11d
0x180008014  jb      short loc_180008001
0x180008016  lea     rdx, aReconstructopt_2; "ReconstructOptionArray: caller passed i"...
0x18000801d  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x180008024  call    WriteDbgTraceErrorGpd
0x180008029  xor     eax, eax
0x18000802b  jmp     short loc_180008053
0x18000802d  cmp     r14d, ebp
0x180008030  ja      loc_180008122
0x180008036  test    r14d, r14d
0x180008039  jz      short loc_18000804E
0x18000803b  mov     r8d, r14d
0x18000803e  lea     rdx, [rsp+458h+Src]; Src
0x180008043  add     r8, r8; Size
0x180008046  mov     rcx, rdi; void *
0x180008049  call    memcpy_0
0x18000804e  mov     eax, 1
0x180008053  mov     r14, [rsp+458h+arg_10]
0x18000805b  mov     r15, [rsp+458h+var_28]
0x180008063  mov     rcx, [rsp+458h+var_38]
0x18000806b  xor     rcx, rsp; StackCookie
0x18000806e  call    __security_check_cookie
0x180008073  add     rsp, 438h
0x18000807a  pop     rdi
0x18000807b  pop     rsi
0x18000807c  pop     rbp
0x18000807d  pop     rbx
0x18000807e  retn
0x180008080  mov     [rsp+rax*2+458h+Src], dl
0x180008084  mov     [rsp+rax*2+458h+var_437], 0
0x180008089  cmp     r10d, r11d
0x18000808c  jnb     short loc_18000809D
0x18000808e  cmp     dword ptr [r15+r10*4], 0
0x180008093  jnz     short loc_1800080A3
0x180008095  inc     r10d
0x180008098  cmp     r10d, r11d
0x18000809b  jb      short loc_18000808E
0x18000809d  jz      loc_180007FD5
0x1800080a3  mov     [rsp+rax*2+458h+var_437], r14b
0x1800080a8  cmp     r10d, r11d
0x1800080ab  jnb     loc_1800081C0
0x1800080b1  cmp     r14d, ebp
0x1800080b4  jnb     loc_1800081CE
0x1800080ba  mov     ecx, r14d
0x1800080bd  lea     rdx, [rcx+rcx]
0x1800080c1  lea     ecx, [r14+1]
0x1800080c5  mov     [rsp+rdx+458h+Src], r10b
0x1800080ca  inc     r10d
0x1800080cd  mov     [rsp+rdx+458h+var_437], cl
0x1800080d1  inc     r14d
0x1800080d4  cmp     r10d, r11d
0x1800080d7  jnb     loc_1800081C0
0x1800080dd  cmp     dword ptr [r15+r10*4], 0
0x1800080e2  jnz     short loc_1800080A8
0x1800080e4  inc     r10d
0x1800080e7  cmp     r10d, r11d
0x1800080ea  jb      short loc_1800080DD
0x1800080ec  jmp     short loc_1800080A8
0x1800080ee  lea     rdx, aReconstructopt_1; "ReconstructOptionArray: Selected option"...
0x1800080f5  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x1800080fc  call    WriteDbgTraceErrorGpd
0x180008101  xor     eax, eax
0x180008103  jmp     loc_180008053
0x180008108  lea     rdx, aReconstructopt; "ReconstructOptionArray: caller passed i"...
0x18000810f  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x180008116  call    WriteDbgTraceErrorGpd
0x18000811b  xor     eax, eax
0x18000811d  jmp     loc_180008063
0x180008122  lea     rdx, aReconstructopt_3; "ReconstructOptionArray: exceeded limit "...
0x180008129  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x180008130  call    WriteDbgTraceErrorGpd
0x180008135  xor     eax, eax
0x180008137  jmp     loc_180008053
0x18000813c  lea     rdx, aReconstructopt_5; "ReconstructOptionArray: caller-supplied"...
0x180008143  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x18000814a  call    WriteDbgTraceErrorGpd
0x18000814f  mov     ebp, 200h
0x180008154  jmp     loc_180007F67
0x180008159  lea     rdx, aReconstructopt_7; "ReconstructOptionArray: GPD contains to"...
0x180008160  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x180008167  call    WriteDbgTraceErrorGpd
0x18000816c  xor     eax, eax
0x18000816e  jmp     loc_180008063
0x180008173  lea     rdx, aReconstructopt_4; "ReconstructOptionArray: Too many featur"...
0x18000817a  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x180008181  call    WriteDbgTraceErrorGpd
0x180008186  xor     eax, eax
0x180008188  jmp     loc_180008063
0x18000818d  mov     [rsp+rax*2+458h+var_437], r14b
0x180008192  test    ecx, ecx
0x180008194  jz      short loc_1800081C0
0x180008196  cmp     r14d, ebp
0x180008199  jnb     short loc_1800081E8
0x18000819b  lea     r8, [rdi+rcx*2]
0x18000819f  mov     ecx, r14d
0x1800081a2  lea     rdx, [rcx+rcx]
0x1800081a6  movzx   ecx, byte ptr [r8]
0x1800081aa  mov     [rsp+rdx+458h+Src], cl
0x1800081ae  lea     ecx, [r14+1]
0x1800081b2  mov     [rsp+rdx+458h+var_437], cl
0x1800081b6  inc     r14d
0x1800081b9  movzx   ecx, byte ptr [r8+1]
0x1800081be  jmp     short loc_180008192
0x1800081c0  lea     ecx, [r14-1]
0x1800081c4  mov     [rsp+rcx*2+458h+var_437], 0
0x1800081c9  jmp     loc_180007FD5
0x1800081ce  lea     rdx, aReconstructopt_0; "ReconstructOptionArray: exceeded limit "...
0x1800081d5  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x1800081dc  call    WriteDbgTraceErrorGpd
0x1800081e1  xor     eax, eax
0x1800081e3  jmp     loc_180008053
0x1800081e8  lea     rdx, aReconstructopt_6; "ReconstructOptionArray: exceeded max su"...
0x1800081ef  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x1800081f6  call    WriteDbgTraceErrorGpd
0x1800081fb  xor     eax, eax
0x1800081fd  jmp     loc_180008053
```
