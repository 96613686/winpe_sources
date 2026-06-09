# dbpageConnect

- ea: `0x18007d350`
- end: `0x18007d3d6`
- name: `dbpageConnect`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180047da0`
- `0x18007d350`
- `0x18009bf50`
- `0x18009eed0`

## string_xrefs

- `0x18007d377`: `CREATE TABLE x(pgno INTEGER PRIMARY KEY, data BLOB, schema HIDDEN)`

## pseudocode

```c
__int64 __fastcall dbpageConnect(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  _QWORD *v5; // rbx
  unsigned int v7; // edi
  _QWORD *v8; // rax

  v5 = 0;
  sqlite3_vtab_config(a1, 3);
  sqlite3_vtab_config(a1, 4);
  v7 = sqlite3_declare_vtab(a1, "CREATE TABLE x(pgno INTEGER PRIMARY KEY, data BLOB, schema HIDDEN)");
  if ( !v7 )
  {
    v8 = (_QWORD *)sqlite3_malloc64(32);
    v5 = v8;
    if ( v8 )
    {
      *v8 = 0;
      v8[1] = 0;
      v8[2] = 0;
      v8[3] = a1;
    }
    else
    {
      v7 = 7;
    }
  }
  *a5 = v5;
  return v7;
}

```

## disassembly

```asm
0x18007d350  mov     [rsp+arg_0], rbx
0x18007d355  mov     [rsp+arg_8], rsi
0x18007d35a  push    rdi
0x18007d35b  sub     rsp, 20h
0x18007d35f  xor     ebx, ebx
0x18007d361  mov     rsi, rcx
0x18007d364  lea     edx, [rbx+3]
0x18007d367  call    sqlite3_vtab_config
0x18007d36c  lea     edx, [rbx+4]
0x18007d36f  mov     rcx, rsi
0x18007d372  call    sqlite3_vtab_config
0x18007d377  lea     rdx, aCreateTableXPg; "CREATE TABLE x(pgno INTEGER PRIMARY KEY"...
0x18007d37e  mov     rcx, rsi
0x18007d381  call    sqlite3_declare_vtab
0x18007d386  mov     edi, eax
0x18007d388  test    eax, eax
0x18007d38a  jnz     short loc_18007D3BC
0x18007d38c  lea     ecx, [rbx+20h]
0x18007d38f  call    sqlite3_malloc64
0x18007d394  mov     rbx, rax
0x18007d397  test    rax, rax
0x18007d39a  jnz     short loc_18007D3A1
0x18007d39c  lea     edi, [rax+7]
0x18007d39f  jmp     short loc_18007D3BC
0x18007d3a1  mov     qword ptr [rax], 0
0x18007d3a8  mov     qword ptr [rax+8], 0
0x18007d3b0  mov     qword ptr [rax+10h], 0
0x18007d3b8  mov     [rax+18h], rsi
0x18007d3bc  mov     rax, [rsp+28h+arg_20]
0x18007d3c1  mov     rsi, [rsp+28h+arg_8]
0x18007d3c6  mov     [rax], rbx
0x18007d3c9  mov     eax, edi
0x18007d3cb  mov     rbx, [rsp+28h+arg_0]
0x18007d3d0  add     rsp, 20h
0x18007d3d4  pop     rdi
0x18007d3d5  retn
```
