# MSCryptEccSetProperty

- ea: `0x180021de0`
- end: `0x180021f67`
- name: `MSCryptEccSetProperty`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004fb50`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800216d8`
- `0x180021de0`
- `0x180021f70`

## string_xrefs

- `0x180021e5a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180021ec7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180021ed9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180021f42`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccSetProperty(_DWORD *a1, const wchar_t *a2, _DWORD *a3, unsigned int a4, int a5, int a6)
{
  int v6; // eax
  int v7; // eax
  unsigned int v8; // ebx
  int v10; // edx
  int v11; // r8d
  int v12; // edx
  int v13; // r8d
  __int64 v14; // r9

  if ( a5 )
  {
    v8 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        112);
    return v8;
  }
  if ( !a1 || *a1 < 0xCu )
  {
    v14 = 445;
    goto LABEL_17;
  }
  v6 = a1[1];
  if ( v6 == 1297304409 )
  {
    v7 = MSCryptEccSetKeyProperty((__int64)a1, a2, a3, a4, a6);
    v8 = v7;
    if ( v7 < 0 )
    {
      DebugTraceError((unsigned int)v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 3976);
      return v8;
    }
    return 0;
  }
  if ( v6 != 1297301836 )
  {
    v14 = 453;
LABEL_17:
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v14);
    v8 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        v13,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        119);
    return v8;
  }
  v8 = MSCryptEccSetAlgProperty(a1);
  if ( (v8 & 0x80000000) == 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v11,
      (unsigned int)"Status",
      v8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      149);
  return v8;
}

```

## disassembly

```asm
0x180021de0  mov     [rsp+arg_0], rbx
0x180021de5  push    rdi
0x180021de6  sub     rsp, 40h
0x180021dea  cmp     [rsp+48h+arg_20], 0
0x180021def  jnz     short loc_180021E34
0x180021df1  test    rcx, rcx
0x180021df4  jz      loc_180021F5C
0x180021dfa  cmp     dword ptr [rcx], 0Ch
0x180021dfd  jb      loc_180021F5C
0x180021e03  mov     eax, [rcx+4]
0x180021e06  cmp     eax, 4D534B59h
0x180021e0b  jnz     short loc_180021E80
0x180021e0d  mov     eax, [rsp+48h+arg_28]
0x180021e11  mov     [rsp+48h+var_28], eax
0x180021e15  call    MSCryptEccSetKeyProperty
0x180021e1a  mov     ebx, eax
0x180021e1c  test    eax, eax
0x180021e1e  js      loc_180021F3C
0x180021e24  xor     ebx, ebx
0x180021e26  mov     eax, ebx
0x180021e28  mov     rbx, [rsp+48h+arg_0]
0x180021e2d  add     rsp, 40h
0x180021e31  pop     rdi
0x180021e32  retn
0x180021e34  mov     ebx, 0C000000Dh
0x180021e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e40  lea     rax, WPP_GLOBAL_Control
0x180021e47  cmp     rcx, rax
0x180021e4a  jz      short loc_180021E26
0x180021e4c  test    byte ptr [rcx+1Ch], 1
0x180021e50  jz      short loc_180021E26
0x180021e52  mov     [rsp+48h+var_18], 0F70h
0x180021e5a  lea     rdi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021e61  mov     [rsp+48h+var_20], rdi
0x180021e66  mov     [rsp+48h+var_28], 0C000000Dh
0x180021e6e  mov     rcx, [rcx+10h]
0x180021e72  lea     r9, aStatus; "Status"
0x180021e79  call    WPP_SF_sDsd
0x180021e7e  jmp     short loc_180021E26
0x180021e80  cmp     eax, 4D53414Ch
0x180021e85  jnz     loc_180021F34
0x180021e8b  mov     eax, [rsp+48h+arg_28]
0x180021e8f  mov     [rsp+48h+var_28], eax
0x180021e93  call    MSCryptEccSetAlgProperty
0x180021e98  mov     ebx, eax
0x180021e9a  test    eax, eax
0x180021e9c  jns     short loc_180021E24
0x180021e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ea5  lea     rax, WPP_GLOBAL_Control
0x180021eac  cmp     rcx, rax
0x180021eaf  jz      loc_180021E26
0x180021eb5  test    byte ptr [rcx+1Ch], 1
0x180021eb9  jz      loc_180021E26
0x180021ebf  mov     [rsp+48h+var_18], 0F95h
0x180021ec7  lea     rdi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021ece  mov     [rsp+48h+var_20], rdi
0x180021ed3  mov     [rsp+48h+var_28], ebx
0x180021ed7  jmp     short loc_180021E6E
0x180021ed9  lea     rdi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021ee0  mov     ecx, 0C0000008h
0x180021ee5  mov     r8, rdi
0x180021ee8  lea     rdx, aStatus; "Status"
0x180021eef  call    DebugTraceError
0x180021ef4  mov     ebx, 0C0000008h
0x180021ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f00  lea     rax, WPP_GLOBAL_Control
0x180021f07  cmp     rcx, rax
0x180021f0a  jz      loc_180021E26
0x180021f10  test    byte ptr [rcx+1Ch], 1
0x180021f14  jz      loc_180021E26
0x180021f1a  mov     [rsp+48h+var_18], 0F77h
0x180021f22  mov     [rsp+48h+var_20], rdi
0x180021f27  mov     [rsp+48h+var_28], 0C0000008h
0x180021f2f  jmp     loc_180021E6E
0x180021f34  mov     r9d, 1C5h
0x180021f3a  jmp     short loc_180021ED9
0x180021f3c  mov     r9d, 0F88h
0x180021f42  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021f49  lea     rdx, aStatus; "Status"
0x180021f50  mov     ecx, eax
0x180021f52  call    DebugTraceError
0x180021f57  jmp     loc_180021E26
0x180021f5c  mov     r9d, 1BDh
0x180021f62  jmp     loc_180021ED9
```
