# StateRepository::Cache::Entity::PkgExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180112298`
- end: `0x1801124d5`
- name: `?Open@PkgExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180272b6c`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x180112298`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18011241f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18011241f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180112356`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801124a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180112356`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801124a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801123f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180112492`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801123f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180112492`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801122fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801122fb`

## string_xrefs

- `0x180112318`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18011243c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1801122e7`: `PkgExtension\Data`
- `0x18011245d`: `PkgExtension\Data`
- `0x180112338`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PkgExtension.hpp`
- `0x1801123cf`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PkgExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PkgExtension_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  char v19; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+248h] [rbp+148h]
  __int64 v23; // [rsp+250h] [rbp+150h]
  _BYTE *v24; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v17 = v16;
  v19 = 1;
  *(_QWORD *)v16 = 0;
  v18 = 0;
  v8 = SRCacheContext_Open(v4, L"PkgExtension\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 311;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
LABEL_4:
    v10 = *(_QWORD *)v16;
    *(_QWORD *)v16 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v16 )
  {
    v8 = -2140733422;
    v9 = 312;
    goto LABEL_3;
  }
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v22 = 0;
  v24 = v21;
  v23 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v20, a2);
  if ( v8 < 0 )
  {
    v12 = 315;
    goto LABEL_11;
  }
  v17 = (int *)a3;
  v18 = 0;
  v19 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v16, v24, 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v12 = 316;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"PkgExtension\\Data");
  if ( v8 < 0 )
  {
    v12 = 318;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v20;
    v20 = 0;
    if ( v13 )
      SRCache_Free(v13);
    goto LABEL_4;
  }
  v14 = v20;
  v20 = 0;
  if ( v14 )
    SRCache_Free(v14);
  v15 = *(_QWORD *)v16;
  *(_QWORD *)v16 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x180112298  mov     [rsp-8+arg_10], rbx
0x18011229d  push    rbp
0x18011229e  push    rsi
0x18011229f  push    rdi
0x1801122a0  push    r14
0x1801122a2  push    r15
0x1801122a4  lea     rbp, [rsp-170h]
0x1801122ac  sub     rsp, 270h
0x1801122b3  mov     rax, cs:__security_cookie
0x1801122ba  xor     rax, rsp
0x1801122bd  mov     [rbp+190h+var_30], rax
0x1801122c4  mov     rcx, [rcx]
0x1801122c7  lea     rax, [rsp+290h+var_270]
0x1801122cc  mov     rsi, r9
0x1801122cf  mov     [rsp+290h+var_268], rax
0x1801122d4  mov     rdi, r8
0x1801122d7  mov     [rsp+290h+var_258], 1
0x1801122dc  mov     r14, rdx
0x1801122df  lea     r9, [rsp+290h+var_260]
0x1801122e4  xor     r15d, r15d
0x1801122e7  lea     rdx, aPkgextensionDa; "PkgExtension\\Data"
0x1801122ee  xor     r8d, r8d
0x1801122f1  mov     qword ptr [rsp+290h+var_270], r15; int
0x1801122f6  mov     [rsp+290h+var_260], r15
0x1801122fb  call    cs:__imp_SRCacheContext_Open
0x180112301  lea     rcx, [rsp+290h+var_268]
0x180112306  mov     ebx, eax
0x180112308  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18011230d  test    ebx, ebx
0x18011230f  jns     short loc_180112363
0x180112311  mov     rcx, [rbp+198h]; this
0x180112318  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18011231f  mov     r9d, ebx; char *
0x180112322  mov     edx, 18Ch; void *
0x180112327  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011232c  mov     edx, 137h; void *
0x180112331  mov     rcx, [rbp+198h]; this
0x180112338  lea     r8, aOnecoreBaseApp_415; "onecore\\base\\appmodel\\StateRepositor"...
0x18011233f  mov     r9d, ebx; char *
0x180112342  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112347  mov     rcx, qword ptr [rsp+290h+var_270]
0x18011234c  mov     qword ptr [rsp+290h+var_270], r15
0x180112351  test    rcx, rcx
0x180112354  jz      short loc_18011235C
0x180112356  call    cs:__imp_SRCacheContext_Close
0x18011235c  mov     eax, ebx
0x18011235e  jmp     loc_1801124AF
0x180112363  cmp     qword ptr [rsp+290h+var_270], r15
0x180112368  setnz   al
0x18011236b  test    al, al
0x18011236d  jnz     short loc_18011237B
0x18011236f  mov     ebx, 80670012h
0x180112374  mov     edx, 138h
0x180112379  jmp     short loc_180112331
0x18011237b  xor     edx, edx; Val
0x18011237d  mov     [rsp+290h+var_250], r15
0x180112382  mov     r8d, 200h; Size
0x180112388  lea     rcx, [rsp+290h+var_248]; void *
0x18011238d  call    memset_0
0x180112392  lea     rax, [rsp+290h+var_248]
0x180112397  mov     [rbp+190h+var_48], r15
0x18011239e  mov     rdx, r14; unsigned __int64
0x1801123a1  mov     [rbp+190h+var_38], rax
0x1801123a8  lea     rcx, [rsp+290h+var_250]; this
0x1801123ad  mov     [rbp+190h+var_40], 100h
0x1801123b8  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1801123bd  mov     ebx, eax
0x1801123bf  test    eax, eax
0x1801123c1  jns     short loc_1801123FC
0x1801123c3  mov     edx, 13Bh; void *
0x1801123c8  mov     rcx, [rbp+198h]; this
0x1801123cf  lea     r8, aOnecoreBaseApp_415; "onecore\\base\\appmodel\\StateRepositor"...
0x1801123d6  mov     r9d, ebx; char *
0x1801123d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801123de  mov     rcx, [rsp+290h+var_250]
0x1801123e3  mov     [rsp+290h+var_250], r15
0x1801123e8  test    rcx, rcx
0x1801123eb  jz      loc_180112347
0x1801123f1  call    cs:__imp_SRCache_Free
0x1801123f7  jmp     loc_180112347
0x1801123fc  mov     rdx, [rbp+190h+var_38]
0x180112403  lea     r9, [rsp+290h+var_260]
0x180112408  mov     rcx, qword ptr [rsp+290h+var_270]
0x18011240d  xor     r8d, r8d
0x180112410  mov     [rsp+290h+var_268], rdi
0x180112415  mov     [rsp+290h+var_260], r15
0x18011241a  mov     [rsp+290h+var_258], 1
0x18011241f  call    cs:__imp_SRCacheContext_OpenSubContext
0x180112425  lea     rcx, [rsp+290h+var_268]
0x18011242a  mov     ebx, eax
0x18011242c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180112431  test    ebx, ebx
0x180112433  jns     short loc_18011245A
0x180112435  mov     rcx, [rbp+198h]; this
0x18011243c  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180112443  mov     r9d, ebx; char *
0x180112446  mov     edx, 1B0h; void *
0x18011244b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112450  mov     edx, 13Ch
0x180112455  jmp     loc_1801123C8
0x18011245a  cmp     [rdi], r15
0x18011245d  lea     rdx, aPkgextensionDa; "PkgExtension\\Data"
0x180112464  lea     rcx, [rsp+290h+var_270]; this
0x180112469  setnz   al
0x18011246c  mov     [rsi], al
0x18011246e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180112473  mov     ebx, eax
0x180112475  test    eax, eax
0x180112477  jns     short loc_180112483
0x180112479  mov     edx, 13Eh
0x18011247e  jmp     loc_1801123C8
0x180112483  mov     rcx, [rsp+290h+var_250]
0x180112488  mov     [rsp+290h+var_250], r15
0x18011248d  test    rcx, rcx
0x180112490  jz      short loc_180112498
0x180112492  call    cs:__imp_SRCache_Free
0x180112498  mov     rcx, qword ptr [rsp+290h+var_270]
0x18011249d  mov     qword ptr [rsp+290h+var_270], r15
0x1801124a2  test    rcx, rcx
0x1801124a5  jz      short loc_1801124AD
0x1801124a7  call    cs:__imp_SRCacheContext_Close
0x1801124ad  xor     eax, eax
0x1801124af  mov     rcx, [rbp+190h+var_30]
0x1801124b6  xor     rcx, rsp; StackCookie
0x1801124b9  call    __security_check_cookie
0x1801124be  mov     rbx, [rsp+290h+arg_10]
0x1801124c6  add     rsp, 270h
0x1801124cd  pop     r15
0x1801124cf  pop     r14
0x1801124d1  pop     rdi
0x1801124d2  pop     rsi
0x1801124d3  pop     rbp
0x1801124d4  retn
```
