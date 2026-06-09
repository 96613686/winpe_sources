# BparseAndWrite

- ea: `0x18000aafc`
- end: `0x18000aef9`
- name: `BparseAndWrite`
- size: `1021`
- prototype: `__int64 __fastcall(int *, unsigned int *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18000a828`

## callees

- `0x180007150`
- `0x180008a30`
- `0x180009330`
- `0x180009e30`
- `0x18000aafc`
- `0x18000af00`
- `0x18000afac`
- `0x18000b0ac`
- `0x18000b518`
- `0x18000b5f0`
- `0x18000bce0`
- `0x18000bdbc`
- `0x18000bf20`
- `0x180040390`
- `0x180045aa4`
- `0x1800741f0`
- `0x1800742e0`
- `0x180074404`
- `0x1800745c8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000ad29`
- `KERNEL32!LocalFree` at `0x18000ad29`
- `KERNEL32!LocalAlloc` at `0x18000ab6c`
- `KERNEL32!LocalAlloc` at `0x18000ab6c`

## string_xrefs

- `0x18000ac6d`: `BparseAndWrite`
- `0x18000aeaa`: `BparseAndWrite`

## pseudocode

```c
__int64 __fastcall BparseAndWrite(int *a1, unsigned int *a2, __int64 a3, _DWORD *a4, _DWORD *a5)
{
  int *v6; // rsi
  int *v7; // r12
  __int64 v8; // rax
  int v9; // r15d
  int v10; // r14d
  unsigned int v11; // edi
  int v12; // r15d
  int *v13; // rdx
  unsigned int v14; // r9d
  unsigned int (__fastcall *v15)(__int128 *, __int64, _QWORD, __int64); // r8
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
    vIdentifySource(a2, (__int64)a5, a3);
    WriteDbgTraceErrorGpd((__int64)"BparseAndWrite", "internal consistency error.  heap ptr not supplied.");
    return 0;
  }
LABEL_3:
  v7 = 0;
  v8 = 4LL * *a2;
  v9 = *((_DWORD *)&mMainKeywordTable + 2 * v8 + 3);
  v10 = (int)(&mMainKeywordTable)[v8 + 1];
  if ( !(_DWORD)a3 )
    goto LABEL_6;
  v7 = (int *)LocalAlloc(0, (unsigned int)a5[628]);
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
        v16 = BparseOrderDep((__int64)&v18, v6, (__int64)a5);
        goto LABEL_18;
      case 10:
      case 11:
      case 12:
        v16 = BparseAndTerminateString((const char **)&v18, v6, v10, a5);
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
        v16 = BparseConstraint((__int64)&v18, v6, a3, (__int64)a5);
        goto LABEL_18;
      case 0:
        v11 = 1;
        goto LABEL_35;
      case 1:
        if ( v12 )
        {
          v14 = 1;
          v15 = (unsigned int (__fastcall *)(__int128 *, __int64, _QWORD, __int64))BparseInteger;
          v13 = v6;
          goto LABEL_17;
        }
        v16 = BparseInteger((__int64)&v18, (unsigned int *)v6, 1);
        goto LABEL_18;
      case 2:
        v16 = BparsePoint((__int64)&v18, (__int64)v6);
        goto LABEL_18;
      case 3:
        v16 = BparseRect((__int64)&v18, (__int64)v6);
        goto LABEL_18;
      case 4:
        v13 = v6;
        if ( v12 )
        {
          v14 = 4;
          v15 = (unsigned int (__fastcall *)(__int128 *, __int64, _QWORD, __int64))BparseQualifiedName;
LABEL_17:
          v16 = BparseList((__int64)&v18, v13, v15, v14, (__int64)a5);
          goto LABEL_18;
        }
        v16 = BparseQualifiedName(&v18, v6, 4, (__int64)a5);
        goto LABEL_18;
      case 5:
        v13 = v6;
        if ( v12 )
        {
          v14 = 5;
          v15 = (unsigned int (__fastcall *)(__int128 *, __int64, _QWORD, __int64))BparseQualifiedNameEx;
          goto LABEL_17;
        }
        v16 = BparseQualifiedNameEx(&v18, (__int64)v6, 5, (__int64)a5);
        goto LABEL_18;
      case 6:
        v13 = v6;
        if ( v12 )
        {
          v14 = 6;
          v15 = (unsigned int (__fastcall *)(__int128 *, __int64, _QWORD, __int64))BparsePartiallyQualifiedName;
          goto LABEL_17;
        }
        v16 = BparsePartiallyQualifiedName(&v18, v6, 6, (__int64)a5);
LABEL_18:
        v11 = v16;
        if ( v16 )
        {
          if ( v19 )
          {
            if ( v12 )
              v10 = 68;
            v11 = (unsigned int)BwriteToHeap(a4, v6, a5[v10 + 559], 4u, (__int64)a5) != 0 ? v16 : 0;
          }
          goto LABEL_35;
        }
        goto LABEL_34;
    }
  }
  if ( (unsigned int)(v10 - 25) <= 0x2A )
  {
    v13 = v6;
    if ( v12 )
    {
      v14 = v10;
      v15 = (unsigned int (__fastcall *)(__int128 *, __int64, _QWORD, __int64))BparseConstant;
      goto LABEL_17;
    }
    v16 = BparseConstant((const char **)&v18, v6, v10, (__int64)a5);
    goto LABEL_18;
  }
  if ( v10 == 22 )
  {
    v13 = v6;
    if ( v12 )
    {
      v14 = 22;
      v15 = (unsigned int (__fastcall *)(__int128 *, __int64, _QWORD, __int64))BparseOptionSymbol;
      goto LABEL_17;
    }
    v16 = BparseOptionSymbol((__int64)&v18, v6, 22, (__int64)a5);
    goto LABEL_18;
  }
  if ( (unsigned int)(v10 - 17) <= 7 )
  {
    v13 = v6;
    if ( v12 )
    {
      v14 = v10;
      v15 = (unsigned int (__fastcall *)(__int128 *, __int64, _QWORD, __int64))BparseSymbol;
      goto LABEL_17;
    }
    v16 = BparseSymbol((__int64)&v18, v6, v10, (__int64)a5);
    goto LABEL_18;
  }
  WriteDbgTraceErrorGpd((__int64)"BparseAndWrite", "internal consistency error - unrecognized VALUE type!");
LABEL_34:
  vIdentifySource(a2, (__int64)a5, a3);
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
0x18000ab32  jnz     loc_18000AC51
0x18000ab38  test    rcx, rcx
0x18000ab3b  jz      loc_18000AC79
0x18000ab41  mov     eax, [rdx]
0x18000ab43  lea     r14, mMainKeywordTable
0x18000ab4a  mov     rbx, [rbp+arg_20]
0x18000ab4e  xor     r12d, r12d
0x18000ab51  shl     rax, 5
0x18000ab55  mov     r15d, [rax+r14+0Ch]
0x18000ab5a  mov     r14d, [rax+r14+8]
0x18000ab5f  test    r8d, r8d
0x18000ab62  jz      short loc_18000AB88
0x18000ab64  mov     edx, [rbx+9D0h]; uBytes
0x18000ab6a  xor     ecx, ecx; uFlags
0x18000ab6c  call    cs:__imp_LocalAlloc
0x18000ab73  nop     dword ptr [rax+rax+00h]
0x18000ab78  mov     r12, rax
0x18000ab7b  test    rax, rax
0x18000ab7e  jz      loc_18000AD37
0x18000ab84  mov     r8d, [rbp+arg_10]
0x18000ab88  mov     edx, 1
0x18000ab8d  xor     edi, edi
0x18000ab8f  and     r15d, edx
0x18000ab92  test    r8d, r8d
0x18000ab95  cmovnz  rsi, r12
0x18000ab99  lea     r10d, [rdx+3]
0x18000ab9d  cmp     r14d, 7
0x18000aba1  jg      loc_18000AC7D
0x18000aba7  jz      loc_18000ACF1
0x18000abad  mov     ecx, r14d
0x18000abb0  test    r14d, r14d
0x18000abb3  jz      loc_18000AE01
0x18000abb9  sub     ecx, edx
0x18000abbb  jz      loc_18000ADD3
0x18000abc1  sub     ecx, edx
0x18000abc3  jz      loc_18000ADBF
0x18000abc9  sub     ecx, edx
0x18000abcb  jz      loc_18000ADAB
0x18000abd1  sub     ecx, edx
0x18000abd3  jnz     loc_18000AD05
0x18000abd9  lea     rcx, [rbp+var_10]
0x18000abdd  mov     rdx, rsi
0x18000abe0  test    r15d, r15d
0x18000abe3  jz      loc_18000AD9B
0x18000abe9  mov     r9d, r10d
0x18000abec  lea     r8, BparseQualifiedName
0x18000abf3  mov     [rsp+40h+var_20], rbx
0x18000abf8  call    BparseList
0x18000abfd  mov     edi, eax
0x18000abff  test    eax, eax
0x18000ac01  jz      loc_18000ACC6
0x18000ac07  test    r14d, r14d
0x18000ac0a  jz      loc_18000ACD1
0x18000ac10  cmp     [rbp+arg_10], 0
0x18000ac14  jz      loc_18000ACD1
0x18000ac1a  mov     rcx, [rbp+arg_18]
0x18000ac1e  mov     eax, 44h ; 'D'
0x18000ac23  test    r15d, r15d
0x18000ac26  mov     [rsp+40h+var_20], rbx
0x18000ac2b  mov     rdx, rsi
0x18000ac2e  cmovnz  r14d, eax
0x18000ac32  movsxd  r8, r14d
0x18000ac35  lea     r9d, [rax-40h]
0x18000ac39  mov     r8d, [rbx+r8*4+8BCh]
0x18000ac41  call    BwriteToHeap
0x18000ac46  neg     eax
0x18000ac48  sbb     ecx, ecx
0x18000ac4a  and     edi, ecx
0x18000ac4c  jmp     loc_18000ACD1
0x18000ac51  test    rax, rax
0x18000ac54  jnz     loc_18000AB41
0x18000ac5a  mov     rdx, [rbp+arg_20]
0x18000ac5e  mov     rcx, r13
0x18000ac61  call    vIdentifySource
0x18000ac66  lea     rdx, aInternalConsis; "internal consistency error.  heap ptr n"...
0x18000ac6d  lea     rcx, aBparseandwrite; "BparseAndWrite"
0x18000ac74  call    WriteDbgTraceErrorGpd
0x18000ac79  xor     eax, eax
0x18000ac7b  jmp     short loc_18000ACD8
0x18000ac7d  mov     ecx, r14d
0x18000ac80  sub     ecx, 8
0x18000ac83  jz      loc_18000AEE5
0x18000ac89  sub     ecx, 2
0x18000ac8c  jz      short loc_18000AC96
0x18000ac8e  sub     ecx, edx
0x18000ac90  jz      short loc_18000AC96
0x18000ac92  sub     ecx, edx
0x18000ac94  jnz     short loc_18000ACAD
0x18000ac96  mov     r9, rbx
0x18000ac99  lea     rcx, [rbp+var_10]
0x18000ac9d  mov     r8d, r14d
0x18000aca0  mov     rdx, rsi
0x18000aca3  call    BparseAndTerminateString
0x18000aca8  jmp     loc_18000ABFD
0x18000acad  sub     ecx, edx
0x18000acaf  jz      loc_18000AED1
0x18000acb5  sub     ecx, 2
0x18000acb8  jz      loc_18000AEBB
0x18000acbe  cmp     ecx, edx
0x18000acc0  jnz     loc_18000AE08
0x18000acc6  mov     rdx, rbx
0x18000acc9  mov     rcx, r13
0x18000accc  call    vIdentifySource
0x18000acd1  test    r12, r12
0x18000acd4  jnz     short loc_18000AD26
0x18000acd6  mov     eax, edi
0x18000acd8  mov     rbx, [rsp+40h+arg_0]
0x18000ace0  add     rsp, 40h
0x18000ace4  pop     r15
0x18000ace6  pop     r14
0x18000ace8  pop     r13
0x18000acea  pop     r12
0x18000acec  pop     rdi
0x18000aced  pop     rsi
0x18000acee  pop     rbp
0x18000acef  retn
0x18000acf1  mov     r9, rbx
0x18000acf4  lea     rcx, [rbp+var_10]
0x18000acf8  mov     rdx, rsi
0x18000acfb  call    BparseConstraint
0x18000ad00  jmp     loc_18000ABFD
0x18000ad05  sub     ecx, edx
0x18000ad07  jnz     short loc_18000AD50
0x18000ad09  lea     rcx, [rbp+var_10]
0x18000ad0d  mov     rdx, rsi
0x18000ad10  test    r15d, r15d
0x18000ad13  jnz     short loc_18000AD89
0x18000ad15  mov     r9, rbx
0x18000ad18  lea     r8d, [r15+5]
0x18000ad1c  call    BparseQualifiedNameEx
0x18000ad21  jmp     loc_18000ABFD
0x18000ad26  mov     rcx, r12; hMem
0x18000ad29  call    cs:__imp_LocalFree
0x18000ad30  nop     dword ptr [rax+rax+00h]
0x18000ad35  jmp     short loc_18000ACD6
0x18000ad37  mov     dword ptr [rbx+8ACh], 3
0x18000ad41  mov     dword ptr [rbx+8B0h], 2
0x18000ad4b  jmp     loc_18000AC79
0x18000ad50  cmp     ecx, edx
0x18000ad52  jnz     loc_18000AE08
0x18000ad58  lea     rcx, [rbp+var_10]
0x18000ad5c  mov     rdx, rsi
0x18000ad5f  test    r15d, r15d
0x18000ad62  jz      short loc_18000AD76
0x18000ad64  mov     r9d, 6
0x18000ad6a  lea     r8, BparsePartiallyQualifiedName
0x18000ad71  jmp     loc_18000ABF3
0x18000ad76  mov     r9, rbx
0x18000ad79  mov     r8d, 6
0x18000ad7f  call    BparsePartiallyQualifiedName
0x18000ad84  jmp     loc_18000ABFD
0x18000ad89  mov     r9d, 5
0x18000ad8f  lea     r8, BparseQualifiedNameEx
0x18000ad96  jmp     loc_18000ABF3
0x18000ad9b  mov     r9, rbx
0x18000ad9e  mov     r8d, r10d
0x18000ada1  call    BparseQualifiedName
0x18000ada6  jmp     loc_18000ABFD
0x18000adab  mov     r8, rbx
0x18000adae  lea     rcx, [rbp+var_10]
0x18000adb2  mov     rdx, rsi
0x18000adb5  call    BparseRect
0x18000adba  jmp     loc_18000ABFD
0x18000adbf  mov     r8, rbx
0x18000adc2  lea     rcx, [rbp+var_10]
0x18000adc6  mov     rdx, rsi
0x18000adc9  call    BparsePoint
0x18000adce  jmp     loc_18000ABFD
0x18000add3  lea     rcx, [rbp+var_10]
0x18000add7  test    r15d, r15d
0x18000adda  jz      short loc_18000ADEE
0x18000addc  mov     r9d, edx
0x18000addf  lea     r8, BparseInteger
0x18000ade6  mov     rdx, rsi
0x18000ade9  jmp     loc_18000ABF3
0x18000adee  mov     r8d, edx
0x18000adf1  mov     r9, rbx
0x18000adf4  mov     rdx, rsi
0x18000adf7  call    BparseInteger
0x18000adfc  jmp     loc_18000ABFD
0x18000ae01  mov     edi, edx
0x18000ae03  jmp     loc_18000ACD1
0x18000ae08  lea     eax, [r14-19h]
0x18000ae0c  cmp     eax, 2Ah ; '*'
0x18000ae0f  ja      short loc_18000AE3C
0x18000ae11  lea     rcx, [rbp+var_10]
0x18000ae15  mov     rdx, rsi
0x18000ae18  test    r15d, r15d
0x18000ae1b  jz      short loc_18000AE2C
0x18000ae1d  mov     r9d, r14d
0x18000ae20  lea     r8, BparseConstant
0x18000ae27  jmp     loc_18000ABF3
0x18000ae2c  mov     r9, rbx
0x18000ae2f  mov     r8d, r14d
0x18000ae32  call    BparseConstant
0x18000ae37  jmp     loc_18000ABFD
0x18000ae3c  mov     r8d, 16h
0x18000ae42  cmp     r14d, r8d
0x18000ae45  jnz     short loc_18000AE6F
0x18000ae47  lea     rcx, [rbp+var_10]
0x18000ae4b  mov     rdx, rsi
0x18000ae4e  test    r15d, r15d
0x18000ae51  jz      short loc_18000AE62
0x18000ae53  mov     r9d, r8d
0x18000ae56  lea     r8, BparseOptionSymbol
0x18000ae5d  jmp     loc_18000ABF3
0x18000ae62  mov     r9, rbx
0x18000ae65  call    BparseOptionSymbol
0x18000ae6a  jmp     loc_18000ABFD
0x18000ae6f  lea     eax, [r14-11h]
0x18000ae73  cmp     eax, 7
0x18000ae76  ja      short loc_18000AEA3
0x18000ae78  lea     rcx, [rbp+var_10]
0x18000ae7c  mov     rdx, rsi
0x18000ae7f  test    r15d, r15d
0x18000ae82  jz      short loc_18000AE93
0x18000ae84  mov     r9d, r14d
0x18000ae87  lea     r8, BparseSymbol
0x18000ae8e  jmp     loc_18000ABF3
0x18000ae93  mov     r9, rbx
0x18000ae96  mov     r8d, r14d
0x18000ae99  call    BparseSymbol
0x18000ae9e  jmp     loc_18000ABFD
0x18000aea3  lea     rdx, aInternalConsis_1; "internal consistency error - unrecogniz"...
0x18000aeaa  lea     rcx, aBparseandwrite; "BparseAndWrite"
0x18000aeb1  call    WriteDbgTraceErrorGpd
0x18000aeb6  jmp     loc_18000ACC6
0x18000aebb  mov     r8, rbx
0x18000aebe  mov     [rsi], edi
0x18000aec0  mov     rdx, rsi
0x18000aec3  lea     rcx, [rbp+var_10]
0x18000aec7  call    BprocessParam
0x18000aecc  jmp     loc_18000ABFD
0x18000aed1  mov     r8, rbx
0x18000aed4  lea     rcx, [rbp+var_10]
0x18000aed8  mov     rdx, rsi
0x18000aedb  call    BparseCommandString
0x18000aee0  jmp     loc_18000ABFD
0x18000aee5  mov     r8, rbx
0x18000aee8  lea     rcx, [rbp+var_10]
0x18000aeec  mov     rdx, rsi
0x18000aeef  call    BparseOrderDep
0x18000aef4  jmp     loc_18000ABFD
```
