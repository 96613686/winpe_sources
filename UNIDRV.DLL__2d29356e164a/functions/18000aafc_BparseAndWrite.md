# BparseAndWrite

- ea: `0x18000aafc`
- end: `0x18000aeec`
- name: `BparseAndWrite`
- size: `1008`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18000a82c`

## callees

- `0x180007220`
- `0x180008ab0`
- `0x180009370`
- `0x180009e3c`
- `0x18000aafc`
- `0x18000aef4`
- `0x18000af9c`
- `0x18000b09c`
- `0x18000b504`
- `0x18000b5d0`
- `0x18000bcf0`
- `0x18000bdc8`
- `0x18000bf30`
- `0x18003f1c0`
- `0x18004485c`
- `0x180072170`
- `0x180072260`
- `0x180072384`
- `0x180072540`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000ad22`
- `KERNEL32!LocalFree` at `0x18000ad22`
- `KERNEL32!LocalAlloc` at `0x18000ab6c`
- `KERNEL32!LocalAlloc` at `0x18000ab6c`

## string_xrefs

- `0x18000ac67`: `BparseAndWrite`
- `0x18000ae9d`: `BparseAndWrite`

## pseudocode

```c
__int64 __fastcall BparseAndWrite(_DWORD *a1, unsigned int *a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  _DWORD *v6; // rsi
  _DWORD *v7; // r12
  __int64 v8; // rax
  int v9; // r15d
  int v10; // r14d
  unsigned int v11; // edi
  int v12; // r15d
  int v13; // edx
  int v14; // r9d
  __int64 (__fastcall *v15)(_QWORD, _QWORD, _QWORD, _QWORD); // r8
  unsigned int v16; // eax
  __int128 v18; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v19; // [rsp+90h] [rbp+50h]

  v19 = a3;
  v6 = a1;
  v18 = *(_OWORD *)(a2 + 6);
  if ( !(_DWORD)a3 )
  {
    if ( a1 )
      goto LABEL_3;
    return 0;
  }
  if ( !a4 )
  {
    vIdentifySource(a2, a5);
    WriteDbgTraceErrorGpd("BparseAndWrite", "internal consistency error.  heap ptr not supplied.");
    return 0;
  }
LABEL_3:
  v7 = 0;
  v8 = 4LL * *a2;
  v9 = *((_DWORD *)&mMainKeywordTable + 2 * v8 + 3);
  v10 = (int)(&mMainKeywordTable)[v8 + 1];
  if ( !(_DWORD)a3 )
    goto LABEL_6;
  v7 = LocalAlloc(0, (unsigned int)a5[628]);
  if ( !v7 )
  {
    a5[555] = 3;
    a5[556] = 2;
    return 0;
  }
  a3 = v19;
LABEL_6:
  v11 = 0;
  v12 = v9 & 1;
  if ( (_DWORD)a3 )
    v6 = v7;
  if ( v10 > 7 )
  {
    switch ( v10 )
    {
      case 8:
        v16 = BparseOrderDep(&v18, v6, a5);
        goto LABEL_18;
      case 10:
      case 11:
      case 12:
        v16 = BparseAndTerminateString(&v18, v6, (unsigned int)v10, a5);
        goto LABEL_18;
      case 13:
        v16 = BparseCommandString((__int64)&v18, v6, (__int64)a5);
        goto LABEL_18;
      case 15:
        *v6 = 0;
        v16 = BprocessParam((__int64)&v18, v6, (__int64)a5);
        goto LABEL_18;
      case 16:
        goto LABEL_34;
    }
  }
  else
  {
    switch ( v10 )
    {
      case 7:
        v16 = BparseConstraint(&v18, v6, a3, a5);
        goto LABEL_18;
      case 0:
        v11 = 1;
        goto LABEL_35;
      case 1:
        if ( v12 )
        {
          v14 = 1;
          v15 = BparseInteger;
          v13 = (int)v6;
          goto LABEL_17;
        }
        v16 = BparseInteger(&v18, v6, 1, a5);
        goto LABEL_18;
      case 2:
        v16 = BparsePoint(&v18, v6, a5);
        goto LABEL_18;
      case 3:
        v16 = BparseRect(&v18, v6, a5);
        goto LABEL_18;
      case 4:
        v13 = (int)v6;
        if ( v12 )
        {
          v14 = 4;
          v15 = BparseQualifiedName;
LABEL_17:
          v16 = BparseList((unsigned int)&v18, v13, (_DWORD)v15, v14, (__int64)a5);
          goto LABEL_18;
        }
        v16 = BparseQualifiedName(&v18, v6, 4, a5);
        goto LABEL_18;
      case 5:
        v13 = (int)v6;
        if ( v12 )
        {
          v14 = 5;
          v15 = BparseQualifiedNameEx;
          goto LABEL_17;
        }
        v16 = BparseQualifiedNameEx(&v18, v6, 5, a5);
        goto LABEL_18;
      case 6:
        v13 = (int)v6;
        if ( v12 )
        {
          v14 = 6;
          v15 = BparsePartiallyQualifiedName;
          goto LABEL_17;
        }
        v16 = BparsePartiallyQualifiedName(&v18, v6, 6, a5);
LABEL_18:
        v11 = v16;
        if ( v16 )
        {
          if ( v19 )
          {
            if ( v12 )
              v10 = 68;
            v11 = (unsigned int)BwriteToHeap(a4, v6, (unsigned int)a5[v10 + 559], 4, a5) != 0 ? v16 : 0;
          }
          goto LABEL_35;
        }
        goto LABEL_34;
    }
  }
  if ( (unsigned int)(v10 - 25) <= 0x2A )
  {
    v13 = (int)v6;
    if ( v12 )
    {
      v14 = v10;
      v15 = BparseConstant;
      goto LABEL_17;
    }
    v16 = BparseConstant(&v18, v6, (unsigned int)v10, a5);
    goto LABEL_18;
  }
  if ( v10 == 22 )
  {
    v13 = (int)v6;
    if ( v12 )
    {
      v14 = 22;
      v15 = BparseOptionSymbol;
      goto LABEL_17;
    }
    v16 = BparseOptionSymbol(&v18, v6, 22, a5);
    goto LABEL_18;
  }
  if ( (unsigned int)(v10 - 17) <= 7 )
  {
    v13 = (int)v6;
    if ( v12 )
    {
      v14 = v10;
      v15 = BparseSymbol;
      goto LABEL_17;
    }
    v16 = BparseSymbol(&v18, v6, (unsigned int)v10, a5);
    goto LABEL_18;
  }
  WriteDbgTraceErrorGpd("BparseAndWrite", "internal consistency error - unrecognized VALUE type!");
LABEL_34:
  vIdentifySource(a2, a5);
LABEL_35:
  if ( v7 )
    LocalFree(v7);
  return v11;
}

```

## disassembly

```asm
0x18000aafc  mov     [rsp-38h+arg_0], rbx
0x18000ab01  mov     [rsp-38h+arg_18], r9
0x18000ab06  mov     [rsp-38h+arg_10], r8d
0x18000ab0b  push    rbp
0x18000ab0c  push    rsi
0x18000ab0d  push    rdi
0x18000ab0e  push    r12
0x18000ab10  push    r13
0x18000ab12  push    r14
0x18000ab14  push    r15
0x18000ab16  mov     rbp, rsp
0x18000ab19  sub     rsp, 40h
0x18000ab1d  mov     rax, r9
0x18000ab20  mov     r13, rdx
0x18000ab23  mov     rsi, rcx
0x18000ab26  movups  xmm0, xmmword ptr [rdx+18h]
0x18000ab2a  movdqu  [rbp+var_10], xmm0
0x18000ab2f  test    r8d, r8d
0x18000ab32  jnz     loc_18000AC4B
0x18000ab38  test    rcx, rcx
0x18000ab3b  jz      loc_18000AC73
0x18000ab41  mov     eax, [rdx]
0x18000ab43  lea     r14, mMainKeywordTable
0x18000ab4a  mov     rbx, [rbp+arg_20]
0x18000ab4e  xor     r12d, r12d
0x18000ab51  shl     rax, 5
0x18000ab55  mov     r15d, [rax+r14+0Ch]
0x18000ab5a  mov     r14d, [rax+r14+8]
0x18000ab5f  test    r8d, r8d
0x18000ab62  jz      short loc_18000AB82
0x18000ab64  mov     edx, [rbx+9D0h]; uBytes
0x18000ab6a  xor     ecx, ecx; uFlags
0x18000ab6c  call    cs:__imp_LocalAlloc
0x18000ab72  mov     r12, rax
0x18000ab75  test    rax, rax
0x18000ab78  jz      loc_18000AD2A
0x18000ab7e  mov     r8d, [rbp+arg_10]
0x18000ab82  mov     edx, 1
0x18000ab87  xor     edi, edi
0x18000ab89  and     r15d, edx
0x18000ab8c  test    r8d, r8d
0x18000ab8f  cmovnz  rsi, r12
0x18000ab93  lea     r10d, [rdx+3]
0x18000ab97  cmp     r14d, 7
0x18000ab9b  jg      loc_18000AC77
0x18000aba1  jz      loc_18000ACEA
0x18000aba7  mov     ecx, r14d
0x18000abaa  test    r14d, r14d
0x18000abad  jz      loc_18000ADF4
0x18000abb3  sub     ecx, edx
0x18000abb5  jz      loc_18000ADC6
0x18000abbb  sub     ecx, edx
0x18000abbd  jz      loc_18000ADB2
0x18000abc3  sub     ecx, edx
0x18000abc5  jz      loc_18000AD9E
0x18000abcb  sub     ecx, edx
0x18000abcd  jnz     loc_18000ACFE
0x18000abd3  lea     rcx, [rbp+var_10]
0x18000abd7  mov     rdx, rsi
0x18000abda  test    r15d, r15d
0x18000abdd  jz      loc_18000AD8E
0x18000abe3  mov     r9d, r10d
0x18000abe6  lea     r8, BparseQualifiedName
0x18000abed  mov     [rsp+40h+var_20], rbx
0x18000abf2  call    BparseList
0x18000abf7  mov     edi, eax
0x18000abf9  test    eax, eax
0x18000abfb  jz      loc_18000ACC0
0x18000ac01  test    r14d, r14d
0x18000ac04  jz      loc_18000ACCB
0x18000ac0a  cmp     [rbp+arg_10], 0
0x18000ac0e  jz      loc_18000ACCB
0x18000ac14  mov     rcx, [rbp+arg_18]
0x18000ac18  mov     eax, 44h ; 'D'
0x18000ac1d  test    r15d, r15d
0x18000ac20  mov     [rsp+40h+var_20], rbx
0x18000ac25  mov     rdx, rsi
0x18000ac28  cmovnz  r14d, eax
0x18000ac2c  movsxd  r8, r14d
0x18000ac2f  lea     r9d, [rax-40h]
0x18000ac33  mov     r8d, [rbx+r8*4+8BCh]
0x18000ac3b  call    BwriteToHeap
0x18000ac40  neg     eax
0x18000ac42  sbb     ecx, ecx
0x18000ac44  and     edi, ecx
0x18000ac46  jmp     loc_18000ACCB
0x18000ac4b  test    rax, rax
0x18000ac4e  jnz     loc_18000AB41
0x18000ac54  mov     rdx, [rbp+arg_20]
0x18000ac58  mov     rcx, r13
0x18000ac5b  call    vIdentifySource
0x18000ac60  lea     rdx, aInternalConsis; "internal consistency error.  heap ptr n"...
0x18000ac67  lea     rcx, aBparseandwrite; "BparseAndWrite"
0x18000ac6e  call    WriteDbgTraceErrorGpd
0x18000ac73  xor     eax, eax
0x18000ac75  jmp     short loc_18000ACD2
0x18000ac77  mov     ecx, r14d
0x18000ac7a  sub     ecx, 8
0x18000ac7d  jz      loc_18000AED8
0x18000ac83  sub     ecx, 2
0x18000ac86  jz      short loc_18000AC90
0x18000ac88  sub     ecx, edx
0x18000ac8a  jz      short loc_18000AC90
0x18000ac8c  sub     ecx, edx
0x18000ac8e  jnz     short loc_18000ACA7
0x18000ac90  mov     r9, rbx
0x18000ac93  lea     rcx, [rbp+var_10]
0x18000ac97  mov     r8d, r14d
0x18000ac9a  mov     rdx, rsi
0x18000ac9d  call    BparseAndTerminateString
0x18000aca2  jmp     loc_18000ABF7
0x18000aca7  sub     ecx, edx
0x18000aca9  jz      loc_18000AEC4
0x18000acaf  sub     ecx, 2
0x18000acb2  jz      loc_18000AEAE
0x18000acb8  cmp     ecx, edx
0x18000acba  jnz     loc_18000ADFB
0x18000acc0  mov     rdx, rbx
0x18000acc3  mov     rcx, r13
0x18000acc6  call    vIdentifySource
0x18000accb  test    r12, r12
0x18000acce  jnz     short loc_18000AD1F
0x18000acd0  mov     eax, edi
0x18000acd2  mov     rbx, [rsp+40h+arg_0]
0x18000acda  add     rsp, 40h
0x18000acde  pop     r15
0x18000ace0  pop     r14
0x18000ace2  pop     r13
0x18000ace4  pop     r12
0x18000ace6  pop     rdi
0x18000ace7  pop     rsi
0x18000ace8  pop     rbp
0x18000ace9  retn
0x18000acea  mov     r9, rbx
0x18000aced  lea     rcx, [rbp+var_10]
0x18000acf1  mov     rdx, rsi
0x18000acf4  call    BparseConstraint
0x18000acf9  jmp     loc_18000ABF7
0x18000acfe  sub     ecx, edx
0x18000ad00  jnz     short loc_18000AD43
0x18000ad02  lea     rcx, [rbp+var_10]
0x18000ad06  mov     rdx, rsi
0x18000ad09  test    r15d, r15d
0x18000ad0c  jnz     short loc_18000AD7C
0x18000ad0e  mov     r9, rbx
0x18000ad11  lea     r8d, [r15+5]
0x18000ad15  call    BparseQualifiedNameEx
0x18000ad1a  jmp     loc_18000ABF7
0x18000ad1f  mov     rcx, r12; hMem
0x18000ad22  call    cs:__imp_LocalFree
0x18000ad28  jmp     short loc_18000ACD0
0x18000ad2a  mov     dword ptr [rbx+8ACh], 3
0x18000ad34  mov     dword ptr [rbx+8B0h], 2
0x18000ad3e  jmp     loc_18000AC73
0x18000ad43  cmp     ecx, edx
0x18000ad45  jnz     loc_18000ADFB
0x18000ad4b  lea     rcx, [rbp+var_10]
0x18000ad4f  mov     rdx, rsi
0x18000ad52  test    r15d, r15d
0x18000ad55  jz      short loc_18000AD69
0x18000ad57  mov     r9d, 6
0x18000ad5d  lea     r8, BparsePartiallyQualifiedName
0x18000ad64  jmp     loc_18000ABED
0x18000ad69  mov     r9, rbx
0x18000ad6c  mov     r8d, 6
0x18000ad72  call    BparsePartiallyQualifiedName
0x18000ad77  jmp     loc_18000ABF7
0x18000ad7c  mov     r9d, 5
0x18000ad82  lea     r8, BparseQualifiedNameEx
0x18000ad89  jmp     loc_18000ABED
0x18000ad8e  mov     r9, rbx
0x18000ad91  mov     r8d, r10d
0x18000ad94  call    BparseQualifiedName
0x18000ad99  jmp     loc_18000ABF7
0x18000ad9e  mov     r8, rbx
0x18000ada1  lea     rcx, [rbp+var_10]
0x18000ada5  mov     rdx, rsi
0x18000ada8  call    BparseRect
0x18000adad  jmp     loc_18000ABF7
0x18000adb2  mov     r8, rbx
0x18000adb5  lea     rcx, [rbp+var_10]
0x18000adb9  mov     rdx, rsi
0x18000adbc  call    BparsePoint
0x18000adc1  jmp     loc_18000ABF7
0x18000adc6  lea     rcx, [rbp+var_10]
0x18000adca  test    r15d, r15d
0x18000adcd  jz      short loc_18000ADE1
0x18000adcf  mov     r9d, edx
0x18000add2  lea     r8, BparseInteger
0x18000add9  mov     rdx, rsi
0x18000addc  jmp     loc_18000ABED
0x18000ade1  mov     r8d, edx
0x18000ade4  mov     r9, rbx
0x18000ade7  mov     rdx, rsi
0x18000adea  call    BparseInteger
0x18000adef  jmp     loc_18000ABF7
0x18000adf4  mov     edi, edx
0x18000adf6  jmp     loc_18000ACCB
0x18000adfb  lea     eax, [r14-19h]
0x18000adff  cmp     eax, 2Ah ; '*'
0x18000ae02  ja      short loc_18000AE2F
0x18000ae04  lea     rcx, [rbp+var_10]
0x18000ae08  mov     rdx, rsi
0x18000ae0b  test    r15d, r15d
0x18000ae0e  jz      short loc_18000AE1F
0x18000ae10  mov     r9d, r14d
0x18000ae13  lea     r8, BparseConstant
0x18000ae1a  jmp     loc_18000ABED
0x18000ae1f  mov     r9, rbx
0x18000ae22  mov     r8d, r14d
0x18000ae25  call    BparseConstant
0x18000ae2a  jmp     loc_18000ABF7
0x18000ae2f  mov     r8d, 16h
0x18000ae35  cmp     r14d, r8d
0x18000ae38  jnz     short loc_18000AE62
0x18000ae3a  lea     rcx, [rbp+var_10]
0x18000ae3e  mov     rdx, rsi
0x18000ae41  test    r15d, r15d
0x18000ae44  jz      short loc_18000AE55
0x18000ae46  mov     r9d, r8d
0x18000ae49  lea     r8, BparseOptionSymbol
0x18000ae50  jmp     loc_18000ABED
0x18000ae55  mov     r9, rbx
0x18000ae58  call    BparseOptionSymbol
0x18000ae5d  jmp     loc_18000ABF7
0x18000ae62  lea     eax, [r14-11h]
0x18000ae66  cmp     eax, 7
0x18000ae69  ja      short loc_18000AE96
0x18000ae6b  lea     rcx, [rbp+var_10]
0x18000ae6f  mov     rdx, rsi
0x18000ae72  test    r15d, r15d
0x18000ae75  jz      short loc_18000AE86
0x18000ae77  mov     r9d, r14d
0x18000ae7a  lea     r8, BparseSymbol
0x18000ae81  jmp     loc_18000ABED
0x18000ae86  mov     r9, rbx
0x18000ae89  mov     r8d, r14d
0x18000ae8c  call    BparseSymbol
0x18000ae91  jmp     loc_18000ABF7
0x18000ae96  lea     rdx, aInternalConsis_1; "internal consistency error - unrecogniz"...
0x18000ae9d  lea     rcx, aBparseandwrite; "BparseAndWrite"
0x18000aea4  call    WriteDbgTraceErrorGpd
0x18000aea9  jmp     loc_18000ACC0
0x18000aeae  mov     r8, rbx
0x18000aeb1  mov     [rsi], edi
0x18000aeb3  mov     rdx, rsi
0x18000aeb6  lea     rcx, [rbp+var_10]
0x18000aeba  call    BprocessParam
0x18000aebf  jmp     loc_18000ABF7
0x18000aec4  mov     r8, rbx
0x18000aec7  lea     rcx, [rbp+var_10]
0x18000aecb  mov     rdx, rsi
0x18000aece  call    BparseCommandString
0x18000aed3  jmp     loc_18000ABF7
0x18000aed8  mov     r8, rbx
0x18000aedb  lea     rcx, [rbp+var_10]
0x18000aedf  mov     rdx, rsi
0x18000aee2  call    BparseOrderDep
0x18000aee7  jmp     loc_18000ABF7
```
