# StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)

- ea: `0x180019430`
- end: `0x1800197fc`
- name: `?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z`
- size: `972`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180051030`

## callees

- `0x180018be0`
- `0x180019430`
- `0x180019b98`
- `0x18001a1f0`
- `0x18004b094`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180019483`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180019483`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800194d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800194d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800194f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800195af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800196ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800196fe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019772`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800197a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800197d3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800194f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800195af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800196ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800196fe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019772`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800197a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800197d3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001958b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001958b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800196b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001978c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800196b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001978c`

## string_xrefs

- `0x180019622`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019677`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019710`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001963d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18001965d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18001969a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800196d7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180019730`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800197b0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800194bc`: `ApplicationExtension\Data`
- `0x1800195c2`: `ApplicationExtension\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(
        __int64 *a1,
        __int64 a2,
        __int64 *a3,
        bool *a4)
{
  __int64 v6; // rcx
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // ebx
  unsigned __int64 v11; // rdi
  __int64 *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rdx
  unsigned __int64 v19; // r9
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rdx
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v32; // [rsp+28h] [rbp-D8h] BYREF
  int *v33; // [rsp+30h] [rbp-D0h]
  __int64 v34; // [rsp+38h] [rbp-C8h] BYREF
  char v35; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v36; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v38[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+258h] [rbp+158h]
  __int64 v40; // [rsp+260h] [rbp+160h]
  _BYTE *v41; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  v6 = *a1;
  if ( !v6 )
    return 0;
  v8 = *((unsigned int *)a1 + 2);
  v36 = 0;
  v9 = SRCacheContext_EnumerateData(v6, v8, &v36);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = v36;
    if ( v36 )
    {
      v12 = (__int64 *)a1[2];
      v32 = 0;
      *(_QWORD *)v31 = 0;
      v33 = v31;
      v13 = *v12;
      v34 = 0;
      v35 = 1;
      v10 = SRCacheContext_Open(v13, L"ApplicationExtension\\Data", 0, &v34);
      if ( v35 )
      {
        v14 = *(_QWORD *)v33;
        *(_QWORD *)v33 = v34;
        if ( v14 )
          SRCacheContext_Close(v14);
      }
      if ( (v10 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18C,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)v10,
          v31[0]);
        v25 = 364;
      }
      else
      {
        if ( *(_QWORD *)v31 )
        {
          v37 = 0;
          memset_0(v38, 0, sizeof(v38));
          v39 = 0;
          v41 = v38;
          v40 = 256;
          v15 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v37, v11);
          v10 = v15;
          if ( v15 < 0 )
          {
            v18 = 368;
          }
          else
          {
            v33 = (int *)&v32;
            v34 = 0;
            v35 = 1;
            v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v31, v41, 0, &v34);
            if ( v35 )
            {
              v16 = *(_QWORD *)v33;
              *(_QWORD *)v33 = v34;
              if ( v16 )
                SRCacheContext_Close(v16);
            }
            if ( (v10 & 0x80000000) != 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1B0,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
                (const char *)v10,
                v31[0]);
              v19 = v10;
              v18 = 369;
LABEL_22:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v18,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
                (const char *)v19,
                v31[0]);
              v22 = v37;
              v37 = 0;
              if ( v22 )
                SRCache_Free(v22);
LABEL_24:
              v23 = *(_QWORD *)v31;
              *(_QWORD *)v31 = 0;
              if ( v23 )
                SRCacheContext_Close(v23);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x145,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
                (const char *)v10,
                v31[0]);
              v24 = v32;
              v32 = 0;
              if ( v24 )
                SRCacheContext_Close(v24);
              if ( (v10 & 0x80000000) == 0 )
                return 0;
              goto LABEL_40;
            }
            *a4 = v32 != 0;
            v15 = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)v31,
                    L"ApplicationExtension\\Data");
            v10 = v15;
            if ( v15 >= 0 )
            {
              v28 = v37;
              v37 = 0;
              if ( v28 )
                SRCache_Free(v28);
              v29 = *(_QWORD *)v31;
              *(_QWORD *)v31 = 0;
              if ( v29 )
                SRCacheContext_Close(v29);
              if ( !*a4
                || (v26 = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(
                            &v32,
                            a3,
                            v17,
                            v11),
                    v10 = v26,
                    v26 >= 0) )
              {
                v27 = v32;
                v32 = 0;
                if ( v27 )
                  SRCacheContext_Close(v27);
                return 0;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x14A,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
                (const char *)(unsigned int)v26,
                v31[0]);
              v30 = v32;
              v32 = 0;
              if ( v30 )
                SRCacheContext_Close(v30);
LABEL_40:
              v21 = 689;
              goto LABEL_20;
            }
            v18 = 371;
          }
          v19 = (unsigned int)v15;
          goto LABEL_22;
        }
        v10 = -2140733422;
        v25 = 365;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
        (const char *)v10,
        v31[0]);
      goto LABEL_24;
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A6,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
    (const char *)(unsigned int)v9,
    v31[0]);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x294,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
    (const char *)v10,
    v31[0]);
  v21 = 684;
LABEL_20:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v21,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
    (const char *)v10,
    v31[0]);
  return v10;
}

```

## disassembly

```asm
0x180019430  push    rbp
0x180019432  push    rbx
0x180019433  push    rsi
0x180019434  push    rdi
0x180019435  push    r12
0x180019437  push    r14
0x180019439  push    r15
0x18001943b  lea     rbp, [rsp-180h]
0x180019443  sub     rsp, 280h
0x18001944a  mov     rax, cs:__security_cookie
0x180019451  xor     rax, rsp
0x180019454  mov     [rbp+1B0h+var_40], rax
0x18001945b  xor     r12d, r12d
0x18001945e  mov     rsi, rcx
0x180019461  mov     [r9], r12b
0x180019464  mov     r14, r9
0x180019467  mov     rcx, [rcx]
0x18001946a  mov     r15, r8
0x18001946d  test    rcx, rcx
0x180019470  jz      loc_1800195F8
0x180019476  mov     edx, [rsi+8]
0x180019479  lea     r8, [rsp+2B0h+var_268]
0x18001947e  mov     [rsp+2B0h+var_268], r12
0x180019483  call    cs:__imp_SRCacheContext_EnumerateData
0x180019489  mov     ebx, eax
0x18001948b  test    eax, eax
0x18001948d  js      loc_18001961B
0x180019493  mov     rdi, [rsp+2B0h+var_268]
0x180019498  test    rdi, rdi
0x18001949b  jz      loc_1800195F8
0x1800194a1  mov     rcx, [rsi+10h]
0x1800194a5  lea     rax, [rsp+2B0h+var_290]
0x1800194aa  lea     r9, [rsp+2B0h+var_278]
0x1800194af  mov     [rsp+2B0h+var_288], r12
0x1800194b4  xor     r8d, r8d
0x1800194b7  mov     qword ptr [rsp+2B0h+var_290], r12; int
0x1800194bc  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x1800194c3  mov     [rsp+2B0h+var_280], rax
0x1800194c8  mov     rcx, [rcx]
0x1800194cb  mov     [rsp+2B0h+var_278], r12
0x1800194d0  mov     [rsp+2B0h+var_270], 1
0x1800194d5  call    cs:__imp_SRCacheContext_Open
0x1800194db  mov     ebx, eax
0x1800194dd  cmp     [rsp+2B0h+var_270], r12b
0x1800194e2  jz      short loc_1800194FF
0x1800194e4  mov     rdx, [rsp+2B0h+var_280]
0x1800194e9  mov     rax, [rsp+2B0h+var_278]
0x1800194ee  mov     rcx, [rdx]
0x1800194f1  mov     [rdx], rax
0x1800194f4  test    rcx, rcx
0x1800194f7  jz      short loc_1800194FF
0x1800194f9  call    cs:__imp_SRCacheContext_Close
0x1800194ff  test    ebx, ebx
0x180019501  js      loc_180019709
0x180019507  cmp     qword ptr [rsp+2B0h+var_290], r12
0x18001950c  setnz   al
0x18001950f  test    al, al
0x180019511  jz      loc_1800197E3
0x180019517  xor     edx, edx; Val
0x180019519  mov     [rsp+2B0h+var_260], r12
0x18001951e  mov     r8d, 200h; Size
0x180019524  lea     rcx, [rsp+2B0h+var_258]; void *
0x180019529  call    memset_0
0x18001952e  lea     rax, [rsp+2B0h+var_258]
0x180019533  mov     [rbp+1B0h+var_58], r12
0x18001953a  mov     rdx, rdi; unsigned __int64
0x18001953d  mov     [rbp+1B0h+var_48], rax
0x180019544  lea     rcx, [rsp+2B0h+var_260]; this
0x180019549  mov     [rbp+1B0h+var_50], 100h
0x180019554  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180019559  mov     ebx, eax
0x18001955b  test    eax, eax
0x18001955d  js      loc_1800197F2
0x180019563  mov     rdx, [rbp+1B0h+var_48]
0x18001956a  lea     rax, [rsp+2B0h+var_288]
0x18001956f  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180019574  lea     r9, [rsp+2B0h+var_278]
0x180019579  xor     r8d, r8d
0x18001957c  mov     [rsp+2B0h+var_280], rax
0x180019581  mov     [rsp+2B0h+var_278], r12
0x180019586  mov     [rsp+2B0h+var_270], 1
0x18001958b  call    cs:__imp_SRCacheContext_OpenSubContext
0x180019591  mov     ebx, eax
0x180019593  cmp     [rsp+2B0h+var_270], r12b
0x180019598  jz      short loc_1800195B5
0x18001959a  mov     rdx, [rsp+2B0h+var_280]
0x18001959f  mov     rax, [rsp+2B0h+var_278]
0x1800195a4  mov     rcx, [rdx]
0x1800195a7  mov     [rdx], rax
0x1800195aa  test    rcx, rcx
0x1800195ad  jz      short loc_1800195B5
0x1800195af  call    cs:__imp_SRCacheContext_Close
0x1800195b5  test    ebx, ebx
0x1800195b7  js      loc_180019670
0x1800195bd  cmp     [rsp+2B0h+var_288], r12
0x1800195c2  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x1800195c9  lea     rcx, [rsp+2B0h+var_290]; this
0x1800195ce  setnz   al
0x1800195d1  mov     [r14], al
0x1800195d4  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800195d9  mov     ebx, eax
0x1800195db  test    eax, eax
0x1800195dd  jns     loc_18001977D
0x1800195e3  mov     edx, 173h
0x1800195e8  mov     r9d, eax
0x1800195eb  jmp     loc_180019693
0x1800195f0  test    ebx, ebx
0x1800195f2  js      loc_1800197D9
0x1800195f8  xor     eax, eax
0x1800195fa  mov     rcx, [rbp+1B0h+var_40]
0x180019601  xor     rcx, rsp; StackCookie
0x180019604  call    __security_check_cookie
0x180019609  add     rsp, 280h
0x180019610  pop     r15
0x180019612  pop     r14
0x180019614  pop     r12
0x180019616  pop     rdi
0x180019617  pop     rsi
0x180019618  pop     rbx
0x180019619  pop     rbp
0x18001961a  retn
0x18001961b  mov     rcx, [rbp+1B8h]; this
0x180019622  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019629  mov     r9d, ebx; char *
0x18001962c  mov     edx, 2A6h; void *
0x180019631  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019636  mov     rcx, [rbp+1B8h]; this
0x18001963d  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019644  mov     r9d, ebx; char *
0x180019647  mov     edx, 294h; void *
0x18001964c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019651  mov     edx, 2ACh; void *
0x180019656  mov     rcx, [rbp+1B8h]; this
0x18001965d  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019664  mov     r9d, ebx; char *
0x180019667  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001966c  mov     eax, ebx
0x18001966e  jmp     short loc_1800195FA
0x180019670  mov     rcx, [rbp+1B8h]; this
0x180019677  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001967e  mov     r9d, ebx; char *
0x180019681  mov     edx, 1B0h; void *
0x180019686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001968b  mov     r9d, ebx; char *
0x18001968e  mov     edx, 171h; void *
0x180019693  mov     rcx, [rbp+1B8h]; this
0x18001969a  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800196a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800196a6  mov     rcx, [rsp+2B0h+var_260]
0x1800196ab  mov     [rsp+2B0h+var_260], r12
0x1800196b0  test    rcx, rcx
0x1800196b3  jz      short loc_1800196BB
0x1800196b5  call    cs:__imp_SRCache_Free
0x1800196bb  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800196c0  mov     qword ptr [rsp+2B0h+var_290], r12; int
0x1800196c5  test    rcx, rcx
0x1800196c8  jz      short loc_1800196D0
0x1800196ca  call    cs:__imp_SRCacheContext_Close
0x1800196d0  mov     rcx, [rbp+1B8h]; this
0x1800196d7  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800196de  mov     r9d, ebx; char *
0x1800196e1  mov     edx, 145h; void *
0x1800196e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800196eb  mov     rcx, [rsp+2B0h+var_288]
0x1800196f0  mov     [rsp+2B0h+var_288], r12
0x1800196f5  test    rcx, rcx
0x1800196f8  jz      loc_1800195F0
0x1800196fe  call    cs:__imp_SRCacheContext_Close
0x180019704  jmp     loc_1800195F0
0x180019709  mov     rcx, [rbp+1B8h]; this
0x180019710  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019717  mov     r9d, ebx; char *
0x18001971a  mov     edx, 18Ch; void *
0x18001971f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019724  mov     edx, 16Ch; void *
0x180019729  mov     rcx, [rbp+1B8h]; this
0x180019730  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019737  mov     r9d, ebx; char *
0x18001973a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001973f  jmp     loc_1800196BB
0x180019744  cmp     [r14], r12b
0x180019747  jz      short loc_18001975F
0x180019749  mov     r9, rdi
0x18001974c  lea     rcx, [rsp+2B0h+var_288]
0x180019751  mov     rdx, r15
0x180019754  call    ?ContextToObject@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,__int64)
0x180019759  mov     ebx, eax
0x18001975b  test    eax, eax
0x18001975d  js      short loc_1800197A9
0x18001975f  mov     rcx, [rsp+2B0h+var_288]
0x180019764  mov     [rsp+2B0h+var_288], r12
0x180019769  test    rcx, rcx
0x18001976c  jz      loc_1800195F8
0x180019772  call    cs:__imp_SRCacheContext_Close
0x180019778  jmp     loc_1800195F8
0x18001977d  mov     rcx, [rsp+2B0h+var_260]
0x180019782  mov     [rsp+2B0h+var_260], r12
0x180019787  test    rcx, rcx
0x18001978a  jz      short loc_180019792
0x18001978c  call    cs:__imp_SRCache_Free
0x180019792  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180019797  mov     qword ptr [rsp+2B0h+var_290], r12; int
0x18001979c  test    rcx, rcx
0x18001979f  jz      short loc_180019744
0x1800197a1  call    cs:__imp_SRCacheContext_Close
0x1800197a7  jmp     short loc_180019744
0x1800197a9  mov     rcx, [rbp+1B8h]; this
0x1800197b0  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800197b7  mov     r9d, eax; char *
0x1800197ba  mov     edx, 14Ah; void *
0x1800197bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800197c4  mov     rcx, [rsp+2B0h+var_288]
0x1800197c9  mov     [rsp+2B0h+var_288], r12
0x1800197ce  test    rcx, rcx
0x1800197d1  jz      short loc_1800197D9
0x1800197d3  call    cs:__imp_SRCacheContext_Close
0x1800197d9  mov     edx, 2B1h
0x1800197de  jmp     loc_180019656
0x1800197e3  mov     ebx, 80670012h
0x1800197e8  mov     edx, 16Dh
0x1800197ed  jmp     loc_180019729
0x1800197f2  mov     edx, 170h
0x1800197f7  jmp     loc_1800195E8
```
