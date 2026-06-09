# StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18002fed8`
- end: `0x1800302ee`
- name: `?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `1046`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18002d000`
- `0x18002fd98`

## callees

- `0x18002fc50`
- `0x18002fcf0`
- `0x18002fed8`
- `0x180058768`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180030166`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180030166`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180030120`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180030120`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002ff3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002ff3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ff63`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030095`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030144`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003019d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800301c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003021d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ff63`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030095`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030144`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003019d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800301c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003021d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030080`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800301b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030080`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800301b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180030182`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180030182`

## string_xrefs

- `0x18002ff38`: `User\Index\UserSid`
- `0x18003017b`: `User\Index\UserSid`
- `0x18003005d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800301fb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180030280`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180030047`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800301db`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003023e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180030260`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800302a7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rbx
  bool v9; // r8
  unsigned __int16 *v10; // rdx
  unsigned __int64 v11; // rdi
  __int64 v12; // r14
  const unsigned __int16 *i; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned __int16 *v18; // rdx
  unsigned __int64 j; // rcx
  __int64 v20; // rcx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  int v29[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v30; // [rsp+28h] [rbp-D8h] BYREF
  int *v31; // [rsp+30h] [rbp-D0h]
  __int64 v32; // [rsp+38h] [rbp-C8h] BYREF
  char v33; // [rsp+40h] [rbp-C0h]
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v35[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+258h] [rbp+158h]
  unsigned __int64 v37; // [rsp+260h] [rbp+160h]
  unsigned __int16 *v38; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v33 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v29 = 0;
  v31 = v29;
  v32 = 0;
  v6 = SRCacheContext_Open(v3, L"User\\Index\\UserSid", 0, &v32);
  if ( v33 )
  {
    v7 = *(_QWORD *)v31;
    *(_QWORD *)v31 = v32;
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
      v29[0]);
    v28 = 185;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v6,
      v29[0]);
LABEL_20:
    v16 = *(_QWORD *)v29;
    *(_QWORD *)v29 = 0;
    if ( v16 )
      SRCacheContext_Close(v16);
    return (unsigned int)v6;
  }
  v8 = *(_QWORD *)v29;
  if ( !*(_QWORD *)v29 )
  {
    v6 = -2140733422;
    v28 = 186;
    goto LABEL_46;
  }
  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  v36 = 0;
  v10 = (unsigned __int16 *)v35;
  v38 = (unsigned __int16 *)v35;
  v37 = 256;
  if ( a2 )
  {
    v11 = 0;
    v12 = 0;
    for ( i = a2; *i; ++i )
    {
      if ( ++v11 >= 0x7FFFFFFF )
      {
        v6 = -2147024809;
        v14 = 309;
        goto LABEL_17;
      }
      if ( *i == 94 )
        ++v12;
    }
    v6 = StateRepository::Cache::Key_NoThrow::EnsureCapacity(
           (StateRepository::Cache::Key_NoThrow *)&v34,
           v12 + v11 + 1,
           v9);
    if ( v6 < 0 )
    {
      v14 = 310;
      goto LABEL_17;
    }
    if ( v12 )
    {
      v18 = &v38[v36];
      for ( j = 0; j < v11; ++v18 )
      {
        if ( *a2 == 94 )
          *v18++ = 94;
        ++j;
        *v18 = *a2++;
      }
      *v18 = 0;
    }
    else
    {
      v6 = StringCchCatW(v38, v37, a2);
      if ( v6 < 0 )
      {
        v14 = 313;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)(unsigned int)v6,
          v29[0]);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBD,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
          (const char *)(unsigned int)v6,
          v29[0]);
        goto LABEL_18;
      }
    }
    v36 += v11;
    v8 = *(_QWORD *)v29;
    v10 = v38;
  }
  v30 = 0;
  v31 = (int *)&v30;
  v32 = 0;
  v33 = 1;
  v6 = SRCacheContext_OpenSubContext(v8, v10, 0, &v32);
  if ( v33 )
  {
    v20 = *(_QWORD *)v31;
    *(_QWORD *)v31 = v32;
    if ( v20 )
      SRCacheContext_Close(v20);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v29[0]);
    v26 = 193;
    goto LABEL_41;
  }
  if ( v30 )
  {
    v21 = SRCacheContext_EnumerateData(v30, 0, a3);
    v6 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v21,
        v29[0]);
      v26 = 196;
      goto LABEL_41;
    }
  }
  v22 = SRCacheContext_AddToCache(*(_QWORD *)v29, L"User\\Index\\UserSid");
  v6 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v22,
      v29[0]);
    v26 = 199;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v6,
      v29[0]);
    v27 = v30;
    v30 = 0;
    if ( v27 )
      SRCacheContext_Close(v27);
LABEL_18:
    v15 = v34;
    v34 = 0;
    if ( v15 )
      SRCache_Free(v15);
    goto LABEL_20;
  }
  v23 = v30;
  v30 = 0;
  if ( v23 )
    SRCacheContext_Close(v23);
  v24 = v34;
  v34 = 0;
  if ( v24 )
    SRCache_Free(v24);
  v25 = *(_QWORD *)v29;
  *(_QWORD *)v29 = 0;
  if ( v25 )
    SRCacheContext_Close(v25);
  return 0;
}

```

## disassembly

```asm
0x18002fed8  mov     [rsp-8+arg_18], rbx
0x18002fedd  push    rbp
0x18002fede  push    rsi
0x18002fedf  push    rdi
0x18002fee0  push    r12
0x18002fee2  push    r13
0x18002fee4  push    r14
0x18002fee6  push    r15
0x18002fee8  lea     rbp, [rsp-180h]
0x18002fef0  sub     rsp, 280h
0x18002fef7  mov     rax, cs:__security_cookie
0x18002fefe  xor     rax, rsp
0x18002ff01  mov     [rbp+1B0h+var_40], rax
0x18002ff08  xor     r12d, r12d
0x18002ff0b  mov     [rsp+2B0h+var_270], 1
0x18002ff10  mov     [r8], r12
0x18002ff13  lea     rax, [rsp+2B0h+var_290]
0x18002ff18  mov     rcx, [rcx]
0x18002ff1b  lea     r9, [rsp+2B0h+var_278]
0x18002ff20  mov     r15, r8
0x18002ff23  mov     qword ptr [rsp+2B0h+var_290], r12; int
0x18002ff28  mov     rsi, rdx
0x18002ff2b  mov     [rsp+2B0h+var_280], rax
0x18002ff30  xor     r8d, r8d
0x18002ff33  mov     [rsp+2B0h+var_278], r12
0x18002ff38  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18002ff3f  call    cs:__imp_SRCacheContext_Open
0x18002ff45  mov     ebx, eax
0x18002ff47  cmp     [rsp+2B0h+var_270], r12b
0x18002ff4c  jz      short loc_18002FF69
0x18002ff4e  mov     r8, [rsp+2B0h+var_280]
0x18002ff53  mov     rdx, [rsp+2B0h+var_278]
0x18002ff58  mov     rcx, [r8]
0x18002ff5b  mov     [r8], rdx
0x18002ff5e  test    rcx, rcx
0x18002ff61  jz      short loc_18002FF69
0x18002ff63  call    cs:__imp_SRCacheContext_Close
0x18002ff69  test    ebx, ebx
0x18002ff6b  js      loc_180030259
0x18002ff71  mov     rbx, qword ptr [rsp+2B0h+var_290]
0x18002ff76  test    rbx, rbx
0x18002ff79  setnz   al
0x18002ff7c  test    al, al
0x18002ff7e  jz      loc_180030294
0x18002ff84  xor     edx, edx; Val
0x18002ff86  mov     [rsp+2B0h+var_260], r12
0x18002ff8b  mov     r8d, 200h; Size
0x18002ff91  lea     rcx, [rsp+2B0h+var_258]; void *
0x18002ff96  call    memset_0
0x18002ff9b  mov     [rbp+1B0h+var_58], r12
0x18002ffa2  lea     rdx, [rsp+2B0h+var_258]
0x18002ffa7  mov     [rbp+1B0h+var_48], rdx
0x18002ffae  mov     [rbp+1B0h+var_50], 100h
0x18002ffb9  test    rsi, rsi
0x18002ffbc  jz      loc_1800300FC
0x18002ffc2  mov     rdi, r12
0x18002ffc5  mov     r14, r12
0x18002ffc8  mov     rax, rsi
0x18002ffcb  mov     r13d, 5Eh ; '^'
0x18002ffd1  cmp     [rax], r12w
0x18002ffd5  jz      short loc_18002FFF7
0x18002ffd7  inc     rdi
0x18002ffda  cmp     rdi, 7FFFFFFFh
0x18002ffe1  jnb     loc_180030228
0x18002ffe7  cmp     [rax], r13w
0x18002ffeb  jz      loc_1800302C5
0x18002fff1  add     rax, 2
0x18002fff5  jmp     short loc_18002FFD1
0x18002fff7  lea     rdx, [rdi+1]
0x18002fffb  add     rdx, r14; unsigned __int64
0x18002fffe  lea     rcx, [rsp+2B0h+var_260]; this
0x180030003  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x180030008  mov     ebx, eax
0x18003000a  test    eax, eax
0x18003000c  js      loc_1800302CD
0x180030012  test    r14, r14
0x180030015  jnz     loc_1800300C7
0x18003001b  mov     rdx, [rbp+1B0h+var_50]; unsigned __int64
0x180030022  mov     r8, rsi; unsigned __int16 *
0x180030025  mov     rcx, [rbp+1B0h+var_48]; unsigned __int16 *
0x18003002c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180030031  mov     ebx, eax
0x180030033  test    eax, eax
0x180030035  jns     loc_1800300E9
0x18003003b  mov     edx, 139h; void *
0x180030040  mov     rcx, [rbp+1B8h]; this
0x180030047  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003004e  mov     r9d, ebx; char *
0x180030051  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030056  mov     rcx, [rbp+1B8h]; this
0x18003005d  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030064  mov     r9d, ebx; char *
0x180030067  mov     edx, 0BDh; void *
0x18003006c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030071  mov     rcx, [rsp+2B0h+var_260]
0x180030076  mov     [rsp+2B0h+var_260], r12
0x18003007b  test    rcx, rcx
0x18003007e  jz      short loc_180030086
0x180030080  call    cs:__imp_SRCache_Free
0x180030086  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18003008b  mov     qword ptr [rsp+2B0h+var_290], r12
0x180030090  test    rcx, rcx
0x180030093  jz      short loc_18003009B
0x180030095  call    cs:__imp_SRCacheContext_Close
0x18003009b  mov     eax, ebx
0x18003009d  mov     rcx, [rbp+1B0h+var_40]
0x1800300a4  xor     rcx, rsp; StackCookie
0x1800300a7  call    __security_check_cookie
0x1800300ac  mov     rbx, [rsp+2B0h+arg_18]
0x1800300b4  add     rsp, 280h
0x1800300bb  pop     r15
0x1800300bd  pop     r14
0x1800300bf  pop     r13
0x1800300c1  pop     r12
0x1800300c3  pop     rdi
0x1800300c4  pop     rsi
0x1800300c5  pop     rbp
0x1800300c6  retn
0x1800300c7  mov     rcx, [rbp+1B0h+var_58]
0x1800300ce  mov     rax, [rbp+1B0h+var_48]
0x1800300d5  lea     rdx, [rax+rcx*2]
0x1800300d9  mov     rcx, r12
0x1800300dc  test    rdi, rdi
0x1800300df  jnz     loc_1800302D7
0x1800300e5  mov     [rdx], r12w
0x1800300e9  add     [rbp+1B0h+var_58], rdi
0x1800300f0  mov     rbx, qword ptr [rsp+2B0h+var_290]
0x1800300f5  mov     rdx, [rbp+1B0h+var_48]
0x1800300fc  lea     rax, [rsp+2B0h+var_288]
0x180030101  mov     [rsp+2B0h+var_288], r12
0x180030106  lea     r9, [rsp+2B0h+var_278]
0x18003010b  mov     [rsp+2B0h+var_280], rax
0x180030110  xor     r8d, r8d
0x180030113  mov     [rsp+2B0h+var_278], r12
0x180030118  mov     rcx, rbx
0x18003011b  mov     [rsp+2B0h+var_270], 1
0x180030120  call    cs:__imp_SRCacheContext_OpenSubContext
0x180030126  mov     ebx, eax
0x180030128  cmp     [rsp+2B0h+var_270], r12b
0x18003012d  jz      short loc_18003014A
0x18003012f  mov     r8, [rsp+2B0h+var_280]
0x180030134  mov     rdx, [rsp+2B0h+var_278]
0x180030139  mov     rcx, [r8]
0x18003013c  mov     [r8], rdx
0x18003013f  test    rcx, rcx
0x180030142  jz      short loc_18003014A
0x180030144  call    cs:__imp_SRCacheContext_Close
0x18003014a  test    ebx, ebx
0x18003014c  js      loc_180030237
0x180030152  mov     rcx, [rsp+2B0h+var_288]
0x180030157  test    rcx, rcx
0x18003015a  setnz   al
0x18003015d  test    al, al
0x18003015f  jz      short loc_180030176
0x180030161  mov     r8, r15
0x180030164  xor     edx, edx
0x180030166  call    cs:__imp_SRCacheContext_EnumerateData
0x18003016c  mov     ebx, eax
0x18003016e  test    eax, eax
0x180030170  js      loc_1800302A0
0x180030176  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18003017b  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x180030182  call    cs:__imp_SRCacheContext_AddToCache
0x180030188  mov     ebx, eax
0x18003018a  test    eax, eax
0x18003018c  js      short loc_1800301D4
0x18003018e  mov     rcx, [rsp+2B0h+var_288]
0x180030193  mov     [rsp+2B0h+var_288], r12
0x180030198  test    rcx, rcx
0x18003019b  jz      short loc_1800301A3
0x18003019d  call    cs:__imp_SRCacheContext_Close
0x1800301a3  mov     rcx, [rsp+2B0h+var_260]
0x1800301a8  mov     [rsp+2B0h+var_260], r12
0x1800301ad  test    rcx, rcx
0x1800301b0  jz      short loc_1800301B8
0x1800301b2  call    cs:__imp_SRCache_Free
0x1800301b8  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800301bd  mov     qword ptr [rsp+2B0h+var_290], r12
0x1800301c2  test    rcx, rcx
0x1800301c5  jz      short loc_1800301CD
0x1800301c7  call    cs:__imp_SRCacheContext_Close
0x1800301cd  xor     eax, eax
0x1800301cf  jmp     loc_18003009D
0x1800301d4  mov     rcx, [rbp+1B8h]; this
0x1800301db  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800301e2  mov     r9d, ebx; char *
0x1800301e5  mov     edx, 1A6h; void *
0x1800301ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800301ef  mov     edx, 0C7h; void *
0x1800301f4  mov     rcx, [rbp+1B8h]; this
0x1800301fb  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030202  mov     r9d, ebx; char *
0x180030205  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003020a  mov     rcx, [rsp+2B0h+var_288]
0x18003020f  mov     [rsp+2B0h+var_288], r12
0x180030214  test    rcx, rcx
0x180030217  jz      loc_180030071
0x18003021d  call    cs:__imp_SRCacheContext_Close
0x180030223  jmp     loc_180030071
0x180030228  mov     ebx, 80070057h
0x18003022d  mov     edx, 135h
0x180030232  jmp     loc_180030040
0x180030237  mov     rcx, [rbp+1B8h]; this
0x18003023e  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030245  mov     r9d, ebx; char *
0x180030248  mov     edx, 1B0h; void *
0x18003024d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030252  mov     edx, 0C1h
0x180030257  jmp     short loc_1800301F4
0x180030259  mov     rcx, [rbp+1B8h]; this
0x180030260  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030267  mov     r9d, ebx; char *
0x18003026a  mov     edx, 18Ch; void *
0x18003026f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030274  mov     edx, 0B9h; void *
0x180030279  mov     rcx, [rbp+1B8h]; this
0x180030280  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030287  mov     r9d, ebx; char *
0x18003028a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003028f  jmp     loc_180030086
0x180030294  mov     ebx, 80670012h
0x180030299  mov     edx, 0BAh
0x18003029e  jmp     short loc_180030279
0x1800302a0  mov     rcx, [rbp+1B8h]; this
0x1800302a7  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800302ae  mov     r9d, ebx; char *
0x1800302b1  mov     edx, 2A6h; void *
0x1800302b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800302bb  mov     edx, 0C4h
0x1800302c0  jmp     loc_1800301F4
0x1800302c5  inc     r14
0x1800302c8  jmp     loc_18002FFF1
0x1800302cd  mov     edx, 136h
0x1800302d2  jmp     loc_180030040
0x1800302d7  cmp     [rsi], r13w
0x1800302db  jnz     loc_18018D5A2
0x1800302e1  mov     [rdx], r13w
0x1800302e5  add     rdx, 2
0x1800302e9  jmp     loc_18018D5A2
0x18018d5a2  movzx   eax, word ptr [rsi]
0x18018d5a5  inc     rcx
0x18018d5a8  mov     [rdx], ax
0x18018d5ab  add     rsi, 2
0x18018d5af  add     rdx, 2
0x18018d5b3  cmp     rcx, rdi
0x18018d5b6  jb      loc_1800302D7
0x18018d5bc  jmp     loc_1800300E5
```
