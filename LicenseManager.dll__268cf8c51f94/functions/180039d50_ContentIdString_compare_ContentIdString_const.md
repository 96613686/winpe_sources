# ContentIdString::compare(ContentIdString const &)

- ea: `0x180039d50`
- end: `0x180039dc8`
- name: `?compare@ContentIdString@@QEBAHAEBV1@@Z`
- size: `120`
- prototype: `__int64 __fastcall(LPCWCH lpString1, const struct ContentIdString *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800579a8`
- `0x180096ba4`
- `0x180096bf4`

## callees

- `0x180039d50`
- `0x180076e64`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039d94`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039d94`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x180039dc0`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x180039dc0`

## pseudocode

```c
__int64 __fastcall ContentIdString::compare(const WCHAR *lpString1, const WCHAR *a2)
{
  LPCWCH v2; // rbx
  const WCHAR *v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // rbp

  v2 = lpString1;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v3 = a2;
  else
    v3 = *(const WCHAR **)a2;
  v4 = *((_QWORD *)a2 + 2);
  v5 = *((_QWORD *)lpString1 + 2);
  if ( (unsigned __int8)IsCompareContentIdPresent(lpString1) )
  {
    if ( *((_QWORD *)v2 + 3) > 7u )
      v2 = *(LPCWCH *)v2;
    return CompareContentId(v2, (unsigned int)v5, v3, (unsigned int)v4);
  }
  else
  {
    if ( *((_QWORD *)v2 + 3) > 7u )
      v2 = *(LPCWCH *)v2;
    return (unsigned int)(CompareStringOrdinal(v2, v5, v3, v4, 1) - 2);
  }
}

```

## disassembly

```asm
0x180039d50  push    rbx
0x180039d52  push    rbp
0x180039d53  push    rsi
0x180039d54  push    rdi
0x180039d55  sub     rsp, 38h
0x180039d59  mov     rbx, rcx
0x180039d5c  cmp     qword ptr [rdx+18h], 7
0x180039d61  jbe     short loc_180039DA6
0x180039d63  mov     rdi, [rdx]
0x180039d66  mov     rsi, [rdx+10h]
0x180039d6a  mov     rbp, [rcx+10h]
0x180039d6e  call    IsCompareContentIdPresent
0x180039d73  test    al, al
0x180039d75  jnz     short loc_180039DAB
0x180039d77  cmp     qword ptr [rbx+18h], 7
0x180039d7c  jbe     short loc_180039D81
0x180039d7e  mov     rbx, [rbx]
0x180039d81  mov     r9d, esi; cchCount2
0x180039d84  mov     edx, ebp; cchCount1
0x180039d86  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180039d8e  mov     r8, rdi; lpString2
0x180039d91  mov     rcx, rbx; lpString1
0x180039d94  call    cs:__imp_CompareStringOrdinal
0x180039d9a  sub     eax, 2
0x180039d9d  add     rsp, 38h
0x180039da1  pop     rdi
0x180039da2  pop     rsi
0x180039da3  pop     rbp
0x180039da4  pop     rbx
0x180039da5  retn
0x180039da6  mov     rdi, rdx
0x180039da9  jmp     short loc_180039D66
0x180039dab  cmp     qword ptr [rbx+18h], 7
0x180039db0  jbe     short loc_180039DB5
0x180039db2  mov     rbx, [rbx]
0x180039db5  mov     r9d, esi
0x180039db8  mov     edx, ebp
0x180039dba  mov     r8, rdi
0x180039dbd  mov     rcx, rbx
0x180039dc0  call    cs:__imp_CompareContentId
0x180039dc6  jmp     short loc_180039D9D
```
