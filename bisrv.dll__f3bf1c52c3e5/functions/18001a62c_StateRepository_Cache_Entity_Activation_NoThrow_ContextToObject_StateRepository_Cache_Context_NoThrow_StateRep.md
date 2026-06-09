# StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,__int64)

- ea: `0x18001a62c`
- end: `0x18001aa04`
- name: `?ContextToObject@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180019804`

## callees

- `0x18001a1f0`
- `0x18001a62c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a6a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a748`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a7a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a7f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a850`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a8a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a8fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a6a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a748`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a7a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a7f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a850`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a8a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a8fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18001a6bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18001a6bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a66a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a71c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a774`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a7cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a824`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a87c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a8d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a66a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a71c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a774`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a7cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a824`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a87c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18001a8d4`

## string_xrefs

- `0x18001a670`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001a6e8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rcx
  int Field_String; // eax
  int v9; // ebx
  __int64 v10; // rcx
  int Field_UInt32; // eax
  __int64 v12; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  __int64 *v32; // [rsp+20h] [rbp-28h]
  __int64 v33; // [rsp+28h] [rbp-20h] BYREF
  char v34; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  v34 = 1;
  v32 = a2 + 1;
  v6 = *a1;
  v33 = 0;
  Field_String = SRCacheContext_GetField_String(v6, L"ActivationKey", &v33);
  v9 = Field_String;
  if ( Field_String < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v32);
  else
    v9 = 0;
  if ( v34 )
  {
    v10 = *v32;
    *v32 = v33;
    if ( v10 )
      SRCache_Free(v10);
  }
  if ( v9 < 0 )
  {
    v12 = 917;
    goto LABEL_9;
  }
  Field_UInt32 = SRCacheContext_GetField_UInt32(*a1, L"Flags", a2 + 2);
  v9 = Field_UInt32;
  if ( Field_UInt32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt32,
      (int)v32);
    v12 = 921;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v9,
      (int)v32);
    return (unsigned int)v9;
  }
  v14 = *a1;
  v32 = a2 + 3;
  v33 = 0;
  v34 = 1;
  v15 = SRCacheContext_GetField_String(v14, L"HostId", &v33);
  v9 = v15;
  if ( v15 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v15,
      (int)v32);
  else
    v9 = 0;
  if ( v34 )
  {
    v16 = *v32;
    *v32 = v33;
    if ( v16 )
      SRCache_Free(v16);
  }
  if ( v9 < 0 )
  {
    v12 = 925;
    goto LABEL_9;
  }
  v17 = *a1;
  v32 = a2 + 4;
  v33 = 0;
  v34 = 1;
  v18 = SRCacheContext_GetField_String(v17, L"Executable", &v33);
  v9 = v18;
  if ( v18 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v18,
      (int)v32);
  else
    v9 = 0;
  if ( v34 )
  {
    v19 = *v32;
    *v32 = v33;
    if ( v19 )
      SRCache_Free(v19);
  }
  if ( v9 < 0 )
  {
    v12 = 929;
    goto LABEL_9;
  }
  v20 = *a1;
  v32 = a2 + 5;
  v33 = 0;
  v34 = 1;
  v21 = SRCacheContext_GetField_String(v20, L"Entrypoint", &v33);
  v9 = v21;
  if ( v21 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v21,
      (int)v32);
  else
    v9 = 0;
  if ( v34 )
  {
    v22 = *v32;
    *v32 = v33;
    if ( v22 )
      SRCache_Free(v22);
  }
  if ( v9 < 0 )
  {
    v12 = 933;
    goto LABEL_9;
  }
  v23 = *a1;
  v32 = a2 + 6;
  v33 = 0;
  v34 = 1;
  v24 = SRCacheContext_GetField_String(v23, L"RuntimeType", &v33);
  v9 = v24;
  if ( v24 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v24,
      (int)v32);
  else
    v9 = 0;
  if ( v34 )
  {
    v25 = *v32;
    *v32 = v33;
    if ( v25 )
      SRCache_Free(v25);
  }
  if ( v9 < 0 )
  {
    v12 = 937;
    goto LABEL_9;
  }
  v26 = *a1;
  v32 = a2 + 7;
  v33 = 0;
  v34 = 1;
  v27 = SRCacheContext_GetField_String(v26, L"StartPage", &v33);
  v9 = v27;
  if ( v27 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v27,
      (int)v32);
  else
    v9 = 0;
  if ( v34 )
  {
    v28 = *v32;
    *v32 = v33;
    if ( v28 )
      SRCache_Free(v28);
  }
  if ( v9 < 0 )
  {
    v12 = 941;
    goto LABEL_9;
  }
  v29 = *a1;
  v32 = a2 + 8;
  v33 = 0;
  v34 = 1;
  v30 = SRCacheContext_GetField_String(v29, L"ResourceGroup", &v33);
  v9 = v30;
  if ( v30 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v30,
      (int)v32);
  else
    v9 = 0;
  if ( v34 )
  {
    v31 = *v32;
    *v32 = v33;
    if ( v31 )
      SRCache_Free(v31);
  }
  if ( v9 < 0 )
  {
    v12 = 945;
    goto LABEL_9;
  }
  *a2 = a4;
  return 0;
}

```

## disassembly

```asm
0x18001a62c  push    rbp
0x18001a62e  push    rbx
0x18001a62f  push    rsi
0x18001a630  push    rdi
0x18001a631  push    r12
0x18001a633  push    r13
0x18001a635  push    r14
0x18001a637  push    r15
0x18001a639  mov     rbp, rsp
0x18001a63c  sub     rsp, 48h
0x18001a640  lea     rax, [rdx+8]
0x18001a644  mov     [rbp+var_18], 1
0x18001a648  mov     rdi, rdx
0x18001a64b  mov     [rbp+var_28], rax
0x18001a64f  mov     rsi, rcx
0x18001a652  lea     rdx, aActivationkey; "ActivationKey"
0x18001a659  mov     rcx, [rcx]
0x18001a65c  lea     r8, [rbp+var_20]
0x18001a660  xor     r15d, r15d
0x18001a663  mov     r14, r9
0x18001a666  mov     [rbp+var_20], r15
0x18001a66a  call    cs:__imp_SRCacheContext_GetField_String
0x18001a670  lea     r12, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a677  mov     r13d, 246h
0x18001a67d  mov     ebx, eax
0x18001a67f  test    eax, eax
0x18001a681  js      loc_18001A94B
0x18001a687  mov     ebx, r15d
0x18001a68a  cmp     [rbp+var_18], r15b
0x18001a68e  jz      short loc_18001A6A9
0x18001a690  mov     rdx, [rbp+var_28]
0x18001a694  mov     rax, [rbp+var_20]
0x18001a698  mov     rcx, [rdx]
0x18001a69b  mov     [rdx], rax
0x18001a69e  test    rcx, rcx
0x18001a6a1  jz      short loc_18001A6A9
0x18001a6a3  call    cs:__imp_SRCache_Free
0x18001a6a9  test    ebx, ebx
0x18001a6ab  js      loc_18001A9C8
0x18001a6b1  mov     rcx, [rsi]
0x18001a6b4  lea     r8, [rdi+10h]
0x18001a6b8  lea     rdx, aFlags; "Flags"
0x18001a6bf  call    cs:__imp_SRCacheContext_GetField_UInt32
0x18001a6c5  mov     ebx, eax
0x18001a6c7  test    eax, eax
0x18001a6c9  jns     short loc_18001A6FE
0x18001a6cb  mov     rcx, [rbp+40h]; this
0x18001a6cf  mov     r9d, eax; char *
0x18001a6d2  mov     r8, r12; unsigned int
0x18001a6d5  mov     edx, 221h; void *
0x18001a6da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a6df  mov     edx, 399h; void *
0x18001a6e4  mov     rcx, [rbp+40h]; this
0x18001a6e8  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a6ef  mov     r9d, ebx; char *
0x18001a6f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a6f7  mov     eax, ebx
0x18001a6f9  jmp     loc_18001A90F
0x18001a6fe  mov     rcx, [rsi]
0x18001a701  lea     rax, [rdi+18h]
0x18001a705  lea     r8, [rbp+var_20]
0x18001a709  mov     [rbp+var_28], rax
0x18001a70d  lea     rdx, aHostid; "HostId"
0x18001a714  mov     [rbp+var_20], r15
0x18001a718  mov     [rbp+var_18], 1
0x18001a71c  call    cs:__imp_SRCacheContext_GetField_String
0x18001a722  mov     ebx, eax
0x18001a724  test    eax, eax
0x18001a726  js      loc_18001A962
0x18001a72c  mov     ebx, r15d
0x18001a72f  cmp     [rbp+var_18], r15b
0x18001a733  jz      short loc_18001A74E
0x18001a735  mov     rdx, [rbp+var_28]
0x18001a739  mov     rax, [rbp+var_20]
0x18001a73d  mov     rcx, [rdx]
0x18001a740  mov     [rdx], rax
0x18001a743  test    rcx, rcx
0x18001a746  jz      short loc_18001A74E
0x18001a748  call    cs:__imp_SRCache_Free
0x18001a74e  test    ebx, ebx
0x18001a750  js      loc_18001A9D2
0x18001a756  mov     rcx, [rsi]
0x18001a759  lea     rax, [rdi+20h]
0x18001a75d  lea     r8, [rbp+var_20]
0x18001a761  mov     [rbp+var_28], rax
0x18001a765  lea     rdx, aExecutable; "Executable"
0x18001a76c  mov     [rbp+var_20], r15
0x18001a770  mov     [rbp+var_18], 1
0x18001a774  call    cs:__imp_SRCacheContext_GetField_String
0x18001a77a  mov     ebx, eax
0x18001a77c  test    eax, eax
0x18001a77e  js      loc_18001A979
0x18001a784  mov     ebx, r15d
0x18001a787  cmp     [rbp+var_18], r15b
0x18001a78b  jz      short loc_18001A7A6
0x18001a78d  mov     rdx, [rbp+var_28]
0x18001a791  mov     rax, [rbp+var_20]
0x18001a795  mov     rcx, [rdx]
0x18001a798  mov     [rdx], rax
0x18001a79b  test    rcx, rcx
0x18001a79e  jz      short loc_18001A7A6
0x18001a7a0  call    cs:__imp_SRCache_Free
0x18001a7a6  test    ebx, ebx
0x18001a7a8  js      loc_18001A9BE
0x18001a7ae  mov     rcx, [rsi]
0x18001a7b1  lea     rax, [rdi+28h]
0x18001a7b5  lea     r8, [rbp+var_20]
0x18001a7b9  mov     [rbp+var_28], rax
0x18001a7bd  lea     rdx, aEntrypoint; "Entrypoint"
0x18001a7c4  mov     [rbp+var_20], r15
0x18001a7c8  mov     [rbp+var_18], 1
0x18001a7cc  call    cs:__imp_SRCacheContext_GetField_String
0x18001a7d2  mov     ebx, eax
0x18001a7d4  test    eax, eax
0x18001a7d6  js      loc_18001A920
0x18001a7dc  mov     ebx, r15d
0x18001a7df  cmp     [rbp+var_18], r15b
0x18001a7e3  jz      short loc_18001A7FE
0x18001a7e5  mov     rdx, [rbp+var_28]
0x18001a7e9  mov     rax, [rbp+var_20]
0x18001a7ed  mov     rcx, [rdx]
0x18001a7f0  mov     [rdx], rax
0x18001a7f3  test    rcx, rcx
0x18001a7f6  jz      short loc_18001A7FE
0x18001a7f8  call    cs:__imp_SRCache_Free
0x18001a7fe  test    ebx, ebx
0x18001a800  js      loc_18001A9DC
0x18001a806  mov     rcx, [rsi]
0x18001a809  lea     rax, [rdi+30h]
0x18001a80d  lea     r8, [rbp+var_20]
0x18001a811  mov     [rbp+var_28], rax
0x18001a815  lea     rdx, aRuntimetype; "RuntimeType"
0x18001a81c  mov     [rbp+var_20], r15
0x18001a820  mov     [rbp+var_18], 1
0x18001a824  call    cs:__imp_SRCacheContext_GetField_String
0x18001a82a  mov     ebx, eax
0x18001a82c  test    eax, eax
0x18001a82e  js      loc_18001A9A7
0x18001a834  mov     ebx, r15d
0x18001a837  cmp     [rbp+var_18], r15b
0x18001a83b  jz      short loc_18001A856
0x18001a83d  mov     rdx, [rbp+var_28]
0x18001a841  mov     rax, [rbp+var_20]
0x18001a845  mov     rcx, [rdx]
0x18001a848  mov     [rdx], rax
0x18001a84b  test    rcx, rcx
0x18001a84e  jz      short loc_18001A856
0x18001a850  call    cs:__imp_SRCache_Free
0x18001a856  test    ebx, ebx
0x18001a858  js      loc_18001A9E6
0x18001a85e  mov     rcx, [rsi]
0x18001a861  lea     rax, [rdi+38h]
0x18001a865  lea     r8, [rbp+var_20]
0x18001a869  mov     [rbp+var_28], rax
0x18001a86d  lea     rdx, aStartpage; "StartPage"
0x18001a874  mov     [rbp+var_20], r15
0x18001a878  mov     [rbp+var_18], 1
0x18001a87c  call    cs:__imp_SRCacheContext_GetField_String
0x18001a882  mov     ebx, eax
0x18001a884  test    eax, eax
0x18001a886  js      loc_18001A990
0x18001a88c  mov     ebx, r15d
0x18001a88f  cmp     [rbp+var_18], r15b
0x18001a893  jz      short loc_18001A8AE
0x18001a895  mov     rdx, [rbp+var_28]
0x18001a899  mov     rax, [rbp+var_20]
0x18001a89d  mov     rcx, [rdx]
0x18001a8a0  mov     [rdx], rax
0x18001a8a3  test    rcx, rcx
0x18001a8a6  jz      short loc_18001A8AE
0x18001a8a8  call    cs:__imp_SRCache_Free
0x18001a8ae  test    ebx, ebx
0x18001a8b0  js      loc_18001A9F0
0x18001a8b6  mov     rcx, [rsi]
0x18001a8b9  lea     rax, [rdi+40h]
0x18001a8bd  lea     r8, [rbp+var_20]
0x18001a8c1  mov     [rbp+var_28], rax
0x18001a8c5  lea     rdx, aResourcegroup; "ResourceGroup"
0x18001a8cc  mov     [rbp+var_20], r15
0x18001a8d0  mov     [rbp+var_18], 1
0x18001a8d4  call    cs:__imp_SRCacheContext_GetField_String
0x18001a8da  mov     ebx, eax
0x18001a8dc  test    eax, eax
0x18001a8de  js      short loc_18001A937
0x18001a8e0  mov     ebx, r15d
0x18001a8e3  cmp     [rbp+var_18], r15b
0x18001a8e7  jz      short loc_18001A902
0x18001a8e9  mov     rdx, [rbp+var_28]
0x18001a8ed  mov     rax, [rbp+var_20]
0x18001a8f1  mov     rcx, [rdx]
0x18001a8f4  mov     [rdx], rax
0x18001a8f7  test    rcx, rcx
0x18001a8fa  jz      short loc_18001A902
0x18001a8fc  call    cs:__imp_SRCache_Free
0x18001a902  test    ebx, ebx
0x18001a904  js      loc_18001A9FA
0x18001a90a  mov     [rdi], r14
0x18001a90d  xor     eax, eax
0x18001a90f  add     rsp, 48h
0x18001a913  pop     r15
0x18001a915  pop     r14
0x18001a917  pop     r13
0x18001a919  pop     r12
0x18001a91b  pop     rdi
0x18001a91c  pop     rsi
0x18001a91d  pop     rbx
0x18001a91e  pop     rbp
0x18001a91f  retn
0x18001a920  mov     rcx, [rbp+40h]; this
0x18001a924  mov     r9d, eax; char *
0x18001a927  mov     r8, r12; unsigned int
0x18001a92a  mov     edx, r13d; void *
0x18001a92d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a932  jmp     loc_18001A7DF
0x18001a937  mov     rcx, [rbp+40h]; this
0x18001a93b  mov     r9d, eax; char *
0x18001a93e  mov     r8, r12; unsigned int
0x18001a941  mov     edx, r13d; void *
0x18001a944  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a949  jmp     short loc_18001A8E3
0x18001a94b  mov     rcx, [rbp+40h]; this
0x18001a94f  mov     r9d, eax; char *
0x18001a952  mov     r8, r12; unsigned int
0x18001a955  mov     edx, r13d; void *
0x18001a958  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a95d  jmp     loc_18001A68A
0x18001a962  mov     rcx, [rbp+40h]; this
0x18001a966  mov     r9d, eax; char *
0x18001a969  mov     r8, r12; unsigned int
0x18001a96c  mov     edx, r13d; void *
0x18001a96f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a974  jmp     loc_18001A72F
0x18001a979  mov     rcx, [rbp+40h]; this
0x18001a97d  mov     r9d, eax; char *
0x18001a980  mov     r8, r12; unsigned int
0x18001a983  mov     edx, r13d; void *
0x18001a986  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a98b  jmp     loc_18001A787
0x18001a990  mov     rcx, [rbp+40h]; this
0x18001a994  mov     r9d, eax; char *
0x18001a997  mov     r8, r12; unsigned int
0x18001a99a  mov     edx, r13d; void *
0x18001a99d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a9a2  jmp     loc_18001A88F
0x18001a9a7  mov     rcx, [rbp+40h]; this
0x18001a9ab  mov     r9d, eax; char *
0x18001a9ae  mov     r8, r12; unsigned int
0x18001a9b1  mov     edx, r13d; void *
0x18001a9b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a9b9  jmp     loc_18001A837
0x18001a9be  mov     edx, 3A1h
0x18001a9c3  jmp     loc_18001A6E4
0x18001a9c8  mov     edx, 395h
0x18001a9cd  jmp     loc_18001A6E4
0x18001a9d2  mov     edx, 39Dh
0x18001a9d7  jmp     loc_18001A6E4
0x18001a9dc  mov     edx, 3A5h
0x18001a9e1  jmp     loc_18001A6E4
0x18001a9e6  mov     edx, 3A9h
0x18001a9eb  jmp     loc_18001A6E4
0x18001a9f0  mov     edx, 3ADh
0x18001a9f5  jmp     loc_18001A6E4
0x18001a9fa  mov     edx, 3B1h
0x18001a9ff  jmp     loc_18001A6E4
```
