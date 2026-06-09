# StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x180016814`
- end: `0x180016afd`
- name: `?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `745`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18005ac6c`

## callees

- `0x180016814`
- `0x180016b10`
- `0x180022164`
- `0x180030914`
- `0x18003e210`
- `0x18003eca8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800169b8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800169b8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180016872`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180016872`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180016896`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800168e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800169dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180016a2f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180016aae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180016ad8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180016896`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800168e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800169dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180016a2f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180016aae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180016ad8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016980`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016ac3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016980`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016ac3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180016a6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180016a6e`

## string_xrefs

- `0x1800168c7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180016959`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180016a0d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800168a7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800169ed`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180016a81`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  int *v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  char v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+258h] [rbp+158h]
  __int64 v28; // [rsp+260h] [rbp+160h]
  _BYTE *v29; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v24 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v20 = 0;
  v22 = v20;
  v23 = 0;
  v6 = SRCacheContext_Open(v3, L"PackageFamily\\Index\\PackageFamilyName", 0, &v23);
  if ( v24 )
  {
    v7 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
    if ( v7 )
      SRCacheContext_Close(v7);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
    v8 = 193;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
LABEL_7:
    v9 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    return (unsigned int)v6;
  }
  if ( !*(_QWORD *)v20 )
  {
    v6 = -2140733422;
    v8 = 194;
    goto LABEL_6;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v29 = v26;
  v28 = 256;
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a2);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v11,
      v20[0]);
LABEL_14:
    v12 = v25;
    v25 = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_7;
  }
  v22 = (int *)&v21;
  v21 = 0;
  v23 = 0;
  v24 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v20, v29, 0, &v23);
  if ( v24 )
  {
    v13 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
    if ( v13 )
      SRCacheContext_Close(v13);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
    v14 = 201;
    goto LABEL_21;
  }
  if ( v21 )
  {
    v6 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)&v21, 0, a3);
    if ( v6 < 0 )
    {
      v14 = 204;
      goto LABEL_21;
    }
  }
  v16 = SRCacheContext_AddToCache(*(_QWORD *)v20, L"PackageFamily\\Index\\PackageFamilyName");
  v6 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      v20[0]);
    v14 = 207;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
    v15 = v21;
    v21 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
    goto LABEL_14;
  }
  v17 = v21;
  v21 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  v18 = v25;
  v25 = 0;
  if ( v18 )
    SRCache_Free();
  v19 = *(_QWORD *)v20;
  *(_QWORD *)v20 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  return 0;
}

```

## disassembly

```asm
0x180016814  push    rbp
0x180016816  push    rbx
0x180016817  push    rsi
0x180016818  push    rdi
0x180016819  push    r14
0x18001681b  lea     rbp, [rsp-180h]
0x180016823  sub     rsp, 280h
0x18001682a  mov     rax, cs:__security_cookie
0x180016831  xor     rax, rsp
0x180016834  mov     [rbp+1A0h+var_30], rax
0x18001683b  xor     r14d, r14d
0x18001683e  mov     [rsp+2A0h+var_260], 1
0x180016843  mov     [r8], r14
0x180016846  lea     rax, [rsp+2A0h+var_280]
0x18001684b  mov     rcx, [rcx]
0x18001684e  lea     r9, [rsp+2A0h+var_268]
0x180016853  mov     rdi, r8
0x180016856  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18001685b  mov     rsi, rdx
0x18001685e  mov     [rsp+2A0h+var_270], rax
0x180016863  xor     r8d, r8d
0x180016866  mov     [rsp+2A0h+var_268], r14
0x18001686b  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x180016872  call    cs:__imp_SRCacheContext_Open
0x180016878  mov     ebx, eax
0x18001687a  cmp     [rsp+2A0h+var_260], r14b
0x18001687f  jz      short loc_18001689C
0x180016881  mov     r8, [rsp+2A0h+var_270]
0x180016886  mov     rdx, [rsp+2A0h+var_268]
0x18001688b  mov     rcx, [r8]
0x18001688e  mov     [r8], rdx
0x180016891  test    rcx, rcx
0x180016894  jz      short loc_18001689C
0x180016896  call    cs:__imp_SRCacheContext_Close
0x18001689c  test    ebx, ebx
0x18001689e  jns     short loc_1800168F2
0x1800168a0  mov     rcx, [rbp+1A8h]; this
0x1800168a7  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800168ae  mov     r9d, ebx; char *
0x1800168b1  mov     edx, 18Ch; void *
0x1800168b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800168bb  mov     edx, 0C1h; void *
0x1800168c0  mov     rcx, [rbp+1A8h]; this
0x1800168c7  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800168ce  mov     r9d, ebx; char *
0x1800168d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800168d6  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800168db  mov     qword ptr [rsp+2A0h+var_280], r14
0x1800168e0  test    rcx, rcx
0x1800168e3  jz      short loc_1800168EB
0x1800168e5  call    cs:__imp_SRCacheContext_Close
0x1800168eb  mov     eax, ebx
0x1800168ed  jmp     loc_180016AE0
0x1800168f2  cmp     qword ptr [rsp+2A0h+var_280], r14
0x1800168f7  setnz   al
0x1800168fa  test    al, al
0x1800168fc  jnz     short loc_18001690A
0x1800168fe  mov     ebx, 80670012h
0x180016903  mov     edx, 0C2h
0x180016908  jmp     short loc_1800168C0
0x18001690a  xor     edx, edx; Val
0x18001690c  mov     [rsp+2A0h+var_250], r14
0x180016911  mov     r8d, 200h; Size
0x180016917  lea     rcx, [rsp+2A0h+var_248]; void *
0x18001691c  call    memset_0
0x180016921  lea     rax, [rsp+2A0h+var_248]
0x180016926  mov     [rbp+1A0h+var_48], r14
0x18001692d  mov     rdx, rsi; unsigned __int16 *
0x180016930  mov     [rbp+1A0h+var_38], rax
0x180016937  lea     rcx, [rsp+2A0h+var_250]; this
0x18001693c  mov     [rbp+1A0h+var_40], 100h
0x180016947  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18001694c  mov     ebx, eax
0x18001694e  test    eax, eax
0x180016950  jns     short loc_18001698B
0x180016952  mov     rcx, [rbp+1A8h]; this
0x180016959  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180016960  mov     r9d, eax; char *
0x180016963  mov     edx, 0C5h; void *
0x180016968  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001696d  mov     rcx, [rsp+2A0h+var_250]
0x180016972  mov     [rsp+2A0h+var_250], r14
0x180016977  test    rcx, rcx
0x18001697a  jz      loc_1800168D6
0x180016980  call    cs:__imp_SRCache_Free
0x180016986  jmp     loc_1800168D6
0x18001698b  mov     rdx, [rbp+1A0h+var_38]
0x180016992  lea     rax, [rsp+2A0h+var_278]
0x180016997  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001699c  lea     r9, [rsp+2A0h+var_268]
0x1800169a1  xor     r8d, r8d
0x1800169a4  mov     [rsp+2A0h+var_270], rax
0x1800169a9  mov     [rsp+2A0h+var_278], r14
0x1800169ae  mov     [rsp+2A0h+var_268], r14
0x1800169b3  mov     [rsp+2A0h+var_260], 1
0x1800169b8  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800169be  mov     ebx, eax
0x1800169c0  cmp     [rsp+2A0h+var_260], r14b
0x1800169c5  jz      short loc_1800169E2
0x1800169c7  mov     r8, [rsp+2A0h+var_270]
0x1800169cc  mov     rdx, [rsp+2A0h+var_268]
0x1800169d1  mov     rcx, [r8]
0x1800169d4  mov     [r8], rdx
0x1800169d7  test    rcx, rcx
0x1800169da  jz      short loc_1800169E2
0x1800169dc  call    cs:__imp_SRCacheContext_Close
0x1800169e2  test    ebx, ebx
0x1800169e4  jns     short loc_180016A3A
0x1800169e6  mov     rcx, [rbp+1A8h]; this
0x1800169ed  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800169f4  mov     r9d, ebx; char *
0x1800169f7  mov     edx, 1B0h; void *
0x1800169fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a01  mov     edx, 0C9h; void *
0x180016a06  mov     rcx, [rbp+1A8h]; this
0x180016a0d  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180016a14  mov     r9d, ebx; char *
0x180016a17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a1c  mov     rcx, [rsp+2A0h+var_278]
0x180016a21  mov     [rsp+2A0h+var_278], r14
0x180016a26  test    rcx, rcx
0x180016a29  jz      loc_18001696D
0x180016a2f  call    cs:__imp_SRCacheContext_Close
0x180016a35  jmp     loc_18001696D
0x180016a3a  cmp     [rsp+2A0h+var_278], r14
0x180016a3f  setnz   al
0x180016a42  test    al, al
0x180016a44  jz      short loc_180016A62
0x180016a46  mov     r8, rdi; __int64 *
0x180016a49  lea     rcx, [rsp+2A0h+var_278]; this
0x180016a4e  xor     edx, edx; int
0x180016a50  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x180016a55  mov     ebx, eax
0x180016a57  test    eax, eax
0x180016a59  jns     short loc_180016A62
0x180016a5b  mov     edx, 0CCh
0x180016a60  jmp     short loc_180016A06
0x180016a62  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180016a67  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x180016a6e  call    cs:__imp_SRCacheContext_AddToCache
0x180016a74  mov     ebx, eax
0x180016a76  test    eax, eax
0x180016a78  jns     short loc_180016A9F
0x180016a7a  mov     rcx, [rbp+1A8h]; this
0x180016a81  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180016a88  mov     r9d, eax; char *
0x180016a8b  mov     edx, 1A6h; void *
0x180016a90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a95  mov     edx, 0CFh
0x180016a9a  jmp     loc_180016A06
0x180016a9f  mov     rcx, [rsp+2A0h+var_278]
0x180016aa4  mov     [rsp+2A0h+var_278], r14
0x180016aa9  test    rcx, rcx
0x180016aac  jz      short loc_180016AB4
0x180016aae  call    cs:__imp_SRCacheContext_Close
0x180016ab4  mov     rcx, [rsp+2A0h+var_250]
0x180016ab9  mov     [rsp+2A0h+var_250], r14
0x180016abe  test    rcx, rcx
0x180016ac1  jz      short loc_180016AC9
0x180016ac3  call    cs:__imp_SRCache_Free
0x180016ac9  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180016ace  mov     qword ptr [rsp+2A0h+var_280], r14
0x180016ad3  test    rcx, rcx
0x180016ad6  jz      short loc_180016ADE
0x180016ad8  call    cs:__imp_SRCacheContext_Close
0x180016ade  xor     eax, eax
0x180016ae0  mov     rcx, [rbp+1A0h+var_30]
0x180016ae7  xor     rcx, rsp; StackCookie
0x180016aea  call    __security_check_cookie
0x180016aef  add     rsp, 280h
0x180016af6  pop     r14
0x180016af8  pop     rdi
0x180016af9  pop     rsi
0x180016afa  pop     rbx
0x180016afb  pop     rbp
0x180016afc  retn
```
