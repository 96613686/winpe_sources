# ConvertPropvarToBool(tagPROPVARIANT const *,bool *)

- ea: `0x18001349c`
- end: `0x18001361d`
- name: `?ConvertPropvarToBool@@YAJPEBUtagPROPVARIANT@@PEA_N@Z`
- size: `385`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, bool *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800117b0`
- `0x18001e434`
- `0x18001f074`
- `0x18001f274`

## callees

- `0x18001349c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013523`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013601`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013523`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013601`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180013561`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180013595`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180013561`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180013595`

## pseudocode

```c
__int64 __fastcall ConvertPropvarToBool(const struct tagPROPVARIANT *a1, bool *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  bool v6; // zf

  v4 = -2147467259;
  switch ( a1->vt )
  {
    case 8u:
LABEL_9:
      if ( CompareStringW(0x7Fu, 1u, a1->bstrVal, -1, L"true", -1) == 2 )
      {
        v4 = 0;
        *a2 = 1;
        return v4;
      }
      v5 = CompareStringW(0x7Fu, 1u, a1->bstrVal, -1, L"false", -1);
      goto LABEL_21;
    case 0xBu:
      v4 = 0;
      *a2 = a1->iVal != 0;
      return v4;
    case 0x11u:
      v4 = 0;
      v6 = a1->cVal == 0;
      goto LABEL_15;
    case 0x12u:
      v4 = 0;
      v6 = a1->iVal == 0;
      goto LABEL_15;
    case 0x13u:
      v4 = 0;
      v6 = a1->lVal == 0;
      goto LABEL_15;
    case 0x15u:
      v4 = 0;
      v6 = a1->hVal.QuadPart == 0;
LABEL_15:
      *a2 = !v6;
      return v4;
  }
  if ( a1->vt != 30 )
  {
    if ( a1->vt != 31 )
      return v4;
    goto LABEL_9;
  }
  if ( CompareStringA(0x7Fu, 1u, a1->pszVal, -1, "true", -1) == 2 )
  {
    *a2 = 1;
    return 0;
  }
  v5 = CompareStringA(0x7Fu, 1u, a1->pszVal, -1, "false", -1);
LABEL_21:
  if ( v5 == 2 )
  {
    v4 = 0;
    *a2 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18001349c  push    rbx
0x18001349e  push    rbp
0x18001349f  push    rsi
0x1800134a0  push    rdi
0x1800134a1  push    r14
0x1800134a3  sub     rsp, 30h
0x1800134a7  movzx   r8d, word ptr [rcx]
0x1800134ab  mov     rsi, rdx
0x1800134ae  mov     rbp, rcx
0x1800134b1  mov     ebx, 80004005h
0x1800134b6  sub     r8d, 8
0x1800134ba  jz      short loc_1800134FE
0x1800134bc  sub     r8d, 3
0x1800134c0  jz      loc_1800135C0
0x1800134c6  sub     r8d, 6
0x1800134ca  jz      loc_1800135B9
0x1800134d0  sub     r8d, 1
0x1800134d4  jz      loc_1800135B1
0x1800134da  sub     r8d, 1
0x1800134de  jz      loc_1800135AA
0x1800134e4  sub     r8d, 2
0x1800134e8  jz      loc_18001359D
0x1800134ee  sub     r8d, 9
0x1800134f2  jz      short loc_18001353C
0x1800134f4  cmp     r8d, 1
0x1800134f8  jnz     loc_180013610
0x1800134fe  mov     r8, [rcx+8]; lpString1
0x180013502  lea     rax, String2; "true"
0x180013509  or      r14d, 0FFFFFFFFh
0x18001350d  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180013512  mov     r9d, r14d; cchCount1
0x180013515  mov     [rsp+58h+lpString2], rax; lpString2
0x18001351a  lea     edi, [r14+2]
0x18001351e  mov     edx, edi; dwCmpFlags
0x180013520  lea     ecx, [rdi+7Eh]; Locale
0x180013523  call    cs:__imp_CompareStringW
0x180013529  cmp     eax, 2
0x18001352c  jnz     loc_1800135E2
0x180013532  xor     ebx, ebx
0x180013534  mov     [rsi], dil
0x180013537  jmp     loc_180013610
0x18001353c  mov     r8, [rcx+8]; lpString1
0x180013540  lea     rax, aTrue_0; "true"
0x180013547  or      r14d, 0FFFFFFFFh
0x18001354b  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180013550  mov     r9d, r14d; cchCount1
0x180013553  mov     [rsp+58h+lpString2], rax; lpString2
0x180013558  lea     edi, [r14+2]
0x18001355c  mov     edx, edi; dwCmpFlags
0x18001355e  lea     ecx, [rdi+7Eh]; Locale
0x180013561  call    cs:__imp_CompareStringA
0x180013567  cmp     eax, 2
0x18001356a  jnz     short loc_180013576
0x18001356c  mov     [rsi], dil
0x18001356f  xor     ebx, ebx
0x180013571  jmp     loc_180013610
0x180013576  mov     r8, [rbp+8]; lpString1
0x18001357a  lea     rax, aFalse; "false"
0x180013581  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180013586  mov     r9d, r14d; cchCount1
0x180013589  mov     edx, edi; dwCmpFlags
0x18001358b  mov     [rsp+58h+lpString2], rax; lpString2
0x180013590  mov     ecx, 7Fh; Locale
0x180013595  call    cs:__imp_CompareStringA
0x18001359b  jmp     short loc_180013607
0x18001359d  xor     ebx, ebx
0x18001359f  cmp     [rcx+8], rbx
0x1800135a3  setnz   al
0x1800135a6  mov     [rdx], al
0x1800135a8  jmp     short loc_180013610
0x1800135aa  xor     ebx, ebx
0x1800135ac  cmp     [rcx+8], ebx
0x1800135af  jmp     short loc_1800135A3
0x1800135b1  xor     ebx, ebx
0x1800135b3  cmp     [rcx+8], bx
0x1800135b7  jmp     short loc_1800135A3
0x1800135b9  xor     ebx, ebx
0x1800135bb  cmp     [rcx+8], bl
0x1800135be  jmp     short loc_1800135A3
0x1800135c0  or      r14d, 0FFFFFFFFh
0x1800135c4  xor     ebx, ebx
0x1800135c6  cmp     [rcx+8], r14w
0x1800135cb  jz      short loc_1800135D8
0x1800135cd  cmp     [rcx+8], bx
0x1800135d1  jnz     short loc_1800135D8
0x1800135d3  mov     dil, bl
0x1800135d6  jmp     short loc_1800135DD
0x1800135d8  mov     edi, 1
0x1800135dd  mov     [rdx], dil
0x1800135e0  jmp     short loc_180013610
0x1800135e2  mov     r8, [rbp+8]; lpString1
0x1800135e6  lea     rax, aFalse_0; "false"
0x1800135ed  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x1800135f2  mov     r9d, r14d; cchCount1
0x1800135f5  mov     edx, edi; dwCmpFlags
0x1800135f7  mov     [rsp+58h+lpString2], rax; lpString2
0x1800135fc  mov     ecx, 7Fh; Locale
0x180013601  call    cs:__imp_CompareStringW
0x180013607  cmp     eax, 2
0x18001360a  jnz     short loc_180013610
0x18001360c  xor     ebx, ebx
0x18001360e  mov     [rsi], bl
0x180013610  mov     eax, ebx
0x180013612  add     rsp, 30h
0x180013616  pop     r14
0x180013618  pop     rdi
0x180013619  pop     rsi
0x18001361a  pop     rbp
0x18001361b  pop     rbx
0x18001361c  retn
```
