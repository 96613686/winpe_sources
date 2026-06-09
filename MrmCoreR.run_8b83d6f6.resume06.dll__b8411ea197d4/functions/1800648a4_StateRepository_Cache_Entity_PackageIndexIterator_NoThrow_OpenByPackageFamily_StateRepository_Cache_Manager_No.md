# StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x1800648a4`
- end: `0x180064bdf`
- name: `?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `827`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180062a00`

## callees

- `0x18001a140`
- `0x18002c8d0`
- `0x1800648a4`
- `0x180064be8`
- `0x18006f374`
- `0x1800862f0`
- `0x180086e44`
- `0x180086f7c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180064ac1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180064b82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180064b9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180064ac1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180064b82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180064b9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064913`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800649b1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800649fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064bb1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064913`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800649b1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800649fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064bb1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180064954`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180064954`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180064af7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180064af7`

## string_xrefs

- `0x180064a61`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800648e8`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18006498e`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800649d1`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180064a9f`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180064b5b`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180064973`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180064b16`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
        StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+238h] [rbp+138h]
  __int64 v26; // [rsp+240h] [rbp+140h]
  _BYTE *v27; // [rsp+248h] [rbp+148h]
  unsigned __int16 v28[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v29; // [rsp+258h] [rbp+158h] BYREF
  char v30; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x792,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)0x80070057LL,
      v22[0]);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8, a2);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v9 = *(_QWORD *)a2;
  *(_QWORD *)v28 = v22;
  *(_QWORD *)v22 = 0;
  v29 = 0;
  v30 = 1;
  v10 = SRCacheContext_Open(v9, L"Package\\Index\\PackageFamily", 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v28);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x798,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
LABEL_8:
    v12 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v11);
    return (unsigned int)v10;
  }
  if ( !*(_QWORD *)v22 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x799,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_13:
    v14 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v14 )
      SRCacheContext_Close(v14, v13);
    return v6;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v26 = 256;
  v27 = v24;
  if ( (unsigned int)o__ui64tow_s_0(a3, v28, 17) )
  {
    v10 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v22[0]);
LABEL_18:
    v15 = 1948;
    goto LABEL_19;
  }
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, v28);
  if ( v10 < 0 )
    goto LABEL_18;
  *(_QWORD *)v28 = this;
  v29 = 0;
  v30 = 1;
  v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v22, v27, 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v28);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    v15 = 1951;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_8;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v17 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v22,
          L"Package\\Index\\PackageFamily");
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v17,
      v22[0]);
    v19 = v23;
    v23 = 0;
    if ( v19 )
      SRCache_Free();
    goto LABEL_13;
  }
  v20 = v23;
  v23 = 0;
  if ( v20 )
    SRCache_Free();
  v21 = *(_QWORD *)v22;
  *(_QWORD *)v22 = 0;
  if ( v21 )
    SRCacheContext_Close(v21, v18);
  return 0;
}

```

## disassembly

```asm
0x1800648a4  mov     [rsp-8+arg_18], rbx
0x1800648a9  push    rbp
0x1800648aa  push    rsi
0x1800648ab  push    rdi
0x1800648ac  push    r14
0x1800648ae  push    r15
0x1800648b0  lea     rbp, [rsp-180h]
0x1800648b8  sub     rsp, 280h
0x1800648bf  mov     rax, cs:__security_cookie
0x1800648c6  xor     rax, rsp
0x1800648c9  mov     [rbp+1A0h+var_28], rax
0x1800648d0  xor     r15d, r15d
0x1800648d3  mov     r14, r8
0x1800648d6  mov     rsi, rdx
0x1800648d9  mov     rbx, rcx
0x1800648dc  test    r8, r8
0x1800648df  jnz     short loc_180064908
0x1800648e1  mov     rcx, [rbp+1A8h]; this
0x1800648e8  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800648ef  mov     ebx, 80070057h
0x1800648f4  mov     edx, 792h; void *
0x1800648f9  mov     r9d, ebx; char *
0x1800648fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064901  mov     eax, ebx
0x180064903  jmp     loc_180064BB9
0x180064908  mov     rcx, [rcx]
0x18006490b  mov     [rbx], r15
0x18006490e  test    rcx, rcx
0x180064911  jz      short loc_180064919
0x180064913  call    cs:__imp_SRCacheContext_Close
0x180064919  mov     [rbx+8], r15d
0x18006491d  lea     rax, [rsp+2A0h+var_280]
0x180064922  mov     [rbx+10h], r15
0x180064926  lea     r9, [rbp+1A0h+var_48]
0x18006492d  mov     rcx, [rsi]
0x180064930  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x180064937  xor     r8d, r8d
0x18006493a  mov     qword ptr [rbp+1A0h+var_50], rax
0x180064941  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x180064946  mov     [rbp+1A0h+var_48], r15
0x18006494d  mov     [rbp+1A0h+var_40], 1
0x180064954  call    cs:__imp_SRCacheContext_Open
0x18006495a  lea     rcx, [rbp+1A0h+var_50]
0x180064961  mov     edi, eax
0x180064963  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180064968  test    edi, edi
0x18006496a  jns     short loc_1800649BE
0x18006496c  mov     rcx, [rbp+1A8h]; this
0x180064973  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18006497a  mov     r9d, edi; char *
0x18006497d  mov     edx, 18Ch; void *
0x180064982  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064987  mov     rcx, [rbp+1A8h]; this
0x18006498e  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064995  mov     r9d, edi; char *
0x180064998  mov     edx, 798h; void *
0x18006499d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800649a2  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800649a7  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800649ac  test    rcx, rcx
0x1800649af  jz      short loc_1800649B7
0x1800649b1  call    cs:__imp_SRCacheContext_Close
0x1800649b7  mov     eax, edi
0x1800649b9  jmp     loc_180064BB9
0x1800649be  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1800649c3  setnz   al
0x1800649c6  test    al, al
0x1800649c8  jnz     short loc_180064A08
0x1800649ca  mov     rcx, [rbp+1A8h]; this
0x1800649d1  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800649d8  mov     ebx, 80670012h
0x1800649dd  mov     edx, 799h; void *
0x1800649e2  mov     r9d, ebx; char *
0x1800649e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800649ea  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800649ef  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800649f4  test    rcx, rcx
0x1800649f7  jz      loc_180064901
0x1800649fd  call    cs:__imp_SRCacheContext_Close
0x180064a03  jmp     loc_180064901
0x180064a08  xor     edx, edx; Val
0x180064a0a  mov     [rsp+2A0h+var_270], r15
0x180064a0f  mov     r8d, 200h; Size
0x180064a15  lea     rcx, [rsp+2A0h+var_268]; void *
0x180064a1a  call    memset_0
0x180064a1f  mov     r9d, 10h
0x180064a25  mov     [rbp+1A0h+var_68], r15
0x180064a2c  lea     rax, [rsp+2A0h+var_268]
0x180064a31  mov     [rbp+1A0h+var_60], 100h
0x180064a3c  lea     rdx, [rbp+1A0h+var_50]
0x180064a43  mov     [rbp+1A0h+var_58], rax
0x180064a4a  mov     rcx, r14
0x180064a4d  lea     r8d, [r9+1]
0x180064a51  call    _o__ui64tow_s_0
0x180064a56  test    eax, eax
0x180064a58  jz      short loc_180064A7C
0x180064a5a  mov     rcx, [rbp+1A8h]; this
0x180064a61  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064a68  mov     edi, 8000FFFFh
0x180064a6d  mov     edx, 166h; void *
0x180064a72  mov     r9d, edi; char *
0x180064a75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064a7a  jmp     short loc_180064A93
0x180064a7c  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x180064a83  lea     rcx, [rsp+2A0h+var_270]; this
0x180064a88  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180064a8d  mov     edi, eax
0x180064a8f  test    eax, eax
0x180064a91  jns     short loc_180064ACC
0x180064a93  mov     edx, 79Ch; void *
0x180064a98  mov     rcx, [rbp+1A8h]; this
0x180064a9f  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064aa6  mov     r9d, edi; char *
0x180064aa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064aae  mov     rcx, [rsp+2A0h+var_270]
0x180064ab3  mov     [rsp+2A0h+var_270], r15
0x180064ab8  test    rcx, rcx
0x180064abb  jz      loc_1800649A2
0x180064ac1  call    cs:__imp_SRCache_Free
0x180064ac7  jmp     loc_1800649A2
0x180064acc  mov     rdx, [rbp+1A0h+var_58]
0x180064ad3  lea     r9, [rbp+1A0h+var_48]
0x180064ada  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180064adf  xor     r8d, r8d
0x180064ae2  mov     qword ptr [rbp+1A0h+var_50], rbx
0x180064ae9  mov     [rbp+1A0h+var_48], r15
0x180064af0  mov     [rbp+1A0h+var_40], 1
0x180064af7  call    cs:__imp_SRCacheContext_OpenSubContext
0x180064afd  lea     rcx, [rbp+1A0h+var_50]
0x180064b04  mov     edi, eax
0x180064b06  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180064b0b  test    edi, edi
0x180064b0d  jns     short loc_180064B34
0x180064b0f  mov     rcx, [rbp+1A8h]; this
0x180064b16  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064b1d  mov     r9d, edi; char *
0x180064b20  mov     edx, 1B0h; void *
0x180064b25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064b2a  mov     edx, 79Fh
0x180064b2f  jmp     loc_180064A98
0x180064b34  cmp     [rbx], r15
0x180064b37  jz      short loc_180064B3D
0x180064b39  mov     [rbx+10h], rsi
0x180064b3d  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x180064b44  lea     rcx, [rsp+2A0h+var_280]; this
0x180064b49  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180064b4e  mov     ebx, eax
0x180064b50  test    eax, eax
0x180064b52  jns     short loc_180064B8D
0x180064b54  mov     rcx, [rbp+1A8h]; this
0x180064b5b  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064b62  mov     r9d, eax; char *
0x180064b65  mov     edx, 7A5h; void *
0x180064b6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064b6f  mov     rcx, [rsp+2A0h+var_270]
0x180064b74  mov     [rsp+2A0h+var_270], r15
0x180064b79  test    rcx, rcx
0x180064b7c  jz      loc_1800649EA
0x180064b82  call    cs:__imp_SRCache_Free
0x180064b88  jmp     loc_1800649EA
0x180064b8d  mov     rcx, [rsp+2A0h+var_270]
0x180064b92  mov     [rsp+2A0h+var_270], r15
0x180064b97  test    rcx, rcx
0x180064b9a  jz      short loc_180064BA2
0x180064b9c  call    cs:__imp_SRCache_Free
0x180064ba2  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180064ba7  mov     qword ptr [rsp+2A0h+var_280], r15
0x180064bac  test    rcx, rcx
0x180064baf  jz      short loc_180064BB7
0x180064bb1  call    cs:__imp_SRCacheContext_Close
0x180064bb7  xor     eax, eax
0x180064bb9  mov     rcx, [rbp+1A0h+var_28]
0x180064bc0  xor     rcx, rsp; StackCookie
0x180064bc3  call    __security_check_cookie
0x180064bc8  mov     rbx, [rsp+2A0h+arg_18]
0x180064bd0  add     rsp, 280h
0x180064bd7  pop     r15
0x180064bd9  pop     r14
0x180064bdb  pop     rdi
0x180064bdc  pop     rsi
0x180064bdd  pop     rbp
0x180064bde  retn
```
