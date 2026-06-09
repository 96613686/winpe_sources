# sqlite3BeginWriteOperation

- ea: `0x1800157d4`
- end: `0x180015842`
- name: `sqlite3BeginWriteOperation`
- size: `110`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180003128`
- `0x18000ded0`
- `0x1800146b8`
- `0x180015848`
- `0x1800167c0`
- `0x1800189c8`
- `0x180019e50`
- `0x180045eb8`
- `0x180050420`
- `0x18007d198`
- `0x180082718`
- `0x1800830cc`
- `0x1800832c0`
- `0x180086c1c`
- `0x180094cfc`

## callees

- `0x1800157d4`
- `0x180085a44`

## pseudocode

```c
int __fastcall sqlite3BeginWriteOperation(__int64 a1, char a2, unsigned int a3)
{
  __int64 v3; // rbx
  char v4; // di
  int v6; // eax
  int result; // eax

  v3 = a1;
  v4 = a3;
  if ( *(_QWORD *)(a1 + 176) )
    v3 = *(_QWORD *)(a1 + 176);
  v6 = *(_DWORD *)(v3 + 132);
  if ( !_bittest(&v6, a3) )
  {
    *(_DWORD *)(v3 + 132) = v6 | (1 << a3);
    if ( a3 == 1 )
      sqlite3OpenTempDatabase((__int64 **)v3);
  }
  result = *(_DWORD *)(v3 + 128) | (1 << v4);
  *(_BYTE *)(v3 + 32) |= a2;
  *(_DWORD *)(v3 + 128) = result;
  return result;
}

```

## disassembly

```asm
0x1800157d4  mov     [rsp+arg_0], rbx
0x1800157d9  mov     [rsp+arg_8], rsi
0x1800157de  push    rdi
0x1800157df  sub     rsp, 20h
0x1800157e3  mov     rax, [rcx+0B0h]
0x1800157ea  mov     rbx, rcx
0x1800157ed  test    rax, rax
0x1800157f0  mov     edi, r8d
0x1800157f3  mov     esi, edx
0x1800157f5  cmovnz  rbx, rax
0x1800157f9  mov     eax, [rbx+84h]
0x1800157ff  bt      eax, r8d
0x180015803  jb      short loc_180015815
0x180015805  bts     eax, r8d
0x180015809  mov     [rbx+84h], eax
0x18001580f  cmp     r8d, 1
0x180015813  jz      short loc_180015838
0x180015815  mov     eax, [rbx+80h]
0x18001581b  bts     eax, edi
0x18001581e  or      [rbx+20h], sil
0x180015822  mov     rsi, [rsp+28h+arg_8]
0x180015827  mov     [rbx+80h], eax
0x18001582d  mov     rbx, [rsp+28h+arg_0]
0x180015832  add     rsp, 20h
0x180015836  pop     rdi
0x180015837  retn
0x180015838  mov     rcx, rbx
0x18001583b  call    sqlite3OpenTempDatabase
0x180015840  jmp     short loc_180015815
```
