# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)

- ea: `0x18001855c`
- end: `0x180018666`
- name: `?GetActivation@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVActivation_NoThrow@234@AEA_N@Z`
- size: `266`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *this, struct StateRepository::Cache::Manager_NoThrow *, struct StateRepository::Cache::Entity::Activation_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180012b9c`

## callees

- `0x1800052b0`
- `0x180007c78`
- `0x18000e4d0`
- `0x18001855c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018609`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018642`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018609`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018642`

## string_xrefs

- `0x18001861a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180018587`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x1800185ea`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int16 **a3,
        bool *a4)
{
  unsigned __int16 *v4; // rdi
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v13; // rcx
  int v14; // [rsp+20h] [rbp-8h]
  int v15; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v17; // [rsp+30h] [rbp+8h] BYREF

  v4 = (unsigned __int16 *)*((_QWORD *)this + 4);
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
         (unsigned __int64)v4,
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
    v8 = StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(
           (StateRepository::Cache::Context_NoThrow *)&v17,
           a3,
           v9,
           v4);
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
0x18001855c  mov     [rsp+arg_8], rbx
0x180018561  mov     [rsp+arg_10], rbp
0x180018566  mov     [rsp+arg_18], rsi
0x18001856b  push    rdi; int
0x18001856c  sub     rsp, 20h
0x180018570  mov     rdi, [rcx+20h]
0x180018574  mov     rsi, r9
0x180018577  mov     rbp, r8
0x18001857a  mov     rax, rdx
0x18001857d  test    rdi, rdi
0x180018580  jnz     short loc_1800185A2
0x180018582  mov     rcx, [rsp+28h]; this
0x180018587  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001858e  mov     ebx, 80070057h
0x180018593  mov     edx, 137h; void *
0x180018598  mov     r9d, ebx; char *
0x18001859b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800185a0  jmp     short loc_180018615
0x1800185a2  and     [rsp+28h+arg_0], 0
0x1800185a8  lea     r8, [rsp+28h+arg_0]; struct StateRepository::Cache::Context_NoThrow *
0x1800185ad  mov     rdx, rdi; __int64
0x1800185b0  mov     rcx, rax; struct StateRepository::Cache::Manager_NoThrow *
0x1800185b3  call    ?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800185b8  mov     ebx, eax
0x1800185ba  test    eax, eax
0x1800185bc  jns     short loc_1800185C5
0x1800185be  mov     edx, 13Ah
0x1800185c3  jmp     short loc_1800185E5
0x1800185c5  cmp     byte ptr [rsi], 0
0x1800185c8  jz      short loc_180018632
0x1800185ca  mov     r9, rdi
0x1800185cd  lea     rcx, [rsp+28h+arg_0]
0x1800185d2  mov     rdx, rbp
0x1800185d5  call    ?ContextToObject@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,__int64)
0x1800185da  mov     ebx, eax
0x1800185dc  test    eax, eax
0x1800185de  jns     short loc_180018632
0x1800185e0  mov     edx, 13Fh; void *
0x1800185e5  mov     rcx, [rsp+28h]; this
0x1800185ea  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800185f1  mov     r9d, eax; char *
0x1800185f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800185f9  mov     rcx, [rsp+28h+arg_0]
0x1800185fe  and     [rsp+28h+arg_0], 0
0x180018604  test    rcx, rcx
0x180018607  jz      short loc_180018615
0x180018609  call    cs:__imp_SRCacheContext_Close
0x180018610  nop     dword ptr [rax+rax+00h]
0x180018615  mov     rcx, [rsp+28h]; this
0x18001861a  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180018621  mov     r9d, ebx; char *
0x180018624  mov     edx, 360h; void *
0x180018629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001862e  mov     eax, ebx
0x180018630  jmp     short loc_180018650
0x180018632  mov     rcx, [rsp+28h+arg_0]
0x180018637  and     [rsp+28h+arg_0], 0
0x18001863d  test    rcx, rcx
0x180018640  jz      short loc_18001864E
0x180018642  call    cs:__imp_SRCacheContext_Close
0x180018649  nop     dword ptr [rax+rax+00h]
0x18001864e  xor     eax, eax
0x180018650  mov     rbx, [rsp+28h+arg_8]
0x180018655  mov     rbp, [rsp+28h+arg_10]
0x18001865a  mov     rsi, [rsp+28h+arg_18]
0x18001865f  add     rsp, 20h
0x180018663  pop     rdi
0x180018664  retn
```
