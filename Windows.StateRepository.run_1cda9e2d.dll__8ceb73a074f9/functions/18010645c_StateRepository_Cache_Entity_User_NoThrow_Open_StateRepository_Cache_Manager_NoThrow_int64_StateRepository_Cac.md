# StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18010645c`
- end: `0x180106699`
- name: `?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1802650ec`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x18010645c`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1801065e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1801065e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010651a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010666b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010651a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010666b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801065b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180106656`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801065b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180106656`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801064bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801064bf`

## string_xrefs

- `0x1801064dc`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180106600`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1801064fc`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-User.hpp`
- `0x180106593`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-User.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"User\\Data", 0, &v18);
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
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-User.hpp",
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
         L"User\\Data");
  if ( v8 < 0 )
  {
    v12 = 274;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-User.hpp",
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
0x18010645c  mov     [rsp-8+arg_10], rbx
0x180106461  push    rbp
0x180106462  push    rsi
0x180106463  push    rdi
0x180106464  push    r14
0x180106466  push    r15
0x180106468  lea     rbp, [rsp-170h]
0x180106470  sub     rsp, 270h
0x180106477  mov     rax, cs:__security_cookie
0x18010647e  xor     rax, rsp
0x180106481  mov     [rbp+190h+var_30], rax
0x180106488  mov     rcx, [rcx]
0x18010648b  lea     rax, [rsp+290h+var_270]
0x180106490  mov     rsi, r9
0x180106493  mov     [rsp+290h+var_268], rax
0x180106498  mov     rdi, r8
0x18010649b  mov     [rsp+290h+var_258], 1
0x1801064a0  mov     r14, rdx
0x1801064a3  lea     r9, [rsp+290h+var_260]
0x1801064a8  xor     r15d, r15d
0x1801064ab  lea     rdx, aUserData; "User\\Data"
0x1801064b2  xor     r8d, r8d
0x1801064b5  mov     qword ptr [rsp+290h+var_270], r15; int
0x1801064ba  mov     [rsp+290h+var_260], r15
0x1801064bf  call    cs:__imp_SRCacheContext_Open
0x1801064c5  lea     rcx, [rsp+290h+var_268]
0x1801064ca  mov     ebx, eax
0x1801064cc  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1801064d1  test    ebx, ebx
0x1801064d3  jns     short loc_180106527
0x1801064d5  mov     rcx, [rbp+198h]; this
0x1801064dc  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1801064e3  mov     r9d, ebx; char *
0x1801064e6  mov     edx, 18Ch; void *
0x1801064eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801064f0  mov     edx, 10Bh; void *
0x1801064f5  mov     rcx, [rbp+198h]; this
0x1801064fc  lea     r8, aOnecoreBaseApp_139; "onecore\\base\\appmodel\\StateRepositor"...
0x180106503  mov     r9d, ebx; char *
0x180106506  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010650b  mov     rcx, qword ptr [rsp+290h+var_270]
0x180106510  mov     qword ptr [rsp+290h+var_270], r15
0x180106515  test    rcx, rcx
0x180106518  jz      short loc_180106520
0x18010651a  call    cs:__imp_SRCacheContext_Close
0x180106520  mov     eax, ebx
0x180106522  jmp     loc_180106673
0x180106527  cmp     qword ptr [rsp+290h+var_270], r15
0x18010652c  setnz   al
0x18010652f  test    al, al
0x180106531  jnz     short loc_18010653F
0x180106533  mov     ebx, 80670012h
0x180106538  mov     edx, 10Ch
0x18010653d  jmp     short loc_1801064F5
0x18010653f  xor     edx, edx; Val
0x180106541  mov     [rsp+290h+var_250], r15
0x180106546  mov     r8d, 200h; Size
0x18010654c  lea     rcx, [rsp+290h+var_248]; void *
0x180106551  call    memset_0
0x180106556  lea     rax, [rsp+290h+var_248]
0x18010655b  mov     [rbp+190h+var_48], r15
0x180106562  mov     rdx, r14; unsigned __int64
0x180106565  mov     [rbp+190h+var_38], rax
0x18010656c  lea     rcx, [rsp+290h+var_250]; this
0x180106571  mov     [rbp+190h+var_40], 100h
0x18010657c  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180106581  mov     ebx, eax
0x180106583  test    eax, eax
0x180106585  jns     short loc_1801065C0
0x180106587  mov     edx, 10Fh; void *
0x18010658c  mov     rcx, [rbp+198h]; this
0x180106593  lea     r8, aOnecoreBaseApp_139; "onecore\\base\\appmodel\\StateRepositor"...
0x18010659a  mov     r9d, ebx; char *
0x18010659d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801065a2  mov     rcx, [rsp+290h+var_250]
0x1801065a7  mov     [rsp+290h+var_250], r15
0x1801065ac  test    rcx, rcx
0x1801065af  jz      loc_18010650B
0x1801065b5  call    cs:__imp_SRCache_Free
0x1801065bb  jmp     loc_18010650B
0x1801065c0  mov     rdx, [rbp+190h+var_38]
0x1801065c7  lea     r9, [rsp+290h+var_260]
0x1801065cc  mov     rcx, qword ptr [rsp+290h+var_270]
0x1801065d1  xor     r8d, r8d
0x1801065d4  mov     [rsp+290h+var_268], rdi
0x1801065d9  mov     [rsp+290h+var_260], r15
0x1801065de  mov     [rsp+290h+var_258], 1
0x1801065e3  call    cs:__imp_SRCacheContext_OpenSubContext
0x1801065e9  lea     rcx, [rsp+290h+var_268]
0x1801065ee  mov     ebx, eax
0x1801065f0  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1801065f5  test    ebx, ebx
0x1801065f7  jns     short loc_18010661E
0x1801065f9  mov     rcx, [rbp+198h]; this
0x180106600  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180106607  mov     r9d, ebx; char *
0x18010660a  mov     edx, 1B0h; void *
0x18010660f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180106614  mov     edx, 110h
0x180106619  jmp     loc_18010658C
0x18010661e  cmp     [rdi], r15
0x180106621  lea     rdx, aUserData; "User\\Data"
0x180106628  lea     rcx, [rsp+290h+var_270]; this
0x18010662d  setnz   al
0x180106630  mov     [rsi], al
0x180106632  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180106637  mov     ebx, eax
0x180106639  test    eax, eax
0x18010663b  jns     short loc_180106647
0x18010663d  mov     edx, 112h
0x180106642  jmp     loc_18010658C
0x180106647  mov     rcx, [rsp+290h+var_250]
0x18010664c  mov     [rsp+290h+var_250], r15
0x180106651  test    rcx, rcx
0x180106654  jz      short loc_18010665C
0x180106656  call    cs:__imp_SRCache_Free
0x18010665c  mov     rcx, qword ptr [rsp+290h+var_270]
0x180106661  mov     qword ptr [rsp+290h+var_270], r15
0x180106666  test    rcx, rcx
0x180106669  jz      short loc_180106671
0x18010666b  call    cs:__imp_SRCacheContext_Close
0x180106671  xor     eax, eax
0x180106673  mov     rcx, [rbp+190h+var_30]
0x18010667a  xor     rcx, rsp; StackCookie
0x18010667d  call    __security_check_cookie
0x180106682  mov     rbx, [rsp+290h+arg_10]
0x18010668a  add     rsp, 270h
0x180106691  pop     r15
0x180106693  pop     r14
0x180106695  pop     rdi
0x180106696  pop     rsi
0x180106697  pop     rbp
0x180106698  retn
```
