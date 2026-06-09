# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x180037dd0`
- end: `0x1800380d3`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `771`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180037d38`

## callees

- `0x18000a980`
- `0x18000b5c0`
- `0x180037dd0`
- `0x18005ae90`
- `0x18005ba40`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180037f74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180037f74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003800a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003800a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180037e2e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180037e2e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180037e52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180037ea1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180037f98`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180037feb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180038084`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800380ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180037e52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180037ea1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180037f98`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180037feb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180038084`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800380ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180037f3c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038099`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180037f3c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038099`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180038044`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180038044`

## string_xrefs

- `0x180037e63`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180037fa9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003801d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180038057`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180037e83`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180037f15`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180037fc9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  int *v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  char v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v27[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+258h] [rbp+158h]
  __int64 v29; // [rsp+260h] [rbp+160h]
  _BYTE *v30; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v25 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v21 = 0;
  v23 = v21;
  v24 = 0;
  v6 = SRCacheContext_Open(v3, L"Package\\Index\\PackageFullName", 0, &v24);
  if ( v25 )
  {
    v7 = *(_QWORD *)v23;
    *(_QWORD *)v23 = v24;
    if ( v7 )
      SRCacheContext_Close(v7);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v21[0]);
    v8 = 1128;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v21[0]);
LABEL_7:
    v9 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    return v6;
  }
  if ( !*(_QWORD *)v21 )
  {
    v6 = -2140733422;
    v8 = 1129;
    goto LABEL_6;
  }
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v28 = 0;
  v30 = v27;
  v29 = 256;
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, a2);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v11,
      v21[0]);
LABEL_14:
    v12 = v26;
    v26 = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_7;
  }
  v23 = (int *)&v22;
  v22 = 0;
  v24 = 0;
  v25 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v30, 0, &v24);
  if ( v25 )
  {
    v13 = *(_QWORD *)v23;
    *(_QWORD *)v23 = v24;
    if ( v13 )
      SRCacheContext_Close(v13);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v21[0]);
    v14 = 1136;
    goto LABEL_21;
  }
  if ( v22 )
  {
    v16 = SRCacheContext_EnumerateData(v22, 0, a3);
    v6 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v16,
        v21[0]);
      v14 = 1139;
      goto LABEL_21;
    }
  }
  v17 = SRCacheContext_AddToCache(*(_QWORD *)v21, L"Package\\Index\\PackageFullName");
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v17,
      v21[0]);
    v14 = 1142;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v21[0]);
    v15 = v22;
    v22 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
    goto LABEL_14;
  }
  v18 = v22;
  v22 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  v19 = v26;
  v26 = 0;
  if ( v19 )
    SRCache_Free();
  v20 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  return 0;
}

```

## disassembly

```asm
0x180037dd0  push    rbp
0x180037dd2  push    rbx
0x180037dd3  push    rsi
0x180037dd4  push    rdi
0x180037dd5  push    r14
0x180037dd7  lea     rbp, [rsp-180h]
0x180037ddf  sub     rsp, 280h
0x180037de6  mov     rax, cs:__security_cookie
0x180037ded  xor     rax, rsp
0x180037df0  mov     [rbp+1A0h+var_30], rax
0x180037df7  xor     r14d, r14d
0x180037dfa  mov     [rsp+2A0h+var_260], 1
0x180037dff  mov     [r8], r14
0x180037e02  lea     rax, [rsp+2A0h+var_280]
0x180037e07  mov     rcx, [rcx]
0x180037e0a  lea     r9, [rsp+2A0h+var_268]
0x180037e0f  mov     rdi, r8
0x180037e12  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x180037e17  mov     rsi, rdx
0x180037e1a  mov     [rsp+2A0h+var_270], rax
0x180037e1f  xor     r8d, r8d
0x180037e22  mov     [rsp+2A0h+var_268], r14
0x180037e27  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x180037e2e  call    cs:__imp_SRCacheContext_Open
0x180037e34  mov     ebx, eax
0x180037e36  cmp     [rsp+2A0h+var_260], r14b
0x180037e3b  jz      short loc_180037E58
0x180037e3d  mov     r8, [rsp+2A0h+var_270]
0x180037e42  mov     rdx, [rsp+2A0h+var_268]
0x180037e47  mov     rcx, [r8]
0x180037e4a  mov     [r8], rdx
0x180037e4d  test    rcx, rcx
0x180037e50  jz      short loc_180037E58
0x180037e52  call    cs:__imp_SRCacheContext_Close
0x180037e58  test    ebx, ebx
0x180037e5a  jns     short loc_180037EAE
0x180037e5c  mov     rcx, [rbp+1A8h]; this
0x180037e63  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x180037e6a  mov     r9d, ebx; char *
0x180037e6d  mov     edx, 18Ch; void *
0x180037e72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037e77  mov     edx, 468h; void *
0x180037e7c  mov     rcx, [rbp+1A8h]; this
0x180037e83  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180037e8a  mov     r9d, ebx; char *
0x180037e8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037e92  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180037e97  mov     qword ptr [rsp+2A0h+var_280], r14
0x180037e9c  test    rcx, rcx
0x180037e9f  jz      short loc_180037EA7
0x180037ea1  call    cs:__imp_SRCacheContext_Close
0x180037ea7  mov     eax, ebx
0x180037ea9  jmp     loc_1800380B6
0x180037eae  cmp     qword ptr [rsp+2A0h+var_280], r14
0x180037eb3  setnz   al
0x180037eb6  test    al, al
0x180037eb8  jnz     short loc_180037EC6
0x180037eba  mov     ebx, 80670012h
0x180037ebf  mov     edx, 469h
0x180037ec4  jmp     short loc_180037E7C
0x180037ec6  xor     edx, edx; Val
0x180037ec8  mov     [rsp+2A0h+var_250], r14
0x180037ecd  mov     r8d, 200h; Size
0x180037ed3  lea     rcx, [rsp+2A0h+var_248]; void *
0x180037ed8  call    memset_0
0x180037edd  lea     rax, [rsp+2A0h+var_248]
0x180037ee2  mov     [rbp+1A0h+var_48], r14
0x180037ee9  mov     rdx, rsi; unsigned __int16 *
0x180037eec  mov     [rbp+1A0h+var_38], rax
0x180037ef3  lea     rcx, [rsp+2A0h+var_250]; this
0x180037ef8  mov     [rbp+1A0h+var_40], 100h
0x180037f03  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180037f08  mov     ebx, eax
0x180037f0a  test    eax, eax
0x180037f0c  jns     short loc_180037F47
0x180037f0e  mov     rcx, [rbp+1A8h]; this
0x180037f15  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180037f1c  mov     r9d, eax; char *
0x180037f1f  mov     edx, 46Ch; void *
0x180037f24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037f29  mov     rcx, [rsp+2A0h+var_250]
0x180037f2e  mov     [rsp+2A0h+var_250], r14
0x180037f33  test    rcx, rcx
0x180037f36  jz      loc_180037E92
0x180037f3c  call    cs:__imp_SRCache_Free
0x180037f42  jmp     loc_180037E92
0x180037f47  mov     rdx, [rbp+1A0h+var_38]
0x180037f4e  lea     rax, [rsp+2A0h+var_278]
0x180037f53  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180037f58  lea     r9, [rsp+2A0h+var_268]
0x180037f5d  xor     r8d, r8d
0x180037f60  mov     [rsp+2A0h+var_270], rax
0x180037f65  mov     [rsp+2A0h+var_278], r14
0x180037f6a  mov     [rsp+2A0h+var_268], r14
0x180037f6f  mov     [rsp+2A0h+var_260], 1
0x180037f74  call    cs:__imp_SRCacheContext_OpenSubContext
0x180037f7a  mov     ebx, eax
0x180037f7c  cmp     [rsp+2A0h+var_260], r14b
0x180037f81  jz      short loc_180037F9E
0x180037f83  mov     r8, [rsp+2A0h+var_270]
0x180037f88  mov     rdx, [rsp+2A0h+var_268]
0x180037f8d  mov     rcx, [r8]
0x180037f90  mov     [r8], rdx
0x180037f93  test    rcx, rcx
0x180037f96  jz      short loc_180037F9E
0x180037f98  call    cs:__imp_SRCacheContext_Close
0x180037f9e  test    ebx, ebx
0x180037fa0  jns     short loc_180037FF6
0x180037fa2  mov     rcx, [rbp+1A8h]; this
0x180037fa9  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x180037fb0  mov     r9d, ebx; char *
0x180037fb3  mov     edx, 1B0h; void *
0x180037fb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037fbd  mov     edx, 470h; void *
0x180037fc2  mov     rcx, [rbp+1A8h]; this
0x180037fc9  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180037fd0  mov     r9d, ebx; char *
0x180037fd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037fd8  mov     rcx, [rsp+2A0h+var_278]
0x180037fdd  mov     [rsp+2A0h+var_278], r14
0x180037fe2  test    rcx, rcx
0x180037fe5  jz      loc_180037F29
0x180037feb  call    cs:__imp_SRCacheContext_Close
0x180037ff1  jmp     loc_180037F29
0x180037ff6  mov     rcx, [rsp+2A0h+var_278]
0x180037ffb  test    rcx, rcx
0x180037ffe  setnz   al
0x180038001  test    al, al
0x180038003  jz      short loc_180038038
0x180038005  mov     r8, rdi
0x180038008  xor     edx, edx
0x18003800a  call    cs:__imp_SRCacheContext_EnumerateData
0x180038010  mov     ebx, eax
0x180038012  test    eax, eax
0x180038014  jns     short loc_180038038
0x180038016  mov     rcx, [rbp+1A8h]; this
0x18003801d  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x180038024  mov     r9d, eax; char *
0x180038027  mov     edx, 2A6h; void *
0x18003802c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038031  mov     edx, 473h
0x180038036  jmp     short loc_180037FC2
0x180038038  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18003803d  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x180038044  call    cs:__imp_SRCacheContext_AddToCache
0x18003804a  mov     ebx, eax
0x18003804c  test    eax, eax
0x18003804e  jns     short loc_180038075
0x180038050  mov     rcx, [rbp+1A8h]; this
0x180038057  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003805e  mov     r9d, eax; char *
0x180038061  mov     edx, 1A6h; void *
0x180038066  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003806b  mov     edx, 476h
0x180038070  jmp     loc_180037FC2
0x180038075  mov     rcx, [rsp+2A0h+var_278]
0x18003807a  mov     [rsp+2A0h+var_278], r14
0x18003807f  test    rcx, rcx
0x180038082  jz      short loc_18003808A
0x180038084  call    cs:__imp_SRCacheContext_Close
0x18003808a  mov     rcx, [rsp+2A0h+var_250]
0x18003808f  mov     [rsp+2A0h+var_250], r14
0x180038094  test    rcx, rcx
0x180038097  jz      short loc_18003809F
0x180038099  call    cs:__imp_SRCache_Free
0x18003809f  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800380a4  mov     qword ptr [rsp+2A0h+var_280], r14
0x1800380a9  test    rcx, rcx
0x1800380ac  jz      short loc_1800380B4
0x1800380ae  call    cs:__imp_SRCacheContext_Close
0x1800380b4  xor     eax, eax
0x1800380b6  mov     rcx, [rbp+1A0h+var_30]
0x1800380bd  xor     rcx, rsp; StackCookie
0x1800380c0  call    __security_check_cookie
0x1800380c5  add     rsp, 280h
0x1800380cc  pop     r14
0x1800380ce  pop     rdi
0x1800380cf  pop     rsi
0x1800380d0  pop     rbx
0x1800380d1  pop     rbp
0x1800380d2  retn
```
