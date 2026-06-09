# jsonEachConnect

- ea: `0x180066340`
- end: `0x1800663a7`
- name: `jsonEachConnect`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18002b8ec`
- `0x180066340`
- `0x180095340`
- `0x180099070`

## string_xrefs

- `0x18006634f`: `CREATE TABLE x(key,value,type,atom,id,parent,fullkey,path,json HIDDEN,root HIDDEN)`

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
0x180066340  mov     [rsp+arg_0], rbx
0x180066345  mov     [rsp+arg_8], rsi
0x18006634a  push    rdi
0x18006634b  sub     rsp, 20h
0x18006634f  lea     rdx, aCreateTableXKe; "CREATE TABLE x(key,value,type,atom,id,p"...
0x180066356  mov     rbx, rcx
0x180066359  call    sqlite3_declare_vtab
0x18006635e  mov     esi, eax
0x180066360  test    eax, eax
0x180066362  jnz     short loc_180066395
0x180066364  lea     edx, [rax+20h]
0x180066367  mov     rcx, rbx
0x18006636a  call    sqlite3DbMallocZero
0x18006636f  mov     rdx, [rsp+28h+arg_20]
0x180066374  mov     rdi, rax
0x180066377  mov     [rdx], rax
0x18006637a  test    rax, rax
0x18006637d  jnz     short loc_180066384
0x18006637f  lea     eax, [rsi+7]
0x180066382  jmp     short loc_180066397
0x180066384  mov     edx, 2
0x180066389  mov     rcx, rbx
0x18006638c  call    sqlite3_vtab_config
0x180066391  mov     [rdi+18h], rbx
0x180066395  mov     eax, esi
0x180066397  mov     rbx, [rsp+28h+arg_0]
0x18006639c  mov     rsi, [rsp+28h+arg_8]
0x1800663a1  add     rsp, 20h
0x1800663a5  pop     rdi
0x1800663a6  retn
```
