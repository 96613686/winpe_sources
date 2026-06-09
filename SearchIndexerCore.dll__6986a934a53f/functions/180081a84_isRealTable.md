# isRealTable

- ea: `0x180081a84`
- end: `0x180081ae9`
- name: `isRealTable`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180072cf0`
- `0x18008f450`

## callees

- `0x180011bcc`
- `0x180081a84`

## string_xrefs

- `0x180081ab6`: `rename columns of`

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
0x180081a84  sub     rsp, 38h
0x180081a88  xor     eax, eax
0x180081a8a  lea     r9, aView_0; "view"
0x180081a91  cmp     byte ptr [rdx+3Fh], 2
0x180081a95  mov     r10d, r8d
0x180081a98  mov     r11, rcx
0x180081a9b  cmovnz  r9, rax
0x180081a9f  cmp     byte ptr [rdx+3Fh], 1
0x180081aa3  jnz     short loc_180081AAE
0x180081aa5  lea     r9, aVirtualTable; "virtual table"
0x180081aac  jmp     short loc_180081AB3
0x180081aae  test    r9, r9
0x180081ab1  jz      short loc_180081AE4
0x180081ab3  test    r10d, r10d
0x180081ab6  lea     rcx, aRenameColumnsO; "rename columns of"
0x180081abd  lea     r8, aDropColumnFrom; "drop column from"
0x180081ac4  cmovz   r8, rcx
0x180081ac8  mov     rcx, [rdx]
0x180081acb  mov     [rsp+38h+var_18], rcx
0x180081ad0  lea     rdx, aCannotSSS; "cannot %s %s \"%s\""
0x180081ad7  mov     rcx, r11
0x180081ada  call    sqlite3ErrorMsg
0x180081adf  mov     eax, 1
0x180081ae4  add     rsp, 38h
0x180081ae8  retn
```
