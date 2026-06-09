# parserDoubleLinkSelect

- ea: `0x1800597b4`
- end: `0x180059873`
- name: `parserDoubleLinkSelect`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000213c`
- `0x180073024`

## callees

- `0x180011bcc`
- `0x1800597b4`
- `0x180076e6c`

## string_xrefs

- `0x18005985f`: `too many terms in compound SELECT`
- `0x180059823`: `%s clause should come after %s not before`

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
0x1800597b4  mov     [rsp+arg_0], rbx
0x1800597b9  mov     [rsp+arg_8], rsi
0x1800597be  push    rdi
0x1800597bf  sub     rsp, 20h
0x1800597c3  cmp     qword ptr [rdx+50h], 0
0x1800597c8  mov     rbx, rdx
0x1800597cb  mov     rsi, rcx
0x1800597ce  jnz     short loc_1800597E0
0x1800597d0  mov     rbx, [rsp+28h+arg_0]
0x1800597d5  mov     rsi, [rsp+28h+arg_8]
0x1800597da  add     rsp, 20h
0x1800597de  pop     rdi
0x1800597df  retn
0x1800597e0  xor     ecx, ecx
0x1800597e2  mov     rax, rbx
0x1800597e5  lea     edi, [rcx+1]
0x1800597e8  bts     dword ptr [rax+4], 8
0x1800597ed  mov     [rax+58h], rcx
0x1800597f1  mov     rcx, rax
0x1800597f4  mov     rax, [rax+50h]
0x1800597f8  test    rax, rax
0x1800597fb  jz      short loc_18005983D
0x1800597fd  mov     rdx, [rax+48h]
0x180059801  inc     edi
0x180059803  test    rdx, rdx
0x180059806  jnz     short loc_18005980E
0x180059808  cmp     [rax+60h], rdx
0x18005980c  jz      short loc_1800597E8
0x18005980e  movzx   ecx, byte ptr [rcx]
0x180059811  call    sqlite3SelectOpName
0x180059816  test    rdx, rdx
0x180059819  lea     r8, aOrderBy; "ORDER BY"
0x180059820  mov     r9, rax
0x180059823  lea     rdx, aSClauseShouldC; "%s clause should come after %s not befo"...
0x18005982a  lea     rax, aLimit; "LIMIT"
0x180059831  mov     rcx, rsi
0x180059834  cmovz   r8, rax
0x180059838  call    sqlite3ErrorMsg
0x18005983d  test    dword ptr [rbx+4], 400h
0x180059844  jnz     short loc_1800597D0
0x180059846  mov     rax, [rsi]
0x180059849  mov     ecx, [rax+98h]
0x18005984f  test    ecx, ecx
0x180059851  jle     loc_1800597D0
0x180059857  cmp     edi, ecx
0x180059859  jle     loc_1800597D0
0x18005985f  lea     rdx, aTooManyTermsIn_1; "too many terms in compound SELECT"
0x180059866  mov     rcx, rsi
0x180059869  call    sqlite3ErrorMsg
0x18005986e  jmp     loc_1800597D0
```
