# MaskGeneration

- ea: `0x180012cc4`
- end: `0x180012f36`
- name: `MaskGeneration`
- size: `626`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180016564`
- `0x1800168c8`
- `0x180016efc`
- `0x1800171b4`

## callees

- `0x180004200`
- `0x180005060`
- `0x180006020`
- `0x180006da0`
- `0x1800078e0`
- `0x180007a7c`
- `0x180009430`
- `0x18000cc10`
- `0x180012cc4`
- `0x18001b79d`

## string_xrefs

- `0x180012d51`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180012ee9`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180012f21`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 MaskGeneration(void *a1, unsigned int a2, ULONG a3, UCHAR *a4, ULONG cbInput, PUCHAR pbOutput, ...)
{
  unsigned int v6; // r15d
  __int64 v7; // rdi
  ULONG v8; // ebx
  unsigned int v9; // r13d
  UCHAR *v10; // rsi
  int v11; // r8d
  NTSTATUS v12; // ebx
  UCHAR *v13; // r12
  unsigned int i; // r14d
  int v15; // r8d
  NTSTATUS v16; // eax
  __int64 j; // rcx
  UCHAR *v18; // r14
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-18h] BYREF
  int v22; // [rsp+A8h] [rbp+50h]
  ULONG v23; // [rsp+B0h] [rbp+58h]
  PUCHAR pbInput; // [rsp+B8h] [rbp+60h]
  __int64 v25; // [rsp+D0h] [rbp+78h] BYREF
  va_list va; // [rsp+D0h] [rbp+78h]
  va_list va1; // [rsp+D8h] [rbp+80h] BYREF

  va_start(va1, pbOutput);
  va_start(va, pbOutput);
  v25 = va_arg(va1, _QWORD);
  pbInput = a4;
  v23 = a3;
  v6 = v25;
  v7 = a2;
  phHash = 0;
  v8 = a3;
  v9 = ((unsigned int)v25 + a2 - 1) / a2;
  if ( v9 < 0x100 )
    LODWORD(v25) = 0;
  v10 = (UCHAR *)SafeAllocaAllocateFromHeap(a2 + a3);
  if ( v10 )
  {
    v13 = pbOutput;
    for ( i = 0; ; ++i )
    {
      HIBYTE(v22) = HIBYTE(i);
      if ( i >= v9 )
        goto LABEL_22;
      v12 = BCryptCreateHash(a1, &phHash, v10, v8, 0, 0, 0);
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)WPP_GLOBAL_Control,
            v15,
            (unsigned int)"Status",
            v12,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c",
            70);
        goto LABEL_23;
      }
      v16 = BCryptHashData(phHash, pbInput, cbInput, 0);
      v12 = v16;
      if ( v16 < 0 )
        goto LABEL_28;
      if ( v9 >= 0x100 )
      {
        for ( j = 0; j != 4; ++j )
          va[j] = ((_BYTE *)&v22 - j)[3];
      }
      else
      {
        BYTE3(v25) = i;
      }
      v16 = BCryptHashData(phHash, (PUCHAR)va, 4u, 0);
      v12 = v16;
      if ( v16 < 0 )
        goto LABEL_28;
      if ( v6 < (unsigned int)v7 )
        break;
      v16 = BCryptFinishHash(phHash, v13, v7, 0);
      v12 = v16;
      if ( v16 < 0 )
        goto LABEL_28;
      v6 -= v7;
      v13 += v7;
      BCryptDestroyHash(phHash);
      v8 = v23;
      phHash = 0;
    }
    v18 = &v10[v23];
    v16 = BCryptFinishHash(phHash, v18, v7, 0);
    v12 = v16;
    if ( v16 >= 0 )
    {
      memcpy_0(v13, v18, v6);
      BCryptDestroyHash(phHash);
      phHash = 0;
LABEL_22:
      v12 = 0;
      goto LABEL_23;
    }
LABEL_28:
    DebugTraceError((unsigned int)v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
  }
  else
  {
    v12 = -1073741801;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        v11,
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c",
        53);
  }
LABEL_23:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v10 )
    MSCryptFree(v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180012cc4  mov     [rsp-40h+pbInput], r9
0x180012cc9  mov     [rsp-40h+arg_10], r8d
0x180012cce  mov     [rsp-40h+hAlgorithm], rcx
0x180012cd3  push    rbp
0x180012cd4  push    rbx
0x180012cd5  push    rsi
0x180012cd6  push    rdi
0x180012cd7  push    r12
0x180012cd9  push    r13
0x180012cdb  push    r14
0x180012cdd  push    r15
0x180012cdf  mov     rbp, rsp
0x180012ce2  sub     rsp, 58h
0x180012ce6  mov     r15d, dword ptr [rbp+arg_30]
0x180012cea  lea     eax, [rdx-1]
0x180012ced  mov     edi, edx
0x180012cef  add     eax, r15d
0x180012cf2  xor     edx, edx
0x180012cf4  mov     [rbp+phHash], 0
0x180012cfc  div     edi
0x180012cfe  mov     ebx, r8d
0x180012d01  mov     r13d, eax
0x180012d04  cmp     eax, 100h
0x180012d09  jnb     short loc_180012D12
0x180012d0b  mov     dword ptr [rbp+arg_30], 0
0x180012d12  lea     ecx, [rdi+r8]
0x180012d16  call    SafeAllocaAllocateFromHeap
0x180012d1b  mov     rsi, rax
0x180012d1e  test    rax, rax
0x180012d21  jnz     short loc_180012D7A
0x180012d23  mov     ebx, 0C0000017h
0x180012d28  mov     rdx, cs:WPP_GLOBAL_Control
0x180012d2f  lea     rcx, WPP_GLOBAL_Control
0x180012d36  cmp     rdx, rcx
0x180012d39  jz      loc_180012EAC
0x180012d3f  test    byte ptr [rdx+1Ch], 1
0x180012d43  jz      loc_180012EAC
0x180012d49  mov     [rsp+58h+dwFlags], 135h
0x180012d51  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012d58  mov     qword ptr [rsp+58h+cbSecret], rax
0x180012d5d  mov     dword ptr [rsp+58h+pbSecret], 0C0000017h
0x180012d65  mov     rcx, [rdx+10h]
0x180012d69  lea     r9, aStatus; "Status"
0x180012d70  call    WPP_SF_sDsd
0x180012d75  jmp     loc_180012EAC
0x180012d7a  mov     r12, [rbp+pbOutput]
0x180012d7e  xor     r14d, r14d
0x180012d81  mov     [rbp+arg_8], r14d
0x180012d85  cmp     r14d, r13d
0x180012d88  jnb     loc_180012EAA
0x180012d8e  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x180012d92  lea     rdx, [rbp+phHash]; phHash
0x180012d96  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180012d9e  mov     r9d, ebx; cbHashObject
0x180012da1  mov     [rsp+58h+cbSecret], 0; cbSecret
0x180012da9  mov     r8, rsi; pbHashObject
0x180012dac  mov     [rsp+58h+pbSecret], 0; pbSecret
0x180012db5  call    BCryptCreateHash
0x180012dba  mov     ebx, eax
0x180012dbc  test    eax, eax
0x180012dbe  js      loc_180012F00
0x180012dc4  mov     r8d, [rbp+cbInput]; cbInput
0x180012dc8  xor     r9d, r9d; dwFlags
0x180012dcb  mov     rdx, [rbp+pbInput]; pbInput
0x180012dcf  mov     rcx, [rbp+phHash]; hHash
0x180012dd3  call    BCryptHashData
0x180012dd8  mov     ebx, eax
0x180012dda  test    eax, eax
0x180012ddc  js      loc_180012EE3
0x180012de2  cmp     r13d, 100h
0x180012de9  jnb     short loc_180012DF1
0x180012deb  mov     byte ptr [rbp+arg_30+3], r14b
0x180012def  jmp     short loc_180012E09
0x180012df1  xor     ecx, ecx
0x180012df3  lea     rax, [rbp+arg_8+3]
0x180012df7  sub     rax, rcx
0x180012dfa  mov     al, [rax]
0x180012dfc  mov     byte ptr [rbp+rcx+arg_30], al
0x180012e00  inc     rcx
0x180012e03  cmp     rcx, 4
0x180012e07  jnz     short loc_180012DF3
0x180012e09  mov     rcx, [rbp+phHash]; hHash
0x180012e0d  lea     rdx, [rbp+arg_30]; pbInput
0x180012e11  xor     r9d, r9d; dwFlags
0x180012e14  lea     r8d, [r9+4]; cbInput
0x180012e18  call    BCryptHashData
0x180012e1d  mov     ebx, eax
0x180012e1f  test    eax, eax
0x180012e21  js      loc_180012EDB
0x180012e27  mov     rcx, [rbp+phHash]; hHash
0x180012e2b  xor     r9d, r9d; dwFlags
0x180012e2e  mov     r8d, edi; cbOutput
0x180012e31  cmp     r15d, edi
0x180012e34  jb      short loc_180012E6E
0x180012e36  mov     rdx, r12; pbOutput
0x180012e39  call    BCryptFinishHash
0x180012e3e  mov     ebx, eax
0x180012e40  test    eax, eax
0x180012e42  js      short loc_180012E66
0x180012e44  mov     rcx, [rbp+phHash]; hHash
0x180012e48  sub     r15d, edi
0x180012e4b  add     r12, rdi
0x180012e4e  call    BCryptDestroyHash
0x180012e53  mov     ebx, [rbp+arg_10]
0x180012e56  inc     r14d
0x180012e59  mov     [rbp+phHash], 0
0x180012e61  jmp     loc_180012D81
0x180012e66  mov     r9d, 177h
0x180012e6c  jmp     short loc_180012EE9
0x180012e6e  mov     r14d, [rbp+arg_10]
0x180012e72  add     r14, rsi
0x180012e75  mov     rdx, r14; pbOutput
0x180012e78  call    BCryptFinishHash
0x180012e7d  mov     ebx, eax
0x180012e7f  test    eax, eax
0x180012e81  jns     short loc_180012E8B
0x180012e83  mov     r9d, 187h
0x180012e89  jmp     short loc_180012EE9
0x180012e8b  mov     r8d, r15d; Size
0x180012e8e  mov     rdx, r14; Src
0x180012e91  mov     rcx, r12; void *
0x180012e94  call    memcpy_0
0x180012e99  mov     rcx, [rbp+phHash]; hHash
0x180012e9d  call    BCryptDestroyHash
0x180012ea2  mov     [rbp+phHash], 0
0x180012eaa  xor     ebx, ebx
0x180012eac  mov     rcx, [rbp+phHash]; hHash
0x180012eb0  test    rcx, rcx
0x180012eb3  jz      short loc_180012EBA
0x180012eb5  call    BCryptDestroyHash
0x180012eba  test    rsi, rsi
0x180012ebd  jz      short loc_180012EC7
0x180012ebf  mov     rcx, rsi
0x180012ec2  call    MSCryptFree
0x180012ec7  mov     eax, ebx
0x180012ec9  add     rsp, 58h
0x180012ecd  pop     r15
0x180012ecf  pop     r14
0x180012ed1  pop     r13
0x180012ed3  pop     r12
0x180012ed5  pop     rdi
0x180012ed6  pop     rsi
0x180012ed7  pop     rbx
0x180012ed8  pop     rbp
0x180012ed9  retn
0x180012edb  mov     r9d, 16Ah
0x180012ee1  jmp     short loc_180012EE9
0x180012ee3  mov     r9d, 151h
0x180012ee9  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012ef0  mov     ecx, eax
0x180012ef2  lea     rdx, aStatus; "Status"
0x180012ef9  call    DebugTraceError
0x180012efe  jmp     short loc_180012EAC
0x180012f00  mov     rdx, cs:WPP_GLOBAL_Control
0x180012f07  lea     rcx, WPP_GLOBAL_Control
0x180012f0e  cmp     rdx, rcx
0x180012f11  jz      short loc_180012EAC
0x180012f13  test    byte ptr [rdx+1Ch], 1
0x180012f17  jz      short loc_180012EAC
0x180012f19  mov     [rsp+58h+dwFlags], 146h
0x180012f21  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012f28  mov     qword ptr [rsp+58h+cbSecret], rax
0x180012f2d  mov     dword ptr [rsp+58h+pbSecret], ebx
0x180012f31  jmp     loc_180012D65
```
