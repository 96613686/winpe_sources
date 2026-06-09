# isRealTable

- ea: `0x180072788`
- end: `0x1800727ed`
- name: `isRealTable`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180080120`
- `0x1800809a0`

## callees

- `0x180060ce8`
- `0x180072788`

## string_xrefs

- `0x1800727ba`: `rename columns of`

## pseudocode

```c
__int64 __fastcall isRealTable(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax
  const char *v4; // r9
  const char *v6; // r8

  result = 0;
  v4 = "view";
  if ( *(_BYTE *)(a2 + 63) != 2 )
    v4 = 0;
  if ( *(_BYTE *)(a2 + 63) == 1 )
  {
    v4 = "virtual table";
  }
  else if ( !v4 )
  {
    return result;
  }
  v6 = "drop column from";
  if ( !a3 )
    v6 = "rename columns of";
  sqlite3ErrorMsg(a1, "cannot %s %s \"%s\"", v6, v4, *(const char **)a2);
  return 1;
}

```

## disassembly

```asm
0x180072788  sub     rsp, 38h
0x18007278c  xor     eax, eax
0x18007278e  lea     r9, aView_0; "view"
0x180072795  cmp     byte ptr [rdx+3Fh], 2
0x180072799  mov     r10d, r8d
0x18007279c  mov     r11, rcx
0x18007279f  cmovnz  r9, rax
0x1800727a3  cmp     byte ptr [rdx+3Fh], 1
0x1800727a7  jnz     short loc_1800727B2
0x1800727a9  lea     r9, aVirtualTable; "virtual table"
0x1800727b0  jmp     short loc_1800727B7
0x1800727b2  test    r9, r9
0x1800727b5  jz      short loc_1800727E8
0x1800727b7  test    r10d, r10d
0x1800727ba  lea     rcx, aRenameColumnsO; "rename columns of"
0x1800727c1  lea     r8, aDropColumnFrom; "drop column from"
0x1800727c8  cmovz   r8, rcx
0x1800727cc  mov     rcx, [rdx]
0x1800727cf  mov     [rsp+38h+var_18], rcx
0x1800727d4  lea     rdx, aCannotSSS; "cannot %s %s \"%s\""
0x1800727db  mov     rcx, r11
0x1800727de  call    sqlite3ErrorMsg
0x1800727e3  mov     eax, 1
0x1800727e8  add     rsp, 38h
0x1800727ec  retn
```
