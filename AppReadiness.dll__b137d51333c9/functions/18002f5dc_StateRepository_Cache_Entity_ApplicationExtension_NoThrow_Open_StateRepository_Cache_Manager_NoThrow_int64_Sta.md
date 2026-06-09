# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18002f5dc`
- end: `0x18002f819`
- name: `?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002f2fc`

## callees

- `0x180019780`
- `0x18001ffa0`
- `0x18002f59c`
- `0x18002f5dc`
- `0x180030914`
- `0x18003e210`
- `0x18003eca8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002f763`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002f763`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002f63f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002f63f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f69a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f7eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f69a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f7eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002f735`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002f7d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002f735`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002f7d6`

## string_xrefs

- `0x18002f65c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002f780`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002f67c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18002f713`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18002f62b`: `ApplicationExtension\Data`
- `0x18002f7a1`: `ApplicationExtension\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"ApplicationExtension\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 364;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
    v9 = 365;
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
    v12 = 368;
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
    v12 = 369;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"ApplicationExtension\\Data");
  if ( v8 < 0 )
  {
    v12 = 371;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
0x18002f5dc  mov     [rsp-8+arg_10], rbx
0x18002f5e1  push    rbp
0x18002f5e2  push    rsi
0x18002f5e3  push    rdi
0x18002f5e4  push    r14
0x18002f5e6  push    r15
0x18002f5e8  lea     rbp, [rsp-170h]
0x18002f5f0  sub     rsp, 270h
0x18002f5f7  mov     rax, cs:__security_cookie
0x18002f5fe  xor     rax, rsp
0x18002f601  mov     [rbp+190h+var_30], rax
0x18002f608  mov     rcx, [rcx]
0x18002f60b  lea     rax, [rsp+290h+var_270]
0x18002f610  mov     rsi, r9
0x18002f613  mov     [rsp+290h+var_268], rax
0x18002f618  mov     rdi, r8
0x18002f61b  mov     [rsp+290h+var_258], 1
0x18002f620  mov     r14, rdx
0x18002f623  lea     r9, [rsp+290h+var_260]
0x18002f628  xor     r15d, r15d
0x18002f62b  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x18002f632  xor     r8d, r8d
0x18002f635  mov     qword ptr [rsp+290h+var_270], r15; int
0x18002f63a  mov     [rsp+290h+var_260], r15
0x18002f63f  call    cs:__imp_SRCacheContext_Open
0x18002f645  lea     rcx, [rsp+290h+var_268]
0x18002f64a  mov     ebx, eax
0x18002f64c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18002f651  test    ebx, ebx
0x18002f653  jns     short loc_18002F6A7
0x18002f655  mov     rcx, [rbp+198h]; this
0x18002f65c  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f663  mov     r9d, ebx; char *
0x18002f666  mov     edx, 18Ch; void *
0x18002f66b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f670  mov     edx, 16Ch; void *
0x18002f675  mov     rcx, [rbp+198h]; this
0x18002f67c  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f683  mov     r9d, ebx; char *
0x18002f686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f68b  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002f690  mov     qword ptr [rsp+290h+var_270], r15
0x18002f695  test    rcx, rcx
0x18002f698  jz      short loc_18002F6A0
0x18002f69a  call    cs:__imp_SRCacheContext_Close
0x18002f6a0  mov     eax, ebx
0x18002f6a2  jmp     loc_18002F7F3
0x18002f6a7  cmp     qword ptr [rsp+290h+var_270], r15
0x18002f6ac  setnz   al
0x18002f6af  test    al, al
0x18002f6b1  jnz     short loc_18002F6BF
0x18002f6b3  mov     ebx, 80670012h
0x18002f6b8  mov     edx, 16Dh
0x18002f6bd  jmp     short loc_18002F675
0x18002f6bf  xor     edx, edx; Val
0x18002f6c1  mov     [rsp+290h+var_250], r15
0x18002f6c6  mov     r8d, 200h; Size
0x18002f6cc  lea     rcx, [rsp+290h+var_248]; void *
0x18002f6d1  call    memset_0
0x18002f6d6  lea     rax, [rsp+290h+var_248]
0x18002f6db  mov     [rbp+190h+var_48], r15
0x18002f6e2  mov     rdx, r14; unsigned __int64
0x18002f6e5  mov     [rbp+190h+var_38], rax
0x18002f6ec  lea     rcx, [rsp+290h+var_250]; this
0x18002f6f1  mov     [rbp+190h+var_40], 100h
0x18002f6fc  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002f701  mov     ebx, eax
0x18002f703  test    eax, eax
0x18002f705  jns     short loc_18002F740
0x18002f707  mov     edx, 170h; void *
0x18002f70c  mov     rcx, [rbp+198h]; this
0x18002f713  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f71a  mov     r9d, ebx; char *
0x18002f71d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f722  mov     rcx, [rsp+290h+var_250]
0x18002f727  mov     [rsp+290h+var_250], r15
0x18002f72c  test    rcx, rcx
0x18002f72f  jz      loc_18002F68B
0x18002f735  call    cs:__imp_SRCache_Free
0x18002f73b  jmp     loc_18002F68B
0x18002f740  mov     rdx, [rbp+190h+var_38]
0x18002f747  lea     r9, [rsp+290h+var_260]
0x18002f74c  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002f751  xor     r8d, r8d
0x18002f754  mov     [rsp+290h+var_268], rdi
0x18002f759  mov     [rsp+290h+var_260], r15
0x18002f75e  mov     [rsp+290h+var_258], 1
0x18002f763  call    cs:__imp_SRCacheContext_OpenSubContext
0x18002f769  lea     rcx, [rsp+290h+var_268]
0x18002f76e  mov     ebx, eax
0x18002f770  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18002f775  test    ebx, ebx
0x18002f777  jns     short loc_18002F79E
0x18002f779  mov     rcx, [rbp+198h]; this
0x18002f780  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f787  mov     r9d, ebx; char *
0x18002f78a  mov     edx, 1B0h; void *
0x18002f78f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f794  mov     edx, 171h
0x18002f799  jmp     loc_18002F70C
0x18002f79e  cmp     [rdi], r15
0x18002f7a1  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x18002f7a8  lea     rcx, [rsp+290h+var_270]; this
0x18002f7ad  setnz   al
0x18002f7b0  mov     [rsi], al
0x18002f7b2  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18002f7b7  mov     ebx, eax
0x18002f7b9  test    eax, eax
0x18002f7bb  jns     short loc_18002F7C7
0x18002f7bd  mov     edx, 173h
0x18002f7c2  jmp     loc_18002F70C
0x18002f7c7  mov     rcx, [rsp+290h+var_250]
0x18002f7cc  mov     [rsp+290h+var_250], r15
0x18002f7d1  test    rcx, rcx
0x18002f7d4  jz      short loc_18002F7DC
0x18002f7d6  call    cs:__imp_SRCache_Free
0x18002f7dc  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002f7e1  mov     qword ptr [rsp+290h+var_270], r15
0x18002f7e6  test    rcx, rcx
0x18002f7e9  jz      short loc_18002F7F1
0x18002f7eb  call    cs:__imp_SRCacheContext_Close
0x18002f7f1  xor     eax, eax
0x18002f7f3  mov     rcx, [rbp+190h+var_30]
0x18002f7fa  xor     rcx, rsp; StackCookie
0x18002f7fd  call    __security_check_cookie
0x18002f802  mov     rbx, [rsp+290h+arg_10]
0x18002f80a  add     rsp, 270h
0x18002f811  pop     r15
0x18002f813  pop     r14
0x18002f815  pop     rdi
0x18002f816  pop     rsi
0x18002f817  pop     rbp
0x18002f818  retn
```
