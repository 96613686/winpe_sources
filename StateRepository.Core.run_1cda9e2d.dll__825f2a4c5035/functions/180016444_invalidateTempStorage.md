# invalidateTempStorage

- ea: `0x180016444`
- end: `0x1800164a3`
- name: `invalidateTempStorage`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180016398`
- `0x180050420`

## callees

- `0x180016444`
- `0x180046938`
- `0x18005bbe8`
- `0x180060ce8`
- `0x180063a1c`

## string_xrefs

- `0x18001648d`: `temporary storage cannot be changed from within a transaction`

## pseudocode

```c
__int64 __fastcall invalidateTempStorage(__int64 *a1)
{
  __int64 v1; // rbx
  __int64 *v2; // r8
  __int64 v3; // rcx
  __int64 v4; // rcx

  v1 = *a1;
  v2 = a1;
  v3 = *(_QWORD *)(*(_QWORD *)(*a1 + 32) + 40LL);
  if ( !v3 )
    return 0;
  if ( *(_BYTE *)(v1 + 101) && !(unsigned int)sqlite3BtreeTxnState(v3) )
  {
    sqlite3BtreeClose(v4);
    *(_QWORD *)(*(_QWORD *)(v1 + 32) + 40LL) = 0;
    sqlite3ResetAllSchemasOfConnection(v1);
    return 0;
  }
  sqlite3ErrorMsg(v2, "temporary storage cannot be changed from within a transaction");
  return 1;
}

```

## disassembly

```asm
0x180016444  push    rbx
0x180016446  sub     rsp, 20h
0x18001644a  mov     rbx, [rcx]
0x18001644d  mov     r8, rcx
0x180016450  mov     rax, [rbx+20h]
0x180016454  mov     rcx, [rax+28h]
0x180016458  test    rcx, rcx
0x18001645b  jz      short loc_180016485
0x18001645d  cmp     byte ptr [rbx+65h], 0
0x180016461  jz      short loc_18001648D
0x180016463  call    sqlite3BtreeTxnState
0x180016468  test    eax, eax
0x18001646a  jnz     short loc_18001648D
0x18001646c  call    sqlite3BtreeClose
0x180016471  mov     rax, [rbx+20h]
0x180016475  mov     rcx, rbx
0x180016478  mov     qword ptr [rax+28h], 0
0x180016480  call    sqlite3ResetAllSchemasOfConnection
0x180016485  xor     eax, eax
0x180016487  add     rsp, 20h
0x18001648b  pop     rbx
0x18001648c  retn
0x18001648d  lea     rdx, aTemporaryStora; "temporary storage cannot be changed fro"...
0x180016494  mov     rcx, r8
0x180016497  call    sqlite3ErrorMsg
0x18001649c  mov     eax, 1
0x1800164a1  jmp     short loc_180016487
```
