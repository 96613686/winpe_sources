# parserDoubleLinkSelect

- ea: `0x14003f1bc`
- end: `0x14003f280`
- name: `parserDoubleLinkSelect`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400a40bc`

## callees

- `0x14003f1bc`
- `0x1400560c4`
- `0x14006efb4`

## string_xrefs

- `0x14003f235`: `%s clause should come after %s not before`
- `0x14003f261`: `too many terms in compound SELECT`

## pseudocode

```c
__int64 __fastcall parserDoubleLinkSelect(__int64 *a1, unsigned __int8 *a2)
{
  __int64 result; // rax
  _DWORD *v4; // rsi
  int v5; // edi
  __int64 v6; // r9
  const char *v7; // r8
  __int64 v8; // r10
  int v9; // ecx

  result = *((_QWORD *)a2 + 10);
  if ( result )
  {
    v4 = a2 + 4;
    *((_QWORD *)a2 + 11) = 0;
    v5 = 1;
    *((_DWORD *)a2 + 1) |= 0x100u;
    while ( 1 )
    {
      ++v5;
      if ( *(_QWORD *)(result + 72) || *(_QWORD *)(result + 96) )
        break;
      *(_QWORD *)(result + 88) = a2;
      a2 = (unsigned __int8 *)result;
      *(_DWORD *)(result + 4) |= 0x100u;
      result = *(_QWORD *)(result + 80);
      if ( !result )
        goto LABEL_10;
    }
    v6 = sqlite3SelectOpName(*a2);
    v7 = "ORDER BY";
    if ( !v8 )
      v7 = "LIMIT";
    result = sqlite3ErrorMsg(a1, "%s clause should come after %s not before", v7, v6);
LABEL_10:
    if ( (*v4 & 0x400) == 0 )
    {
      result = *a1;
      v9 = *(_DWORD *)(*a1 + 152);
      if ( v9 > 0 && v5 > v9 )
        return sqlite3ErrorMsg(a1, "too many terms in compound SELECT");
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003f1bc  mov     [rsp+arg_0], rbx
0x14003f1c1  mov     [rsp+arg_8], rsi
0x14003f1c6  push    rdi
0x14003f1c7  sub     rsp, 20h
0x14003f1cb  mov     rax, [rdx+50h]
0x14003f1cf  mov     rbx, rcx
0x14003f1d2  test    rax, rax
0x14003f1d5  jz      loc_14003F270
0x14003f1db  lea     rsi, [rdx+4]
0x14003f1df  mov     qword ptr [rdx+58h], 0
0x14003f1e7  mov     ecx, 100h
0x14003f1ec  mov     edi, 1
0x14003f1f1  or      [rsi], ecx
0x14003f1f3  mov     r10, [rax+48h]
0x14003f1f7  inc     edi
0x14003f1f9  test    r10, r10
0x14003f1fc  jnz     short loc_14003F219
0x14003f1fe  cmp     [rax+60h], r10
0x14003f202  jnz     short loc_14003F219
0x14003f204  mov     [rax+58h], rdx
0x14003f208  mov     rdx, rax
0x14003f20b  or      [rax+4], ecx
0x14003f20e  mov     rax, [rax+50h]
0x14003f212  test    rax, rax
0x14003f215  jnz     short loc_14003F1F3
0x14003f217  jmp     short loc_14003F248
0x14003f219  movzx   ecx, byte ptr [rdx]
0x14003f21c  call    sqlite3SelectOpName
0x14003f221  mov     r9, rax
0x14003f224  lea     r8, aOrderBy; "ORDER BY"
0x14003f22b  test    r10, r10
0x14003f22e  lea     rax, aLimit; "LIMIT"
0x14003f235  lea     rdx, aSClauseShouldC; "%s clause should come after %s not befo"...
0x14003f23c  mov     rcx, rbx
0x14003f23f  cmovz   r8, rax
0x14003f243  call    sqlite3ErrorMsg
0x14003f248  test    dword ptr [rsi], 400h
0x14003f24e  jnz     short loc_14003F270
0x14003f250  mov     rax, [rbx]
0x14003f253  mov     ecx, [rax+98h]
0x14003f259  test    ecx, ecx
0x14003f25b  jle     short loc_14003F270
0x14003f25d  cmp     edi, ecx
0x14003f25f  jle     short loc_14003F270
0x14003f261  lea     rdx, aTooManyTermsIn_1; "too many terms in compound SELECT"
0x14003f268  mov     rcx, rbx
0x14003f26b  call    sqlite3ErrorMsg
0x14003f270  mov     rbx, [rsp+28h+arg_0]
0x14003f275  mov     rsi, [rsp+28h+arg_8]
0x14003f27a  add     rsp, 20h
0x14003f27e  pop     rdi
0x14003f27f  retn
```
