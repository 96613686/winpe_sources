# invalidateTempStorage

- ea: `0x180063fe8`
- end: `0x180064047`
- name: `invalidateTempStorage`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180016bf4`
- `0x1800578a8`

## callees

- `0x180014464`
- `0x1800363c8`
- `0x180063fe8`
- `0x1800798dc`
- `0x180089a6c`

## string_xrefs

- `0x180064031`: `temporary storage cannot be changed from within a transaction`

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
0x180063fe8  push    rbx
0x180063fea  sub     rsp, 20h
0x180063fee  mov     rbx, [rcx]
0x180063ff1  mov     r8, rcx
0x180063ff4  mov     rax, [rbx+20h]
0x180063ff8  mov     rcx, [rax+28h]
0x180063ffc  test    rcx, rcx
0x180063fff  jz      short loc_180064029
0x180064001  cmp     byte ptr [rbx+65h], 0
0x180064005  jz      short loc_180064031
0x180064007  call    sqlite3BtreeTxnState
0x18006400c  test    eax, eax
0x18006400e  jnz     short loc_180064031
0x180064010  call    sqlite3BtreeClose
0x180064015  mov     rax, [rbx+20h]
0x180064019  mov     rcx, rbx
0x18006401c  mov     qword ptr [rax+28h], 0
0x180064024  call    sqlite3ResetAllSchemasOfConnection
0x180064029  xor     eax, eax
0x18006402b  add     rsp, 20h
0x18006402f  pop     rbx
0x180064030  retn
0x180064031  lea     rdx, aTemporaryStora; "temporary storage cannot be changed fro"...
0x180064038  mov     rcx, r8
0x18006403b  call    sqlite3ErrorMsg
0x180064040  mov     eax, 1
0x180064045  jmp     short loc_18006402B
```
