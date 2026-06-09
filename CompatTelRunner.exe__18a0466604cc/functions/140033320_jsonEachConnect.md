# jsonEachConnect

- ea: `0x140033320`
- end: `0x140033398`
- name: `jsonEachConnect`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x140033320`
- `0x140062c2c`
- `0x140089cf0`
- `0x14008b1cc`
- `0x14008ffd0`

## string_xrefs

- `0x14003332a`: `CREATE TABLE x(key,value,type,atom,id,parent,fullkey,path,json HIDDEN,root HIDDEN)`

## pseudocode

```c
__int64 __fastcall jsonEachConnect(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  unsigned int v6; // ebx
  __int64 v7; // rax

  v6 = sqlite3_declare_vtab(a1, "CREATE TABLE x(key,value,type,atom,id,parent,fullkey,path,json HIDDEN,root HIDDEN)");
  if ( !v6 )
  {
    if ( (unsigned int)sqlite3_initialize() )
    {
      *a5 = 0;
      return 7;
    }
    v7 = sqlite3Malloc(24);
    *a5 = v7;
    if ( !v7 )
      return 7;
    *(_OWORD *)v7 = 0;
    *(_QWORD *)(v7 + 16) = 0;
    sqlite3_vtab_config(a1, 2);
  }
  return v6;
}

```

## disassembly

```asm
0x140033320  mov     [rsp+arg_0], rbx
0x140033325  push    rdi
0x140033326  sub     rsp, 20h
0x14003332a  lea     rdx, aCreateTableXKe; "CREATE TABLE x(key,value,type,atom,id,p"...
0x140033331  mov     rdi, rcx
0x140033334  call    sqlite3_declare_vtab
0x140033339  mov     ebx, eax
0x14003333b  test    eax, eax
0x14003333d  jnz     short loc_14003338B
0x14003333f  call    sqlite3_initialize
0x140033344  test    eax, eax
0x140033346  jz      short loc_140033356
0x140033348  mov     rax, [rsp+28h+arg_20]
0x14003334d  mov     qword ptr [rax], 0
0x140033354  jmp     short loc_14003336D
0x140033356  mov     ecx, 18h
0x14003335b  call    sqlite3Malloc
0x140033360  mov     rcx, [rsp+28h+arg_20]
0x140033365  mov     [rcx], rax
0x140033368  test    rax, rax
0x14003336b  jnz     short loc_140033374
0x14003336d  mov     eax, 7
0x140033372  jmp     short loc_14003338D
0x140033374  xor     ecx, ecx
0x140033376  xorps   xmm0, xmm0
0x140033379  movups  xmmword ptr [rax], xmm0
0x14003337c  mov     [rax+10h], rcx
0x140033380  lea     edx, [rcx+2]
0x140033383  mov     rcx, rdi
0x140033386  call    sqlite3_vtab_config
0x14003338b  mov     eax, ebx
0x14003338d  mov     rbx, [rsp+28h+arg_0]
0x140033392  add     rsp, 20h
0x140033396  pop     rdi
0x140033397  retn
```
