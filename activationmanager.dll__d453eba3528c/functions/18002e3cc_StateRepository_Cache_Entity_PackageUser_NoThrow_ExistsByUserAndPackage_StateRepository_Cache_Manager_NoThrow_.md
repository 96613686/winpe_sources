# StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)

- ea: `0x18002e3cc`
- end: `0x18002e736`
- name: `?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z`
- size: `874`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18002ce50`
- `0x18008df24`

## callees

- `0x180008be0`
- `0x18000b5c0`
- `0x18002e3cc`
- `0x18002ec54`
- `0x18005ae90`
- `0x18005ba40`
- `0x18008e088`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002e5e0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002e5e0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002e467`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002e467`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002e48b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002e4de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002e604`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002e657`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002e6e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002e70f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002e48b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002e4de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002e604`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002e657`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002e6e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002e70f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002e577`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002e6fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002e577`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002e6fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002e6a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002e6a5`

## string_xrefs

- `0x18002e49c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002e615`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002e6b8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002e415`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18002e4bc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18002e555`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18002e635`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        bool *a4)
{
  __int64 v7; // rdx
  int IsEmpty; // ebx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned __int16 v14; // dx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  bool v24[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v27; // [rsp+38h] [rbp-C8h]
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  char v29; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+258h] [rbp+158h]
  __int64 v33; // [rsp+260h] [rbp+160h]
  _BYTE *v34; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( !a2 )
  {
    v7 = 153;
LABEL_3:
    IsEmpty = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)0x80070057LL,
      *(int *)v24);
    return (unsigned int)IsEmpty;
  }
  if ( !a3 )
  {
    v7 = 154;
    goto LABEL_3;
  }
  v10 = *(_QWORD *)a1;
  v27 = &v25;
  v25 = 0;
  v28 = 0;
  v29 = 1;
  IsEmpty = SRCacheContext_Open(v10, L"PackageUser\\Index\\UserAndPackage", 0, &v28);
  if ( v29 )
  {
    v11 = *v27;
    *v27 = v28;
    if ( v11 )
      SRCacheContext_Close(v11);
  }
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      *(int *)v24);
    v12 = 158;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)IsEmpty,
      *(int *)v24);
LABEL_13:
    v13 = v25;
    v25 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    return (unsigned int)IsEmpty;
  }
  if ( !v25 )
  {
    IsEmpty = -2140733422;
    v12 = 159;
    goto LABEL_12;
  }
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v32 = 0;
  v34 = v31;
  v33 = 256;
  IsEmpty = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v30, a2);
  if ( IsEmpty < 0 )
  {
    v15 = 162;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)IsEmpty,
      *(int *)v24);
LABEL_20:
    v16 = v30;
    v30 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_13;
  }
  IsEmpty = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v30, v14);
  if ( IsEmpty < 0 )
  {
    v15 = 163;
    goto LABEL_19;
  }
  IsEmpty = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v30, a3);
  if ( IsEmpty < 0 )
  {
    v15 = 164;
    goto LABEL_19;
  }
  v27 = &v26;
  v26 = 0;
  v28 = 0;
  v29 = 1;
  IsEmpty = SRCacheContext_OpenSubContext(v25, v34, 0, &v28);
  if ( v29 )
  {
    v17 = *v27;
    *v27 = v28;
    if ( v17 )
      SRCacheContext_Close(v17);
  }
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      *(int *)v24);
    v18 = 168;
    goto LABEL_31;
  }
  if ( v26 )
  {
    v24[0] = 0;
    IsEmpty = StateRepository::Cache::Context_NoThrow::IsEmpty((StateRepository::Cache::Context_NoThrow *)&v26, v24);
    if ( IsEmpty < 0 )
    {
      v18 = 172;
      goto LABEL_31;
    }
    *a4 = !v24[0];
  }
  v20 = SRCacheContext_AddToCache(v25, L"PackageUser\\Index\\UserAndPackage");
  IsEmpty = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v20,
      *(int *)v24);
    v18 = 176;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)IsEmpty,
      *(int *)v24);
    v19 = v26;
    v26 = 0;
    if ( v19 )
      SRCacheContext_Close(v19);
    goto LABEL_20;
  }
  v21 = v26;
  v26 = 0;
  if ( v21 )
    SRCacheContext_Close(v21);
  v22 = v30;
  v30 = 0;
  if ( v22 )
    SRCache_Free();
  v23 = v25;
  v25 = 0;
  if ( v23 )
    SRCacheContext_Close(v23);
  return 0;
}

```

## disassembly

```asm
0x18002e3cc  push    rbp
0x18002e3ce  push    rbx
0x18002e3cf  push    rsi
0x18002e3d0  push    rdi
0x18002e3d1  push    r14
0x18002e3d3  push    r15
0x18002e3d5  lea     rbp, [rsp-188h]
0x18002e3dd  sub     rsp, 288h
0x18002e3e4  mov     rax, cs:__security_cookie
0x18002e3eb  xor     rax, rsp
0x18002e3ee  mov     [rbp+1B0h+var_40], rax
0x18002e3f5  xor     r15d, r15d
0x18002e3f8  mov     rsi, r9
0x18002e3fb  mov     [r9], r15b
0x18002e3fe  mov     rdi, r8
0x18002e401  mov     r14, rdx
0x18002e404  test    rdx, rdx
0x18002e407  jnz     short loc_18002E430
0x18002e409  mov     edx, 99h; void *
0x18002e40e  mov     rcx, [rbp+1B8h]; this
0x18002e415  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002e41c  mov     ebx, 80070057h
0x18002e421  mov     r9d, ebx; char *
0x18002e424  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e429  mov     eax, ebx
0x18002e42b  jmp     loc_18002E717
0x18002e430  test    rdi, rdi
0x18002e433  jnz     short loc_18002E43C
0x18002e435  mov     edx, 9Ah
0x18002e43a  jmp     short loc_18002E40E
0x18002e43c  mov     rcx, [rcx]
0x18002e43f  lea     rax, [rsp+2B0h+var_288]
0x18002e444  lea     r9, [rsp+2B0h+var_270]
0x18002e449  mov     [rsp+2B0h+var_278], rax
0x18002e44e  xor     r8d, r8d
0x18002e451  mov     [rsp+2B0h+var_288], r15
0x18002e456  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x18002e45d  mov     [rsp+2B0h+var_270], r15
0x18002e462  mov     [rsp+2B0h+var_268], 1
0x18002e467  call    cs:__imp_SRCacheContext_Open
0x18002e46d  mov     ebx, eax
0x18002e46f  cmp     [rsp+2B0h+var_268], r15b
0x18002e474  jz      short loc_18002E491
0x18002e476  mov     r8, [rsp+2B0h+var_278]
0x18002e47b  mov     rdx, [rsp+2B0h+var_270]
0x18002e480  mov     rcx, [r8]
0x18002e483  mov     [r8], rdx
0x18002e486  test    rcx, rcx
0x18002e489  jz      short loc_18002E491
0x18002e48b  call    cs:__imp_SRCacheContext_Close
0x18002e491  test    ebx, ebx
0x18002e493  jns     short loc_18002E4E9
0x18002e495  mov     rcx, [rbp+1B8h]; this
0x18002e49c  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002e4a3  mov     r9d, ebx; char *
0x18002e4a6  mov     edx, 18Ch; void *
0x18002e4ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e4b0  mov     edx, 9Eh; void *
0x18002e4b5  mov     rcx, [rbp+1B8h]; this
0x18002e4bc  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002e4c3  mov     r9d, ebx; char *
0x18002e4c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e4cb  mov     rcx, [rsp+2B0h+var_288]
0x18002e4d0  mov     [rsp+2B0h+var_288], r15
0x18002e4d5  test    rcx, rcx
0x18002e4d8  jz      loc_18002E429
0x18002e4de  call    cs:__imp_SRCacheContext_Close
0x18002e4e4  jmp     loc_18002E429
0x18002e4e9  cmp     [rsp+2B0h+var_288], r15
0x18002e4ee  setnz   al
0x18002e4f1  test    al, al
0x18002e4f3  jnz     short loc_18002E501
0x18002e4f5  mov     ebx, 80670012h
0x18002e4fa  mov     edx, 9Fh
0x18002e4ff  jmp     short loc_18002E4B5
0x18002e501  xor     edx, edx; Val
0x18002e503  mov     [rsp+2B0h+var_260], r15
0x18002e508  mov     r8d, 200h; Size
0x18002e50e  lea     rcx, [rsp+2B0h+var_258]; void *
0x18002e513  call    memset_0
0x18002e518  lea     rax, [rsp+2B0h+var_258]
0x18002e51d  mov     [rbp+1B0h+var_58], r15
0x18002e524  mov     rdx, r14; unsigned __int64
0x18002e527  mov     [rbp+1B0h+var_48], rax
0x18002e52e  lea     rcx, [rsp+2B0h+var_260]; this
0x18002e533  mov     [rbp+1B0h+var_50], 100h
0x18002e53e  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002e543  mov     ebx, eax
0x18002e545  test    eax, eax
0x18002e547  jns     short loc_18002E582
0x18002e549  mov     edx, 0A2h; void *
0x18002e54e  mov     rcx, [rbp+1B8h]; this
0x18002e555  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002e55c  mov     r9d, ebx; char *
0x18002e55f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e564  mov     rcx, [rsp+2B0h+var_260]
0x18002e569  mov     [rsp+2B0h+var_260], r15
0x18002e56e  test    rcx, rcx
0x18002e571  jz      loc_18002E4CB
0x18002e577  call    cs:__imp_SRCache_Free
0x18002e57d  jmp     loc_18002E4CB
0x18002e582  lea     rcx, [rsp+2B0h+var_260]; this
0x18002e587  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18002e58c  mov     ebx, eax
0x18002e58e  test    eax, eax
0x18002e590  jns     short loc_18002E599
0x18002e592  mov     edx, 0A3h
0x18002e597  jmp     short loc_18002E54E
0x18002e599  mov     rdx, rdi; unsigned __int64
0x18002e59c  lea     rcx, [rsp+2B0h+var_260]; this
0x18002e5a1  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002e5a6  mov     ebx, eax
0x18002e5a8  test    eax, eax
0x18002e5aa  jns     short loc_18002E5B3
0x18002e5ac  mov     edx, 0A4h
0x18002e5b1  jmp     short loc_18002E54E
0x18002e5b3  mov     rdx, [rbp+1B0h+var_48]
0x18002e5ba  lea     rax, [rsp+2B0h+var_280]
0x18002e5bf  mov     rcx, [rsp+2B0h+var_288]
0x18002e5c4  lea     r9, [rsp+2B0h+var_270]
0x18002e5c9  xor     r8d, r8d
0x18002e5cc  mov     [rsp+2B0h+var_278], rax
0x18002e5d1  mov     [rsp+2B0h+var_280], r15
0x18002e5d6  mov     [rsp+2B0h+var_270], r15
0x18002e5db  mov     [rsp+2B0h+var_268], 1
0x18002e5e0  call    cs:__imp_SRCacheContext_OpenSubContext
0x18002e5e6  mov     ebx, eax
0x18002e5e8  cmp     [rsp+2B0h+var_268], r15b
0x18002e5ed  jz      short loc_18002E60A
0x18002e5ef  mov     r8, [rsp+2B0h+var_278]
0x18002e5f4  mov     rdx, [rsp+2B0h+var_270]
0x18002e5f9  mov     rcx, [r8]
0x18002e5fc  mov     [r8], rdx
0x18002e5ff  test    rcx, rcx
0x18002e602  jz      short loc_18002E60A
0x18002e604  call    cs:__imp_SRCacheContext_Close
0x18002e60a  test    ebx, ebx
0x18002e60c  jns     short loc_18002E662
0x18002e60e  mov     rcx, [rbp+1B8h]; this
0x18002e615  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002e61c  mov     r9d, ebx; char *
0x18002e61f  mov     edx, 1B0h; void *
0x18002e624  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e629  mov     edx, 0A8h; void *
0x18002e62e  mov     rcx, [rbp+1B8h]; this
0x18002e635  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002e63c  mov     r9d, ebx; char *
0x18002e63f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e644  mov     rcx, [rsp+2B0h+var_280]
0x18002e649  mov     [rsp+2B0h+var_280], r15
0x18002e64e  test    rcx, rcx
0x18002e651  jz      loc_18002E564
0x18002e657  call    cs:__imp_SRCacheContext_Close
0x18002e65d  jmp     loc_18002E564
0x18002e662  cmp     [rsp+2B0h+var_280], r15
0x18002e667  setnz   al
0x18002e66a  test    al, al
0x18002e66c  jz      short loc_18002E699
0x18002e66e  lea     rdx, [rsp+2B0h+var_290]; bool *
0x18002e673  mov     [rsp+2B0h+var_290], r15b; int
0x18002e678  lea     rcx, [rsp+2B0h+var_280]; this
0x18002e67d  call    ?IsEmpty@Context_NoThrow@Cache@StateRepository@@QEAAJAEA_N@Z; StateRepository::Cache::Context_NoThrow::IsEmpty(bool &)
0x18002e682  mov     ebx, eax
0x18002e684  test    eax, eax
0x18002e686  jns     short loc_18002E68F
0x18002e688  mov     edx, 0ACh
0x18002e68d  jmp     short loc_18002E62E
0x18002e68f  cmp     [rsp+2B0h+var_290], r15b
0x18002e694  setz    al
0x18002e697  mov     [rsi], al
0x18002e699  mov     rcx, [rsp+2B0h+var_288]
0x18002e69e  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x18002e6a5  call    cs:__imp_SRCacheContext_AddToCache
0x18002e6ab  mov     ebx, eax
0x18002e6ad  test    eax, eax
0x18002e6af  jns     short loc_18002E6D6
0x18002e6b1  mov     rcx, [rbp+1B8h]; this
0x18002e6b8  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002e6bf  mov     r9d, eax; char *
0x18002e6c2  mov     edx, 1A6h; void *
0x18002e6c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e6cc  mov     edx, 0B0h
0x18002e6d1  jmp     loc_18002E62E
0x18002e6d6  mov     rcx, [rsp+2B0h+var_280]
0x18002e6db  mov     [rsp+2B0h+var_280], r15
0x18002e6e0  test    rcx, rcx
0x18002e6e3  jz      short loc_18002E6EB
0x18002e6e5  call    cs:__imp_SRCacheContext_Close
0x18002e6eb  mov     rcx, [rsp+2B0h+var_260]
0x18002e6f0  mov     [rsp+2B0h+var_260], r15
0x18002e6f5  test    rcx, rcx
0x18002e6f8  jz      short loc_18002E700
0x18002e6fa  call    cs:__imp_SRCache_Free
0x18002e700  mov     rcx, [rsp+2B0h+var_288]
0x18002e705  mov     [rsp+2B0h+var_288], r15
0x18002e70a  test    rcx, rcx
0x18002e70d  jz      short loc_18002E715
0x18002e70f  call    cs:__imp_SRCacheContext_Close
0x18002e715  xor     eax, eax
0x18002e717  mov     rcx, [rbp+1B0h+var_40]
0x18002e71e  xor     rcx, rsp; StackCookie
0x18002e721  call    __security_check_cookie
0x18002e726  add     rsp, 288h
0x18002e72d  pop     r15
0x18002e72f  pop     r14
0x18002e731  pop     rdi
0x18002e732  pop     rsi
0x18002e733  pop     rbx
0x18002e734  pop     rbp
0x18002e735  retn
```
