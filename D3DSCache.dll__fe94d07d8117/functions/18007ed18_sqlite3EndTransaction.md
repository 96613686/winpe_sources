# sqlite3EndTransaction

- ea: `0x18007ed18`
- end: `0x18007ed8c`
- name: `sqlite3EndTransaction`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001bc30`

## callees

- `0x18000b4bc`
- `0x18003d480`
- `0x18004002c`
- `0x18007ed18`

## string_xrefs

- `0x18007ed37`: `ROLLBACK`
- `0x18007ed30`: `COMMIT`

## pseudocode

```c
__int64 __fastcall sqlite3EndTransaction(__int64 a1, int a2)
{
  const char *v2; // r8
  BOOL v4; // edi
  __int64 result; // rax

  v2 = "ROLLBACK";
  v4 = a2 == 12;
  if ( a2 != 12 )
    v2 = "COMMIT";
  result = sqlite3AuthCheck(a1, 22, (_DWORD)v2, 0, 0);
  if ( !(_DWORD)result )
  {
    result = sqlite3GetVdbe(a1);
    if ( result )
      return sqlite3VdbeAddOp3(result, 1, 1, v4, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18007ed18  mov     [rsp+arg_0], rbx
0x18007ed1d  push    rdi
0x18007ed1e  sub     rsp, 30h
0x18007ed22  xor     edi, edi
0x18007ed24  mov     [rsp+38h+var_18], 0
0x18007ed2d  cmp     edx, 0Ch
0x18007ed30  lea     rax, aCommit; "COMMIT"
0x18007ed37  lea     r8, aRollback; "ROLLBACK"
0x18007ed3e  mov     rbx, rcx
0x18007ed41  setz    dil
0x18007ed45  cmovnz  r8, rax
0x18007ed49  xor     r9d, r9d
0x18007ed4c  lea     edx, [r9+16h]
0x18007ed50  call    sqlite3AuthCheck
0x18007ed55  test    eax, eax
0x18007ed57  jnz     short loc_18007ED81
0x18007ed59  mov     rcx, rbx
0x18007ed5c  call    sqlite3GetVdbe
0x18007ed61  test    rax, rax
0x18007ed64  jz      short loc_18007ED81
0x18007ed66  mov     edx, 1
0x18007ed6b  mov     dword ptr [rsp+38h+var_18], 0
0x18007ed73  mov     r8d, edx
0x18007ed76  mov     r9d, edi
0x18007ed79  mov     rcx, rax
0x18007ed7c  call    sqlite3VdbeAddOp3
0x18007ed81  mov     rbx, [rsp+38h+arg_0]
0x18007ed86  add     rsp, 30h
0x18007ed8a  pop     rdi
0x18007ed8b  retn
```
