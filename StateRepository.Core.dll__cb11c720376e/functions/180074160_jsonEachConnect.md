# jsonEachConnect

- ea: `0x180074160`
- end: `0x1800741c7`
- name: `jsonEachConnect`
- size: `103`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000f720`
- `0x180074160`
- `0x18008dfb0`
- `0x180090eb0`

## string_xrefs

- `0x18007416f`: `CREATE TABLE x(key,value,type,atom,id,parent,fullkey,path,json HIDDEN,root HIDDEN)`

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
      return v6 + 7;
    sqlite3_vtab_config(a1, 2);
    *(_QWORD *)(v7 + 24) = a1;
  }
  return v6;
}

```

## disassembly

```asm
0x180074160  mov     [rsp+arg_0], rbx
0x180074165  mov     [rsp+arg_8], rsi
0x18007416a  push    rdi
0x18007416b  sub     rsp, 20h
0x18007416f  lea     rdx, aCreateTableXKe; "CREATE TABLE x(key,value,type,atom,id,p"...
0x180074176  mov     rbx, rcx
0x180074179  call    sqlite3_declare_vtab
0x18007417e  mov     esi, eax
0x180074180  test    eax, eax
0x180074182  jnz     short loc_1800741B5
0x180074184  lea     edx, [rax+20h]
0x180074187  mov     rcx, rbx
0x18007418a  call    sqlite3DbMallocZero
0x18007418f  mov     rdx, [rsp+28h+arg_20]
0x180074194  mov     rdi, rax
0x180074197  mov     [rdx], rax
0x18007419a  test    rax, rax
0x18007419d  jnz     short loc_1800741A4
0x18007419f  lea     eax, [rsi+7]
0x1800741a2  jmp     short loc_1800741B7
0x1800741a4  mov     edx, 2
0x1800741a9  mov     rcx, rbx
0x1800741ac  call    sqlite3_vtab_config
0x1800741b1  mov     [rdi+18h], rbx
0x1800741b5  mov     eax, esi
0x1800741b7  mov     rbx, [rsp+28h+arg_0]
0x1800741bc  mov     rsi, [rsp+28h+arg_8]
0x1800741c1  add     rsp, 20h
0x1800741c5  pop     rdi
0x1800741c6  retn
```
