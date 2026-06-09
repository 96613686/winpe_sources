# StateRepository::CacheManagement::GetIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *,ushort * *)

- ea: `0x18005b694`
- end: `0x18005b7be`
- name: `?GetIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBGPEAPEAG@Z`
- size: `298`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Context_NoThrow *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x18004883c`
- `0x18005969c`
- `0x180059bd8`
- `0x18005a120`
- `0x18005a664`
- `0x18005abac`
- `0x18005b11c`
- `0x18005babc`
- `0x18005c014`
- `0x18005c588`
- `0x18005cad0`
- `0x18005cfdc`
- `0x18005d494`
- `0x1800a0d38`
- `0x1800b0cb4`
- `0x1800b3144`
- `0x1800c68d4`
- `0x1800d8940`
- `0x18010a75c`
- `0x1801535a0`
- `0x1801699ac`
- `0x18016ef68`
- `0x18026ad88`
- `0x18026bd88`
- `0x180271be4`
- `0x180273c48`

## callees

- `0x18001a9e0`
- `0x18005b694`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18005b719`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18005b719`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18005b6d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18005b6d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005b6f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005b755`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005b7ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005b6f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005b755`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005b7ae`

## string_xrefs

- `0x18005b78e`: `onecore\base\appmodel\staterepository\dataaccesslayer\cachemanagement.cpp`
- `0x18005b72d`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18005b771`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::CacheManagement::GetIndexKeys(
        struct StateRepository::Cache::Context_NoThrow *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v3; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  int Field_String; // eax
  __int64 v9; // rdx
  __int64 v11; // rcx
  int v12; // [rsp+20h] [rbp-20h]
  __int64 v13; // [rsp+28h] [rbp-18h] BYREF
  char v14; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  __int64 v16; // [rsp+50h] [rbp+10h] BYREF

  *a3 = 0;
  v3 = *(_QWORD *)a1;
  v16 = 0;
  v13 = 0;
  v14 = 1;
  v5 = SRCacheContext_OpenSubContext(v3, a2, 0, &v13);
  if ( v14 )
  {
    v6 = v16;
    v16 = v13;
    if ( v6 )
      SRCacheContext_Close(v6);
  }
  if ( (v5 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)v5,
      (int)&v16);
    v9 = 1428;
    goto LABEL_12;
  }
  v7 = v16;
  if ( v16 )
  {
    Field_String = SRCacheContext_GetField_String(v16, L"_IndexKeys", a3);
    v5 = Field_String;
    if ( Field_String < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)Field_String,
        (int)&v16);
      v9 = 1431;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\cachemanagement.cpp",
        (const char *)v5,
        v12);
      v11 = v16;
      v16 = 0;
      if ( v11 )
        SRCacheContext_Close(v11);
      return v5;
    }
    v7 = v16;
  }
  v16 = 0;
  if ( v7 )
    SRCacheContext_Close(v7);
  return 0;
}

```

## disassembly

```asm
0x18005b694  mov     [rsp-8+arg_8], rbx
0x18005b699  mov     [rsp-8+arg_10], rdi
0x18005b69e  push    rbp
0x18005b69f  mov     rbp, rsp
0x18005b6a2  sub     rsp, 40h
0x18005b6a6  mov     qword ptr [r8], 0
0x18005b6ad  lea     rax, [rbp+arg_0]
0x18005b6b1  mov     rcx, [rcx]
0x18005b6b4  lea     r9, [rbp+var_18]
0x18005b6b8  mov     rdi, r8
0x18005b6bb  mov     [rbp+var_20], rax
0x18005b6bf  xor     r8d, r8d
0x18005b6c2  mov     [rbp+arg_0], 0
0x18005b6ca  mov     [rbp+var_18], 0
0x18005b6d2  mov     [rbp+var_10], 1
0x18005b6d6  call    cs:__imp_SRCacheContext_OpenSubContext
0x18005b6dc  cmp     [rbp+var_10], 0
0x18005b6e0  mov     ebx, eax
0x18005b6e2  jz      short loc_18005B6FD
0x18005b6e4  mov     r8, [rbp+var_20]
0x18005b6e8  mov     rdx, [rbp+var_18]
0x18005b6ec  mov     rcx, [r8]
0x18005b6ef  mov     [r8], rdx
0x18005b6f2  test    rcx, rcx
0x18005b6f5  jz      short loc_18005B6FD
0x18005b6f7  call    cs:__imp_SRCacheContext_Close
0x18005b6fd  test    ebx, ebx
0x18005b6ff  js      short loc_18005B76D
0x18005b701  mov     rcx, [rbp+arg_0]
0x18005b705  test    rcx, rcx
0x18005b708  setnz   al
0x18005b70b  test    al, al
0x18005b70d  jz      short loc_18005B748
0x18005b70f  mov     r8, rdi
0x18005b712  lea     rdx, ?_IndexKeys@Constants@Cache@StateRepository@@3QBGB; "_IndexKeys"
0x18005b719  call    cs:__imp_SRCacheContext_GetField_String
0x18005b71f  mov     ebx, eax
0x18005b721  test    eax, eax
0x18005b723  jns     loc_18005B7B8
0x18005b729  mov     rcx, [rbp+8]; this
0x18005b72d  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18005b734  mov     r9d, eax; char *
0x18005b737  mov     edx, 246h; void *
0x18005b73c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b741  mov     edx, 597h
0x18005b746  jmp     short loc_18005B78A
0x18005b748  mov     [rbp+arg_0], 0
0x18005b750  test    rcx, rcx
0x18005b753  jz      short loc_18005B75B
0x18005b755  call    cs:__imp_SRCacheContext_Close
0x18005b75b  xor     eax, eax
0x18005b75d  mov     rbx, [rsp+40h+arg_8]
0x18005b762  mov     rdi, [rsp+40h+arg_10]
0x18005b767  add     rsp, 40h
0x18005b76b  pop     rbp
0x18005b76c  retn
0x18005b76d  mov     rcx, [rbp+8]; this
0x18005b771  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18005b778  mov     r9d, ebx; char *
0x18005b77b  mov     edx, 1B0h; void *
0x18005b780  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b785  mov     edx, 594h; void *
0x18005b78a  mov     rcx, [rbp+8]; this
0x18005b78e  lea     r8, aOnecoreBaseApp_221; "onecore\\base\\appmodel\\staterepositor"...
0x18005b795  mov     r9d, ebx; char *
0x18005b798  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b79d  mov     rcx, [rbp+arg_0]
0x18005b7a1  mov     [rbp+arg_0], 0
0x18005b7a9  test    rcx, rcx
0x18005b7ac  jz      short loc_18005B7B4
0x18005b7ae  call    cs:__imp_SRCacheContext_Close
0x18005b7b4  mov     eax, ebx
0x18005b7b6  jmp     short loc_18005B75D
0x18005b7b8  mov     rcx, [rbp+arg_0]
0x18005b7bc  jmp     short loc_18005B748
```
