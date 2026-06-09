# StateRepository::Cache::Entity::Application_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)

- ea: `0x180008590`
- end: `0x180008b1a`
- name: `?Get@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `1418`
- prototype: `static int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, enum StateRepository::Cache::Entity::Application_NoThrow::CacheFlags, struct StateRepository::Cache::Entity::Application_NoThrow *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180005880`
- `0x18002e95c`

## callees

- `0x180005520`
- `0x180007c78`
- `0x180008590`
- `0x180008b20`
- `0x180017fb8`
- `0x180018170`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x180008738`
- `msvcrt!_ui64tow_s` at `0x180008738`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800089c9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008a3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800089c9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008a3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180008631`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180008631`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000865b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008926`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800089e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008a1a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008a55`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008abb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008ada`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000865b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008926`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800089e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008a1a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008a55`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008abb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008ada`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800088fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800088fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180008970`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180008970`

## string_xrefs

- `0x18000867a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000893d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000898d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000874f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800087a1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800087e7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180008858`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800085d7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008695`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800086c1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800089ad`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800089f7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008a98`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::Get(
        __int64 *a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        bool *a5)
{
  __int64 v9; // rcx
  __int64 v10; // rsi
  HRESULT v11; // edi
  __int64 v12; // rcx
  __int64 v13; // rcx
  bool v14; // r8
  __int64 v15; // rbx
  wchar_t *i; // rax
  int v17; // eax
  size_t v18; // r9
  STRSAFE_LPCWSTR v19; // rsi
  size_t *v20; // r8
  __int64 v21; // r11
  wchar_t *v22; // rdx
  wchar_t *v23; // rcx
  __int64 v24; // r8
  wchar_t v25; // ax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  int v36; // eax
  unsigned int v37; // ebx
  __int64 v38; // rcx
  __int64 v39; // rcx
  size_t v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  __int64 v43; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v44; // [rsp+38h] [rbp-C8h] BYREF
  size_t pcchDestLength; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v46; // [rsp+48h] [rbp-B8h]
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  char v48; // [rsp+58h] [rbp-A8h]
  __int64 *v49; // [rsp+60h] [rbp-A0h]
  __int64 v50; // [rsp+68h] [rbp-98h] BYREF
  char v51; // [rsp+70h] [rbp-90h]
  __int64 v52; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v53[512]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v54; // [rsp+288h] [rbp+188h]
  size_t cchDest; // [rsp+290h] [rbp+190h]
  STRSAFE_LPCWSTR pszDest; // [rsp+298h] [rbp+198h]
  wchar_t Buffer[20]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      v40);
    return 2147942487LL;
  }
  v9 = *a1;
  v10 = 0;
  v46 = &v43;
  v44 = 0;
  v43 = 0;
  v47 = 0;
  v48 = 1;
  v11 = SRCacheContext_Open(v9, L"Application\\Data", 0, &v47);
  if ( v48 )
  {
    v12 = *v46;
    *v46 = v47;
    if ( v12 )
      SRCacheContext_Close();
  }
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v11,
      v40);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B1,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v11,
      v41);
    goto LABEL_46;
  }
  if ( !v43 )
  {
    v11 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80670012LL,
      v40);
    v13 = v43;
    v43 = 0;
    if ( !v13 )
      goto LABEL_48;
    goto LABEL_47;
  }
  v52 = 0;
  memset_0(v53, 0, sizeof(v53));
  v54 = 0;
  cchDest = 256;
  pszDest = (STRSAFE_LPCWSTR)v53;
  if ( _ui64tow_s(a2, Buffer, 0x11u, 16) )
  {
    v11 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v40);
LABEL_36:
    v26 = 437;
    goto LABEL_44;
  }
  v15 = 0;
  for ( i = Buffer; *i; ++i )
  {
    if ( (unsigned __int64)++v15 >= 0x7FFFFFFF )
    {
      v11 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x80070057LL,
        v40);
      goto LABEL_35;
    }
    if ( *i == 94 )
      ++v10;
  }
  v17 = StateRepository::Cache::Key_NoThrow::EnsureCapacity(
          (StateRepository::Cache::Key_NoThrow *)&v52,
          v10 + v15 + v54 + 1,
          v14);
  v11 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)(unsigned int)v17,
      v40);
    goto LABEL_35;
  }
  if ( v10 )
  {
    v22 = (wchar_t *)&pszDest[v54];
    v23 = Buffer;
    if ( v15 )
    {
      v24 = v15;
      do
      {
        if ( *v23 == 94 )
          *v22++ = 94;
        v25 = *v23++;
        *v22++ = v25;
        --v24;
      }
      while ( v24 );
    }
    *v22 = 0;
  }
  else
  {
    pcchDestLength = 0;
    v19 = pszDest;
    v11 = StringValidateDestAndLengthW(pszDest, cchDest, &pcchDestLength, v18);
    if ( v11 >= 0 )
      v11 = StringCopyWorkerW((STRSAFE_LPWSTR)&v19[pcchDestLength], v21 - pcchDestLength, v20, Buffer, v40);
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)(unsigned int)v11,
        v40);
      goto LABEL_35;
    }
  }
  v54 += v15;
  v11 = 0;
LABEL_35:
  if ( v11 < 0 )
    goto LABEL_36;
  v49 = &v44;
  v50 = 0;
  v51 = 1;
  v11 = SRCacheContext_OpenSubContext(v43, pszDest, 0, &v50);
  if ( v51 )
  {
    v27 = *v49;
    *v49 = v50;
    if ( v27 )
      SRCacheContext_Close();
  }
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v11,
      v40);
    v26 = 438;
    goto LABEL_44;
  }
  v28 = v43;
  *a5 = v44 != 0;
  v29 = SRCacheContext_AddToCache(v28, L"Application\\Data");
  v11 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v29,
      v40);
    v26 = 440;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v11,
      v40);
    v30 = v52;
    v52 = 0;
    if ( v30 )
      SRCache_Free();
LABEL_46:
    v31 = v43;
    v43 = 0;
    if ( !v31 )
    {
LABEL_48:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x156,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
        (const char *)(unsigned int)v11,
        v42);
      v32 = v44;
      v44 = 0;
      if ( v32 )
        SRCacheContext_Close();
      return (unsigned int)v11;
    }
LABEL_47:
    SRCacheContext_Close();
    goto LABEL_48;
  }
  v33 = v52;
  v52 = 0;
  if ( v33 )
    SRCache_Free();
  v34 = v43;
  v43 = 0;
  if ( v34 )
    SRCacheContext_Close();
  if ( !*a5 )
  {
    v35 = v44;
    v44 = 0;
    if ( !v35 )
      return 0;
    goto LABEL_63;
  }
  v36 = StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(&v44, a4, a3, a2);
  v37 = v36;
  if ( v36 >= 0 )
  {
    v39 = v44;
    v44 = 0;
    if ( !v39 )
      return 0;
LABEL_63:
    SRCacheContext_Close();
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x15B,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
    (const char *)(unsigned int)v36,
    v40);
  v38 = v44;
  v44 = 0;
  if ( v38 )
    SRCacheContext_Close();
  return v37;
}

```

## disassembly

```asm
0x180008590  push    rbp
0x180008592  push    rdi
0x180008593  push    r12
0x180008595  push    r13
0x180008597  push    r14
0x180008599  push    r15
0x18000859b  lea     rbp, [rsp-1D8h]
0x1800085a3  sub     rsp, 2D8h
0x1800085aa  mov     rax, cs:__security_cookie
0x1800085b1  xor     rax, rsp
0x1800085b4  mov     [rbp+200h+var_38], rax
0x1800085bb  mov     r14, [rbp+200h+arg_20]
0x1800085c2  mov     r13, r9
0x1800085c5  mov     r12, r8
0x1800085c8  mov     r15, rdx
0x1800085cb  test    rdx, rdx
0x1800085ce  jnz     short loc_1800085F7
0x1800085d0  mov     rcx, [rbp+208h]; this
0x1800085d7  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800085de  mov     edi, 80070057h
0x1800085e3  mov     edx, 153h; void *
0x1800085e8  mov     r9d, edi; char *
0x1800085eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800085f0  mov     eax, edi
0x1800085f2  jmp     loc_180008AF8
0x1800085f7  mov     rcx, [rcx]
0x1800085fa  lea     rax, [rsp+300h+var_2D0]
0x1800085ff  mov     [rsp+300h+var_30], rsi
0x180008607  lea     r9, [rsp+300h+var_2B0]
0x18000860c  xor     esi, esi
0x18000860e  mov     [rsp+300h+var_2B8], rax
0x180008613  xor     r8d, r8d
0x180008616  mov     [rsp+300h+var_2C8], rsi
0x18000861b  lea     rdx, aApplicationDat; "Application\\Data"
0x180008622  mov     [rsp+300h+var_2D0], rsi
0x180008627  mov     [rsp+300h+var_2B0], rsi
0x18000862c  mov     [rsp+300h+var_2A8], 1
0x180008631  call    cs:__imp_SRCacheContext_Open
0x180008638  nop     dword ptr [rax+rax+00h]
0x18000863d  mov     edi, eax
0x18000863f  cmp     [rsp+300h+var_2A8], sil
0x180008644  jz      short loc_180008667
0x180008646  mov     rdx, [rsp+300h+var_2B8]
0x18000864b  mov     rax, [rsp+300h+var_2B0]
0x180008650  mov     rcx, [rdx]
0x180008653  mov     [rdx], rax
0x180008656  test    rcx, rcx
0x180008659  jz      short loc_180008667
0x18000865b  call    cs:__imp_SRCacheContext_Close
0x180008662  nop     dword ptr [rax+rax+00h]
0x180008667  mov     [rsp+300h+arg_10], rbx
0x18000866f  test    edi, edi
0x180008671  jns     short loc_1800086AE
0x180008673  mov     rcx, [rbp+208h]; this
0x18000867a  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008681  mov     r9d, edi; char *
0x180008684  mov     edx, 18Ch; void *
0x180008689  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000868e  mov     rcx, [rbp+208h]; this
0x180008695  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000869c  mov     r9d, edi; char *
0x18000869f  mov     edx, 1B1h; void *
0x1800086a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086a9  jmp     loc_1800089D5
0x1800086ae  cmp     [rsp+300h+var_2D0], rsi
0x1800086b3  setnz   al
0x1800086b6  test    al, al
0x1800086b8  jnz     short loc_1800086F2
0x1800086ba  mov     rcx, [rbp+208h]; this
0x1800086c1  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800086c8  mov     edi, 80670012h
0x1800086cd  mov     edx, 1B2h; void *
0x1800086d2  mov     r9d, edi; char *
0x1800086d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086da  mov     rcx, [rsp+300h+var_2D0]
0x1800086df  mov     [rsp+300h+var_2D0], rsi
0x1800086e4  test    rcx, rcx
0x1800086e7  jnz     loc_1800089E4
0x1800086ed  jmp     loc_1800089F0
0x1800086f2  xor     edx, edx; Val
0x1800086f4  mov     [rbp+200h+var_280], rsi
0x1800086f8  mov     r8d, 200h; Size
0x1800086fe  lea     rcx, [rbp+200h+var_278]; void *
0x180008702  call    memset_0
0x180008707  mov     r9d, 10h; Radix
0x18000870d  mov     [rbp+200h+var_78], rsi
0x180008714  lea     rax, [rbp+200h+var_278]
0x180008718  mov     [rbp+200h+cchDest], 100h
0x180008723  lea     rdx, [rbp+200h+Buffer]; Buffer
0x18000872a  mov     [rbp+200h+pszDest], rax
0x180008731  mov     rcx, r15; Value
0x180008734  lea     r8d, [r9+1]; BufferCount
0x180008738  call    cs:__imp__ui64tow_s
0x18000873f  nop     dword ptr [rax+rax+00h]
0x180008744  test    eax, eax
0x180008746  jz      short loc_18000876D
0x180008748  mov     rcx, [rbp+208h]; this
0x18000874f  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008756  mov     edi, 8000FFFFh
0x18000875b  mov     edx, 166h; void *
0x180008760  mov     r9d, edi; char *
0x180008763  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008768  jmp     loc_1800088CA
0x18000876d  mov     rbx, rsi
0x180008770  lea     rax, [rbp+200h+Buffer]
0x180008777  movzx   ecx, word ptr [rax]
0x18000877a  test    cx, cx
0x18000877d  jz      short loc_1800087C1
0x18000877f  inc     rbx
0x180008782  cmp     rbx, 7FFFFFFFh
0x180008789  jnb     short loc_18000879A
0x18000878b  cmp     cx, 5Eh ; '^'
0x18000878f  jnz     short loc_180008794
0x180008791  inc     rsi
0x180008794  add     rax, 2
0x180008798  jmp     short loc_180008777
0x18000879a  mov     rcx, [rbp+208h]; this
0x1800087a1  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800087a8  mov     edi, 80070057h
0x1800087ad  mov     edx, 135h; void *
0x1800087b2  mov     r9d, edi; char *
0x1800087b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087ba  xor     esi, esi
0x1800087bc  jmp     loc_1800088C6
0x1800087c1  mov     rdx, [rbp+200h+var_78]
0x1800087c8  lea     rcx, [rbp+200h+var_280]; this
0x1800087cc  inc     rdx
0x1800087cf  add     rdx, rbx
0x1800087d2  add     rdx, rsi; unsigned __int64
0x1800087d5  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x1800087da  mov     edi, eax
0x1800087dc  test    eax, eax
0x1800087de  jns     short loc_180008802
0x1800087e0  mov     rcx, [rbp+208h]; this
0x1800087e7  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800087ee  mov     r9d, eax; char *
0x1800087f1  mov     edx, 136h; void *
0x1800087f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087fb  xor     esi, esi
0x1800087fd  jmp     loc_1800088C6
0x180008802  test    rsi, rsi
0x180008805  jnz     short loc_180008874
0x180008807  mov     r11, [rbp+200h+cchDest]
0x18000880e  lea     r8, [rsp+300h+pcchDestLength]; pcchDestLength
0x180008813  mov     [rsp+300h+pcchDestLength], rsi
0x180008818  mov     rdx, r11; cchDest
0x18000881b  mov     rsi, [rbp+200h+pszDest]
0x180008822  mov     rcx, rsi; pszDest
0x180008825  call    StringValidateDestAndLengthW
0x18000882a  mov     edi, eax
0x18000882c  test    eax, eax
0x18000882e  js      short loc_18000884D
0x180008830  mov     rax, [rsp+300h+pcchDestLength]
0x180008835  lea     r9, [rbp+200h+Buffer]; pszSrc
0x18000883c  sub     r11, rax
0x18000883f  mov     rdx, r11; cchDest
0x180008842  lea     rcx, [rsi+rax*2]; pszDest
0x180008846  call    StringCopyWorkerW
0x18000884b  mov     edi, eax
0x18000884d  test    edi, edi
0x18000884f  jns     short loc_180008870
0x180008851  mov     rcx, [rbp+208h]; this
0x180008858  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000885f  mov     r9d, edi; char *
0x180008862  mov     edx, 139h; void *
0x180008867  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000886c  xor     esi, esi
0x18000886e  jmp     short loc_1800088C6
0x180008870  xor     esi, esi
0x180008872  jmp     short loc_1800088BD
0x180008874  mov     rcx, [rbp+200h+var_78]
0x18000887b  mov     rax, [rbp+200h+pszDest]
0x180008882  lea     rdx, [rax+rcx*2]
0x180008886  lea     rcx, [rbp+200h+Buffer]
0x18000888d  test    rbx, rbx
0x180008890  jz      short loc_1800088B8
0x180008892  mov     r8, rbx
0x180008895  cmp     word ptr [rcx], 5Eh ; '^'
0x180008899  jnz     short loc_1800088A4
0x18000889b  mov     word ptr [rdx], 5Eh ; '^'
0x1800088a0  add     rdx, 2
0x1800088a4  movzx   eax, word ptr [rcx]
0x1800088a7  add     rcx, 2
0x1800088ab  mov     [rdx], ax
0x1800088ae  add     rdx, 2
0x1800088b2  sub     r8, 1
0x1800088b6  jnz     short loc_180008895
0x1800088b8  xor     esi, esi
0x1800088ba  mov     [rdx], si
0x1800088bd  add     [rbp+200h+var_78], rbx
0x1800088c4  mov     edi, esi
0x1800088c6  test    edi, edi
0x1800088c8  jns     short loc_1800088D4
0x1800088ca  mov     edx, 1B5h
0x1800088cf  jmp     loc_1800089A6
0x1800088d4  mov     rdx, [rbp+200h+pszDest]
0x1800088db  lea     rax, [rsp+300h+var_2C8]
0x1800088e0  mov     rcx, [rsp+300h+var_2D0]
0x1800088e5  lea     r9, [rsp+300h+var_298]
0x1800088ea  xor     r8d, r8d
0x1800088ed  mov     [rsp+300h+var_2A0], rax
0x1800088f2  mov     [rsp+300h+var_298], rsi
0x1800088f7  mov     [rsp+300h+var_290], 1
0x1800088fc  call    cs:__imp_SRCacheContext_OpenSubContext
0x180008903  nop     dword ptr [rax+rax+00h]
0x180008908  cmp     [rsp+300h+var_290], 0
0x18000890d  mov     edi, eax
0x18000890f  jz      short loc_180008932
0x180008911  mov     rdx, [rsp+300h+var_2A0]
0x180008916  mov     rax, [rsp+300h+var_298]
0x18000891b  mov     rcx, [rdx]
0x18000891e  mov     [rdx], rax
0x180008921  test    rcx, rcx
0x180008924  jz      short loc_180008932
0x180008926  call    cs:__imp_SRCacheContext_Close
0x18000892d  nop     dword ptr [rax+rax+00h]
0x180008932  test    edi, edi
0x180008934  jns     short loc_180008958
0x180008936  mov     rcx, [rbp+208h]; this
0x18000893d  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008944  mov     r9d, edi; char *
0x180008947  mov     edx, 1B0h; void *
0x18000894c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008951  mov     edx, 1B6h
0x180008956  jmp     short loc_1800089A6
0x180008958  cmp     [rsp+300h+var_2C8], 0
0x18000895e  lea     rdx, aApplicationDat; "Application\\Data"
0x180008965  mov     rcx, [rsp+300h+var_2D0]
0x18000896a  setnz   al
0x18000896d  mov     [r14], al
0x180008970  call    cs:__imp_SRCacheContext_AddToCache
0x180008977  nop     dword ptr [rax+rax+00h]
0x18000897c  mov     edi, eax
0x18000897e  test    eax, eax
0x180008980  jns     loc_180008A2D
0x180008986  mov     rcx, [rbp+208h]; this
0x18000898d  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008994  mov     r9d, eax; char *
0x180008997  mov     edx, 1A6h; void *
0x18000899c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089a1  mov     edx, 1B8h; void *
0x1800089a6  mov     rcx, [rbp+208h]; this
0x1800089ad  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800089b4  mov     r9d, edi; char *
0x1800089b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089bc  mov     rcx, [rbp+200h+var_280]
0x1800089c0  mov     [rbp+200h+var_280], rsi
0x1800089c4  test    rcx, rcx
0x1800089c7  jz      short loc_1800089D5
0x1800089c9  call    cs:__imp_SRCache_Free
0x1800089d0  nop     dword ptr [rax+rax+00h]
0x1800089d5  mov     rcx, [rsp+300h+var_2D0]
0x1800089da  mov     [rsp+300h+var_2D0], rsi
0x1800089df  test    rcx, rcx
0x1800089e2  jz      short loc_1800089F0
0x1800089e4  call    cs:__imp_SRCacheContext_Close
0x1800089eb  nop     dword ptr [rax+rax+00h]
0x1800089f0  mov     rcx, [rbp+208h]; this
0x1800089f7  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800089fe  mov     r9d, edi; char *
0x180008a01  mov     edx, 156h; void *
0x180008a06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a0b  mov     rcx, [rsp+300h+var_2C8]
0x180008a10  mov     [rsp+300h+var_2C8], rsi
0x180008a15  test    rcx, rcx
0x180008a18  jz      short loc_180008A26
0x180008a1a  call    cs:__imp_SRCacheContext_Close
0x180008a21  nop     dword ptr [rax+rax+00h]
0x180008a26  mov     eax, edi
0x180008a28  jmp     loc_180008AE8
0x180008a2d  mov     rcx, [rbp+200h+var_280]
0x180008a31  mov     [rbp+200h+var_280], rsi
0x180008a35  test    rcx, rcx
0x180008a38  jz      short loc_180008A46
0x180008a3a  call    cs:__imp_SRCache_Free
0x180008a41  nop     dword ptr [rax+rax+00h]
0x180008a46  mov     rcx, [rsp+300h+var_2D0]
0x180008a4b  mov     [rsp+300h+var_2D0], rsi
0x180008a50  test    rcx, rcx
0x180008a53  jz      short loc_180008A61
0x180008a55  call    cs:__imp_SRCacheContext_Close
0x180008a5c  nop     dword ptr [rax+rax+00h]
0x180008a61  cmp     byte ptr [r14], 0
0x180008a65  jnz     short loc_180008A78
0x180008a67  mov     rcx, [rsp+300h+var_2C8]
0x180008a6c  mov     [rsp+300h+var_2C8], rsi
0x180008a71  test    rcx, rcx
0x180008a74  jnz     short loc_180008ADA
0x180008a76  jmp     short loc_180008AE6
0x180008a78  mov     r9, r15
0x180008a7b  lea     rcx, [rsp+300h+var_2C8]
0x180008a80  mov     r8, r12
0x180008a83  mov     rdx, r13
0x180008a86  call    ?ContextToObject@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,__int64)
0x180008a8b  mov     ebx, eax
0x180008a8d  test    eax, eax
0x180008a8f  jns     short loc_180008ACB
0x180008a91  mov     rcx, [rbp+208h]; this
0x180008a98  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008a9f  mov     r9d, eax; char *
  ... truncated ...
```
