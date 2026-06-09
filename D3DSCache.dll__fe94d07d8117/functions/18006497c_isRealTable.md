# isRealTable

- ea: `0x18006497c`
- end: `0x1800649e1`
- name: `isRealTable`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180076e24`
- `0x1800776a4`

## callees

- `0x180014464`
- `0x18006497c`

## string_xrefs

- `0x1800649ae`: `rename columns of`

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
0x18006497c  sub     rsp, 38h
0x180064980  xor     eax, eax
0x180064982  lea     r9, aView_0; "view"
0x180064989  cmp     byte ptr [rdx+3Fh], 2
0x18006498d  mov     r10d, r8d
0x180064990  mov     r11, rcx
0x180064993  cmovnz  r9, rax
0x180064997  cmp     byte ptr [rdx+3Fh], 1
0x18006499b  jnz     short loc_1800649A6
0x18006499d  lea     r9, aVirtualTable; "virtual table"
0x1800649a4  jmp     short loc_1800649AB
0x1800649a6  test    r9, r9
0x1800649a9  jz      short loc_1800649DC
0x1800649ab  test    r10d, r10d
0x1800649ae  lea     rcx, aRenameColumnsO; "rename columns of"
0x1800649b5  lea     r8, aDropColumnFrom; "drop column from"
0x1800649bc  cmovz   r8, rcx
0x1800649c0  mov     rcx, [rdx]
0x1800649c3  mov     [rsp+38h+var_18], rcx
0x1800649c8  lea     rdx, aCannotSSS; "cannot %s %s \"%s\""
0x1800649cf  mov     rcx, r11
0x1800649d2  call    sqlite3ErrorMsg
0x1800649d7  mov     eax, 1
0x1800649dc  add     rsp, 38h
0x1800649e0  retn
```
