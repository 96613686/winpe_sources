# StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x18002f820`
- end: `0x18002fb04`
- name: `?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `740`
- prototype: `int(StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004da98`

## callees

- `0x180019780`
- `0x18001ffa0`
- `0x18002f59c`
- `0x18002f820`
- `0x180030914`
- `0x18003e210`
- `0x18003eca8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002fa1e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002fa1e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002f8c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002f8c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f88f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f923`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f96f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002fad6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f88f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f923`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f96f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002fad6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002f9f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002faa7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002fac1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002f9f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002faa7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002fac1`

## string_xrefs

- `0x18002f8e5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002fa3b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002f864`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18002f900`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18002f943`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18002f9ce`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18002fa80`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(
        StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // rcx
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

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      v19[0]);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v9 = *(_QWORD *)a2;
  v20 = v19;
  *(_QWORD *)v19 = 0;
  v21 = 0;
  v22 = 1;
  v10 = SRCacheContext_Open(v9, L"Application\\Index\\Package", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
LABEL_8:
    v11 = *(_QWORD *)v19;
    *(_QWORD *)v19 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v10;
  }
  if ( !*(_QWORD *)v19 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_13:
    v12 = *(_QWORD *)v19;
    *(_QWORD *)v19 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return v6;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
  if ( v10 < 0 )
  {
    v13 = 1001;
    goto LABEL_17;
  }
  v20 = (int *)this;
  v21 = 0;
  v22 = 1;
  v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v19, v27, 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
    v13 = 1004;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
    v14 = v23;
    v23 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_8;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v15 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v19,
          L"Application\\Index\\Package");
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F2,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v15,
      v19[0]);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_13;
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
0x18002f820  mov     [rsp-8+arg_18], rbx
0x18002f825  push    rbp
0x18002f826  push    rsi
0x18002f827  push    rdi
0x18002f828  push    r14
0x18002f82a  push    r15
0x18002f82c  lea     rbp, [rsp-170h]
0x18002f834  sub     rsp, 270h
0x18002f83b  mov     rax, cs:__security_cookie
0x18002f842  xor     rax, rsp
0x18002f845  mov     [rbp+190h+var_30], rax
0x18002f84c  xor     r15d, r15d
0x18002f84f  mov     r14, r8
0x18002f852  mov     rsi, rdx
0x18002f855  mov     rbx, rcx
0x18002f858  test    r8, r8
0x18002f85b  jnz     short loc_18002F884
0x18002f85d  mov     rcx, [rbp+198h]; this
0x18002f864  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f86b  mov     ebx, 80070057h
0x18002f870  mov     edx, 3DFh; void *
0x18002f875  mov     r9d, ebx; char *
0x18002f878  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f87d  mov     eax, ebx
0x18002f87f  jmp     loc_18002FADE
0x18002f884  mov     rcx, [rcx]
0x18002f887  mov     [rbx], r15
0x18002f88a  test    rcx, rcx
0x18002f88d  jz      short loc_18002F895
0x18002f88f  call    cs:__imp_SRCacheContext_Close
0x18002f895  mov     [rbx+8], r15d
0x18002f899  lea     rax, [rsp+290h+var_270]
0x18002f89e  mov     [rbx+10h], r15
0x18002f8a2  lea     r9, [rsp+290h+var_260]
0x18002f8a7  mov     rcx, [rsi]
0x18002f8aa  lea     rdx, aApplicationInd; "Application\\Index\\Package"
0x18002f8b1  xor     r8d, r8d
0x18002f8b4  mov     [rsp+290h+var_268], rax
0x18002f8b9  mov     qword ptr [rsp+290h+var_270], r15; int
0x18002f8be  mov     [rsp+290h+var_260], r15
0x18002f8c3  mov     [rsp+290h+var_258], 1
0x18002f8c8  call    cs:__imp_SRCacheContext_Open
0x18002f8ce  lea     rcx, [rsp+290h+var_268]
0x18002f8d3  mov     edi, eax
0x18002f8d5  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18002f8da  test    edi, edi
0x18002f8dc  jns     short loc_18002F930
0x18002f8de  mov     rcx, [rbp+198h]; this
0x18002f8e5  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f8ec  mov     r9d, edi; char *
0x18002f8ef  mov     edx, 18Ch; void *
0x18002f8f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f8f9  mov     rcx, [rbp+198h]; this
0x18002f900  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f907  mov     r9d, edi; char *
0x18002f90a  mov     edx, 3E5h; void *
0x18002f90f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f914  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002f919  mov     qword ptr [rsp+290h+var_270], r15
0x18002f91e  test    rcx, rcx
0x18002f921  jz      short loc_18002F929
0x18002f923  call    cs:__imp_SRCacheContext_Close
0x18002f929  mov     eax, edi
0x18002f92b  jmp     loc_18002FADE
0x18002f930  cmp     qword ptr [rsp+290h+var_270], r15
0x18002f935  setnz   al
0x18002f938  test    al, al
0x18002f93a  jnz     short loc_18002F97A
0x18002f93c  mov     rcx, [rbp+198h]; this
0x18002f943  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f94a  mov     ebx, 80670012h
0x18002f94f  mov     edx, 3E6h; void *
0x18002f954  mov     r9d, ebx; char *
0x18002f957  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f95c  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002f961  mov     qword ptr [rsp+290h+var_270], r15
0x18002f966  test    rcx, rcx
0x18002f969  jz      loc_18002F87D
0x18002f96f  call    cs:__imp_SRCacheContext_Close
0x18002f975  jmp     loc_18002F87D
0x18002f97a  xor     edx, edx; Val
0x18002f97c  mov     [rsp+290h+var_250], r15
0x18002f981  mov     r8d, 200h; Size
0x18002f987  lea     rcx, [rsp+290h+var_248]; void *
0x18002f98c  call    memset_0
0x18002f991  lea     rax, [rsp+290h+var_248]
0x18002f996  mov     [rbp+190h+var_48], r15
0x18002f99d  mov     rdx, r14; unsigned __int64
0x18002f9a0  mov     [rbp+190h+var_38], rax
0x18002f9a7  lea     rcx, [rsp+290h+var_250]; this
0x18002f9ac  mov     [rbp+190h+var_40], 100h
0x18002f9b7  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002f9bc  mov     edi, eax
0x18002f9be  test    eax, eax
0x18002f9c0  jns     short loc_18002F9FB
0x18002f9c2  mov     edx, 3E9h; void *
0x18002f9c7  mov     rcx, [rbp+198h]; this
0x18002f9ce  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f9d5  mov     r9d, edi; char *
0x18002f9d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f9dd  mov     rcx, [rsp+290h+var_250]
0x18002f9e2  mov     [rsp+290h+var_250], r15
0x18002f9e7  test    rcx, rcx
0x18002f9ea  jz      loc_18002F914
0x18002f9f0  call    cs:__imp_SRCache_Free
0x18002f9f6  jmp     loc_18002F914
0x18002f9fb  mov     rdx, [rbp+190h+var_38]
0x18002fa02  lea     r9, [rsp+290h+var_260]
0x18002fa07  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002fa0c  xor     r8d, r8d
0x18002fa0f  mov     [rsp+290h+var_268], rbx
0x18002fa14  mov     [rsp+290h+var_260], r15
0x18002fa19  mov     [rsp+290h+var_258], 1
0x18002fa1e  call    cs:__imp_SRCacheContext_OpenSubContext
0x18002fa24  lea     rcx, [rsp+290h+var_268]
0x18002fa29  mov     edi, eax
0x18002fa2b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18002fa30  test    edi, edi
0x18002fa32  jns     short loc_18002FA59
0x18002fa34  mov     rcx, [rbp+198h]; this
0x18002fa3b  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002fa42  mov     r9d, edi; char *
0x18002fa45  mov     edx, 1B0h; void *
0x18002fa4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fa4f  mov     edx, 3ECh
0x18002fa54  jmp     loc_18002F9C7
0x18002fa59  cmp     [rbx], r15
0x18002fa5c  jz      short loc_18002FA62
0x18002fa5e  mov     [rbx+10h], rsi
0x18002fa62  lea     rdx, aApplicationInd; "Application\\Index\\Package"
0x18002fa69  lea     rcx, [rsp+290h+var_270]; this
0x18002fa6e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18002fa73  mov     ebx, eax
0x18002fa75  test    eax, eax
0x18002fa77  jns     short loc_18002FAB2
0x18002fa79  mov     rcx, [rbp+198h]; this
0x18002fa80  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002fa87  mov     r9d, eax; char *
0x18002fa8a  mov     edx, 3F2h; void *
0x18002fa8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fa94  mov     rcx, [rsp+290h+var_250]
0x18002fa99  mov     [rsp+290h+var_250], r15
0x18002fa9e  test    rcx, rcx
0x18002faa1  jz      loc_18002F95C
0x18002faa7  call    cs:__imp_SRCache_Free
0x18002faad  jmp     loc_18002F95C
0x18002fab2  mov     rcx, [rsp+290h+var_250]
0x18002fab7  mov     [rsp+290h+var_250], r15
0x18002fabc  test    rcx, rcx
0x18002fabf  jz      short loc_18002FAC7
0x18002fac1  call    cs:__imp_SRCache_Free
0x18002fac7  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002facc  mov     qword ptr [rsp+290h+var_270], r15
0x18002fad1  test    rcx, rcx
0x18002fad4  jz      short loc_18002FADC
0x18002fad6  call    cs:__imp_SRCacheContext_Close
0x18002fadc  xor     eax, eax
0x18002fade  mov     rcx, [rbp+190h+var_30]
0x18002fae5  xor     rcx, rsp; StackCookie
0x18002fae8  call    __security_check_cookie
0x18002faed  mov     rbx, [rsp+290h+arg_18]
0x18002faf5  add     rsp, 270h
0x18002fafc  pop     r15
0x18002fafe  pop     r14
0x18002fb00  pop     rdi
0x18002fb01  pop     rsi
0x18002fb02  pop     rbp
0x18002fb03  retn
```
