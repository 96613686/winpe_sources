# ValidateDSAAlgorithm

- ea: `0x180052794`
- end: `0x180052871`
- name: `ValidateDSAAlgorithm`
- size: `221`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180051820`
- `0x180069710`
- `0x180069c80`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180052794`

## string_xrefs

- `0x1800527c5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x180052840`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall ValidateDSAAlgorithm(_DWORD *a1, unsigned int a2, int *a3, _QWORD *a4)
{
  __int64 v4; // r9
  unsigned int v5; // ebx
  int v6; // edx

  if ( a1 && a3 && a4 )
  {
    if ( a2 && ((a2 & 0x3F) != 0 || a2 - 512 > 0xA00) )
    {
      v4 = 161;
LABEL_8:
      v5 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v4);
      return v5;
    }
    if ( *a1 != 16 || a1[1] != 1297301836 || a1[2] != 196611 )
    {
      v4 = 175;
      goto LABEL_8;
    }
    v5 = 0;
    if ( a2 )
      v6 = a2 >> 3;
    else
      v6 = 128;
    *a3 = v6;
    *a4 = a1;
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
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c",
        148);
  }
  return v5;
}

```

## disassembly

```asm
0x180052794  push    rbx
0x180052796  sub     rsp, 40h
0x18005279a  test    rcx, rcx
0x18005279d  jz      short loc_18005281E
0x18005279f  test    r8, r8
0x1800527a2  jz      short loc_18005281E
0x1800527a4  test    r9, r9
0x1800527a7  jz      short loc_18005281E
0x1800527a9  test    edx, edx
0x1800527ab  jz      short loc_1800527E7
0x1800527ad  test    dl, 3Fh
0x1800527b0  jnz     short loc_1800527BF
0x1800527b2  lea     eax, [rdx-200h]
0x1800527b8  cmp     eax, 0A00h
0x1800527bd  jbe     short loc_1800527E7
0x1800527bf  mov     r9d, 0A1h
0x1800527c5  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800527cc  mov     ecx, 0C000000Dh
0x1800527d1  lea     rdx, aStatus; "Status"
0x1800527d8  mov     ebx, 0C000000Dh
0x1800527dd  call    DebugTraceError
0x1800527e2  jmp     loc_180052868
0x1800527e7  cmp     dword ptr [rcx], 10h
0x1800527ea  jnz     short loc_180052816
0x1800527ec  cmp     dword ptr [rcx+4], 4D53414Ch
0x1800527f3  jnz     short loc_180052816
0x1800527f5  cmp     dword ptr [rcx+8], 30003h
0x1800527fc  jnz     short loc_180052816
0x1800527fe  xor     ebx, ebx
0x180052800  test    edx, edx
0x180052802  jnz     short loc_18005280B
0x180052804  mov     edx, 80h
0x180052809  jmp     short loc_18005280E
0x18005280b  shr     edx, 3
0x18005280e  mov     [r8], edx
0x180052811  mov     [r9], rcx
0x180052814  jmp     short loc_180052868
0x180052816  mov     r9d, 0AFh
0x18005281c  jmp     short loc_1800527C5
0x18005281e  mov     ebx, 0C000000Dh
0x180052823  mov     rcx, cs:WPP_GLOBAL_Control
0x18005282a  lea     rax, WPP_GLOBAL_Control
0x180052831  cmp     rcx, rax
0x180052834  jz      short loc_180052868
0x180052836  test    byte ptr [rcx+1Ch], 1
0x18005283a  jz      short loc_180052868
0x18005283c  mov     rcx, [rcx+10h]
0x180052840  lea     rax, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052847  mov     [rsp+48h+var_18], 94h
0x18005284f  lea     r9, aStatus; "Status"
0x180052856  mov     [rsp+48h+var_20], rax
0x18005285b  mov     [rsp+48h+var_28], 0C000000Dh
0x180052863  call    WPP_SF_sDsd
0x180052868  mov     eax, ebx
0x18005286a  add     rsp, 40h
0x18005286e  pop     rbx
0x18005286f  retn
```
