# ReservedForLocalUse::IsStringProhibited<ushort>(unsigned __int64,ushort const *)

- ea: `0x18000cee0`
- end: `0x18000cfd5`
- name: `??$IsStringProhibited@G@ReservedForLocalUse@@YA_N_KPEBG@Z`
- size: `245`
- prototype: `char __fastcall(unsigned __int64 cchCount1, LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e444`

## callees

- `0x18000cee0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cf26`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cf67`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cfc1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cf26`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cf67`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cfc1`

## pseudocode

```c
char __fastcall ReservedForLocalUse::IsStringProhibited<unsigned short>(unsigned __int64 cchCount1, LPCWCH lpString1)
{
  unsigned __int64 i; // rbx
  __int64 v5; // r9
  unsigned __int64 j; // rbx
  unsigned __int64 v7; // rdx
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rdi

  for ( i = 0; i < 0x18; ++i )
  {
    v5 = (unsigned int)dword_18004E190[4 * i];
    if ( cchCount1 == v5 && CompareStringOrdinal(lpString1, cchCount1, (&off_18004E198)[2 * i], v5, 1) == 2 )
      return 1;
  }
  for ( j = 0; j < 0x17; ++j )
  {
    v7 = (unsigned int)dword_18004E020[4 * j];
    if ( cchCount1 >= v7 && CompareStringOrdinal(lpString1, v7, (&off_18004E028)[2 * j], v7, 1) == 2 )
      return 1;
  }
  if ( cchCount1 && lpString1[cchCount1 - 1] == 46 )
    return 1;
  if ( cchCount1 >= 5 )
  {
    v9 = 0;
    v10 = cchCount1 - 5;
    while ( v9 <= v10 )
    {
      if ( CompareStringOrdinal(&lpString1[v9], 5, L".xn--", 5, 1) == 2 )
        return 1;
      ++v9;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000cee0  push    rbx
0x18000cee2  push    rbp
0x18000cee3  push    rsi
0x18000cee4  push    rdi
0x18000cee5  sub     rsp, 38h
0x18000cee9  mov     rsi, rdx
0x18000ceec  lea     rbp, __ImageBase
0x18000cef3  mov     rdi, rcx
0x18000cef6  xor     ebx, ebx
0x18000cef8  cmp     rbx, 18h
0x18000cefc  jnb     short loc_18000CF36
0x18000cefe  mov     r8, rbx
0x18000cf01  add     r8, r8
0x18000cf04  mov     r9d, ss:rva dword_18004E190[rbp+r8*8]; cchCount2
0x18000cf0c  cmp     rdi, r9
0x18000cf0f  jnz     short loc_18000CF31
0x18000cf11  mov     r8, ss:rva off_18004E198[rbp+r8*8]; lpString2
0x18000cf19  mov     edx, edi; cchCount1
0x18000cf1b  mov     rcx, rsi; lpString1
0x18000cf1e  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18000cf26  call    cs:__imp_CompareStringOrdinal
0x18000cf2c  cmp     eax, 2
0x18000cf2f  jz      short loc_18000CF77
0x18000cf31  inc     rbx
0x18000cf34  jmp     short loc_18000CEF8
0x18000cf36  xor     ebx, ebx
0x18000cf38  cmp     rbx, 17h
0x18000cf3c  jnb     short loc_18000CF82
0x18000cf3e  mov     r8, rbx
0x18000cf41  add     r8, r8
0x18000cf44  mov     edx, ss:rva dword_18004E020[rbp+r8*8]; cchCount1
0x18000cf4c  cmp     rdi, rdx
0x18000cf4f  jb      short loc_18000CF72
0x18000cf51  mov     r8, ss:rva off_18004E028[rbp+r8*8]; lpString2
0x18000cf59  mov     r9d, edx; cchCount2
0x18000cf5c  mov     rcx, rsi; lpString1
0x18000cf5f  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18000cf67  call    cs:__imp_CompareStringOrdinal
0x18000cf6d  cmp     eax, 2
0x18000cf70  jz      short loc_18000CF77
0x18000cf72  inc     rbx
0x18000cf75  jmp     short loc_18000CF38
0x18000cf77  mov     al, 1
0x18000cf79  add     rsp, 38h
0x18000cf7d  pop     rdi
0x18000cf7e  pop     rsi
0x18000cf7f  pop     rbp
0x18000cf80  pop     rbx
0x18000cf81  retn
0x18000cf82  test    rdi, rdi
0x18000cf85  jz      short loc_18000CF8F
0x18000cf87  cmp     word ptr [rsi+rdi*2-2], 2Eh ; '.'
0x18000cf8d  jz      short loc_18000CF77
0x18000cf8f  cmp     rdi, 5
0x18000cf93  jb      short loc_18000CFD1
0x18000cf95  xor     ebx, ebx
0x18000cf97  add     rdi, 0FFFFFFFFFFFFFFFBh
0x18000cf9b  nop     dword ptr [rax+rax+00h]
0x18000cfa0  cmp     rbx, rdi
0x18000cfa3  ja      short loc_18000CFD1
0x18000cfa5  mov     r9d, 5; cchCount2
0x18000cfab  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18000cfb3  mov     edx, r9d; cchCount1
0x18000cfb6  lea     rcx, [rsi+rbx*2]; lpString1
0x18000cfba  lea     r8, String2; ".xn--"
0x18000cfc1  call    cs:__imp_CompareStringOrdinal
0x18000cfc7  cmp     eax, 2
0x18000cfca  jz      short loc_18000CF77
0x18000cfcc  inc     rbx
0x18000cfcf  jmp     short loc_18000CFA0
0x18000cfd1  xor     al, al
0x18000cfd3  jmp     short loc_18000CF79
```
