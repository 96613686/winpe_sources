# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x180019694`
- end: `0x1800199a3`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `783`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180018748`
- `0x180019588`

## callees

- `0x180019694`
- `0x18001a140`
- `0x18002c8d0`
- `0x1800862f0`
- `0x180086f7c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019843`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800198a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019843`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800198a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019716`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800197d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001982e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019858`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800198bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001990d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019716`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800197d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001982e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019858`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800198bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001990d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800196f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800196f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x1800197f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x1800197f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800197ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800197ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001980f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001980f`

## string_xrefs

- `0x180019884`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800198d7`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800198ef`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18001991c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001993e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019960`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019985`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  int v25[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  int *v27; // [rsp+30h] [rbp-D0h]
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  char v29; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+258h] [rbp+158h]
  __int64 v33; // [rsp+260h] [rbp+160h]
  _BYTE *v34; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v29 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v25 = 0;
  v27 = v25;
  v28 = 0;
  v6 = SRCacheContext_Open(v3, L"Package\\Index\\PackageFullName", 0, &v28);
  if ( v29 )
  {
    v7 = v28;
    v8 = *(_QWORD *)v27;
    *(_QWORD *)v27 = v28;
    if ( v8 )
      SRCacheContext_Close(v8, v7);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v25[0]);
    v22 = 1128;
    goto LABEL_28;
  }
  if ( !*(_QWORD *)v25 )
  {
    v6 = -2140733422;
    v22 = 1129;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)v6,
      v25[0]);
    goto LABEL_24;
  }
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v32 = 0;
  v34 = v31;
  v33 = 256;
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v30, a2);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v9,
      v25[0]);
  }
  else
  {
    v27 = (int *)&v26;
    v26 = 0;
    v28 = 0;
    v29 = 1;
    v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v25, v34, 0, &v28);
    if ( v29 )
    {
      v10 = v28;
      v11 = *(_QWORD *)v27;
      *(_QWORD *)v27 = v28;
      if ( v11 )
        SRCacheContext_Close(v11, v10);
    }
    if ( (v6 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)v6,
        v25[0]);
      v24 = 1136;
    }
    else if ( v26 && (v12 = SRCacheContext_EnumerateData(v26, 0, a3), v6 = v12, v12 < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v12,
        v25[0]);
      v24 = 1139;
    }
    else
    {
      v13 = SRCacheContext_AddToCache(*(_QWORD *)v25, L"Package\\Index\\PackageFullName");
      v6 = v13;
      if ( v13 >= 0 )
      {
        v15 = v26;
        v26 = 0;
        if ( v15 )
          SRCacheContext_Close(v15, v14);
        v16 = v30;
        v30 = 0;
        if ( v16 )
          SRCache_Free();
        v17 = *(_QWORD *)v25;
        *(_QWORD *)v25 = 0;
        if ( v17 )
          SRCacheContext_Close(v17, v14);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v13,
        v25[0]);
      v24 = 1142;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)v6,
      v25[0]);
    v23 = v26;
    v26 = 0;
    if ( v23 )
      SRCacheContext_Close(v23, v19);
  }
  v20 = v30;
  v30 = 0;
  if ( v20 )
    SRCache_Free();
LABEL_24:
  v21 = *(_QWORD *)v25;
  *(_QWORD *)v25 = 0;
  if ( v21 )
    SRCacheContext_Close(v21, v19);
  return v6;
}

```

## disassembly

```asm
0x180019694  push    rbp
0x180019696  push    rbx
0x180019697  push    rsi
0x180019698  push    rdi
0x180019699  push    r14
0x18001969b  lea     rbp, [rsp-180h]
0x1800196a3  sub     rsp, 280h
0x1800196aa  mov     rax, cs:__security_cookie
0x1800196b1  xor     rax, rsp
0x1800196b4  mov     [rbp+1A0h+var_30], rax
0x1800196bb  xor     r14d, r14d
0x1800196be  mov     [rsp+2A0h+var_260], 1
0x1800196c3  mov     [r8], r14
0x1800196c6  lea     rax, [rsp+2A0h+var_280]
0x1800196cb  mov     rcx, [rcx]
0x1800196ce  lea     r9, [rsp+2A0h+var_268]
0x1800196d3  mov     rdi, r8
0x1800196d6  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x1800196db  mov     rsi, rdx
0x1800196de  mov     [rsp+2A0h+var_270], rax
0x1800196e3  xor     r8d, r8d
0x1800196e6  mov     [rsp+2A0h+var_268], r14
0x1800196eb  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x1800196f2  call    cs:__imp_SRCacheContext_Open
0x1800196f8  mov     ebx, eax
0x1800196fa  cmp     [rsp+2A0h+var_260], r14b
0x1800196ff  jz      short loc_18001971C
0x180019701  mov     r8, [rsp+2A0h+var_270]
0x180019706  mov     rdx, [rsp+2A0h+var_268]
0x18001970b  mov     rcx, [r8]
0x18001970e  mov     [r8], rdx
0x180019711  test    rcx, rcx
0x180019714  jz      short loc_18001971C
0x180019716  call    cs:__imp_SRCacheContext_Close
0x18001971c  test    ebx, ebx
0x18001971e  js      loc_180019915
0x180019724  cmp     qword ptr [rsp+2A0h+var_280], r14
0x180019729  setnz   al
0x18001972c  test    al, al
0x18001972e  jz      loc_1800198C6
0x180019734  xor     edx, edx; Val
0x180019736  mov     [rsp+2A0h+var_250], r14
0x18001973b  mov     r8d, 200h; Size
0x180019741  lea     rcx, [rsp+2A0h+var_248]; void *
0x180019746  call    memset_0
0x18001974b  lea     rax, [rsp+2A0h+var_248]
0x180019750  mov     [rbp+1A0h+var_48], r14
0x180019757  mov     rdx, rsi; unsigned __int16 *
0x18001975a  mov     [rbp+1A0h+var_38], rax
0x180019761  lea     rcx, [rsp+2A0h+var_250]; this
0x180019766  mov     [rbp+1A0h+var_40], 100h
0x180019771  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180019776  mov     ebx, eax
0x180019778  test    eax, eax
0x18001977a  js      loc_18001987D
0x180019780  mov     rdx, [rbp+1A0h+var_38]
0x180019787  lea     rax, [rsp+2A0h+var_278]
0x18001978c  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180019791  lea     r9, [rsp+2A0h+var_268]
0x180019796  xor     r8d, r8d
0x180019799  mov     [rsp+2A0h+var_270], rax
0x18001979e  mov     [rsp+2A0h+var_278], r14
0x1800197a3  mov     [rsp+2A0h+var_268], r14
0x1800197a8  mov     [rsp+2A0h+var_260], 1
0x1800197ad  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800197b3  mov     ebx, eax
0x1800197b5  cmp     [rsp+2A0h+var_260], r14b
0x1800197ba  jz      short loc_1800197D7
0x1800197bc  mov     r8, [rsp+2A0h+var_270]
0x1800197c1  mov     rdx, [rsp+2A0h+var_268]
0x1800197c6  mov     rcx, [r8]
0x1800197c9  mov     [r8], rdx
0x1800197cc  test    rcx, rcx
0x1800197cf  jz      short loc_1800197D7
0x1800197d1  call    cs:__imp_SRCacheContext_Close
0x1800197d7  test    ebx, ebx
0x1800197d9  js      loc_180019937
0x1800197df  mov     rcx, [rsp+2A0h+var_278]
0x1800197e4  test    rcx, rcx
0x1800197e7  setnz   al
0x1800197ea  test    al, al
0x1800197ec  jz      short loc_180019803
0x1800197ee  mov     r8, rdi
0x1800197f1  xor     edx, edx
0x1800197f3  call    cs:__imp_SRCacheContext_EnumerateData
0x1800197f9  mov     ebx, eax
0x1800197fb  test    eax, eax
0x1800197fd  js      loc_180019959
0x180019803  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180019808  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18001980f  call    cs:__imp_SRCacheContext_AddToCache
0x180019815  mov     ebx, eax
0x180019817  test    eax, eax
0x180019819  js      loc_18001997E
0x18001981f  mov     rcx, [rsp+2A0h+var_278]
0x180019824  mov     [rsp+2A0h+var_278], r14
0x180019829  test    rcx, rcx
0x18001982c  jz      short loc_180019834
0x18001982e  call    cs:__imp_SRCacheContext_Close
0x180019834  mov     rcx, [rsp+2A0h+var_250]
0x180019839  mov     [rsp+2A0h+var_250], r14
0x18001983e  test    rcx, rcx
0x180019841  jz      short loc_180019849
0x180019843  call    cs:__imp_SRCache_Free
0x180019849  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001984e  mov     qword ptr [rsp+2A0h+var_280], r14
0x180019853  test    rcx, rcx
0x180019856  jz      short loc_18001985E
0x180019858  call    cs:__imp_SRCacheContext_Close
0x18001985e  xor     eax, eax
0x180019860  mov     rcx, [rbp+1A0h+var_30]
0x180019867  xor     rcx, rsp; StackCookie
0x18001986a  call    __security_check_cookie
0x18001986f  add     rsp, 280h
0x180019876  pop     r14
0x180019878  pop     rdi
0x180019879  pop     rsi
0x18001987a  pop     rbx
0x18001987b  pop     rbp
0x18001987c  retn
0x18001987d  mov     rcx, [rbp+1A8h]; this
0x180019884  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001988b  mov     r9d, ebx; char *
0x18001988e  mov     edx, 46Ch; void *
0x180019893  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019898  mov     rcx, [rsp+2A0h+var_250]
0x18001989d  mov     [rsp+2A0h+var_250], r14
0x1800198a2  test    rcx, rcx
0x1800198a5  jz      short loc_1800198AD
0x1800198a7  call    cs:__imp_SRCache_Free
0x1800198ad  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800198b2  mov     qword ptr [rsp+2A0h+var_280], r14
0x1800198b7  test    rcx, rcx
0x1800198ba  jz      short loc_1800198C2
0x1800198bc  call    cs:__imp_SRCacheContext_Close
0x1800198c2  mov     eax, ebx
0x1800198c4  jmp     short loc_180019860
0x1800198c6  mov     ebx, 80670012h
0x1800198cb  mov     edx, 469h; void *
0x1800198d0  mov     rcx, [rbp+1A8h]; this
0x1800198d7  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800198de  mov     r9d, ebx; char *
0x1800198e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198e6  jmp     short loc_1800198AD
0x1800198e8  mov     rcx, [rbp+1A8h]; this
0x1800198ef  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800198f6  mov     r9d, ebx; char *
0x1800198f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198fe  mov     rcx, [rsp+2A0h+var_278]
0x180019903  mov     [rsp+2A0h+var_278], r14
0x180019908  test    rcx, rcx
0x18001990b  jz      short loc_180019898
0x18001990d  call    cs:__imp_SRCacheContext_Close
0x180019913  jmp     short loc_180019898
0x180019915  mov     rcx, [rbp+1A8h]; this
0x18001991c  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019923  mov     r9d, ebx; char *
0x180019926  mov     edx, 18Ch; void *
0x18001992b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019930  mov     edx, 468h
0x180019935  jmp     short loc_1800198D0
0x180019937  mov     rcx, [rbp+1A8h]; this
0x18001993e  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019945  mov     r9d, ebx; char *
0x180019948  mov     edx, 1B0h; void *
0x18001994d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019952  mov     edx, 470h; void *
0x180019957  jmp     short loc_1800198E8
0x180019959  mov     rcx, [rbp+1A8h]; this
0x180019960  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019967  mov     r9d, ebx; char *
0x18001996a  mov     edx, 2A6h; void *
0x18001996f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019974  mov     edx, 473h
0x180019979  jmp     loc_1800198E8
0x18001997e  mov     rcx, [rbp+1A8h]; this
0x180019985  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001998c  mov     r9d, ebx; char *
0x18001998f  mov     edx, 1A6h; void *
0x180019994  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019999  mov     edx, 476h
0x18001999e  jmp     loc_1800198E8
```
