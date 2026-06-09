# CheckAndGetPssHashAlgorithm

- ea: `0x18003d884`
- end: `0x18003d961`
- name: `CheckAndGetPssHashAlgorithm`
- size: `221`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003d000`
- `0x18003d300`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18003d884`
- `0x18003d968`

## string_xrefs

- `0x18003d8ef`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003d93f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall CheckAndGetPssHashAlgorithm(__int64 a1, unsigned int a2, __int64 *a3)
{
  __int64 SymCryptHashAlgorithm; // rax
  unsigned int v5; // ebx

  if ( a1 && *(_QWORD *)a1 )
  {
    if ( a2 > 0x4000 || *(_DWORD *)(a1 + 8) > 0x4000u )
    {
      v5 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          110);
    }
    else
    {
      SymCryptHashAlgorithm = GetSymCryptHashAlgorithm(*(_QWORD *)a1);
      if ( SymCryptHashAlgorithm )
      {
        *a3 = SymCryptHashAlgorithm;
        return 0;
      }
      else
      {
        v5 = -1073741811;
        DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 118);
      }
    }
  }
  else
  {
    v5 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        100);
  }
  return v5;
}

```

## disassembly

```asm
0x18003d884  push    rbx
0x18003d886  sub     rsp, 40h
0x18003d88a  mov     rbx, r8
0x18003d88d  test    rcx, rcx
0x18003d890  jz      short loc_18003D8C5
0x18003d892  cmp     qword ptr [rcx], 0
0x18003d896  jz      short loc_18003D8C5
0x18003d898  mov     eax, 4000h
0x18003d89d  cmp     edx, eax
0x18003d89f  ja      short loc_18003D911
0x18003d8a1  cmp     [rcx+8], eax
0x18003d8a4  ja      short loc_18003D911
0x18003d8a6  mov     rcx, [rcx]
0x18003d8a9  call    GetSymCryptHashAlgorithm
0x18003d8ae  test    rax, rax
0x18003d8b1  jz      loc_18003D939
0x18003d8b7  mov     [rbx], rax
0x18003d8ba  xor     ebx, ebx
0x18003d8bc  mov     eax, ebx
0x18003d8be  add     rsp, 40h
0x18003d8c2  pop     rbx
0x18003d8c3  retn
0x18003d8c5  mov     ebx, 0C000000Dh
0x18003d8ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d8d1  lea     rax, WPP_GLOBAL_Control
0x18003d8d8  cmp     rcx, rax
0x18003d8db  jz      short loc_18003D8BC
0x18003d8dd  test    byte ptr [rcx+1Ch], 1
0x18003d8e1  jz      short loc_18003D8BC
0x18003d8e3  mov     [rsp+48h+var_18], 64h ; 'd'
0x18003d8eb  mov     rcx, [rcx+10h]
0x18003d8ef  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d8f6  mov     [rsp+48h+var_20], rax
0x18003d8fb  lea     r9, aStatus; "Status"
0x18003d902  mov     [rsp+48h+var_28], 0C000000Dh
0x18003d90a  call    WPP_SF_sDsd
0x18003d90f  jmp     short loc_18003D8BC
0x18003d911  mov     ebx, 0C000000Dh
0x18003d916  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d91d  lea     rax, WPP_GLOBAL_Control
0x18003d924  cmp     rcx, rax
0x18003d927  jz      short loc_18003D8BC
0x18003d929  test    byte ptr [rcx+1Ch], 1
0x18003d92d  jz      short loc_18003D8BC
0x18003d92f  mov     [rsp+48h+var_18], 6Eh ; 'n'
0x18003d937  jmp     short loc_18003D8EB
0x18003d939  mov     r9d, 76h ; 'v'
0x18003d93f  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d946  lea     rdx, aStatus; "Status"
0x18003d94d  mov     ecx, 0C000000Dh
0x18003d952  mov     ebx, 0C000000Dh
0x18003d957  call    DebugTraceError
0x18003d95c  jmp     loc_18003D8BC
```
