# ConvertPropvarToBool(tagPROPVARIANT const *,bool *)

- ea: `0x180013e20`
- end: `0x180013fba`
- name: `?ConvertPropvarToBool@@YAJPEBUtagPROPVARIANT@@PEA_N@Z`
- size: `410`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, bool *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011fc0`
- `0x18001f284`
- `0x18001ff78`
- `0x18002019c`

## callees

- `0x180013e20`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013ea7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013f97`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013ea7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013f97`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180013eeb`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180013f25`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180013eeb`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180013f25`

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
0x180013e20  push    rbx
0x180013e22  push    rbp
0x180013e23  push    rsi
0x180013e24  push    rdi
0x180013e25  push    r14
0x180013e27  sub     rsp, 30h
0x180013e2b  movzx   r8d, word ptr [rcx]
0x180013e2f  mov     rsi, rdx
0x180013e32  mov     rbp, rcx
0x180013e35  mov     ebx, 80004005h
0x180013e3a  sub     r8d, 8
0x180013e3e  jz      short loc_180013E82
0x180013e40  sub     r8d, 3
0x180013e44  jz      loc_180013F56
0x180013e4a  sub     r8d, 6
0x180013e4e  jz      loc_180013F4F
0x180013e54  sub     r8d, 1
0x180013e58  jz      loc_180013F47
0x180013e5e  sub     r8d, 1
0x180013e62  jz      loc_180013F40
0x180013e68  sub     r8d, 2
0x180013e6c  jz      loc_180013F33
0x180013e72  sub     r8d, 9
0x180013e76  jz      short loc_180013EC6
0x180013e78  cmp     r8d, 1
0x180013e7c  jnz     loc_180013FAC
0x180013e82  mov     r8, [rcx+8]; lpString1
0x180013e86  lea     rax, String2; "true"
0x180013e8d  or      r14d, 0FFFFFFFFh
0x180013e91  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180013e96  mov     r9d, r14d; cchCount1
0x180013e99  mov     [rsp+58h+lpString2], rax; lpString2
0x180013e9e  lea     edi, [r14+2]
0x180013ea2  mov     edx, edi; dwCmpFlags
0x180013ea4  lea     ecx, [rdi+7Eh]; Locale
0x180013ea7  call    cs:__imp_CompareStringW
0x180013eae  nop     dword ptr [rax+rax+00h]
0x180013eb3  cmp     eax, 2
0x180013eb6  jnz     loc_180013F78
0x180013ebc  xor     ebx, ebx
0x180013ebe  mov     [rsi], dil
0x180013ec1  jmp     loc_180013FAC
0x180013ec6  mov     r8, [rcx+8]; lpString1
0x180013eca  lea     rax, aTrue_0; "true"
0x180013ed1  or      r14d, 0FFFFFFFFh
0x180013ed5  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180013eda  mov     r9d, r14d; cchCount1
0x180013edd  mov     [rsp+58h+lpString2], rax; lpString2
0x180013ee2  lea     edi, [r14+2]
0x180013ee6  mov     edx, edi; dwCmpFlags
0x180013ee8  lea     ecx, [rdi+7Eh]; Locale
0x180013eeb  call    cs:__imp_CompareStringA
0x180013ef2  nop     dword ptr [rax+rax+00h]
0x180013ef7  cmp     eax, 2
0x180013efa  jnz     short loc_180013F06
0x180013efc  mov     [rsi], dil
0x180013eff  xor     ebx, ebx
0x180013f01  jmp     loc_180013FAC
0x180013f06  mov     r8, [rbp+8]; lpString1
0x180013f0a  lea     rax, aFalse; "false"
0x180013f11  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180013f16  mov     r9d, r14d; cchCount1
0x180013f19  mov     edx, edi; dwCmpFlags
0x180013f1b  mov     [rsp+58h+lpString2], rax; lpString2
0x180013f20  mov     ecx, 7Fh; Locale
0x180013f25  call    cs:__imp_CompareStringA
0x180013f2c  nop     dword ptr [rax+rax+00h]
0x180013f31  jmp     short loc_180013FA3
0x180013f33  xor     ebx, ebx
0x180013f35  cmp     [rcx+8], rbx
0x180013f39  setnz   al
0x180013f3c  mov     [rdx], al
0x180013f3e  jmp     short loc_180013FAC
0x180013f40  xor     ebx, ebx
0x180013f42  cmp     [rcx+8], ebx
0x180013f45  jmp     short loc_180013F39
0x180013f47  xor     ebx, ebx
0x180013f49  cmp     [rcx+8], bx
0x180013f4d  jmp     short loc_180013F39
0x180013f4f  xor     ebx, ebx
0x180013f51  cmp     [rcx+8], bl
0x180013f54  jmp     short loc_180013F39
0x180013f56  or      r14d, 0FFFFFFFFh
0x180013f5a  xor     ebx, ebx
0x180013f5c  cmp     [rcx+8], r14w
0x180013f61  jz      short loc_180013F6E
0x180013f63  cmp     [rcx+8], bx
0x180013f67  jnz     short loc_180013F6E
0x180013f69  mov     dil, bl
0x180013f6c  jmp     short loc_180013F73
0x180013f6e  mov     edi, 1
0x180013f73  mov     [rdx], dil
0x180013f76  jmp     short loc_180013FAC
0x180013f78  mov     r8, [rbp+8]; lpString1
0x180013f7c  lea     rax, aFalse_0; "false"
0x180013f83  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180013f88  mov     r9d, r14d; cchCount1
0x180013f8b  mov     edx, edi; dwCmpFlags
0x180013f8d  mov     [rsp+58h+lpString2], rax; lpString2
0x180013f92  mov     ecx, 7Fh; Locale
0x180013f97  call    cs:__imp_CompareStringW
0x180013f9e  nop     dword ptr [rax+rax+00h]
0x180013fa3  cmp     eax, 2
0x180013fa6  jnz     short loc_180013FAC
0x180013fa8  xor     ebx, ebx
0x180013faa  mov     [rsi], bl
0x180013fac  mov     eax, ebx
0x180013fae  add     rsp, 30h
0x180013fb2  pop     r14
0x180013fb4  pop     rdi
0x180013fb5  pop     rsi
0x180013fb6  pop     rbp
0x180013fb7  pop     rbx
0x180013fb8  retn
```
