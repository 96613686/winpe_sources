# VerifyPKCS1SigningFormat

- ea: `0x180012a70`
- end: `0x180012cbd`
- name: `VerifyPKCS1SigningFormat`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180017420`

## callees

- `0x180004200`
- `0x180005060`
- `0x180007a7c`
- `0x180009430`
- `0x18000f6a8`
- `0x180012a70`
- `0x18001b791`
- `0x18001b79d`
- `0x18001b7a9`

## string_xrefs

- `0x180012ab9`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180012aee`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180012c01`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180012c7c`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall VerifyPKCS1SigningFormat(
        unsigned int a1,
        __int64 a2,
        const void *a3,
        unsigned int a4,
        void *Buf2,
        unsigned int Size,
        int a7)
{
  size_t v8; // r14
  _WORD *v10; // rax
  unsigned int v11; // r12d
  _WORD *v12; // rsi
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // edx
  int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // rcx

  v8 = a4;
  v10 = (_WORD *)SafeAllocaAllocateFromHeap(Size);
  v11 = 0;
  v12 = v10;
  if ( v10 )
  {
    if ( a7 )
    {
      v13 = -1073741595;
      while ( v11 < a1 )
      {
        memset_0(v12, 0, Size);
        v14 = ApplyPKCS1SigningFormat(
                *(void **)(a2 + 16LL * v11 + 8),
                *(unsigned int *)(a2 + 16LL * v11),
                (__int64)v12,
                Size,
                1);
        v13 = v14;
        if ( v14 < 0 )
        {
          v17 = (unsigned int)v14;
          goto LABEL_22;
        }
        if ( !memcmp_0(v12, Buf2, Size) )
        {
          v13 = 0;
          goto LABEL_23;
        }
        v13 = -1073700864;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v15,
            v16,
            (unsigned int)"Status",
            0,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c",
            219);
        ++v11;
      }
      goto LABEL_23;
    }
    memset_0(v10, 0, Size);
    if ( (unsigned int)v8 <= 0x80 )
    {
      if ( (int)v8 + 11 <= Size )
      {
        *v12 = 256;
        *((_BYTE *)v12 + Size - (unsigned int)v8 - 1) = 0;
        memset_0(v12 + 1, 255, Size - (unsigned int)v8 - 3);
        memcpy_0((char *)v12 + Size - (unsigned int)v8, a3, v8);
        if ( !memcmp_0(v12, Buf2, Size) )
        {
          v13 = 0;
LABEL_23:
          MSCryptFree(v12);
          return v13;
        }
        v13 = -1073700864;
        v17 = 3221266432LL;
LABEL_22:
        DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
        goto LABEL_23;
      }
      v13 = -1073741811;
      v18 = 3221225485LL;
    }
    else
    {
      v13 = -1073741595;
      v18 = 3221225701LL;
    }
    DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
    v17 = v13;
    goto LABEL_22;
  }
  v13 = -1073741801;
  DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
  return v13;
}

```

## disassembly

```asm
0x180012a70  mov     [rsp+arg_0], rbx
0x180012a75  mov     [rsp+arg_10], r8
0x180012a7a  mov     [rsp+arg_8], rdx
0x180012a7f  push    rbp
0x180012a80  push    rsi
0x180012a81  push    rdi
0x180012a82  push    r12
0x180012a84  push    r13
0x180012a86  push    r14
0x180012a88  push    r15
0x180012a8a  sub     rsp, 40h
0x180012a8e  mov     ebp, dword ptr [rsp+78h+Size]
0x180012a95  mov     r13d, ecx
0x180012a98  mov     ecx, ebp
0x180012a9a  mov     r14d, r9d
0x180012a9d  mov     rdi, r8
0x180012aa0  mov     r15d, ebp
0x180012aa3  call    SafeAllocaAllocateFromHeap
0x180012aa8  xor     r12d, r12d
0x180012aab  mov     rsi, rax
0x180012aae  test    rax, rax
0x180012ab1  jnz     short loc_180012ADB
0x180012ab3  mov     r9d, 0B8h
0x180012ab9  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012ac0  lea     rdx, aStatus; "Status"
0x180012ac7  mov     ecx, 0C0000017h
0x180012acc  mov     ebx, 0C0000017h
0x180012ad1  call    DebugTraceError
0x180012ad6  jmp     loc_180012CA2
0x180012adb  cmp     [rsp+78h+arg_30], r12d
0x180012ae3  jz      loc_180012BC1
0x180012ae9  mov     ebx, 0C00000E5h
0x180012aee  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012af5  cmp     r12d, r13d
0x180012af8  jnb     loc_180012C9A
0x180012afe  mov     r8, r15; Size
0x180012b01  xor     edx, edx; Val
0x180012b03  mov     rcx, rsi; void *
0x180012b06  call    memset_0
0x180012b0b  mov     rax, [rsp+78h+arg_8]
0x180012b13  mov     r9d, r14d
0x180012b16  mov     r8, [rsp+78h+arg_10]
0x180012b1e  mov     [rsp+78h+var_48], 1; int
0x180012b26  mov     ecx, r12d
0x180012b29  add     rcx, rcx
0x180012b2c  mov     [rsp+78h+var_50], ebp; int
0x180012b30  mov     [rsp+78h+var_58], rsi; __int64
0x180012b35  mov     edx, [rax+rcx*8]; Size
0x180012b38  mov     rcx, [rax+rcx*8+8]; Src
0x180012b3d  call    ApplyPKCS1SigningFormat
0x180012b42  mov     ebx, eax
0x180012b44  test    eax, eax
0x180012b46  js      short loc_180012BB1
0x180012b48  mov     rdx, [rsp+78h+Buf2]; Buf2
0x180012b50  mov     r8, r15; Size
0x180012b53  mov     rcx, rsi; Buf1
0x180012b56  call    memcmp_0
0x180012b5b  test    eax, eax
0x180012b5d  jz      short loc_180012BAA
0x180012b5f  mov     ebx, 0C000A000h
0x180012b64  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b6b  lea     rax, WPP_GLOBAL_Control
0x180012b72  cmp     rcx, rax
0x180012b75  jz      short loc_180012BA2
0x180012b77  test    byte ptr [rcx+1Ch], 1
0x180012b7b  jz      short loc_180012BA2
0x180012b7d  mov     rcx, [rcx+10h]
0x180012b81  lea     r9, aStatus; "Status"
0x180012b88  mov     [rsp+78h+var_48], 0DBh
0x180012b90  mov     qword ptr [rsp+78h+var_50], rdi
0x180012b95  mov     dword ptr [rsp+78h+var_58], 0C000A000h
0x180012b9d  call    WPP_SF_sDsd
0x180012ba2  inc     r12d
0x180012ba5  jmp     loc_180012AF5
0x180012baa  xor     ebx, ebx
0x180012bac  jmp     loc_180012C9A
0x180012bb1  mov     r9d, 0CEh
0x180012bb7  mov     r8, rdi
0x180012bba  mov     ecx, eax
0x180012bbc  jmp     loc_180012C8E
0x180012bc1  mov     r8, r15; Size
0x180012bc4  xor     edx, edx; Val
0x180012bc6  mov     rcx, rsi; void *
0x180012bc9  call    memset_0
0x180012bce  cmp     r14d, 80h
0x180012bd5  jbe     short loc_180012BE9
0x180012bd7  mov     ebx, 0C00000E5h
0x180012bdc  mov     ecx, 0C00000E5h
0x180012be1  mov     r9d, 5Fh ; '_'
0x180012be7  jmp     short loc_180012C01
0x180012be9  lea     eax, [r14+0Bh]
0x180012bed  cmp     eax, ebp
0x180012bef  jbe     short loc_180012C24
0x180012bf1  mov     ebx, 0C000000Dh
0x180012bf6  mov     ecx, 0C000000Dh
0x180012bfb  mov     r9d, 69h ; 'i'
0x180012c01  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012c08  mov     r8, rdi
0x180012c0b  lea     rdx, aStatus; "Status"
0x180012c12  call    DebugTraceError
0x180012c17  mov     r9d, 0ECh
0x180012c1d  mov     r8, rdi
0x180012c20  mov     ecx, ebx
0x180012c22  jmp     short loc_180012C8E
0x180012c24  mov     word ptr [rsi], 100h
0x180012c29  lea     rcx, [rsi+2]; void *
0x180012c2d  sub     ebp, r14d
0x180012c30  lea     edx, [rbp-3]
0x180012c33  lea     eax, [rdx+2]
0x180012c36  mov     ebx, edx
0x180012c38  mov     r8d, edx; Size
0x180012c3b  mov     edx, 0FFh; Val
0x180012c40  mov     [rax+rsi], r12b
0x180012c44  call    memset_0
0x180012c49  lea     rcx, [rbx+3]
0x180012c4d  mov     r8, r14; Size
0x180012c50  add     rcx, rsi; void *
0x180012c53  mov     rdx, rdi; Src
0x180012c56  call    memcpy_0
0x180012c5b  mov     rdx, [rsp+78h+Buf2]; Buf2
0x180012c63  mov     r8, r15; Size
0x180012c66  mov     rcx, rsi; Buf1
0x180012c69  call    memcmp_0
0x180012c6e  test    eax, eax
0x180012c70  jnz     short loc_180012C77
0x180012c72  mov     ebx, r12d
0x180012c75  jmp     short loc_180012C9A
0x180012c77  mov     ebx, 0C000A000h
0x180012c7c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012c83  mov     r9d, 0F8h
0x180012c89  mov     ecx, 0C000A000h
0x180012c8e  lea     rdx, aStatus; "Status"
0x180012c95  call    DebugTraceError
0x180012c9a  mov     rcx, rsi
0x180012c9d  call    MSCryptFree
0x180012ca2  mov     eax, ebx
0x180012ca4  mov     rbx, [rsp+78h+arg_0]
0x180012cac  add     rsp, 40h
0x180012cb0  pop     r15
0x180012cb2  pop     r14
0x180012cb4  pop     r13
0x180012cb6  pop     r12
0x180012cb8  pop     rdi
0x180012cb9  pop     rsi
0x180012cba  pop     rbp
0x180012cbb  retn
```
