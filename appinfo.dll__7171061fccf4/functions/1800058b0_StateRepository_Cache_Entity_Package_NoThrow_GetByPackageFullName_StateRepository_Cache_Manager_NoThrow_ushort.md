# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)

- ea: `0x1800058b0`
- end: `0x180005cd5`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `1061`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800187f0`
- `0x180036898`

## callees

- `0x180004cb0`
- `0x1800058b0`
- `0x180006c50`
- `0x18000720c`
- `0x180007f00`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180005a1d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180005a1d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005a84`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005bc0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005c35`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005a84`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005bc0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005c35`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000598b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005a41`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005a99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005ad8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005b40`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005c4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005c6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005ca5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000598b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005a41`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005a99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005ad8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005b40`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005c4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005c6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005ca5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180005967`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180005967`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180005a65`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180005a65`

## string_xrefs

- `0x180005bd2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180005bf7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180005cb7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180005af4`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180005b1d`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180005b55`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180005b77`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180005ba1`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180005c12`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180005c7e`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 *a4,
        bool *a5)
{
  int v8; // eax
  unsigned int v9; // ebx
  unsigned __int64 v10; // rbx
  __int64 v12; // rcx
  unsigned int v13; // edi
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned __int64 v26; // r9
  __int64 v27; // rdx
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

  v36 = 0;
  *a5 = 0;
  v8 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(a1, a2, (__int64 *)&v36);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = v36;
    if ( !v36 )
      return 0;
    v12 = *(_QWORD *)a1;
    v33 = v31;
    v32 = 0;
    *(_QWORD *)v31 = 0;
    v34 = 0;
    v35 = 1;
    v13 = SRCacheContext_Open(v12, L"Package\\Data", 0, &v34);
    if ( v35 )
    {
      v14 = *(_QWORD *)v33;
      *(_QWORD *)v33 = v34;
      if ( v14 )
        SRCacheContext_Close(v14);
    }
    if ( (v13 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)v13,
        v31[0]);
      v23 = 1192;
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
        v15 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v37, v10);
        v13 = v15;
        if ( v15 < 0 )
        {
          v26 = (unsigned int)v15;
          v27 = 1196;
        }
        else
        {
          v33 = (int *)&v32;
          v34 = 0;
          v35 = 1;
          v13 = SRCacheContext_OpenSubContext(*(_QWORD *)v31, v41, 0, &v34);
          if ( v35 )
          {
            v16 = *(_QWORD *)v33;
            *(_QWORD *)v33 = v34;
            if ( v16 )
              SRCacheContext_Close(v16);
          }
          if ( (v13 & 0x80000000) == 0 )
          {
            v17 = *(_QWORD *)v31;
            *a5 = v32 != 0;
            v18 = SRCacheContext_AddToCache(v17, L"Package\\Data");
            v13 = v18;
            if ( v18 >= 0 )
            {
              v19 = v37;
              v37 = 0;
              if ( v19 )
                SRCache_Free(v19);
              v20 = *(_QWORD *)v31;
              *(_QWORD *)v31 = 0;
              if ( v20 )
                SRCacheContext_Close(v20);
              if ( !*a5 )
              {
                v22 = v32;
                v32 = 0;
                if ( !v22 )
                  return 0;
                goto LABEL_22;
              }
              v21 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&v32, a4, a3, v10);
              v13 = v21;
              if ( v21 >= 0 )
              {
                v22 = v32;
                v32 = 0;
                if ( !v22 )
                  return 0;
LABEL_22:
                SRCacheContext_Close(v22);
                return 0;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x45B,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
                (const char *)(unsigned int)v21,
                v31[0]);
              v30 = v32;
              v32 = 0;
              if ( v30 )
                SRCacheContext_Close(v30);
              goto LABEL_29;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1A6,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
              (const char *)(unsigned int)v18,
              v31[0]);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4AF,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
              (const char *)v13,
              v31[0]);
            v29 = v37;
            v37 = 0;
            if ( v29 )
              SRCache_Free(v29);
            v24 = *(_QWORD *)v31;
            *(_QWORD *)v31 = 0;
            if ( !v24 )
            {
LABEL_26:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x456,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
                (const char *)v13,
                v31[0]);
              v25 = v32;
              v32 = 0;
              if ( v25 )
                SRCacheContext_Close(v25);
              if ( (v13 & 0x80000000) == 0 )
                return 0;
LABEL_29:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x490,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
                (const char *)v13,
                v31[0]);
              return v13;
            }
LABEL_38:
            SRCacheContext_Close(v24);
            goto LABEL_26;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B0,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
            (const char *)v13,
            v31[0]);
          v26 = v13;
          v27 = 1197;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
          (const char *)v26,
          v31[0]);
        v28 = v37;
        v37 = 0;
        if ( v28 )
          SRCache_Free(v28);
LABEL_25:
        v24 = *(_QWORD *)v31;
        *(_QWORD *)v31 = 0;
        if ( !v24 )
          goto LABEL_26;
        goto LABEL_38;
      }
      v13 = -2140733422;
      v23 = 1193;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)v13,
      v31[0]);
    goto LABEL_25;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x48D,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
    (const char *)(unsigned int)v8,
    v31[0]);
  return v9;
}

```

## disassembly

```asm
0x1800058b0  push    rbp
0x1800058b2  push    rbx
0x1800058b3  push    rsi
0x1800058b4  push    rdi
0x1800058b5  push    r12
0x1800058b7  push    r14
0x1800058b9  push    r15
0x1800058bb  lea     rbp, [rsp-180h]
0x1800058c3  sub     rsp, 280h
0x1800058ca  mov     rax, cs:__security_cookie
0x1800058d1  xor     rax, rsp
0x1800058d4  mov     [rbp+1B0h+var_40], rax
0x1800058db  mov     rsi, [rbp+1B0h+arg_20]
0x1800058e2  mov     r14, r8
0x1800058e5  xor     r12d, r12d
0x1800058e8  lea     r8, [rsp+2B0h+var_268]; __int64 *
0x1800058ed  mov     r15, r9
0x1800058f0  mov     [rsp+2B0h+var_268], r12
0x1800058f5  mov     rdi, rcx
0x1800058f8  mov     byte ptr [rsi], 0
0x1800058fb  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180005900  mov     ebx, eax
0x180005902  test    eax, eax
0x180005904  js      loc_180005B70
0x18000590a  mov     rbx, [rsp+2B0h+var_268]
0x18000590f  test    rbx, rbx
0x180005912  jnz     short loc_180005937
0x180005914  xor     eax, eax
0x180005916  mov     rcx, [rbp+1B0h+var_40]
0x18000591d  xor     rcx, rsp; StackCookie
0x180005920  call    __security_check_cookie
0x180005925  add     rsp, 280h
0x18000592c  pop     r15
0x18000592e  pop     r14
0x180005930  pop     r12
0x180005932  pop     rdi
0x180005933  pop     rsi
0x180005934  pop     rbx
0x180005935  pop     rbp
0x180005936  retn
0x180005937  mov     rcx, [rdi]
0x18000593a  lea     rax, [rsp+2B0h+var_290]
0x18000593f  lea     r9, [rsp+2B0h+var_278]
0x180005944  mov     [rsp+2B0h+var_280], rax
0x180005949  xor     r8d, r8d
0x18000594c  mov     [rsp+2B0h+var_288], r12
0x180005951  lea     rdx, aPackageData; "Package\\Data"
0x180005958  mov     qword ptr [rsp+2B0h+var_290], r12; int
0x18000595d  mov     [rsp+2B0h+var_278], r12
0x180005962  mov     [rsp+2B0h+var_270], 1
0x180005967  call    cs:__imp_SRCacheContext_Open
0x18000596d  mov     edi, eax
0x18000596f  cmp     [rsp+2B0h+var_270], r12b
0x180005974  jz      short loc_180005991
0x180005976  mov     rdx, [rsp+2B0h+var_280]
0x18000597b  mov     rax, [rsp+2B0h+var_278]
0x180005980  mov     rcx, [rdx]
0x180005983  mov     [rdx], rax
0x180005986  test    rcx, rcx
0x180005989  jz      short loc_180005991
0x18000598b  call    cs:__imp_SRCacheContext_Close
0x180005991  test    edi, edi
0x180005993  js      loc_180005CB0
0x180005999  cmp     qword ptr [rsp+2B0h+var_290], r12
0x18000599e  setnz   al
0x1800059a1  test    al, al
0x1800059a3  jz      loc_180005AE3
0x1800059a9  xor     edx, edx; Val
0x1800059ab  mov     [rsp+2B0h+var_260], r12
0x1800059b0  mov     r8d, 200h; Size
0x1800059b6  lea     rcx, [rsp+2B0h+var_258]; void *
0x1800059bb  call    memset_0
0x1800059c0  lea     rax, [rsp+2B0h+var_258]
0x1800059c5  mov     [rbp+1B0h+var_58], r12
0x1800059cc  mov     rdx, rbx; unsigned __int64
0x1800059cf  mov     [rbp+1B0h+var_48], rax
0x1800059d6  lea     rcx, [rsp+2B0h+var_260]; this
0x1800059db  mov     [rbp+1B0h+var_50], 100h
0x1800059e6  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800059eb  mov     edi, eax
0x1800059ed  test    eax, eax
0x1800059ef  js      loc_180005B92
0x1800059f5  mov     rdx, [rbp+1B0h+var_48]
0x1800059fc  lea     rax, [rsp+2B0h+var_288]
0x180005a01  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180005a06  lea     r9, [rsp+2B0h+var_278]
0x180005a0b  xor     r8d, r8d
0x180005a0e  mov     [rsp+2B0h+var_280], rax
0x180005a13  mov     [rsp+2B0h+var_278], r12
0x180005a18  mov     [rsp+2B0h+var_270], 1
0x180005a1d  call    cs:__imp_SRCacheContext_OpenSubContext
0x180005a23  mov     edi, eax
0x180005a25  cmp     [rsp+2B0h+var_270], r12b
0x180005a2a  jz      short loc_180005A47
0x180005a2c  mov     rdx, [rsp+2B0h+var_280]
0x180005a31  mov     rax, [rsp+2B0h+var_278]
0x180005a36  mov     rcx, [rdx]
0x180005a39  mov     [rdx], rax
0x180005a3c  test    rcx, rcx
0x180005a3f  jz      short loc_180005A47
0x180005a41  call    cs:__imp_SRCacheContext_Close
0x180005a47  test    edi, edi
0x180005a49  js      loc_180005BCB
0x180005a4f  cmp     [rsp+2B0h+var_288], r12
0x180005a54  lea     rdx, aPackageData; "Package\\Data"
0x180005a5b  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180005a60  setnz   al
0x180005a63  mov     [rsi], al
0x180005a65  call    cs:__imp_SRCacheContext_AddToCache
0x180005a6b  mov     edi, eax
0x180005a6d  test    eax, eax
0x180005a6f  js      loc_180005BF0
0x180005a75  mov     rcx, [rsp+2B0h+var_260]
0x180005a7a  mov     [rsp+2B0h+var_260], r12
0x180005a7f  test    rcx, rcx
0x180005a82  jz      short loc_180005A8A
0x180005a84  call    cs:__imp_SRCache_Free
0x180005a8a  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180005a8f  mov     qword ptr [rsp+2B0h+var_290], r12; int
0x180005a94  test    rcx, rcx
0x180005a97  jz      short loc_180005A9F
0x180005a99  call    cs:__imp_SRCacheContext_Close
0x180005a9f  cmp     [rsi], r12b
0x180005aa2  jz      loc_180005C59
0x180005aa8  mov     r9, rbx
0x180005aab  lea     rcx, [rsp+2B0h+var_288]
0x180005ab0  mov     r8, r14
0x180005ab3  mov     rdx, r15
0x180005ab6  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x180005abb  mov     edi, eax
0x180005abd  test    eax, eax
0x180005abf  js      loc_180005C77
0x180005ac5  mov     rcx, [rsp+2B0h+var_288]
0x180005aca  mov     [rsp+2B0h+var_288], r12
0x180005acf  test    rcx, rcx
0x180005ad2  jz      loc_180005914
0x180005ad8  call    cs:__imp_SRCacheContext_Close
0x180005ade  jmp     loc_180005914
0x180005ae3  mov     edi, 80670012h
0x180005ae8  mov     edx, 4A9h; void *
0x180005aed  mov     rcx, [rbp+1B8h]; this
0x180005af4  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005afb  mov     r9d, edi; char *
0x180005afe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b03  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180005b08  mov     qword ptr [rsp+2B0h+var_290], r12; int
0x180005b0d  test    rcx, rcx
0x180005b10  jnz     loc_180005C4E
0x180005b16  mov     rcx, [rbp+1B8h]; this
0x180005b1d  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005b24  mov     r9d, edi; char *
0x180005b27  mov     edx, 456h; void *
0x180005b2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b31  mov     rcx, [rsp+2B0h+var_288]
0x180005b36  mov     [rsp+2B0h+var_288], r12
0x180005b3b  test    rcx, rcx
0x180005b3e  jz      short loc_180005B46
0x180005b40  call    cs:__imp_SRCacheContext_Close
0x180005b46  test    edi, edi
0x180005b48  jns     loc_180005914
0x180005b4e  mov     rcx, [rbp+1B8h]; this
0x180005b55  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005b5c  mov     r9d, edi; char *
0x180005b5f  mov     edx, 490h; void *
0x180005b64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b69  mov     eax, edi
0x180005b6b  jmp     loc_180005916
0x180005b70  mov     rcx, [rbp+1B8h]; this
0x180005b77  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005b7e  mov     r9d, ebx; char *
0x180005b81  mov     edx, 48Dh; void *
0x180005b86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b8b  mov     eax, ebx
0x180005b8d  jmp     loc_180005916
0x180005b92  mov     r9d, eax; char *
0x180005b95  mov     edx, 4ACh; void *
0x180005b9a  mov     rcx, [rbp+1B8h]; this
0x180005ba1  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005ba8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005bad  mov     rcx, [rsp+2B0h+var_260]
0x180005bb2  mov     [rsp+2B0h+var_260], r12
0x180005bb7  test    rcx, rcx
0x180005bba  jz      loc_180005B03
0x180005bc0  call    cs:__imp_SRCache_Free
0x180005bc6  jmp     loc_180005B03
0x180005bcb  mov     rcx, [rbp+1B8h]; this
0x180005bd2  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005bd9  mov     r9d, edi; char *
0x180005bdc  mov     edx, 1B0h; void *
0x180005be1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005be6  mov     r9d, edi
0x180005be9  mov     edx, 4ADh
0x180005bee  jmp     short loc_180005B9A
0x180005bf0  mov     rcx, [rbp+1B8h]; this
0x180005bf7  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005bfe  mov     r9d, edi; char *
0x180005c01  mov     edx, 1A6h; void *
0x180005c06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c0b  mov     rcx, [rbp+1B8h]; this
0x180005c12  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005c19  mov     r9d, edi; char *
0x180005c1c  mov     edx, 4AFh; void *
0x180005c21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c26  mov     rcx, [rsp+2B0h+var_260]
0x180005c2b  mov     [rsp+2B0h+var_260], r12
0x180005c30  test    rcx, rcx
0x180005c33  jz      short loc_180005C3B
0x180005c35  call    cs:__imp_SRCache_Free
0x180005c3b  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180005c40  mov     qword ptr [rsp+2B0h+var_290], r12
0x180005c45  test    rcx, rcx
0x180005c48  jz      loc_180005B16
0x180005c4e  call    cs:__imp_SRCacheContext_Close
0x180005c54  jmp     loc_180005B16
0x180005c59  mov     rcx, [rsp+2B0h+var_288]
0x180005c5e  mov     [rsp+2B0h+var_288], r12
0x180005c63  test    rcx, rcx
0x180005c66  jz      loc_180005914
0x180005c6c  call    cs:__imp_SRCacheContext_Close
0x180005c72  jmp     loc_180005914
0x180005c77  mov     rcx, [rbp+1B8h]; this
0x180005c7e  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005c85  mov     r9d, eax; char *
0x180005c88  mov     edx, 45Bh; void *
0x180005c8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c92  mov     rcx, [rsp+2B0h+var_288]
0x180005c97  mov     [rsp+2B0h+var_288], r12
0x180005c9c  test    rcx, rcx
0x180005c9f  jz      loc_180005B4E
0x180005ca5  call    cs:__imp_SRCacheContext_Close
0x180005cab  jmp     loc_180005B4E
0x180005cb0  mov     rcx, [rbp+1B8h]; this
0x180005cb7  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005cbe  mov     r9d, edi; char *
0x180005cc1  mov     edx, 18Ch; void *
0x180005cc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ccb  mov     edx, 4A8h
0x180005cd0  jmp     loc_180005AED
```
