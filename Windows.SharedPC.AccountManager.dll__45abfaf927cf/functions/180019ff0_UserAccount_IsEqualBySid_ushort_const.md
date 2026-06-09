# UserAccount::IsEqualBySid(ushort const *)

- ea: `0x180019ff0`
- end: `0x18001a063`
- name: `?IsEqualBySid@UserAccount@@UEAA_NPEBG@Z`
- size: `115`
- prototype: `bool __fastcall(UserAccount *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180019ff0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a052`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a052`

## pseudocode

```c
bool __fastcall UserAccount::IsEqualBySid(UserAccount *this, const unsigned __int16 *a2)
{
  const WCHAR *v2; // r8
  __int64 v3; // rax
  int v4; // r9d
  __int64 v5; // rdx
  __int64 v6; // rax
  const WCHAR *v7; // rcx

  v2 = a2;
  v3 = *((_QWORD *)this + 8);
  v4 = -(a2 != 0);
  if ( !a2 )
    v2 = &String2;
  v5 = -1;
  if ( v3 != -1 )
  {
    v7 = (const WCHAR *)*((_QWORD *)this + 7);
    LODWORD(v5) = v3;
    if ( v7 )
      return CompareStringOrdinal(v7, v5, v2, v4, 1) == 2;
LABEL_9:
    v7 = &String2;
    return CompareStringOrdinal(v7, v5, v2, v4, 1) == 2;
  }
  v6 = *((_QWORD *)this + 7);
  if ( !v6 )
  {
    LODWORD(v5) = 0;
    goto LABEL_9;
  }
  do
    ++v5;
  while ( *(_WORD *)(v6 + 2 * v5) );
  v7 = (const WCHAR *)*((_QWORD *)this + 7);
  return CompareStringOrdinal(v7, v5, v2, v4, 1) == 2;
}

```

## disassembly

```asm
0x180019ff0  sub     rsp, 38h
0x180019ff4  mov     rax, rdx
0x180019ff7  lea     r11, String2
0x180019ffe  neg     rax
0x18001a001  mov     r8, rdx
0x18001a004  mov     rax, [rcx+40h]
0x18001a008  sbb     r9d, r9d; cchCount2
0x18001a00b  xor     r10d, r10d
0x18001a00e  test    rdx, rdx
0x18001a011  cmovz   r8, r11; lpString2
0x18001a015  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001a019  cmp     rax, rdx
0x18001a01c  jnz     short loc_18001A03B
0x18001a01e  mov     rax, [rcx+38h]
0x18001a022  test    rax, rax
0x18001a025  jz      short loc_18001A036
0x18001a027  inc     rdx
0x18001a02a  cmp     [rax+rdx*2], r10w
0x18001a02f  jnz     short loc_18001A027
0x18001a031  mov     rcx, rax
0x18001a034  jmp     short loc_18001A04A
0x18001a036  mov     rdx, r10
0x18001a039  jmp     short loc_18001A047
0x18001a03b  mov     rcx, [rcx+38h]
0x18001a03f  mov     rdx, rax; cchCount1
0x18001a042  test    rcx, rcx
0x18001a045  jnz     short loc_18001A04A
0x18001a047  mov     rcx, r11; lpString1
0x18001a04a  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18001a052  call    cs:__imp_CompareStringOrdinal
0x18001a058  cmp     eax, 2
0x18001a05b  setz    al
0x18001a05e  add     rsp, 38h
0x18001a062  retn
```
