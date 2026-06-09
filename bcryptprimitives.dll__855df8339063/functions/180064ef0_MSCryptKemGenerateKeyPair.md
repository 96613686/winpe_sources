# MSCryptKemGenerateKeyPair

- ea: `0x180064ef0`
- end: `0x180064fde`
- name: `MSCryptKemGenerateKeyPair`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180010270`
- `0x180063b00`
- `0x180064ef0`
- `0x1800653d4`

## string_xrefs

- `0x180064f32`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`
- `0x180064f9b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall MSCryptKemGenerateKeyPair(__int64 a1, _QWORD *a2, int a3, unsigned int a4)
{
  __int64 v6; // r9
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  __int64 v13; // [rsp+20h] [rbp-18h] BYREF
  __int64 v14; // [rsp+28h] [rbp-10h] BYREF

  v14 = 0;
  v13 = 0;
  if ( a3 )
  {
    v6 = 1179;
LABEL_3:
    v7 = -1073741811;
    v8 = 3221225485LL;
LABEL_4:
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v6);
    return v7;
  }
  if ( (a4 & 0xFFFFFFF7) != 0 )
  {
    v6 = 1186;
    goto LABEL_3;
  }
  v9 = ValidateKemAlgorithm(a1, &v14);
  v7 = v9;
  if ( v9 < 0 )
  {
    v6 = 1193;
    v8 = (unsigned int)v9;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v6 = 1200;
    goto LABEL_3;
  }
  v10 = CreateNewMSCryptKemKey(&v13, a4, *(unsigned int *)(v14 + 8));
  v7 = v10;
  if ( v10 >= 0 )
  {
    v11 = 0;
    *a2 = v13;
  }
  else
  {
    DebugTraceError((unsigned int)v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", 1207);
    v11 = v13;
  }
  if ( v11 )
    MSCryptFree(v11);
  return v7;
}

```

## disassembly

```asm
0x180064ef0  mov     rax, rsp
0x180064ef3  mov     [rax+8], rbx
0x180064ef7  mov     [rax+10h], rsi
0x180064efb  push    rdi
0x180064efc  sub     rsp, 30h
0x180064f00  mov     qword ptr [rax-10h], 0
0x180064f08  mov     esi, r9d
0x180064f0b  mov     qword ptr [rax-18h], 0
0x180064f13  mov     rdi, rdx
0x180064f16  test    r8d, r8d
0x180064f19  jz      short loc_180064F43
0x180064f1b  mov     r9d, 49Bh
0x180064f21  mov     ebx, 0C000000Dh
0x180064f26  mov     ecx, 0C000000Dh
0x180064f2b  lea     rdx, aStatus; "Status"
0x180064f32  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180064f39  call    DebugTraceError
0x180064f3e  jmp     loc_180064FCB
0x180064f43  test    esi, 0FFFFFFF7h
0x180064f49  jz      short loc_180064F53
0x180064f4b  mov     r9d, 4A2h
0x180064f51  jmp     short loc_180064F21
0x180064f53  lea     rdx, [rsp+38h+var_10]
0x180064f58  call    ValidateKemAlgorithm
0x180064f5d  mov     ebx, eax
0x180064f5f  test    eax, eax
0x180064f61  jns     short loc_180064F6D
0x180064f63  mov     r9d, 4A9h
0x180064f69  mov     ecx, eax
0x180064f6b  jmp     short loc_180064F2B
0x180064f6d  test    rdi, rdi
0x180064f70  jnz     short loc_180064F7A
0x180064f72  mov     r9d, 4B0h
0x180064f78  jmp     short loc_180064F21
0x180064f7a  mov     r8, [rsp+38h+var_10]
0x180064f7f  lea     rcx, [rsp+38h+var_18]
0x180064f84  mov     edx, esi
0x180064f86  mov     r8d, [r8+8]
0x180064f8a  call    CreateNewMSCryptKemKey
0x180064f8f  mov     ebx, eax
0x180064f91  test    eax, eax
0x180064f93  jns     short loc_180064FB7
0x180064f95  mov     r9d, 4B7h
0x180064f9b  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180064fa2  lea     rdx, aStatus; "Status"
0x180064fa9  mov     ecx, eax
0x180064fab  call    DebugTraceError
0x180064fb0  mov     rcx, [rsp+38h+var_18]
0x180064fb5  jmp     short loc_180064FC1
0x180064fb7  mov     rax, [rsp+38h+var_18]
0x180064fbc  xor     ecx, ecx
0x180064fbe  mov     [rdi], rax
0x180064fc1  test    rcx, rcx
0x180064fc4  jz      short loc_180064FCB
0x180064fc6  call    MSCryptFree
0x180064fcb  mov     rsi, [rsp+38h+arg_8]
0x180064fd0  mov     eax, ebx
0x180064fd2  mov     rbx, [rsp+38h+arg_0]
0x180064fd7  add     rsp, 30h
0x180064fdb  pop     rdi
0x180064fdc  retn
```
