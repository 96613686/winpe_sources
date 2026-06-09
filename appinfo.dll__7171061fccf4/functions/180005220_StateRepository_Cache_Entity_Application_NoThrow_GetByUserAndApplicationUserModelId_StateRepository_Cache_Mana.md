# StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)

- ea: `0x180005220`
- end: `0x1800053bc`
- name: `?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a938`
- `0x180018228`
- `0x180035698`

## callees

- `0x180005220`
- `0x180005d20`
- `0x18000720c`
- `0x1800089e0`
- `0x180009414`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005325`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000537f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005398`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005325`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000537f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005398`

## string_xrefs

- `0x1800052ee`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18000524a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180005302`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000535c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  _BYTE *v6; // rbx
  int v10; // ebp
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-48h]
  int v19; // [rsp+20h] [rbp-48h]
  int v20; // [rsp+20h] [rbp-48h]
  __int128 v21; // [rsp+30h] [rbp-38h] BYREF
  __int128 v22; // [rsp+40h] [rbp-28h]
  __int128 v23; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v6 = (_BYTE *)a6;
  *(_BYTE *)a6 = 0;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x573,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      v18);
    return 2147942487LL;
  }
  a6 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v10 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(a1, a2, a3, &a6);
  if ( v10 < 0 )
  {
    v12 = 468;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v10,
      v18);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x578,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v10,
      v19);
    v13 = *((_QWORD *)&v23 + 1);
    *((_QWORD *)&v23 + 1) = 0;
    if ( v13 )
      SRCache_Free();
    return (unsigned int)v10;
  }
  if ( a6 )
  {
    v18 = (int)v6;
    v10 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(a1, a6, v11, &v21);
    if ( v10 < 0 )
    {
      v12 = 471;
      goto LABEL_8;
    }
  }
  if ( *v6
    && (v20 = (int)v6,
        v14 = StateRepository::Cache::Entity::Application_NoThrow::Get(a1, *((_QWORD *)&v22 + 1), a4, a5),
        v15 = v14,
        v14 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v14,
      v20);
    v16 = *((_QWORD *)&v23 + 1);
    *((_QWORD *)&v23 + 1) = 0;
    if ( v16 )
      SRCache_Free();
    return v15;
  }
  else
  {
    v17 = *((_QWORD *)&v23 + 1);
    *((_QWORD *)&v23 + 1) = 0;
    if ( v17 )
      SRCache_Free();
    return 0;
  }
}

```

## disassembly

```asm
0x180005220  mov     [rsp+arg_10], rbx
0x180005225  mov     [rsp+arg_18], rsi
0x18000522a  push    rdi
0x18000522b  sub     rsp, 60h
0x18000522f  mov     rbx, [rsp+68h+arg_28]
0x180005237  mov     rsi, r9
0x18000523a  mov     rdi, rcx
0x18000523d  mov     byte ptr [rbx], 0
0x180005240  test    rdx, rdx
0x180005243  jnz     short loc_180005278
0x180005245  mov     rcx, [rsp+68h]; this
0x18000524a  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005251  mov     r9d, 80070057h; char *
0x180005257  mov     edx, 573h; void *
0x18000525c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005261  mov     eax, 80070057h
0x180005266  lea     r11, [rsp+68h+var_8]
0x18000526b  mov     rbx, [r11+20h]
0x18000526f  mov     rsi, [r11+28h]
0x180005273  mov     rsp, r11
0x180005276  pop     rdi
0x180005277  retn
0x180005278  xorps   xmm0, xmm0
0x18000527b  mov     [rsp+68h+arg_0], rbp
0x180005280  xorps   xmm1, xmm1
0x180005283  mov     [rsp+68h+arg_8], r14
0x180005288  xor     r14d, r14d
0x18000528b  lea     r9, [rsp+68h+arg_28]; __int64 *
0x180005293  mov     [rsp+68h+arg_28], r14
0x18000529b  movdqu  [rsp+68h+var_38], xmm0
0x1800052a1  movdqu  [rsp+68h+var_28], xmm1
0x1800052a7  movdqu  [rsp+68h+var_18], xmm0
0x1800052ad  call    ?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)
0x1800052b2  mov     ebp, eax
0x1800052b4  test    eax, eax
0x1800052b6  jns     short loc_1800052BF
0x1800052b8  mov     edx, 1D4h
0x1800052bd  jmp     short loc_1800052E9
0x1800052bf  mov     rdx, [rsp+68h+arg_28]
0x1800052c7  test    rdx, rdx
0x1800052ca  jz      short loc_18000532F
0x1800052cc  lea     r9, [rsp+68h+var_38]
0x1800052d1  mov     qword ptr [rsp+68h+var_48], rbx; int
0x1800052d6  mov     rcx, rdi
0x1800052d9  call    ?Get@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)
0x1800052de  mov     ebp, eax
0x1800052e0  test    eax, eax
0x1800052e2  jns     short loc_18000532F
0x1800052e4  mov     edx, 1D7h; void *
0x1800052e9  mov     rcx, [rsp+68h]; this
0x1800052ee  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800052f5  mov     r9d, ebp; char *
0x1800052f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052fd  mov     rcx, [rsp+68h]; this
0x180005302  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005309  mov     r9d, ebp; char *
0x18000530c  mov     edx, 578h; void *
0x180005311  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005316  mov     rcx, qword ptr [rsp+68h+var_18+8]
0x18000531b  mov     qword ptr [rsp+68h+var_18+8], r14
0x180005320  test    rcx, rcx
0x180005323  jz      short loc_18000532B
0x180005325  call    cs:__imp_SRCache_Free
0x18000532b  mov     eax, ebp
0x18000532d  jmp     short loc_1800053A0
0x18000532f  cmp     [rbx], r14b
0x180005332  jz      short loc_180005389
0x180005334  mov     r9, [rsp+68h+arg_20]
0x18000533c  mov     r8, rsi
0x18000533f  mov     rdx, qword ptr [rsp+68h+var_28+8]
0x180005344  mov     rcx, rdi
0x180005347  mov     qword ptr [rsp+68h+var_48], rbx; int
0x18000534c  call    ?Get@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180005351  mov     ebx, eax
0x180005353  test    eax, eax
0x180005355  jns     short loc_180005389
0x180005357  mov     rcx, [rsp+68h]; this
0x18000535c  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005363  mov     r9d, eax; char *
0x180005366  mov     edx, 57Ch; void *
0x18000536b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005370  mov     rcx, qword ptr [rsp+68h+var_18+8]
0x180005375  mov     qword ptr [rsp+68h+var_18+8], r14
0x18000537a  test    rcx, rcx
0x18000537d  jz      short loc_180005385
0x18000537f  call    cs:__imp_SRCache_Free
0x180005385  mov     eax, ebx
0x180005387  jmp     short loc_1800053A0
0x180005389  mov     rcx, qword ptr [rsp+68h+var_18+8]
0x18000538e  mov     qword ptr [rsp+68h+var_18+8], r14
0x180005393  test    rcx, rcx
0x180005396  jz      short loc_18000539E
0x180005398  call    cs:__imp_SRCache_Free
0x18000539e  xor     eax, eax
0x1800053a0  mov     rbp, [rsp+68h+arg_0]
0x1800053a5  lea     r11, [rsp+68h+var_8]
0x1800053aa  mov     rbx, [r11+20h]
0x1800053ae  mov     rsi, [r11+28h]
0x1800053b2  mov     r14, [rsp+68h+arg_8]
0x1800053b7  mov     rsp, r11
0x1800053ba  pop     rdi
0x1800053bb  retn
```
