# StateRepository::Cache::Entity::Application_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18002fb0c`
- end: `0x18002fd49`
- name: `?Open@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002f3dc`

## callees

- `0x180019780`
- `0x18001ffa0`
- `0x18002f59c`
- `0x18002fb0c`
- `0x180030914`
- `0x18003e210`
- `0x18003eca8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002fc93`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002fc93`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002fb6f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002fb6f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002fbca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002fd1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002fbca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002fd1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002fc65`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002fd06`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002fc65`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002fd06`

## string_xrefs

- `0x18002fb8c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002fcb0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002fbac`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18002fc43`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"Application\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 433;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
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
    v9 = 434;
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
    v12 = 437;
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
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v12 = 438;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"Application\\Data");
  if ( v8 < 0 )
  {
    v12 = 440;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v20;
    v20 = 0;
    if ( v13 )
      SRCache_Free();
    goto LABEL_4;
  }
  v14 = v20;
  v20 = 0;
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
0x18002fb0c  mov     [rsp-8+arg_10], rbx
0x18002fb11  push    rbp
0x18002fb12  push    rsi
0x18002fb13  push    rdi
0x18002fb14  push    r14
0x18002fb16  push    r15
0x18002fb18  lea     rbp, [rsp-170h]
0x18002fb20  sub     rsp, 270h
0x18002fb27  mov     rax, cs:__security_cookie
0x18002fb2e  xor     rax, rsp
0x18002fb31  mov     [rbp+190h+var_30], rax
0x18002fb38  mov     rcx, [rcx]
0x18002fb3b  lea     rax, [rsp+290h+var_270]
0x18002fb40  mov     rsi, r9
0x18002fb43  mov     [rsp+290h+var_268], rax
0x18002fb48  mov     rdi, r8
0x18002fb4b  mov     [rsp+290h+var_258], 1
0x18002fb50  mov     r14, rdx
0x18002fb53  lea     r9, [rsp+290h+var_260]
0x18002fb58  xor     r15d, r15d
0x18002fb5b  lea     rdx, aApplicationDat; "Application\\Data"
0x18002fb62  xor     r8d, r8d
0x18002fb65  mov     qword ptr [rsp+290h+var_270], r15; int
0x18002fb6a  mov     [rsp+290h+var_260], r15
0x18002fb6f  call    cs:__imp_SRCacheContext_Open
0x18002fb75  lea     rcx, [rsp+290h+var_268]
0x18002fb7a  mov     ebx, eax
0x18002fb7c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18002fb81  test    ebx, ebx
0x18002fb83  jns     short loc_18002FBD7
0x18002fb85  mov     rcx, [rbp+198h]; this
0x18002fb8c  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002fb93  mov     r9d, ebx; char *
0x18002fb96  mov     edx, 18Ch; void *
0x18002fb9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fba0  mov     edx, 1B1h; void *
0x18002fba5  mov     rcx, [rbp+198h]; this
0x18002fbac  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002fbb3  mov     r9d, ebx; char *
0x18002fbb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fbbb  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002fbc0  mov     qword ptr [rsp+290h+var_270], r15
0x18002fbc5  test    rcx, rcx
0x18002fbc8  jz      short loc_18002FBD0
0x18002fbca  call    cs:__imp_SRCacheContext_Close
0x18002fbd0  mov     eax, ebx
0x18002fbd2  jmp     loc_18002FD23
0x18002fbd7  cmp     qword ptr [rsp+290h+var_270], r15
0x18002fbdc  setnz   al
0x18002fbdf  test    al, al
0x18002fbe1  jnz     short loc_18002FBEF
0x18002fbe3  mov     ebx, 80670012h
0x18002fbe8  mov     edx, 1B2h
0x18002fbed  jmp     short loc_18002FBA5
0x18002fbef  xor     edx, edx; Val
0x18002fbf1  mov     [rsp+290h+var_250], r15
0x18002fbf6  mov     r8d, 200h; Size
0x18002fbfc  lea     rcx, [rsp+290h+var_248]; void *
0x18002fc01  call    memset_0
0x18002fc06  lea     rax, [rsp+290h+var_248]
0x18002fc0b  mov     [rbp+190h+var_48], r15
0x18002fc12  mov     rdx, r14; unsigned __int64
0x18002fc15  mov     [rbp+190h+var_38], rax
0x18002fc1c  lea     rcx, [rsp+290h+var_250]; this
0x18002fc21  mov     [rbp+190h+var_40], 100h
0x18002fc2c  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002fc31  mov     ebx, eax
0x18002fc33  test    eax, eax
0x18002fc35  jns     short loc_18002FC70
0x18002fc37  mov     edx, 1B5h; void *
0x18002fc3c  mov     rcx, [rbp+198h]; this
0x18002fc43  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002fc4a  mov     r9d, ebx; char *
0x18002fc4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fc52  mov     rcx, [rsp+290h+var_250]
0x18002fc57  mov     [rsp+290h+var_250], r15
0x18002fc5c  test    rcx, rcx
0x18002fc5f  jz      loc_18002FBBB
0x18002fc65  call    cs:__imp_SRCache_Free
0x18002fc6b  jmp     loc_18002FBBB
0x18002fc70  mov     rdx, [rbp+190h+var_38]
0x18002fc77  lea     r9, [rsp+290h+var_260]
0x18002fc7c  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002fc81  xor     r8d, r8d
0x18002fc84  mov     [rsp+290h+var_268], rdi
0x18002fc89  mov     [rsp+290h+var_260], r15
0x18002fc8e  mov     [rsp+290h+var_258], 1
0x18002fc93  call    cs:__imp_SRCacheContext_OpenSubContext
0x18002fc99  lea     rcx, [rsp+290h+var_268]
0x18002fc9e  mov     ebx, eax
0x18002fca0  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18002fca5  test    ebx, ebx
0x18002fca7  jns     short loc_18002FCCE
0x18002fca9  mov     rcx, [rbp+198h]; this
0x18002fcb0  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002fcb7  mov     r9d, ebx; char *
0x18002fcba  mov     edx, 1B0h; void *
0x18002fcbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fcc4  mov     edx, 1B6h
0x18002fcc9  jmp     loc_18002FC3C
0x18002fcce  cmp     [rdi], r15
0x18002fcd1  lea     rdx, aApplicationDat; "Application\\Data"
0x18002fcd8  lea     rcx, [rsp+290h+var_270]; this
0x18002fcdd  setnz   al
0x18002fce0  mov     [rsi], al
0x18002fce2  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18002fce7  mov     ebx, eax
0x18002fce9  test    eax, eax
0x18002fceb  jns     short loc_18002FCF7
0x18002fced  mov     edx, 1B8h
0x18002fcf2  jmp     loc_18002FC3C
0x18002fcf7  mov     rcx, [rsp+290h+var_250]
0x18002fcfc  mov     [rsp+290h+var_250], r15
0x18002fd01  test    rcx, rcx
0x18002fd04  jz      short loc_18002FD0C
0x18002fd06  call    cs:__imp_SRCache_Free
0x18002fd0c  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002fd11  mov     qword ptr [rsp+290h+var_270], r15
0x18002fd16  test    rcx, rcx
0x18002fd19  jz      short loc_18002FD21
0x18002fd1b  call    cs:__imp_SRCacheContext_Close
0x18002fd21  xor     eax, eax
0x18002fd23  mov     rcx, [rbp+190h+var_30]
0x18002fd2a  xor     rcx, rsp; StackCookie
0x18002fd2d  call    __security_check_cookie
0x18002fd32  mov     rbx, [rsp+290h+arg_10]
0x18002fd3a  add     rsp, 270h
0x18002fd41  pop     r15
0x18002fd43  pop     r14
0x18002fd45  pop     rdi
0x18002fd46  pop     rsi
0x18002fd47  pop     rbp
0x18002fd48  retn
```
