# StateRepository::Migration::Context::Open(StateRepository::Partition,StateRepository::Database &)

- ea: `0x18000c1f4`
- end: `0x18000c25d`
- name: `?Open@Context@Migration@StateRepository@@QEBAJW4Partition@3@AEAVDatabase@3@@Z`
- size: `105`
- prototype: `__int64 __fastcall(__int64, unsigned int, StateRepository::Database *)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bb64`
- `0x18000c9b0`
- `0x18000d0a0`
- `0x18000e620`
- `0x18000ec40`
- `0x18000ed80`
- `0x180012e90`
- `0x180013750`
- `0x180013980`
- `0x180013c40`
- `0x180014350`
- `0x1800145e0`

## callees

- `0x18000a3c0`
- `0x18000c1f4`
- `0x180018804`

## import_xrefs

- `Windows.StateRepository!StateRepository_DataAccessLayer_DatabaseCache_Get` at `0x18000c238`
- `Windows.StateRepository!StateRepository_DataAccessLayer_DatabaseCache_Get` at `0x18000c238`

## pseudocode

```c
__int64 __fastcall StateRepository::Migration::Context::Open(
        __int64 a1,
        unsigned int a2,
        StateRepository::Database *a3)
{
  int v5; // ebx
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = StateRepository::Database::Close(a3);
  if ( v5 < 0 )
  {
    v6 = 77;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\inc\\Context.hpp",
      (const char *)(unsigned int)v5,
      v8);
    return (unsigned int)v5;
  }
  v5 = StateRepository_DataAccessLayer_DatabaseCache_Get(a2, a3);
  if ( v5 < 0 )
  {
    v6 = 79;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c1f4  mov     [rsp+arg_0], rbx
0x18000c1f9  mov     [rsp+arg_8], rsi
0x18000c1fe  push    rdi; int
0x18000c1ff  sub     rsp, 20h
0x18000c203  mov     rcx, r8; this
0x18000c206  mov     rdi, r8
0x18000c209  mov     esi, edx
0x18000c20b  call    ?Close@Database@StateRepository@@QEAAJXZ; StateRepository::Database::Close(void)
0x18000c210  mov     ebx, eax
0x18000c212  test    eax, eax
0x18000c214  jns     short loc_18000C233
0x18000c216  mov     edx, 4Dh ; 'M'; void *
0x18000c21b  mov     rcx, [rsp+28h]; this
0x18000c220  lea     r8, aOnecoreBaseApp_47; "onecore\\base\\appmodel\\staterepositor"...
0x18000c227  mov     r9d, ebx; char *
0x18000c22a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c22f  mov     eax, ebx
0x18000c231  jmp     short loc_18000C24D
0x18000c233  mov     rdx, rdi
0x18000c236  mov     ecx, esi
0x18000c238  call    cs:__imp_StateRepository_DataAccessLayer_DatabaseCache_Get
0x18000c23e  mov     ebx, eax
0x18000c240  test    eax, eax
0x18000c242  jns     short loc_18000C24B
0x18000c244  mov     edx, 4Fh ; 'O'
0x18000c249  jmp     short loc_18000C21B
0x18000c24b  xor     eax, eax
0x18000c24d  mov     rbx, [rsp+28h+arg_0]
0x18000c252  mov     rsi, [rsp+28h+arg_8]
0x18000c257  add     rsp, 20h
0x18000c25b  pop     rdi
0x18000c25c  retn
```
