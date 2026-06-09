# BInterpretTokens

- ea: `0x180041eec`
- end: `0x18004222c`
- name: `BInterpretTokens`
- size: `832`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800701a8`

## callees

- `0x180007220`
- `0x180008fc8`
- `0x18000a0b8`
- `0x18000a2d8`
- `0x18000aef4`
- `0x180037834`
- `0x180041eec`
- `0x180042240`
- `0x1800445dc`
- `0x18004485c`
- `0x180070d04`
- `0x180074550`

## string_xrefs

- `0x180042100`: `BInterpretTokens`
- `0x1800421a0`: `BInterpretTokens`
- `0x1800421e0`: `BInterpretTokens`

## pseudocode

```c
_BOOL8 __fastcall BInterpretTokens(__int64 a1, unsigned int a2, _DWORD *a3)
{
  unsigned __int16 i; // di
  __int64 v7; // rdx
  __int64 v8; // rax
  const char *v9; // rcx
  size_t v10; // r8
  int v11; // r8d
  int v12; // eax
  int v13; // r8d
  unsigned __int16 v14; // si
  unsigned int *v15; // rdi
  unsigned int v16; // ecx
  __int64 v17; // rdx
  __int64 v19; // rdx
  int v20; // ecx
  int v21; // ecx
  bool v22; // zf
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  const char *v26; // [rsp+50h] [rbp-10h] BYREF
  __int64 v27; // [rsp+58h] [rbp-8h]
  __int64 v28; // [rsp+A0h] [rbp+40h] BYREF

  if ( a2 )
  {
    v27 = 8;
    v26 = "InputBin";
    for ( i = 0; ; ++i )
    {
      v7 = 56LL * i;
      if ( *(_DWORD *)(v7 + a1) == 65283 )
        break;
      if ( *(_DWORD *)(v7 + a1) < 0xFF00u )
      {
        v8 = 4LL * *(unsigned int *)(v7 + a1);
        if ( !LODWORD((&mMainKeywordTable)[v8 + 2]) && *((_DWORD *)&mMainKeywordTable + 2 * v8 + 5) == 1 )
        {
          v9 = *(const char **)(v7 + a1 + 24);
          if ( v9 )
          {
            v10 = *(unsigned int *)(v7 + a1 + 32);
            if ( (_DWORD)v10 == 8 && !strncmp_0(v9, "InputBin", v10) )
            {
              v12 = DWregisterSymbol((unsigned int)&v26, 1, v11, -1, (__int64)a3);
              if ( v12 != -1 )
              {
                LODWORD(v27) = 10;
                v26 = "FORMSOURCE";
                DWregisterSymbol((unsigned int)&v26, 2, v13, v12, (__int64)a3);
              }
              break;
            }
          }
        }
      }
    }
  }
  else
  {
    HIDWORD(v28) = 0;
    BwriteToHeap((char *)&v28 + 4, &qword_18007D1D0, 2, 4, a3);
    BexchangeArbDataInFOATNode(0, 0, 104);
  }
  v14 = 0;
  while ( (int)a3[555] < 2 )
  {
    v15 = (unsigned int *)(a1 + 56LL * v14);
    v16 = *v15;
    if ( *v15 == a3[558] )
    {
      v17 = 1;
LABEL_40:
      VIgnoreBlock(a1 + 56LL * v14, v17, a3);
      goto LABEL_41;
    }
    switch ( v16 )
    {
      case 0xFF00u:
        goto LABEL_41;
      case 0xFF01u:
        if ( !(unsigned int)BidentifyAttributeKeyword(a1 + 56LL * v14, a3) )
        {
          if ( !a2 )
            goto LABEL_41;
          vIdentifySource(a1 + 56LL * v14, a3);
          WriteDbgTraceErrorGpd(
            "BInterpretTokens",
            "Warning, unrecognized keyword: %0.*s",
            v15[4],
            *((const char **)v15 + 1));
          v17 = 0;
          goto LABEL_40;
        }
        v16 = *v15;
        break;
      case 0xFF02u:
        goto LABEL_41;
      case 0xFF03u:
        return a3[153] == 0;
    }
    v19 = 4LL * v16;
    v20 = (int)(&mMainKeywordTable)[v19 + 2];
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( v21 )
      {
        v22 = v21 == 1;
        v23 = a1 + 56LL * v14;
        if ( !v22 )
        {
          vIdentifySource(v23, a3);
          WriteDbgTraceErrorGpd(
            "BInterpretTokens",
            "Internal Error: unrecognized keyword type! %0.*s.",
            v15[4],
            *((const char **)v15 + 1));
          a3[555] = 3;
          a3[556] = 4;
          goto LABEL_41;
        }
        v24 = BprocessSpecialKeyword(v23, a2, a3);
      }
      else
      {
        if ( a2 )
          goto LABEL_41;
        v24 = BprocessAttribute(a1 + 56LL * v14, a3, &mMainKeywordTable);
      }
      goto LABEL_29;
    }
    if ( *((_DWORD *)&mMainKeywordTable + 2 * v19 + 5) != 14 )
    {
      v24 = BpushState(a1 + 56LL * v14, a2, a3);
LABEL_29:
      if ( !v24 )
        vIdentifySource(a1 + 56LL * v14, a3);
      goto LABEL_41;
    }
    v25 = a3[153];
    if ( v25 )
    {
      a3[153] = v25 - 1;
    }
    else
    {
      a3[556] = 1;
      a3[555] = 3;
      vIdentifySource(a1 + 56LL * v14, a3);
      WriteDbgTraceErrorGpd("BInterpretTokens", "Unmatched closing brace!");
    }
LABEL_41:
    ++v14;
  }
  return 0;
}

```

## disassembly

```asm
0x180041eec  mov     [rsp-28h+arg_0], rbx
0x180041ef1  mov     [rsp-28h+arg_18], rsi
0x180041ef6  push    rbp
0x180041ef7  push    rdi
0x180041ef8  push    r13
0x180041efa  push    r14
0x180041efc  push    r15
0x180041efe  mov     rbp, rsp
0x180041f01  sub     rsp, 60h
0x180041f05  mov     rbx, r8
0x180041f08  lea     r8, mMainKeywordTable
0x180041f0f  mov     r14d, edx
0x180041f12  mov     r15, rcx
0x180041f15  mov     r13d, 1
0x180041f1b  test    edx, edx
0x180041f1d  jz      loc_180041FE5
0x180041f23  lea     rsi, aInputbin; "InputBin"
0x180041f2a  mov     [rbp+var_8], 8
0x180041f32  mov     [rbp+var_10], rsi
0x180041f36  xor     edi, edi
0x180041f38  movzx   eax, di
0x180041f3b  imul    rdx, rax, 38h ; '8'
0x180041f3f  cmp     dword ptr [rdx+r15], 0FF03h
0x180041f47  jz      loc_18004205A
0x180041f4d  cmp     dword ptr [rdx+r15], 0FF00h
0x180041f55  jnb     short loc_180041F96
0x180041f57  mov     eax, [rdx+r15]
0x180041f5b  shl     rax, 5
0x180041f5f  cmp     dword ptr [rax+r8+10h], 0
0x180041f65  jnz     short loc_180041F96
0x180041f67  cmp     [rax+r8+14h], r13d
0x180041f6c  jnz     short loc_180041F96
0x180041f6e  mov     rcx, [rdx+r15+18h]; Str1
0x180041f73  test    rcx, rcx
0x180041f76  jz      short loc_180041F96
0x180041f78  mov     r8d, [rdx+r15+20h]; MaxCount
0x180041f7d  cmp     r8d, 8
0x180041f81  jnz     short loc_180041F8F
0x180041f83  mov     rdx, rsi; Str2
0x180041f86  call    strncmp_0
0x180041f8b  test    eax, eax
0x180041f8d  jz      short loc_180041F9C
0x180041f8f  lea     r8, mMainKeywordTable
0x180041f96  add     di, r13w
0x180041f9a  jmp     short loc_180041F38
0x180041f9c  or      edi, 0FFFFFFFFh
0x180041f9f  mov     [rsp+60h+var_40], rbx
0x180041fa4  mov     r9d, edi
0x180041fa7  lea     rcx, [rbp+var_10]
0x180041fab  mov     edx, r13d
0x180041fae  call    DWregisterSymbol
0x180041fb3  cmp     eax, edi
0x180041fb5  jz      loc_180042053
0x180041fbb  lea     rcx, aFormsource; "FORMSOURCE"
0x180041fc2  mov     dword ptr [rbp+var_8], 0Ah
0x180041fc9  mov     [rbp+var_10], rcx
0x180041fcd  mov     r9d, eax
0x180041fd0  lea     rcx, [rbp+var_10]
0x180041fd4  mov     [rsp+60h+var_40], rbx
0x180041fd9  mov     edx, 2
0x180041fde  call    DWregisterSymbol
0x180041fe3  jmp     short loc_180042053
0x180041fe5  mov     r9d, 4
0x180041feb  mov     [rbp+arg_10], 0
0x180041ff3  lea     rdx, qword_18007D1D0
0x180041ffa  mov     [rbp+arg_8], 0
0x180042001  lea     rcx, [rbp+arg_10+4]
0x180042005  mov     [rsp+60h+var_40], rbx
0x18004200a  lea     r8d, [r9-2]
0x18004200e  call    BwriteToHeap
0x180042013  mov     [rsp+60h+var_20], rbx
0x180042018  lea     rax, [rbp+arg_8]
0x18004201c  xor     edx, edx
0x18004201e  mov     [rsp+60h+var_28], 0
0x180042026  mov     [rsp+60h+var_30], rax
0x18004202b  xor     ecx, ecx
0x18004202d  lea     rax, [rbp+arg_10]
0x180042031  mov     dword ptr [rbp+arg_10], 0
0x180042038  mov     [rsp+60h+var_38], rax
0x18004203d  lea     r9d, [rdx+8]
0x180042041  mov     [rsp+60h+var_40], 0
0x18004204a  lea     r8d, [rdx+68h]
0x18004204e  call    BexchangeArbDataInFOATNode
0x180042053  lea     r8, mMainKeywordTable
0x18004205a  xor     esi, esi
0x18004205c  jmp     loc_180042204
0x180042061  movzx   eax, si
0x180042064  imul    rdi, rax, 38h ; '8'
0x180042068  add     rdi, r15
0x18004206b  mov     ecx, [rdi]
0x18004206d  cmp     ecx, [rbx+8B8h]
0x180042073  jnz     short loc_18004207D
0x180042075  mov     edx, r13d
0x180042078  jmp     loc_1800421EE
0x18004207d  mov     eax, ecx
0x18004207f  sub     eax, 0FF00h
0x180042084  jz      loc_180042200
0x18004208a  sub     eax, r13d
0x18004208d  jz      short loc_1800420AD
0x18004208f  sub     eax, r13d
0x180042092  jz      loc_180042200
0x180042098  cmp     eax, r13d
0x18004209b  jnz     short loc_1800420C9
0x18004209d  xor     eax, eax
0x18004209f  cmp     [rbx+264h], eax
0x1800420a5  setz    al
0x1800420a8  jmp     loc_180042213
0x1800420ad  mov     rdx, rbx
0x1800420b0  mov     rcx, rdi
0x1800420b3  call    BidentifyAttributeKeyword
0x1800420b8  test    eax, eax
0x1800420ba  jz      loc_1800421C1
0x1800420c0  mov     ecx, [rdi]
0x1800420c2  lea     r8, mMainKeywordTable
0x1800420c9  mov     edx, ecx
0x1800420cb  shl     rdx, 5
0x1800420cf  mov     ecx, [rdx+r8+10h]
0x1800420d4  test    ecx, ecx
0x1800420d6  jz      loc_18004215E
0x1800420dc  sub     ecx, r13d
0x1800420df  jz      short loc_180042148
0x1800420e1  cmp     ecx, r13d
0x1800420e4  mov     rcx, rdi
0x1800420e7  jz      short loc_180042125
0x1800420e9  mov     rdx, rbx
0x1800420ec  call    vIdentifySource
0x1800420f1  mov     r9, [rdi+8]
0x1800420f5  lea     rdx, aInternalErrorU_0; "Internal Error: unrecognized keyword ty"...
0x1800420fc  mov     r8d, [rdi+10h]
0x180042100  lea     rcx, aBinterprettoke; "BInterpretTokens"
0x180042107  call    WriteDbgTraceErrorGpd
0x18004210c  mov     dword ptr [rbx+8ACh], 3
0x180042116  mov     dword ptr [rbx+8B0h], 4
0x180042120  jmp     loc_1800421F9
0x180042125  mov     r8, rbx
0x180042128  mov     edx, r14d
0x18004212b  call    BprocessSpecialKeyword
0x180042130  test    eax, eax
0x180042132  jnz     loc_1800421F9
0x180042138  mov     rdx, rbx
0x18004213b  mov     rcx, rdi
0x18004213e  call    vIdentifySource
0x180042143  jmp     loc_1800421F9
0x180042148  test    r14d, r14d
0x18004214b  jnz     loc_180042200
0x180042151  mov     rdx, rbx
0x180042154  mov     rcx, rdi
0x180042157  call    BprocessAttribute
0x18004215c  jmp     short loc_180042130
0x18004215e  cmp     dword ptr [rdx+r8+14h], 0Eh
0x180042164  jnz     short loc_1800421AE
0x180042166  mov     eax, [rbx+264h]
0x18004216c  test    eax, eax
0x18004216e  jz      short loc_18004217D
0x180042170  dec     eax
0x180042172  mov     [rbx+264h], eax
0x180042178  jmp     loc_180042200
0x18004217d  mov     rdx, rbx
0x180042180  mov     [rbx+8B0h], r13d
0x180042187  mov     rcx, rdi
0x18004218a  mov     dword ptr [rbx+8ACh], 3
0x180042194  call    vIdentifySource
0x180042199  lea     rdx, aUnmatchedClosi; "Unmatched closing brace!"
0x1800421a0  lea     rcx, aBinterprettoke; "BInterpretTokens"
0x1800421a7  call    WriteDbgTraceErrorGpd
0x1800421ac  jmp     short loc_1800421F9
0x1800421ae  mov     r8, rbx
0x1800421b1  mov     edx, r14d
0x1800421b4  mov     rcx, rdi
0x1800421b7  call    BpushState
0x1800421bc  jmp     loc_180042130
0x1800421c1  test    r14d, r14d
0x1800421c4  jz      short loc_1800421F9
0x1800421c6  mov     rdx, rbx
0x1800421c9  mov     rcx, rdi
0x1800421cc  call    vIdentifySource
0x1800421d1  mov     r9, [rdi+8]
0x1800421d5  lea     rdx, aWarningUnrecog; "Warning, unrecognized keyword: %0.*s"
0x1800421dc  mov     r8d, [rdi+10h]
0x1800421e0  lea     rcx, aBinterprettoke; "BInterpretTokens"
0x1800421e7  call    WriteDbgTraceErrorGpd
0x1800421ec  xor     edx, edx
0x1800421ee  mov     r8, rbx
0x1800421f1  mov     rcx, rdi
0x1800421f4  call    VIgnoreBlock
0x1800421f9  lea     r8, mMainKeywordTable
0x180042200  add     si, r13w
0x180042204  cmp     dword ptr [rbx+8ACh], 2
0x18004220b  jl      loc_180042061
0x180042211  xor     eax, eax
0x180042213  lea     r11, [rsp+60h+var_s0]
0x180042218  mov     rbx, [r11+30h]
0x18004221c  mov     rsi, [r11+48h]
0x180042220  mov     rsp, r11
0x180042223  pop     r15
0x180042225  pop     r14
0x180042227  pop     r13
0x180042229  pop     rdi
0x18004222a  pop     rbp
0x18004222b  retn
```
