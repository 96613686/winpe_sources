# MSCryptEcDhSetProperty

- ea: `0x180021c50`
- end: `0x180021dd1`
- name: `MSCryptEcDhSetProperty`
- size: `385`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800216d8`
- `0x180021c50`
- `0x180021f70`

## string_xrefs

- `0x180021cc6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180021d31`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180021d43`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180021dac`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEcDhSetProperty(_DWORD *a1, const wchar_t *a2, _DWORD *a3, unsigned int a4, int a5)
{
  int v5; // eax
  unsigned int v6; // edi
  int v8; // edx
  int v9; // r8d
  int v10; // edx
  int v11; // r8d
  __int64 v12; // r9

  if ( a5 )
  {
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        112);
    return v6;
  }
  if ( !a1 || *a1 < 0xCu )
  {
    v12 = 445;
    goto LABEL_17;
  }
  if ( a1[1] == 1297304409 )
  {
    v5 = MSCryptEccSetKeyProperty((__int64)a1, a2, a3, a4, 0);
    v6 = v5;
    if ( v5 < 0 )
    {
      DebugTraceError((unsigned int)v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 3976);
      return v6;
    }
    return 0;
  }
  if ( a1[1] != 1297301836 )
  {
    v12 = 453;
LABEL_17:
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v12);
    v6 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        v11,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        119);
    return v6;
  }
  v6 = MSCryptEccSetAlgProperty(a1);
  if ( (v6 & 0x80000000) == 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v9,
      (unsigned int)"Status",
      v6,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      149);
  return v6;
}

```

## disassembly

```asm
0x180021c50  mov     [rsp+arg_0], rbx
0x180021c55  push    rdi
0x180021c56  sub     rsp, 40h
0x180021c5a  xor     ebx, ebx
0x180021c5c  cmp     [rsp+48h+arg_20], ebx
0x180021c60  jnz     short loc_180021CA0
0x180021c62  test    rcx, rcx
0x180021c65  jz      loc_180021DC6
0x180021c6b  cmp     dword ptr [rcx], 0Ch
0x180021c6e  jb      loc_180021DC6
0x180021c74  cmp     dword ptr [rcx+4], 4D534B59h
0x180021c7b  jnz     short loc_180021CEC
0x180021c7d  mov     [rsp+48h+var_28], ebx
0x180021c81  call    MSCryptEccSetKeyProperty
0x180021c86  mov     edi, eax
0x180021c88  test    eax, eax
0x180021c8a  js      loc_180021DA6
0x180021c90  mov     edi, ebx
0x180021c92  mov     rbx, [rsp+48h+arg_0]
0x180021c97  mov     eax, edi
0x180021c99  add     rsp, 40h
0x180021c9d  pop     rdi
0x180021c9e  retn
0x180021ca0  mov     edi, 0C000000Dh
0x180021ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x180021cac  lea     rax, WPP_GLOBAL_Control
0x180021cb3  cmp     rcx, rax
0x180021cb6  jz      short loc_180021C92
0x180021cb8  test    byte ptr [rcx+1Ch], 1
0x180021cbc  jz      short loc_180021C92
0x180021cbe  mov     [rsp+48h+var_18], 0F70h
0x180021cc6  lea     rbx, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021ccd  mov     [rsp+48h+var_20], rbx
0x180021cd2  mov     [rsp+48h+var_28], 0C000000Dh
0x180021cda  mov     rcx, [rcx+10h]
0x180021cde  lea     r9, aStatus; "Status"
0x180021ce5  call    WPP_SF_sDsd
0x180021cea  jmp     short loc_180021C92
0x180021cec  cmp     dword ptr [rcx+4], 4D53414Ch
0x180021cf3  jnz     loc_180021D9E
0x180021cf9  mov     [rsp+48h+var_28], ebx
0x180021cfd  call    MSCryptEccSetAlgProperty
0x180021d02  mov     edi, eax
0x180021d04  test    eax, eax
0x180021d06  jns     short loc_180021C90
0x180021d08  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d0f  lea     rax, WPP_GLOBAL_Control
0x180021d16  cmp     rcx, rax
0x180021d19  jz      loc_180021C92
0x180021d1f  test    byte ptr [rcx+1Ch], 1
0x180021d23  jz      loc_180021C92
0x180021d29  mov     [rsp+48h+var_18], 0F95h
0x180021d31  lea     rbx, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021d38  mov     [rsp+48h+var_20], rbx
0x180021d3d  mov     [rsp+48h+var_28], edi
0x180021d41  jmp     short loc_180021CDA
0x180021d43  lea     rbx, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021d4a  mov     r8, rbx
0x180021d4d  lea     rdx, aStatus; "Status"
0x180021d54  mov     ecx, 0C0000008h
0x180021d59  call    DebugTraceError
0x180021d5e  mov     edi, 0C0000008h
0x180021d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d6a  lea     rax, WPP_GLOBAL_Control
0x180021d71  cmp     rcx, rax
0x180021d74  jz      loc_180021C92
0x180021d7a  test    byte ptr [rcx+1Ch], 1
0x180021d7e  jz      loc_180021C92
0x180021d84  mov     [rsp+48h+var_18], 0F77h
0x180021d8c  mov     [rsp+48h+var_20], rbx
0x180021d91  mov     [rsp+48h+var_28], 0C0000008h
0x180021d99  jmp     loc_180021CDA
0x180021d9e  mov     r9d, 1C5h
0x180021da4  jmp     short loc_180021D43
0x180021da6  mov     r9d, 0F88h
0x180021dac  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021db3  lea     rdx, aStatus; "Status"
0x180021dba  mov     ecx, eax
0x180021dbc  call    DebugTraceError
0x180021dc1  jmp     loc_180021C92
0x180021dc6  mov     r9d, 1BDh
0x180021dcc  jmp     loc_180021D43
```
