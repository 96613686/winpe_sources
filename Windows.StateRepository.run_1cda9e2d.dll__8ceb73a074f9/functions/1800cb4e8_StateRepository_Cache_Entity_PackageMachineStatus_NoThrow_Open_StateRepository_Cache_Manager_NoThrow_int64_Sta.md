# StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800cb4e8`
- end: `0x1800cb725`
- name: `?Open@PackageMachineStatus_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18026c3c4`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x1800cb4e8`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800cb66f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800cb66f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cb5a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cb6f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cb5a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cb6f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cb641`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cb6e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cb641`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cb6e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800cb54b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800cb54b`

## string_xrefs

- `0x1800cb568`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800cb68c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800cb588`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageMachineStatus.hpp`
- `0x1800cb61f`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageMachineStatus.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PackageMachineStatus\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 309;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageMachineStatus.hpp",
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
    v9 = 310;
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
    v12 = 313;
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
    v12 = 314;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"PackageMachineStatus\\Data");
  if ( v8 < 0 )
  {
    v12 = 316;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageMachineStatus.hpp",
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
0x1800cb4e8  mov     [rsp-8+arg_10], rbx
0x1800cb4ed  push    rbp
0x1800cb4ee  push    rsi
0x1800cb4ef  push    rdi
0x1800cb4f0  push    r14
0x1800cb4f2  push    r15
0x1800cb4f4  lea     rbp, [rsp-170h]
0x1800cb4fc  sub     rsp, 270h
0x1800cb503  mov     rax, cs:__security_cookie
0x1800cb50a  xor     rax, rsp
0x1800cb50d  mov     [rbp+190h+var_30], rax
0x1800cb514  mov     rcx, [rcx]
0x1800cb517  lea     rax, [rsp+290h+var_270]
0x1800cb51c  mov     rsi, r9
0x1800cb51f  mov     [rsp+290h+var_268], rax
0x1800cb524  mov     rdi, r8
0x1800cb527  mov     [rsp+290h+var_258], 1
0x1800cb52c  mov     r14, rdx
0x1800cb52f  lea     r9, [rsp+290h+var_260]
0x1800cb534  xor     r15d, r15d
0x1800cb537  lea     rdx, aPackagemachine_8; "PackageMachineStatus\\Data"
0x1800cb53e  xor     r8d, r8d
0x1800cb541  mov     qword ptr [rsp+290h+var_270], r15; int
0x1800cb546  mov     [rsp+290h+var_260], r15
0x1800cb54b  call    cs:__imp_SRCacheContext_Open
0x1800cb551  lea     rcx, [rsp+290h+var_268]
0x1800cb556  mov     ebx, eax
0x1800cb558  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800cb55d  test    ebx, ebx
0x1800cb55f  jns     short loc_1800CB5B3
0x1800cb561  mov     rcx, [rbp+198h]; this
0x1800cb568  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800cb56f  mov     r9d, ebx; char *
0x1800cb572  mov     edx, 18Ch; void *
0x1800cb577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb57c  mov     edx, 135h; void *
0x1800cb581  mov     rcx, [rbp+198h]; this
0x1800cb588  lea     r8, aOnecoreBaseApp_98; "onecore\\base\\appmodel\\StateRepositor"...
0x1800cb58f  mov     r9d, ebx; char *
0x1800cb592  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb597  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800cb59c  mov     qword ptr [rsp+290h+var_270], r15
0x1800cb5a1  test    rcx, rcx
0x1800cb5a4  jz      short loc_1800CB5AC
0x1800cb5a6  call    cs:__imp_SRCacheContext_Close
0x1800cb5ac  mov     eax, ebx
0x1800cb5ae  jmp     loc_1800CB6FF
0x1800cb5b3  cmp     qword ptr [rsp+290h+var_270], r15
0x1800cb5b8  setnz   al
0x1800cb5bb  test    al, al
0x1800cb5bd  jnz     short loc_1800CB5CB
0x1800cb5bf  mov     ebx, 80670012h
0x1800cb5c4  mov     edx, 136h
0x1800cb5c9  jmp     short loc_1800CB581
0x1800cb5cb  xor     edx, edx; Val
0x1800cb5cd  mov     [rsp+290h+var_250], r15
0x1800cb5d2  mov     r8d, 200h; Size
0x1800cb5d8  lea     rcx, [rsp+290h+var_248]; void *
0x1800cb5dd  call    memset_0
0x1800cb5e2  lea     rax, [rsp+290h+var_248]
0x1800cb5e7  mov     [rbp+190h+var_48], r15
0x1800cb5ee  mov     rdx, r14; unsigned __int64
0x1800cb5f1  mov     [rbp+190h+var_38], rax
0x1800cb5f8  lea     rcx, [rsp+290h+var_250]; this
0x1800cb5fd  mov     [rbp+190h+var_40], 100h
0x1800cb608  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800cb60d  mov     ebx, eax
0x1800cb60f  test    eax, eax
0x1800cb611  jns     short loc_1800CB64C
0x1800cb613  mov     edx, 139h; void *
0x1800cb618  mov     rcx, [rbp+198h]; this
0x1800cb61f  lea     r8, aOnecoreBaseApp_98; "onecore\\base\\appmodel\\StateRepositor"...
0x1800cb626  mov     r9d, ebx; char *
0x1800cb629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb62e  mov     rcx, [rsp+290h+var_250]
0x1800cb633  mov     [rsp+290h+var_250], r15
0x1800cb638  test    rcx, rcx
0x1800cb63b  jz      loc_1800CB597
0x1800cb641  call    cs:__imp_SRCache_Free
0x1800cb647  jmp     loc_1800CB597
0x1800cb64c  mov     rdx, [rbp+190h+var_38]
0x1800cb653  lea     r9, [rsp+290h+var_260]
0x1800cb658  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800cb65d  xor     r8d, r8d
0x1800cb660  mov     [rsp+290h+var_268], rdi
0x1800cb665  mov     [rsp+290h+var_260], r15
0x1800cb66a  mov     [rsp+290h+var_258], 1
0x1800cb66f  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800cb675  lea     rcx, [rsp+290h+var_268]
0x1800cb67a  mov     ebx, eax
0x1800cb67c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800cb681  test    ebx, ebx
0x1800cb683  jns     short loc_1800CB6AA
0x1800cb685  mov     rcx, [rbp+198h]; this
0x1800cb68c  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800cb693  mov     r9d, ebx; char *
0x1800cb696  mov     edx, 1B0h; void *
0x1800cb69b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb6a0  mov     edx, 13Ah
0x1800cb6a5  jmp     loc_1800CB618
0x1800cb6aa  cmp     [rdi], r15
0x1800cb6ad  lea     rdx, aPackagemachine_8; "PackageMachineStatus\\Data"
0x1800cb6b4  lea     rcx, [rsp+290h+var_270]; this
0x1800cb6b9  setnz   al
0x1800cb6bc  mov     [rsi], al
0x1800cb6be  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800cb6c3  mov     ebx, eax
0x1800cb6c5  test    eax, eax
0x1800cb6c7  jns     short loc_1800CB6D3
0x1800cb6c9  mov     edx, 13Ch
0x1800cb6ce  jmp     loc_1800CB618
0x1800cb6d3  mov     rcx, [rsp+290h+var_250]
0x1800cb6d8  mov     [rsp+290h+var_250], r15
0x1800cb6dd  test    rcx, rcx
0x1800cb6e0  jz      short loc_1800CB6E8
0x1800cb6e2  call    cs:__imp_SRCache_Free
0x1800cb6e8  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800cb6ed  mov     qword ptr [rsp+290h+var_270], r15
0x1800cb6f2  test    rcx, rcx
0x1800cb6f5  jz      short loc_1800CB6FD
0x1800cb6f7  call    cs:__imp_SRCacheContext_Close
0x1800cb6fd  xor     eax, eax
0x1800cb6ff  mov     rcx, [rbp+190h+var_30]
0x1800cb706  xor     rcx, rsp; StackCookie
0x1800cb709  call    __security_check_cookie
0x1800cb70e  mov     rbx, [rsp+290h+arg_10]
0x1800cb716  add     rsp, 270h
0x1800cb71d  pop     r15
0x1800cb71f  pop     r14
0x1800cb721  pop     rdi
0x1800cb722  pop     rsi
0x1800cb723  pop     rbp
0x1800cb724  retn
```
