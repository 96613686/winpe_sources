# GPDReconstructOptionArray

- ea: `0x180007ff0`
- end: `0x1800082c1`
- name: `GPDReconstructOptionArray`
- size: `721`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003340`
- `0x1800073f0`
- `0x1800082c8`

## callees

- `0x180007220`
- `0x180007ff0`
- `0x1800487e0`
- `0x180074580`

## string_xrefs

- `0x1800081e1`: `ReconstructOptionArray: exceeded limit of combined options array.`

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
      "GPDReconstructOptionArray",
      "ReconstructOptionArray: caller-supplied array exceeds supported size.  Continuiing, but some options may be ignored.");
    v7 = 512;
  }
  if ( !a2 )
  {
    WriteDbgTraceErrorGpd("GPDReconstructOptionArray", "ReconstructOptionArray: caller passed in invalid pOptions.");
    return 0;
  }
  v10 = *(_DWORD *)(a1 + 20) + *(_DWORD *)(a1 + 24);
  if ( v10 > 0x200 )
  {
    WriteDbgTraceErrorGpd(
      "GPDReconstructOptionArray",
      "ReconstructOptionArray: GPD contains too many features.  Aborting.");
    return 0;
  }
  if ( v10 > v7 )
  {
    WriteDbgTraceErrorGpd("GPDReconstructOptionArray", "ReconstructOptionArray: Too many features in GPD.");
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
          "GPDReconstructOptionArray",
          "ReconstructOptionArray: Selected options has too few elements for current feature.",
          (unsigned int)v11);
        return 0;
      }
      v16 = 0;
      if ( !v15 )
      {
LABEL_16:
        WriteDbgTraceErrorGpd(
          "GPDReconstructOptionArray",
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
            "GPDReconstructOptionArray",
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
            "GPDReconstructOptionArray",
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
      "GPDReconstructOptionArray",
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
0x180007ff0  push    rbx
0x180007ff2  push    rbp
0x180007ff3  push    rsi
0x180007ff4  push    rdi
0x180007ff5  sub     rsp, 438h
0x180007ffc  mov     rax, cs:__security_cookie
0x180008003  xor     rax, rsp
0x180008006  mov     [rsp+458h+var_38], rax
0x18000800e  mov     ebx, r9d
0x180008011  mov     ebp, r8d
0x180008014  mov     rdi, rdx
0x180008017  mov     rsi, rcx
0x18000801a  cmp     r8d, 200h
0x180008021  ja      loc_1800081FB
0x180008027  test    rdi, rdi
0x18000802a  jz      loc_1800081C7
0x180008030  mov     r9d, [rsi+18h]
0x180008034  add     r9d, [rsi+14h]
0x180008038  cmp     r9d, 200h
0x18000803f  ja      loc_180008218
0x180008045  cmp     r9d, ebp
0x180008048  ja      loc_180008232
0x18000804e  mov     [rsp+458h+arg_10], r14
0x180008056  xor     eax, eax
0x180008058  mov     [rsp+458h+var_28], r15
0x180008060  mov     r14d, r9d
0x180008063  mov     r15, [rsp+458h+arg_20]
0x18000806b  nop     dword ptr [rax+rax+00h]
0x180008070  cmp     eax, r9d
0x180008073  jnb     short loc_1800080ED
0x180008075  mov     r8d, eax
0x180008078  cmp     eax, ebx
0x18000807a  jz      short loc_180008099
0x18000807c  movzx   ecx, byte ptr [rdi+rax*2]
0x180008080  mov     [rsp+rax*2+458h+Src], cl
0x180008084  movzx   ecx, byte ptr [rdi+rax*2+1]
0x180008089  test    ecx, ecx
0x18000808b  jnz     loc_18000824C
0x180008091  mov     [rsp+rax*2+458h+var_437], cl
0x180008095  inc     eax
0x180008097  jmp     short loc_180008070
0x180008099  mov     rcx, [rsi+70h]
0x18000809d  imul    rdx, r8, 18Ch
0x1800080a4  mov     r11d, [rdx+rcx+188h]
0x1800080ac  cmp     r11d, [rsp+458h+arg_28]
0x1800080b4  ja      loc_1800081AD
0x1800080ba  xor     edx, edx
0x1800080bc  test    r11d, r11d
0x1800080bf  jz      short loc_1800080D6
0x1800080c1  mov     ecx, edx
0x1800080c3  lea     r10d, [rdx+1]
0x1800080c7  cmp     dword ptr [r15+rcx*4], 0
0x1800080cc  jnz     short loc_18000813F
0x1800080ce  mov     edx, r10d
0x1800080d1  cmp     r10d, r11d
0x1800080d4  jb      short loc_1800080C1
0x1800080d6  lea     rdx, aReconstructopt_2; "ReconstructOptionArray: caller passed i"...
0x1800080dd  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x1800080e4  call    WriteDbgTraceErrorGpd
0x1800080e9  xor     eax, eax
0x1800080eb  jmp     short loc_180008113
0x1800080ed  cmp     r14d, ebp
0x1800080f0  ja      loc_1800081E1
0x1800080f6  test    r14d, r14d
0x1800080f9  jz      short loc_18000810E
0x1800080fb  mov     r8d, r14d
0x1800080fe  lea     rdx, [rsp+458h+Src]; Src
0x180008103  add     r8, r8; Size
0x180008106  mov     rcx, rdi; void *
0x180008109  call    memcpy_0
0x18000810e  mov     eax, 1
0x180008113  mov     r14, [rsp+458h+arg_10]
0x18000811b  mov     r15, [rsp+458h+var_28]
0x180008123  mov     rcx, [rsp+458h+var_38]
0x18000812b  xor     rcx, rsp; StackCookie
0x18000812e  call    __security_check_cookie
0x180008133  add     rsp, 438h
0x18000813a  pop     rdi
0x18000813b  pop     rsi
0x18000813c  pop     rbp
0x18000813d  pop     rbx
0x18000813e  retn
0x18000813f  mov     [rsp+rax*2+458h+Src], dl
0x180008143  mov     [rsp+rax*2+458h+var_437], 0
0x180008148  cmp     r10d, r11d
0x18000814b  jnb     short loc_18000815C
0x18000814d  cmp     dword ptr [r15+r10*4], 0
0x180008152  jnz     short loc_180008162
0x180008154  inc     r10d
0x180008157  cmp     r10d, r11d
0x18000815a  jb      short loc_18000814D
0x18000815c  jz      loc_180008095
0x180008162  mov     [rsp+rax*2+458h+var_437], r14b
0x180008167  cmp     r10d, r11d
0x18000816a  jnb     loc_18000827F
0x180008170  cmp     r14d, ebp
0x180008173  jnb     loc_18000828D
0x180008179  mov     ecx, r14d
0x18000817c  lea     rdx, [rcx+rcx]
0x180008180  lea     ecx, [r14+1]
0x180008184  mov     [rsp+rdx+458h+Src], r10b
0x180008189  inc     r10d
0x18000818c  mov     [rsp+rdx+458h+var_437], cl
0x180008190  inc     r14d
0x180008193  cmp     r10d, r11d
0x180008196  jnb     loc_18000827F
0x18000819c  cmp     dword ptr [r15+r10*4], 0
0x1800081a1  jnz     short loc_180008167
0x1800081a3  inc     r10d
0x1800081a6  cmp     r10d, r11d
0x1800081a9  jb      short loc_18000819C
0x1800081ab  jmp     short loc_180008167
0x1800081ad  lea     rdx, aReconstructopt_1; "ReconstructOptionArray: Selected option"...
0x1800081b4  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x1800081bb  call    WriteDbgTraceErrorGpd
0x1800081c0  xor     eax, eax
0x1800081c2  jmp     loc_180008113
0x1800081c7  lea     rdx, aReconstructopt; "ReconstructOptionArray: caller passed i"...
0x1800081ce  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x1800081d5  call    WriteDbgTraceErrorGpd
0x1800081da  xor     eax, eax
0x1800081dc  jmp     loc_180008123
0x1800081e1  lea     rdx, aReconstructopt_3; "ReconstructOptionArray: exceeded limit "...
0x1800081e8  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x1800081ef  call    WriteDbgTraceErrorGpd
0x1800081f4  xor     eax, eax
0x1800081f6  jmp     loc_180008113
0x1800081fb  lea     rdx, aReconstructopt_5; "ReconstructOptionArray: caller-supplied"...
0x180008202  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x180008209  call    WriteDbgTraceErrorGpd
0x18000820e  mov     ebp, 200h
0x180008213  jmp     loc_180008027
0x180008218  lea     rdx, aReconstructopt_7; "ReconstructOptionArray: GPD contains to"...
0x18000821f  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x180008226  call    WriteDbgTraceErrorGpd
0x18000822b  xor     eax, eax
0x18000822d  jmp     loc_180008123
0x180008232  lea     rdx, aReconstructopt_4; "ReconstructOptionArray: Too many featur"...
0x180008239  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x180008240  call    WriteDbgTraceErrorGpd
0x180008245  xor     eax, eax
0x180008247  jmp     loc_180008123
0x18000824c  mov     [rsp+rax*2+458h+var_437], r14b
0x180008251  test    ecx, ecx
0x180008253  jz      short loc_18000827F
0x180008255  cmp     r14d, ebp
0x180008258  jnb     short loc_1800082A7
0x18000825a  lea     r8, [rdi+rcx*2]
0x18000825e  mov     ecx, r14d
0x180008261  lea     rdx, [rcx+rcx]
0x180008265  movzx   ecx, byte ptr [r8]
0x180008269  mov     [rsp+rdx+458h+Src], cl
0x18000826d  lea     ecx, [r14+1]
0x180008271  mov     [rsp+rdx+458h+var_437], cl
0x180008275  inc     r14d
0x180008278  movzx   ecx, byte ptr [r8+1]
0x18000827d  jmp     short loc_180008251
0x18000827f  lea     ecx, [r14-1]
0x180008283  mov     [rsp+rcx*2+458h+var_437], 0
0x180008288  jmp     loc_180008095
0x18000828d  lea     rdx, aReconstructopt_0; "ReconstructOptionArray: exceeded limit "...
0x180008294  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x18000829b  call    WriteDbgTraceErrorGpd
0x1800082a0  xor     eax, eax
0x1800082a2  jmp     loc_180008113
0x1800082a7  lea     rdx, aReconstructopt_6; "ReconstructOptionArray: exceeded max su"...
0x1800082ae  lea     rcx, aGpdreconstruct; "GPDReconstructOptionArray"
0x1800082b5  call    WriteDbgTraceErrorGpd
0x1800082ba  xor     eax, eax
0x1800082bc  jmp     loc_180008113
```
