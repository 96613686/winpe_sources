# StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::OpenByName(StateRepository::Cache::Manager_NoThrow &,wchar_t const *)

- ea: `0x18007a4e4`
- end: `0x18007a74d`
- name: `?OpenByName@PkgExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEB_W@Z`
- size: `617`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180078fd0`

## callees

- `0x180004ca0`
- `0x180005758`
- `0x18000b064`
- `0x180078da0`
- `0x18007a43c`
- `0x18007a4e4`
- `0x18007a754`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a64e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a6f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a70a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a64e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a6f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a70a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a527`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a588`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a5cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a71f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a527`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a588`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a5cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a71f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18007a69b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18007a69b`

## string_xrefs

- `0x18007a6ae`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007a565`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x18007a5a3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x18007a62c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x18007a6c9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x18007a536`: `PkgExtension\Index\Name`
- `0x18007a694`: `PkgExtension\Index\Name`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::OpenByName(
        StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const wchar_t *a3)
{
  __int64 v4; // rcx
  int v7; // eax
  int v8; // edi
  __int64 v9; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  bool v19[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v22[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+238h] [rbp+138h]
  __int64 v24; // [rsp+240h] [rbp+140h]
  wchar_t *v25; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v4 )
    SRCacheContext_Close();
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v20 = 0;
  v19[0] = 0;
  v7 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v20,
         a2,
         L"PkgExtension\\Index\\Name",
         v19);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x256,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v7,
      *(int *)v19);
LABEL_5:
    v9 = v20;
    v20 = 0;
    if ( v9 )
      SRCacheContext_Close();
    return (unsigned int)v8;
  }
  if ( !v19[0] )
  {
    v11 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)0x80670012LL,
      *(int *)v19);
LABEL_10:
    v12 = v20;
    v20 = 0;
    if ( v12 )
      SRCacheContext_Close();
    return v11;
  }
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v23 = 0;
  v25 = (wchar_t *)v22;
  v24 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v21, a3);
  if ( v8 < 0 )
  {
    v13 = 602;
    goto LABEL_15;
  }
  v19[0] = 0;
  v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v20,
         v25,
         v19);
  if ( v8 < 0 )
  {
    v13 = 605;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v8,
      *(int *)v19);
    v14 = v21;
    v21 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_5;
  }
  if ( v19[0] )
    *((_QWORD *)this + 2) = a2;
  v15 = SRCacheContext_AddToCache(v20, L"PkgExtension\\Index\\Name");
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v15,
      *(int *)v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x263,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)v11,
      *(int *)v19);
    v16 = v21;
    v21 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_10;
  }
  v17 = v21;
  v21 = 0;
  if ( v17 )
    SRCache_Free();
  v18 = v20;
  v20 = 0;
  if ( v18 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x18007a4e4  mov     [rsp-8+arg_18], rbx
0x18007a4e9  push    rbp
0x18007a4ea  push    rsi
0x18007a4eb  push    rdi
0x18007a4ec  push    r14
0x18007a4ee  push    r15
0x18007a4f0  lea     rbp, [rsp-160h]
0x18007a4f8  sub     rsp, 260h
0x18007a4ff  mov     rax, cs:__security_cookie
0x18007a506  xor     rax, rsp
0x18007a509  mov     [rbp+180h+var_30], rax
0x18007a510  mov     rbx, rcx
0x18007a513  xor     r15d, r15d
0x18007a516  mov     rcx, [rcx]
0x18007a519  mov     r14, r8
0x18007a51c  mov     rsi, rdx
0x18007a51f  mov     [rbx], r15
0x18007a522  test    rcx, rcx
0x18007a525  jz      short loc_18007A52D
0x18007a527  call    cs:__imp_SRCacheContext_Close
0x18007a52d  lea     r9, [rsp+280h+var_260]; bool *
0x18007a532  mov     [rbx+8], r15d
0x18007a536  lea     r8, aPkgextensionIn; "PkgExtension\\Index\\Name"
0x18007a53d  mov     [rbx+10h], r15
0x18007a541  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18007a544  mov     [rsp+280h+var_258], r15
0x18007a549  lea     rcx, [rsp+280h+var_258]; this
0x18007a54e  mov     [rsp+280h+var_260], r15b; int
0x18007a553  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEB_WAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,wchar_t const *,bool &)
0x18007a558  mov     edi, eax
0x18007a55a  test    eax, eax
0x18007a55c  jns     short loc_18007A595
0x18007a55e  mov     rcx, [rbp+188h]; this
0x18007a565  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a56c  mov     r9d, eax; char *
0x18007a56f  mov     edx, 256h; void *
0x18007a574  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a579  mov     rcx, [rsp+280h+var_258]
0x18007a57e  mov     [rsp+280h+var_258], r15
0x18007a583  test    rcx, rcx
0x18007a586  jz      short loc_18007A58E
0x18007a588  call    cs:__imp_SRCacheContext_Close
0x18007a58e  mov     eax, edi
0x18007a590  jmp     loc_18007A727
0x18007a595  cmp     [rsp+280h+var_260], r15b
0x18007a59a  jnz     short loc_18007A5D8
0x18007a59c  mov     rcx, [rbp+188h]; this
0x18007a5a3  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a5aa  mov     ebx, 80670012h
0x18007a5af  mov     edx, 257h; void *
0x18007a5b4  mov     r9d, ebx; char *
0x18007a5b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a5bc  mov     rcx, [rsp+280h+var_258]
0x18007a5c1  mov     [rsp+280h+var_258], r15
0x18007a5c6  test    rcx, rcx
0x18007a5c9  jz      short loc_18007A5D1
0x18007a5cb  call    cs:__imp_SRCacheContext_Close
0x18007a5d1  mov     eax, ebx
0x18007a5d3  jmp     loc_18007A727
0x18007a5d8  xor     edx, edx; Val
0x18007a5da  mov     [rsp+280h+var_250], r15
0x18007a5df  mov     r8d, 200h; Size
0x18007a5e5  lea     rcx, [rsp+280h+var_248]; void *
0x18007a5ea  call    memset_0
0x18007a5ef  lea     rax, [rsp+280h+var_248]
0x18007a5f4  mov     [rbp+180h+var_48], r15
0x18007a5fb  mov     rdx, r14; wchar_t *
0x18007a5fe  mov     [rbp+180h+var_38], rax
0x18007a605  lea     rcx, [rsp+280h+var_250]; this
0x18007a60a  mov     [rbp+180h+var_40], 100h
0x18007a615  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)
0x18007a61a  mov     edi, eax
0x18007a61c  test    eax, eax
0x18007a61e  jns     short loc_18007A659
0x18007a620  mov     edx, 25Ah; void *
0x18007a625  mov     rcx, [rbp+188h]; this
0x18007a62c  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a633  mov     r9d, edi; char *
0x18007a636  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a63b  mov     rcx, [rsp+280h+var_250]
0x18007a640  mov     [rsp+280h+var_250], r15
0x18007a645  test    rcx, rcx
0x18007a648  jz      loc_18007A579
0x18007a64e  call    cs:__imp_SRCache_Free
0x18007a654  jmp     loc_18007A579
0x18007a659  mov     r8, [rbp+180h+var_38]; wchar_t *
0x18007a660  lea     r9, [rsp+280h+var_260]; bool *
0x18007a665  lea     rdx, [rsp+280h+var_258]; struct StateRepository::Cache::Context_NoThrow *
0x18007a66a  mov     [rsp+280h+var_260], r15b; int
0x18007a66f  mov     rcx, rbx; this
0x18007a672  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEB_WAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,wchar_t const *,bool &)
0x18007a677  mov     edi, eax
0x18007a679  test    eax, eax
0x18007a67b  jns     short loc_18007A684
0x18007a67d  mov     edx, 25Dh
0x18007a682  jmp     short loc_18007A625
0x18007a684  cmp     [rsp+280h+var_260], r15b
0x18007a689  jz      short loc_18007A68F
0x18007a68b  mov     [rbx+10h], rsi
0x18007a68f  mov     rcx, [rsp+280h+var_258]
0x18007a694  lea     rdx, aPkgextensionIn; "PkgExtension\\Index\\Name"
0x18007a69b  call    cs:__imp_SRCacheContext_AddToCache
0x18007a6a1  mov     ebx, eax
0x18007a6a3  test    eax, eax
0x18007a6a5  jns     short loc_18007A6FB
0x18007a6a7  mov     rcx, [rbp+188h]; this
0x18007a6ae  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a6b5  mov     r9d, eax; char *
0x18007a6b8  mov     edx, 1A6h; void *
0x18007a6bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a6c2  mov     rcx, [rbp+188h]; this
0x18007a6c9  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a6d0  mov     r9d, ebx; char *
0x18007a6d3  mov     edx, 263h; void *
0x18007a6d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a6dd  mov     rcx, [rsp+280h+var_250]
0x18007a6e2  mov     [rsp+280h+var_250], r15
0x18007a6e7  test    rcx, rcx
0x18007a6ea  jz      loc_18007A5BC
0x18007a6f0  call    cs:__imp_SRCache_Free
0x18007a6f6  jmp     loc_18007A5BC
0x18007a6fb  mov     rcx, [rsp+280h+var_250]
0x18007a700  mov     [rsp+280h+var_250], r15
0x18007a705  test    rcx, rcx
0x18007a708  jz      short loc_18007A710
0x18007a70a  call    cs:__imp_SRCache_Free
0x18007a710  mov     rcx, [rsp+280h+var_258]
0x18007a715  mov     [rsp+280h+var_258], r15
0x18007a71a  test    rcx, rcx
0x18007a71d  jz      short loc_18007A725
0x18007a71f  call    cs:__imp_SRCacheContext_Close
0x18007a725  xor     eax, eax
0x18007a727  mov     rcx, [rbp+180h+var_30]
0x18007a72e  xor     rcx, rsp; StackCookie
0x18007a731  call    __security_check_cookie
0x18007a736  mov     rbx, [rsp+280h+arg_18]
0x18007a73e  add     rsp, 260h
0x18007a745  pop     r15
0x18007a747  pop     r14
0x18007a749  pop     rdi
0x18007a74a  pop     rsi
0x18007a74b  pop     rbp
0x18007a74c  retn
```
