# RtlCompareEncodedLBlobs

- ea: `0x18000fc1c`
- end: `0x18000fee8`
- name: `RtlCompareEncodedLBlobs`
- size: `716`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f6bc`
- `0x1800223f4`

## callees

- `0x180008140`
- `0x18000fafc`
- `0x18000fc1c`
- `0x1800107e0`
- `0x180033010`

## string_xrefs

- `0x18000fc69`: `RtlCompareEncodedLBlobs`
- `0x18000fc98`: `RtlCompareEncodedLBlobs`
- `0x18000fd7d`: `RtlCompareEncodedLBlobs`
- `0x18000fdc8`: `RtlCompareEncodedLBlobs`
- `0x18000fe93`: `RtlCompareEncodedLBlobs`
- `0x18000fe9e`: `Not-null check failed: ComparisonResult`

## pseudocode

```c
__int64 __fastcall RtlCompareEncodedLBlobs(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 (__fastcall *a5)(_QWORD),
        int *a6)
{
  const char *v7; // rax
  __int64 v8; // rbx
  int v9; // ecx
  __int64 v10; // rdi
  __int64 v11; // rsi
  __int64 v12; // r14
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // eax
  int v16; // eax
  __int64 v18; // rax
  unsigned int v19; // r12d
  __int64 v20; // rax
  const char *v21; // [rsp+20h] [rbp-40h] BYREF
  const char *v22; // [rsp+28h] [rbp-38h]
  __int64 v23; // [rsp+30h] [rbp-30h]
  const char *v24; // [rsp+38h] [rbp-28h]
  unsigned int v25; // [rsp+40h] [rbp-20h]
  unsigned int v26; // [rsp+44h] [rbp-1Ch]
  _BYTE v27[24]; // [rsp+48h] [rbp-18h] BYREF

  if ( !a6 )
  {
    v23 = 2251;
    v21 = "onecore\\base\\lstring\\lblob.cpp";
    v22 = "RtlCompareEncodedLBlobs";
    v7 = "Not-null check failed: ComparisonResult";
    goto LABEL_39;
  }
  *a6 = 0;
  if ( !a1 )
  {
    v23 = 2252;
    v21 = "onecore\\base\\lstring\\lblob.cpp";
    v22 = "RtlCompareEncodedLBlobs";
    v7 = "Not-null check failed: String1";
LABEL_39:
    v24 = v7;
    RtlReportErrorOrigination(&v21, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a3 )
  {
    v23 = 2254;
    v21 = "onecore\\base\\lstring\\lblob.cpp";
    v22 = "RtlCompareEncodedLBlobs";
    v7 = "Not-null check failed: String2";
    goto LABEL_39;
  }
  v8 = a1[2];
  v9 = 0;
  v10 = a3[2];
  v11 = v8 + *a1;
  v12 = v10 + *a3;
  if ( v8 == v11 )
  {
LABEL_34:
    if ( v10 != v12 )
      v9 = -1;
    v16 = v9;
LABEL_37:
    *a6 = v16;
    return 0;
  }
  else
  {
    if ( a5 )
    {
      while ( 1 )
      {
        if ( v10 == v12 )
          goto LABEL_14;
        v13 = RtlDecodeUtf16LE(v27, v8, v11);
        v8 = *(_QWORD *)(v13 + 8);
        v25 = *(_DWORD *)v13;
        if ( v25 == -1 )
          break;
        v14 = RtlDecodeUtf16LE(&v21, v10, v12);
        v10 = *(_QWORD *)(v14 + 8);
        v26 = *(_DWORD *)v14;
        if ( v26 == -1 )
        {
          if ( (int)v10 < 0 )
          {
            v23 = 2276;
            goto LABEL_18;
          }
LABEL_40:
          INTERNAL_ERROR_ACTION(-1073741595);
        }
        v25 = a5(v25);
        v15 = a5(v26);
        if ( v25 < v15 )
          goto LABEL_29;
        if ( v25 != v15 )
          goto LABEL_15;
        v9 = 0;
        if ( v8 == v11 )
          goto LABEL_14;
      }
      if ( (int)v8 >= 0 )
        goto LABEL_40;
      v23 = 2275;
    }
    else
    {
      while ( 1 )
      {
        if ( v10 == v12 )
        {
LABEL_14:
          if ( v8 == v11 )
            goto LABEL_34;
LABEL_15:
          v16 = 1;
          goto LABEL_37;
        }
        v18 = RtlDecodeUtf16LE(&v21, v8, v11);
        v19 = *(_DWORD *)v18;
        v8 = *(_QWORD *)(v18 + 8);
        if ( *(_DWORD *)v18 == -1 )
          break;
        v20 = RtlDecodeUtf16LE(v27, v10, v12);
        v10 = *(_QWORD *)(v20 + 8);
        if ( *(_DWORD *)v20 == -1 )
        {
          if ( (int)v10 >= 0 )
            goto LABEL_40;
          v23 = 2293;
LABEL_18:
          v21 = "onecore\\base\\lstring\\lblob.cpp";
          v22 = "RtlCompareEncodedLBlobs";
          v24 = "__rv.UcsCharacter != (0xffffffff)";
          RtlReportErrorOrigination(&v21, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v10);
          return (unsigned int)v10;
        }
        if ( v19 < *(_DWORD *)v20 )
        {
LABEL_29:
          v16 = -1;
          goto LABEL_37;
        }
        if ( v19 != *(_DWORD *)v20 )
          goto LABEL_15;
        v9 = 0;
        if ( v8 == v11 )
          goto LABEL_14;
      }
      if ( (int)v8 >= 0 )
        goto LABEL_40;
      v23 = 2292;
    }
    v21 = "onecore\\base\\lstring\\lblob.cpp";
    v22 = "RtlCompareEncodedLBlobs";
    v24 = "__rv.UcsCharacter != (0xffffffff)";
    RtlReportErrorOrigination(&v21, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v8);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x18000fc1c  mov     [rsp-28h+arg_8], rbx
0x18000fc21  mov     [rsp-28h+arg_18], rsi
0x18000fc26  push    rbp
0x18000fc27  push    rdi
0x18000fc28  push    r12
0x18000fc2a  push    r13
0x18000fc2c  push    r14
0x18000fc2e  mov     rbp, rsp
0x18000fc31  sub     rsp, 60h
0x18000fc35  mov     r13, [rbp+arg_28]
0x18000fc39  mov     rax, rcx
0x18000fc3c  mov     r12, [rbp+arg_20]
0x18000fc40  test    r13, r13
0x18000fc43  jz      loc_18000FE80
0x18000fc49  mov     dword ptr [r13+0], 0
0x18000fc51  test    rax, rax
0x18000fc54  jnz     short loc_18000FC80
0x18000fc56  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18000fc5d  mov     [rbp+var_30], 8CCh
0x18000fc65  mov     [rbp+var_40], rax
0x18000fc69  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x18000fc70  mov     [rbp+var_38], rax
0x18000fc74  lea     rax, aNotNullCheckFa_1; "Not-null check failed: String1"
0x18000fc7b  jmp     loc_18000FEA5
0x18000fc80  test    r8, r8
0x18000fc83  jnz     short loc_18000FCAF
0x18000fc85  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18000fc8c  mov     [rbp+var_30], 8CEh
0x18000fc94  mov     [rbp+var_40], rax
0x18000fc98  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x18000fc9f  mov     [rbp+var_38], rax
0x18000fca3  lea     rax, aNotNullCheckFa_10; "Not-null check failed: String2"
0x18000fcaa  jmp     loc_18000FEA5
0x18000fcaf  mov     rbx, [rax+10h]
0x18000fcb3  xor     ecx, ecx
0x18000fcb5  mov     rsi, [rax]
0x18000fcb8  mov     rdi, [r8+10h]
0x18000fcbc  add     rsi, rbx
0x18000fcbf  mov     r14, [r8]
0x18000fcc2  add     r14, rdi
0x18000fcc5  cmp     rbx, rsi
0x18000fcc8  jz      loc_18000FE6D
0x18000fcce  test    r12, r12
0x18000fcd1  jz      loc_18000FDEE
0x18000fcd7  cmp     rdi, r14
0x18000fcda  jz      short loc_18000FD45
0x18000fcdc  mov     r8, rsi
0x18000fcdf  lea     rcx, [rbp+var_18]
0x18000fce3  mov     rdx, rbx
0x18000fce6  call    RtlDecodeUtf16LE
0x18000fceb  mov     ecx, [rax]
0x18000fced  mov     rbx, [rax+8]
0x18000fcf1  mov     [rbp+var_20], ecx
0x18000fcf4  cmp     ecx, 0FFFFFFFFh
0x18000fcf7  jz      loc_18000FDA3
0x18000fcfd  mov     r8, r14
0x18000fd00  lea     rcx, [rbp+var_40]
0x18000fd04  mov     rdx, rdi
0x18000fd07  call    RtlDecodeUtf16LE
0x18000fd0c  mov     ecx, [rax]
0x18000fd0e  mov     rdi, [rax+8]
0x18000fd12  mov     [rbp+var_1C], ecx
0x18000fd15  cmp     ecx, 0FFFFFFFFh
0x18000fd18  jz      short loc_18000FD58
0x18000fd1a  mov     ecx, [rbp+var_20]
0x18000fd1d  mov     rax, r12
0x18000fd20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd25  mov     ecx, [rbp+var_1C]
0x18000fd28  mov     [rbp+var_20], eax
0x18000fd2b  mov     rax, r12
0x18000fd2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd33  cmp     [rbp+var_20], eax
0x18000fd36  jb      loc_18000FE42
0x18000fd3c  jnz     short loc_18000FD4E
0x18000fd3e  xor     ecx, ecx
0x18000fd40  cmp     rbx, rsi
0x18000fd43  jnz     short loc_18000FCD7
0x18000fd45  cmp     rbx, rsi
0x18000fd48  jz      loc_18000FE6D
0x18000fd4e  mov     eax, 1
0x18000fd53  jmp     loc_18000FE78
0x18000fd58  test    edi, edi
0x18000fd5a  jns     loc_18000FEDD
0x18000fd60  mov     [rbp+var_30], 8E4h
0x18000fd68  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18000fd6f  mov     r8d, edi
0x18000fd72  mov     [rbp+var_40], rax
0x18000fd76  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18000fd7d  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x18000fd84  mov     [rbp+var_38], rax
0x18000fd88  lea     rcx, [rbp+var_40]
0x18000fd8c  lea     rax, aRvUcscharacter; "__rv.UcsCharacter != (0xffffffff)"
0x18000fd93  mov     [rbp+var_28], rax
0x18000fd97  call    RtlReportErrorOrigination
0x18000fd9c  mov     eax, edi
0x18000fd9e  jmp     loc_18000FEC4
0x18000fda3  test    ebx, ebx
0x18000fda5  jns     loc_18000FEDD
0x18000fdab  mov     [rbp+var_30], 8E3h
0x18000fdb3  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18000fdba  mov     r8d, ebx
0x18000fdbd  mov     [rbp+var_40], rax
0x18000fdc1  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18000fdc8  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x18000fdcf  mov     [rbp+var_38], rax
0x18000fdd3  lea     rcx, [rbp+var_40]
0x18000fdd7  lea     rax, aRvUcscharacter; "__rv.UcsCharacter != (0xffffffff)"
0x18000fdde  mov     [rbp+var_28], rax
0x18000fde2  call    RtlReportErrorOrigination
0x18000fde7  mov     eax, ebx
0x18000fde9  jmp     loc_18000FEC4
0x18000fdee  cmp     rdi, r14
0x18000fdf1  jz      loc_18000FD45
0x18000fdf7  mov     r8, rsi
0x18000fdfa  lea     rcx, [rbp+var_40]
0x18000fdfe  mov     rdx, rbx
0x18000fe01  call    RtlDecodeUtf16LE
0x18000fe06  mov     r12d, [rax]
0x18000fe09  mov     rbx, [rax+8]
0x18000fe0d  cmp     r12d, 0FFFFFFFFh
0x18000fe11  jz      short loc_18000FE5C
0x18000fe13  mov     r8, r14
0x18000fe16  lea     rcx, [rbp+var_18]
0x18000fe1a  mov     rdx, rdi
0x18000fe1d  call    RtlDecodeUtf16LE
0x18000fe22  cmp     dword ptr [rax], 0FFFFFFFFh
0x18000fe25  mov     rdi, [rax+8]
0x18000fe29  jz      short loc_18000FE47
0x18000fe2b  cmp     r12d, [rax]
0x18000fe2e  jb      short loc_18000FE42
0x18000fe30  jnz     loc_18000FD4E
0x18000fe36  xor     ecx, ecx
0x18000fe38  cmp     rbx, rsi
0x18000fe3b  jnz     short loc_18000FDEE
0x18000fe3d  jmp     loc_18000FD45
0x18000fe42  or      eax, 0FFFFFFFFh
0x18000fe45  jmp     short loc_18000FE78
0x18000fe47  test    edi, edi
0x18000fe49  jns     loc_18000FEDD
0x18000fe4f  mov     [rbp+var_30], 8F5h
0x18000fe57  jmp     loc_18000FD68
0x18000fe5c  test    ebx, ebx
0x18000fe5e  jns     short loc_18000FEDD
0x18000fe60  mov     [rbp+var_30], 8F4h
0x18000fe68  jmp     loc_18000FDB3
0x18000fe6d  or      eax, 0FFFFFFFFh
0x18000fe70  cmp     rdi, r14
0x18000fe73  cmovnz  ecx, eax
0x18000fe76  mov     eax, ecx
0x18000fe78  mov     [r13+0], eax
0x18000fe7c  xor     eax, eax
0x18000fe7e  jmp     short loc_18000FEC4
0x18000fe80  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18000fe87  mov     [rbp+var_30], 8CBh
0x18000fe8f  mov     [rbp+var_40], rax
0x18000fe93  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x18000fe9a  mov     [rbp+var_38], rax
0x18000fe9e  lea     rax, aNotNullCheckFa_8; "Not-null check failed: ComparisonResult"
0x18000fea5  mov     r8d, 0C000000Dh
0x18000feab  mov     [rbp+var_28], rax
0x18000feaf  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18000feb6  lea     rcx, [rbp+var_40]
0x18000feba  call    RtlReportErrorOrigination
0x18000febf  mov     eax, 0C000000Dh
0x18000fec4  lea     r11, [rsp+60h+var_s0]
0x18000fec9  mov     rbx, [r11+38h]
0x18000fecd  mov     rsi, [r11+48h]
0x18000fed1  mov     rsp, r11
0x18000fed4  pop     r14
0x18000fed6  pop     r13
0x18000fed8  pop     r12
0x18000feda  pop     rdi
0x18000fedb  pop     rbp
0x18000fedc  retn
0x18000fedd  mov     ecx, 0C00000E5h; int
0x18000fee2  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
