# MSCryptKDOpenProvider

- ea: `0x18004eef0`
- end: `0x18004f100`
- name: `MSCryptKDOpenProvider`
- size: `528`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800102a0`
- `0x18004eef0`
- `0x18007f765`

## string_xrefs

- `0x18004f03e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18004f092`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18004f0b6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDOpenProvider(_QWORD *a1, const wchar_t *a2, int a3)
{
  char v3; // di
  int v6; // edx
  int v7; // r8d
  int v8; // ebx
  _DWORD *v9; // rax
  int v10; // edx
  int v11; // r8d
  unsigned int v12; // ebx
  __int64 v14; // r9

  v3 = a3;
  if ( !a1 )
  {
    v14 = 396;
LABEL_25:
    v12 = -1073741811;
    DebugTraceError(
      3221225485LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v14);
    return v12;
  }
  if ( (a3 & 0xFFFFFFFE) != 0 )
  {
    v14 = 403;
    goto LABEL_25;
  }
  if ( !wcscmp_0(a2, L"SP800_108_CTR_HMAC") )
  {
    v8 = 393217;
    goto LABEL_11;
  }
  if ( !wcscmp_0(a2, L"SP800_56A_CONCAT") )
  {
    v8 = 393218;
    goto LABEL_11;
  }
  if ( !wcscmp_0(a2, L"PBKDF2") )
  {
    v8 = 393219;
    goto LABEL_11;
  }
  if ( !wcscmp_0(a2, L"CAPI_KDF") )
  {
    v8 = 393220;
    goto LABEL_11;
  }
  if ( !wcscmp_0(a2, L"TLS1_1_KDF") )
  {
    v8 = 393221;
    goto LABEL_11;
  }
  if ( !wcscmp_0(a2, L"TLS1_2_KDF") )
  {
    v8 = 393222;
LABEL_11:
    v9 = (_DWORD *)SafeAllocaAllocateFromHeap(20);
    if ( v9 )
    {
      v9[2] = v8;
      v9[4] = v3 & 1;
      v12 = 0;
      *v9 = 20;
      v9[1] = 1297301836;
      v9[3] = 640;
      *a1 = v9;
    }
    else
    {
      v12 = -1073741801;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          v11,
          (unsigned int)"Status",
          23,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
          206);
    }
    return v12;
  }
  if ( !wcscmp_0(a2, L"HKDF") )
  {
    v8 = 393223;
    goto LABEL_11;
  }
  v12 = -1073741637;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      v7,
      (unsigned int)"Status",
      187,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      192);
  return v12;
}

```

## disassembly

```asm
0x18004eef0  mov     [rsp+arg_0], rbx
0x18004eef5  mov     [rsp+arg_8], rsi
0x18004eefa  push    rdi
0x18004eefb  sub     rsp, 40h
0x18004eeff  mov     edi, r8d
0x18004ef02  mov     rbx, rdx
0x18004ef05  mov     rsi, rcx
0x18004ef08  test    rcx, rcx
0x18004ef0b  jz      loc_18004F0A8
0x18004ef11  test    r8d, 0FFFFFFFEh
0x18004ef18  jnz     loc_18004F0B0
0x18004ef1e  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x18004ef25  mov     rcx, rbx; String1
0x18004ef28  call    wcscmp_0
0x18004ef2d  test    eax, eax
0x18004ef2f  jz      loc_18004F02F
0x18004ef35  lea     rdx, aSp80056aConcat; "SP800_56A_CONCAT"
0x18004ef3c  mov     rcx, rbx; String1
0x18004ef3f  call    wcscmp_0
0x18004ef44  test    eax, eax
0x18004ef46  jz      loc_18004F0D8
0x18004ef4c  lea     rdx, aPbkdf2; "PBKDF2"
0x18004ef53  mov     rcx, rbx; String1
0x18004ef56  call    wcscmp_0
0x18004ef5b  test    eax, eax
0x18004ef5d  jz      loc_18004F028
0x18004ef63  lea     rdx, aCapiKdf; "CAPI_KDF"
0x18004ef6a  mov     rcx, rbx; String1
0x18004ef6d  call    wcscmp_0
0x18004ef72  test    eax, eax
0x18004ef74  jz      loc_18004F0E2
0x18004ef7a  lea     rdx, aTls11Kdf; "TLS1_1_KDF"
0x18004ef81  mov     rcx, rbx; String1
0x18004ef84  call    wcscmp_0
0x18004ef89  test    eax, eax
0x18004ef8b  jz      loc_18004F0EC
0x18004ef91  lea     rdx, aTls12Kdf; "TLS1_2_KDF"
0x18004ef98  mov     rcx, rbx; String1
0x18004ef9b  call    wcscmp_0
0x18004efa0  test    eax, eax
0x18004efa2  jz      loc_18004F0F6
0x18004efa8  lea     rdx, aHkdf; "HKDF"
0x18004efaf  mov     rcx, rbx; String1
0x18004efb2  call    wcscmp_0
0x18004efb7  test    eax, eax
0x18004efb9  jnz     loc_18004F064
0x18004efbf  mov     ebx, 60007h
0x18004efc4  mov     ecx, 14h
0x18004efc9  call    SafeAllocaAllocateFromHeap
0x18004efce  test    rax, rax
0x18004efd1  jnz     short loc_18004F004
0x18004efd3  mov     ebx, 0C0000017h
0x18004efd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004efdf  lea     rax, WPP_GLOBAL_Control
0x18004efe6  cmp     rcx, rax
0x18004efe9  jz      short loc_18004EFF1
0x18004efeb  test    byte ptr [rcx+1Ch], 1
0x18004efef  jnz     short loc_18004F036
0x18004eff1  mov     rsi, [rsp+48h+arg_8]
0x18004eff6  mov     eax, ebx
0x18004eff8  mov     rbx, [rsp+48h+arg_0]
0x18004effd  add     rsp, 40h
0x18004f001  pop     rdi
0x18004f002  retn
0x18004f004  and     edi, 1
0x18004f007  mov     [rax+8], ebx
0x18004f00a  mov     [rax+10h], edi
0x18004f00d  xor     ebx, ebx
0x18004f00f  mov     dword ptr [rax], 14h
0x18004f015  mov     dword ptr [rax+4], 4D53414Ch
0x18004f01c  mov     dword ptr [rax+0Ch], 280h
0x18004f023  mov     [rsi], rax
0x18004f026  jmp     short loc_18004EFF1
0x18004f028  mov     ebx, 60003h
0x18004f02d  jmp     short loc_18004EFC4
0x18004f02f  mov     ebx, 60001h
0x18004f034  jmp     short loc_18004EFC4
0x18004f036  mov     [rsp+48h+var_18], 1CEh
0x18004f03e  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004f045  mov     [rsp+48h+var_20], rax
0x18004f04a  mov     [rsp+48h+var_28], 0C0000017h
0x18004f052  mov     rcx, [rcx+10h]
0x18004f056  lea     r9, aStatus; "Status"
0x18004f05d  call    WPP_SF_sDsd
0x18004f062  jmp     short loc_18004EFF1
0x18004f064  mov     ebx, 0C00000BBh
0x18004f069  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f070  lea     rax, WPP_GLOBAL_Control
0x18004f077  cmp     rcx, rax
0x18004f07a  jz      loc_18004EFF1
0x18004f080  test    byte ptr [rcx+1Ch], 1
0x18004f084  jz      loc_18004EFF1
0x18004f08a  mov     [rsp+48h+var_18], 1C0h
0x18004f092  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004f099  mov     [rsp+48h+var_20], rax
0x18004f09e  mov     [rsp+48h+var_28], 0C00000BBh
0x18004f0a6  jmp     short loc_18004F052
0x18004f0a8  mov     r9d, 18Ch
0x18004f0ae  jmp     short loc_18004F0B6
0x18004f0b0  mov     r9d, 193h
0x18004f0b6  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004f0bd  mov     ecx, 0C000000Dh
0x18004f0c2  lea     rdx, aStatus; "Status"
0x18004f0c9  mov     ebx, 0C000000Dh
0x18004f0ce  call    DebugTraceError
0x18004f0d3  jmp     loc_18004EFF1
0x18004f0d8  mov     ebx, 60002h
0x18004f0dd  jmp     loc_18004EFC4
0x18004f0e2  mov     ebx, 60004h
0x18004f0e7  jmp     loc_18004EFC4
0x18004f0ec  mov     ebx, 60005h
0x18004f0f1  jmp     loc_18004EFC4
0x18004f0f6  mov     ebx, 60006h
0x18004f0fb  jmp     loc_18004EFC4
```
