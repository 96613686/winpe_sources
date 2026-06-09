# MSCrypt_Hash

- ea: `0x18007d95c`
- end: `0x18007da33`
- name: `MSCrypt_Hash`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007dd2c`

## callees

- `0x18000ecb0`
- `0x180017240`
- `0x1800173f0`
- `0x180063170`
- `0x18007d95c`
- `0x18007f790`

## string_xrefs

- `0x18007d9ab`: `onecore\ds\security\cryptoapi\ncrypt\kdf\sp800_56a.c`

## pseudocode

```c
__int64 __fastcall MSCrypt_Hash(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        void *a5,
        unsigned int a6,
        unsigned int *a7)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  unsigned int v12; // eax
  __int64 v13; // rcx
  _BYTE *v14; // rax
  _BYTE Src[64]; // [rsp+20h] [rbp-78h] BYREF

  v9 = MSCryptHashData(a1, a3, a4, 0);
  v10 = v9;
  if ( v9 )
  {
    v11 = 597;
LABEL_3:
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\sp800_56a.c", v11);
    goto LABEL_9;
  }
  v9 = MSCryptFinishHash(a1, (__int64)Src, a2, 0);
  v10 = v9;
  if ( v9 )
  {
    v11 = 608;
    goto LABEL_3;
  }
  v12 = a6;
  if ( a2 <= a6 )
    v12 = a2;
  *a7 = v12;
  memcpy_0(a5, Src, v12);
LABEL_9:
  v13 = 64;
  v14 = Src;
  do
  {
    *v14++ = 0;
    --v13;
  }
  while ( v13 );
  return v10;
}

```

## disassembly

```asm
0x18007d95c  push    rbx
0x18007d95e  push    rbp
0x18007d95f  push    rsi
0x18007d960  push    rdi
0x18007d961  push    r14
0x18007d963  sub     rsp, 70h
0x18007d967  mov     rax, cs:__security_cookie
0x18007d96e  xor     rax, rsp
0x18007d971  mov     [rsp+98h+var_38], rax
0x18007d976  mov     rbp, [rsp+98h+arg_20]
0x18007d97e  mov     r10d, r9d
0x18007d981  mov     r14, [rsp+98h+arg_30]
0x18007d989  mov     rax, r8
0x18007d98c  mov     edi, edx
0x18007d98e  mov     r8d, r10d
0x18007d991  mov     rdx, rax
0x18007d994  xor     r9d, r9d
0x18007d997  mov     rsi, rcx
0x18007d99a  call    MSCryptHashData
0x18007d99f  mov     ebx, eax
0x18007d9a1  test    eax, eax
0x18007d9a3  jz      short loc_18007D9C2
0x18007d9a5  mov     r9d, 255h
0x18007d9ab  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007d9b2  mov     ecx, eax
0x18007d9b4  lea     rdx, aStatus; "Status"
0x18007d9bb  call    DebugTraceError
0x18007d9c0  jmp     short loc_18007DA02
0x18007d9c2  xor     r9d, r9d
0x18007d9c5  lea     rdx, [rsp+98h+Src]
0x18007d9ca  mov     r8d, edi
0x18007d9cd  mov     rcx, rsi
0x18007d9d0  call    MSCryptFinishHash
0x18007d9d5  mov     ebx, eax
0x18007d9d7  test    eax, eax
0x18007d9d9  jz      short loc_18007D9E3
0x18007d9db  mov     r9d, 260h
0x18007d9e1  jmp     short loc_18007D9AB
0x18007d9e3  mov     eax, [rsp+98h+arg_28]
0x18007d9ea  lea     rdx, [rsp+98h+Src]; Src
0x18007d9ef  cmp     edi, eax
0x18007d9f1  mov     rcx, rbp; void *
0x18007d9f4  cmovbe  eax, edi
0x18007d9f7  mov     r8d, eax; Size
0x18007d9fa  mov     [r14], r8d
0x18007d9fd  call    memcpy_0
0x18007da02  mov     ecx, 40h ; '@'
0x18007da07  lea     rax, [rsp+98h+Src]
0x18007da0c  mov     byte ptr [rax], 0
0x18007da0f  inc     rax
0x18007da12  sub     rcx, 1
0x18007da16  jnz     short loc_18007DA0C
0x18007da18  mov     eax, ebx
0x18007da1a  mov     rcx, [rsp+98h+var_38]
0x18007da1f  xor     rcx, rsp; StackCookie
0x18007da22  call    __security_check_cookie
0x18007da27  add     rsp, 70h
0x18007da2b  pop     r14
0x18007da2d  pop     rdi
0x18007da2e  pop     rsi
0x18007da2f  pop     rbp
0x18007da30  pop     rbx
0x18007da31  retn
```
