# StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow::OpenByName(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x180014784`
- end: `0x180014a3a`
- name: `?OpenByName@AppExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `694`
- prototype: `int(StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180012adc`

## callees

- `0x180002980`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x180014784`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800147c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001485b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800148a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014a0c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800147c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001485b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800148a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014a0c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014926`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800149dd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800149f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014926`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800149dd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800149f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180014800`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180014800`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180014954`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180014954`

## string_xrefs

- `0x18001481d`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180014971`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180014838`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`
- `0x18001487b`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`
- `0x180014904`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`
- `0x1800149b6`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`
- `0x1800147e2`: `AppExtension\Index\Name`
- `0x180014998`: `AppExtension\Index\Name`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow::OpenByName(
        StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rcx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  bool v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 *v21; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  char v23; // [rsp+38h] [rbp-C8h]
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+248h] [rbp+148h]
  __int64 v27; // [rsp+250h] [rbp+150h]
  _BYTE *v28; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v4 )
    SRCacheContext_Close(v4);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  v21 = (__int64 *)v20;
  *(_QWORD *)v20 = 0;
  v22 = 0;
  v23 = 1;
  v8 = SRCacheContext_Open(v7, L"AppExtension\\Index\\Name", 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x256,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
LABEL_5:
    v9 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v20 )
  {
    v11 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_10:
    v12 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return v11;
  }
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v26 = 0;
  v28 = v25;
  v27 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, a3, v13);
  if ( v8 < 0 )
  {
    v14 = 602;
    goto LABEL_15;
  }
  v21 = (__int64 *)this;
  v22 = 0;
  v23 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v20, v28, 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v14 = 605;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v15 = v24;
    v24 = 0;
    if ( v15 )
      SRCache_Free(v15);
    goto LABEL_5;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v16 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v20,
          L"AppExtension\\Index\\Name");
  v11 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x263,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)v16,
      v20[0]);
    v17 = v24;
    v24 = 0;
    if ( v17 )
      SRCache_Free(v17);
    goto LABEL_10;
  }
  v18 = v24;
  v24 = 0;
  if ( v18 )
    SRCache_Free(v18);
  v19 = *(_QWORD *)v20;
  *(_QWORD *)v20 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  return 0;
}

```

## disassembly

```asm
0x180014784  mov     [rsp-8+arg_18], rbx
0x180014789  push    rbp
0x18001478a  push    rsi
0x18001478b  push    rdi
0x18001478c  push    r14
0x18001478e  push    r15
0x180014790  lea     rbp, [rsp-170h]
0x180014798  sub     rsp, 270h
0x18001479f  mov     rax, cs:__security_cookie
0x1800147a6  xor     rax, rsp
0x1800147a9  mov     [rbp+190h+var_30], rax
0x1800147b0  mov     rbx, rcx
0x1800147b3  xor     r15d, r15d
0x1800147b6  mov     rcx, [rcx]
0x1800147b9  mov     r14, r8
0x1800147bc  mov     rsi, rdx
0x1800147bf  mov     [rbx], r15
0x1800147c2  test    rcx, rcx
0x1800147c5  jz      short loc_1800147CD
0x1800147c7  call    cs:__imp_SRCacheContext_Close
0x1800147cd  mov     [rbx+8], r15d
0x1800147d1  lea     rax, [rsp+290h+var_270]
0x1800147d6  mov     [rbx+10h], r15
0x1800147da  lea     r9, [rsp+290h+var_260]
0x1800147df  mov     rcx, [rsi]
0x1800147e2  lea     rdx, aAppextensionIn; "AppExtension\\Index\\Name"
0x1800147e9  xor     r8d, r8d
0x1800147ec  mov     [rsp+290h+var_268], rax
0x1800147f1  mov     qword ptr [rsp+290h+var_270], r15; int
0x1800147f6  mov     [rsp+290h+var_260], r15
0x1800147fb  mov     [rsp+290h+var_258], 1
0x180014800  call    cs:__imp_SRCacheContext_Open
0x180014806  lea     rcx, [rsp+290h+var_268]
0x18001480b  mov     edi, eax
0x18001480d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180014812  test    edi, edi
0x180014814  jns     short loc_180014868
0x180014816  mov     rcx, [rbp+198h]; this
0x18001481d  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180014824  mov     r9d, edi; char *
0x180014827  mov     edx, 18Ch; void *
0x18001482c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014831  mov     rcx, [rbp+198h]; this
0x180014838  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x18001483f  mov     r9d, edi; char *
0x180014842  mov     edx, 256h; void *
0x180014847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001484c  mov     rcx, qword ptr [rsp+290h+var_270]
0x180014851  mov     qword ptr [rsp+290h+var_270], r15
0x180014856  test    rcx, rcx
0x180014859  jz      short loc_180014861
0x18001485b  call    cs:__imp_SRCacheContext_Close
0x180014861  mov     eax, edi
0x180014863  jmp     loc_180014A14
0x180014868  cmp     qword ptr [rsp+290h+var_270], r15
0x18001486d  setnz   al
0x180014870  test    al, al
0x180014872  jnz     short loc_1800148B0
0x180014874  mov     rcx, [rbp+198h]; this
0x18001487b  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x180014882  mov     ebx, 80670012h
0x180014887  mov     edx, 257h; void *
0x18001488c  mov     r9d, ebx; char *
0x18001488f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014894  mov     rcx, qword ptr [rsp+290h+var_270]
0x180014899  mov     qword ptr [rsp+290h+var_270], r15
0x18001489e  test    rcx, rcx
0x1800148a1  jz      short loc_1800148A9
0x1800148a3  call    cs:__imp_SRCacheContext_Close
0x1800148a9  mov     eax, ebx
0x1800148ab  jmp     loc_180014A14
0x1800148b0  xor     edx, edx; Val
0x1800148b2  mov     [rsp+290h+var_250], r15
0x1800148b7  mov     r8d, 200h; Size
0x1800148bd  lea     rcx, [rsp+290h+var_248]; void *
0x1800148c2  call    memset_0
0x1800148c7  lea     rax, [rsp+290h+var_248]
0x1800148cc  mov     [rbp+190h+var_48], r15
0x1800148d3  mov     rdx, r14; unsigned __int16 *
0x1800148d6  mov     [rbp+190h+var_38], rax
0x1800148dd  lea     rcx, [rsp+290h+var_250]; this
0x1800148e2  mov     [rbp+190h+var_40], 100h
0x1800148ed  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800148f2  mov     edi, eax
0x1800148f4  test    eax, eax
0x1800148f6  jns     short loc_180014931
0x1800148f8  mov     edx, 25Ah; void *
0x1800148fd  mov     rcx, [rbp+198h]; this
0x180014904  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x18001490b  mov     r9d, edi; char *
0x18001490e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014913  mov     rcx, [rsp+290h+var_250]
0x180014918  mov     [rsp+290h+var_250], r15
0x18001491d  test    rcx, rcx
0x180014920  jz      loc_18001484C
0x180014926  call    cs:__imp_SRCache_Free
0x18001492c  jmp     loc_18001484C
0x180014931  mov     rdx, [rbp+190h+var_38]
0x180014938  lea     r9, [rsp+290h+var_260]
0x18001493d  mov     rcx, qword ptr [rsp+290h+var_270]
0x180014942  xor     r8d, r8d
0x180014945  mov     [rsp+290h+var_268], rbx
0x18001494a  mov     [rsp+290h+var_260], r15
0x18001494f  mov     [rsp+290h+var_258], 1
0x180014954  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001495a  lea     rcx, [rsp+290h+var_268]
0x18001495f  mov     edi, eax
0x180014961  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180014966  test    edi, edi
0x180014968  jns     short loc_18001498F
0x18001496a  mov     rcx, [rbp+198h]; this
0x180014971  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180014978  mov     r9d, edi; char *
0x18001497b  mov     edx, 1B0h; void *
0x180014980  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014985  mov     edx, 25Dh
0x18001498a  jmp     loc_1800148FD
0x18001498f  cmp     [rbx], r15
0x180014992  jz      short loc_180014998
0x180014994  mov     [rbx+10h], rsi
0x180014998  lea     rdx, aAppextensionIn; "AppExtension\\Index\\Name"
0x18001499f  lea     rcx, [rsp+290h+var_270]; this
0x1800149a4  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800149a9  mov     ebx, eax
0x1800149ab  test    eax, eax
0x1800149ad  jns     short loc_1800149E8
0x1800149af  mov     rcx, [rbp+198h]; this
0x1800149b6  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x1800149bd  mov     r9d, eax; char *
0x1800149c0  mov     edx, 263h; void *
0x1800149c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800149ca  mov     rcx, [rsp+290h+var_250]
0x1800149cf  mov     [rsp+290h+var_250], r15
0x1800149d4  test    rcx, rcx
0x1800149d7  jz      loc_180014894
0x1800149dd  call    cs:__imp_SRCache_Free
0x1800149e3  jmp     loc_180014894
0x1800149e8  mov     rcx, [rsp+290h+var_250]
0x1800149ed  mov     [rsp+290h+var_250], r15
0x1800149f2  test    rcx, rcx
0x1800149f5  jz      short loc_1800149FD
0x1800149f7  call    cs:__imp_SRCache_Free
0x1800149fd  mov     rcx, qword ptr [rsp+290h+var_270]
0x180014a02  mov     qword ptr [rsp+290h+var_270], r15
0x180014a07  test    rcx, rcx
0x180014a0a  jz      short loc_180014A12
0x180014a0c  call    cs:__imp_SRCacheContext_Close
0x180014a12  xor     eax, eax
0x180014a14  mov     rcx, [rbp+190h+var_30]
0x180014a1b  xor     rcx, rsp; StackCookie
0x180014a1e  call    __security_check_cookie
0x180014a23  mov     rbx, [rsp+290h+arg_18]
0x180014a2b  add     rsp, 270h
0x180014a32  pop     r15
0x180014a34  pop     r14
0x180014a36  pop     rdi
0x180014a37  pop     rsi
0x180014a38  pop     rbp
0x180014a39  retn
```
