# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18004fde4`
- end: `0x1800500ce`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `746`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004d9a8`

## callees

- `0x18004fb30`
- `0x18004fde4`
- `0x180098bf4`
- `0x1800f0260`
- `0x1800f10e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18004ff36`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18004ff36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18005004b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18005004b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004fe79`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004fec8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180050007`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800500a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004fe79`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004fec8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180050007`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800500a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18004fe4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18004fe4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18004ffdd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18004ffdd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004ffa7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005008b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004ffa7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005008b`

## string_xrefs

- `0x18004ff47`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Key.hpp`
- `0x18004feaa`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-Package.hpp`
- `0x18004ff85`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-Package.hpp`
- `0x18004fe8a`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180050018`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18005005e`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v26[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+238h] [rbp+138h]
  __int64 v28; // [rsp+240h] [rbp+140h]
  _BYTE *v29; // [rsp+248h] [rbp+148h]
  unsigned __int16 v30[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v31; // [rsp+258h] [rbp+158h] BYREF
  char v32; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a1;
  *(_QWORD *)v30 = v24;
  v32 = 1;
  *(_QWORD *)v24 = 0;
  v31 = 0;
  v8 = SRCacheContext_Open(v4, L"Package\\Data", 0, &v31);
  if ( v32 )
  {
    v9 = v31;
    v10 = **(_QWORD **)v30;
    **(_QWORD **)v30 = v31;
    if ( v10 )
      SRCacheContext_Close(v10, v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
    v11 = 1192;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
LABEL_7:
    v13 = *(_QWORD *)v24;
    *(_QWORD *)v24 = 0;
    if ( v13 )
      SRCacheContext_Close(v13, v12);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v24 )
  {
    v8 = -2140733422;
    v11 = 1193;
    goto LABEL_6;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v28 = 256;
  v29 = v26;
  if ( (unsigned int)_o__ui64tow_s(a2, v30, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v24[0]);
LABEL_15:
    v15 = 1196;
    goto LABEL_16;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, v30);
  if ( v8 < 0 )
    goto LABEL_15;
  *(_QWORD *)v30 = a3;
  v31 = 0;
  v32 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v24, v29, 0, &v31);
  if ( v32 )
  {
    v17 = v31;
    v18 = **(_QWORD **)v30;
    **(_QWORD **)v30 = v31;
    if ( v18 )
      SRCacheContext_Close(v18, v17);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
    v15 = 1197;
    goto LABEL_16;
  }
  v19 = *(_QWORD *)v24;
  *a4 = *(_QWORD *)a3 != 0;
  v20 = SRCacheContext_AddToCache(v19, L"Package\\Data");
  v8 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v20,
      v24[0]);
    v15 = 1199;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
    v16 = v25;
    v25 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_7;
  }
  v22 = v25;
  v25 = 0;
  if ( v22 )
    SRCache_Free();
  v23 = *(_QWORD *)v24;
  *(_QWORD *)v24 = 0;
  if ( v23 )
    SRCacheContext_Close(v23, v21);
  return 0;
}

```

## disassembly

```asm
0x18004fde4  mov     [rsp-8+arg_10], rbx
0x18004fde9  push    rbp
0x18004fdea  push    rsi
0x18004fdeb  push    rdi
0x18004fdec  push    r14
0x18004fdee  push    r15
0x18004fdf0  lea     rbp, [rsp-180h]
0x18004fdf8  sub     rsp, 280h
0x18004fdff  mov     rax, cs:__security_cookie
0x18004fe06  xor     rax, rsp
0x18004fe09  mov     [rbp+1A0h+var_28], rax
0x18004fe10  mov     rcx, [rcx]
0x18004fe13  lea     rax, [rsp+2A0h+var_280]
0x18004fe18  mov     r14, r9
0x18004fe1b  mov     qword ptr [rbp+1A0h+var_50], rax
0x18004fe22  mov     rdi, r8
0x18004fe25  mov     [rbp+1A0h+var_40], 1
0x18004fe2c  mov     rsi, rdx
0x18004fe2f  lea     r9, [rbp+1A0h+var_48]
0x18004fe36  xor     r15d, r15d
0x18004fe39  lea     rdx, aPackageData; "Package\\Data"
0x18004fe40  xor     r8d, r8d
0x18004fe43  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x18004fe48  mov     [rbp+1A0h+var_48], r15
0x18004fe4f  call    cs:__imp_SRCacheContext_Open
0x18004fe55  mov     ebx, eax
0x18004fe57  cmp     [rbp+1A0h+var_40], r15b
0x18004fe5e  jz      short loc_18004FE7F
0x18004fe60  mov     r8, qword ptr [rbp+1A0h+var_50]
0x18004fe67  mov     rdx, [rbp+1A0h+var_48]
0x18004fe6e  mov     rcx, [r8]
0x18004fe71  mov     [r8], rdx
0x18004fe74  test    rcx, rcx
0x18004fe77  jz      short loc_18004FE7F
0x18004fe79  call    cs:__imp_SRCacheContext_Close
0x18004fe7f  test    ebx, ebx
0x18004fe81  jns     short loc_18004FED5
0x18004fe83  mov     rcx, [rbp+1A8h]; this
0x18004fe8a  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateRepositor"...
0x18004fe91  mov     r9d, ebx; char *
0x18004fe94  mov     edx, 18Ch; void *
0x18004fe99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fe9e  mov     edx, 4A8h; void *
0x18004fea3  mov     rcx, [rbp+1A8h]; this
0x18004feaa  lea     r8, aOnecoreBaseApp_120; "onecore\\base\\appmodel\\StateRepositor"...
0x18004feb1  mov     r9d, ebx; char *
0x18004feb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004feb9  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18004febe  mov     qword ptr [rsp+2A0h+var_280], r15
0x18004fec3  test    rcx, rcx
0x18004fec6  jz      short loc_18004FECE
0x18004fec8  call    cs:__imp_SRCacheContext_Close
0x18004fece  mov     eax, ebx
0x18004fed0  jmp     loc_1800500A8
0x18004fed5  cmp     qword ptr [rsp+2A0h+var_280], r15
0x18004feda  setnz   al
0x18004fedd  test    al, al
0x18004fedf  jnz     short loc_18004FEED
0x18004fee1  mov     ebx, 80670012h
0x18004fee6  mov     edx, 4A9h
0x18004feeb  jmp     short loc_18004FEA3
0x18004feed  xor     edx, edx; Val
0x18004feef  mov     [rsp+2A0h+var_270], r15
0x18004fef4  mov     r8d, 200h; Size
0x18004fefa  lea     rcx, [rsp+2A0h+var_268]; void *
0x18004feff  call    memset_0
0x18004ff04  mov     r9d, 10h
0x18004ff0a  mov     [rbp+1A0h+var_68], r15
0x18004ff11  lea     rax, [rsp+2A0h+var_268]
0x18004ff16  mov     [rbp+1A0h+var_60], 100h
0x18004ff21  lea     rdx, [rbp+1A0h+var_50]
0x18004ff28  mov     [rbp+1A0h+var_58], rax
0x18004ff2f  mov     rcx, rsi
0x18004ff32  lea     r8d, [r9+1]
0x18004ff36  call    cs:__imp__o__ui64tow_s
0x18004ff3c  test    eax, eax
0x18004ff3e  jz      short loc_18004FF62
0x18004ff40  mov     rcx, [rbp+1A8h]; this
0x18004ff47  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x18004ff4e  mov     ebx, 8000FFFFh
0x18004ff53  mov     edx, 166h; void *
0x18004ff58  mov     r9d, ebx; char *
0x18004ff5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ff60  jmp     short loc_18004FF79
0x18004ff62  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x18004ff69  lea     rcx, [rsp+2A0h+var_270]; this
0x18004ff6e  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18004ff73  mov     ebx, eax
0x18004ff75  test    eax, eax
0x18004ff77  jns     short loc_18004FFB2
0x18004ff79  mov     edx, 4ACh; void *
0x18004ff7e  mov     rcx, [rbp+1A8h]; this
0x18004ff85  lea     r8, aOnecoreBaseApp_120; "onecore\\base\\appmodel\\StateRepositor"...
0x18004ff8c  mov     r9d, ebx; char *
0x18004ff8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ff94  mov     rcx, [rsp+2A0h+var_270]
0x18004ff99  mov     [rsp+2A0h+var_270], r15
0x18004ff9e  test    rcx, rcx
0x18004ffa1  jz      loc_18004FEB9
0x18004ffa7  call    cs:__imp_SRCache_Free
0x18004ffad  jmp     loc_18004FEB9
0x18004ffb2  mov     rdx, [rbp+1A0h+var_58]
0x18004ffb9  lea     r9, [rbp+1A0h+var_48]
0x18004ffc0  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18004ffc5  xor     r8d, r8d
0x18004ffc8  mov     qword ptr [rbp+1A0h+var_50], rdi
0x18004ffcf  mov     [rbp+1A0h+var_48], r15
0x18004ffd6  mov     [rbp+1A0h+var_40], 1
0x18004ffdd  call    cs:__imp_SRCacheContext_OpenSubContext
0x18004ffe3  mov     ebx, eax
0x18004ffe5  cmp     [rbp+1A0h+var_40], r15b
0x18004ffec  jz      short loc_18005000D
0x18004ffee  mov     r8, qword ptr [rbp+1A0h+var_50]
0x18004fff5  mov     rdx, [rbp+1A0h+var_48]
0x18004fffc  mov     rcx, [r8]
0x18004ffff  mov     [r8], rdx
0x180050002  test    rcx, rcx
0x180050005  jz      short loc_18005000D
0x180050007  call    cs:__imp_SRCacheContext_Close
0x18005000d  test    ebx, ebx
0x18005000f  jns     short loc_180050036
0x180050011  mov     rcx, [rbp+1A8h]; this
0x180050018  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateRepositor"...
0x18005001f  mov     r9d, ebx; char *
0x180050022  mov     edx, 1B0h; void *
0x180050027  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005002c  mov     edx, 4ADh
0x180050031  jmp     loc_18004FF7E
0x180050036  cmp     [rdi], r15
0x180050039  lea     rdx, aPackageData; "Package\\Data"
0x180050040  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180050045  setnz   al
0x180050048  mov     [r14], al
0x18005004b  call    cs:__imp_SRCacheContext_AddToCache
0x180050051  mov     ebx, eax
0x180050053  test    eax, eax
0x180050055  jns     short loc_18005007C
0x180050057  mov     rcx, [rbp+1A8h]; this
0x18005005e  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateRepositor"...
0x180050065  mov     r9d, eax; char *
0x180050068  mov     edx, 1A6h; void *
0x18005006d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050072  mov     edx, 4AFh
0x180050077  jmp     loc_18004FF7E
0x18005007c  mov     rcx, [rsp+2A0h+var_270]
0x180050081  mov     [rsp+2A0h+var_270], r15
0x180050086  test    rcx, rcx
0x180050089  jz      short loc_180050091
0x18005008b  call    cs:__imp_SRCache_Free
0x180050091  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180050096  mov     qword ptr [rsp+2A0h+var_280], r15
0x18005009b  test    rcx, rcx
0x18005009e  jz      short loc_1800500A6
0x1800500a0  call    cs:__imp_SRCacheContext_Close
0x1800500a6  xor     eax, eax
0x1800500a8  mov     rcx, [rbp+1A0h+var_28]
0x1800500af  xor     rcx, rsp; StackCookie
0x1800500b2  call    __security_check_cookie
0x1800500b7  mov     rbx, [rsp+2A0h+arg_10]
0x1800500bf  add     rsp, 280h
0x1800500c6  pop     r15
0x1800500c8  pop     r14
0x1800500ca  pop     rdi
0x1800500cb  pop     rsi
0x1800500cc  pop     rbp
0x1800500cd  retn
```
