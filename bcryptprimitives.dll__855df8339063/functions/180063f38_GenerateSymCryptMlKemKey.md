# GenerateSymCryptMlKemKey

- ea: `0x180063f38`
- end: `0x180063fd3`
- name: `GenerateSymCryptMlKemKey`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180064dc0`

## callees

- `0x180001180`
- `0x180001240`
- `0x180001270`
- `0x18000ecb0`
- `0x180056cf0`
- `0x180063f38`

## string_xrefs

- `0x180063f60`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`
- `0x180063f96`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall GenerateSymCryptMlKemKey(__int64 a1, __int64 *a2, unsigned int a3)
{
  __int64 v5; // rax
  __int64 v6; // rdi
  unsigned int v7; // ebx
  unsigned int v8; // eax

  v5 = SymCryptMlKemkeyAllocate(a1);
  v6 = v5;
  if ( v5 )
  {
    v8 = SymCryptMlKemkeyGenerate(v5, a3);
    if ( v8 )
    {
      v7 = SymcryptErrorCodeToNtStatus(v8);
      DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", 422);
      SymCryptMlKemkeyFree(v6);
    }
    else
    {
      v7 = 0;
      *a2 = v6;
    }
  }
  else
  {
    v7 = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", 414);
  }
  return v7;
}

```

## disassembly

```asm
0x180063f38  mov     [rsp+arg_0], rbx
0x180063f3d  mov     [rsp+arg_8], rsi
0x180063f42  push    rdi
0x180063f43  sub     rsp, 20h
0x180063f47  mov     ebx, r8d
0x180063f4a  mov     rsi, rdx
0x180063f4d  call    SymCryptMlKemkeyAllocate
0x180063f52  mov     rdi, rax
0x180063f55  test    rax, rax
0x180063f58  jnz     short loc_180063F7F
0x180063f5a  mov     r9d, 19Eh
0x180063f60  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180063f67  lea     rdx, aStatus; "Status"
0x180063f6e  mov     ecx, 0C0000017h
0x180063f73  mov     ebx, 0C0000017h
0x180063f78  call    DebugTraceError
0x180063f7d  jmp     short loc_180063FC0
0x180063f7f  mov     edx, ebx
0x180063f81  mov     rcx, rdi
0x180063f84  call    SymCryptMlKemkeyGenerate
0x180063f89  test    eax, eax
0x180063f8b  jz      short loc_180063FBB
0x180063f8d  mov     ecx, eax
0x180063f8f  call    SymcryptErrorCodeToNtStatus
0x180063f94  mov     ecx, eax
0x180063f96  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180063f9d  mov     r9d, 1A6h
0x180063fa3  lea     rdx, aStatus; "Status"
0x180063faa  mov     ebx, eax
0x180063fac  call    DebugTraceError
0x180063fb1  mov     rcx, rdi
0x180063fb4  call    SymCryptMlKemkeyFree
0x180063fb9  jmp     short loc_180063FC0
0x180063fbb  xor     ebx, ebx
0x180063fbd  mov     [rsi], rdi
0x180063fc0  mov     rsi, [rsp+28h+arg_8]
0x180063fc5  mov     eax, ebx
0x180063fc7  mov     rbx, [rsp+28h+arg_0]
0x180063fcc  add     rsp, 20h
0x180063fd0  pop     rdi
0x180063fd1  retn
```
