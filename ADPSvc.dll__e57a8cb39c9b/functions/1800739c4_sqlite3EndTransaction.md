# sqlite3EndTransaction

- ea: `0x1800739c4`
- end: `0x180073a38`
- name: `sqlite3EndTransaction`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800c3bd8`

## callees

- `0x1800693b0`
- `0x1800739c4`
- `0x18007d478`
- `0x1800923d8`

## string_xrefs

- `0x1800739e3`: `ROLLBACK`
- `0x1800739dc`: `COMMIT`

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
0x1800739c4  mov     [rsp+arg_0], rbx
0x1800739c9  push    rdi
0x1800739ca  sub     rsp, 30h
0x1800739ce  xor     edi, edi
0x1800739d0  mov     [rsp+38h+var_18], 0
0x1800739d9  cmp     edx, 0Ch
0x1800739dc  lea     rax, aCommit; "COMMIT"
0x1800739e3  lea     r8, aRollback; "ROLLBACK"
0x1800739ea  mov     rbx, rcx
0x1800739ed  setz    dil
0x1800739f1  cmovnz  r8, rax
0x1800739f5  xor     r9d, r9d
0x1800739f8  lea     edx, [r9+16h]
0x1800739fc  call    sqlite3AuthCheck
0x180073a01  test    eax, eax
0x180073a03  jnz     short loc_180073A2D
0x180073a05  mov     rcx, rbx
0x180073a08  call    sqlite3GetVdbe
0x180073a0d  test    rax, rax
0x180073a10  jz      short loc_180073A2D
0x180073a12  mov     edx, 1
0x180073a17  mov     dword ptr [rsp+38h+var_18], 0
0x180073a1f  mov     r8d, edx
0x180073a22  mov     r9d, edi
0x180073a25  mov     rcx, rax
0x180073a28  call    sqlite3VdbeAddOp3
0x180073a2d  mov     rbx, [rsp+38h+arg_0]
0x180073a32  add     rsp, 30h
0x180073a36  pop     rdi
0x180073a37  retn
```
