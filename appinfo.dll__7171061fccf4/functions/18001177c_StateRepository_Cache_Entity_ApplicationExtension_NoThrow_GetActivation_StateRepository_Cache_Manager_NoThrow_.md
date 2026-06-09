# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)

- ea: `0x18001177c`
- end: `0x18001186b`
- name: `?GetActivation@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVActivation_NoThrow@234@AEA_N@Z`
- size: `239`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *this, struct StateRepository::Cache::Manager_NoThrow *, struct StateRepository::Cache::Entity::Activation_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000a938`

## callees

- `0x180004a70`
- `0x18000720c`
- `0x180008600`
- `0x18001177c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180011824`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001185a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180011824`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001185a`

## string_xrefs

- `0x18001179c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x180011802`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18001182f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        struct StateRepository::Cache::Entity::Activation_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rdi
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v13; // rcx
  int v14; // [rsp+20h] [rbp-28h]
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v17; // [rsp+50h] [rbp+8h] BYREF

  v4 = *((_QWORD *)this + 4);
  if ( !v4 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)0x80070057LL,
      v14);
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x360,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)v7,
      v15);
    return v7;
  }
  v17 = 0;
  v8 = StateRepository::Cache::Entity::Activation_NoThrow::Open(
         a2,
         v4,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         a4);
  v7 = v8;
  if ( v8 < 0 )
  {
    v10 = 314;
    goto LABEL_8;
  }
  if ( *a4 )
  {
    v8 = StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(&v17, a3, v9, v4);
    v7 = v8;
    if ( v8 < 0 )
    {
      v10 = 319;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
        (const char *)(unsigned int)v8,
        v14);
      v11 = v17;
      v17 = 0;
      if ( v11 )
        SRCacheContext_Close(v11);
      goto LABEL_10;
    }
  }
  v13 = v17;
  v17 = 0;
  if ( v13 )
    SRCacheContext_Close(v13);
  return 0;
}

```

## disassembly

```asm
0x18001177c  push    rbx
0x18001177e  push    rbp
0x18001177f  push    rsi
0x180011780  push    rdi
0x180011781  sub     rsp, 28h
0x180011785  mov     rdi, [rcx+20h]
0x180011789  mov     rsi, r9
0x18001178c  mov     rbp, r8
0x18001178f  mov     rax, rdx
0x180011792  test    rdi, rdi
0x180011795  jnz     short loc_1800117B7
0x180011797  mov     rcx, [rsp+48h]; this
0x18001179c  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800117a3  mov     ebx, 80070057h
0x1800117a8  mov     edx, 137h; void *
0x1800117ad  mov     r9d, ebx; char *
0x1800117b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800117b5  jmp     short loc_18001182A
0x1800117b7  lea     r8, [rsp+48h+arg_0]; struct StateRepository::Cache::Context_NoThrow *
0x1800117bc  mov     [rsp+48h+arg_0], 0
0x1800117c5  mov     rdx, rdi; __int64
0x1800117c8  mov     rcx, rax; struct StateRepository::Cache::Manager_NoThrow *
0x1800117cb  call    ?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800117d0  mov     ebx, eax
0x1800117d2  test    eax, eax
0x1800117d4  jns     short loc_1800117DD
0x1800117d6  mov     edx, 13Ah
0x1800117db  jmp     short loc_1800117FD
0x1800117dd  cmp     byte ptr [rsi], 0
0x1800117e0  jz      short loc_180011847
0x1800117e2  mov     r9, rdi
0x1800117e5  lea     rcx, [rsp+48h+arg_0]
0x1800117ea  mov     rdx, rbp
0x1800117ed  call    ?ContextToObject@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,__int64)
0x1800117f2  mov     ebx, eax
0x1800117f4  test    eax, eax
0x1800117f6  jns     short loc_180011847
0x1800117f8  mov     edx, 13Fh; void *
0x1800117fd  mov     rcx, [rsp+48h]; this
0x180011802  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180011809  mov     r9d, eax; char *
0x18001180c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011811  mov     rcx, [rsp+48h+arg_0]
0x180011816  mov     [rsp+48h+arg_0], 0
0x18001181f  test    rcx, rcx
0x180011822  jz      short loc_18001182A
0x180011824  call    cs:__imp_SRCacheContext_Close
0x18001182a  mov     rcx, [rsp+48h]; this
0x18001182f  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180011836  mov     r9d, ebx; char *
0x180011839  mov     edx, 360h; void *
0x18001183e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011843  mov     eax, ebx
0x180011845  jmp     short loc_180011862
0x180011847  mov     rcx, [rsp+48h+arg_0]
0x18001184c  mov     [rsp+48h+arg_0], 0
0x180011855  test    rcx, rcx
0x180011858  jz      short loc_180011860
0x18001185a  call    cs:__imp_SRCacheContext_Close
0x180011860  xor     eax, eax
0x180011862  add     rsp, 28h
0x180011866  pop     rdi
0x180011867  pop     rsi
0x180011868  pop     rbp
0x180011869  pop     rbx
0x18001186a  retn
```
