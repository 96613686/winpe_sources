# multivalueConnect

- ea: `0x1800649c0`
- end: `0x180064a7a`
- name: `multivalueConnect`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180031d80`
- `0x18003c510`
- `0x180041eb0`
- `0x180047da0`
- `0x1800649c0`
- `0x180069d50`
- `0x18009bf50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180064a4b`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180064a4b`

## string_xrefs

- `0x1800649ee`: `CREATE TABLE x("Index" INTEGER NOT NULL, Value, MultiValueBlob HIDDEN BLOB);`

## pseudocode

```c
__int64 __fastcall multivalueConnect(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5, __int64 *a6)
{
  __int64 v7; // rbx
  unsigned int v8; // r14d
  __int64 v9; // rax
  __int64 v10; // rbp
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rdi
  __int64 result; // rax

  if ( !(unsigned int)sqlite3_initialize() )
  {
    v7 = sqlite3Malloc(24);
    if ( v7 )
    {
      *(_OWORD *)v7 = 0;
      *(_QWORD *)(v7 + 16) = 0;
      v8 = sqlite3_declare_vtab(a1, "CREATE TABLE x(\"Index\" INTEGER NOT NULL, Value, MultiValueBlob HIDDEN BLOB);");
      if ( !v8 )
      {
        *a5 = v7;
        return 0;
      }
      sqlite3_free(v7);
      v9 = sqlite3_errmsg(a1);
      v10 = v9;
      v11 = -1;
      do
        ++v11;
      while ( *(_BYTE *)(v11 + v9) );
      v12 = sqlite3_malloc64(v11 + 1);
      v13 = v12;
      if ( v12 )
      {
        _o_strncpy_s(v12, v11 + 1, v10, v11);
        result = v8;
        *a6 = v13;
        return result;
      }
    }
  }
  return 7;
}

```

## disassembly

```asm
0x1800649c0  push    rbx
0x1800649c2  push    rbp
0x1800649c3  push    rsi
0x1800649c4  push    rdi
0x1800649c5  push    r14
0x1800649c7  sub     rsp, 20h
0x1800649cb  mov     rdi, rcx
0x1800649ce  call    sqlite3_initialize
0x1800649d3  test    eax, eax
0x1800649d5  jnz     loc_180064A6A
0x1800649db  lea     ecx, [rax+18h]
0x1800649de  call    sqlite3Malloc
0x1800649e3  mov     rbx, rax
0x1800649e6  test    rax, rax
0x1800649e9  jz      short loc_180064A6A
0x1800649eb  xorps   xmm0, xmm0
0x1800649ee  lea     rdx, aCreateTableXIn; "CREATE TABLE x(\"Index\" INTEGER NOT NU"...
0x1800649f5  xor     eax, eax
0x1800649f7  mov     rcx, rdi
0x1800649fa  movups  xmmword ptr [rbx], xmm0
0x1800649fd  mov     [rbx+10h], rax
0x180064a01  call    sqlite3_declare_vtab
0x180064a06  mov     r14d, eax
0x180064a09  test    eax, eax
0x180064a0b  jz      short loc_180064A5E
0x180064a0d  mov     rcx, rbx
0x180064a10  call    sqlite3_free
0x180064a15  mov     rcx, rdi
0x180064a18  call    sqlite3_errmsg
0x180064a1d  mov     rbp, rax
0x180064a20  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180064a24  inc     rbx
0x180064a27  cmp     byte ptr [rbx+rax], 0
0x180064a2b  jnz     short loc_180064A24
0x180064a2d  lea     rcx, [rbx+1]
0x180064a31  call    sqlite3_malloc64
0x180064a36  mov     rdi, rax
0x180064a39  test    rax, rax
0x180064a3c  jz      short loc_180064A6A
0x180064a3e  mov     r9, rbx
0x180064a41  lea     rdx, [rbx+1]
0x180064a45  mov     r8, rbp
0x180064a48  mov     rcx, rax
0x180064a4b  call    cs:__imp__o_strncpy_s
0x180064a51  mov     rcx, [rsp+48h+arg_28]
0x180064a56  mov     eax, r14d
0x180064a59  mov     [rcx], rdi
0x180064a5c  jmp     short loc_180064A6F
0x180064a5e  mov     rax, [rsp+48h+arg_20]
0x180064a63  mov     [rax], rbx
0x180064a66  xor     eax, eax
0x180064a68  jmp     short loc_180064A6F
0x180064a6a  mov     eax, 7
0x180064a6f  add     rsp, 20h
0x180064a73  pop     r14
0x180064a75  pop     rdi
0x180064a76  pop     rsi
0x180064a77  pop     rbp
0x180064a78  pop     rbx
0x180064a79  retn
```
