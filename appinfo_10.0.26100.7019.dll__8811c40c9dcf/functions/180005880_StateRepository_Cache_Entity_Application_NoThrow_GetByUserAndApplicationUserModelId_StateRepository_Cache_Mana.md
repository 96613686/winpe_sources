# StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)

- ea: `0x180005880`
- end: `0x180005a40`
- name: `?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `448`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180012b9c`
- `0x1800320a8`
- `0x180038740`

## callees

- `0x180004814`
- `0x180005880`
- `0x180005a40`
- `0x180007c78`
- `0x180008590`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005986`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800059e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005a05`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005986`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800059e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005a05`

## string_xrefs

- `0x18000594f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x1800058aa`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180005963`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800059c3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  bool *v6; // rbx
  int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // ebp
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // [rsp+20h] [rbp-48h]
  int v23; // [rsp+20h] [rbp-48h]
  int v24; // [rsp+20h] [rbp-48h]
  __int128 v25; // [rsp+30h] [rbp-38h] BYREF
  __int128 v26; // [rsp+40h] [rbp-28h]
  __int128 v27; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v6 = (bool *)a6;
  *(_BYTE *)a6 = 0;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x573,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      v22);
    return 2147942487LL;
  }
  a6 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v10 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(a1, a2, a3, &a6);
  v12 = v10;
  if ( v10 < 0 )
  {
    v13 = 468;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v10,
      v22);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x578,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)v12,
      v23);
    v16 = *((_QWORD *)&v27 + 1);
    *((_QWORD *)&v27 + 1) = 0;
    if ( v16 )
      SRCache_Free(v16, v15);
    return v12;
  }
  v14 = a6;
  if ( a6 )
  {
    v22 = (int)v6;
    v10 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(a1, a6, v11, &v25);
    v12 = v10;
    if ( v10 < 0 )
    {
      v13 = 471;
      goto LABEL_8;
    }
  }
  if ( *v6
    && (v17 = StateRepository::Cache::Entity::Application_NoThrow::Get(
                (__int64 *)a1,
                *((unsigned __int64 *)&v26 + 1),
                a4,
                a5,
                v6),
        v18 = v17,
        v17 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v17,
      v24);
    v20 = *((_QWORD *)&v27 + 1);
    *((_QWORD *)&v27 + 1) = 0;
    if ( v20 )
      SRCache_Free(v20, v19);
    return v18;
  }
  else
  {
    v21 = *((_QWORD *)&v27 + 1);
    *((_QWORD *)&v27 + 1) = 0;
    if ( v21 )
      SRCache_Free(v21, v14);
    return 0;
  }
}

```

## disassembly

```asm
0x180005880  mov     [rsp+arg_10], rbx
0x180005885  mov     [rsp+arg_18], rsi
0x18000588a  push    rdi
0x18000588b  sub     rsp, 60h
0x18000588f  mov     rbx, [rsp+68h+arg_28]
0x180005897  mov     rsi, r9
0x18000589a  mov     rdi, rcx
0x18000589d  mov     byte ptr [rbx], 0
0x1800058a0  test    rdx, rdx
0x1800058a3  jnz     short loc_1800058D9
0x1800058a5  mov     rcx, [rsp+68h]; this
0x1800058aa  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800058b1  mov     r9d, 80070057h; char *
0x1800058b7  mov     edx, 573h; void *
0x1800058bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800058c1  mov     eax, 80070057h
0x1800058c6  lea     r11, [rsp+68h+var_8]
0x1800058cb  mov     rbx, [r11+20h]
0x1800058cf  mov     rsi, [r11+28h]
0x1800058d3  mov     rsp, r11
0x1800058d6  pop     rdi
0x1800058d7  retn
0x1800058d9  xorps   xmm0, xmm0
0x1800058dc  mov     [rsp+68h+arg_0], rbp
0x1800058e1  xorps   xmm1, xmm1
0x1800058e4  mov     [rsp+68h+arg_8], r14
0x1800058e9  xor     r14d, r14d
0x1800058ec  lea     r9, [rsp+68h+arg_28]; __int64 *
0x1800058f4  mov     [rsp+68h+arg_28], r14
0x1800058fc  movdqu  [rsp+68h+var_38], xmm0
0x180005902  movdqu  [rsp+68h+var_28], xmm1
0x180005908  movdqu  [rsp+68h+var_18], xmm0
0x18000590e  call    ?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)
0x180005913  mov     ebp, eax
0x180005915  test    eax, eax
0x180005917  jns     short loc_180005920
0x180005919  mov     edx, 1D4h
0x18000591e  jmp     short loc_18000594A
0x180005920  mov     rdx, [rsp+68h+arg_28]
0x180005928  test    rdx, rdx
0x18000592b  jz      short loc_180005996
0x18000592d  lea     r9, [rsp+68h+var_38]
0x180005932  mov     qword ptr [rsp+68h+var_48], rbx; int
0x180005937  mov     rcx, rdi
0x18000593a  call    ?Get@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)
0x18000593f  mov     ebp, eax
0x180005941  test    eax, eax
0x180005943  jns     short loc_180005996
0x180005945  mov     edx, 1D7h; void *
0x18000594a  mov     rcx, [rsp+68h]; this
0x18000594f  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005956  mov     r9d, eax; char *
0x180005959  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000595e  mov     rcx, [rsp+68h]; this
0x180005963  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000596a  mov     r9d, ebp; char *
0x18000596d  mov     edx, 578h; void *
0x180005972  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005977  mov     rcx, qword ptr [rsp+68h+var_18+8]
0x18000597c  mov     qword ptr [rsp+68h+var_18+8], r14
0x180005981  test    rcx, rcx
0x180005984  jz      short loc_180005992
0x180005986  call    cs:__imp_SRCache_Free
0x18000598d  nop     dword ptr [rax+rax+00h]
0x180005992  mov     eax, ebp
0x180005994  jmp     short loc_180005A13
0x180005996  cmp     [rbx], r14b
0x180005999  jz      short loc_1800059F6
0x18000599b  mov     r9, [rsp+68h+arg_20]
0x1800059a3  mov     r8, rsi
0x1800059a6  mov     rdx, qword ptr [rsp+68h+var_28+8]
0x1800059ab  mov     rcx, rdi
0x1800059ae  mov     qword ptr [rsp+68h+var_48], rbx; int
0x1800059b3  call    ?Get@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x1800059b8  mov     ebx, eax
0x1800059ba  test    eax, eax
0x1800059bc  jns     short loc_1800059F6
0x1800059be  mov     rcx, [rsp+68h]; this
0x1800059c3  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800059ca  mov     r9d, eax; char *
0x1800059cd  mov     edx, 57Ch; void *
0x1800059d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800059d7  mov     rcx, qword ptr [rsp+68h+var_18+8]
0x1800059dc  mov     qword ptr [rsp+68h+var_18+8], r14
0x1800059e1  test    rcx, rcx
0x1800059e4  jz      short loc_1800059F2
0x1800059e6  call    cs:__imp_SRCache_Free
0x1800059ed  nop     dword ptr [rax+rax+00h]
0x1800059f2  mov     eax, ebx
0x1800059f4  jmp     short loc_180005A13
0x1800059f6  mov     rcx, qword ptr [rsp+68h+var_18+8]
0x1800059fb  mov     qword ptr [rsp+68h+var_18+8], r14
0x180005a00  test    rcx, rcx
0x180005a03  jz      short loc_180005A11
0x180005a05  call    cs:__imp_SRCache_Free
0x180005a0c  nop     dword ptr [rax+rax+00h]
0x180005a11  xor     eax, eax
0x180005a13  mov     rbp, [rsp+68h+arg_0]
0x180005a18  lea     r11, [rsp+68h+var_8]
0x180005a1d  mov     rbx, [r11+20h]
0x180005a21  mov     rsi, [r11+28h]
0x180005a25  mov     r14, [rsp+68h+arg_8]
0x180005a2a  mov     rsp, r11
0x180005a2d  pop     rdi
0x180005a2e  retn
```
