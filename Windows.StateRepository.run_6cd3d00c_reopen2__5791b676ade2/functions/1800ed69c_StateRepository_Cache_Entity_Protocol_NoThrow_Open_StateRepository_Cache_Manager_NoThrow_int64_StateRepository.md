# StateRepository::Cache::Entity::Protocol_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800ed69c`
- end: `0x1800ed8d9`
- name: `?Open@Protocol_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18026fea0`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x1800ed69c`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800ed823`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800ed823`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ed75a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ed8ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ed75a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ed8ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ed7f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ed896`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ed7f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ed896`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800ed6ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800ed6ff`

## string_xrefs

- `0x1800ed6eb`: `Protocol\Data`
- `0x1800ed861`: `Protocol\Data`
- `0x1800ed71c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800ed840`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800ed73c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-Protocol.hpp`
- `0x1800ed7d3`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-Protocol.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Protocol_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"Protocol\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 277;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-Protocol.hpp",
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
    v9 = 278;
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
    v12 = 281;
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
    v12 = 282;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"Protocol\\Data");
  if ( v8 < 0 )
  {
    v12 = 284;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-Protocol.hpp",
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
0x1800ed69c  mov     [rsp-8+arg_10], rbx
0x1800ed6a1  push    rbp
0x1800ed6a2  push    rsi
0x1800ed6a3  push    rdi
0x1800ed6a4  push    r14
0x1800ed6a6  push    r15
0x1800ed6a8  lea     rbp, [rsp-170h]
0x1800ed6b0  sub     rsp, 270h
0x1800ed6b7  mov     rax, cs:__security_cookie
0x1800ed6be  xor     rax, rsp
0x1800ed6c1  mov     [rbp+190h+var_30], rax
0x1800ed6c8  mov     rcx, [rcx]
0x1800ed6cb  lea     rax, [rsp+290h+var_270]
0x1800ed6d0  mov     rsi, r9
0x1800ed6d3  mov     [rsp+290h+var_268], rax
0x1800ed6d8  mov     rdi, r8
0x1800ed6db  mov     [rsp+290h+var_258], 1
0x1800ed6e0  mov     r14, rdx
0x1800ed6e3  lea     r9, [rsp+290h+var_260]
0x1800ed6e8  xor     r15d, r15d
0x1800ed6eb  lea     rdx, aProtocolData; "Protocol\\Data"
0x1800ed6f2  xor     r8d, r8d
0x1800ed6f5  mov     qword ptr [rsp+290h+var_270], r15; int
0x1800ed6fa  mov     [rsp+290h+var_260], r15
0x1800ed6ff  call    cs:__imp_SRCacheContext_Open
0x1800ed705  lea     rcx, [rsp+290h+var_268]
0x1800ed70a  mov     ebx, eax
0x1800ed70c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800ed711  test    ebx, ebx
0x1800ed713  jns     short loc_1800ED767
0x1800ed715  mov     rcx, [rbp+198h]; this
0x1800ed71c  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800ed723  mov     r9d, ebx; char *
0x1800ed726  mov     edx, 18Ch; void *
0x1800ed72b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed730  mov     edx, 115h; void *
0x1800ed735  mov     rcx, [rbp+198h]; this
0x1800ed73c  lea     r8, aOnecoreBaseApp_166; "onecore\\base\\appmodel\\StateRepositor"...
0x1800ed743  mov     r9d, ebx; char *
0x1800ed746  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed74b  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800ed750  mov     qword ptr [rsp+290h+var_270], r15
0x1800ed755  test    rcx, rcx
0x1800ed758  jz      short loc_1800ED760
0x1800ed75a  call    cs:__imp_SRCacheContext_Close
0x1800ed760  mov     eax, ebx
0x1800ed762  jmp     loc_1800ED8B3
0x1800ed767  cmp     qword ptr [rsp+290h+var_270], r15
0x1800ed76c  setnz   al
0x1800ed76f  test    al, al
0x1800ed771  jnz     short loc_1800ED77F
0x1800ed773  mov     ebx, 80670012h
0x1800ed778  mov     edx, 116h
0x1800ed77d  jmp     short loc_1800ED735
0x1800ed77f  xor     edx, edx; Val
0x1800ed781  mov     [rsp+290h+var_250], r15
0x1800ed786  mov     r8d, 200h; Size
0x1800ed78c  lea     rcx, [rsp+290h+var_248]; void *
0x1800ed791  call    memset_0
0x1800ed796  lea     rax, [rsp+290h+var_248]
0x1800ed79b  mov     [rbp+190h+var_48], r15
0x1800ed7a2  mov     rdx, r14; unsigned __int64
0x1800ed7a5  mov     [rbp+190h+var_38], rax
0x1800ed7ac  lea     rcx, [rsp+290h+var_250]; this
0x1800ed7b1  mov     [rbp+190h+var_40], 100h
0x1800ed7bc  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800ed7c1  mov     ebx, eax
0x1800ed7c3  test    eax, eax
0x1800ed7c5  jns     short loc_1800ED800
0x1800ed7c7  mov     edx, 119h; void *
0x1800ed7cc  mov     rcx, [rbp+198h]; this
0x1800ed7d3  lea     r8, aOnecoreBaseApp_166; "onecore\\base\\appmodel\\StateRepositor"...
0x1800ed7da  mov     r9d, ebx; char *
0x1800ed7dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed7e2  mov     rcx, [rsp+290h+var_250]
0x1800ed7e7  mov     [rsp+290h+var_250], r15
0x1800ed7ec  test    rcx, rcx
0x1800ed7ef  jz      loc_1800ED74B
0x1800ed7f5  call    cs:__imp_SRCache_Free
0x1800ed7fb  jmp     loc_1800ED74B
0x1800ed800  mov     rdx, [rbp+190h+var_38]
0x1800ed807  lea     r9, [rsp+290h+var_260]
0x1800ed80c  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800ed811  xor     r8d, r8d
0x1800ed814  mov     [rsp+290h+var_268], rdi
0x1800ed819  mov     [rsp+290h+var_260], r15
0x1800ed81e  mov     [rsp+290h+var_258], 1
0x1800ed823  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800ed829  lea     rcx, [rsp+290h+var_268]
0x1800ed82e  mov     ebx, eax
0x1800ed830  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800ed835  test    ebx, ebx
0x1800ed837  jns     short loc_1800ED85E
0x1800ed839  mov     rcx, [rbp+198h]; this
0x1800ed840  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800ed847  mov     r9d, ebx; char *
0x1800ed84a  mov     edx, 1B0h; void *
0x1800ed84f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed854  mov     edx, 11Ah
0x1800ed859  jmp     loc_1800ED7CC
0x1800ed85e  cmp     [rdi], r15
0x1800ed861  lea     rdx, aProtocolData; "Protocol\\Data"
0x1800ed868  lea     rcx, [rsp+290h+var_270]; this
0x1800ed86d  setnz   al
0x1800ed870  mov     [rsi], al
0x1800ed872  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800ed877  mov     ebx, eax
0x1800ed879  test    eax, eax
0x1800ed87b  jns     short loc_1800ED887
0x1800ed87d  mov     edx, 11Ch
0x1800ed882  jmp     loc_1800ED7CC
0x1800ed887  mov     rcx, [rsp+290h+var_250]
0x1800ed88c  mov     [rsp+290h+var_250], r15
0x1800ed891  test    rcx, rcx
0x1800ed894  jz      short loc_1800ED89C
0x1800ed896  call    cs:__imp_SRCache_Free
0x1800ed89c  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800ed8a1  mov     qword ptr [rsp+290h+var_270], r15
0x1800ed8a6  test    rcx, rcx
0x1800ed8a9  jz      short loc_1800ED8B1
0x1800ed8ab  call    cs:__imp_SRCacheContext_Close
0x1800ed8b1  xor     eax, eax
0x1800ed8b3  mov     rcx, [rbp+190h+var_30]
0x1800ed8ba  xor     rcx, rsp; StackCookie
0x1800ed8bd  call    __security_check_cookie
0x1800ed8c2  mov     rbx, [rsp+290h+arg_10]
0x1800ed8ca  add     rsp, 270h
0x1800ed8d1  pop     r15
0x1800ed8d3  pop     r14
0x1800ed8d5  pop     rdi
0x1800ed8d6  pop     rsi
0x1800ed8d7  pop     rbp
0x1800ed8d8  retn
```
