# jsonEachConnect

- ea: `0x1800833d0`
- end: `0x180083437`
- name: `jsonEachConnect`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18003d380`
- `0x1800833d0`
- `0x18009bf50`
- `0x18009eed0`

## string_xrefs

- `0x1800833df`: `CREATE TABLE x(key,value,type,atom,id,parent,fullkey,path,json HIDDEN,root HIDDEN)`

## pseudocode

```c
__int64 __fastcall jsonEachConnect(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  unsigned int v6; // esi
  __int64 v7; // rdi

  v6 = sqlite3_declare_vtab(a1, "CREATE TABLE x(key,value,type,atom,id,parent,fullkey,path,json HIDDEN,root HIDDEN)");
  if ( !v6 )
  {
    v7 = sqlite3DbMallocZero(a1, 32);
    *a5 = v7;
    if ( !v7 )
      return 7;
    sqlite3_vtab_config(a1, 2);
    *(_QWORD *)(v7 + 24) = a1;
  }
  return v6;
}

```

## disassembly

```asm
0x1800833d0  mov     [rsp+arg_0], rbx
0x1800833d5  mov     [rsp+arg_8], rsi
0x1800833da  push    rdi
0x1800833db  sub     rsp, 20h
0x1800833df  lea     rdx, aCreateTableXKe; "CREATE TABLE x(key,value,type,atom,id,p"...
0x1800833e6  mov     rbx, rcx
0x1800833e9  call    sqlite3_declare_vtab
0x1800833ee  mov     esi, eax
0x1800833f0  test    eax, eax
0x1800833f2  jnz     short loc_180083425
0x1800833f4  lea     edx, [rax+20h]
0x1800833f7  mov     rcx, rbx
0x1800833fa  call    sqlite3DbMallocZero
0x1800833ff  mov     rdx, [rsp+28h+arg_20]
0x180083404  mov     rdi, rax
0x180083407  mov     [rdx], rax
0x18008340a  test    rax, rax
0x18008340d  jnz     short loc_180083414
0x18008340f  lea     eax, [rsi+7]
0x180083412  jmp     short loc_180083427
0x180083414  mov     edx, 2
0x180083419  mov     rcx, rbx
0x18008341c  call    sqlite3_vtab_config
0x180083421  mov     [rdi+18h], rbx
0x180083425  mov     eax, esi
0x180083427  mov     rbx, [rsp+28h+arg_0]
0x18008342c  mov     rsi, [rsp+28h+arg_8]
0x180083431  add     rsp, 20h
0x180083435  pop     rdi
0x180083436  retn
```
