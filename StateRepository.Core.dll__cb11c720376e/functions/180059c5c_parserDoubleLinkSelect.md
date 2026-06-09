# parserDoubleLinkSelect

- ea: `0x180059c5c`
- end: `0x180059d1b`
- name: `parserDoubleLinkSelect`
- size: `191`
- prototype: `void __fastcall(__int64, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180031b38`
- `0x180068028`

## callees

- `0x180059c5c`
- `0x180060ce8`
- `0x18006536c`

## string_xrefs

- `0x180059ccb`: `%s clause should come after %s not before`
- `0x180059d07`: `too many terms in compound SELECT`

## pseudocode

```c
void __fastcall parserDoubleLinkSelect(__int64 a1, unsigned __int8 *a2)
{
  unsigned __int8 *v4; // rcx
  unsigned __int8 *v5; // rax
  int v6; // edi
  __int64 v7; // rax
  const char *v8; // r8
  __int64 v9; // rdx
  int v10; // ecx

  if ( *((_QWORD *)a2 + 10) )
  {
    v4 = 0;
    v5 = a2;
    v6 = 1;
    while ( 1 )
    {
      *((_DWORD *)v5 + 1) |= 0x100u;
      *((_QWORD *)v5 + 11) = v4;
      v4 = v5;
      v5 = (unsigned __int8 *)*((_QWORD *)v5 + 10);
      if ( !v5 )
        break;
      ++v6;
      if ( *((_QWORD *)v5 + 9) || *((_QWORD *)v5 + 12) )
      {
        v7 = sqlite3SelectOpName(*v4);
        v8 = "ORDER BY";
        if ( !v9 )
          v8 = "LIMIT";
        sqlite3ErrorMsg(a1, "%s clause should come after %s not before", v8, v7);
        break;
      }
    }
    if ( (*((_DWORD *)a2 + 1) & 0x600) == 0 )
    {
      v10 = *(_DWORD *)(*(_QWORD *)a1 + 152LL);
      if ( v10 > 0 && v6 > v10 )
        sqlite3ErrorMsg(a1, "too many terms in compound SELECT");
    }
  }
}

```

## disassembly

```asm
0x180059c5c  mov     [rsp+arg_0], rbx
0x180059c61  mov     [rsp+arg_8], rsi
0x180059c66  push    rdi
0x180059c67  sub     rsp, 20h
0x180059c6b  cmp     qword ptr [rdx+50h], 0
0x180059c70  mov     rbx, rdx
0x180059c73  mov     rsi, rcx
0x180059c76  jnz     short loc_180059C88
0x180059c78  mov     rbx, [rsp+28h+arg_0]
0x180059c7d  mov     rsi, [rsp+28h+arg_8]
0x180059c82  add     rsp, 20h
0x180059c86  pop     rdi
0x180059c87  retn
0x180059c88  xor     ecx, ecx
0x180059c8a  mov     rax, rbx
0x180059c8d  lea     edi, [rcx+1]
0x180059c90  bts     dword ptr [rax+4], 8
0x180059c95  mov     [rax+58h], rcx
0x180059c99  mov     rcx, rax
0x180059c9c  mov     rax, [rax+50h]
0x180059ca0  test    rax, rax
0x180059ca3  jz      short loc_180059CE5
0x180059ca5  mov     rdx, [rax+48h]
0x180059ca9  inc     edi
0x180059cab  test    rdx, rdx
0x180059cae  jnz     short loc_180059CB6
0x180059cb0  cmp     [rax+60h], rdx
0x180059cb4  jz      short loc_180059C90
0x180059cb6  movzx   ecx, byte ptr [rcx]
0x180059cb9  call    sqlite3SelectOpName
0x180059cbe  test    rdx, rdx
0x180059cc1  lea     r8, aOrderBy; "ORDER BY"
0x180059cc8  mov     r9, rax
0x180059ccb  lea     rdx, aSClauseShouldC; "%s clause should come after %s not befo"...
0x180059cd2  lea     rax, aLimit; "LIMIT"
0x180059cd9  mov     rcx, rsi
0x180059cdc  cmovz   r8, rax
0x180059ce0  call    sqlite3ErrorMsg
0x180059ce5  test    dword ptr [rbx+4], 600h
0x180059cec  jnz     short loc_180059C78
0x180059cee  mov     rax, [rsi]
0x180059cf1  mov     ecx, [rax+98h]
0x180059cf7  test    ecx, ecx
0x180059cf9  jle     loc_180059C78
0x180059cff  cmp     edi, ecx
0x180059d01  jle     loc_180059C78
0x180059d07  lea     rdx, aTooManyTermsIn_1; "too many terms in compound SELECT"
0x180059d0e  mov     rcx, rsi
0x180059d11  call    sqlite3ErrorMsg
0x180059d16  jmp     loc_180059C78
```
