# GenerateSymCryptCompositeMlKemKey

- ea: `0x180063e40`
- end: `0x180063f31`
- name: `GenerateSymCryptCompositeMlKemKey`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180064dc0`

## callees

- `0x18000ecb0`
- `0x18002e290`
- `0x180056cf0`
- `0x180063e40`
- `0x18006ff00`
- `0x18006ffc0`
- `0x180070154`
- `0x18007f790`

## string_xrefs

- `0x180063e8b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall GenerateSymCryptCompositeMlKemKey(int a1, unsigned int ***a2, int a3)
{
  unsigned int **v5; // rbx
  __int64 v6; // rsi
  unsigned int v7; // edi
  __int64 v8; // r9
  __int64 v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  _BYTE *v13; // rax
  _BYTE Src[32]; // [rsp+30h] [rbp-48h] BYREF

  v5 = (unsigned int **)SymCryptCompositeMlKemkeyAllocate(a1);
  v6 = 32;
  if ( v5 )
  {
    v10 = SymCryptCallbackRandom(Src, 32);
    if ( v10 )
    {
      v11 = SymcryptErrorCodeToNtStatus(v10);
      v8 = 470;
    }
    else
    {
      v12 = SymCryptCompositeMlKemkeySetValue(Src, 0x20u, 1u, a3, v5);
      if ( !v12 )
      {
        v7 = 0;
        *a2 = v5;
        v5 = 0;
        goto LABEL_10;
      }
      v11 = SymcryptErrorCodeToNtStatus(v12);
      v8 = 482;
    }
    v7 = v11;
    v9 = v11;
  }
  else
  {
    v7 = -1073741801;
    v8 = 457;
    v9 = 3221225495LL;
  }
  DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v8);
LABEL_10:
  v13 = Src;
  do
  {
    *v13++ = 0;
    --v6;
  }
  while ( v6 );
  if ( v5 )
    SymCryptCompositeMlKemkeyFree((__int64)v5);
  return v7;
}

```

## disassembly

```asm
0x180063e40  mov     [rsp+arg_18], rbx
0x180063e45  push    rsi
0x180063e46  push    rdi
0x180063e47  push    r14
0x180063e49  sub     rsp, 60h
0x180063e4d  mov     rax, cs:__security_cookie
0x180063e54  xor     rax, rsp
0x180063e57  mov     [rsp+78h+var_28], rax
0x180063e5c  mov     edi, r8d
0x180063e5f  mov     r14, rdx
0x180063e62  call    SymCryptCompositeMlKemkeyAllocate
0x180063e67  mov     rbx, rax
0x180063e6a  mov     esi, 20h ; ' '
0x180063e6f  test    rax, rax
0x180063e72  jnz     short loc_180063E99
0x180063e74  mov     edi, 0C0000017h
0x180063e79  mov     r9d, 1C9h
0x180063e7f  mov     ecx, 0C0000017h
0x180063e84  lea     rdx, aStatus; "Status"
0x180063e8b  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180063e92  call    DebugTraceError
0x180063e97  jmp     short loc_180063EF2
0x180063e99  mov     rdx, rsi
0x180063e9c  lea     rcx, [rsp+78h+Src]
0x180063ea1  call    SymCryptCallbackRandom
0x180063ea6  test    eax, eax
0x180063ea8  jz      short loc_180063EBD
0x180063eaa  mov     ecx, eax
0x180063eac  call    SymcryptErrorCodeToNtStatus
0x180063eb1  mov     r9d, 1D6h
0x180063eb7  mov     edi, eax
0x180063eb9  mov     ecx, eax
0x180063ebb  jmp     short loc_180063E84
0x180063ebd  mov     r9d, edi
0x180063ec0  mov     [rsp+78h+var_58], rbx; __int64
0x180063ec5  mov     r8d, 1
0x180063ecb  lea     rcx, [rsp+78h+Src]; Src
0x180063ed0  mov     rdx, rsi; Size
0x180063ed3  call    SymCryptCompositeMlKemkeySetValue
0x180063ed8  test    eax, eax
0x180063eda  jz      short loc_180063EEB
0x180063edc  mov     ecx, eax
0x180063ede  call    SymcryptErrorCodeToNtStatus
0x180063ee3  mov     r9d, 1E2h
0x180063ee9  jmp     short loc_180063EB7
0x180063eeb  xor     edi, edi
0x180063eed  mov     [r14], rbx
0x180063ef0  xor     ebx, ebx
0x180063ef2  lea     rax, [rsp+78h+Src]
0x180063ef7  mov     byte ptr [rax], 0
0x180063efa  inc     rax
0x180063efd  sub     rsi, 1
0x180063f01  jnz     short loc_180063EF7
0x180063f03  test    rbx, rbx
0x180063f06  jz      short loc_180063F10
0x180063f08  mov     rcx, rbx
0x180063f0b  call    SymCryptCompositeMlKemkeyFree
0x180063f10  mov     eax, edi
0x180063f12  mov     rcx, [rsp+78h+var_28]
0x180063f17  xor     rcx, rsp; StackCookie
0x180063f1a  call    __security_check_cookie
0x180063f1f  mov     rbx, [rsp+78h+arg_18]
0x180063f27  add     rsp, 60h
0x180063f2b  pop     r14
0x180063f2d  pop     rdi
0x180063f2e  pop     rsi
0x180063f2f  retn
```
