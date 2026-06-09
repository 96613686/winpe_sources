# StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)

- ea: `0x18002d548`
- end: `0x18002d63b`
- name: `?Get@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `243`
- prototype: `static int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, enum StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags, struct StateRepository::Cache::Entity::PackageFamily_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180033538`

## callees

- `0x180007c78`
- `0x18002c818`
- `0x18002d548`
- `0x1800352a8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d5d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d617`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d5d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d617`

## string_xrefs

- `0x18002d570`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002d5b8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        __int64 a3,
        _QWORD *a4,
        bool *a5)
{
  int v7; // ebx
  bool *v9; // rsi
  const WCHAR *v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v16; // [rsp+40h] [rbp+18h] BYREF

  v16 = a3;
  if ( !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( v7 < 0 )
  {
    v11 = 175;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    v7 = StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(
           (StateRepository::Cache::Context_NoThrow *)&v16,
           a4,
           v10,
           a2);
    if ( v7 < 0 )
    {
      v11 = 180;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
        (const char *)(unsigned int)v7,
        v14);
      v12 = v16;
      v16 = 0;
      if ( v12 )
        SRCacheContext_Close(v12);
      return (unsigned int)v7;
    }
  }
  v13 = v16;
  v16 = 0;
  if ( v13 )
    SRCacheContext_Close(v13);
  return 0;
}

```

## disassembly

```asm
0x18002d548  mov     rax, rsp
0x18002d54b  mov     [rax+8], rbx
0x18002d54f  mov     [rax+10h], rbp
0x18002d553  mov     [rax+20h], rsi
0x18002d557  mov     [rax+18h], r8
0x18002d55b  push    rdi; int
0x18002d55c  sub     rsp, 20h
0x18002d560  mov     rbp, r9
0x18002d563  mov     rdi, rdx
0x18002d566  test    rdx, rdx
0x18002d569  jnz     short loc_18002D590
0x18002d56b  mov     rcx, [rsp+28h]; this
0x18002d570  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d577  mov     ebx, 80070057h
0x18002d57c  mov     edx, 0ACh; void *
0x18002d581  mov     r9d, ebx; char *
0x18002d584  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d589  mov     eax, ebx
0x18002d58b  jmp     loc_18002D625
0x18002d590  mov     rsi, [rsp+28h+arg_20]
0x18002d595  lea     r8, [rsp+28h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18002d59a  and     [rsp+28h+arg_10], 0
0x18002d5a0  mov     r9, rsi; bool *
0x18002d5a3  call    ?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18002d5a8  mov     ebx, eax
0x18002d5aa  test    eax, eax
0x18002d5ac  jns     short loc_18002D5E5
0x18002d5ae  mov     edx, 0AFh; void *
0x18002d5b3  mov     rcx, [rsp+28h]; this
0x18002d5b8  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d5bf  mov     r9d, ebx; char *
0x18002d5c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d5c7  mov     rcx, [rsp+28h+arg_10]
0x18002d5cc  and     [rsp+28h+arg_10], 0
0x18002d5d2  test    rcx, rcx
0x18002d5d5  jz      short loc_18002D589
0x18002d5d7  call    cs:__imp_SRCacheContext_Close
0x18002d5de  nop     dword ptr [rax+rax+00h]
0x18002d5e3  jmp     short loc_18002D589
0x18002d5e5  cmp     byte ptr [rsi], 0
0x18002d5e8  jz      short loc_18002D607
0x18002d5ea  mov     r9, rdi
0x18002d5ed  lea     rcx, [rsp+28h+arg_10]
0x18002d5f2  mov     rdx, rbp
0x18002d5f5  call    ?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)
0x18002d5fa  mov     ebx, eax
0x18002d5fc  test    eax, eax
0x18002d5fe  jns     short loc_18002D607
0x18002d600  mov     edx, 0B4h
0x18002d605  jmp     short loc_18002D5B3
0x18002d607  mov     rcx, [rsp+28h+arg_10]
0x18002d60c  and     [rsp+28h+arg_10], 0
0x18002d612  test    rcx, rcx
0x18002d615  jz      short loc_18002D623
0x18002d617  call    cs:__imp_SRCacheContext_Close
0x18002d61e  nop     dword ptr [rax+rax+00h]
0x18002d623  xor     eax, eax
0x18002d625  mov     rbx, [rsp+28h+arg_0]
0x18002d62a  mov     rbp, [rsp+28h+arg_8]
0x18002d62f  mov     rsi, [rsp+28h+arg_18]
0x18002d634  add     rsp, 20h
0x18002d638  pop     rdi
0x18002d639  retn
```
