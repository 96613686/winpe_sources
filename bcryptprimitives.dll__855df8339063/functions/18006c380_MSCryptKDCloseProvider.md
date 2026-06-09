# MSCryptKDCloseProvider

- ea: `0x18006c380`
- end: `0x18006c3fd`
- name: `MSCryptKDCloseProvider`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180053750`

## callees

- `0x18000ecb0`
- `0x180010270`
- `0x180011640`
- `0x18006c380`

## string_xrefs

- `0x18006c3aa`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDCloseProvider(__int64 a1, int a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r9
  __int64 v4; // rcx
  int v5; // eax
  unsigned int *v6; // rcx
  _BYTE *v7; // rdx
  __int64 v8; // rax
  unsigned int *v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = 0;
  if ( a2 )
  {
    v2 = -1073741811;
    v3 = 515;
    v4 = 3221225485LL;
LABEL_3:
    DebugTraceError(
      v4,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v3);
    return v2;
  }
  v5 = ValidateKeyDerivationAlgorithm(a1, &v10);
  v2 = v5;
  if ( v5 < 0 )
  {
    v3 = 527;
    v4 = (unsigned int)v5;
    goto LABEL_3;
  }
  v6 = v10;
  v7 = v10;
  v8 = *v10;
  if ( *v10 )
  {
    do
    {
      *v7++ = 0;
      --v8;
    }
    while ( v8 );
  }
  MSCryptFree(v6);
  return 0;
}

```

## disassembly

```asm
0x18006c380  push    rbx
0x18006c382  sub     rsp, 20h
0x18006c386  mov     [rsp+28h+arg_10], 0
0x18006c38f  test    edx, edx
0x18006c391  jz      short loc_18006C3B8
0x18006c393  mov     ebx, 0C000000Dh
0x18006c398  mov     r9d, 203h
0x18006c39e  mov     ecx, 0C000000Dh
0x18006c3a3  lea     rdx, aStatus; "Status"
0x18006c3aa  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006c3b1  call    DebugTraceError
0x18006c3b6  jmp     short loc_18006C3F4
0x18006c3b8  lea     rdx, [rsp+28h+arg_10]
0x18006c3bd  call    ValidateKeyDerivationAlgorithm
0x18006c3c2  mov     ebx, eax
0x18006c3c4  test    eax, eax
0x18006c3c6  jns     short loc_18006C3D2
0x18006c3c8  mov     r9d, 20Fh
0x18006c3ce  mov     ecx, eax
0x18006c3d0  jmp     short loc_18006C3A3
0x18006c3d2  mov     rcx, [rsp+28h+arg_10]
0x18006c3d7  mov     rdx, rcx
0x18006c3da  mov     eax, [rcx]
0x18006c3dc  test    rax, rax
0x18006c3df  jz      short loc_18006C3ED
0x18006c3e1  mov     byte ptr [rdx], 0
0x18006c3e4  inc     rdx
0x18006c3e7  sub     rax, 1
0x18006c3eb  jnz     short loc_18006C3E1
0x18006c3ed  call    MSCryptFree
0x18006c3f2  xor     ebx, ebx
0x18006c3f4  mov     eax, ebx
0x18006c3f6  add     rsp, 20h
0x18006c3fa  pop     rbx
0x18006c3fb  retn
```
