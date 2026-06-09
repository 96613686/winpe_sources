# StateRepository::Cache::Entity::PackageFamilyUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180101828`
- end: `0x180101a65`
- name: `?Open@PackageFamilyUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1802720f4`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x180101828`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1801019af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1801019af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801018e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180101a37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801018e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180101a37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180101981`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180101a22`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180101981`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180101a22`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18010188b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18010188b`

## string_xrefs

- `0x1801018a8`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1801019cc`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1801018c8`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageFamilyUser.hpp`
- `0x18010195f`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageFamilyUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamilyUser_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PackageFamilyUser\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 267;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageFamilyUser.hpp",
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
    v9 = 268;
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
    v12 = 271;
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
    v12 = 272;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"PackageFamilyUser\\Data");
  if ( v8 < 0 )
  {
    v12 = 274;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageFamilyUser.hpp",
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
0x180101828  mov     [rsp-8+arg_10], rbx
0x18010182d  push    rbp
0x18010182e  push    rsi
0x18010182f  push    rdi
0x180101830  push    r14
0x180101832  push    r15
0x180101834  lea     rbp, [rsp-170h]
0x18010183c  sub     rsp, 270h
0x180101843  mov     rax, cs:__security_cookie
0x18010184a  xor     rax, rsp
0x18010184d  mov     [rbp+190h+var_30], rax
0x180101854  mov     rcx, [rcx]
0x180101857  lea     rax, [rsp+290h+var_270]
0x18010185c  mov     rsi, r9
0x18010185f  mov     [rsp+290h+var_268], rax
0x180101864  mov     rdi, r8
0x180101867  mov     [rsp+290h+var_258], 1
0x18010186c  mov     r14, rdx
0x18010186f  lea     r9, [rsp+290h+var_260]
0x180101874  xor     r15d, r15d
0x180101877  lea     rdx, aPackagefamilyu_6; "PackageFamilyUser\\Data"
0x18010187e  xor     r8d, r8d
0x180101881  mov     qword ptr [rsp+290h+var_270], r15; int
0x180101886  mov     [rsp+290h+var_260], r15
0x18010188b  call    cs:__imp_SRCacheContext_Open
0x180101891  lea     rcx, [rsp+290h+var_268]
0x180101896  mov     ebx, eax
0x180101898  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18010189d  test    ebx, ebx
0x18010189f  jns     short loc_1801018F3
0x1801018a1  mov     rcx, [rbp+198h]; this
0x1801018a8  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1801018af  mov     r9d, ebx; char *
0x1801018b2  mov     edx, 18Ch; void *
0x1801018b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801018bc  mov     edx, 10Bh; void *
0x1801018c1  mov     rcx, [rbp+198h]; this
0x1801018c8  lea     r8, aOnecoreBaseApp_174; "onecore\\base\\appmodel\\StateRepositor"...
0x1801018cf  mov     r9d, ebx; char *
0x1801018d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801018d7  mov     rcx, qword ptr [rsp+290h+var_270]
0x1801018dc  mov     qword ptr [rsp+290h+var_270], r15
0x1801018e1  test    rcx, rcx
0x1801018e4  jz      short loc_1801018EC
0x1801018e6  call    cs:__imp_SRCacheContext_Close
0x1801018ec  mov     eax, ebx
0x1801018ee  jmp     loc_180101A3F
0x1801018f3  cmp     qword ptr [rsp+290h+var_270], r15
0x1801018f8  setnz   al
0x1801018fb  test    al, al
0x1801018fd  jnz     short loc_18010190B
0x1801018ff  mov     ebx, 80670012h
0x180101904  mov     edx, 10Ch
0x180101909  jmp     short loc_1801018C1
0x18010190b  xor     edx, edx; Val
0x18010190d  mov     [rsp+290h+var_250], r15
0x180101912  mov     r8d, 200h; Size
0x180101918  lea     rcx, [rsp+290h+var_248]; void *
0x18010191d  call    memset_0
0x180101922  lea     rax, [rsp+290h+var_248]
0x180101927  mov     [rbp+190h+var_48], r15
0x18010192e  mov     rdx, r14; unsigned __int64
0x180101931  mov     [rbp+190h+var_38], rax
0x180101938  lea     rcx, [rsp+290h+var_250]; this
0x18010193d  mov     [rbp+190h+var_40], 100h
0x180101948  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18010194d  mov     ebx, eax
0x18010194f  test    eax, eax
0x180101951  jns     short loc_18010198C
0x180101953  mov     edx, 10Fh; void *
0x180101958  mov     rcx, [rbp+198h]; this
0x18010195f  lea     r8, aOnecoreBaseApp_174; "onecore\\base\\appmodel\\StateRepositor"...
0x180101966  mov     r9d, ebx; char *
0x180101969  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010196e  mov     rcx, [rsp+290h+var_250]
0x180101973  mov     [rsp+290h+var_250], r15
0x180101978  test    rcx, rcx
0x18010197b  jz      loc_1801018D7
0x180101981  call    cs:__imp_SRCache_Free
0x180101987  jmp     loc_1801018D7
0x18010198c  mov     rdx, [rbp+190h+var_38]
0x180101993  lea     r9, [rsp+290h+var_260]
0x180101998  mov     rcx, qword ptr [rsp+290h+var_270]
0x18010199d  xor     r8d, r8d
0x1801019a0  mov     [rsp+290h+var_268], rdi
0x1801019a5  mov     [rsp+290h+var_260], r15
0x1801019aa  mov     [rsp+290h+var_258], 1
0x1801019af  call    cs:__imp_SRCacheContext_OpenSubContext
0x1801019b5  lea     rcx, [rsp+290h+var_268]
0x1801019ba  mov     ebx, eax
0x1801019bc  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1801019c1  test    ebx, ebx
0x1801019c3  jns     short loc_1801019EA
0x1801019c5  mov     rcx, [rbp+198h]; this
0x1801019cc  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1801019d3  mov     r9d, ebx; char *
0x1801019d6  mov     edx, 1B0h; void *
0x1801019db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801019e0  mov     edx, 110h
0x1801019e5  jmp     loc_180101958
0x1801019ea  cmp     [rdi], r15
0x1801019ed  lea     rdx, aPackagefamilyu_6; "PackageFamilyUser\\Data"
0x1801019f4  lea     rcx, [rsp+290h+var_270]; this
0x1801019f9  setnz   al
0x1801019fc  mov     [rsi], al
0x1801019fe  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180101a03  mov     ebx, eax
0x180101a05  test    eax, eax
0x180101a07  jns     short loc_180101A13
0x180101a09  mov     edx, 112h
0x180101a0e  jmp     loc_180101958
0x180101a13  mov     rcx, [rsp+290h+var_250]
0x180101a18  mov     [rsp+290h+var_250], r15
0x180101a1d  test    rcx, rcx
0x180101a20  jz      short loc_180101A28
0x180101a22  call    cs:__imp_SRCache_Free
0x180101a28  mov     rcx, qword ptr [rsp+290h+var_270]
0x180101a2d  mov     qword ptr [rsp+290h+var_270], r15
0x180101a32  test    rcx, rcx
0x180101a35  jz      short loc_180101A3D
0x180101a37  call    cs:__imp_SRCacheContext_Close
0x180101a3d  xor     eax, eax
0x180101a3f  mov     rcx, [rbp+190h+var_30]
0x180101a46  xor     rcx, rsp; StackCookie
0x180101a49  call    __security_check_cookie
0x180101a4e  mov     rbx, [rsp+290h+arg_10]
0x180101a56  add     rsp, 270h
0x180101a5d  pop     r15
0x180101a5f  pop     r14
0x180101a61  pop     rdi
0x180101a62  pop     rsi
0x180101a63  pop     rbp
0x180101a64  retn
```
