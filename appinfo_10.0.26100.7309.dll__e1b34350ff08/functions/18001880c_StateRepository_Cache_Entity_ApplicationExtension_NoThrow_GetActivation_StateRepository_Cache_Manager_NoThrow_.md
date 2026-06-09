# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)

- ea: `0x18001880c`
- end: `0x180018916`
- name: `?GetActivation@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVActivation_NoThrow@234@AEA_N@Z`
- size: `266`
- prototype: `int(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, struct StateRepository::Cache::Entity::Activation_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180012cdc`

## callees

- `0x1800052b0`
- `0x180007c78`
- `0x18000e410`
- `0x18001880c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800188b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800188f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800188b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800188f2`

## string_xrefs

- `0x1800188ca`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180018837`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18001889a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

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
0x18001880c  mov     [rsp+arg_8], rbx
0x180018811  mov     [rsp+arg_10], rbp
0x180018816  mov     [rsp+arg_18], rsi
0x18001881b  push    rdi; int
0x18001881c  sub     rsp, 20h
0x180018820  mov     rdi, [rcx+20h]
0x180018824  mov     rsi, r9
0x180018827  mov     rbp, r8
0x18001882a  mov     rax, rdx
0x18001882d  test    rdi, rdi
0x180018830  jnz     short loc_180018852
0x180018832  mov     rcx, [rsp+28h]; this
0x180018837  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001883e  mov     ebx, 80070057h
0x180018843  mov     edx, 137h; void *
0x180018848  mov     r9d, ebx; char *
0x18001884b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018850  jmp     short loc_1800188C5
0x180018852  and     [rsp+28h+arg_0], 0
0x180018858  lea     r8, [rsp+28h+arg_0]; struct StateRepository::Cache::Context_NoThrow *
0x18001885d  mov     rdx, rdi; __int64
0x180018860  mov     rcx, rax; struct StateRepository::Cache::Manager_NoThrow *
0x180018863  call    ?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180018868  mov     ebx, eax
0x18001886a  test    eax, eax
0x18001886c  jns     short loc_180018875
0x18001886e  mov     edx, 13Ah
0x180018873  jmp     short loc_180018895
0x180018875  cmp     byte ptr [rsi], 0
0x180018878  jz      short loc_1800188E2
0x18001887a  mov     r9, rdi
0x18001887d  lea     rcx, [rsp+28h+arg_0]
0x180018882  mov     rdx, rbp
0x180018885  call    ?ContextToObject@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,__int64)
0x18001888a  mov     ebx, eax
0x18001888c  test    eax, eax
0x18001888e  jns     short loc_1800188E2
0x180018890  mov     edx, 13Fh; void *
0x180018895  mov     rcx, [rsp+28h]; this
0x18001889a  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800188a1  mov     r9d, eax; char *
0x1800188a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188a9  mov     rcx, [rsp+28h+arg_0]
0x1800188ae  and     [rsp+28h+arg_0], 0
0x1800188b4  test    rcx, rcx
0x1800188b7  jz      short loc_1800188C5
0x1800188b9  call    cs:__imp_SRCacheContext_Close
0x1800188c0  nop     dword ptr [rax+rax+00h]
0x1800188c5  mov     rcx, [rsp+28h]; this
0x1800188ca  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800188d1  mov     r9d, ebx; char *
0x1800188d4  mov     edx, 360h; void *
0x1800188d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188de  mov     eax, ebx
0x1800188e0  jmp     short loc_180018900
0x1800188e2  mov     rcx, [rsp+28h+arg_0]
0x1800188e7  and     [rsp+28h+arg_0], 0
0x1800188ed  test    rcx, rcx
0x1800188f0  jz      short loc_1800188FE
0x1800188f2  call    cs:__imp_SRCacheContext_Close
0x1800188f9  nop     dword ptr [rax+rax+00h]
0x1800188fe  xor     eax, eax
0x180018900  mov     rbx, [rsp+28h+arg_8]
0x180018905  mov     rbp, [rsp+28h+arg_10]
0x18001890a  mov     rsi, [rsp+28h+arg_18]
0x18001890f  add     rsp, 20h
0x180018913  pop     rdi
0x180018914  retn
```
