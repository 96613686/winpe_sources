# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)

- ea: `0x180006510`
- end: `0x18000695c`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `1100`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180029d24`
- `0x1800337f8`

## callees

- `0x1800055d0`
- `0x180006510`
- `0x180006970`
- `0x1800075b0`
- `0x180007c78`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800065c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800065c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800065f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800066b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000671e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006763`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800067a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000692e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800065f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800066b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000671e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006763`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800067a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000692e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000668a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000668a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006703`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006804`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800068a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006703`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006804`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800068a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800066de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800066de`

## string_xrefs

- `0x180006785`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800067bf`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800067e9`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18000687e`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800068c7`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18000690b`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180006941`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180006819`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000683e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180006863`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
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
  unsigned __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v31; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 v32; // [rsp+30h] [rbp-D0h] BYREF
  int *v33; // [rsp+38h] [rbp-C8h]
  __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  char v35; // [rsp+48h] [rbp-B8h]
  __int64 *v36; // [rsp+50h] [rbp-B0h]
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  char v38; // [rsp+60h] [rbp-A0h]
  __int64 v39; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v40[512]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v41; // [rsp+278h] [rbp+178h]
  __int64 v42; // [rsp+280h] [rbp+180h]
  _BYTE *v43; // [rsp+288h] [rbp+188h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v32 = 0;
  *a5 = 0;
  v8 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(a1, a2, (__int64 *)&v32);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x483,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v8,
      v30[0]);
    return v9;
  }
  v10 = v32;
  if ( !v32 )
    return 0;
  v12 = *(_QWORD *)a1;
  v33 = v30;
  v31 = 0;
  *(_QWORD *)v30 = 0;
  v34 = 0;
  v35 = 1;
  v13 = SRCacheContext_Open(v12, L"Package\\Data", 0, &v34);
  if ( v35 )
  {
    v14 = *(_QWORD *)v33;
    *(_QWORD *)v33 = v34;
    if ( v14 )
      ((void (*)(void))SRCacheContext_Close)();
  }
  if ( (v13 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v13,
      v30[0]);
    v23 = 1182;
    goto LABEL_24;
  }
  if ( !*(_QWORD *)v30 )
  {
    v13 = -2140733422;
    v23 = 1183;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)v13,
      v30[0]);
    goto LABEL_25;
  }
  v39 = 0;
  memset_0(v40, 0, sizeof(v40));
  v41 = 0;
  v43 = v40;
  v42 = 256;
  v15 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v39, v10);
  v13 = v15;
  if ( v15 < 0 )
  {
    v25 = (unsigned int)v15;
    v26 = 1186;
    goto LABEL_29;
  }
  v36 = &v31;
  v37 = 0;
  v38 = 1;
  v13 = SRCacheContext_OpenSubContext(*(_QWORD *)v30, v43, 0, &v37);
  if ( v38 )
  {
    v16 = *v36;
    *v36 = v37;
    if ( v16 )
      ((void (*)(void))SRCacheContext_Close)();
  }
  if ( (v13 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v13,
      v30[0]);
    v25 = v13;
    v26 = 1187;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)v25,
      v30[0]);
    v27 = v39;
    v39 = 0;
    if ( v27 )
      SRCache_Free();
LABEL_25:
    v24 = *(_QWORD *)v30;
    *(_QWORD *)v30 = 0;
    if ( !v24 )
      goto LABEL_36;
    goto LABEL_26;
  }
  v17 = *(_QWORD *)v30;
  *a5 = v31 != 0;
  v18 = SRCacheContext_AddToCache(v17, L"Package\\Data");
  v13 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v18,
      v30[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)v13,
      v30[0]);
    v28 = v39;
    v39 = 0;
    if ( v28 )
      SRCache_Free();
    v24 = *(_QWORD *)v30;
    *(_QWORD *)v30 = 0;
    if ( !v24 )
    {
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44C,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
        (const char *)v13,
        v30[0]);
      v29 = v31;
      v31 = 0;
      if ( !v29 )
        goto LABEL_42;
      goto LABEL_41;
    }
LABEL_26:
    SRCacheContext_Close(v24);
    goto LABEL_36;
  }
  v19 = v39;
  v39 = 0;
  if ( v19 )
    SRCache_Free();
  v20 = *(_QWORD *)v30;
  *(_QWORD *)v30 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  if ( !*a5 )
  {
    v22 = v31;
    v31 = 0;
    if ( !v22 )
      return 0;
    goto LABEL_22;
  }
  v21 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&v31, a4, a3, v10);
  v13 = v21;
  if ( v21 >= 0 )
  {
    v22 = v31;
    v31 = 0;
    if ( !v22 )
      return 0;
LABEL_22:
    SRCacheContext_Close(v22);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x451,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
    (const char *)(unsigned int)v21,
    v30[0]);
  v29 = v31;
  v31 = 0;
  if ( !v29 )
    goto LABEL_42;
LABEL_41:
  SRCacheContext_Close(v29);
LABEL_42:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x486,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
    (const char *)v13,
    v30[0]);
  return v13;
}

```

## disassembly

```asm
0x180006510  push    rbp
0x180006512  push    rbx
0x180006513  push    rsi
0x180006514  push    rdi
0x180006515  push    r12
0x180006517  push    r14
0x180006519  push    r15
0x18000651b  lea     rbp, [rsp-1A0h]
0x180006523  sub     rsp, 2A0h
0x18000652a  mov     rax, cs:__security_cookie
0x180006531  xor     rax, rsp
0x180006534  mov     [rbp+1D0h+var_40], rax
0x18000653b  mov     rsi, [rbp+1D0h+arg_20]
0x180006542  mov     r14, r8
0x180006545  xor     r12d, r12d
0x180006548  lea     r8, [rsp+2D0h+var_2A0]; __int64 *
0x18000654d  mov     r15, r9
0x180006550  mov     [rsp+2D0h+var_2A0], r12
0x180006555  mov     rdi, rcx
0x180006558  mov     byte ptr [rsi], 0
0x18000655b  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180006560  mov     ebx, eax
0x180006562  test    eax, eax
0x180006564  js      loc_1800067B8
0x18000656a  mov     rbx, [rsp+2D0h+var_2A0]
0x18000656f  test    rbx, rbx
0x180006572  jnz     short loc_180006598
0x180006574  xor     eax, eax
0x180006576  mov     rcx, [rbp+1D0h+var_40]
0x18000657d  xor     rcx, rsp; StackCookie
0x180006580  call    __security_check_cookie
0x180006585  add     rsp, 2A0h
0x18000658c  pop     r15
0x18000658e  pop     r14
0x180006590  pop     r12
0x180006592  pop     rdi
0x180006593  pop     rsi
0x180006594  pop     rbx
0x180006595  pop     rbp
0x180006596  retn
0x180006598  mov     rcx, [rdi]
0x18000659b  lea     rax, [rsp+2D0h+var_2B0]
0x1800065a0  lea     r9, [rsp+2D0h+var_290]
0x1800065a5  mov     [rsp+2D0h+var_298], rax
0x1800065aa  xor     r8d, r8d
0x1800065ad  mov     [rsp+2D0h+var_2A8], r12
0x1800065b2  lea     rdx, aPackageData; "Package\\Data"
0x1800065b9  mov     qword ptr [rsp+2D0h+var_2B0], r12; int
0x1800065be  mov     [rsp+2D0h+var_290], r12
0x1800065c3  mov     [rsp+2D0h+var_288], 1
0x1800065c8  call    cs:__imp_SRCacheContext_Open
0x1800065cf  nop     dword ptr [rax+rax+00h]
0x1800065d4  mov     edi, eax
0x1800065d6  cmp     [rsp+2D0h+var_288], r12b
0x1800065db  jz      short loc_1800065FE
0x1800065dd  mov     rdx, [rsp+2D0h+var_298]
0x1800065e2  mov     rax, [rsp+2D0h+var_290]
0x1800065e7  mov     rcx, [rdx]
0x1800065ea  mov     [rdx], rax
0x1800065ed  test    rcx, rcx
0x1800065f0  jz      short loc_1800065FE
0x1800065f2  call    cs:__imp_SRCacheContext_Close
0x1800065f9  nop     dword ptr [rax+rax+00h]
0x1800065fe  test    edi, edi
0x180006600  js      loc_180006837
0x180006606  cmp     qword ptr [rsp+2D0h+var_2B0], r12
0x18000660b  setnz   al
0x18000660e  test    al, al
0x180006610  jz      loc_180006774
0x180006616  xor     edx, edx; Val
0x180006618  mov     [rsp+2D0h+var_260], r12
0x18000661d  mov     r8d, 200h; Size
0x180006623  lea     rcx, [rsp+2D0h+var_258]; void *
0x180006628  call    memset_0
0x18000662d  lea     rax, [rsp+2D0h+var_258]
0x180006632  mov     [rbp+1D0h+var_58], r12
0x180006639  mov     rdx, rbx; unsigned __int64
0x18000663c  mov     [rbp+1D0h+var_48], rax
0x180006643  lea     rcx, [rsp+2D0h+var_260]; this
0x180006648  mov     [rbp+1D0h+var_50], 100h
0x180006653  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180006658  mov     edi, eax
0x18000665a  test    eax, eax
0x18000665c  js      loc_1800067DA
0x180006662  mov     rdx, [rbp+1D0h+var_48]
0x180006669  lea     rax, [rsp+2D0h+var_2A8]
0x18000666e  mov     rcx, qword ptr [rsp+2D0h+var_2B0]
0x180006673  lea     r9, [rsp+2D0h+var_278]
0x180006678  xor     r8d, r8d
0x18000667b  mov     [rsp+2D0h+var_280], rax
0x180006680  mov     [rsp+2D0h+var_278], r12
0x180006685  mov     [rsp+2D0h+var_270], 1
0x18000668a  call    cs:__imp_SRCacheContext_OpenSubContext
0x180006691  nop     dword ptr [rax+rax+00h]
0x180006696  mov     edi, eax
0x180006698  cmp     [rsp+2D0h+var_270], r12b
0x18000669d  jz      short loc_1800066C0
0x18000669f  mov     rdx, [rsp+2D0h+var_280]
0x1800066a4  mov     rax, [rsp+2D0h+var_278]
0x1800066a9  mov     rcx, [rdx]
0x1800066ac  mov     [rdx], rax
0x1800066af  test    rcx, rcx
0x1800066b2  jz      short loc_1800066C0
0x1800066b4  call    cs:__imp_SRCacheContext_Close
0x1800066bb  nop     dword ptr [rax+rax+00h]
0x1800066c0  test    edi, edi
0x1800066c2  js      loc_180006812
0x1800066c8  cmp     [rsp+2D0h+var_2A8], r12
0x1800066cd  lea     rdx, aPackageData; "Package\\Data"
0x1800066d4  mov     rcx, qword ptr [rsp+2D0h+var_2B0]
0x1800066d9  setnz   al
0x1800066dc  mov     [rsi], al
0x1800066de  call    cs:__imp_SRCacheContext_AddToCache
0x1800066e5  nop     dword ptr [rax+rax+00h]
0x1800066ea  mov     edi, eax
0x1800066ec  test    eax, eax
0x1800066ee  js      loc_18000685C
0x1800066f4  mov     rcx, [rsp+2D0h+var_260]
0x1800066f9  mov     [rsp+2D0h+var_260], r12
0x1800066fe  test    rcx, rcx
0x180006701  jz      short loc_18000670F
0x180006703  call    cs:__imp_SRCache_Free
0x18000670a  nop     dword ptr [rax+rax+00h]
0x18000670f  mov     rcx, qword ptr [rsp+2D0h+var_2B0]
0x180006714  mov     qword ptr [rsp+2D0h+var_2B0], r12; int
0x180006719  test    rcx, rcx
0x18000671c  jz      short loc_18000672A
0x18000671e  call    cs:__imp_SRCacheContext_Close
0x180006725  nop     dword ptr [rax+rax+00h]
0x18000672a  cmp     [rsi], r12b
0x18000672d  jz      loc_1800068EC
0x180006733  mov     r9, rbx
0x180006736  lea     rcx, [rsp+2D0h+var_2A8]
0x18000673b  mov     r8, r14
0x18000673e  mov     rdx, r15
0x180006741  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x180006746  mov     edi, eax
0x180006748  test    eax, eax
0x18000674a  js      loc_180006904
0x180006750  mov     rcx, [rsp+2D0h+var_2A8]
0x180006755  mov     [rsp+2D0h+var_2A8], r12
0x18000675a  test    rcx, rcx
0x18000675d  jz      loc_180006574
0x180006763  call    cs:__imp_SRCacheContext_Close
0x18000676a  nop     dword ptr [rax+rax+00h]
0x18000676f  jmp     loc_180006574
0x180006774  mov     edi, 80670012h
0x180006779  mov     edx, 49Fh; void *
0x18000677e  mov     rcx, [rbp+1D8h]; this
0x180006785  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000678c  mov     r9d, edi; char *
0x18000678f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006794  mov     rcx, qword ptr [rsp+2D0h+var_2B0]
0x180006799  mov     qword ptr [rsp+2D0h+var_2B0], r12
0x18000679e  test    rcx, rcx
0x1800067a1  jz      loc_1800068C0
0x1800067a7  call    cs:__imp_SRCacheContext_Close
0x1800067ae  nop     dword ptr [rax+rax+00h]
0x1800067b3  jmp     loc_1800068C0
0x1800067b8  mov     rcx, [rbp+1D8h]; this
0x1800067bf  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800067c6  mov     r9d, ebx; char *
0x1800067c9  mov     edx, 483h; void *
0x1800067ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067d3  mov     eax, ebx
0x1800067d5  jmp     loc_180006576
0x1800067da  mov     r9d, eax; char *
0x1800067dd  mov     edx, 4A2h; void *
0x1800067e2  mov     rcx, [rbp+1D8h]; this
0x1800067e9  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800067f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067f5  mov     rcx, [rsp+2D0h+var_260]
0x1800067fa  mov     [rsp+2D0h+var_260], r12
0x1800067ff  test    rcx, rcx
0x180006802  jz      short loc_180006794
0x180006804  call    cs:__imp_SRCache_Free
0x18000680b  nop     dword ptr [rax+rax+00h]
0x180006810  jmp     short loc_180006794
0x180006812  mov     rcx, [rbp+1D8h]; this
0x180006819  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006820  mov     r9d, edi; char *
0x180006823  mov     edx, 1B0h; void *
0x180006828  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000682d  mov     r9d, edi
0x180006830  mov     edx, 4A3h
0x180006835  jmp     short loc_1800067E2
0x180006837  mov     rcx, [rbp+1D8h]; this
0x18000683e  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006845  mov     r9d, edi; char *
0x180006848  mov     edx, 18Ch; void *
0x18000684d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006852  mov     edx, 49Eh
0x180006857  jmp     loc_18000677E
0x18000685c  mov     rcx, [rbp+1D8h]; this
0x180006863  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000686a  mov     r9d, edi; char *
0x18000686d  mov     edx, 1A6h; void *
0x180006872  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006877  mov     rcx, [rbp+1D8h]; this
0x18000687e  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006885  mov     r9d, edi; char *
0x180006888  mov     edx, 4A5h; void *
0x18000688d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006892  mov     rcx, [rsp+2D0h+var_260]
0x180006897  mov     [rsp+2D0h+var_260], r12
0x18000689c  test    rcx, rcx
0x18000689f  jz      short loc_1800068AD
0x1800068a1  call    cs:__imp_SRCache_Free
0x1800068a8  nop     dword ptr [rax+rax+00h]
0x1800068ad  mov     rcx, qword ptr [rsp+2D0h+var_2B0]
0x1800068b2  mov     qword ptr [rsp+2D0h+var_2B0], r12; int
0x1800068b7  test    rcx, rcx
0x1800068ba  jnz     loc_1800067A7
0x1800068c0  mov     rcx, [rbp+1D8h]; this
0x1800068c7  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800068ce  mov     r9d, edi; char *
0x1800068d1  mov     edx, 44Ch; void *
0x1800068d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800068db  mov     rcx, [rsp+2D0h+var_2A8]
0x1800068e0  mov     [rsp+2D0h+var_2A8], r12
0x1800068e5  test    rcx, rcx
0x1800068e8  jnz     short loc_18000692E
0x1800068ea  jmp     short loc_18000693A
0x1800068ec  mov     rcx, [rsp+2D0h+var_2A8]
0x1800068f1  mov     [rsp+2D0h+var_2A8], r12
0x1800068f6  test    rcx, rcx
0x1800068f9  jz      loc_180006574
0x1800068ff  jmp     loc_180006763
0x180006904  mov     rcx, [rbp+1D8h]; this
0x18000690b  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006912  mov     r9d, eax; char *
0x180006915  mov     edx, 451h; void *
0x18000691a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000691f  mov     rcx, [rsp+2D0h+var_2A8]
0x180006924  mov     [rsp+2D0h+var_2A8], r12
0x180006929  test    rcx, rcx
0x18000692c  jz      short loc_18000693A
0x18000692e  call    cs:__imp_SRCacheContext_Close
0x180006935  nop     dword ptr [rax+rax+00h]
0x18000693a  mov     rcx, [rbp+1D8h]; this
0x180006941  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006948  mov     r9d, edi; char *
0x18000694b  mov     edx, 486h; void *
0x180006950  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006955  mov     eax, edi
0x180006957  jmp     loc_180006576
```
