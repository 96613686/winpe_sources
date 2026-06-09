# sqlite3EndTransaction

- ea: `0x18005820c`
- end: `0x180058301`
- name: `sqlite3EndTransaction`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000213c`

## callees

- `0x180011bcc`
- `0x180015eb0`
- `0x1800168c0`
- `0x18005820c`
- `0x1800b0010`

## string_xrefs

- `0x180058227`: `ROLLBACK`
- `0x18005821d`: `COMMIT`

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
0x18005820c  mov     [rsp+arg_0], rbx
0x180058211  mov     [rsp+arg_8], rsi
0x180058216  push    rdi
0x180058217  sub     rsp, 40h
0x18005821b  xor     esi, esi
0x18005821d  lea     rax, aCommit; "COMMIT"
0x180058224  cmp     edx, 0Ch
0x180058227  lea     r8, aRollback; "ROLLBACK"
0x18005822e  mov     rbx, rcx
0x180058231  mov     rcx, [rcx]
0x180058234  cmovnz  r8, rax
0x180058238  setz    sil
0x18005823c  mov     rax, [rcx+200h]
0x180058243  test    rax, rax
0x180058246  jnz     short loc_180058280
0x180058248  mov     rcx, rbx
0x18005824b  call    sqlite3GetVdbe
0x180058250  test    rax, rax
0x180058253  jz      short loc_180058270
0x180058255  mov     edx, 1
0x18005825a  mov     dword ptr [rsp+48h+var_28], 0
0x180058262  mov     r8d, edx
0x180058265  mov     r9d, esi
0x180058268  mov     rcx, rax
0x18005826b  call    sqlite3VdbeAddOp3
0x180058270  mov     rbx, [rsp+48h+arg_0]
0x180058275  mov     rsi, [rsp+48h+arg_8]
0x18005827a  add     rsp, 40h
0x18005827e  pop     rdi
0x18005827f  retn
0x180058280  cmp     byte ptr [rcx+0C5h], 0
0x180058287  jnz     short loc_180058248
0x180058289  cmp     byte ptr [rbx+134h], 0
0x180058290  jnz     short loc_180058248
0x180058292  mov     rdx, [rbx+178h]
0x180058299  xor     r9d, r9d
0x18005829c  mov     rcx, [rcx+208h]
0x1800582a3  mov     [rsp+48h+var_20], rdx
0x1800582a8  mov     [rsp+48h+var_28], 0
0x1800582b1  lea     edx, [r9+16h]
0x1800582b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800582ba  mov     edi, eax
0x1800582bc  cmp     eax, 1
0x1800582bf  jnz     short loc_1800582E1
0x1800582c1  lea     rdx, aNotAuthorized; "not authorized"
0x1800582c8  mov     rcx, rbx
0x1800582cb  call    sqlite3ErrorMsg
0x1800582d0  mov     dword ptr [rbx+18h], 17h
0x1800582d7  test    edi, edi
0x1800582d9  jz      loc_180058248
0x1800582df  jmp     short loc_180058270
0x1800582e1  test    eax, 0FFFFFFFDh
0x1800582e6  jz      short loc_1800582D7
0x1800582e8  lea     rdx, aAuthorizerMalf; "authorizer malfunction"
0x1800582ef  mov     rcx, rbx
0x1800582f2  mov     edi, 1
0x1800582f7  call    sqlite3ErrorMsg
0x1800582fc  mov     [rbx+18h], edi
0x1800582ff  jmp     short loc_1800582D7
```
