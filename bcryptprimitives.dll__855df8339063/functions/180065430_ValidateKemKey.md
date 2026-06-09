# ValidateKemKey

- ea: `0x180065430`
- end: `0x1800654da`
- name: `ValidateKemKey`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180064680`
- `0x1800648f0`
- `0x180064a80`
- `0x180064ae0`
- `0x180064c80`
- `0x180064dc0`
- `0x180065260`

## callees

- `0x18000ecb0`
- `0x180064284`
- `0x180065430`

## string_xrefs

- `0x1800654bb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall ValidateKemKey(_DWORD *a1, _QWORD *a2, int a3)
{
  int MsCryptKemKeyLength; // eax
  unsigned int v7; // edi
  __int64 v8; // r9
  __int64 v9; // rcx
  int v11; // [rsp+50h] [rbp+8h] BYREF

  v11 = 0;
  if ( !a1 || !a2 )
  {
    v8 = 307;
    goto LABEL_13;
  }
  MsCryptKemKeyLength = GetMsCryptKemKeyLength((unsigned int)a1[2], &v11);
  v7 = MsCryptKemKeyLength;
  if ( MsCryptKemKeyLength < 0 )
  {
    v8 = 316;
    v9 = (unsigned int)MsCryptKemKeyLength;
LABEL_14:
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v8);
    return v7;
  }
  if ( a1[1] != 1297302859 || *a1 != v11 )
  {
    v8 = 324;
LABEL_13:
    v9 = 3221225485LL;
    v7 = -1073741811;
    goto LABEL_14;
  }
  if ( a3 && !a1[4] )
  {
    v7 = -1073741816;
    v8 = 331;
    v9 = 3221225480LL;
    goto LABEL_14;
  }
  *a2 = a1;
  return v7;
}

```

## disassembly

```asm
0x180065430  push    rbx
0x180065432  push    rbp
0x180065433  push    rsi
0x180065434  push    rdi
0x180065435  sub     rsp, 28h
0x180065439  mov     [rsp+48h+arg_0], 0
0x180065441  mov     ebp, r8d
0x180065444  mov     rsi, rdx
0x180065447  mov     rbx, rcx
0x18006544a  test    rcx, rcx
0x18006544d  jz      short loc_1800654AB
0x18006544f  test    rdx, rdx
0x180065452  jz      short loc_1800654AB
0x180065454  mov     ecx, [rcx+8]
0x180065457  lea     rdx, [rsp+48h+arg_0]
0x18006545c  call    GetMsCryptKemKeyLength
0x180065461  mov     edi, eax
0x180065463  test    eax, eax
0x180065465  jns     short loc_180065471
0x180065467  mov     r9d, 13Ch
0x18006546d  mov     ecx, eax
0x18006546f  jmp     short loc_1800654BB
0x180065471  cmp     dword ptr [rbx+4], 4D53454Bh
0x180065478  jnz     short loc_1800654A3
0x18006547a  mov     eax, [rsp+48h+arg_0]
0x18006547e  cmp     [rbx], eax
0x180065480  jnz     short loc_1800654A3
0x180065482  test    ebp, ebp
0x180065484  jz      short loc_18006549E
0x180065486  cmp     dword ptr [rbx+10h], 0
0x18006548a  jnz     short loc_18006549E
0x18006548c  mov     edi, 0C0000008h
0x180065491  mov     r9d, 14Bh
0x180065497  mov     ecx, 0C0000008h
0x18006549c  jmp     short loc_1800654BB
0x18006549e  mov     [rsi], rbx
0x1800654a1  jmp     short loc_1800654CE
0x1800654a3  mov     r9d, 144h
0x1800654a9  jmp     short loc_1800654B1
0x1800654ab  mov     r9d, 133h
0x1800654b1  mov     ecx, 0C000000Dh
0x1800654b6  mov     edi, 0C000000Dh
0x1800654bb  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800654c2  lea     rdx, aStatus; "Status"
0x1800654c9  call    DebugTraceError
0x1800654ce  mov     eax, edi
0x1800654d0  add     rsp, 28h
0x1800654d4  pop     rdi
0x1800654d5  pop     rsi
0x1800654d6  pop     rbp
0x1800654d7  pop     rbx
0x1800654d8  retn
```
