# MSCryptCloseRsaProvider

- ea: `0x18003c430`
- end: `0x18003c4dd`
- name: `MSCryptCloseRsaProvider`
- size: `173`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004a060`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800225a0`
- `0x18003c430`
- `0x18003ce58`

## string_xrefs

- `0x18003c48e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003c4be`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptCloseRsaProvider(__int64 a1, int a2)
{
  unsigned int v2; // ebx
  unsigned int *v3; // rax
  __int64 v4; // rcx
  _BYTE *v5; // rdx

  v2 = 0;
  if ( a2 )
  {
    v2 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        220);
  }
  else
  {
    v3 = (unsigned int *)validateMSCryptRsaAlgorithm();
    if ( v3 )
    {
      v4 = *v3;
      v5 = v3;
      if ( *v3 )
      {
        do
        {
          *v5++ = 0;
          --v4;
        }
        while ( v4 );
      }
      BCryptFree(v3, v5);
    }
    else
    {
      v2 = -1073741816;
      DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 485);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18003c430  push    rbx
0x18003c432  sub     rsp, 40h
0x18003c436  xor     ebx, ebx
0x18003c438  test    edx, edx
0x18003c43a  jnz     short loc_18003C46C
0x18003c43c  call    validateMSCryptRsaAlgorithm
0x18003c441  test    rax, rax
0x18003c444  jz      short loc_18003C4B8
0x18003c446  mov     ecx, [rax]
0x18003c448  mov     rdx, rax
0x18003c44b  test    rcx, rcx
0x18003c44e  jz      short loc_18003C45B
0x18003c450  mov     [rdx], bl
0x18003c452  inc     rdx
0x18003c455  sub     rcx, 1
0x18003c459  jnz     short loc_18003C450
0x18003c45b  mov     rcx, rax
0x18003c45e  call    BCryptFree
0x18003c463  mov     eax, ebx
0x18003c465  add     rsp, 40h
0x18003c469  pop     rbx
0x18003c46a  retn
0x18003c46c  mov     ebx, 0C000000Dh
0x18003c471  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c478  lea     rax, WPP_GLOBAL_Control
0x18003c47f  cmp     rcx, rax
0x18003c482  jz      short loc_18003C463
0x18003c484  test    byte ptr [rcx+1Ch], 1
0x18003c488  jz      short loc_18003C463
0x18003c48a  mov     rcx, [rcx+10h]
0x18003c48e  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c495  mov     [rsp+48h+var_18], 1DCh
0x18003c49d  lea     r9, aStatus; "Status"
0x18003c4a4  mov     [rsp+48h+var_20], r8
0x18003c4a9  mov     [rsp+48h+var_28], 0C000000Dh
0x18003c4b1  call    WPP_SF_sDsd
0x18003c4b6  jmp     short loc_18003C463
0x18003c4b8  mov     r9d, 1E5h
0x18003c4be  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c4c5  lea     rdx, aStatus; "Status"
0x18003c4cc  mov     ecx, 0C0000008h
0x18003c4d1  mov     ebx, 0C0000008h
0x18003c4d6  call    DebugTraceError
0x18003c4db  jmp     short loc_18003C463
```
