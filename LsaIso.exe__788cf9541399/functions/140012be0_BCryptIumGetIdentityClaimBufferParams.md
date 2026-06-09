# BCryptIumGetIdentityClaimBufferParams

- ea: `0x140012be0`
- end: `0x140012d1b`
- name: `BCryptIumGetIdentityClaimBufferParams`
- size: `315`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012ee8`

## callees

- `0x140012be0`
- `0x140037b10`

## string_xrefs

- `0x140012d05`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`

## pseudocode

```c
__int64 __fastcall BCryptIumGetIdentityClaimBufferParams(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  unsigned int v3; // ebx
  unsigned int v4; // r10d
  __int64 v5; // r11
  unsigned int i; // r9d
  __int64 v7; // r8

  if ( !a2 )
  {
    v2 = 59;
LABEL_36:
    v3 = -1073741811;
    VBS_ATTEST_TRACE_ERROR_IN(
      3221225485LL,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
      v2);
    return v3;
  }
  *(_OWORD *)a2 = 0;
  v3 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  if ( a1 )
  {
    if ( *(_DWORD *)a1 || (v4 = *(_DWORD *)(a1 + 4), v4 - 1 > 4) || (v5 = *(_QWORD *)(a1 + 8)) == 0 )
    {
      v2 = 79;
      goto LABEL_36;
    }
    for ( i = 0; i < v4 && i < 5; ++i )
    {
      v7 = v5 + 16LL * i;
      if ( !v7 || !*(_QWORD *)(v7 + 8) )
      {
        v2 = 149;
        goto LABEL_36;
      }
      switch ( *(_DWORD *)(v7 + 4) )
      {
        case '1':
          if ( *(_QWORD *)a2 )
          {
            v2 = 135;
            goto LABEL_36;
          }
          *(_QWORD *)a2 = v7;
          break;
        case 'Z':
          if ( *(_QWORD *)(a2 + 8) )
          {
            v2 = 95;
            goto LABEL_36;
          }
          *(_QWORD *)(a2 + 8) = v7;
          break;
        case '[':
          if ( *(_QWORD *)(a2 + 16) )
          {
            v2 = 105;
            goto LABEL_36;
          }
          *(_QWORD *)(a2 + 16) = v7;
          break;
        case '\\':
          if ( *(_QWORD *)(a2 + 24) )
          {
            v2 = 115;
            goto LABEL_36;
          }
          *(_QWORD *)(a2 + 24) = v7;
          break;
        case ']':
          if ( *(_QWORD *)(a2 + 32) )
          {
            v2 = 125;
            goto LABEL_36;
          }
          *(_QWORD *)(a2 + 32) = v7;
          break;
        default:
          v2 = 142;
          goto LABEL_36;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140012be0  push    rbx
0x140012be2  sub     rsp, 20h
0x140012be6  test    rdx, rdx
0x140012be9  jnz     short loc_140012BF4
0x140012beb  lea     r8d, [rdx+3Bh]
0x140012bef  jmp     loc_140012D00
0x140012bf4  xorps   xmm0, xmm0
0x140012bf7  xor     eax, eax
0x140012bf9  movups  xmmword ptr [rdx], xmm0
0x140012bfc  xor     ebx, ebx
0x140012bfe  movups  xmmword ptr [rdx+10h], xmm0
0x140012c02  mov     [rdx+20h], rax
0x140012c06  test    rcx, rcx
0x140012c09  jz      loc_140012D13
0x140012c0f  cmp     [rcx], eax
0x140012c11  jnz     loc_140012CFA
0x140012c17  mov     r10d, [rcx+4]
0x140012c1b  lea     eax, [r10-1]
0x140012c1f  cmp     eax, 4
0x140012c22  ja      loc_140012CFA
0x140012c28  mov     r11, [rcx+8]
0x140012c2c  test    r11, r11
0x140012c2f  jz      loc_140012CFA
0x140012c35  xor     r9d, r9d
0x140012c38  cmp     r9d, r10d
0x140012c3b  jnb     loc_140012D13
0x140012c41  cmp     r9d, 5
0x140012c45  jnb     loc_140012D13
0x140012c4b  mov     r8d, r9d
0x140012c4e  shl     r8, 4
0x140012c52  add     r8, r11
0x140012c55  jz      loc_140012CF2
0x140012c5b  cmp     [r8+8], rbx
0x140012c5f  jz      loc_140012CF2
0x140012c65  mov     ecx, [r8+4]
0x140012c69  sub     ecx, 31h ; '1'
0x140012c6c  jz      short loc_140012CB2
0x140012c6e  sub     ecx, 29h ; ')'
0x140012c71  jz      short loc_140012CA6
0x140012c73  sub     ecx, 1
0x140012c76  jz      short loc_140012C9A
0x140012c78  sub     ecx, 1
0x140012c7b  jz      short loc_140012C8E
0x140012c7d  cmp     ecx, 1
0x140012c80  jnz     short loc_140012CCA
0x140012c82  cmp     [rdx+20h], rbx
0x140012c86  jnz     short loc_140012CC2
0x140012c88  mov     [rdx+20h], r8
0x140012c8c  jmp     short loc_140012CBA
0x140012c8e  cmp     [rdx+18h], rbx
0x140012c92  jnz     short loc_140012CD2
0x140012c94  mov     [rdx+18h], r8
0x140012c98  jmp     short loc_140012CBA
0x140012c9a  cmp     [rdx+10h], rbx
0x140012c9e  jnz     short loc_140012CDA
0x140012ca0  mov     [rdx+10h], r8
0x140012ca4  jmp     short loc_140012CBA
0x140012ca6  cmp     [rdx+8], rbx
0x140012caa  jnz     short loc_140012CE2
0x140012cac  mov     [rdx+8], r8
0x140012cb0  jmp     short loc_140012CBA
0x140012cb2  cmp     [rdx], rbx
0x140012cb5  jnz     short loc_140012CEA
0x140012cb7  mov     [rdx], r8
0x140012cba  inc     r9d
0x140012cbd  jmp     loc_140012C38
0x140012cc2  mov     r8d, 7Dh ; '}'
0x140012cc8  jmp     short loc_140012D00
0x140012cca  mov     r8d, 8Eh
0x140012cd0  jmp     short loc_140012D00
0x140012cd2  mov     r8d, 73h ; 's'
0x140012cd8  jmp     short loc_140012D00
0x140012cda  mov     r8d, 69h ; 'i'
0x140012ce0  jmp     short loc_140012D00
0x140012ce2  mov     r8d, 5Fh ; '_'
0x140012ce8  jmp     short loc_140012D00
0x140012cea  mov     r8d, 87h
0x140012cf0  jmp     short loc_140012D00
0x140012cf2  mov     r8d, 95h
0x140012cf8  jmp     short loc_140012D00
0x140012cfa  mov     r8d, 4Fh ; 'O'
0x140012d00  mov     ecx, 0C000000Dh
0x140012d05  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140012d0c  mov     ebx, ecx
0x140012d0e  call    VBS_ATTEST_TRACE_ERROR_IN
0x140012d13  mov     eax, ebx
0x140012d15  add     rsp, 20h
0x140012d19  pop     rbx
0x140012d1a  retn
```
