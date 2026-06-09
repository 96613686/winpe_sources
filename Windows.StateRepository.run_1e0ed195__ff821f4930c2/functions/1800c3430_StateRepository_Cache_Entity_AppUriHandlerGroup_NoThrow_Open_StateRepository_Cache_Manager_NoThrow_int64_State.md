# StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800c3430`
- end: `0x1800c366d`
- name: `?Open@AppUriHandlerGroup_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1802693d0`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x1800c3430`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800c35b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800c35b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c34ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c363f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c34ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c363f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c3589`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c362a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c3589`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c362a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800c3493`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800c3493`

## string_xrefs

- `0x1800c34b0`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800c35d4`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800c34d0`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-AppUriHandlerGroup.hpp`
- `0x1800c3567`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-AppUriHandlerGroup.hpp`
- `0x1800c347f`: `AppUriHandlerGroup\Data`
- `0x1800c35f5`: `AppUriHandlerGroup\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
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
  v8 = SRCacheContext_Open(v4, L"AppUriHandlerGroup\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 245;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-AppUriHandlerGroup.hpp",
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
    v9 = 246;
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
    v12 = 249;
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
    v12 = 250;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"AppUriHandlerGroup\\Data");
  if ( v8 < 0 )
  {
    v12 = 252;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-AppUriHandlerGroup.hpp",
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
0x1800c3430  mov     [rsp-8+arg_10], rbx
0x1800c3435  push    rbp
0x1800c3436  push    rsi
0x1800c3437  push    rdi
0x1800c3438  push    r14
0x1800c343a  push    r15
0x1800c343c  lea     rbp, [rsp-170h]
0x1800c3444  sub     rsp, 270h
0x1800c344b  mov     rax, cs:__security_cookie
0x1800c3452  xor     rax, rsp
0x1800c3455  mov     [rbp+190h+var_30], rax
0x1800c345c  mov     rcx, [rcx]
0x1800c345f  lea     rax, [rsp+290h+var_270]
0x1800c3464  mov     rsi, r9
0x1800c3467  mov     [rsp+290h+var_268], rax
0x1800c346c  mov     rdi, r8
0x1800c346f  mov     [rsp+290h+var_258], 1
0x1800c3474  mov     r14, rdx
0x1800c3477  lea     r9, [rsp+290h+var_260]
0x1800c347c  xor     r15d, r15d
0x1800c347f  lea     rdx, aAppurihandlerg_3; "AppUriHandlerGroup\\Data"
0x1800c3486  xor     r8d, r8d
0x1800c3489  mov     qword ptr [rsp+290h+var_270], r15; int
0x1800c348e  mov     [rsp+290h+var_260], r15
0x1800c3493  call    cs:__imp_SRCacheContext_Open
0x1800c3499  lea     rcx, [rsp+290h+var_268]
0x1800c349e  mov     ebx, eax
0x1800c34a0  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800c34a5  test    ebx, ebx
0x1800c34a7  jns     short loc_1800C34FB
0x1800c34a9  mov     rcx, [rbp+198h]; this
0x1800c34b0  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800c34b7  mov     r9d, ebx; char *
0x1800c34ba  mov     edx, 18Ch; void *
0x1800c34bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c34c4  mov     edx, 0F5h; void *
0x1800c34c9  mov     rcx, [rbp+198h]; this
0x1800c34d0  lea     r8, aOnecoreBaseApp_116; "onecore\\base\\appmodel\\StateRepositor"...
0x1800c34d7  mov     r9d, ebx; char *
0x1800c34da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c34df  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800c34e4  mov     qword ptr [rsp+290h+var_270], r15
0x1800c34e9  test    rcx, rcx
0x1800c34ec  jz      short loc_1800C34F4
0x1800c34ee  call    cs:__imp_SRCacheContext_Close
0x1800c34f4  mov     eax, ebx
0x1800c34f6  jmp     loc_1800C3647
0x1800c34fb  cmp     qword ptr [rsp+290h+var_270], r15
0x1800c3500  setnz   al
0x1800c3503  test    al, al
0x1800c3505  jnz     short loc_1800C3513
0x1800c3507  mov     ebx, 80670012h
0x1800c350c  mov     edx, 0F6h
0x1800c3511  jmp     short loc_1800C34C9
0x1800c3513  xor     edx, edx; Val
0x1800c3515  mov     [rsp+290h+var_250], r15
0x1800c351a  mov     r8d, 200h; Size
0x1800c3520  lea     rcx, [rsp+290h+var_248]; void *
0x1800c3525  call    memset_0
0x1800c352a  lea     rax, [rsp+290h+var_248]
0x1800c352f  mov     [rbp+190h+var_48], r15
0x1800c3536  mov     rdx, r14; unsigned __int64
0x1800c3539  mov     [rbp+190h+var_38], rax
0x1800c3540  lea     rcx, [rsp+290h+var_250]; this
0x1800c3545  mov     [rbp+190h+var_40], 100h
0x1800c3550  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800c3555  mov     ebx, eax
0x1800c3557  test    eax, eax
0x1800c3559  jns     short loc_1800C3594
0x1800c355b  mov     edx, 0F9h; void *
0x1800c3560  mov     rcx, [rbp+198h]; this
0x1800c3567  lea     r8, aOnecoreBaseApp_116; "onecore\\base\\appmodel\\StateRepositor"...
0x1800c356e  mov     r9d, ebx; char *
0x1800c3571  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3576  mov     rcx, [rsp+290h+var_250]
0x1800c357b  mov     [rsp+290h+var_250], r15
0x1800c3580  test    rcx, rcx
0x1800c3583  jz      loc_1800C34DF
0x1800c3589  call    cs:__imp_SRCache_Free
0x1800c358f  jmp     loc_1800C34DF
0x1800c3594  mov     rdx, [rbp+190h+var_38]
0x1800c359b  lea     r9, [rsp+290h+var_260]
0x1800c35a0  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800c35a5  xor     r8d, r8d
0x1800c35a8  mov     [rsp+290h+var_268], rdi
0x1800c35ad  mov     [rsp+290h+var_260], r15
0x1800c35b2  mov     [rsp+290h+var_258], 1
0x1800c35b7  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800c35bd  lea     rcx, [rsp+290h+var_268]
0x1800c35c2  mov     ebx, eax
0x1800c35c4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800c35c9  test    ebx, ebx
0x1800c35cb  jns     short loc_1800C35F2
0x1800c35cd  mov     rcx, [rbp+198h]; this
0x1800c35d4  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800c35db  mov     r9d, ebx; char *
0x1800c35de  mov     edx, 1B0h; void *
0x1800c35e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c35e8  mov     edx, 0FAh
0x1800c35ed  jmp     loc_1800C3560
0x1800c35f2  cmp     [rdi], r15
0x1800c35f5  lea     rdx, aAppurihandlerg_3; "AppUriHandlerGroup\\Data"
0x1800c35fc  lea     rcx, [rsp+290h+var_270]; this
0x1800c3601  setnz   al
0x1800c3604  mov     [rsi], al
0x1800c3606  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800c360b  mov     ebx, eax
0x1800c360d  test    eax, eax
0x1800c360f  jns     short loc_1800C361B
0x1800c3611  mov     edx, 0FCh
0x1800c3616  jmp     loc_1800C3560
0x1800c361b  mov     rcx, [rsp+290h+var_250]
0x1800c3620  mov     [rsp+290h+var_250], r15
0x1800c3625  test    rcx, rcx
0x1800c3628  jz      short loc_1800C3630
0x1800c362a  call    cs:__imp_SRCache_Free
0x1800c3630  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800c3635  mov     qword ptr [rsp+290h+var_270], r15
0x1800c363a  test    rcx, rcx
0x1800c363d  jz      short loc_1800C3645
0x1800c363f  call    cs:__imp_SRCacheContext_Close
0x1800c3645  xor     eax, eax
0x1800c3647  mov     rcx, [rbp+190h+var_30]
0x1800c364e  xor     rcx, rsp; StackCookie
0x1800c3651  call    __security_check_cookie
0x1800c3656  mov     rbx, [rsp+290h+arg_10]
0x1800c365e  add     rsp, 270h
0x1800c3665  pop     r15
0x1800c3667  pop     r14
0x1800c3669  pop     rdi
0x1800c366a  pop     rsi
0x1800c366b  pop     rbp
0x1800c366c  retn
```
