# StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18002fd50`
- end: `0x18002ff8d`
- name: `?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002f4bc`

## callees

- `0x180019780`
- `0x18001ffa0`
- `0x18002f59c`
- `0x18002fd50`
- `0x180030914`
- `0x18003e210`
- `0x18003eca8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002fed7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002fed7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002fdb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002fdb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002fe0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ff5f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002fe0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ff5f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002fea9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002ff4a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002fea9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002ff4a`

## string_xrefs

- `0x18002fdd0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002fef4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002fdf0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18002fe87`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"Activation\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 391;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
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
    v9 = 392;
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
    v12 = 395;
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
    v12 = 396;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"Activation\\Data");
  if ( v8 < 0 )
  {
    v12 = 398;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
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
0x18002fd50  mov     [rsp-8+arg_10], rbx
0x18002fd55  push    rbp
0x18002fd56  push    rsi
0x18002fd57  push    rdi
0x18002fd58  push    r14
0x18002fd5a  push    r15
0x18002fd5c  lea     rbp, [rsp-170h]
0x18002fd64  sub     rsp, 270h
0x18002fd6b  mov     rax, cs:__security_cookie
0x18002fd72  xor     rax, rsp
0x18002fd75  mov     [rbp+190h+var_30], rax
0x18002fd7c  mov     rcx, [rcx]
0x18002fd7f  lea     rax, [rsp+290h+var_270]
0x18002fd84  mov     rsi, r9
0x18002fd87  mov     [rsp+290h+var_268], rax
0x18002fd8c  mov     rdi, r8
0x18002fd8f  mov     [rsp+290h+var_258], 1
0x18002fd94  mov     r14, rdx
0x18002fd97  lea     r9, [rsp+290h+var_260]
0x18002fd9c  xor     r15d, r15d
0x18002fd9f  lea     rdx, aActivationData; "Activation\\Data"
0x18002fda6  xor     r8d, r8d
0x18002fda9  mov     qword ptr [rsp+290h+var_270], r15; int
0x18002fdae  mov     [rsp+290h+var_260], r15
0x18002fdb3  call    cs:__imp_SRCacheContext_Open
0x18002fdb9  lea     rcx, [rsp+290h+var_268]
0x18002fdbe  mov     ebx, eax
0x18002fdc0  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18002fdc5  test    ebx, ebx
0x18002fdc7  jns     short loc_18002FE1B
0x18002fdc9  mov     rcx, [rbp+198h]; this
0x18002fdd0  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002fdd7  mov     r9d, ebx; char *
0x18002fdda  mov     edx, 18Ch; void *
0x18002fddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fde4  mov     edx, 187h; void *
0x18002fde9  mov     rcx, [rbp+198h]; this
0x18002fdf0  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002fdf7  mov     r9d, ebx; char *
0x18002fdfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fdff  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002fe04  mov     qword ptr [rsp+290h+var_270], r15
0x18002fe09  test    rcx, rcx
0x18002fe0c  jz      short loc_18002FE14
0x18002fe0e  call    cs:__imp_SRCacheContext_Close
0x18002fe14  mov     eax, ebx
0x18002fe16  jmp     loc_18002FF67
0x18002fe1b  cmp     qword ptr [rsp+290h+var_270], r15
0x18002fe20  setnz   al
0x18002fe23  test    al, al
0x18002fe25  jnz     short loc_18002FE33
0x18002fe27  mov     ebx, 80670012h
0x18002fe2c  mov     edx, 188h
0x18002fe31  jmp     short loc_18002FDE9
0x18002fe33  xor     edx, edx; Val
0x18002fe35  mov     [rsp+290h+var_250], r15
0x18002fe3a  mov     r8d, 200h; Size
0x18002fe40  lea     rcx, [rsp+290h+var_248]; void *
0x18002fe45  call    memset_0
0x18002fe4a  lea     rax, [rsp+290h+var_248]
0x18002fe4f  mov     [rbp+190h+var_48], r15
0x18002fe56  mov     rdx, r14; unsigned __int64
0x18002fe59  mov     [rbp+190h+var_38], rax
0x18002fe60  lea     rcx, [rsp+290h+var_250]; this
0x18002fe65  mov     [rbp+190h+var_40], 100h
0x18002fe70  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002fe75  mov     ebx, eax
0x18002fe77  test    eax, eax
0x18002fe79  jns     short loc_18002FEB4
0x18002fe7b  mov     edx, 18Bh; void *
0x18002fe80  mov     rcx, [rbp+198h]; this
0x18002fe87  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002fe8e  mov     r9d, ebx; char *
0x18002fe91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fe96  mov     rcx, [rsp+290h+var_250]
0x18002fe9b  mov     [rsp+290h+var_250], r15
0x18002fea0  test    rcx, rcx
0x18002fea3  jz      loc_18002FDFF
0x18002fea9  call    cs:__imp_SRCache_Free
0x18002feaf  jmp     loc_18002FDFF
0x18002feb4  mov     rdx, [rbp+190h+var_38]
0x18002febb  lea     r9, [rsp+290h+var_260]
0x18002fec0  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002fec5  xor     r8d, r8d
0x18002fec8  mov     [rsp+290h+var_268], rdi
0x18002fecd  mov     [rsp+290h+var_260], r15
0x18002fed2  mov     [rsp+290h+var_258], 1
0x18002fed7  call    cs:__imp_SRCacheContext_OpenSubContext
0x18002fedd  lea     rcx, [rsp+290h+var_268]
0x18002fee2  mov     ebx, eax
0x18002fee4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18002fee9  test    ebx, ebx
0x18002feeb  jns     short loc_18002FF12
0x18002feed  mov     rcx, [rbp+198h]; this
0x18002fef4  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002fefb  mov     r9d, ebx; char *
0x18002fefe  mov     edx, 1B0h; void *
0x18002ff03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ff08  mov     edx, 18Ch
0x18002ff0d  jmp     loc_18002FE80
0x18002ff12  cmp     [rdi], r15
0x18002ff15  lea     rdx, aActivationData; "Activation\\Data"
0x18002ff1c  lea     rcx, [rsp+290h+var_270]; this
0x18002ff21  setnz   al
0x18002ff24  mov     [rsi], al
0x18002ff26  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18002ff2b  mov     ebx, eax
0x18002ff2d  test    eax, eax
0x18002ff2f  jns     short loc_18002FF3B
0x18002ff31  mov     edx, 18Eh
0x18002ff36  jmp     loc_18002FE80
0x18002ff3b  mov     rcx, [rsp+290h+var_250]
0x18002ff40  mov     [rsp+290h+var_250], r15
0x18002ff45  test    rcx, rcx
0x18002ff48  jz      short loc_18002FF50
0x18002ff4a  call    cs:__imp_SRCache_Free
0x18002ff50  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002ff55  mov     qword ptr [rsp+290h+var_270], r15
0x18002ff5a  test    rcx, rcx
0x18002ff5d  jz      short loc_18002FF65
0x18002ff5f  call    cs:__imp_SRCacheContext_Close
0x18002ff65  xor     eax, eax
0x18002ff67  mov     rcx, [rbp+190h+var_30]
0x18002ff6e  xor     rcx, rsp; StackCookie
0x18002ff71  call    __security_check_cookie
0x18002ff76  mov     rbx, [rsp+290h+arg_10]
0x18002ff7e  add     rsp, 270h
0x18002ff85  pop     r15
0x18002ff87  pop     r14
0x18002ff89  pop     rdi
0x18002ff8a  pop     rsi
0x18002ff8b  pop     rbp
0x18002ff8c  retn
```
