# MSCryptGenerateKeyPair

- ea: `0x18003c070`
- end: `0x18003c173`
- name: `MSCryptGenerateKeyPair`
- size: `259`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18003c070`
- `0x18003ce58`
- `0x180049500`

## string_xrefs

- `0x18003c0e4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180081ea6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptGenerateKeyPair(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // r8d
  int v7; // r9d
  unsigned int v8; // r10d
  unsigned int v9; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  int v13; // eax

  if ( (a4 & 0xFFFEFFFF) != 0 )
  {
    v11 = 927;
LABEL_11:
    v9 = -1073741811;
    v12 = 3221225485LL;
    goto LABEL_18;
  }
  v5 = validateMSCryptRsaAlgorithm();
  if ( !v5 )
  {
    v9 = -1073741816;
    v11 = 936;
    v12 = 3221225480LL;
    goto LABEL_18;
  }
  if ( !v4 )
  {
    v11 = 943;
    goto LABEL_11;
  }
  if ( v6 >= ((v7 & 0x10000) != 0 ? 384 : 512) && v8 <= 0x4000 && (v8 & 7) == 0 )
  {
    v13 = CreateAndInitializeNewKey(v5, v8, v4);
    v9 = v13;
    if ( v13 >= 0 )
      return 0;
    v11 = 967;
    v12 = (unsigned int)v13;
LABEL_18:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v11);
    return v9;
  }
  v9 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      v6,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
      189);
  return v9;
}

```

## disassembly

```asm
0x18003c070  push    rbx
0x18003c072  sub     rsp, 40h
0x18003c076  mov     r10d, r8d
0x18003c079  test    r9d, 0FFFEFFFFh
0x18003c080  jnz     loc_18003C10E
0x18003c086  call    validateMSCryptRsaAlgorithm
0x18003c08b  mov     rcx, rax
0x18003c08e  test    rax, rax
0x18003c091  jz      loc_18003C12B
0x18003c097  test    rdx, rdx
0x18003c09a  jz      short loc_18003C116
0x18003c09c  and     r9d, 10000h
0x18003c0a3  neg     r9d
0x18003c0a6  sbb     eax, eax
0x18003c0a8  and     eax, 0FFFFFF80h
0x18003c0ab  add     eax, 200h
0x18003c0b0  cmp     r8d, eax
0x18003c0b3  jnb     loc_18003C140
0x18003c0b9  mov     ebx, 0C000000Dh
0x18003c0be  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c0c5  lea     rax, WPP_GLOBAL_Control
0x18003c0cc  cmp     rcx, rax
0x18003c0cf  jz      short loc_18003C0D7
0x18003c0d1  test    byte ptr [rcx+1Ch], 1
0x18003c0d5  jnz     short loc_18003C0E0
0x18003c0d7  mov     eax, ebx
0x18003c0d9  add     rsp, 40h
0x18003c0dd  pop     rbx
0x18003c0de  retn
0x18003c0e0  mov     rcx, [rcx+10h]
0x18003c0e4  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c0eb  mov     [rsp+48h+var_18], 3BDh
0x18003c0f3  lea     r9, aStatus; "Status"
0x18003c0fa  mov     [rsp+48h+var_20], rax
0x18003c0ff  mov     [rsp+48h+var_28], 0C000000Dh
0x18003c107  call    WPP_SF_sDsd
0x18003c10c  jmp     short loc_18003C0D7
0x18003c10e  mov     r9d, 39Fh
0x18003c114  jmp     short loc_18003C11C
0x18003c116  mov     r9d, 3AFh
0x18003c11c  mov     ebx, 0C000000Dh
0x18003c121  mov     ecx, 0C000000Dh
0x18003c126  jmp     loc_180081EA6
0x18003c12b  mov     ebx, 0C0000008h
0x18003c130  mov     r9d, 3A8h
0x18003c136  mov     ecx, 0C0000008h
0x18003c13b  jmp     loc_180081EA6
0x18003c140  cmp     r10d, 4000h
0x18003c147  ja      loc_18003C0B9
0x18003c14d  test    r10b, 7
0x18003c151  jnz     loc_18003C0B9
0x18003c157  mov     r8, rdx
0x18003c15a  mov     edx, r10d
0x18003c15d  call    CreateAndInitializeNewKey
0x18003c162  mov     ebx, eax
0x18003c164  test    eax, eax
0x18003c166  js      loc_180081E9E
0x18003c16c  xor     ebx, ebx
0x18003c16e  jmp     loc_18003C0D7
0x180081e9e  mov     r9d, 3C7h
0x180081ea4  mov     ecx, eax
0x180081ea6  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180081ead  lea     rdx, aStatus; "Status"
0x180081eb4  call    DebugTraceError
0x180081eb9  nop
0x180081eba  jmp     loc_18003C0D7
```
