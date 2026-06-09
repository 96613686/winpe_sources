# MSCryptCloseKemProvider

- ea: `0x1800645f0`
- end: `0x180064678`
- name: `MSCryptCloseKemProvider`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x1800225a0`
- `0x1800645f0`
- `0x1800653d4`

## string_xrefs

- `0x180064624`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall MSCryptCloseKemProvider(__int64 a1, int a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rcx
  unsigned int *v7; // rcx
  _BYTE *v8; // rdx
  __int64 v9; // rax
  unsigned int *v11; // [rsp+40h] [rbp+18h] BYREF

  v11 = 0;
  v3 = ValidateKemAlgorithm(a1, &v11);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 1138;
    v6 = (unsigned int)v3;
LABEL_3:
    DebugTraceError(v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v5);
    return v4;
  }
  if ( a2 )
  {
    v4 = -1073741811;
    v5 = 1145;
    v6 = 3221225485LL;
    goto LABEL_3;
  }
  v7 = v11;
  v8 = v11;
  v9 = *v11;
  if ( *v11 )
  {
    do
    {
      *v8++ = 0;
      --v9;
    }
    while ( v9 );
  }
  BCryptFree(v7, v8);
  return 0;
}

```

## disassembly

```asm
0x1800645f0  mov     [rsp+arg_0], rbx
0x1800645f5  push    rdi
0x1800645f6  sub     rsp, 20h
0x1800645fa  mov     edi, edx
0x1800645fc  mov     [rsp+28h+arg_10], 0
0x180064605  lea     rdx, [rsp+28h+arg_10]
0x18006460a  call    ValidateKemAlgorithm
0x18006460f  mov     ebx, eax
0x180064611  test    eax, eax
0x180064613  jns     short loc_180064632
0x180064615  mov     r9d, 472h
0x18006461b  mov     ecx, eax
0x18006461d  lea     rdx, aStatus; "Status"
0x180064624  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006462b  call    DebugTraceError
0x180064630  jmp     short loc_18006466A
0x180064632  test    edi, edi
0x180064634  jz      short loc_180064648
0x180064636  mov     ebx, 0C000000Dh
0x18006463b  mov     r9d, 479h
0x180064641  mov     ecx, 0C000000Dh
0x180064646  jmp     short loc_18006461D
0x180064648  mov     rcx, [rsp+28h+arg_10]
0x18006464d  mov     rdx, rcx
0x180064650  mov     eax, [rcx]
0x180064652  test    rax, rax
0x180064655  jz      short loc_180064663
0x180064657  mov     byte ptr [rdx], 0
0x18006465a  inc     rdx
0x18006465d  sub     rax, 1
0x180064661  jnz     short loc_180064657
0x180064663  call    BCryptFree
0x180064668  xor     ebx, ebx
0x18006466a  mov     eax, ebx
0x18006466c  mov     rbx, [rsp+28h+arg_0]
0x180064671  add     rsp, 20h
0x180064675  pop     rdi
0x180064676  retn
```
