# ValidateDSAKey

- ea: `0x18005196c`
- end: `0x180051a29`
- name: `ValidateDSAKey`
- size: `189`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800697b0`
- `0x1800698a0`
- `0x1800699e4`
- `0x180069e28`
- `0x18006a110`
- `0x18006a250`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18005196c`

## string_xrefs

- `0x1800519e0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x180082ba2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall ValidateDSAKey(__int64 a1, int a2, _QWORD *a3)
{
  unsigned int v3; // ebx
  int v5; // edx
  __int64 v7; // r9

  v3 = 0;
  if ( a1 && a3 )
  {
    if ( *(_DWORD *)(a1 + 4) != 1297304409
      || *(_DWORD *)(a1 + 8) != 196611
      || (v5 = *(_DWORD *)(a1 + 12), (unsigned int)(v5 - 64) > 0x140)
      || (v5 & 7) != 0 )
    {
      v7 = 233;
      goto LABEL_16;
    }
    if ( a2 && !*(_BYTE *)(*(_QWORD *)(a1 + 40) + 4LL) )
    {
      v7 = 243;
LABEL_16:
      v3 = -1073741816;
      DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v7);
      return v3;
    }
    *a3 = a1;
  }
  else
  {
    v3 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c",
        216);
  }
  return v3;
}

```

## disassembly

```asm
0x18005196c  push    rbx
0x18005196e  sub     rsp, 40h
0x180051972  xor     ebx, ebx
0x180051974  mov     r9d, edx
0x180051977  test    rcx, rcx
0x18005197a  jz      short loc_1800519BE
0x18005197c  test    r8, r8
0x18005197f  jz      short loc_1800519BE
0x180051981  cmp     dword ptr [rcx+4], 4D534B59h
0x180051988  jnz     loc_180051A1E
0x18005198e  cmp     dword ptr [rcx+8], 30003h
0x180051995  jnz     loc_180051A1E
0x18005199b  mov     edx, [rcx+0Ch]
0x18005199e  lea     eax, [rdx-40h]
0x1800519a1  cmp     eax, 140h
0x1800519a6  ja      short loc_180051A1E
0x1800519a8  test    dl, 7
0x1800519ab  jnz     short loc_180051A1E
0x1800519ad  test    r9d, r9d
0x1800519b0  jnz     short loc_180051A0A
0x1800519b2  mov     [r8], rcx
0x1800519b5  mov     eax, ebx
0x1800519b7  add     rsp, 40h
0x1800519bb  pop     rbx
0x1800519bc  retn
0x1800519be  mov     ebx, 0C0000008h
0x1800519c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800519ca  lea     rax, WPP_GLOBAL_Control
0x1800519d1  cmp     rcx, rax
0x1800519d4  jz      short loc_1800519B5
0x1800519d6  test    byte ptr [rcx+1Ch], 1
0x1800519da  jz      short loc_1800519B5
0x1800519dc  mov     rcx, [rcx+10h]
0x1800519e0  lea     rax, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800519e7  mov     [rsp+48h+var_18], 0D8h
0x1800519ef  lea     r9, aStatus; "Status"
0x1800519f6  mov     [rsp+48h+var_20], rax
0x1800519fb  mov     [rsp+48h+var_28], 0C0000008h
0x180051a03  call    WPP_SF_sDsd
0x180051a08  jmp     short loc_1800519B5
0x180051a0a  mov     rax, [rcx+28h]
0x180051a0e  cmp     [rax+4], bl
0x180051a11  jnz     short loc_1800519B2
0x180051a13  mov     r9d, 0F3h
0x180051a19  jmp     loc_180082BA2
0x180051a1e  mov     r9d, 0E9h
0x180051a24  jmp     loc_180082BA2
0x180082ba2  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180082ba9  mov     ecx, 0C0000008h
0x180082bae  lea     rdx, aStatus; "Status"
0x180082bb5  mov     ebx, 0C0000008h
0x180082bba  call    DebugTraceError
0x180082bbf  nop
0x180082bc0  jmp     loc_1800519B5
```
