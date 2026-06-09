# StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::OpenByName(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x180017c9c`
- end: `0x180017f52`
- name: `?OpenByName@PkgExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `694`
- prototype: `int(StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180017168`

## callees

- `0x180002980`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x180017c9c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017cdf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017d73`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017dbb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017f24`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017cdf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017d73`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017dbb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017f24`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017e3e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017ef5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017f0f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017e3e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017ef5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017f0f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180017d18`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180017d18`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180017e6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180017e6c`

## string_xrefs

- `0x180017d35`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180017e89`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180017d50`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`
- `0x180017d93`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`
- `0x180017e1c`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`
- `0x180017ece`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`
- `0x180017cfa`: `PkgExtension\Index\Name`
- `0x180017eb0`: `PkgExtension\Index\Name`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::OpenByName(
        StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rcx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v20; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  char v22; // [rsp+38h] [rbp-C8h]
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+248h] [rbp+148h]
  __int64 v26; // [rsp+250h] [rbp+150h]
  _BYTE *v27; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v4 )
    SRCacheContext_Close(v4);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  v20 = v19;
  *(_QWORD *)v19 = 0;
  v21 = 0;
  v22 = 1;
  v8 = SRCacheContext_Open(v7, L"PkgExtension\\Index\\Name", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v19[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x256,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v8,
      v19[0]);
LABEL_5:
    v9 = *(_QWORD *)v19;
    *(_QWORD *)v19 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v19 )
  {
    v11 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_10:
    v12 = *(_QWORD *)v19;
    *(_QWORD *)v19 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return v11;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
  if ( v8 < 0 )
  {
    v13 = 602;
    goto LABEL_15;
  }
  v20 = (int *)this;
  v21 = 0;
  v22 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v19, v27, 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v19[0]);
    v13 = 605;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v8,
      v19[0]);
    v14 = v23;
    v23 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_5;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v15 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v19,
          L"PkgExtension\\Index\\Name");
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x263,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v15,
      v19[0]);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_10;
  }
  v17 = v23;
  v23 = 0;
  if ( v17 )
    SRCache_Free();
  v18 = *(_QWORD *)v19;
  *(_QWORD *)v19 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return 0;
}

```

## disassembly

```asm
0x180017c9c  mov     [rsp-8+arg_18], rbx
0x180017ca1  push    rbp
0x180017ca2  push    rsi
0x180017ca3  push    rdi
0x180017ca4  push    r14
0x180017ca6  push    r15
0x180017ca8  lea     rbp, [rsp-170h]
0x180017cb0  sub     rsp, 270h
0x180017cb7  mov     rax, cs:__security_cookie
0x180017cbe  xor     rax, rsp
0x180017cc1  mov     [rbp+190h+var_30], rax
0x180017cc8  mov     rbx, rcx
0x180017ccb  xor     r15d, r15d
0x180017cce  mov     rcx, [rcx]
0x180017cd1  mov     r14, r8
0x180017cd4  mov     rsi, rdx
0x180017cd7  mov     [rbx], r15
0x180017cda  test    rcx, rcx
0x180017cdd  jz      short loc_180017CE5
0x180017cdf  call    cs:__imp_SRCacheContext_Close
0x180017ce5  mov     [rbx+8], r15d
0x180017ce9  lea     rax, [rsp+290h+var_270]
0x180017cee  mov     [rbx+10h], r15
0x180017cf2  lea     r9, [rsp+290h+var_260]
0x180017cf7  mov     rcx, [rsi]
0x180017cfa  lea     rdx, aPkgextensionIn; "PkgExtension\\Index\\Name"
0x180017d01  xor     r8d, r8d
0x180017d04  mov     [rsp+290h+var_268], rax
0x180017d09  mov     qword ptr [rsp+290h+var_270], r15; int
0x180017d0e  mov     [rsp+290h+var_260], r15
0x180017d13  mov     [rsp+290h+var_258], 1
0x180017d18  call    cs:__imp_SRCacheContext_Open
0x180017d1e  lea     rcx, [rsp+290h+var_268]
0x180017d23  mov     edi, eax
0x180017d25  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180017d2a  test    edi, edi
0x180017d2c  jns     short loc_180017D80
0x180017d2e  mov     rcx, [rbp+198h]; this
0x180017d35  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180017d3c  mov     r9d, edi; char *
0x180017d3f  mov     edx, 18Ch; void *
0x180017d44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d49  mov     rcx, [rbp+198h]; this
0x180017d50  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x180017d57  mov     r9d, edi; char *
0x180017d5a  mov     edx, 256h; void *
0x180017d5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d64  mov     rcx, qword ptr [rsp+290h+var_270]
0x180017d69  mov     qword ptr [rsp+290h+var_270], r15
0x180017d6e  test    rcx, rcx
0x180017d71  jz      short loc_180017D79
0x180017d73  call    cs:__imp_SRCacheContext_Close
0x180017d79  mov     eax, edi
0x180017d7b  jmp     loc_180017F2C
0x180017d80  cmp     qword ptr [rsp+290h+var_270], r15
0x180017d85  setnz   al
0x180017d88  test    al, al
0x180017d8a  jnz     short loc_180017DC8
0x180017d8c  mov     rcx, [rbp+198h]; this
0x180017d93  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x180017d9a  mov     ebx, 80670012h
0x180017d9f  mov     edx, 257h; void *
0x180017da4  mov     r9d, ebx; char *
0x180017da7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017dac  mov     rcx, qword ptr [rsp+290h+var_270]
0x180017db1  mov     qword ptr [rsp+290h+var_270], r15
0x180017db6  test    rcx, rcx
0x180017db9  jz      short loc_180017DC1
0x180017dbb  call    cs:__imp_SRCacheContext_Close
0x180017dc1  mov     eax, ebx
0x180017dc3  jmp     loc_180017F2C
0x180017dc8  xor     edx, edx; Val
0x180017dca  mov     [rsp+290h+var_250], r15
0x180017dcf  mov     r8d, 200h; Size
0x180017dd5  lea     rcx, [rsp+290h+var_248]; void *
0x180017dda  call    memset_0
0x180017ddf  lea     rax, [rsp+290h+var_248]
0x180017de4  mov     [rbp+190h+var_48], r15
0x180017deb  mov     rdx, r14; unsigned __int16 *
0x180017dee  mov     [rbp+190h+var_38], rax
0x180017df5  lea     rcx, [rsp+290h+var_250]; this
0x180017dfa  mov     [rbp+190h+var_40], 100h
0x180017e05  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180017e0a  mov     edi, eax
0x180017e0c  test    eax, eax
0x180017e0e  jns     short loc_180017E49
0x180017e10  mov     edx, 25Ah; void *
0x180017e15  mov     rcx, [rbp+198h]; this
0x180017e1c  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x180017e23  mov     r9d, edi; char *
0x180017e26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e2b  mov     rcx, [rsp+290h+var_250]
0x180017e30  mov     [rsp+290h+var_250], r15
0x180017e35  test    rcx, rcx
0x180017e38  jz      loc_180017D64
0x180017e3e  call    cs:__imp_SRCache_Free
0x180017e44  jmp     loc_180017D64
0x180017e49  mov     rdx, [rbp+190h+var_38]
0x180017e50  lea     r9, [rsp+290h+var_260]
0x180017e55  mov     rcx, qword ptr [rsp+290h+var_270]
0x180017e5a  xor     r8d, r8d
0x180017e5d  mov     [rsp+290h+var_268], rbx
0x180017e62  mov     [rsp+290h+var_260], r15
0x180017e67  mov     [rsp+290h+var_258], 1
0x180017e6c  call    cs:__imp_SRCacheContext_OpenSubContext
0x180017e72  lea     rcx, [rsp+290h+var_268]
0x180017e77  mov     edi, eax
0x180017e79  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180017e7e  test    edi, edi
0x180017e80  jns     short loc_180017EA7
0x180017e82  mov     rcx, [rbp+198h]; this
0x180017e89  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180017e90  mov     r9d, edi; char *
0x180017e93  mov     edx, 1B0h; void *
0x180017e98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e9d  mov     edx, 25Dh
0x180017ea2  jmp     loc_180017E15
0x180017ea7  cmp     [rbx], r15
0x180017eaa  jz      short loc_180017EB0
0x180017eac  mov     [rbx+10h], rsi
0x180017eb0  lea     rdx, aPkgextensionIn; "PkgExtension\\Index\\Name"
0x180017eb7  lea     rcx, [rsp+290h+var_270]; this
0x180017ebc  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180017ec1  mov     ebx, eax
0x180017ec3  test    eax, eax
0x180017ec5  jns     short loc_180017F00
0x180017ec7  mov     rcx, [rbp+198h]; this
0x180017ece  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x180017ed5  mov     r9d, eax; char *
0x180017ed8  mov     edx, 263h; void *
0x180017edd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ee2  mov     rcx, [rsp+290h+var_250]
0x180017ee7  mov     [rsp+290h+var_250], r15
0x180017eec  test    rcx, rcx
0x180017eef  jz      loc_180017DAC
0x180017ef5  call    cs:__imp_SRCache_Free
0x180017efb  jmp     loc_180017DAC
0x180017f00  mov     rcx, [rsp+290h+var_250]
0x180017f05  mov     [rsp+290h+var_250], r15
0x180017f0a  test    rcx, rcx
0x180017f0d  jz      short loc_180017F15
0x180017f0f  call    cs:__imp_SRCache_Free
0x180017f15  mov     rcx, qword ptr [rsp+290h+var_270]
0x180017f1a  mov     qword ptr [rsp+290h+var_270], r15
0x180017f1f  test    rcx, rcx
0x180017f22  jz      short loc_180017F2A
0x180017f24  call    cs:__imp_SRCacheContext_Close
0x180017f2a  xor     eax, eax
0x180017f2c  mov     rcx, [rbp+190h+var_30]
0x180017f33  xor     rcx, rsp; StackCookie
0x180017f36  call    __security_check_cookie
0x180017f3b  mov     rbx, [rsp+290h+arg_18]
0x180017f43  add     rsp, 270h
0x180017f4a  pop     r15
0x180017f4c  pop     r14
0x180017f4e  pop     rdi
0x180017f4f  pop     rsi
0x180017f50  pop     rbp
0x180017f51  retn
```
