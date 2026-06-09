# StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x180017a4c`
- end: `0x180017d48`
- name: `?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `764`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800526e0`

## callees

- `0x180017a4c`
- `0x180018be0`
- `0x18001a1f0`
- `0x18001c314`
- `0x18004b094`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180017af4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180017af4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017abb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017b18`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017b67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017bb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017d1a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017abb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017b18`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017b67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017bb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017d1a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180017c62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180017c62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017c34`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017ceb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017d05`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017c34`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017ceb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017d05`

## string_xrefs

- `0x180017b29`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180017c7f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180017a90`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180017b44`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180017b87`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180017c12`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180017cc4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(
        StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 *v21; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  char v23; // [rsp+38h] [rbp-C8h]
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+248h] [rbp+148h]
  __int64 v27; // [rsp+250h] [rbp+150h]
  _BYTE *v28; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      v20[0]);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v9 = *(_QWORD *)a2;
  v21 = (__int64 *)v20;
  *(_QWORD *)v20 = 0;
  v22 = 0;
  v23 = 1;
  v10 = SRCacheContext_Open(v9, L"Application\\Index\\Package", 0, &v22);
  if ( v23 )
  {
    v11 = *v21;
    *v21 = v22;
    if ( v11 )
      SRCacheContext_Close(v11);
  }
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v20[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v10,
      v20[0]);
LABEL_11:
    v12 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return (unsigned int)v10;
  }
  if ( !*(_QWORD *)v20 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_16:
    v13 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    return v6;
  }
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v26 = 0;
  v28 = v25;
  v27 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, a3);
  if ( v10 < 0 )
  {
    v14 = 1001;
    goto LABEL_20;
  }
  v21 = (__int64 *)this;
  v22 = 0;
  v23 = 1;
  v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v20, v28, 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v20[0]);
    v14 = 1004;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v10,
      v20[0]);
    v15 = v24;
    v24 = 0;
    if ( v15 )
      SRCache_Free(v15);
    goto LABEL_11;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v16 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v20,
          L"Application\\Index\\Package");
  v6 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F2,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v16,
      v20[0]);
    v17 = v24;
    v24 = 0;
    if ( v17 )
      SRCache_Free(v17);
    goto LABEL_16;
  }
  v18 = v24;
  v24 = 0;
  if ( v18 )
    SRCache_Free(v18);
  v19 = *(_QWORD *)v20;
  *(_QWORD *)v20 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  return 0;
}

```

## disassembly

```asm
0x180017a4c  mov     [rsp-8+arg_18], rbx
0x180017a51  push    rbp
0x180017a52  push    rsi
0x180017a53  push    rdi
0x180017a54  push    r14
0x180017a56  push    r15
0x180017a58  lea     rbp, [rsp-170h]
0x180017a60  sub     rsp, 270h
0x180017a67  mov     rax, cs:__security_cookie
0x180017a6e  xor     rax, rsp
0x180017a71  mov     [rbp+190h+var_30], rax
0x180017a78  xor     r15d, r15d
0x180017a7b  mov     r14, r8
0x180017a7e  mov     rsi, rdx
0x180017a81  mov     rbx, rcx
0x180017a84  test    r8, r8
0x180017a87  jnz     short loc_180017AB0
0x180017a89  mov     rcx, [rbp+198h]; this
0x180017a90  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017a97  mov     ebx, 80070057h
0x180017a9c  mov     edx, 3DFh; void *
0x180017aa1  mov     r9d, ebx; char *
0x180017aa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017aa9  mov     eax, ebx
0x180017aab  jmp     loc_180017D22
0x180017ab0  mov     rcx, [rcx]
0x180017ab3  mov     [rbx], r15
0x180017ab6  test    rcx, rcx
0x180017ab9  jz      short loc_180017AC1
0x180017abb  call    cs:__imp_SRCacheContext_Close
0x180017ac1  mov     [rbx+8], r15d
0x180017ac5  lea     rax, [rsp+290h+var_270]
0x180017aca  mov     [rbx+10h], r15
0x180017ace  lea     r9, [rsp+290h+var_260]
0x180017ad3  mov     rcx, [rsi]
0x180017ad6  lea     rdx, aApplicationInd_0; "Application\\Index\\Package"
0x180017add  xor     r8d, r8d
0x180017ae0  mov     [rsp+290h+var_268], rax
0x180017ae5  mov     qword ptr [rsp+290h+var_270], r15; int
0x180017aea  mov     [rsp+290h+var_260], r15
0x180017aef  mov     [rsp+290h+var_258], 1
0x180017af4  call    cs:__imp_SRCacheContext_Open
0x180017afa  mov     edi, eax
0x180017afc  cmp     [rsp+290h+var_258], r15b
0x180017b01  jz      short loc_180017B1E
0x180017b03  mov     r8, [rsp+290h+var_268]
0x180017b08  mov     rdx, [rsp+290h+var_260]
0x180017b0d  mov     rcx, [r8]
0x180017b10  mov     [r8], rdx
0x180017b13  test    rcx, rcx
0x180017b16  jz      short loc_180017B1E
0x180017b18  call    cs:__imp_SRCacheContext_Close
0x180017b1e  test    edi, edi
0x180017b20  jns     short loc_180017B74
0x180017b22  mov     rcx, [rbp+198h]; this
0x180017b29  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017b30  mov     r9d, edi; char *
0x180017b33  mov     edx, 18Ch; void *
0x180017b38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b3d  mov     rcx, [rbp+198h]; this
0x180017b44  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017b4b  mov     r9d, edi; char *
0x180017b4e  mov     edx, 3E5h; void *
0x180017b53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b58  mov     rcx, qword ptr [rsp+290h+var_270]
0x180017b5d  mov     qword ptr [rsp+290h+var_270], r15
0x180017b62  test    rcx, rcx
0x180017b65  jz      short loc_180017B6D
0x180017b67  call    cs:__imp_SRCacheContext_Close
0x180017b6d  mov     eax, edi
0x180017b6f  jmp     loc_180017D22
0x180017b74  cmp     qword ptr [rsp+290h+var_270], r15
0x180017b79  setnz   al
0x180017b7c  test    al, al
0x180017b7e  jnz     short loc_180017BBE
0x180017b80  mov     rcx, [rbp+198h]; this
0x180017b87  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017b8e  mov     ebx, 80670012h
0x180017b93  mov     edx, 3E6h; void *
0x180017b98  mov     r9d, ebx; char *
0x180017b9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ba0  mov     rcx, qword ptr [rsp+290h+var_270]
0x180017ba5  mov     qword ptr [rsp+290h+var_270], r15
0x180017baa  test    rcx, rcx
0x180017bad  jz      loc_180017AA9
0x180017bb3  call    cs:__imp_SRCacheContext_Close
0x180017bb9  jmp     loc_180017AA9
0x180017bbe  xor     edx, edx; Val
0x180017bc0  mov     [rsp+290h+var_250], r15
0x180017bc5  mov     r8d, 200h; Size
0x180017bcb  lea     rcx, [rsp+290h+var_248]; void *
0x180017bd0  call    memset_0
0x180017bd5  lea     rax, [rsp+290h+var_248]
0x180017bda  mov     [rbp+190h+var_48], r15
0x180017be1  mov     rdx, r14; unsigned __int64
0x180017be4  mov     [rbp+190h+var_38], rax
0x180017beb  lea     rcx, [rsp+290h+var_250]; this
0x180017bf0  mov     [rbp+190h+var_40], 100h
0x180017bfb  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180017c00  mov     edi, eax
0x180017c02  test    eax, eax
0x180017c04  jns     short loc_180017C3F
0x180017c06  mov     edx, 3E9h; void *
0x180017c0b  mov     rcx, [rbp+198h]; this
0x180017c12  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017c19  mov     r9d, edi; char *
0x180017c1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c21  mov     rcx, [rsp+290h+var_250]
0x180017c26  mov     [rsp+290h+var_250], r15
0x180017c2b  test    rcx, rcx
0x180017c2e  jz      loc_180017B58
0x180017c34  call    cs:__imp_SRCache_Free
0x180017c3a  jmp     loc_180017B58
0x180017c3f  mov     rdx, [rbp+190h+var_38]
0x180017c46  lea     r9, [rsp+290h+var_260]
0x180017c4b  mov     rcx, qword ptr [rsp+290h+var_270]
0x180017c50  xor     r8d, r8d
0x180017c53  mov     [rsp+290h+var_268], rbx
0x180017c58  mov     [rsp+290h+var_260], r15
0x180017c5d  mov     [rsp+290h+var_258], 1
0x180017c62  call    cs:__imp_SRCacheContext_OpenSubContext
0x180017c68  lea     rcx, [rsp+290h+var_268]
0x180017c6d  mov     edi, eax
0x180017c6f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180017c74  test    edi, edi
0x180017c76  jns     short loc_180017C9D
0x180017c78  mov     rcx, [rbp+198h]; this
0x180017c7f  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017c86  mov     r9d, edi; char *
0x180017c89  mov     edx, 1B0h; void *
0x180017c8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c93  mov     edx, 3ECh
0x180017c98  jmp     loc_180017C0B
0x180017c9d  cmp     [rbx], r15
0x180017ca0  jz      short loc_180017CA6
0x180017ca2  mov     [rbx+10h], rsi
0x180017ca6  lea     rdx, aApplicationInd_0; "Application\\Index\\Package"
0x180017cad  lea     rcx, [rsp+290h+var_270]; this
0x180017cb2  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180017cb7  mov     ebx, eax
0x180017cb9  test    eax, eax
0x180017cbb  jns     short loc_180017CF6
0x180017cbd  mov     rcx, [rbp+198h]; this
0x180017cc4  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017ccb  mov     r9d, eax; char *
0x180017cce  mov     edx, 3F2h; void *
0x180017cd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017cd8  mov     rcx, [rsp+290h+var_250]
0x180017cdd  mov     [rsp+290h+var_250], r15
0x180017ce2  test    rcx, rcx
0x180017ce5  jz      loc_180017BA0
0x180017ceb  call    cs:__imp_SRCache_Free
0x180017cf1  jmp     loc_180017BA0
0x180017cf6  mov     rcx, [rsp+290h+var_250]
0x180017cfb  mov     [rsp+290h+var_250], r15
0x180017d00  test    rcx, rcx
0x180017d03  jz      short loc_180017D0B
0x180017d05  call    cs:__imp_SRCache_Free
0x180017d0b  mov     rcx, qword ptr [rsp+290h+var_270]
0x180017d10  mov     qword ptr [rsp+290h+var_270], r15
0x180017d15  test    rcx, rcx
0x180017d18  jz      short loc_180017D20
0x180017d1a  call    cs:__imp_SRCacheContext_Close
0x180017d20  xor     eax, eax
0x180017d22  mov     rcx, [rbp+190h+var_30]
0x180017d29  xor     rcx, rsp; StackCookie
0x180017d2c  call    __security_check_cookie
0x180017d31  mov     rbx, [rsp+290h+arg_18]
0x180017d39  add     rsp, 270h
0x180017d40  pop     r15
0x180017d42  pop     r14
0x180017d44  pop     rdi
0x180017d45  pop     rsi
0x180017d46  pop     rbp
0x180017d47  retn
```
