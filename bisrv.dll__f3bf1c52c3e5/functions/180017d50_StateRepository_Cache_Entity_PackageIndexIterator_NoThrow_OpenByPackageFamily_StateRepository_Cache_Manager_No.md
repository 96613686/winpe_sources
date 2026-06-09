# StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x180017d50`
- end: `0x180018064`
- name: `?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `788`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800526e0`

## callees

- `0x180017d50`
- `0x180018be0`
- `0x18001a1f0`
- `0x18004b094`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180017df8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180017df8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017dbf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017e1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017e6b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017eb7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017f8a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018036`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017dbf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017e1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017e6b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017eb7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017f8a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018036`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180017f66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180017f66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017f38`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180018007`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180018021`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017f38`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180018007`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180018021`

## string_xrefs

- `0x180017e2d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180017f9b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180017d94`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180017e48`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180017e8b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180017f16`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180017fe0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
        StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *this,
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
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v22; // [rsp+28h] [rbp-D8h]
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  char v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+248h] [rbp+148h]
  __int64 v28; // [rsp+250h] [rbp+150h]
  _BYTE *v29; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x792,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80070057LL,
      v21[0]);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v9 = *(_QWORD *)a2;
  v22 = v21;
  *(_QWORD *)v21 = 0;
  v23 = 0;
  v24 = 1;
  v10 = SRCacheContext_Open(v9, L"Package\\Index\\PackageFamily", 0, &v23);
  if ( v24 )
  {
    v11 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
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
      v21[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x798,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v10,
      v21[0]);
LABEL_11:
    v12 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return (unsigned int)v10;
  }
  if ( !*(_QWORD *)v21 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x799,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_16:
    v13 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    return v6;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v29 = v26;
  v28 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a3);
  if ( v10 < 0 )
  {
    v14 = 1948;
    goto LABEL_20;
  }
  v22 = (int *)this;
  v23 = 0;
  v24 = 1;
  v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v29, 0, &v23);
  if ( v24 )
  {
    v16 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
    if ( v16 )
      SRCacheContext_Close(v16);
  }
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v21[0]);
    v14 = 1951;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v10,
      v21[0]);
    v15 = v25;
    v25 = 0;
    if ( v15 )
      SRCache_Free(v15);
    goto LABEL_11;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v17 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v21,
          L"Package\\Index\\PackageFamily");
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v17,
      v21[0]);
    v18 = v25;
    v25 = 0;
    if ( v18 )
      SRCache_Free(v18);
    goto LABEL_16;
  }
  v19 = v25;
  v25 = 0;
  if ( v19 )
    SRCache_Free(v19);
  v20 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  return 0;
}

```

## disassembly

```asm
0x180017d50  mov     [rsp-8+arg_18], rbx
0x180017d55  push    rbp
0x180017d56  push    rsi
0x180017d57  push    rdi
0x180017d58  push    r14
0x180017d5a  push    r15
0x180017d5c  lea     rbp, [rsp-170h]
0x180017d64  sub     rsp, 270h
0x180017d6b  mov     rax, cs:__security_cookie
0x180017d72  xor     rax, rsp
0x180017d75  mov     [rbp+190h+var_30], rax
0x180017d7c  xor     r15d, r15d
0x180017d7f  mov     r14, r8
0x180017d82  mov     rsi, rdx
0x180017d85  mov     rbx, rcx
0x180017d88  test    r8, r8
0x180017d8b  jnz     short loc_180017DB4
0x180017d8d  mov     rcx, [rbp+198h]; this
0x180017d94  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017d9b  mov     ebx, 80070057h
0x180017da0  mov     edx, 792h; void *
0x180017da5  mov     r9d, ebx; char *
0x180017da8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017dad  mov     eax, ebx
0x180017daf  jmp     loc_18001803E
0x180017db4  mov     rcx, [rcx]
0x180017db7  mov     [rbx], r15
0x180017dba  test    rcx, rcx
0x180017dbd  jz      short loc_180017DC5
0x180017dbf  call    cs:__imp_SRCacheContext_Close
0x180017dc5  mov     [rbx+8], r15d
0x180017dc9  lea     rax, [rsp+290h+var_270]
0x180017dce  mov     [rbx+10h], r15
0x180017dd2  lea     r9, [rsp+290h+var_260]
0x180017dd7  mov     rcx, [rsi]
0x180017dda  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x180017de1  xor     r8d, r8d
0x180017de4  mov     [rsp+290h+var_268], rax
0x180017de9  mov     qword ptr [rsp+290h+var_270], r15; int
0x180017dee  mov     [rsp+290h+var_260], r15
0x180017df3  mov     [rsp+290h+var_258], 1
0x180017df8  call    cs:__imp_SRCacheContext_Open
0x180017dfe  mov     edi, eax
0x180017e00  cmp     [rsp+290h+var_258], r15b
0x180017e05  jz      short loc_180017E22
0x180017e07  mov     r8, [rsp+290h+var_268]
0x180017e0c  mov     rdx, [rsp+290h+var_260]
0x180017e11  mov     rcx, [r8]
0x180017e14  mov     [r8], rdx
0x180017e17  test    rcx, rcx
0x180017e1a  jz      short loc_180017E22
0x180017e1c  call    cs:__imp_SRCacheContext_Close
0x180017e22  test    edi, edi
0x180017e24  jns     short loc_180017E78
0x180017e26  mov     rcx, [rbp+198h]; this
0x180017e2d  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017e34  mov     r9d, edi; char *
0x180017e37  mov     edx, 18Ch; void *
0x180017e3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e41  mov     rcx, [rbp+198h]; this
0x180017e48  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017e4f  mov     r9d, edi; char *
0x180017e52  mov     edx, 798h; void *
0x180017e57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e5c  mov     rcx, qword ptr [rsp+290h+var_270]
0x180017e61  mov     qword ptr [rsp+290h+var_270], r15
0x180017e66  test    rcx, rcx
0x180017e69  jz      short loc_180017E71
0x180017e6b  call    cs:__imp_SRCacheContext_Close
0x180017e71  mov     eax, edi
0x180017e73  jmp     loc_18001803E
0x180017e78  cmp     qword ptr [rsp+290h+var_270], r15
0x180017e7d  setnz   al
0x180017e80  test    al, al
0x180017e82  jnz     short loc_180017EC2
0x180017e84  mov     rcx, [rbp+198h]; this
0x180017e8b  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017e92  mov     ebx, 80670012h
0x180017e97  mov     edx, 799h; void *
0x180017e9c  mov     r9d, ebx; char *
0x180017e9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ea4  mov     rcx, qword ptr [rsp+290h+var_270]
0x180017ea9  mov     qword ptr [rsp+290h+var_270], r15
0x180017eae  test    rcx, rcx
0x180017eb1  jz      loc_180017DAD
0x180017eb7  call    cs:__imp_SRCacheContext_Close
0x180017ebd  jmp     loc_180017DAD
0x180017ec2  xor     edx, edx; Val
0x180017ec4  mov     [rsp+290h+var_250], r15
0x180017ec9  mov     r8d, 200h; Size
0x180017ecf  lea     rcx, [rsp+290h+var_248]; void *
0x180017ed4  call    memset_0
0x180017ed9  lea     rax, [rsp+290h+var_248]
0x180017ede  mov     [rbp+190h+var_48], r15
0x180017ee5  mov     rdx, r14; unsigned __int64
0x180017ee8  mov     [rbp+190h+var_38], rax
0x180017eef  lea     rcx, [rsp+290h+var_250]; this
0x180017ef4  mov     [rbp+190h+var_40], 100h
0x180017eff  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180017f04  mov     edi, eax
0x180017f06  test    eax, eax
0x180017f08  jns     short loc_180017F43
0x180017f0a  mov     edx, 79Ch; void *
0x180017f0f  mov     rcx, [rbp+198h]; this
0x180017f16  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017f1d  mov     r9d, edi; char *
0x180017f20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017f25  mov     rcx, [rsp+290h+var_250]
0x180017f2a  mov     [rsp+290h+var_250], r15
0x180017f2f  test    rcx, rcx
0x180017f32  jz      loc_180017E5C
0x180017f38  call    cs:__imp_SRCache_Free
0x180017f3e  jmp     loc_180017E5C
0x180017f43  mov     rdx, [rbp+190h+var_38]
0x180017f4a  lea     r9, [rsp+290h+var_260]
0x180017f4f  mov     rcx, qword ptr [rsp+290h+var_270]
0x180017f54  xor     r8d, r8d
0x180017f57  mov     [rsp+290h+var_268], rbx
0x180017f5c  mov     [rsp+290h+var_260], r15
0x180017f61  mov     [rsp+290h+var_258], 1
0x180017f66  call    cs:__imp_SRCacheContext_OpenSubContext
0x180017f6c  mov     edi, eax
0x180017f6e  cmp     [rsp+290h+var_258], r15b
0x180017f73  jz      short loc_180017F90
0x180017f75  mov     r8, [rsp+290h+var_268]
0x180017f7a  mov     rdx, [rsp+290h+var_260]
0x180017f7f  mov     rcx, [r8]
0x180017f82  mov     [r8], rdx
0x180017f85  test    rcx, rcx
0x180017f88  jz      short loc_180017F90
0x180017f8a  call    cs:__imp_SRCacheContext_Close
0x180017f90  test    edi, edi
0x180017f92  jns     short loc_180017FB9
0x180017f94  mov     rcx, [rbp+198h]; this
0x180017f9b  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017fa2  mov     r9d, edi; char *
0x180017fa5  mov     edx, 1B0h; void *
0x180017faa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017faf  mov     edx, 79Fh
0x180017fb4  jmp     loc_180017F0F
0x180017fb9  cmp     [rbx], r15
0x180017fbc  jz      short loc_180017FC2
0x180017fbe  mov     [rbx+10h], rsi
0x180017fc2  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x180017fc9  lea     rcx, [rsp+290h+var_270]; this
0x180017fce  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180017fd3  mov     ebx, eax
0x180017fd5  test    eax, eax
0x180017fd7  jns     short loc_180018012
0x180017fd9  mov     rcx, [rbp+198h]; this
0x180017fe0  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017fe7  mov     r9d, eax; char *
0x180017fea  mov     edx, 7A5h; void *
0x180017fef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ff4  mov     rcx, [rsp+290h+var_250]
0x180017ff9  mov     [rsp+290h+var_250], r15
0x180017ffe  test    rcx, rcx
0x180018001  jz      loc_180017EA4
0x180018007  call    cs:__imp_SRCache_Free
0x18001800d  jmp     loc_180017EA4
0x180018012  mov     rcx, [rsp+290h+var_250]
0x180018017  mov     [rsp+290h+var_250], r15
0x18001801c  test    rcx, rcx
0x18001801f  jz      short loc_180018027
0x180018021  call    cs:__imp_SRCache_Free
0x180018027  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001802c  mov     qword ptr [rsp+290h+var_270], r15
0x180018031  test    rcx, rcx
0x180018034  jz      short loc_18001803C
0x180018036  call    cs:__imp_SRCacheContext_Close
0x18001803c  xor     eax, eax
0x18001803e  mov     rcx, [rbp+190h+var_30]
0x180018045  xor     rcx, rsp; StackCookie
0x180018048  call    __security_check_cookie
0x18001804d  mov     rbx, [rsp+290h+arg_18]
0x180018055  add     rsp, 270h
0x18001805c  pop     r15
0x18001805e  pop     r14
0x180018060  pop     rdi
0x180018061  pop     rsi
0x180018062  pop     rbp
0x180018063  retn
```
