# StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180004950`
- end: `0x180004ea7`
- name: `?Open@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `1367`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004814`

## callees

- `0x180004950`
- `0x180007c78`
- `0x180010a90`
- `0x180017fb8`
- `0x180018170`
- `0x180042912`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x180004adb`
- `msvcrt!_ui64tow_s` at `0x180004adb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004d1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004df0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004e5d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004d1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004df0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004e5d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800049b1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800049b1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180004b97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180004b97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800049db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004a30`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004a7c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004d37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004d97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004e78`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800049db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004a30`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004a7c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004d37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004d97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004e78`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180004d6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180004d6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180004e17`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180004e17`

## string_xrefs

- `0x180004a0d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180004a56`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180004cf9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180004dce`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x1800049f2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180004dae`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180004e30`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180004af2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180004b4f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180004bb2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180004bd2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180004c76`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v12; // rcx
  size_t v13; // r9
  HRESULT v14; // edi
  wchar_t *v15; // rax
  __int64 v16; // r14
  __int64 v17; // rbx
  size_t v18; // r11
  size_t v19; // rdi
  void *v20; // rax
  void *v21; // rsi
  wchar_t *v22; // rsi
  size_t *v23; // r8
  __int64 v24; // r11
  _WORD *v25; // rdx
  wchar_t *v26; // rcx
  __int64 v27; // r8
  __int16 v28; // ax
  void *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rdx
  void *v33; // rcx
  __int64 v34; // rcx
  int v35; // eax
  void *v36; // rcx
  __int64 v37; // rcx
  size_t v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  __int64 v42; // [rsp+30h] [rbp-D0h] BYREF
  struct StateRepository::Cache::Context_NoThrow *v43; // [rsp+38h] [rbp-C8h]
  __int64 v44; // [rsp+40h] [rbp-C0h] BYREF
  char v45; // [rsp+48h] [rbp-B8h]
  size_t pcchDestLength[2]; // [rsp+50h] [rbp-B0h] BYREF
  void *v47; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v48[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v49; // [rsp+268h] [rbp+168h]
  size_t cchDest; // [rsp+270h] [rbp+170h]
  void *Src; // [rsp+278h] [rbp+178h]
  wchar_t Buffer[20]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v4 = *(_QWORD *)a1;
  v43 = (struct StateRepository::Cache::Context_NoThrow *)&v42;
  v45 = 1;
  v42 = 0;
  v44 = 0;
  v8 = SRCacheContext_Open(v4, L"ApplicationUser\\Data", 0, &v44);
  if ( v45 )
  {
    v9 = *(_QWORD *)v43;
    *(_QWORD *)v43 = v44;
    if ( v9 )
      SRCacheContext_Close();
  }
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v8,
      v38);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)v8,
      v39);
LABEL_6:
    v10 = v42;
    v42 = 0;
    if ( v10 )
      SRCacheContext_Close();
    return v8;
  }
  if ( !v42 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)0x80670012LL,
      v38);
    v12 = v42;
    v42 = 0;
    if ( v12 )
      SRCacheContext_Close();
    return 2154233874LL;
  }
  v47 = 0;
  memset_0(v48, 0, sizeof(v48));
  v49 = 0;
  cchDest = 256;
  Src = v48;
  if ( _ui64tow_s(a2, Buffer, 0x11u, 16) )
  {
    v14 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v38);
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FD,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v14,
      v38);
    v29 = v47;
    v47 = 0;
    if ( v29 )
      SRCache_Free();
    v30 = v42;
    v42 = 0;
    if ( v30 )
      SRCacheContext_Close();
    return (unsigned int)v14;
  }
  v15 = Buffer;
  v16 = 0;
  v17 = 0;
  while ( *v15 )
  {
    if ( (unsigned __int64)++v17 >= 0x7FFFFFFF )
    {
      v14 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x80070057LL,
        v38);
      goto LABEL_38;
    }
    if ( *v15 == 94 )
      ++v16;
    ++v15;
  }
  v18 = cchDest;
  v19 = v16 + v17 + v49 + 1;
  if ( v19 > cchDest )
  {
    v20 = (void *)SRCache_AllocStringBuffer((unsigned int)v19);
    v21 = v20;
    if ( !v20 )
    {
      v14 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x8007000ELL,
        v38);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x136,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x8007000ELL,
        v40);
      goto LABEL_38;
    }
    memcpy_0(v20, Src, 2 * cchDest);
    wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>::reset<unsigned short *>(
      &v47,
      v21);
    v18 = v19;
    Src = v47;
    cchDest = v19;
  }
  if ( v16 )
  {
    v25 = (char *)Src + 2 * v49;
    v26 = Buffer;
    if ( v17 )
    {
      v27 = v17;
      do
      {
        if ( *v26 == 94 )
          *v25++ = 94;
        v28 = *v26++;
        *v25++ = v28;
        --v27;
      }
      while ( v27 );
    }
    *v25 = 0;
  }
  else
  {
    v22 = (wchar_t *)Src;
    pcchDestLength[0] = 0;
    v14 = StringValidateDestAndLengthW((STRSAFE_LPCWSTR)Src, v18, pcchDestLength, v13);
    if ( v14 >= 0 )
      v14 = StringCopyWorkerW(&v22[pcchDestLength[0]], v24 - pcchDestLength[0], v23, Buffer, v38);
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)(unsigned int)v14,
        v38);
      goto LABEL_38;
    }
  }
  v49 += v17;
  v14 = 0;
LABEL_38:
  if ( v14 < 0 )
    goto LABEL_39;
  v43 = a3;
  v44 = 0;
  v45 = 1;
  v8 = SRCacheContext_OpenSubContext(v42, Src, 0, &v44);
  if ( v45 )
  {
    v31 = *(_QWORD *)v43;
    *(_QWORD *)v43 = v44;
    if ( v31 )
      SRCacheContext_Close();
  }
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v8,
      v38);
    v32 = 510;
    goto LABEL_49;
  }
  v34 = v42;
  *a4 = *(_QWORD *)a3 != 0;
  v35 = SRCacheContext_AddToCache(v34, L"ApplicationUser\\Data");
  v8 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v35,
      v38);
    v32 = 512;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)v8,
      v41);
    v33 = v47;
    v47 = 0;
    if ( v33 )
      SRCache_Free();
    goto LABEL_6;
  }
  v36 = v47;
  v47 = 0;
  if ( v36 )
    SRCache_Free();
  v37 = v42;
  v42 = 0;
  if ( v37 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x180004950  push    rbp
0x180004952  push    rbx
0x180004953  push    rdi
0x180004954  push    r12
0x180004956  push    r13
0x180004958  push    r15
0x18000495a  lea     rbp, [rsp-1B8h]
0x180004962  sub     rsp, 2B8h
0x180004969  mov     rax, cs:__security_cookie
0x180004970  xor     rax, rsp
0x180004973  mov     [rbp+1E0h+var_38], rax
0x18000497a  mov     rcx, [rcx]
0x18000497d  lea     rax, [rsp+2E0h+var_2B0]
0x180004982  mov     r12, r9
0x180004985  mov     [rsp+2E0h+var_2A8], rax
0x18000498a  mov     r15, r8
0x18000498d  mov     [rsp+2E0h+var_298], 1
0x180004992  mov     rdi, rdx
0x180004995  lea     r9, [rsp+2E0h+var_2A0]
0x18000499a  xor     r13d, r13d
0x18000499d  lea     rdx, aApplicationuse; "ApplicationUser\\Data"
0x1800049a4  xor     r8d, r8d
0x1800049a7  mov     [rsp+2E0h+var_2B0], r13
0x1800049ac  mov     [rsp+2E0h+var_2A0], r13
0x1800049b1  call    cs:__imp_SRCacheContext_Open
0x1800049b8  nop     dword ptr [rax+rax+00h]
0x1800049bd  mov     ebx, eax
0x1800049bf  cmp     [rsp+2E0h+var_298], r13b
0x1800049c4  jz      short loc_1800049E7
0x1800049c6  mov     r8, [rsp+2E0h+var_2A8]
0x1800049cb  mov     rdx, [rsp+2E0h+var_2A0]
0x1800049d0  mov     rcx, [r8]
0x1800049d3  mov     [r8], rdx
0x1800049d6  test    rcx, rcx
0x1800049d9  jz      short loc_1800049E7
0x1800049db  call    cs:__imp_SRCacheContext_Close
0x1800049e2  nop     dword ptr [rax+rax+00h]
0x1800049e7  test    ebx, ebx
0x1800049e9  jns     short loc_180004A43
0x1800049eb  mov     rcx, [rbp+1E8h]; this
0x1800049f2  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800049f9  mov     r9d, ebx; char *
0x1800049fc  mov     edx, 18Ch; void *
0x180004a01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a06  mov     rcx, [rbp+1E8h]; this
0x180004a0d  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004a14  mov     r9d, ebx; char *
0x180004a17  mov     edx, 1F9h; void *
0x180004a1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a21  mov     rcx, [rsp+2E0h+var_2B0]
0x180004a26  mov     [rsp+2E0h+var_2B0], r13
0x180004a2b  test    rcx, rcx
0x180004a2e  jz      short loc_180004A3C
0x180004a30  call    cs:__imp_SRCacheContext_Close
0x180004a37  nop     dword ptr [rax+rax+00h]
0x180004a3c  mov     eax, ebx
0x180004a3e  jmp     loc_180004E86
0x180004a43  cmp     [rsp+2E0h+var_2B0], r13
0x180004a48  setnz   al
0x180004a4b  test    al, al
0x180004a4d  jnz     short loc_180004A92
0x180004a4f  mov     rcx, [rbp+1E8h]; this
0x180004a56  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004a5d  mov     r9d, 80670012h; char *
0x180004a63  mov     edx, 1FAh; void *
0x180004a68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a6d  mov     rcx, [rsp+2E0h+var_2B0]
0x180004a72  mov     [rsp+2E0h+var_2B0], r13
0x180004a77  test    rcx, rcx
0x180004a7a  jz      short loc_180004A88
0x180004a7c  call    cs:__imp_SRCacheContext_Close
0x180004a83  nop     dword ptr [rax+rax+00h]
0x180004a88  mov     eax, 80670012h
0x180004a8d  jmp     loc_180004E86
0x180004a92  xor     edx, edx; Val
0x180004a94  mov     [rsp+2E0h+var_280], r13
0x180004a99  mov     r8d, 200h; Size
0x180004a9f  lea     rcx, [rsp+2E0h+var_278]; void *
0x180004aa4  call    memset_0
0x180004aa9  mov     r9d, 10h; Radix
0x180004aaf  mov     [rbp+1E0h+var_78], r13
0x180004ab6  lea     rax, [rsp+2E0h+var_278]
0x180004abb  mov     [rbp+1E0h+cchDest], 100h
0x180004ac6  lea     rdx, [rbp+1E0h+Buffer]; Buffer
0x180004acd  mov     [rbp+1E0h+Src], rax
0x180004ad4  mov     rcx, rdi; Value
0x180004ad7  lea     r8d, [r9+1]; BufferCount
0x180004adb  call    cs:__imp__ui64tow_s
0x180004ae2  nop     dword ptr [rax+rax+00h]
0x180004ae7  test    eax, eax
0x180004ae9  jz      short loc_180004B10
0x180004aeb  mov     rcx, [rbp+1E8h]; this
0x180004af2  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004af9  mov     edi, 8000FFFFh
0x180004afe  mov     edx, 166h; void *
0x180004b03  mov     r9d, edi; char *
0x180004b06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b0b  jmp     loc_180004CF2
0x180004b10  mov     [rsp+2E0h+var_30], r14
0x180004b18  lea     rax, [rbp+1E0h+Buffer]
0x180004b1f  mov     r14, r13
0x180004b22  mov     rbx, r13
0x180004b25  movzx   ecx, word ptr [rax]
0x180004b28  test    cx, cx
0x180004b2b  jz      short loc_180004B6D
0x180004b2d  inc     rbx
0x180004b30  cmp     rbx, 7FFFFFFFh
0x180004b37  jnb     short loc_180004B48
0x180004b39  cmp     cx, 5Eh ; '^'
0x180004b3d  jnz     short loc_180004B42
0x180004b3f  inc     r14
0x180004b42  add     rax, 2
0x180004b46  jmp     short loc_180004B25
0x180004b48  mov     rcx, [rbp+1E8h]; this
0x180004b4f  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004b56  mov     edi, 80070057h
0x180004b5b  mov     edx, 135h; void *
0x180004b60  mov     r9d, edi; char *
0x180004b63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b68  jmp     loc_180004CE6
0x180004b6d  mov     rdi, [rbp+1E0h+var_78]
0x180004b74  mov     r11, [rbp+1E0h+cchDest]
0x180004b7b  inc     rdi
0x180004b7e  add     rdi, rbx
0x180004b81  mov     [rsp+2E0h+arg_10], rsi
0x180004b89  add     rdi, r14
0x180004b8c  cmp     rdi, r11
0x180004b8f  jbe     loc_180004C27
0x180004b95  mov     ecx, edi
0x180004b97  call    cs:__imp_SRCache_AllocStringBuffer
0x180004b9e  nop     dword ptr [rax+rax+00h]
0x180004ba3  mov     rsi, rax
0x180004ba6  test    rax, rax
0x180004ba9  jnz     short loc_180004BEB
0x180004bab  mov     rcx, [rbp+1E8h]; this
0x180004bb2  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004bb9  mov     edi, 8007000Eh
0x180004bbe  mov     edx, 193h; void *
0x180004bc3  mov     r9d, edi; char *
0x180004bc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004bcb  mov     rcx, [rbp+1E8h]; this
0x180004bd2  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004bd9  mov     r9d, edi; char *
0x180004bdc  mov     edx, 136h; void *
0x180004be1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004be6  jmp     loc_180004CDE
0x180004beb  mov     r8, [rbp+1E0h+cchDest]
0x180004bf2  mov     rcx, rsi; void *
0x180004bf5  mov     rdx, [rbp+1E0h+Src]; Src
0x180004bfc  add     r8, r8; Size
0x180004bff  call    memcpy_0
0x180004c04  mov     rdx, rsi
0x180004c07  lea     rcx, [rsp+2E0h+var_280]
0x180004c0c  call    ??$reset@PEAG@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>::reset<ushort *>(ushort *)
0x180004c11  mov     rax, [rsp+2E0h+var_280]
0x180004c16  mov     r11, rdi
0x180004c19  mov     [rbp+1E0h+Src], rax
0x180004c20  mov     [rbp+1E0h+cchDest], rdi
0x180004c27  test    r14, r14
0x180004c2a  jnz     short loc_180004C8C
0x180004c2c  mov     rsi, [rbp+1E0h+Src]
0x180004c33  lea     r8, [rsp+2E0h+pcchDestLength]; pcchDestLength
0x180004c38  mov     rcx, rsi; pszDest
0x180004c3b  mov     [rsp+2E0h+pcchDestLength], r13
0x180004c40  mov     rdx, r11; cchDest
0x180004c43  call    StringValidateDestAndLengthW
0x180004c48  mov     edi, eax
0x180004c4a  test    eax, eax
0x180004c4c  js      short loc_180004C6B
0x180004c4e  mov     rax, [rsp+2E0h+pcchDestLength]
0x180004c53  lea     r9, [rbp+1E0h+Buffer]; pszSrc
0x180004c5a  sub     r11, rax
0x180004c5d  mov     rdx, r11; cchDest
0x180004c60  lea     rcx, [rsi+rax*2]; pszDest
0x180004c64  call    StringCopyWorkerW
0x180004c69  mov     edi, eax
0x180004c6b  test    edi, edi
0x180004c6d  jns     short loc_180004CD4
0x180004c6f  mov     rcx, [rbp+1E8h]; this
0x180004c76  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004c7d  mov     r9d, edi; char *
0x180004c80  mov     edx, 139h; void *
0x180004c85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c8a  jmp     short loc_180004CDE
0x180004c8c  mov     rcx, [rbp+1E0h+var_78]
0x180004c93  mov     rax, [rbp+1E0h+Src]
0x180004c9a  lea     rdx, [rax+rcx*2]
0x180004c9e  lea     rcx, [rbp+1E0h+Buffer]
0x180004ca5  test    rbx, rbx
0x180004ca8  jz      short loc_180004CD0
0x180004caa  mov     r8, rbx
0x180004cad  cmp     word ptr [rcx], 5Eh ; '^'
0x180004cb1  jnz     short loc_180004CBC
0x180004cb3  mov     word ptr [rdx], 5Eh ; '^'
0x180004cb8  add     rdx, 2
0x180004cbc  movzx   eax, word ptr [rcx]
0x180004cbf  add     rcx, 2
0x180004cc3  mov     [rdx], ax
0x180004cc6  add     rdx, 2
0x180004cca  sub     r8, 1
0x180004cce  jnz     short loc_180004CAD
0x180004cd0  mov     [rdx], r13w
0x180004cd4  add     [rbp+1E0h+var_78], rbx
0x180004cdb  mov     edi, r13d
0x180004cde  mov     rsi, [rsp+2E0h+arg_10]
0x180004ce6  mov     r14, [rsp+2E0h+var_30]
0x180004cee  test    edi, edi
0x180004cf0  jns     short loc_180004D4A
0x180004cf2  mov     rcx, [rbp+1E8h]; this
0x180004cf9  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004d00  mov     r9d, edi; char *
0x180004d03  mov     edx, 1FDh; void *
0x180004d08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d0d  mov     rcx, [rsp+2E0h+var_280]
0x180004d12  mov     [rsp+2E0h+var_280], r13
0x180004d17  test    rcx, rcx
0x180004d1a  jz      short loc_180004D28
0x180004d1c  call    cs:__imp_SRCache_Free
0x180004d23  nop     dword ptr [rax+rax+00h]
0x180004d28  mov     rcx, [rsp+2E0h+var_2B0]
0x180004d2d  mov     [rsp+2E0h+var_2B0], r13
0x180004d32  test    rcx, rcx
0x180004d35  jz      short loc_180004D43
0x180004d37  call    cs:__imp_SRCacheContext_Close
0x180004d3e  nop     dword ptr [rax+rax+00h]
0x180004d43  mov     eax, edi
0x180004d45  jmp     loc_180004E86
0x180004d4a  mov     rdx, [rbp+1E0h+Src]
0x180004d51  lea     r9, [rsp+2E0h+var_2A0]
0x180004d56  mov     rcx, [rsp+2E0h+var_2B0]
0x180004d5b  xor     r8d, r8d
0x180004d5e  mov     [rsp+2E0h+var_2A8], r15
0x180004d63  mov     [rsp+2E0h+var_2A0], r13
0x180004d68  mov     [rsp+2E0h+var_298], 1
0x180004d6d  call    cs:__imp_SRCacheContext_OpenSubContext
0x180004d74  nop     dword ptr [rax+rax+00h]
0x180004d79  mov     ebx, eax
0x180004d7b  cmp     [rsp+2E0h+var_298], r13b
0x180004d80  jz      short loc_180004DA3
0x180004d82  mov     r8, [rsp+2E0h+var_2A8]
0x180004d87  mov     rdx, [rsp+2E0h+var_2A0]
0x180004d8c  mov     rcx, [r8]
0x180004d8f  mov     [r8], rdx
0x180004d92  test    rcx, rcx
0x180004d95  jz      short loc_180004DA3
0x180004d97  call    cs:__imp_SRCacheContext_Close
0x180004d9e  nop     dword ptr [rax+rax+00h]
0x180004da3  test    ebx, ebx
0x180004da5  jns     short loc_180004E01
0x180004da7  mov     rcx, [rbp+1E8h]; this
0x180004dae  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004db5  mov     r9d, ebx; char *
0x180004db8  mov     edx, 1B0h; void *
0x180004dbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dc2  mov     edx, 1FEh; void *
0x180004dc7  mov     rcx, [rbp+1E8h]; this
0x180004dce  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004dd5  mov     r9d, ebx; char *
0x180004dd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ddd  mov     rcx, [rsp+2E0h+var_280]
0x180004de2  mov     [rsp+2E0h+var_280], r13
0x180004de7  test    rcx, rcx
0x180004dea  jz      loc_180004A21
0x180004df0  call    cs:__imp_SRCache_Free
0x180004df7  nop     dword ptr [rax+rax+00h]
0x180004dfc  jmp     loc_180004A21
0x180004e01  cmp     [r15], r13
0x180004e04  lea     rdx, aApplicationuse; "ApplicationUser\\Data"
0x180004e0b  mov     rcx, [rsp+2E0h+var_2B0]
0x180004e10  setnz   al
0x180004e13  mov     [r12], al
0x180004e17  call    cs:__imp_SRCacheContext_AddToCache
0x180004e1e  nop     dword ptr [rax+rax+00h]
0x180004e23  mov     ebx, eax
0x180004e25  test    eax, eax
0x180004e27  jns     short loc_180004E4E
0x180004e29  mov     rcx, [rbp+1E8h]; this
0x180004e30  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004e37  mov     r9d, eax; char *
0x180004e3a  mov     edx, 1A6h; void *
0x180004e3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e44  mov     edx, 200h
0x180004e49  jmp     loc_180004DC7
0x180004e4e  mov     rcx, [rsp+2E0h+var_280]
0x180004e53  mov     [rsp+2E0h+var_280], r13
0x180004e58  test    rcx, rcx
0x180004e5b  jz      short loc_180004E69
0x180004e5d  call    cs:__imp_SRCache_Free
0x180004e64  nop     dword ptr [rax+rax+00h]
0x180004e69  mov     rcx, [rsp+2E0h+var_2B0]
0x180004e6e  mov     [rsp+2E0h+var_2B0], r13
0x180004e73  test    rcx, rcx
0x180004e76  jz      short loc_180004E84
0x180004e78  call    cs:__imp_SRCacheContext_Close
0x180004e7f  nop     dword ptr [rax+rax+00h]
0x180004e84  xor     eax, eax
0x180004e86  mov     rcx, [rbp+1E0h+var_38]
0x180004e8d  xor     rcx, rsp; StackCookie
0x180004e90  call    __security_check_cookie
0x180004e95  add     rsp, 2B8h
  ... truncated ...
```
