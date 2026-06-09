# parserDoubleLinkSelect

- ea: `0x18006fbcc`
- end: `0x18006fc82`
- name: `parserDoubleLinkSelect`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001bc30`
- `0x180054118`

## callees

- `0x180014464`
- `0x18006fbcc`
- `0x18008ac04`

## string_xrefs

- `0x18006fc2f`: `%s clause should come after %s not before`
- `0x18006fc63`: `too many terms in compound SELECT`

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
    if ( (*((_DWORD *)a2 + 1) & 0x400) == 0 )
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
0x18006fbcc  mov     [rsp+arg_0], rbx
0x18006fbd1  mov     [rsp+arg_8], rsi
0x18006fbd6  push    rdi
0x18006fbd7  sub     rsp, 20h
0x18006fbdb  cmp     qword ptr [rdx+50h], 0
0x18006fbe0  mov     rbx, rdx
0x18006fbe3  mov     rsi, rcx
0x18006fbe6  jz      loc_18006FC72
0x18006fbec  xor     ecx, ecx
0x18006fbee  mov     rax, rdx
0x18006fbf1  lea     edi, [rcx+1]
0x18006fbf4  bts     dword ptr [rax+4], 8
0x18006fbf9  mov     [rax+58h], rcx
0x18006fbfd  mov     rcx, rax
0x18006fc00  mov     rax, [rax+50h]
0x18006fc04  test    rax, rax
0x18006fc07  jz      short loc_18006FC49
0x18006fc09  mov     rdx, [rax+48h]
0x18006fc0d  inc     edi
0x18006fc0f  test    rdx, rdx
0x18006fc12  jnz     short loc_18006FC1A
0x18006fc14  cmp     [rax+60h], rdx
0x18006fc18  jz      short loc_18006FBF4
0x18006fc1a  movzx   ecx, byte ptr [rcx]
0x18006fc1d  call    sqlite3SelectOpName
0x18006fc22  test    rdx, rdx
0x18006fc25  lea     r8, aOrderBy; "ORDER BY"
0x18006fc2c  mov     r9, rax
0x18006fc2f  lea     rdx, aSClauseShouldC; "%s clause should come after %s not befo"...
0x18006fc36  lea     rax, aLimit; "LIMIT"
0x18006fc3d  mov     rcx, rsi
0x18006fc40  cmovz   r8, rax
0x18006fc44  call    sqlite3ErrorMsg
0x18006fc49  test    dword ptr [rbx+4], 400h
0x18006fc50  jnz     short loc_18006FC72
0x18006fc52  mov     rax, [rsi]
0x18006fc55  mov     ecx, [rax+98h]
0x18006fc5b  test    ecx, ecx
0x18006fc5d  jle     short loc_18006FC72
0x18006fc5f  cmp     edi, ecx
0x18006fc61  jle     short loc_18006FC72
0x18006fc63  lea     rdx, aTooManyTermsIn_1; "too many terms in compound SELECT"
0x18006fc6a  mov     rcx, rsi
0x18006fc6d  call    sqlite3ErrorMsg
0x18006fc72  mov     rbx, [rsp+28h+arg_0]
0x18006fc77  mov     rsi, [rsp+28h+arg_8]
0x18006fc7c  add     rsp, 20h
0x18006fc80  pop     rdi
0x18006fc81  retn
```
