# StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800158b0`
- end: `0x180015b44`
- name: `?Open@PackageMachineStatus_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `660`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180014cd8`

## callees

- `0x180002980`
- `0x1800035c4`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x1800158b0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015978`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015b16`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015978`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015b16`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015a56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015b01`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015a56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015b01`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001591b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001591b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180015a8c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180015a8c`

## string_xrefs

- `0x1800159f6`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x18001593a`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180015aab`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18001595a`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageMachineStatus.hpp`
- `0x180015a34`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageMachineStatus.hpp`

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
  int v16[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+238h] [rbp+138h]
  __int64 v20; // [rsp+240h] [rbp+140h]
  _BYTE *v21; // [rsp+248h] [rbp+148h]
  unsigned __int16 v22[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v23; // [rsp+258h] [rbp+158h] BYREF
  char v24; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a1;
  *(_QWORD *)v22 = v16;
  v24 = 1;
  *(_QWORD *)v16 = 0;
  v23 = 0;
  v8 = SRCacheContext_Open(v4, L"PackageMachineStatus\\Data", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 309;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageMachineStatus.hpp",
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
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v19 = 0;
  v20 = 256;
  v21 = v18;
  if ( (unsigned int)o__ui64tow_s_0(a2, v22, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v16[0]);
LABEL_12:
    v12 = 313;
    goto LABEL_13;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v17, v22);
  if ( v8 < 0 )
    goto LABEL_12;
  *(_QWORD *)v22 = a3;
  v23 = 0;
  v24 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v16, v21, 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v12 = 314;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"PackageMachineStatus\\Data");
  if ( v8 < 0 )
  {
    v12 = 316;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageMachineStatus.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v17;
    v17 = 0;
    if ( v13 )
      SRCache_Free();
    goto LABEL_4;
  }
  v14 = v17;
  v17 = 0;
  if ( v14 )
    SRCache_Free();
  v15 = *(_QWORD *)v16;
  *(_QWORD *)v16 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x1800158b0  mov     [rsp-8+arg_10], rbx
0x1800158b5  push    rbp
0x1800158b6  push    rsi
0x1800158b7  push    rdi
0x1800158b8  push    r14
0x1800158ba  push    r15
0x1800158bc  lea     rbp, [rsp-180h]
0x1800158c4  sub     rsp, 280h
0x1800158cb  mov     rax, cs:__security_cookie
0x1800158d2  xor     rax, rsp
0x1800158d5  mov     [rbp+1A0h+var_28], rax
0x1800158dc  mov     rcx, [rcx]
0x1800158df  lea     rax, [rsp+2A0h+var_280]
0x1800158e4  mov     rsi, r9
0x1800158e7  mov     qword ptr [rbp+1A0h+var_50], rax
0x1800158ee  mov     rdi, r8
0x1800158f1  mov     [rbp+1A0h+var_40], 1
0x1800158f8  mov     r14, rdx
0x1800158fb  lea     r9, [rbp+1A0h+var_48]
0x180015902  xor     r15d, r15d
0x180015905  lea     rdx, aPackagemachine_0; "PackageMachineStatus\\Data"
0x18001590c  xor     r8d, r8d
0x18001590f  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x180015914  mov     [rbp+1A0h+var_48], r15
0x18001591b  call    cs:__imp_SRCacheContext_Open
0x180015921  lea     rcx, [rbp+1A0h+var_50]
0x180015928  mov     ebx, eax
0x18001592a  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001592f  test    ebx, ebx
0x180015931  jns     short loc_180015985
0x180015933  mov     rcx, [rbp+1A8h]; this
0x18001593a  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180015941  mov     r9d, ebx; char *
0x180015944  mov     edx, 18Ch; void *
0x180015949  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001594e  mov     edx, 135h; void *
0x180015953  mov     rcx, [rbp+1A8h]; this
0x18001595a  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x180015961  mov     r9d, ebx; char *
0x180015964  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015969  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001596e  mov     qword ptr [rsp+2A0h+var_280], r15
0x180015973  test    rcx, rcx
0x180015976  jz      short loc_18001597E
0x180015978  call    cs:__imp_SRCacheContext_Close
0x18001597e  mov     eax, ebx
0x180015980  jmp     loc_180015B1E
0x180015985  cmp     qword ptr [rsp+2A0h+var_280], r15
0x18001598a  setnz   al
0x18001598d  test    al, al
0x18001598f  jnz     short loc_18001599D
0x180015991  mov     ebx, 80670012h
0x180015996  mov     edx, 136h
0x18001599b  jmp     short loc_180015953
0x18001599d  xor     edx, edx; Val
0x18001599f  mov     [rsp+2A0h+var_270], r15
0x1800159a4  mov     r8d, 200h; Size
0x1800159aa  lea     rcx, [rsp+2A0h+var_268]; void *
0x1800159af  call    memset_0
0x1800159b4  mov     r9d, 10h
0x1800159ba  mov     [rbp+1A0h+var_68], r15
0x1800159c1  lea     rax, [rsp+2A0h+var_268]
0x1800159c6  mov     [rbp+1A0h+var_60], 100h
0x1800159d1  lea     rdx, [rbp+1A0h+var_50]
0x1800159d8  mov     [rbp+1A0h+var_58], rax
0x1800159df  mov     rcx, r14
0x1800159e2  lea     r8d, [r9+1]
0x1800159e6  call    _o__ui64tow_s_0
0x1800159eb  test    eax, eax
0x1800159ed  jz      short loc_180015A11
0x1800159ef  mov     rcx, [rbp+1A8h]; this
0x1800159f6  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x1800159fd  mov     ebx, 8000FFFFh
0x180015a02  mov     edx, 166h; void *
0x180015a07  mov     r9d, ebx; char *
0x180015a0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015a0f  jmp     short loc_180015A28
0x180015a11  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x180015a18  lea     rcx, [rsp+2A0h+var_270]; this
0x180015a1d  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180015a22  mov     ebx, eax
0x180015a24  test    eax, eax
0x180015a26  jns     short loc_180015A61
0x180015a28  mov     edx, 139h; void *
0x180015a2d  mov     rcx, [rbp+1A8h]; this
0x180015a34  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x180015a3b  mov     r9d, ebx; char *
0x180015a3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015a43  mov     rcx, [rsp+2A0h+var_270]
0x180015a48  mov     [rsp+2A0h+var_270], r15
0x180015a4d  test    rcx, rcx
0x180015a50  jz      loc_180015969
0x180015a56  call    cs:__imp_SRCache_Free
0x180015a5c  jmp     loc_180015969
0x180015a61  mov     rdx, [rbp+1A0h+var_58]
0x180015a68  lea     r9, [rbp+1A0h+var_48]
0x180015a6f  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180015a74  xor     r8d, r8d
0x180015a77  mov     qword ptr [rbp+1A0h+var_50], rdi
0x180015a7e  mov     [rbp+1A0h+var_48], r15
0x180015a85  mov     [rbp+1A0h+var_40], 1
0x180015a8c  call    cs:__imp_SRCacheContext_OpenSubContext
0x180015a92  lea     rcx, [rbp+1A0h+var_50]
0x180015a99  mov     ebx, eax
0x180015a9b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180015aa0  test    ebx, ebx
0x180015aa2  jns     short loc_180015AC9
0x180015aa4  mov     rcx, [rbp+1A8h]; this
0x180015aab  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180015ab2  mov     r9d, ebx; char *
0x180015ab5  mov     edx, 1B0h; void *
0x180015aba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015abf  mov     edx, 13Ah
0x180015ac4  jmp     loc_180015A2D
0x180015ac9  cmp     [rdi], r15
0x180015acc  lea     rdx, aPackagemachine_0; "PackageMachineStatus\\Data"
0x180015ad3  lea     rcx, [rsp+2A0h+var_280]; this
0x180015ad8  setnz   al
0x180015adb  mov     [rsi], al
0x180015add  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180015ae2  mov     ebx, eax
0x180015ae4  test    eax, eax
0x180015ae6  jns     short loc_180015AF2
0x180015ae8  mov     edx, 13Ch
0x180015aed  jmp     loc_180015A2D
0x180015af2  mov     rcx, [rsp+2A0h+var_270]
0x180015af7  mov     [rsp+2A0h+var_270], r15
0x180015afc  test    rcx, rcx
0x180015aff  jz      short loc_180015B07
0x180015b01  call    cs:__imp_SRCache_Free
0x180015b07  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180015b0c  mov     qword ptr [rsp+2A0h+var_280], r15
0x180015b11  test    rcx, rcx
0x180015b14  jz      short loc_180015B1C
0x180015b16  call    cs:__imp_SRCacheContext_Close
0x180015b1c  xor     eax, eax
0x180015b1e  mov     rcx, [rbp+1A0h+var_28]
0x180015b25  xor     rcx, rsp; StackCookie
0x180015b28  call    __security_check_cookie
0x180015b2d  mov     rbx, [rsp+2A0h+arg_10]
0x180015b35  add     rsp, 280h
0x180015b3c  pop     r15
0x180015b3e  pop     r14
0x180015b40  pop     rdi
0x180015b41  pop     rsi
0x180015b42  pop     rbp
0x180015b43  retn
```
