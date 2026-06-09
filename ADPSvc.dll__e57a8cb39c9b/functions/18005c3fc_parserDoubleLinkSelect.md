# parserDoubleLinkSelect

- ea: `0x18005c3fc`
- end: `0x18005c4c0`
- name: `parserDoubleLinkSelect`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800c3bd8`

## callees

- `0x18005c3fc`
- `0x180073aec`
- `0x18008da14`

## string_xrefs

- `0x18005c475`: `%s clause should come after %s not before`
- `0x18005c4a1`: `too many terms in compound SELECT`

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
0x18005c3fc  mov     [rsp+arg_0], rbx
0x18005c401  mov     [rsp+arg_8], rsi
0x18005c406  push    rdi
0x18005c407  sub     rsp, 20h
0x18005c40b  mov     rax, [rdx+50h]
0x18005c40f  mov     rbx, rcx
0x18005c412  test    rax, rax
0x18005c415  jz      loc_18005C4B0
0x18005c41b  lea     rsi, [rdx+4]
0x18005c41f  mov     qword ptr [rdx+58h], 0
0x18005c427  mov     ecx, 100h
0x18005c42c  mov     edi, 1
0x18005c431  or      [rsi], ecx
0x18005c433  mov     r10, [rax+48h]
0x18005c437  inc     edi
0x18005c439  test    r10, r10
0x18005c43c  jnz     short loc_18005C459
0x18005c43e  cmp     [rax+60h], r10
0x18005c442  jnz     short loc_18005C459
0x18005c444  mov     [rax+58h], rdx
0x18005c448  mov     rdx, rax
0x18005c44b  or      [rax+4], ecx
0x18005c44e  mov     rax, [rax+50h]
0x18005c452  test    rax, rax
0x18005c455  jnz     short loc_18005C433
0x18005c457  jmp     short loc_18005C488
0x18005c459  movzx   ecx, byte ptr [rdx]
0x18005c45c  call    sqlite3SelectOpName
0x18005c461  mov     r9, rax
0x18005c464  lea     r8, aOrderBy; "ORDER BY"
0x18005c46b  test    r10, r10
0x18005c46e  lea     rax, aLimit; "LIMIT"
0x18005c475  lea     rdx, aSClauseShouldC; "%s clause should come after %s not befo"...
0x18005c47c  mov     rcx, rbx
0x18005c47f  cmovz   r8, rax
0x18005c483  call    sqlite3ErrorMsg
0x18005c488  test    dword ptr [rsi], 400h
0x18005c48e  jnz     short loc_18005C4B0
0x18005c490  mov     rax, [rbx]
0x18005c493  mov     ecx, [rax+98h]
0x18005c499  test    ecx, ecx
0x18005c49b  jle     short loc_18005C4B0
0x18005c49d  cmp     edi, ecx
0x18005c49f  jle     short loc_18005C4B0
0x18005c4a1  lea     rdx, aTooManyTermsIn_1; "too many terms in compound SELECT"
0x18005c4a8  mov     rcx, rbx
0x18005c4ab  call    sqlite3ErrorMsg
0x18005c4b0  mov     rbx, [rsp+28h+arg_0]
0x18005c4b5  mov     rsi, [rsp+28h+arg_8]
0x18005c4ba  add     rsp, 20h
0x18005c4be  pop     rdi
0x18005c4bf  retn
```
