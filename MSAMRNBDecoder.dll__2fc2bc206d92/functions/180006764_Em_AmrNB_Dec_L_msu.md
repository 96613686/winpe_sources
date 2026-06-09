# Em_AmrNB_Dec_L_msu

- ea: `0x180006764`
- end: `0x1800067a4`
- name: `Em_AmrNB_Dec_L_msu`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180003800`
- `0x180004d24`
- `0x180004dd0`
- `0x180006eb4`
- `0x180007b6c`
- `0x180007d60`
- `0x1800085b4`
- `0x180009a74`

## callees

- `0x180006764`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_L_msu(int a1, __int16 a2, __int16 a3)
{
  int v4; // ecx
  int v5; // eax
  unsigned int v6; // ecx

  v4 = a3 * a2;
  v5 = 2 * v4;
  if ( v4 == 0x40000000 )
    v5 = 0x7FFFFFFF;
  v6 = a1 - v5;
  if ( (a1 ^ v5) < 0 && ((a1 ^ v6) & 0x80000000) != 0 )
  {
    v6 = 0x7FFFFFFF;
    if ( a1 < 0 )
      return 0x80000000;
  }
  return v6;
}

```

## disassembly

```asm
0x180006764  mov     r9d, ecx
0x180006767  movsx   eax, r8w
0x18000676b  movsx   ecx, dx
0x18000676e  mov     edx, 7FFFFFFFh
0x180006773  imul    ecx, eax
0x180006776  lea     eax, [rcx+rcx]
0x180006779  cmp     ecx, 40000000h
0x18000677f  jnz     short loc_180006783
0x180006781  mov     eax, edx
0x180006783  mov     ecx, r9d
0x180006786  sub     ecx, eax
0x180006788  xor     eax, r9d
0x18000678b  jge     short loc_1800067A1
0x18000678d  mov     eax, ecx
0x18000678f  xor     eax, r9d
0x180006792  jge     short loc_1800067A1
0x180006794  test    r9d, r9d
0x180006797  mov     ecx, edx
0x180006799  mov     eax, 80000000h
0x18000679e  cmovs   ecx, eax
0x1800067a1  mov     eax, ecx
0x1800067a3  retn
```
