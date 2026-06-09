# StateRepository::Cache::Entity::Application_NoThrow::GetByPackageAndPackageRelativeApplicationId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)

- ea: `0x18001bc18`
- end: `0x18001bede`
- name: `?GetByPackageAndPackageRelativeApplicationId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z`
- size: `710`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001aa0c`

## callees

- `0x180018be0`
- `0x180019f90`
- `0x18001a1f0`
- `0x18001bc18`
- `0x18001bee4`
- `0x18001c314`
- `0x180032490`
- `0x18003ba54`
- `0x18004b094`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001bcd4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001be2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001be8d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001beb7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001bcd4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001be2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001be8d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001beb7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001bdce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001bdce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bd65`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bea2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bd65`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bea2`

## string_xrefs

- `0x18001bdeb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001bc5c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18001bcb6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18001bd43`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18001be0b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::GetByPackageAndPackageRelativeApplicationId(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        __int64 *a4)
{
  int v7; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned __int16 v11; // dx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // [rsp+20h] [rbp-E0h]
  int *v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  char v26; // [rsp+58h] [rbp-A8h]
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+268h] [rbp+168h]
  __int64 v30; // [rsp+270h] [rbp+170h]
  _BYTE *v31; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *a4 = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      v19);
    return (unsigned int)v7;
  }
  LOBYTE(v21) = 0;
  v20 = &v21;
  v22 = 0;
  v7 = StateRepository::Cache::Context_NoThrow::Open(
         &v22,
         a1,
         L"Application\\Index\\PackageAndPackageRelativeApplicationId");
  if ( v7 < 0 )
  {
    v9 = 363;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v7,
      (int)&v21);
LABEL_7:
    v10 = v22;
    v22 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v7;
  }
  if ( !(_BYTE)v21 )
  {
    v7 = -2140733422;
    v9 = 364;
    goto LABEL_6;
  }
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v29 = 0;
  v31 = v28;
  v30 = 256;
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a2);
  if ( v7 < 0 )
  {
    v12 = 367;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v7,
      (int)&v21);
LABEL_14:
    v13 = v27;
    v27 = 0;
    if ( v13 )
      SRCache_Free(v13);
    goto LABEL_7;
  }
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, v11);
  if ( v7 < 0 )
  {
    v12 = 368;
    goto LABEL_13;
  }
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a3);
  if ( v7 < 0 )
  {
    v12 = 369;
    goto LABEL_13;
  }
  v24 = &v23;
  v23 = 0;
  v25 = 0;
  v26 = 1;
  v7 = SRCacheContext_OpenSubContext(v22, v31, 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v24);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v7,
      (int)&v21);
    v14 = 373;
    goto LABEL_22;
  }
  if ( v23 )
  {
    v7 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)&v23, 0, a4);
    if ( v7 < 0 )
    {
      v14 = 376;
      goto LABEL_22;
    }
  }
  v7 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v22,
         L"Application\\Index\\PackageAndPackageRelativeApplicationId");
  if ( v7 < 0 )
  {
    v14 = 379;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v7,
      (int)v20);
    v15 = v23;
    v23 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
    goto LABEL_14;
  }
  v16 = v23;
  v23 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  v17 = v27;
  v27 = 0;
  if ( v17 )
    SRCache_Free(v17);
  v18 = v22;
  v22 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return 0;
}

```

## disassembly

```asm
0x18001bc18  push    rbp
0x18001bc1a  push    rbx
0x18001bc1b  push    rsi
0x18001bc1c  push    rdi
0x18001bc1d  push    r14
0x18001bc1f  push    r15
0x18001bc21  lea     rbp, [rsp-198h]
0x18001bc29  sub     rsp, 298h
0x18001bc30  mov     rax, cs:__security_cookie
0x18001bc37  xor     rax, rsp
0x18001bc3a  mov     [rbp+1C0h+var_40], rax
0x18001bc41  xor     r15d, r15d
0x18001bc44  mov     rsi, r9
0x18001bc47  mov     [r9], r15
0x18001bc4a  mov     r14, r8
0x18001bc4d  mov     rdi, rdx
0x18001bc50  test    rdx, rdx
0x18001bc53  jnz     short loc_18001BC7C
0x18001bc55  mov     rcx, [rbp+1C8h]; this
0x18001bc5c  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001bc63  mov     ebx, 80070057h
0x18001bc68  mov     edx, 167h; void *
0x18001bc6d  mov     r9d, ebx; char *
0x18001bc70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bc75  mov     eax, ebx
0x18001bc77  jmp     loc_18001BEBF
0x18001bc7c  lea     rax, [rsp+2C0h+var_290]
0x18001bc81  mov     byte ptr [rsp+2C0h+var_290], r15b
0x18001bc86  mov     rdx, rcx
0x18001bc89  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x18001bc8e  lea     rcx, [rsp+2C0h+var_288]
0x18001bc93  mov     [rsp+2C0h+var_288], r15
0x18001bc98  lea     r8, aApplicationInd; "Application\\Index\\PackageAndPackageRe"...
0x18001bc9f  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18001bca4  mov     ebx, eax
0x18001bca6  test    eax, eax
0x18001bca8  jns     short loc_18001BCDC
0x18001bcaa  mov     edx, 16Bh; void *
0x18001bcaf  mov     rcx, [rbp+1C8h]; this
0x18001bcb6  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001bcbd  mov     r9d, ebx; char *
0x18001bcc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bcc5  mov     rcx, [rsp+2C0h+var_288]
0x18001bcca  mov     [rsp+2C0h+var_288], r15
0x18001bccf  test    rcx, rcx
0x18001bcd2  jz      short loc_18001BC75
0x18001bcd4  call    cs:__imp_SRCacheContext_Close
0x18001bcda  jmp     short loc_18001BC75
0x18001bcdc  cmp     byte ptr [rsp+2C0h+var_290], r15b
0x18001bce1  jnz     short loc_18001BCEF
0x18001bce3  mov     ebx, 80670012h
0x18001bce8  mov     edx, 16Ch
0x18001bced  jmp     short loc_18001BCAF
0x18001bcef  xor     edx, edx; Val
0x18001bcf1  mov     [rsp+2C0h+var_260], r15
0x18001bcf6  mov     r8d, 200h; Size
0x18001bcfc  lea     rcx, [rsp+2C0h+var_258]; void *
0x18001bd01  call    memset_0
0x18001bd06  lea     rax, [rsp+2C0h+var_258]
0x18001bd0b  mov     [rbp+1C0h+var_58], r15
0x18001bd12  mov     rdx, rdi; unsigned __int64
0x18001bd15  mov     [rbp+1C0h+var_48], rax
0x18001bd1c  lea     rcx, [rsp+2C0h+var_260]; this
0x18001bd21  mov     [rbp+1C0h+var_50], 100h
0x18001bd2c  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001bd31  mov     ebx, eax
0x18001bd33  test    eax, eax
0x18001bd35  jns     short loc_18001BD70
0x18001bd37  mov     edx, 16Fh; void *
0x18001bd3c  mov     rcx, [rbp+1C8h]; this
0x18001bd43  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001bd4a  mov     r9d, ebx; char *
0x18001bd4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bd52  mov     rcx, [rsp+2C0h+var_260]
0x18001bd57  mov     [rsp+2C0h+var_260], r15
0x18001bd5c  test    rcx, rcx
0x18001bd5f  jz      loc_18001BCC5
0x18001bd65  call    cs:__imp_SRCache_Free
0x18001bd6b  jmp     loc_18001BCC5
0x18001bd70  lea     rcx, [rsp+2C0h+var_260]; this
0x18001bd75  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18001bd7a  mov     ebx, eax
0x18001bd7c  test    eax, eax
0x18001bd7e  jns     short loc_18001BD87
0x18001bd80  mov     edx, 170h
0x18001bd85  jmp     short loc_18001BD3C
0x18001bd87  mov     rdx, r14; unsigned __int16 *
0x18001bd8a  lea     rcx, [rsp+2C0h+var_260]; this
0x18001bd8f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18001bd94  mov     ebx, eax
0x18001bd96  test    eax, eax
0x18001bd98  jns     short loc_18001BDA1
0x18001bd9a  mov     edx, 171h
0x18001bd9f  jmp     short loc_18001BD3C
0x18001bda1  mov     rdx, [rbp+1C0h+var_48]
0x18001bda8  lea     rax, [rsp+2C0h+var_280]
0x18001bdad  mov     rcx, [rsp+2C0h+var_288]
0x18001bdb2  lea     r9, [rsp+2C0h+var_270]
0x18001bdb7  xor     r8d, r8d
0x18001bdba  mov     [rsp+2C0h+var_278], rax
0x18001bdbf  mov     [rsp+2C0h+var_280], r15
0x18001bdc4  mov     [rsp+2C0h+var_270], r15
0x18001bdc9  mov     [rsp+2C0h+var_268], 1
0x18001bdce  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001bdd4  lea     rcx, [rsp+2C0h+var_278]
0x18001bdd9  mov     ebx, eax
0x18001bddb  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001bde0  test    ebx, ebx
0x18001bde2  jns     short loc_18001BE38
0x18001bde4  mov     rcx, [rbp+1C8h]; this
0x18001bdeb  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001bdf2  mov     r9d, ebx; char *
0x18001bdf5  mov     edx, 1B0h; void *
0x18001bdfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bdff  mov     edx, 175h; void *
0x18001be04  mov     rcx, [rbp+1C8h]; this
0x18001be0b  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001be12  mov     r9d, ebx; char *
0x18001be15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001be1a  mov     rcx, [rsp+2C0h+var_280]
0x18001be1f  mov     [rsp+2C0h+var_280], r15
0x18001be24  test    rcx, rcx
0x18001be27  jz      loc_18001BD52
0x18001be2d  call    cs:__imp_SRCacheContext_Close
0x18001be33  jmp     loc_18001BD52
0x18001be38  cmp     [rsp+2C0h+var_280], r15
0x18001be3d  setnz   al
0x18001be40  test    al, al
0x18001be42  jz      short loc_18001BE60
0x18001be44  mov     r8, rsi; __int64 *
0x18001be47  lea     rcx, [rsp+2C0h+var_280]; this
0x18001be4c  xor     edx, edx; int
0x18001be4e  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18001be53  mov     ebx, eax
0x18001be55  test    eax, eax
0x18001be57  jns     short loc_18001BE60
0x18001be59  mov     edx, 178h
0x18001be5e  jmp     short loc_18001BE04
0x18001be60  lea     rdx, aApplicationInd; "Application\\Index\\PackageAndPackageRe"...
0x18001be67  lea     rcx, [rsp+2C0h+var_288]; this
0x18001be6c  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001be71  mov     ebx, eax
0x18001be73  test    eax, eax
0x18001be75  jns     short loc_18001BE7E
0x18001be77  mov     edx, 17Bh
0x18001be7c  jmp     short loc_18001BE04
0x18001be7e  mov     rcx, [rsp+2C0h+var_280]
0x18001be83  mov     [rsp+2C0h+var_280], r15
0x18001be88  test    rcx, rcx
0x18001be8b  jz      short loc_18001BE93
0x18001be8d  call    cs:__imp_SRCacheContext_Close
0x18001be93  mov     rcx, [rsp+2C0h+var_260]
0x18001be98  mov     [rsp+2C0h+var_260], r15
0x18001be9d  test    rcx, rcx
0x18001bea0  jz      short loc_18001BEA8
0x18001bea2  call    cs:__imp_SRCache_Free
0x18001bea8  mov     rcx, [rsp+2C0h+var_288]
0x18001bead  mov     [rsp+2C0h+var_288], r15
0x18001beb2  test    rcx, rcx
0x18001beb5  jz      short loc_18001BEBD
0x18001beb7  call    cs:__imp_SRCacheContext_Close
0x18001bebd  xor     eax, eax
0x18001bebf  mov     rcx, [rbp+1C0h+var_40]
0x18001bec6  xor     rcx, rsp; StackCookie
0x18001bec9  call    __security_check_cookie
0x18001bece  add     rsp, 298h
0x18001bed5  pop     r15
0x18001bed7  pop     r14
0x18001bed9  pop     rdi
0x18001beda  pop     rsi
0x18001bedb  pop     rbx
0x18001bedc  pop     rbp
0x18001bedd  retn
```
