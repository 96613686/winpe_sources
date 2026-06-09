# StateRepository::Cache::Entity::PackageExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)

- ea: `0x1800797c8`
- end: `0x180079a8f`
- name: `?Get@PackageExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `711`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180078fd0`

## callees

- `0x180004ca0`
- `0x180005758`
- `0x18000b064`
- `0x180078f4c`
- `0x1800797c8`
- `0x18007a43c`
- `0x18007a754`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180079a03`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180079a03`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079970`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800799d3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079970`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800799d3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079985`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800799b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800799e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079a61`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079985`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800799b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800799e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079a61`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18007991b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18007991b`

## string_xrefs

- `0x180079932`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180079a16`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180079810`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x18007986d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x180079955`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x180079997`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x180079a31`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x18007984c`: `PackageExtension\Data`
- `0x180079914`: `PackageExtension\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExtension_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        bool *a5)
{
  unsigned int v7; // ebx
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int Field_UInt32; // eax
  bool v25[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v29[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+248h] [rbp+148h]
  __int64 v31; // [rsp+250h] [rbp+150h]
  wchar_t *v32; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x113,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)0x80070057LL,
      *(int *)v25);
    return v7;
  }
  v27 = 0;
  v26 = 0;
  v25[0] = 0;
  v9 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v26,
         a1,
         L"PackageExtension\\Data",
         v25);
  v7 = v9;
  if ( v9 < 0 )
  {
    v10 = (unsigned int)v9;
    v11 = 317;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)v10,
      *(int *)v25);
LABEL_17:
    v18 = v26;
    v26 = 0;
    if ( v18 )
      SRCacheContext_Close();
    v19 = 278;
    goto LABEL_20;
  }
  if ( !v25[0] )
  {
    v7 = -2140733422;
    v11 = 318;
    v10 = 2154233874LL;
    goto LABEL_6;
  }
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v30 = 0;
  v32 = (wchar_t *)v29;
  v31 = 256;
  v12 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, a2);
  v7 = v12;
  if ( v12 < 0 )
  {
    v13 = (unsigned int)v12;
    v14 = 321;
    goto LABEL_15;
  }
  v15 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
          (StateRepository::Cache::Context_NoThrow *)&v27,
          (struct StateRepository::Cache::Context_NoThrow *)&v26,
          v32,
          a5);
  v7 = v15;
  if ( v15 < 0 )
  {
    v13 = (unsigned int)v15;
    v14 = 322;
    goto LABEL_15;
  }
  v16 = SRCacheContext_AddToCache(v26, L"PackageExtension\\Data");
  v7 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      *(int *)v25);
    v13 = v7;
    v14 = 324;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)v13,
      *(int *)v25);
    v17 = v28;
    v28 = 0;
    if ( v17 )
      SRCache_Free();
    goto LABEL_17;
  }
  v21 = v28;
  v28 = 0;
  if ( v21 )
    SRCache_Free();
  v22 = v26;
  v26 = 0;
  if ( v22 )
    SRCacheContext_Close();
  v23 = v27;
  if ( *a5 )
  {
    Field_UInt32 = SRCacheContext_GetField_UInt32(v27, L"Package", a4 + 1);
    v7 = Field_UInt32;
    if ( Field_UInt32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)Field_UInt32,
        *(int *)v25);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39D,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
        (const char *)v7,
        *(int *)v25);
      v19 = 283;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
        (const char *)v7,
        *(int *)v25);
      v20 = v27;
      v27 = 0;
      if ( v20 )
        SRCacheContext_Close();
      return v7;
    }
    v23 = v27;
    *a4 = a2;
  }
  v27 = 0;
  if ( v23 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x1800797c8  mov     [rsp-8+arg_10], rbx
0x1800797cd  push    rbp
0x1800797ce  push    rsi
0x1800797cf  push    rdi
0x1800797d0  push    r14
0x1800797d2  push    r15
0x1800797d4  lea     rbp, [rsp-170h]
0x1800797dc  sub     rsp, 270h
0x1800797e3  mov     rax, cs:__security_cookie
0x1800797ea  xor     rax, rsp
0x1800797ed  mov     [rbp+190h+var_30], rax
0x1800797f4  mov     r14, [rbp+190h+arg_20]
0x1800797fb  xor     r15d, r15d
0x1800797fe  mov     rsi, r9
0x180079801  mov     rdi, rdx
0x180079804  test    rdx, rdx
0x180079807  jnz     short loc_180079830
0x180079809  mov     rcx, [rbp+198h]; this
0x180079810  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079817  mov     ebx, 80070057h
0x18007981c  mov     edx, 113h; void *
0x180079821  mov     r9d, ebx; char *
0x180079824  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079829  mov     eax, ebx
0x18007982b  jmp     loc_180079A69
0x180079830  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x180079833  mov     [rsp+290h+var_260], r15
0x180079838  lea     rcx, [rsp+290h+var_268]; this
0x18007983d  mov     [rsp+290h+var_268], r15
0x180079842  lea     r9, [rsp+290h+var_270]; bool *
0x180079847  mov     [rsp+290h+var_270], r15b; int
0x18007984c  lea     r8, aPackageextensi; "PackageExtension\\Data"
0x180079853  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEB_WAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,wchar_t const *,bool &)
0x180079858  mov     ebx, eax
0x18007985a  test    eax, eax
0x18007985c  jns     short loc_18007987E
0x18007985e  mov     r9d, eax; char *
0x180079861  mov     edx, 13Dh; void *
0x180079866  mov     rcx, [rbp+198h]; this
0x18007986d  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079874  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079879  jmp     loc_180079976
0x18007987e  cmp     [rsp+290h+var_270], r15b
0x180079883  jnz     short loc_180079894
0x180079885  mov     ebx, 80670012h
0x18007988a  mov     edx, 13Eh
0x18007988f  mov     r9d, ebx
0x180079892  jmp     short loc_180079866
0x180079894  xor     edx, edx; Val
0x180079896  mov     [rsp+290h+var_250], r15
0x18007989b  mov     r8d, 200h; Size
0x1800798a1  lea     rcx, [rsp+290h+var_248]; void *
0x1800798a6  call    memset_0
0x1800798ab  lea     rax, [rsp+290h+var_248]
0x1800798b0  mov     [rbp+190h+var_48], r15
0x1800798b7  mov     rdx, rdi; __int64
0x1800798ba  mov     [rbp+190h+var_38], rax
0x1800798c1  lea     rcx, [rsp+290h+var_250]; this
0x1800798c6  mov     [rbp+190h+var_40], 100h
0x1800798d1  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800798d6  mov     ebx, eax
0x1800798d8  test    eax, eax
0x1800798da  jns     short loc_1800798E6
0x1800798dc  mov     r9d, eax
0x1800798df  mov     edx, 141h
0x1800798e4  jmp     short loc_18007994E
0x1800798e6  mov     r8, [rbp+190h+var_38]; wchar_t *
0x1800798ed  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800798f2  mov     r9, r14; bool *
0x1800798f5  lea     rcx, [rsp+290h+var_260]; this
0x1800798fa  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEB_WAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,wchar_t const *,bool &)
0x1800798ff  mov     ebx, eax
0x180079901  test    eax, eax
0x180079903  jns     short loc_18007990F
0x180079905  mov     r9d, eax
0x180079908  mov     edx, 142h
0x18007990d  jmp     short loc_18007994E
0x18007990f  mov     rcx, [rsp+290h+var_268]
0x180079914  lea     rdx, aPackageextensi; "PackageExtension\\Data"
0x18007991b  call    cs:__imp_SRCacheContext_AddToCache
0x180079921  mov     ebx, eax
0x180079923  test    eax, eax
0x180079925  jns     loc_1800799C4
0x18007992b  mov     rcx, [rbp+198h]; this
0x180079932  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079939  mov     r9d, eax; char *
0x18007993c  mov     edx, 1A6h; void *
0x180079941  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079946  mov     r9d, ebx; char *
0x180079949  mov     edx, 144h; void *
0x18007994e  mov     rcx, [rbp+198h]; this
0x180079955  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007995c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079961  mov     rcx, [rsp+290h+var_250]
0x180079966  mov     [rsp+290h+var_250], r15
0x18007996b  test    rcx, rcx
0x18007996e  jz      short loc_180079976
0x180079970  call    cs:__imp_SRCache_Free
0x180079976  mov     rcx, [rsp+290h+var_268]
0x18007997b  mov     [rsp+290h+var_268], r15
0x180079980  test    rcx, rcx
0x180079983  jz      short loc_18007998B
0x180079985  call    cs:__imp_SRCacheContext_Close
0x18007998b  mov     edx, 116h; void *
0x180079990  mov     rcx, [rbp+198h]; this
0x180079997  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007999e  mov     r9d, ebx; char *
0x1800799a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800799a6  mov     rcx, [rsp+290h+var_260]
0x1800799ab  mov     [rsp+290h+var_260], r15
0x1800799b0  test    rcx, rcx
0x1800799b3  jz      loc_180079829
0x1800799b9  call    cs:__imp_SRCacheContext_Close
0x1800799bf  jmp     loc_180079829
0x1800799c4  mov     rcx, [rsp+290h+var_250]
0x1800799c9  mov     [rsp+290h+var_250], r15
0x1800799ce  test    rcx, rcx
0x1800799d1  jz      short loc_1800799D9
0x1800799d3  call    cs:__imp_SRCache_Free
0x1800799d9  mov     rcx, [rsp+290h+var_268]
0x1800799de  mov     [rsp+290h+var_268], r15
0x1800799e3  test    rcx, rcx
0x1800799e6  jz      short loc_1800799EE
0x1800799e8  call    cs:__imp_SRCacheContext_Close
0x1800799ee  mov     rcx, [rsp+290h+var_260]
0x1800799f3  cmp     [r14], r15b
0x1800799f6  jz      short loc_180079A57
0x1800799f8  lea     r8, [rsi+8]
0x1800799fc  lea     rdx, aPackage; "Package"
0x180079a03  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180079a09  mov     ebx, eax
0x180079a0b  test    eax, eax
0x180079a0d  jns     short loc_180079A4F
0x180079a0f  mov     rcx, [rbp+198h]; this
0x180079a16  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079a1d  mov     r9d, eax; char *
0x180079a20  mov     edx, 221h; void *
0x180079a25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079a2a  mov     rcx, [rbp+198h]; this
0x180079a31  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079a38  mov     r9d, ebx; char *
0x180079a3b  mov     edx, 39Dh; void *
0x180079a40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079a45  mov     edx, 11Bh
0x180079a4a  jmp     loc_180079990
0x180079a4f  mov     rcx, [rsp+290h+var_260]
0x180079a54  mov     [rsi], rdi
0x180079a57  mov     [rsp+290h+var_260], r15
0x180079a5c  test    rcx, rcx
0x180079a5f  jz      short loc_180079A67
0x180079a61  call    cs:__imp_SRCacheContext_Close
0x180079a67  xor     eax, eax
0x180079a69  mov     rcx, [rbp+190h+var_30]
0x180079a70  xor     rcx, rsp; StackCookie
0x180079a73  call    __security_check_cookie
0x180079a78  mov     rbx, [rsp+290h+arg_10]
0x180079a80  add     rsp, 270h
0x180079a87  pop     r15
0x180079a89  pop     r14
0x180079a8b  pop     rdi
0x180079a8c  pop     rsi
0x180079a8d  pop     rbp
0x180079a8e  retn
```
