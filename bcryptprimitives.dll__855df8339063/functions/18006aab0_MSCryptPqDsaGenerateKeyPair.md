# MSCryptPqDsaGenerateKeyPair

- ea: `0x18006aab0`
- end: `0x18006ab5b`
- name: `MSCryptPqDsaGenerateKeyPair`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18006aab0`
- `0x18006b940`
- `0x18006bcc4`

## string_xrefs

- `0x18006aace`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptPqDsaGenerateKeyPair(unsigned __int64 a1, __int64 *a2, int a3, int a4)
{
  __int64 v5; // r9
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rax
  char v9; // r9
  __int64 PqDsaKey; // rax

  if ( !a1 )
  {
    v5 = 987;
LABEL_3:
    v6 = -1073741811;
    v7 = 3221225485LL;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v5 = 994;
    goto LABEL_3;
  }
  if ( a3 )
  {
    v5 = 1001;
    goto LABEL_3;
  }
  if ( (a4 & 0xFFFFFFF7) != 0 )
  {
    v5 = 1008;
    goto LABEL_3;
  }
  v8 = validatePqDsaAlgorithm(a1);
  if ( v8 )
  {
    PqDsaKey = createPqDsaKey(*(_DWORD **)(v8 + 16), v9);
    if ( PqDsaKey )
    {
      *a2 = PqDsaKey;
      return 0;
    }
    v6 = -1073741801;
    v5 = 1024;
    v7 = 3221225495LL;
  }
  else
  {
    v6 = -1073741816;
    v5 = 1016;
    v7 = 3221225480LL;
  }
LABEL_4:
  DebugTraceError(v7, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v5);
  return v6;
}

```

## disassembly

```asm
0x18006aab0  push    rbx
0x18006aab2  sub     rsp, 20h
0x18006aab6  mov     rbx, rdx
0x18006aab9  test    rcx, rcx
0x18006aabc  jnz     short loc_18006AAE3
0x18006aabe  mov     r9d, 3DBh
0x18006aac4  mov     ebx, 0C000000Dh
0x18006aac9  mov     ecx, 0C000000Dh
0x18006aace  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006aad5  lea     rdx, aStatus_0; "status"
0x18006aadc  call    DebugTraceError
0x18006aae1  jmp     short loc_18006AB52
0x18006aae3  test    rbx, rbx
0x18006aae6  jnz     short loc_18006AAF0
0x18006aae8  mov     r9d, 3E2h
0x18006aaee  jmp     short loc_18006AAC4
0x18006aaf0  test    r8d, r8d
0x18006aaf3  jz      short loc_18006AAFD
0x18006aaf5  mov     r9d, 3E9h
0x18006aafb  jmp     short loc_18006AAC4
0x18006aafd  test    r9d, 0FFFFFFF7h
0x18006ab04  jz      short loc_18006AB0E
0x18006ab06  mov     r9d, 3F0h
0x18006ab0c  jmp     short loc_18006AAC4
0x18006ab0e  call    validatePqDsaAlgorithm
0x18006ab13  test    rax, rax
0x18006ab16  jnz     short loc_18006AB2A
0x18006ab18  mov     ebx, 0C0000008h
0x18006ab1d  mov     r9d, 3F8h
0x18006ab23  mov     ecx, 0C0000008h
0x18006ab28  jmp     short loc_18006AACE
0x18006ab2a  mov     rcx, [rax+10h]
0x18006ab2e  mov     edx, r9d
0x18006ab31  call    createPqDsaKey
0x18006ab36  test    rax, rax
0x18006ab39  jnz     short loc_18006AB4D
0x18006ab3b  mov     ebx, 0C0000017h
0x18006ab40  mov     r9d, 400h
0x18006ab46  mov     ecx, 0C0000017h
0x18006ab4b  jmp     short loc_18006AACE
0x18006ab4d  mov     [rbx], rax
0x18006ab50  xor     ebx, ebx
0x18006ab52  mov     eax, ebx
0x18006ab54  add     rsp, 20h
0x18006ab58  pop     rbx
0x18006ab59  retn
```
