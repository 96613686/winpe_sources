# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)

- ea: `0x180019804`
- end: `0x180019b92`
- name: `?GetActivation@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVActivation_NoThrow@234@AEA_N@Z`
- size: `910`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, struct StateRepository::Cache::Entity::Activation_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180051030`

## callees

- `0x180018be0`
- `0x180019804`
- `0x18001a1f0`
- `0x18001a62c`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180019876`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180019876`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001989a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019950`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800199de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019a0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019b04`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019b35`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019b6b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001989a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019950`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800199de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019a0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019b04`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019b35`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019b6b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001992c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001992c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800199c9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019b20`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800199c9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019b20`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180019974`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180019974`

## string_xrefs

- `0x18001998b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019a81`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019aa6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019a23`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800199ae`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x1800199eb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x180019a5f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x180019ac6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x180019b44`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        struct StateRepository::Cache::Entity::Activation_NoThrow *a3,
        bool *a4)
{
  unsigned __int64 v4; // rsi
  __int64 v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // rdx
  unsigned __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v28; // [rsp+28h] [rbp-D8h] BYREF
  int *v29; // [rsp+30h] [rbp-D0h]
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  char v31; // [rsp+40h] [rbp-C0h]
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v33[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+258h] [rbp+158h]
  __int64 v35; // [rsp+260h] [rbp+160h]
  _BYTE *v36; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v4 = *((_QWORD *)this + 4);
  if ( !v4 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)0x80070057LL,
      v27[0]);
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x360,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)v8,
      v27[0]);
    return v8;
  }
  v28 = 0;
  v29 = v27;
  v7 = *(_QWORD *)a2;
  *(_QWORD *)v27 = 0;
  v30 = 0;
  v31 = 1;
  v8 = SRCacheContext_Open(v7, L"Activation\\Data", 0, &v30);
  if ( v31 )
  {
    v9 = *(_QWORD *)v29;
    *(_QWORD *)v29 = v30;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v8,
      v27[0]);
    v21 = 391;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)v8,
      v27[0]);
    goto LABEL_17;
  }
  if ( !*(_QWORD *)v27 )
  {
    v8 = -2140733422;
    v21 = 392;
    goto LABEL_26;
  }
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  v34 = 0;
  v36 = v33;
  v35 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v32, v4);
  v8 = v10;
  if ( v10 < 0 )
  {
    v16 = (unsigned int)v10;
    v15 = 395;
  }
  else
  {
    v29 = (int *)&v28;
    v30 = 0;
    v31 = 1;
    v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v27, v36, 0, &v30);
    if ( v31 )
    {
      v11 = *(_QWORD *)v29;
      *(_QWORD *)v29 = v30;
      if ( v11 )
        SRCacheContext_Close(v11);
    }
    if ( (v8 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)v8,
        v27[0]);
      v15 = 396;
    }
    else
    {
      v12 = *(_QWORD *)v27;
      *a4 = v28 != 0;
      v13 = SRCacheContext_AddToCache(v12, L"Activation\\Data");
      v8 = v13;
      if ( v13 >= 0 )
      {
        v24 = v32;
        v32 = 0;
        if ( v24 )
          SRCache_Free(v24);
        v25 = *(_QWORD *)v27;
        *(_QWORD *)v27 = 0;
        if ( v25 )
          SRCacheContext_Close(v25);
        if ( *a4 )
        {
          v22 = StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(&v28, (__int64 *)a3, v14, v4);
          v8 = v22;
          if ( v22 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x13F,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
              (const char *)(unsigned int)v22,
              v27[0]);
            v26 = v28;
            v28 = 0;
            if ( v26 )
              SRCacheContext_Close(v26);
            goto LABEL_22;
          }
        }
        v23 = v28;
        v28 = 0;
        if ( v23 )
          SRCacheContext_Close(v23);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v13,
        v27[0]);
      v15 = 398;
    }
    v16 = v8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
    (const char *)v16,
    v27[0]);
  v17 = v32;
  v32 = 0;
  if ( v17 )
    SRCache_Free(v17);
LABEL_17:
  v18 = *(_QWORD *)v27;
  *(_QWORD *)v27 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x13A,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
    (const char *)v8,
    v27[0]);
  v19 = v28;
  v28 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_22;
  return 0;
}

```

## disassembly

```asm
0x180019804  push    rbp
0x180019806  push    rbx
0x180019807  push    rsi
0x180019808  push    rdi
0x180019809  push    r14
0x18001980b  push    r15
0x18001980d  lea     rbp, [rsp-188h]
0x180019815  sub     rsp, 288h
0x18001981c  mov     rax, cs:__security_cookie
0x180019823  xor     rax, rsp
0x180019826  mov     [rbp+1B0h+var_40], rax
0x18001982d  mov     rsi, [rcx+20h]
0x180019831  xor     r15d, r15d
0x180019834  mov     rdi, r9
0x180019837  mov     r14, r8
0x18001983a  mov     rax, rdx
0x18001983d  test    rsi, rsi
0x180019840  jz      loc_180019A58
0x180019846  lea     rcx, [rsp+2B0h+var_290]
0x18001984b  mov     [rsp+2B0h+var_288], r15
0x180019850  mov     [rsp+2B0h+var_280], rcx
0x180019855  lea     r9, [rsp+2B0h+var_278]
0x18001985a  mov     rcx, [rax]
0x18001985d  lea     rdx, aActivationData; "Activation\\Data"
0x180019864  xor     r8d, r8d
0x180019867  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x18001986c  mov     [rsp+2B0h+var_278], r15
0x180019871  mov     [rsp+2B0h+var_270], 1
0x180019876  call    cs:__imp_SRCacheContext_Open
0x18001987c  mov     ebx, eax
0x18001987e  cmp     [rsp+2B0h+var_270], r15b
0x180019883  jz      short loc_1800198A0
0x180019885  mov     rdx, [rsp+2B0h+var_280]
0x18001988a  mov     rax, [rsp+2B0h+var_278]
0x18001988f  mov     rcx, [rdx]
0x180019892  mov     [rdx], rax
0x180019895  test    rcx, rcx
0x180019898  jz      short loc_1800198A0
0x18001989a  call    cs:__imp_SRCacheContext_Close
0x1800198a0  test    ebx, ebx
0x1800198a2  js      loc_180019A9F
0x1800198a8  cmp     qword ptr [rsp+2B0h+var_290], r15
0x1800198ad  setnz   al
0x1800198b0  test    al, al
0x1800198b2  jz      loc_180019B76
0x1800198b8  xor     edx, edx; Val
0x1800198ba  mov     [rsp+2B0h+var_260], r15
0x1800198bf  mov     r8d, 200h; Size
0x1800198c5  lea     rcx, [rsp+2B0h+var_258]; void *
0x1800198ca  call    memset_0
0x1800198cf  lea     rax, [rsp+2B0h+var_258]
0x1800198d4  mov     [rbp+1B0h+var_58], r15
0x1800198db  mov     rdx, rsi; unsigned __int64
0x1800198de  mov     [rbp+1B0h+var_48], rax
0x1800198e5  lea     rcx, [rsp+2B0h+var_260]; this
0x1800198ea  mov     [rbp+1B0h+var_50], 100h
0x1800198f5  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800198fa  mov     ebx, eax
0x1800198fc  test    eax, eax
0x1800198fe  js      loc_180019B85
0x180019904  mov     rdx, [rbp+1B0h+var_48]
0x18001990b  lea     rax, [rsp+2B0h+var_288]
0x180019910  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180019915  lea     r9, [rsp+2B0h+var_278]
0x18001991a  xor     r8d, r8d
0x18001991d  mov     [rsp+2B0h+var_280], rax
0x180019922  mov     [rsp+2B0h+var_278], r15
0x180019927  mov     [rsp+2B0h+var_270], 1
0x18001992c  call    cs:__imp_SRCacheContext_OpenSubContext
0x180019932  mov     ebx, eax
0x180019934  cmp     [rsp+2B0h+var_270], r15b
0x180019939  jz      short loc_180019956
0x18001993b  mov     rdx, [rsp+2B0h+var_280]
0x180019940  mov     rax, [rsp+2B0h+var_278]
0x180019945  mov     rcx, [rdx]
0x180019948  mov     [rdx], rax
0x18001994b  test    rcx, rcx
0x18001994e  jz      short loc_180019956
0x180019950  call    cs:__imp_SRCacheContext_Close
0x180019956  test    ebx, ebx
0x180019958  js      loc_180019A7A
0x18001995e  cmp     [rsp+2B0h+var_288], r15
0x180019963  lea     rdx, aActivationData; "Activation\\Data"
0x18001996a  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001996f  setnz   al
0x180019972  mov     [rdi], al
0x180019974  call    cs:__imp_SRCacheContext_AddToCache
0x18001997a  mov     ebx, eax
0x18001997c  test    eax, eax
0x18001997e  jns     loc_180019B11
0x180019984  mov     rcx, [rbp+1B8h]; this
0x18001998b  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019992  mov     r9d, eax; char *
0x180019995  mov     edx, 1A6h; void *
0x18001999a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001999f  mov     edx, 18Eh; void *
0x1800199a4  mov     r9d, ebx; char *
0x1800199a7  mov     rcx, [rbp+1B8h]; this
0x1800199ae  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800199b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800199ba  mov     rcx, [rsp+2B0h+var_260]
0x1800199bf  mov     [rsp+2B0h+var_260], r15
0x1800199c4  test    rcx, rcx
0x1800199c7  jz      short loc_1800199CF
0x1800199c9  call    cs:__imp_SRCache_Free
0x1800199cf  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800199d4  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x1800199d9  test    rcx, rcx
0x1800199dc  jz      short loc_1800199E4
0x1800199de  call    cs:__imp_SRCacheContext_Close
0x1800199e4  mov     rcx, [rbp+1B8h]; this
0x1800199eb  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800199f2  mov     r9d, ebx; char *
0x1800199f5  mov     edx, 13Ah; void *
0x1800199fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800199ff  mov     rcx, [rsp+2B0h+var_288]
0x180019a04  mov     [rsp+2B0h+var_288], r15
0x180019a09  test    rcx, rcx
0x180019a0c  jz      short loc_180019A14
0x180019a0e  call    cs:__imp_SRCacheContext_Close
0x180019a14  test    ebx, ebx
0x180019a16  jns     loc_180019B0A
0x180019a1c  mov     rcx, [rbp+1B8h]; this
0x180019a23  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019a2a  mov     r9d, ebx; char *
0x180019a2d  mov     edx, 360h; void *
0x180019a32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a37  mov     eax, ebx
0x180019a39  mov     rcx, [rbp+1B0h+var_40]
0x180019a40  xor     rcx, rsp; StackCookie
0x180019a43  call    __security_check_cookie
0x180019a48  add     rsp, 288h
0x180019a4f  pop     r15
0x180019a51  pop     r14
0x180019a53  pop     rdi
0x180019a54  pop     rsi
0x180019a55  pop     rbx
0x180019a56  pop     rbp
0x180019a57  retn
0x180019a58  mov     rcx, [rbp+1B8h]; this
0x180019a5f  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019a66  mov     ebx, 80070057h
0x180019a6b  mov     edx, 137h; void *
0x180019a70  mov     r9d, ebx; char *
0x180019a73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a78  jmp     short loc_180019A1C
0x180019a7a  mov     rcx, [rbp+1B8h]; this
0x180019a81  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019a88  mov     r9d, ebx; char *
0x180019a8b  mov     edx, 1B0h; void *
0x180019a90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a95  mov     edx, 18Ch
0x180019a9a  jmp     loc_1800199A4
0x180019a9f  mov     rcx, [rbp+1B8h]; this
0x180019aa6  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019aad  mov     r9d, ebx; char *
0x180019ab0  mov     edx, 18Ch; void *
0x180019ab5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019aba  mov     edx, 187h; void *
0x180019abf  mov     rcx, [rbp+1B8h]; this
0x180019ac6  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019acd  mov     r9d, ebx; char *
0x180019ad0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ad5  jmp     loc_1800199CF
0x180019ada  cmp     [rdi], r15b
0x180019add  jz      short loc_180019AF5
0x180019adf  mov     r9, rsi
0x180019ae2  lea     rcx, [rsp+2B0h+var_288]
0x180019ae7  mov     rdx, r14
0x180019aea  call    ?ContextToObject@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,__int64)
0x180019aef  mov     ebx, eax
0x180019af1  test    eax, eax
0x180019af3  js      short loc_180019B3D
0x180019af5  mov     rcx, [rsp+2B0h+var_288]
0x180019afa  mov     [rsp+2B0h+var_288], r15
0x180019aff  test    rcx, rcx
0x180019b02  jz      short loc_180019B0A
0x180019b04  call    cs:__imp_SRCacheContext_Close
0x180019b0a  xor     eax, eax
0x180019b0c  jmp     loc_180019A39
0x180019b11  mov     rcx, [rsp+2B0h+var_260]
0x180019b16  mov     [rsp+2B0h+var_260], r15
0x180019b1b  test    rcx, rcx
0x180019b1e  jz      short loc_180019B26
0x180019b20  call    cs:__imp_SRCache_Free
0x180019b26  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180019b2b  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x180019b30  test    rcx, rcx
0x180019b33  jz      short loc_180019ADA
0x180019b35  call    cs:__imp_SRCacheContext_Close
0x180019b3b  jmp     short loc_180019ADA
0x180019b3d  mov     rcx, [rbp+1B8h]; this
0x180019b44  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019b4b  mov     r9d, eax; char *
0x180019b4e  mov     edx, 13Fh; void *
0x180019b53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019b58  mov     rcx, [rsp+2B0h+var_288]
0x180019b5d  mov     [rsp+2B0h+var_288], r15
0x180019b62  test    rcx, rcx
0x180019b65  jz      loc_180019A1C
0x180019b6b  call    cs:__imp_SRCacheContext_Close
0x180019b71  jmp     loc_180019A1C
0x180019b76  mov     ebx, 80670012h
0x180019b7b  mov     edx, 188h
0x180019b80  jmp     loc_180019ABF
0x180019b85  mov     r9d, eax
0x180019b88  mov     edx, 18Bh
0x180019b8d  jmp     loc_1800199A7
```
