# MSCryptKDGetKeyProperty

- ea: `0x18004729c`
- end: `0x1800473a2`
- name: `MSCryptKDGetKeyProperty`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000cc40`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18004729c`
- `0x1800473b0`
- `0x18007f765`

## string_xrefs

- `0x180047306`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18004734e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDGetKeyProperty(__int64 a1, const wchar_t *a2, _DWORD *a3, unsigned int a4, int *a5)
{
  int v8; // edi
  int v9; // ebx
  int v10; // edx
  int v11; // r8d
  _QWORD v13[9]; // [rsp+40h] [rbp-48h] BYREF

  v13[0] = 0;
  v8 = *a5;
  v9 = ValidateKeyDerivationKey(a1, v13);
  if ( v9 >= 0 )
  {
    if ( !wcscmp_0(a2, L"KeyLength") || !wcscmp_0(a2, L"KeyStrength") )
    {
      v8 = 4;
      if ( a3 )
      {
        if ( a4 >= 4 )
        {
          *a3 = 8 * *(_DWORD *)(v13[0] + 16LL);
          v9 = 0;
        }
        else
        {
          v9 = -1073741789;
        }
      }
      else
      {
        v9 = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v10,
            v11,
            (unsigned int)"Status",
            0,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
            31);
      }
    }
    else
    {
      v9 = -1073741637;
      DebugTraceError(
        3221225659LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        815);
    }
  }
  *a5 = v8;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004729c  push    rbx
0x18004729e  push    rbp
0x18004729f  push    rsi
0x1800472a0  push    rdi
0x1800472a1  push    r14
0x1800472a3  push    r15
0x1800472a5  sub     rsp, 58h
0x1800472a9  mov     r14, [rsp+88h+arg_20]
0x1800472b1  mov     rbp, rdx
0x1800472b4  lea     rdx, [rsp+88h+var_48]
0x1800472b9  mov     [rsp+88h+var_48], 0
0x1800472c2  mov     r15d, r9d
0x1800472c5  mov     rsi, r8
0x1800472c8  mov     edi, [r14]
0x1800472cb  call    ValidateKeyDerivationKey
0x1800472d0  mov     ebx, eax
0x1800472d2  test    eax, eax
0x1800472d4  js      loc_18004738F
0x1800472da  lea     rdx, aKeylength; "KeyLength"
0x1800472e1  mov     rcx, rbp; String1
0x1800472e4  call    wcscmp_0
0x1800472e9  test    eax, eax
0x1800472eb  jz      short loc_180047325
0x1800472ed  lea     rdx, aKeystrength; "KeyStrength"
0x1800472f4  mov     rcx, rbp; String1
0x1800472f7  call    wcscmp_0
0x1800472fc  test    eax, eax
0x1800472fe  jz      short loc_180047325
0x180047300  mov     r9d, 32Fh
0x180047306  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004730d  lea     rdx, aStatus; "Status"
0x180047314  mov     ecx, 0C00000BBh
0x180047319  mov     ebx, 0C00000BBh
0x18004731e  call    DebugTraceError
0x180047323  jmp     short loc_18004738F
0x180047325  mov     edi, 4
0x18004732a  test    rsi, rsi
0x18004732d  jnz     short loc_180047374
0x18004732f  xor     ebx, ebx
0x180047331  mov     rcx, cs:WPP_GLOBAL_Control
0x180047338  lea     rax, WPP_GLOBAL_Control
0x18004733f  cmp     rcx, rax
0x180047342  jz      short loc_18004738F
0x180047344  test    byte ptr [rcx+1Ch], 1
0x180047348  jz      short loc_18004738F
0x18004734a  mov     rcx, [rcx+10h]
0x18004734e  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047355  mov     [rsp+88h+var_58], 31Fh
0x18004735d  lea     r9, aStatus; "Status"
0x180047364  mov     [rsp+88h+var_60], rax
0x180047369  mov     [rsp+88h+var_68], ebx
0x18004736d  call    WPP_SF_sDsd
0x180047372  jmp     short loc_18004738F
0x180047374  cmp     r15d, edi
0x180047377  jnb     short loc_180047380
0x180047379  mov     ebx, 0C0000023h
0x18004737e  jmp     short loc_18004738F
0x180047380  mov     rax, [rsp+88h+var_48]
0x180047385  mov     ecx, [rax+10h]
0x180047388  shl     ecx, 3
0x18004738b  mov     [rsi], ecx
0x18004738d  xor     ebx, ebx
0x18004738f  mov     [r14], edi
0x180047392  mov     eax, ebx
0x180047394  add     rsp, 58h
0x180047398  pop     r15
0x18004739a  pop     r14
0x18004739c  pop     rdi
0x18004739d  pop     rsi
0x18004739e  pop     rbp
0x18004739f  pop     rbx
0x1800473a0  retn
```
