# sqlite3EndTransaction

- ea: `0x180054b80`
- end: `0x180054c76`
- name: `sqlite3EndTransaction`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180031b38`

## callees

- `0x180010810`
- `0x1800119e0`
- `0x180054b80`
- `0x180060ce8`
- `0x18009a010`

## string_xrefs

- `0x180054b9b`: `ROLLBACK`
- `0x180054b91`: `COMMIT`

## pseudocode

```c
__int64 __fastcall sqlite3EndTransaction(__int64 *a1, int a2)
{
  int v2; // esi
  const char *v3; // r8
  __int64 v5; // rcx
  __int64 (__fastcall *v6)(_QWORD, __int64, const char *); // rax
  __int64 result; // rax
  int v8; // edi

  v2 = 0;
  v3 = "ROLLBACK";
  v5 = *a1;
  if ( a2 != 12 )
    v3 = "COMMIT";
  LOBYTE(v2) = a2 == 12;
  v6 = *(__int64 (__fastcall **)(_QWORD, __int64, const char *))(v5 + 512);
  if ( !v6 || *(_BYTE *)(v5 + 197) || *((_BYTE *)a1 + 308) )
    goto LABEL_4;
  result = v6(*(_QWORD *)(v5 + 520), 22, v3);
  v8 = result;
  if ( (_DWORD)result == 1 )
  {
    result = sqlite3ErrorMsg(a1, "not authorized");
    *((_DWORD *)a1 + 6) = 23;
  }
  else if ( (result & 0xFFFFFFFD) != 0 )
  {
    v8 = 1;
    result = sqlite3ErrorMsg(a1, "authorizer malfunction");
    *((_DWORD *)a1 + 6) = 1;
  }
  if ( !v8 )
  {
LABEL_4:
    result = sqlite3GetVdbe(a1);
    if ( result )
      return sqlite3VdbeAddOp3(result, 1, 1, v2, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180054b80  mov     [rsp+arg_0], rbx
0x180054b85  mov     [rsp+arg_8], rsi
0x180054b8a  push    rdi
0x180054b8b  sub     rsp, 40h
0x180054b8f  xor     esi, esi
0x180054b91  lea     rax, aCommit; "COMMIT"
0x180054b98  cmp     edx, 0Ch
0x180054b9b  lea     r8, aRollback; "ROLLBACK"
0x180054ba2  mov     rbx, rcx
0x180054ba5  mov     rcx, [rcx]
0x180054ba8  cmovnz  r8, rax
0x180054bac  setz    sil
0x180054bb0  mov     rax, [rcx+200h]
0x180054bb7  test    rax, rax
0x180054bba  jnz     short loc_180054BFA
0x180054bbc  mov     rcx, rbx
0x180054bbf  call    sqlite3GetVdbe
0x180054bc4  test    rax, rax
0x180054bc7  jz      short loc_180054BEA
0x180054bc9  mov     edx, 1
0x180054bce  mov     dword ptr [rsp+48h+var_28], 0
0x180054bd6  mov     r8d, edx
0x180054bd9  mov     r9d, esi
0x180054bdc  mov     rcx, rax
0x180054bdf  call    sqlite3VdbeAddOp3
0x180054be4  jmp     short loc_180054BEA
0x180054be6  test    edi, edi
0x180054be8  jz      short loc_180054BBC
0x180054bea  mov     rbx, [rsp+48h+arg_0]
0x180054bef  mov     rsi, [rsp+48h+arg_8]
0x180054bf4  add     rsp, 40h
0x180054bf8  pop     rdi
0x180054bf9  retn
0x180054bfa  cmp     byte ptr [rcx+0C5h], 0
0x180054c01  jnz     short loc_180054BBC
0x180054c03  cmp     byte ptr [rbx+134h], 0
0x180054c0a  jnz     short loc_180054BBC
0x180054c0c  mov     rdx, [rbx+178h]
0x180054c13  xor     r9d, r9d
0x180054c16  mov     rcx, [rcx+208h]
0x180054c1d  mov     [rsp+48h+var_20], rdx
0x180054c22  mov     [rsp+48h+var_28], 0
0x180054c2b  lea     edx, [r9+16h]
0x180054c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c34  mov     edi, eax
0x180054c36  cmp     eax, 1
0x180054c39  jnz     short loc_180054C53
0x180054c3b  lea     rdx, aNotAuthorized; "not authorized"
0x180054c42  mov     rcx, rbx
0x180054c45  call    sqlite3ErrorMsg
0x180054c4a  mov     dword ptr [rbx+18h], 17h
0x180054c51  jmp     short loc_180054BE6
0x180054c53  test    eax, 0FFFFFFFDh
0x180054c58  jz      short loc_180054BE6
0x180054c5a  lea     rdx, aAuthorizerMalf; "authorizer malfunction"
0x180054c61  mov     rcx, rbx
0x180054c64  mov     edi, 1
0x180054c69  call    sqlite3ErrorMsg
0x180054c6e  mov     [rbx+18h], edi
0x180054c71  jmp     loc_180054BE6
```
