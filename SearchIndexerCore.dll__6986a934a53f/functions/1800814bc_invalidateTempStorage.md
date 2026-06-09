# invalidateTempStorage

- ea: `0x1800814bc`
- end: `0x18008151b`
- name: `invalidateTempStorage`
- size: `95`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18007af14`
- `0x180093bb0`

## callees

- `0x180011bcc`
- `0x1800324d0`
- `0x180046be0`
- `0x180059d90`
- `0x1800814bc`

## string_xrefs

- `0x180081505`: `temporary storage cannot be changed from within a transaction`

## pseudocode

```c
__int64 __fastcall invalidateTempStorage(__int64 *a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 *v3; // r8
  __int64 v4; // rcx
  __int64 v5; // rcx

  v2 = *a1;
  v3 = a1;
  v4 = *(_QWORD *)(*(_QWORD *)(*a1 + 32) + 40LL);
  if ( !v4 )
    return 0;
  if ( *(_BYTE *)(v2 + 101) && !(unsigned int)sqlite3BtreeTxnState(v4, a2, v3) )
  {
    sqlite3BtreeClose(v5);
    *(_QWORD *)(*(_QWORD *)(v2 + 32) + 40LL) = 0;
    sqlite3ResetAllSchemasOfConnection(v2);
    return 0;
  }
  sqlite3ErrorMsg(v3, "temporary storage cannot be changed from within a transaction");
  return 1;
}

```

## disassembly

```asm
0x1800814bc  push    rbx
0x1800814be  sub     rsp, 20h
0x1800814c2  mov     rbx, [rcx]
0x1800814c5  mov     r8, rcx
0x1800814c8  mov     rax, [rbx+20h]
0x1800814cc  mov     rcx, [rax+28h]
0x1800814d0  test    rcx, rcx
0x1800814d3  jz      short loc_1800814FD
0x1800814d5  cmp     byte ptr [rbx+65h], 0
0x1800814d9  jz      short loc_180081505
0x1800814db  call    sqlite3BtreeTxnState
0x1800814e0  test    eax, eax
0x1800814e2  jnz     short loc_180081505
0x1800814e4  call    sqlite3BtreeClose
0x1800814e9  mov     rax, [rbx+20h]
0x1800814ed  mov     rcx, rbx
0x1800814f0  mov     qword ptr [rax+28h], 0
0x1800814f8  call    sqlite3ResetAllSchemasOfConnection
0x1800814fd  xor     eax, eax
0x1800814ff  add     rsp, 20h
0x180081503  pop     rbx
0x180081504  retn
0x180081505  lea     rdx, aTemporaryStora; "temporary storage cannot be changed fro"...
0x18008150c  mov     rcx, r8
0x18008150f  call    sqlite3ErrorMsg
0x180081514  mov     eax, 1
0x180081519  jmp     short loc_1800814FF
```
