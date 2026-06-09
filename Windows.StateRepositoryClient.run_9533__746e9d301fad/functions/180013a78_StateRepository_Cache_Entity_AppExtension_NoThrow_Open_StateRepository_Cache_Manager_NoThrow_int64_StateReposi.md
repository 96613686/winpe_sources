# StateRepository::Cache::Entity::AppExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180013a78`
- end: `0x180013d0c`
- name: `?Open@AppExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `660`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180012d30`

## callees

- `0x180002980`
- `0x1800035c4`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x180013a78`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013b40`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013cde`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013b40`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013cde`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180013c1e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180013cc9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180013c1e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180013cc9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180013ae3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180013ae3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180013c54`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180013c54`

## string_xrefs

- `0x180013bbe`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x180013b02`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180013c73`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180013b22`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`
- `0x180013bfc`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`
- `0x180013acd`: `AppExtension\Data`
- `0x180013c94`: `AppExtension\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppExtension_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"AppExtension\\Data", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 311;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
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
    v12 = 315;
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
    v12 = 316;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"AppExtension\\Data");
  if ( v8 < 0 )
  {
    v12 = 318;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
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
0x180013a78  mov     [rsp-8+arg_10], rbx
0x180013a7d  push    rbp
0x180013a7e  push    rsi
0x180013a7f  push    rdi
0x180013a80  push    r14
0x180013a82  push    r15
0x180013a84  lea     rbp, [rsp-180h]
0x180013a8c  sub     rsp, 280h
0x180013a93  mov     rax, cs:__security_cookie
0x180013a9a  xor     rax, rsp
0x180013a9d  mov     [rbp+1A0h+var_28], rax
0x180013aa4  mov     rcx, [rcx]
0x180013aa7  lea     rax, [rsp+2A0h+var_280]
0x180013aac  mov     rsi, r9
0x180013aaf  mov     qword ptr [rbp+1A0h+var_50], rax
0x180013ab6  mov     rdi, r8
0x180013ab9  mov     [rbp+1A0h+var_40], 1
0x180013ac0  mov     r14, rdx
0x180013ac3  lea     r9, [rbp+1A0h+var_48]
0x180013aca  xor     r15d, r15d
0x180013acd  lea     rdx, aAppextensionDa; "AppExtension\\Data"
0x180013ad4  xor     r8d, r8d
0x180013ad7  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x180013adc  mov     [rbp+1A0h+var_48], r15
0x180013ae3  call    cs:__imp_SRCacheContext_Open
0x180013ae9  lea     rcx, [rbp+1A0h+var_50]
0x180013af0  mov     ebx, eax
0x180013af2  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180013af7  test    ebx, ebx
0x180013af9  jns     short loc_180013B4D
0x180013afb  mov     rcx, [rbp+1A8h]; this
0x180013b02  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180013b09  mov     r9d, ebx; char *
0x180013b0c  mov     edx, 18Ch; void *
0x180013b11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013b16  mov     edx, 137h; void *
0x180013b1b  mov     rcx, [rbp+1A8h]; this
0x180013b22  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x180013b29  mov     r9d, ebx; char *
0x180013b2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013b31  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180013b36  mov     qword ptr [rsp+2A0h+var_280], r15
0x180013b3b  test    rcx, rcx
0x180013b3e  jz      short loc_180013B46
0x180013b40  call    cs:__imp_SRCacheContext_Close
0x180013b46  mov     eax, ebx
0x180013b48  jmp     loc_180013CE6
0x180013b4d  cmp     qword ptr [rsp+2A0h+var_280], r15
0x180013b52  setnz   al
0x180013b55  test    al, al
0x180013b57  jnz     short loc_180013B65
0x180013b59  mov     ebx, 80670012h
0x180013b5e  mov     edx, 138h
0x180013b63  jmp     short loc_180013B1B
0x180013b65  xor     edx, edx; Val
0x180013b67  mov     [rsp+2A0h+var_270], r15
0x180013b6c  mov     r8d, 200h; Size
0x180013b72  lea     rcx, [rsp+2A0h+var_268]; void *
0x180013b77  call    memset_0
0x180013b7c  mov     r9d, 10h
0x180013b82  mov     [rbp+1A0h+var_68], r15
0x180013b89  lea     rax, [rsp+2A0h+var_268]
0x180013b8e  mov     [rbp+1A0h+var_60], 100h
0x180013b99  lea     rdx, [rbp+1A0h+var_50]
0x180013ba0  mov     [rbp+1A0h+var_58], rax
0x180013ba7  mov     rcx, r14
0x180013baa  lea     r8d, [r9+1]
0x180013bae  call    _o__ui64tow_s_0
0x180013bb3  test    eax, eax
0x180013bb5  jz      short loc_180013BD9
0x180013bb7  mov     rcx, [rbp+1A8h]; this
0x180013bbe  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x180013bc5  mov     ebx, 8000FFFFh
0x180013bca  mov     edx, 166h; void *
0x180013bcf  mov     r9d, ebx; char *
0x180013bd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013bd7  jmp     short loc_180013BF0
0x180013bd9  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x180013be0  lea     rcx, [rsp+2A0h+var_270]; this
0x180013be5  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180013bea  mov     ebx, eax
0x180013bec  test    eax, eax
0x180013bee  jns     short loc_180013C29
0x180013bf0  mov     edx, 13Bh; void *
0x180013bf5  mov     rcx, [rbp+1A8h]; this
0x180013bfc  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x180013c03  mov     r9d, ebx; char *
0x180013c06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013c0b  mov     rcx, [rsp+2A0h+var_270]
0x180013c10  mov     [rsp+2A0h+var_270], r15
0x180013c15  test    rcx, rcx
0x180013c18  jz      loc_180013B31
0x180013c1e  call    cs:__imp_SRCache_Free
0x180013c24  jmp     loc_180013B31
0x180013c29  mov     rdx, [rbp+1A0h+var_58]
0x180013c30  lea     r9, [rbp+1A0h+var_48]
0x180013c37  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180013c3c  xor     r8d, r8d
0x180013c3f  mov     qword ptr [rbp+1A0h+var_50], rdi
0x180013c46  mov     [rbp+1A0h+var_48], r15
0x180013c4d  mov     [rbp+1A0h+var_40], 1
0x180013c54  call    cs:__imp_SRCacheContext_OpenSubContext
0x180013c5a  lea     rcx, [rbp+1A0h+var_50]
0x180013c61  mov     ebx, eax
0x180013c63  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180013c68  test    ebx, ebx
0x180013c6a  jns     short loc_180013C91
0x180013c6c  mov     rcx, [rbp+1A8h]; this
0x180013c73  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180013c7a  mov     r9d, ebx; char *
0x180013c7d  mov     edx, 1B0h; void *
0x180013c82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013c87  mov     edx, 13Ch
0x180013c8c  jmp     loc_180013BF5
0x180013c91  cmp     [rdi], r15
0x180013c94  lea     rdx, aAppextensionDa; "AppExtension\\Data"
0x180013c9b  lea     rcx, [rsp+2A0h+var_280]; this
0x180013ca0  setnz   al
0x180013ca3  mov     [rsi], al
0x180013ca5  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180013caa  mov     ebx, eax
0x180013cac  test    eax, eax
0x180013cae  jns     short loc_180013CBA
0x180013cb0  mov     edx, 13Eh
0x180013cb5  jmp     loc_180013BF5
0x180013cba  mov     rcx, [rsp+2A0h+var_270]
0x180013cbf  mov     [rsp+2A0h+var_270], r15
0x180013cc4  test    rcx, rcx
0x180013cc7  jz      short loc_180013CCF
0x180013cc9  call    cs:__imp_SRCache_Free
0x180013ccf  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180013cd4  mov     qword ptr [rsp+2A0h+var_280], r15
0x180013cd9  test    rcx, rcx
0x180013cdc  jz      short loc_180013CE4
0x180013cde  call    cs:__imp_SRCacheContext_Close
0x180013ce4  xor     eax, eax
0x180013ce6  mov     rcx, [rbp+1A0h+var_28]
0x180013ced  xor     rcx, rsp; StackCookie
0x180013cf0  call    __security_check_cookie
0x180013cf5  mov     rbx, [rsp+2A0h+arg_10]
0x180013cfd  add     rsp, 280h
0x180013d04  pop     r15
0x180013d06  pop     r14
0x180013d08  pop     rdi
0x180013d09  pop     rsi
0x180013d0a  pop     rbp
0x180013d0b  retn
```
