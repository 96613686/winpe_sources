# ExportFullRsaKey

- ea: `0x18000e628`
- end: `0x18000e7f3`
- name: `ExportFullRsaKey`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009ba0`

## callees

- `0x180004200`
- `0x180005060`
- `0x180007a7c`
- `0x180009430`
- `0x18000bac0`
- `0x18000e628`
- `0x18001c010`

## string_xrefs

- `0x18000e67e`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`
- `0x18000e727`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`
- `0x18000e799`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ExportFullRsaKey(
        __int64 (__fastcall *a1)(__int64, __int64, const wchar_t *),
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        int a7)
{
  unsigned int v11; // ebx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdi
  int v16; // eax
  _DWORD v18[22]; // [rsp+40h] [rbp-58h] BYREF

  v18[0] = 0;
  if ( a7 )
  {
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
        203);
    return v11;
  }
  v11 = a1(a2, a3, L"RSAFULLPRIVATEBLOB");
  if ( (v11 & 0x80000000) == 0 )
    return v11;
  v12 = ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *, _QWORD, _DWORD, _DWORD *, _DWORD))a1)(
          a2,
          a3,
          L"RSAPRIVATEBLOB",
          0,
          0,
          v18,
          0);
  v11 = v12;
  if ( v12 < 0 )
  {
    v13 = (unsigned int)v12;
LABEL_8:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
    return v11;
  }
  v14 = SafeAllocaAllocateFromHeap(v18[0]);
  v15 = v14;
  if ( !v14 )
  {
    v11 = -1073741801;
    v13 = 3221225495LL;
    goto LABEL_8;
  }
  v16 = ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *, __int64, _DWORD, _DWORD *, _DWORD))a1)(
          a2,
          a3,
          L"RSAPRIVATEBLOB",
          v14,
          v18[0],
          v18,
          0);
  v11 = v16;
  if ( v16 < 0 || (v16 = ConvertRsaPrivateBlobToFullRsa(v15, v18[0], a4, a5, a6), v11 = v16, v16 < 0) )
    DebugTraceError(
      (unsigned int)v16,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
  else
    v11 = 0;
  MSCryptFree(v15);
  return v11;
}

```

## disassembly

```asm
0x18000e628  push    rbx
0x18000e62a  push    rbp
0x18000e62b  push    rsi
0x18000e62c  push    rdi
0x18000e62d  push    r12
0x18000e62f  push    r13
0x18000e631  push    r14
0x18000e633  push    r15
0x18000e635  sub     rsp, 58h
0x18000e639  xor     edi, edi
0x18000e63b  mov     r15, r9
0x18000e63e  mov     rsi, r8
0x18000e641  mov     rbp, rdx
0x18000e644  mov     r14, rcx
0x18000e647  mov     [rsp+98h+var_58], edi
0x18000e64b  cmp     [rsp+98h+arg_30], edi
0x18000e652  jz      short loc_18000E6AB
0x18000e654  mov     ebx, 0C000000Dh
0x18000e659  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e660  lea     rax, WPP_GLOBAL_Control
0x18000e667  cmp     rcx, rax
0x18000e66a  jz      loc_18000E7DF
0x18000e670  test    byte ptr [rcx+1Ch], 1
0x18000e674  jz      loc_18000E7DF
0x18000e67a  mov     rcx, [rcx+10h]
0x18000e67e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e685  mov     [rsp+98h+var_68], 3CBh
0x18000e68d  lea     r9, aStatus; "Status"
0x18000e694  mov     [rsp+98h+var_70], r8
0x18000e699  mov     dword ptr [rsp+98h+var_78], 0C000000Dh
0x18000e6a1  call    WPP_SF_sDsd
0x18000e6a6  jmp     loc_18000E7DF
0x18000e6ab  mov     r12, [rsp+98h+arg_28]
0x18000e6b3  lea     r8, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x18000e6ba  mov     r13d, [rsp+98h+arg_20]
0x18000e6c2  mov     rdx, rsi
0x18000e6c5  mov     [rsp+98h+var_68], edi
0x18000e6c9  mov     rcx, rbp
0x18000e6cc  mov     [rsp+98h+var_70], r12
0x18000e6d1  mov     rax, r14
0x18000e6d4  mov     dword ptr [rsp+98h+var_78], r13d
0x18000e6d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6de  mov     ebx, eax
0x18000e6e0  test    eax, eax
0x18000e6e2  jns     loc_18000E7DF
0x18000e6e8  lea     rax, [rsp+98h+var_58]
0x18000e6ed  mov     [rsp+98h+var_68], edi
0x18000e6f1  mov     [rsp+98h+var_70], rax
0x18000e6f6  lea     r8, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18000e6fd  mov     rax, r14
0x18000e700  mov     dword ptr [rsp+98h+var_78], edi
0x18000e704  xor     r9d, r9d
0x18000e707  mov     rdx, rsi
0x18000e70a  mov     rcx, rbp
0x18000e70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e712  mov     ebx, eax
0x18000e714  test    eax, eax
0x18000e716  jns     short loc_18000E738
0x18000e718  mov     r9d, 3ECh
0x18000e71e  mov     ecx, eax
0x18000e720  lea     rdx, aStatus; "Status"
0x18000e727  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e72e  call    DebugTraceError
0x18000e733  jmp     loc_18000E7DF
0x18000e738  mov     ecx, [rsp+98h+var_58]
0x18000e73c  call    SafeAllocaAllocateFromHeap
0x18000e741  mov     rdi, rax
0x18000e744  test    rax, rax
0x18000e747  jnz     short loc_18000E75B
0x18000e749  mov     ebx, 0C0000017h
0x18000e74e  mov     r9d, 3F4h
0x18000e754  mov     ecx, 0C0000017h
0x18000e759  jmp     short loc_18000E720
0x18000e75b  lea     rax, [rsp+98h+var_58]
0x18000e760  mov     [rsp+98h+var_68], 0
0x18000e768  mov     [rsp+98h+var_70], rax
0x18000e76d  lea     r8, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18000e774  mov     eax, [rsp+98h+var_58]
0x18000e778  mov     r9, rdi
0x18000e77b  mov     dword ptr [rsp+98h+var_78], eax
0x18000e77f  mov     rdx, rsi
0x18000e782  mov     rax, r14
0x18000e785  mov     rcx, rbp
0x18000e788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e78d  mov     ebx, eax
0x18000e78f  test    eax, eax
0x18000e791  jns     short loc_18000E7B0
0x18000e793  mov     r9d, 402h
0x18000e799  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e7a0  mov     ecx, eax
0x18000e7a2  lea     rdx, aStatus; "Status"
0x18000e7a9  call    DebugTraceError
0x18000e7ae  jmp     short loc_18000E7D7
0x18000e7b0  mov     edx, [rsp+98h+var_58]
0x18000e7b4  mov     r9d, r13d
0x18000e7b7  mov     r8, r15
0x18000e7ba  mov     [rsp+98h+var_78], r12
0x18000e7bf  mov     rcx, rdi
0x18000e7c2  call    ConvertRsaPrivateBlobToFullRsa
0x18000e7c7  mov     ebx, eax
0x18000e7c9  test    eax, eax
0x18000e7cb  jns     short loc_18000E7D5
0x18000e7cd  mov     r9d, 413h
0x18000e7d3  jmp     short loc_18000E799
0x18000e7d5  xor     ebx, ebx
0x18000e7d7  mov     rcx, rdi
0x18000e7da  call    MSCryptFree
0x18000e7df  mov     eax, ebx
0x18000e7e1  add     rsp, 58h
0x18000e7e5  pop     r15
0x18000e7e7  pop     r14
0x18000e7e9  pop     r13
0x18000e7eb  pop     r12
0x18000e7ed  pop     rdi
0x18000e7ee  pop     rsi
0x18000e7ef  pop     rbp
0x18000e7f0  pop     rbx
0x18000e7f1  retn
```
