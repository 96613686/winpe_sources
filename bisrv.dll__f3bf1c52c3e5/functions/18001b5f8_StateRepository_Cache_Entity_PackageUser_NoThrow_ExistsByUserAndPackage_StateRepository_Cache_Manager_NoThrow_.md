# StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)

- ea: `0x18001b5f8`
- end: `0x18001b97f`
- name: `?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z`
- size: `903`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001afd4`
- `0x1800526e0`

## callees

- `0x180018be0`
- `0x18001a1f0`
- `0x18001b5f8`
- `0x18001bee4`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001b693`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001b693`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b6b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b70a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b830`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b883`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b92e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b958`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b6b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b70a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b830`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b883`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b92e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b958`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001b80c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001b80c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b7a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b943`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b7a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b943`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001b8ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001b8ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x18001b8a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x18001b8a7`

## string_xrefs

- `0x18001b6c8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001b841`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001b8ba`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001b901`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001b641`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18001b6e8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18001b781`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18001b861`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        bool *a4)
{
  __int64 v7; // rdx
  int v8; // ebx
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
  int IsEmpty; // eax
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  int *v28; // [rsp+38h] [rbp-C8h]
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  char v30; // [rsp+48h] [rbp-B8h]
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v32[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+258h] [rbp+158h]
  __int64 v34; // [rsp+260h] [rbp+160h]
  _BYTE *v35; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( !a2 )
  {
    v7 = 153;
LABEL_3:
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)0x80070057LL,
      v25[0]);
    return (unsigned int)v8;
  }
  if ( !a3 )
  {
    v7 = 154;
    goto LABEL_3;
  }
  v10 = *(_QWORD *)a1;
  v28 = v25;
  *(_QWORD *)v25 = 0;
  v29 = 0;
  v30 = 1;
  v8 = SRCacheContext_Open(v10, L"PackageUser\\Index\\UserAndPackage", 0, &v29);
  if ( v30 )
  {
    v11 = *(_QWORD *)v28;
    *(_QWORD *)v28 = v29;
    if ( v11 )
      SRCacheContext_Close(v11);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v25[0]);
    v12 = 158;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v25[0]);
LABEL_13:
    v13 = *(_QWORD *)v25;
    *(_QWORD *)v25 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v25 )
  {
    v8 = -2140733422;
    v12 = 159;
    goto LABEL_12;
  }
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  v33 = 0;
  v35 = v32;
  v34 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, a2);
  if ( v8 < 0 )
  {
    v15 = 162;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v25[0]);
LABEL_20:
    v16 = v31;
    v31 = 0;
    if ( v16 )
      SRCache_Free(v16);
    goto LABEL_13;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, v14);
  if ( v8 < 0 )
  {
    v15 = 163;
    goto LABEL_19;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, a3);
  if ( v8 < 0 )
  {
    v15 = 164;
    goto LABEL_19;
  }
  v28 = (int *)&v26;
  v26 = 0;
  v29 = 0;
  v30 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v25, v35, 0, &v29);
  if ( v30 )
  {
    v17 = *(_QWORD *)v28;
    *(_QWORD *)v28 = v29;
    if ( v17 )
      SRCacheContext_Close(v17);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v25[0]);
    v18 = 168;
    goto LABEL_31;
  }
  if ( v26 )
  {
    v27 = 0;
    IsEmpty = SRCacheContext_IsEmpty(v26, &v27);
    v8 = IsEmpty;
    if ( IsEmpty < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B8,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)IsEmpty,
        v25[0]);
      v18 = 172;
      goto LABEL_31;
    }
    *a4 = v27 == 0;
  }
  v21 = SRCacheContext_AddToCache(*(_QWORD *)v25, L"PackageUser\\Index\\UserAndPackage");
  v8 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v21,
      v25[0]);
    v18 = 176;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v25[0]);
    v19 = v26;
    v26 = 0;
    if ( v19 )
      SRCacheContext_Close(v19);
    goto LABEL_20;
  }
  v22 = v26;
  v26 = 0;
  if ( v22 )
    SRCacheContext_Close(v22);
  v23 = v31;
  v31 = 0;
  if ( v23 )
    SRCache_Free(v23);
  v24 = *(_QWORD *)v25;
  *(_QWORD *)v25 = 0;
  if ( v24 )
    SRCacheContext_Close(v24);
  return 0;
}

```

## disassembly

```asm
0x18001b5f8  push    rbp
0x18001b5fa  push    rbx
0x18001b5fb  push    rsi
0x18001b5fc  push    rdi
0x18001b5fd  push    r14
0x18001b5ff  push    r15
0x18001b601  lea     rbp, [rsp-188h]
0x18001b609  sub     rsp, 288h
0x18001b610  mov     rax, cs:__security_cookie
0x18001b617  xor     rax, rsp
0x18001b61a  mov     [rbp+1B0h+var_40], rax
0x18001b621  xor     r15d, r15d
0x18001b624  mov     r14, r9
0x18001b627  mov     [r9], r15b
0x18001b62a  mov     rdi, r8
0x18001b62d  mov     rsi, rdx
0x18001b630  test    rdx, rdx
0x18001b633  jnz     short loc_18001B65C
0x18001b635  mov     edx, 99h; void *
0x18001b63a  mov     rcx, [rbp+1B8h]; this
0x18001b641  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b648  mov     ebx, 80070057h
0x18001b64d  mov     r9d, ebx; char *
0x18001b650  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b655  mov     eax, ebx
0x18001b657  jmp     loc_18001B960
0x18001b65c  test    rdi, rdi
0x18001b65f  jnz     short loc_18001B668
0x18001b661  mov     edx, 9Ah
0x18001b666  jmp     short loc_18001B63A
0x18001b668  mov     rcx, [rcx]
0x18001b66b  lea     rax, [rsp+2B0h+var_290]
0x18001b670  lea     r9, [rsp+2B0h+var_270]
0x18001b675  mov     [rsp+2B0h+var_278], rax
0x18001b67a  xor     r8d, r8d
0x18001b67d  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x18001b682  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x18001b689  mov     [rsp+2B0h+var_270], r15
0x18001b68e  mov     [rsp+2B0h+var_268], 1
0x18001b693  call    cs:__imp_SRCacheContext_Open
0x18001b699  mov     ebx, eax
0x18001b69b  cmp     [rsp+2B0h+var_268], r15b
0x18001b6a0  jz      short loc_18001B6BD
0x18001b6a2  mov     r8, [rsp+2B0h+var_278]
0x18001b6a7  mov     rdx, [rsp+2B0h+var_270]
0x18001b6ac  mov     rcx, [r8]
0x18001b6af  mov     [r8], rdx
0x18001b6b2  test    rcx, rcx
0x18001b6b5  jz      short loc_18001B6BD
0x18001b6b7  call    cs:__imp_SRCacheContext_Close
0x18001b6bd  test    ebx, ebx
0x18001b6bf  jns     short loc_18001B715
0x18001b6c1  mov     rcx, [rbp+1B8h]; this
0x18001b6c8  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b6cf  mov     r9d, ebx; char *
0x18001b6d2  mov     edx, 18Ch; void *
0x18001b6d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b6dc  mov     edx, 9Eh; void *
0x18001b6e1  mov     rcx, [rbp+1B8h]; this
0x18001b6e8  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b6ef  mov     r9d, ebx; char *
0x18001b6f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b6f7  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001b6fc  mov     qword ptr [rsp+2B0h+var_290], r15
0x18001b701  test    rcx, rcx
0x18001b704  jz      loc_18001B655
0x18001b70a  call    cs:__imp_SRCacheContext_Close
0x18001b710  jmp     loc_18001B655
0x18001b715  cmp     qword ptr [rsp+2B0h+var_290], r15
0x18001b71a  setnz   al
0x18001b71d  test    al, al
0x18001b71f  jnz     short loc_18001B72D
0x18001b721  mov     ebx, 80670012h
0x18001b726  mov     edx, 9Fh
0x18001b72b  jmp     short loc_18001B6E1
0x18001b72d  xor     edx, edx; Val
0x18001b72f  mov     [rsp+2B0h+var_260], r15
0x18001b734  mov     r8d, 200h; Size
0x18001b73a  lea     rcx, [rsp+2B0h+var_258]; void *
0x18001b73f  call    memset_0
0x18001b744  lea     rax, [rsp+2B0h+var_258]
0x18001b749  mov     [rbp+1B0h+var_58], r15
0x18001b750  mov     rdx, rsi; unsigned __int64
0x18001b753  mov     [rbp+1B0h+var_48], rax
0x18001b75a  lea     rcx, [rsp+2B0h+var_260]; this
0x18001b75f  mov     [rbp+1B0h+var_50], 100h
0x18001b76a  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001b76f  mov     ebx, eax
0x18001b771  test    eax, eax
0x18001b773  jns     short loc_18001B7AE
0x18001b775  mov     edx, 0A2h; void *
0x18001b77a  mov     rcx, [rbp+1B8h]; this
0x18001b781  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b788  mov     r9d, ebx; char *
0x18001b78b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b790  mov     rcx, [rsp+2B0h+var_260]
0x18001b795  mov     [rsp+2B0h+var_260], r15
0x18001b79a  test    rcx, rcx
0x18001b79d  jz      loc_18001B6F7
0x18001b7a3  call    cs:__imp_SRCache_Free
0x18001b7a9  jmp     loc_18001B6F7
0x18001b7ae  lea     rcx, [rsp+2B0h+var_260]; this
0x18001b7b3  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18001b7b8  mov     ebx, eax
0x18001b7ba  test    eax, eax
0x18001b7bc  jns     short loc_18001B7C5
0x18001b7be  mov     edx, 0A3h
0x18001b7c3  jmp     short loc_18001B77A
0x18001b7c5  mov     rdx, rdi; unsigned __int64
0x18001b7c8  lea     rcx, [rsp+2B0h+var_260]; this
0x18001b7cd  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001b7d2  mov     ebx, eax
0x18001b7d4  test    eax, eax
0x18001b7d6  jns     short loc_18001B7DF
0x18001b7d8  mov     edx, 0A4h
0x18001b7dd  jmp     short loc_18001B77A
0x18001b7df  mov     rdx, [rbp+1B0h+var_48]
0x18001b7e6  lea     rax, [rsp+2B0h+var_288]
0x18001b7eb  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001b7f0  lea     r9, [rsp+2B0h+var_270]
0x18001b7f5  xor     r8d, r8d
0x18001b7f8  mov     [rsp+2B0h+var_278], rax
0x18001b7fd  mov     [rsp+2B0h+var_288], r15
0x18001b802  mov     [rsp+2B0h+var_270], r15
0x18001b807  mov     [rsp+2B0h+var_268], 1
0x18001b80c  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001b812  mov     ebx, eax
0x18001b814  cmp     [rsp+2B0h+var_268], r15b
0x18001b819  jz      short loc_18001B836
0x18001b81b  mov     r8, [rsp+2B0h+var_278]
0x18001b820  mov     rdx, [rsp+2B0h+var_270]
0x18001b825  mov     rcx, [r8]
0x18001b828  mov     [r8], rdx
0x18001b82b  test    rcx, rcx
0x18001b82e  jz      short loc_18001B836
0x18001b830  call    cs:__imp_SRCacheContext_Close
0x18001b836  test    ebx, ebx
0x18001b838  jns     short loc_18001B88E
0x18001b83a  mov     rcx, [rbp+1B8h]; this
0x18001b841  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b848  mov     r9d, ebx; char *
0x18001b84b  mov     edx, 1B0h; void *
0x18001b850  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b855  mov     edx, 0A8h; void *
0x18001b85a  mov     rcx, [rbp+1B8h]; this
0x18001b861  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b868  mov     r9d, ebx; char *
0x18001b86b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b870  mov     rcx, [rsp+2B0h+var_288]
0x18001b875  mov     [rsp+2B0h+var_288], r15
0x18001b87a  test    rcx, rcx
0x18001b87d  jz      loc_18001B790
0x18001b883  call    cs:__imp_SRCacheContext_Close
0x18001b889  jmp     loc_18001B790
0x18001b88e  mov     rcx, [rsp+2B0h+var_288]
0x18001b893  test    rcx, rcx
0x18001b896  setnz   al
0x18001b899  test    al, al
0x18001b89b  jz      short loc_18001B8E2
0x18001b89d  lea     rdx, [rsp+2B0h+var_280]
0x18001b8a2  mov     [rsp+2B0h+var_280], r15d
0x18001b8a7  call    cs:__imp_SRCacheContext_IsEmpty
0x18001b8ad  mov     ebx, eax
0x18001b8af  test    eax, eax
0x18001b8b1  jns     short loc_18001B8D5
0x18001b8b3  mov     rcx, [rbp+1B8h]; this
0x18001b8ba  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b8c1  mov     r9d, eax; char *
0x18001b8c4  mov     edx, 2B8h; void *
0x18001b8c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b8ce  mov     edx, 0ACh
0x18001b8d3  jmp     short loc_18001B85A
0x18001b8d5  cmp     [rsp+2B0h+var_280], r15d
0x18001b8da  setnz   al
0x18001b8dd  xor     al, 1
0x18001b8df  mov     [r14], al
0x18001b8e2  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001b8e7  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x18001b8ee  call    cs:__imp_SRCacheContext_AddToCache
0x18001b8f4  mov     ebx, eax
0x18001b8f6  test    eax, eax
0x18001b8f8  jns     short loc_18001B91F
0x18001b8fa  mov     rcx, [rbp+1B8h]; this
0x18001b901  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b908  mov     r9d, eax; char *
0x18001b90b  mov     edx, 1A6h; void *
0x18001b910  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b915  mov     edx, 0B0h
0x18001b91a  jmp     loc_18001B85A
0x18001b91f  mov     rcx, [rsp+2B0h+var_288]
0x18001b924  mov     [rsp+2B0h+var_288], r15
0x18001b929  test    rcx, rcx
0x18001b92c  jz      short loc_18001B934
0x18001b92e  call    cs:__imp_SRCacheContext_Close
0x18001b934  mov     rcx, [rsp+2B0h+var_260]
0x18001b939  mov     [rsp+2B0h+var_260], r15
0x18001b93e  test    rcx, rcx
0x18001b941  jz      short loc_18001B949
0x18001b943  call    cs:__imp_SRCache_Free
0x18001b949  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001b94e  mov     qword ptr [rsp+2B0h+var_290], r15
0x18001b953  test    rcx, rcx
0x18001b956  jz      short loc_18001B95E
0x18001b958  call    cs:__imp_SRCacheContext_Close
0x18001b95e  xor     eax, eax
0x18001b960  mov     rcx, [rbp+1B0h+var_40]
0x18001b967  xor     rcx, rsp; StackCookie
0x18001b96a  call    __security_check_cookie
0x18001b96f  add     rsp, 288h
0x18001b976  pop     r15
0x18001b978  pop     r14
0x18001b97a  pop     rdi
0x18001b97b  pop     rsi
0x18001b97c  pop     rbx
0x18001b97d  pop     rbp
0x18001b97e  retn
```
