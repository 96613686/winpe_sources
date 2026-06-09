# MSCryptAesKeyUnwrapPadValidateInput

- ea: `0x1800667e4`
- end: `0x180066889`
- name: `MSCryptAesKeyUnwrapPadValidateInput`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180066428`

## callees

- `0x18000c040`
- `0x18000ecb0`
- `0x1800667e4`

## string_xrefs

- `0x180066868`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`

## pseudocode

```c
__int64 __fastcall MSCryptAesKeyUnwrapPadValidateInput(__int64 a1, unsigned int a2)
{
  int Property; // eax
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rcx
  unsigned int v8; // [rsp+50h] [rbp+18h] BYREF
  int v9; // [rsp+58h] [rbp+20h] BYREF

  v9 = 0;
  v8 = 0;
  Property = MSCryptGetProperty(a1, (__int64)L"BlockLength", &v9, 4u, &v8, 0);
  v4 = Property;
  if ( Property < 0 )
  {
    v5 = 544;
    v6 = (unsigned int)Property;
LABEL_10:
    DebugTraceError(v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c", v5);
    return v4;
  }
  if ( v8 != 4 || v9 != 16 )
  {
    v5 = 552;
    goto LABEL_9;
  }
  if ( (a2 & 7) != 0 || a2 < 0x10 )
  {
    v5 = 560;
LABEL_9:
    v6 = 3221225843LL;
    v4 = -1073741453;
    goto LABEL_10;
  }
  return v4;
}

```

## disassembly

```asm
0x1800667e4  mov     rax, rsp
0x1800667e7  mov     [rax+8], rbx
0x1800667eb  push    rdi
0x1800667ec  sub     rsp, 30h
0x1800667f0  mov     dword ptr [rax-10h], 0
0x1800667f7  mov     edi, edx
0x1800667f9  mov     dword ptr [rax+20h], 0
0x180066800  mov     r9d, 4
0x180066806  mov     dword ptr [rax+18h], 0
0x18006680d  lea     rax, [rax+18h]
0x180066811  lea     r8, [rsp+38h+arg_18]
0x180066816  mov     [rsp+38h+var_18], rax
0x18006681b  lea     rdx, aBlocklength; "BlockLength"
0x180066822  call    MSCryptGetProperty
0x180066827  mov     ebx, eax
0x180066829  test    eax, eax
0x18006682b  jns     short loc_180066837
0x18006682d  mov     r9d, 220h
0x180066833  mov     ecx, eax
0x180066835  jmp     short loc_180066868
0x180066837  cmp     [rsp+38h+arg_10], 4
0x18006683c  jnz     short loc_180066858
0x18006683e  cmp     [rsp+38h+arg_18], 10h
0x180066843  jnz     short loc_180066858
0x180066845  test    dil, 7
0x180066849  jnz     short loc_180066850
0x18006684b  cmp     edi, 10h
0x18006684e  jnb     short loc_18006687B
0x180066850  mov     r9d, 230h
0x180066856  jmp     short loc_18006685E
0x180066858  mov     r9d, 228h
0x18006685e  mov     ecx, 0C0000173h
0x180066863  mov     ebx, 0C0000173h
0x180066868  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006686f  lea     rdx, aStatus; "Status"
0x180066876  call    DebugTraceError
0x18006687b  mov     eax, ebx
0x18006687d  mov     rbx, [rsp+38h+arg_0]
0x180066882  add     rsp, 30h
0x180066886  pop     rdi
0x180066887  retn
```
