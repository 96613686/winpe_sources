# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x1800073e8`
- end: `0x180007623`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `571`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000eaec`

## callees

- `0x180001960`
- `0x1800022ea`
- `0x1800052a8`
- `0x180006ddc`
- `0x1800073e8`
- `0x18000e678`
- `0x18000e920`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180007568`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180007568`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007467`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000754f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800075d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800075fe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007467`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000754f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800075d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800075fe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800074f6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800075e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800074f6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800075e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000759b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000759b`

## string_xrefs

- `0x180007577`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800075aa`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180007449`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800074d2`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180007534`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  int v5; // ebx
  int v6; // r9d
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v10; // eax
  int v11; // r9d
  __int64 v12; // rcx
  int v13; // r9d
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  int v17; // r9d
  int v18; // eax
  int v19; // r9d
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  bool v23; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v27[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+248h] [rbp+148h]
  __int64 v29; // [rsp+250h] [rbp+150h]
  unsigned __int16 *v30; // [rsp+258h] [rbp+158h]

  *a3 = 0;
  v23 = 0;
  v24 = 0;
  v5 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v24,
         a1,
         L"Package\\Index\\PackageFullName",
         &v23);
  if ( v5 < 0 )
  {
    v7 = 1128;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)v7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (wil::details *)(unsigned int)v5,
      v6);
LABEL_4:
    v8 = v24;
    v24 = 0;
    if ( v8 )
      SRCacheContext_Close();
    return (unsigned int)v5;
  }
  if ( !v23 )
  {
    v5 = -2140733422;
    v7 = 1129;
    goto LABEL_3;
  }
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v28 = 0;
  v30 = (unsigned __int16 *)v27;
  v29 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, a2);
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)0x46C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (wil::details *)(unsigned int)v10,
      v11);
LABEL_11:
    v12 = v26;
    v26 = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_4;
  }
  v25 = 0;
  v23 = 0;
  v5 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         (struct StateRepository::Cache::Context_NoThrow *)&v24,
         v30,
         &v23);
  if ( v5 < 0 )
  {
    v14 = 1136;
    goto LABEL_15;
  }
  if ( v23 )
  {
    v16 = SRCacheContext_EnumerateData(v25, 0, a3);
    v5 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        (wil::details::in1diag3 *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (wil::details *)(unsigned int)v16,
        v17);
      v14 = 1139;
      goto LABEL_15;
    }
  }
  v18 = SRCacheContext_AddToCache(v24, L"Package\\Index\\PackageFullName");
  v5 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (wil::details *)(unsigned int)v18,
      v19);
    v14 = 1142;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (wil::details *)(unsigned int)v5,
      v13);
    v15 = v25;
    v25 = 0;
    if ( v15 )
      SRCacheContext_Close();
    goto LABEL_11;
  }
  v20 = v25;
  v25 = 0;
  if ( v20 )
    SRCacheContext_Close();
  v21 = v26;
  v26 = 0;
  if ( v21 )
    SRCache_Free();
  v22 = v24;
  v24 = 0;
  if ( v22 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x1800073e8  push    rbp
0x1800073ea  push    rbx
0x1800073eb  push    rsi
0x1800073ec  push    rdi
0x1800073ed  push    r14
0x1800073ef  lea     rbp, [rsp-170h]
0x1800073f7  sub     rsp, 270h
0x1800073fe  mov     rax, cs:__security_cookie
0x180007405  xor     rax, rsp
0x180007408  mov     [rbp+190h+var_30], rax
0x18000740f  xor     r14d, r14d
0x180007412  lea     r9, [rsp+290h+var_270]; bool *
0x180007417  mov     rsi, rdx
0x18000741a  mov     [r8], r14
0x18000741d  mov     rdi, r8
0x180007420  mov     [rsp+290h+var_270], r14b
0x180007425  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x180007428  mov     [rsp+290h+var_268], r14
0x18000742d  lea     r8, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x180007434  lea     rcx, [rsp+290h+var_268]; this
0x180007439  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18000743e  mov     ebx, eax
0x180007440  test    eax, eax
0x180007442  jns     short loc_180007474
0x180007444  mov     ecx, 468h; this
0x180007449  lea     rdx, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007450  mov     r8d, ebx; wil::details *
0x180007453  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x180007458  mov     rcx, [rsp+290h+var_268]
0x18000745d  mov     [rsp+290h+var_268], r14
0x180007462  test    rcx, rcx
0x180007465  jz      short loc_18000746D
0x180007467  call    cs:__imp_SRCacheContext_Close
0x18000746d  mov     eax, ebx
0x18000746f  jmp     loc_180007606
0x180007474  cmp     [rsp+290h+var_270], r14b
0x180007479  jnz     short loc_180007487
0x18000747b  mov     ebx, 80670012h
0x180007480  mov     ecx, 469h
0x180007485  jmp     short loc_180007449
0x180007487  xor     edx, edx; Val
0x180007489  mov     [rsp+290h+var_250], r14
0x18000748e  mov     r8d, 200h; Size
0x180007494  lea     rcx, [rsp+290h+var_248]; void *
0x180007499  call    memset_0
0x18000749e  lea     rax, [rsp+290h+var_248]
0x1800074a3  mov     [rbp+190h+var_48], r14
0x1800074aa  mov     rdx, rsi; unsigned __int16 *
0x1800074ad  mov     [rbp+190h+var_38], rax
0x1800074b4  lea     rcx, [rsp+290h+var_250]; this
0x1800074b9  mov     [rbp+190h+var_40], 100h
0x1800074c4  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800074c9  mov     ebx, eax
0x1800074cb  test    eax, eax
0x1800074cd  jns     short loc_180007501
0x1800074cf  mov     r8d, eax; wil::details *
0x1800074d2  lea     rdx, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800074d9  mov     ecx, 46Ch; this
0x1800074de  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x1800074e3  mov     rcx, [rsp+290h+var_250]
0x1800074e8  mov     [rsp+290h+var_250], r14
0x1800074ed  test    rcx, rcx
0x1800074f0  jz      loc_180007458
0x1800074f6  call    cs:__imp_SRCache_Free
0x1800074fc  jmp     loc_180007458
0x180007501  mov     r8, [rbp+190h+var_38]; unsigned __int16 *
0x180007508  lea     r9, [rsp+290h+var_270]; bool *
0x18000750d  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x180007512  mov     [rsp+290h+var_260], r14
0x180007517  lea     rcx, [rsp+290h+var_260]; this
0x18000751c  mov     [rsp+290h+var_270], r14b
0x180007521  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x180007526  mov     ebx, eax
0x180007528  test    eax, eax
0x18000752a  jns     short loc_180007557
0x18000752c  mov     ecx, 470h; this
0x180007531  mov     r8d, ebx; wil::details *
0x180007534  lea     rdx, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000753b  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x180007540  mov     rcx, [rsp+290h+var_260]
0x180007545  mov     [rsp+290h+var_260], r14
0x18000754a  test    rcx, rcx
0x18000754d  jz      short loc_1800074E3
0x18000754f  call    cs:__imp_SRCacheContext_Close
0x180007555  jmp     short loc_1800074E3
0x180007557  cmp     [rsp+290h+var_270], r14b
0x18000755c  jz      short loc_18000758F
0x18000755e  mov     rcx, [rsp+290h+var_260]
0x180007563  mov     r8, rdi
0x180007566  xor     edx, edx
0x180007568  call    cs:__imp_SRCacheContext_EnumerateData
0x18000756e  mov     ebx, eax
0x180007570  test    eax, eax
0x180007572  jns     short loc_18000758F
0x180007574  mov     r8d, eax; wil::details *
0x180007577  lea     rdx, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000757e  mov     ecx, 2A6h; this
0x180007583  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x180007588  mov     ecx, 473h
0x18000758d  jmp     short loc_180007531
0x18000758f  mov     rcx, [rsp+290h+var_268]
0x180007594  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x18000759b  call    cs:__imp_SRCacheContext_AddToCache
0x1800075a1  mov     ebx, eax
0x1800075a3  test    eax, eax
0x1800075a5  jns     short loc_1800075C5
0x1800075a7  mov     r8d, eax; wil::details *
0x1800075aa  lea     rdx, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800075b1  mov     ecx, 1A6h; this
0x1800075b6  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x1800075bb  mov     ecx, 476h
0x1800075c0  jmp     loc_180007531
0x1800075c5  mov     rcx, [rsp+290h+var_260]
0x1800075ca  mov     [rsp+290h+var_260], r14
0x1800075cf  test    rcx, rcx
0x1800075d2  jz      short loc_1800075DA
0x1800075d4  call    cs:__imp_SRCacheContext_Close
0x1800075da  mov     rcx, [rsp+290h+var_250]
0x1800075df  mov     [rsp+290h+var_250], r14
0x1800075e4  test    rcx, rcx
0x1800075e7  jz      short loc_1800075EF
0x1800075e9  call    cs:__imp_SRCache_Free
0x1800075ef  mov     rcx, [rsp+290h+var_268]
0x1800075f4  mov     [rsp+290h+var_268], r14
0x1800075f9  test    rcx, rcx
0x1800075fc  jz      short loc_180007604
0x1800075fe  call    cs:__imp_SRCacheContext_Close
0x180007604  xor     eax, eax
0x180007606  mov     rcx, [rbp+190h+var_30]
0x18000760d  xor     rcx, rsp; StackCookie
0x180007610  call    __security_check_cookie
0x180007615  add     rsp, 270h
0x18000761c  pop     r14
0x18000761e  pop     rdi
0x18000761f  pop     rsi
0x180007620  pop     rbx
0x180007621  pop     rbp
0x180007622  retn
```
