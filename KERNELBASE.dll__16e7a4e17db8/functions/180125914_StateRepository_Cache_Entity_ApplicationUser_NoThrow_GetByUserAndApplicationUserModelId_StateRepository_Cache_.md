# StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)

- ea: `0x180125914`
- end: `0x180125bf9`
- name: `?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z`
- size: `741`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800284a0`

## callees

- `0x18002f340`
- `0x18002f620`
- `0x180058520`
- `0x180058768`
- `0x1800caf60`
- `0x1800e15d8`
- `0x1800e665c`
- `0x180125914`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801259a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801259a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801259c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180125a1a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180125b4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180125ba8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180125bd2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801259c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180125a1a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180125b4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180125ba8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180125bd2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180125ab3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180125bbd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180125ab3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180125bbd`

## string_xrefs

- `0x1801259d8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180125958`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x1801259f8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180125a91`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180125b2b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        __int64 *a4)
{
  int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int16 v12; // dx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v24; // [rsp+48h] [rbp-B8h]
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
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)0x80070057LL,
      v20);
    return (unsigned int)v6;
  }
  v8 = *(_QWORD *)a1;
  v24 = &v22;
  v22 = 0;
  v25 = 0;
  v26 = 1;
  v6 = SRCacheContext_Open(v8, L"ApplicationUser\\Index\\UserAndApplicationUserModelId", 0, &v25);
  if ( v26 )
  {
    v9 = *v24;
    *v24 = v25;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v20);
    v10 = 425;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v6,
      v20);
LABEL_10:
    v11 = v22;
    v22 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v6;
  }
  if ( !v22 )
  {
    v6 = -2140733422;
    v10 = 426;
    goto LABEL_9;
  }
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v29 = 0;
  v31 = v28;
  v30 = 256;
  v6 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a2);
  if ( v6 < 0 )
  {
    v13 = 429;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v6,
      v20);
LABEL_17:
    v14 = v27;
    v27 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_10;
  }
  v6 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, v12);
  if ( v6 < 0 )
  {
    v13 = 430;
    goto LABEL_16;
  }
  v6 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a3);
  if ( v6 < 0 )
  {
    v13 = 431;
    goto LABEL_16;
  }
  v23 = 0;
  LOBYTE(v21) = 0;
  v6 = StateRepository::Cache::Context_NoThrow::OpenSubContext(&v23, &v22, v31);
  if ( v6 < 0 )
  {
    v15 = 435;
    goto LABEL_25;
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v22,
         L"ApplicationUser\\Index\\UserAndApplicationUserModelId");
  if ( v6 < 0 )
  {
    v15 = 441;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v6,
      (int)&v21);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCacheContext_Close(v16);
    goto LABEL_17;
  }
  v17 = v23;
  v23 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  v18 = v27;
  v27 = 0;
  if ( v18 )
    SRCache_Free(v18);
  v19 = v22;
  v22 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  return 0;
}

```

## disassembly

```asm
0x180125914  push    rbp
0x180125916  push    rbx
0x180125917  push    rsi
0x180125918  push    rdi
0x180125919  push    r14
0x18012591b  push    r15
0x18012591d  lea     rbp, [rsp-198h]
0x180125925  sub     rsp, 298h
0x18012592c  mov     rax, cs:__security_cookie
0x180125933  xor     rax, rsp
0x180125936  mov     [rbp+1C0h+var_40], rax
0x18012593d  xor     r15d, r15d
0x180125940  mov     rsi, r9
0x180125943  mov     [r9], r15
0x180125946  mov     r14, r8
0x180125949  mov     rdi, rdx
0x18012594c  test    rdx, rdx
0x18012594f  jnz     short loc_180125978
0x180125951  mov     rcx, [rbp+1C8h]; this
0x180125958  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18012595f  mov     ebx, 80070057h
0x180125964  mov     edx, 1A5h; void *
0x180125969  mov     r9d, ebx; char *
0x18012596c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125971  mov     eax, ebx
0x180125973  jmp     loc_180125BDA
0x180125978  mov     rcx, [rcx]
0x18012597b  lea     rax, [rsp+2C0h+var_288]
0x180125980  lea     r9, [rsp+2C0h+var_270]
0x180125985  mov     [rsp+2C0h+var_278], rax
0x18012598a  xor     r8d, r8d
0x18012598d  mov     [rsp+2C0h+var_288], r15
0x180125992  lea     rdx, aApplicationuse_3; "ApplicationUser\\Index\\UserAndApplicat"...
0x180125999  mov     [rsp+2C0h+var_270], r15
0x18012599e  mov     [rsp+2C0h+var_268], 1
0x1801259a3  call    cs:__imp_SRCacheContext_Open
0x1801259a9  mov     ebx, eax
0x1801259ab  cmp     [rsp+2C0h+var_268], r15b
0x1801259b0  jz      short loc_1801259CD
0x1801259b2  mov     r8, [rsp+2C0h+var_278]
0x1801259b7  mov     rdx, [rsp+2C0h+var_270]
0x1801259bc  mov     rcx, [r8]
0x1801259bf  mov     [r8], rdx
0x1801259c2  test    rcx, rcx
0x1801259c5  jz      short loc_1801259CD
0x1801259c7  call    cs:__imp_SRCacheContext_Close
0x1801259cd  test    ebx, ebx
0x1801259cf  jns     short loc_180125A25
0x1801259d1  mov     rcx, [rbp+1C8h]; this
0x1801259d8  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801259df  mov     r9d, ebx; char *
0x1801259e2  mov     edx, 18Ch; void *
0x1801259e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801259ec  mov     edx, 1A9h; void *
0x1801259f1  mov     rcx, [rbp+1C8h]; this
0x1801259f8  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801259ff  mov     r9d, ebx; char *
0x180125a02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125a07  mov     rcx, [rsp+2C0h+var_288]
0x180125a0c  mov     [rsp+2C0h+var_288], r15
0x180125a11  test    rcx, rcx
0x180125a14  jz      loc_180125971
0x180125a1a  call    cs:__imp_SRCacheContext_Close
0x180125a20  jmp     loc_180125971
0x180125a25  cmp     [rsp+2C0h+var_288], r15
0x180125a2a  setnz   al
0x180125a2d  test    al, al
0x180125a2f  jnz     short loc_180125A3D
0x180125a31  mov     ebx, 80670012h
0x180125a36  mov     edx, 1AAh
0x180125a3b  jmp     short loc_1801259F1
0x180125a3d  xor     edx, edx; Val
0x180125a3f  mov     [rsp+2C0h+var_260], r15
0x180125a44  mov     r8d, 200h; Size
0x180125a4a  lea     rcx, [rsp+2C0h+var_258]; void *
0x180125a4f  call    memset_0
0x180125a54  lea     rax, [rsp+2C0h+var_258]
0x180125a59  mov     [rbp+1C0h+var_58], r15
0x180125a60  mov     rdx, rdi; unsigned __int64
0x180125a63  mov     [rbp+1C0h+var_48], rax
0x180125a6a  lea     rcx, [rsp+2C0h+var_260]; this
0x180125a6f  mov     [rbp+1C0h+var_50], 100h
0x180125a7a  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180125a7f  mov     ebx, eax
0x180125a81  test    eax, eax
0x180125a83  jns     short loc_180125ABE
0x180125a85  mov     edx, 1ADh; void *
0x180125a8a  mov     rcx, [rbp+1C8h]; this
0x180125a91  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180125a98  mov     r9d, ebx; char *
0x180125a9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125aa0  mov     rcx, [rsp+2C0h+var_260]
0x180125aa5  mov     [rsp+2C0h+var_260], r15
0x180125aaa  test    rcx, rcx
0x180125aad  jz      loc_180125A07
0x180125ab3  call    cs:__imp_SRCache_Free
0x180125ab9  jmp     loc_180125A07
0x180125abe  lea     rcx, [rsp+2C0h+var_260]; this
0x180125ac3  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x180125ac8  mov     ebx, eax
0x180125aca  test    eax, eax
0x180125acc  jns     short loc_180125AD5
0x180125ace  mov     edx, 1AEh
0x180125ad3  jmp     short loc_180125A8A
0x180125ad5  mov     rdx, r14; unsigned __int16 *
0x180125ad8  lea     rcx, [rsp+2C0h+var_260]; this
0x180125add  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180125ae2  mov     ebx, eax
0x180125ae4  test    eax, eax
0x180125ae6  jns     short loc_180125AEF
0x180125ae8  mov     edx, 1AFh
0x180125aed  jmp     short loc_180125A8A
0x180125aef  mov     r8, [rbp+1C0h+var_48]
0x180125af6  lea     rax, [rsp+2C0h+var_290]
0x180125afb  lea     rdx, [rsp+2C0h+var_288]
0x180125b00  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x180125b05  lea     rcx, [rsp+2C0h+var_280]
0x180125b0a  mov     [rsp+2C0h+var_280], r15
0x180125b0f  mov     byte ptr [rsp+2C0h+var_290], r15b
0x180125b14  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180125b19  mov     ebx, eax
0x180125b1b  test    eax, eax
0x180125b1d  jns     short loc_180125B58
0x180125b1f  mov     edx, 1B3h; void *
0x180125b24  mov     rcx, [rbp+1C8h]; this
0x180125b2b  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180125b32  mov     r9d, ebx; char *
0x180125b35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125b3a  mov     rcx, [rsp+2C0h+var_280]
0x180125b3f  mov     [rsp+2C0h+var_280], r15
0x180125b44  test    rcx, rcx
0x180125b47  jz      loc_180125AA0
0x180125b4d  call    cs:__imp_SRCacheContext_Close
0x180125b53  jmp     loc_180125AA0
0x180125b58  cmp     byte ptr [rsp+2C0h+var_290], r15b
0x180125b5d  jz      short loc_180125B7B
0x180125b5f  mov     r8, rsi; __int64 *
0x180125b62  lea     rcx, [rsp+2C0h+var_280]; this
0x180125b67  xor     edx, edx; int
0x180125b69  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x180125b6e  mov     ebx, eax
0x180125b70  test    eax, eax
0x180125b72  jns     short loc_180125B7B
0x180125b74  mov     edx, 1B6h
0x180125b79  jmp     short loc_180125B24
0x180125b7b  lea     rdx, aApplicationuse_3; "ApplicationUser\\Index\\UserAndApplicat"...
0x180125b82  lea     rcx, [rsp+2C0h+var_288]; this
0x180125b87  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180125b8c  mov     ebx, eax
0x180125b8e  test    eax, eax
0x180125b90  jns     short loc_180125B99
0x180125b92  mov     edx, 1B9h
0x180125b97  jmp     short loc_180125B24
0x180125b99  mov     rcx, [rsp+2C0h+var_280]
0x180125b9e  mov     [rsp+2C0h+var_280], r15
0x180125ba3  test    rcx, rcx
0x180125ba6  jz      short loc_180125BAE
0x180125ba8  call    cs:__imp_SRCacheContext_Close
0x180125bae  mov     rcx, [rsp+2C0h+var_260]
0x180125bb3  mov     [rsp+2C0h+var_260], r15
0x180125bb8  test    rcx, rcx
0x180125bbb  jz      short loc_180125BC3
0x180125bbd  call    cs:__imp_SRCache_Free
0x180125bc3  mov     rcx, [rsp+2C0h+var_288]
0x180125bc8  mov     [rsp+2C0h+var_288], r15
0x180125bcd  test    rcx, rcx
0x180125bd0  jz      short loc_180125BD8
0x180125bd2  call    cs:__imp_SRCacheContext_Close
0x180125bd8  xor     eax, eax
0x180125bda  mov     rcx, [rbp+1C0h+var_40]
0x180125be1  xor     rcx, rsp; StackCookie
0x180125be4  call    __security_check_cookie
0x180125be9  add     rsp, 298h
0x180125bf0  pop     r15
0x180125bf2  pop     r14
0x180125bf4  pop     rdi
0x180125bf5  pop     rsi
0x180125bf6  pop     rbx
0x180125bf7  pop     rbp
0x180125bf8  retn
```
