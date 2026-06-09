# StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180008f10`
- end: `0x18000935f`
- name: `?Open@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `1103`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180009414`

## callees

- `0x18000720c`
- `0x180008f10`
- `0x180009370`
- `0x18001a208`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x18000908d`
- `msvcrt!_ui64tow_s` at `0x18000908d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180009211`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180009211`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000917b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800092ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000931a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000917b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800092ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000931a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008f95`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008fe4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000902a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180009190`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180009235`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180009301`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000932f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008f95`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008fe4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000902a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180009190`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180009235`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180009301`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000932f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180008f71`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180008f71`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000929b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000929b`

## string_xrefs

- `0x180008fa6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180009246`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800092ae`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180009142`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180008fc1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180009004`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180009158`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180009261`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x1800092c9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

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
  int v13; // edi
  __int64 v14; // rdx
  unsigned __int64 v15; // rbx
  wchar_t *v16; // rax
  __int64 v17; // rsi
  const void *v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // r8
  unsigned __int16 *v21; // rdx
  wchar_t *i; // rcx
  unsigned int v23; // ebx
  __int64 v24; // rcx
  const void *v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  const void *v29; // rcx
  __int64 v30; // rcx
  int v31[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v32; // [rsp+28h] [rbp-D8h]
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  char v34; // [rsp+38h] [rbp-C8h]
  const void *v35; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v36[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+248h] [rbp+148h]
  unsigned __int64 v38; // [rsp+250h] [rbp+150h]
  unsigned __int16 *v39; // [rsp+258h] [rbp+158h]
  wchar_t Buffer[20]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v4 = *(_QWORD *)a1;
  v32 = v31;
  v34 = 1;
  *(_QWORD *)v31 = 0;
  v33 = 0;
  v8 = SRCacheContext_Open(v4, L"ApplicationUser\\Data", 0, &v33);
  if ( v34 )
  {
    v9 = *(_QWORD *)v32;
    *(_QWORD *)v32 = v33;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v8,
      v31[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)v8,
      v31[0]);
    v10 = *(_QWORD *)v31;
    *(_QWORD *)v31 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return v8;
  }
  if ( !*(_QWORD *)v31 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)0x80670012LL,
      0);
    v12 = *(_QWORD *)v31;
    *(_QWORD *)v31 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return 2154233874LL;
  }
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  v37 = 0;
  v39 = (unsigned __int16 *)v36;
  v38 = 256;
  if ( _ui64tow_s(a2, Buffer, 0x11u, 16) )
  {
    v13 = -2147418113;
    v14 = 358;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)(unsigned int)v13,
      v31[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FD,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v13,
      v31[0]);
    v18 = v35;
    v35 = 0;
    if ( v18 )
      SRCache_Free(v18);
    v19 = *(_QWORD *)v31;
    *(_QWORD *)v31 = 0;
    if ( v19 )
      SRCacheContext_Close(v19);
    return (unsigned int)v13;
  }
  v15 = 0;
  v16 = Buffer;
  v17 = 0;
  while ( *v16 )
  {
    if ( ++v15 >= 0x7FFFFFFF )
    {
      v13 = -2147024809;
      v14 = 309;
      goto LABEL_26;
    }
    if ( *v16 == 94 )
      ++v17;
    ++v16;
  }
  v13 = StateRepository::Cache::Key_NoThrow::EnsureCapacity(&v35, (const void *)(v15 + v17 + v37 + 1));
  if ( v13 < 0 )
  {
    v14 = 310;
    goto LABEL_26;
  }
  if ( v17 )
  {
    v20 = 0;
    v21 = &v39[v37];
    for ( i = Buffer; v20 < v15; ++v21 )
    {
      if ( *i == 94 )
        *v21++ = 94;
      ++v20;
      *v21 = *i++;
    }
    *v21 = 0;
  }
  else
  {
    v13 = StringCchCatW(v39, v38, Buffer);
    if ( v13 < 0 )
    {
      v14 = 313;
      goto LABEL_26;
    }
  }
  v37 += v15;
  v32 = (int *)a3;
  v33 = 0;
  v34 = 1;
  v23 = SRCacheContext_OpenSubContext(*(_QWORD *)v31, v39, 0, &v33);
  if ( v34 )
  {
    v24 = *(_QWORD *)v32;
    *(_QWORD *)v32 = v33;
    if ( v24 )
      SRCacheContext_Close(v24);
  }
  if ( (v23 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v23,
      v31[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FE,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)v23,
      v31[0]);
    v25 = v35;
    v35 = 0;
    if ( !v25 )
      goto LABEL_45;
    goto LABEL_44;
  }
  v26 = *(_QWORD *)v31;
  *a4 = *(_QWORD *)a3 != 0;
  v27 = SRCacheContext_AddToCache(v26, L"ApplicationUser\\Data");
  v23 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v27,
      v31[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x200,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)v23,
      v31[0]);
    v25 = v35;
    v35 = 0;
    if ( !v25 )
    {
LABEL_45:
      v28 = *(_QWORD *)v31;
      *(_QWORD *)v31 = 0;
      if ( v28 )
        SRCacheContext_Close(v28);
      return v23;
    }
LABEL_44:
    SRCache_Free(v25);
    goto LABEL_45;
  }
  v29 = v35;
  v35 = 0;
  if ( v29 )
    SRCache_Free(v29);
  v30 = *(_QWORD *)v31;
  *(_QWORD *)v31 = 0;
  if ( v30 )
    SRCacheContext_Close(v30);
  return 0;
}

```

## disassembly

```asm
0x180008f10  push    rbp
0x180008f12  push    rbx
0x180008f13  push    rdi
0x180008f14  push    r12
0x180008f16  push    r14
0x180008f18  push    r15
0x180008f1a  lea     rbp, [rsp-198h]
0x180008f22  sub     rsp, 298h
0x180008f29  mov     rax, cs:__security_cookie
0x180008f30  xor     rax, rsp
0x180008f33  mov     [rbp+1C0h+var_38], rax
0x180008f3a  mov     rcx, [rcx]
0x180008f3d  lea     rax, [rsp+2C0h+var_2A0]
0x180008f42  mov     r15, r9
0x180008f45  mov     [rsp+2C0h+var_298], rax
0x180008f4a  mov     r14, r8
0x180008f4d  mov     [rsp+2C0h+var_288], 1
0x180008f52  mov     rdi, rdx
0x180008f55  lea     r9, [rsp+2C0h+var_290]
0x180008f5a  xor     r12d, r12d
0x180008f5d  lea     rdx, aApplicationuse; "ApplicationUser\\Data"
0x180008f64  xor     r8d, r8d
0x180008f67  mov     qword ptr [rsp+2C0h+var_2A0], r12; int
0x180008f6c  mov     [rsp+2C0h+var_290], r12
0x180008f71  call    cs:__imp_SRCacheContext_Open
0x180008f77  mov     ebx, eax
0x180008f79  cmp     [rsp+2C0h+var_288], r12b
0x180008f7e  jz      short loc_180008F9B
0x180008f80  mov     r8, [rsp+2C0h+var_298]
0x180008f85  mov     rdx, [rsp+2C0h+var_290]
0x180008f8a  mov     rcx, [r8]
0x180008f8d  mov     [r8], rdx
0x180008f90  test    rcx, rcx
0x180008f93  jz      short loc_180008F9B
0x180008f95  call    cs:__imp_SRCacheContext_Close
0x180008f9b  test    ebx, ebx
0x180008f9d  jns     short loc_180008FF1
0x180008f9f  mov     rcx, [rbp+1C8h]; this
0x180008fa6  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008fad  mov     r9d, ebx; char *
0x180008fb0  mov     edx, 18Ch; void *
0x180008fb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fba  mov     rcx, [rbp+1C8h]; this
0x180008fc1  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008fc8  mov     r9d, ebx; char *
0x180008fcb  mov     edx, 1F9h; void *
0x180008fd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fd5  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x180008fda  mov     qword ptr [rsp+2C0h+var_2A0], r12
0x180008fdf  test    rcx, rcx
0x180008fe2  jz      short loc_180008FEA
0x180008fe4  call    cs:__imp_SRCacheContext_Close
0x180008fea  mov     eax, ebx
0x180008fec  jmp     loc_18000933F
0x180008ff1  cmp     qword ptr [rsp+2C0h+var_2A0], r12
0x180008ff6  setnz   al
0x180008ff9  test    al, al
0x180008ffb  jnz     short loc_18000903A
0x180008ffd  mov     rcx, [rbp+1C8h]; this
0x180009004  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000900b  mov     r9d, 80670012h; char *
0x180009011  mov     edx, 1FAh; void *
0x180009016  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000901b  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x180009020  mov     qword ptr [rsp+2C0h+var_2A0], r12
0x180009025  test    rcx, rcx
0x180009028  jz      short loc_180009030
0x18000902a  call    cs:__imp_SRCacheContext_Close
0x180009030  mov     eax, 80670012h
0x180009035  jmp     loc_18000933F
0x18000903a  xor     edx, edx; Val
0x18000903c  mov     [rsp+2C0h+var_30], rsi
0x180009044  mov     r8d, 200h; Size
0x18000904a  mov     [rsp+2C0h+var_280], r12
0x18000904f  lea     rcx, [rsp+2C0h+var_278]; void *
0x180009054  call    memset_0
0x180009059  lea     rax, [rsp+2C0h+var_278]
0x18000905e  mov     [rbp+1C0h+var_78], r12
0x180009065  mov     r9d, 10h; Radix
0x18000906b  mov     [rbp+1C0h+var_68], rax
0x180009072  mov     r8d, 11h; BufferCount
0x180009078  mov     [rbp+1C0h+var_70], 100h
0x180009083  lea     rdx, [rbp+1C0h+Buffer]; Buffer
0x18000908a  mov     rcx, rdi; Value
0x18000908d  call    cs:__imp__ui64tow_s
0x180009093  test    eax, eax
0x180009095  jz      short loc_1800090A6
0x180009097  mov     edi, 8000FFFFh
0x18000909c  mov     edx, 166h
0x1800090a1  jmp     loc_18000913B
0x1800090a6  mov     rbx, r12
0x1800090a9  lea     rax, [rbp+1C0h+Buffer]
0x1800090b0  mov     rsi, r12
0x1800090b3  movzx   ecx, word ptr [rax]
0x1800090b6  test    cx, cx
0x1800090b9  jz      short loc_1800090E2
0x1800090bb  inc     rbx
0x1800090be  cmp     rbx, 7FFFFFFFh
0x1800090c5  jnb     short loc_1800090D6
0x1800090c7  cmp     cx, 5Eh ; '^'
0x1800090cb  jnz     short loc_1800090D0
0x1800090cd  inc     rsi
0x1800090d0  add     rax, 2
0x1800090d4  jmp     short loc_1800090B3
0x1800090d6  mov     edi, 80070057h
0x1800090db  mov     edx, 135h
0x1800090e0  jmp     short loc_18000913B
0x1800090e2  mov     rdx, [rbp+1C0h+var_78]
0x1800090e9  lea     rcx, [rsp+2C0h+var_280]; this
0x1800090ee  inc     rdx
0x1800090f1  add     rdx, rsi
0x1800090f4  add     rdx, rbx; unsigned __int64
0x1800090f7  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x1800090fc  mov     edi, eax
0x1800090fe  test    eax, eax
0x180009100  jns     short loc_180009109
0x180009102  mov     edx, 136h
0x180009107  jmp     short loc_18000913B
0x180009109  test    rsi, rsi
0x18000910c  jnz     loc_18000919D
0x180009112  mov     rdx, [rbp+1C0h+var_70]; unsigned __int64
0x180009119  lea     r8, [rbp+1C0h+Buffer]; unsigned __int16 *
0x180009120  mov     rcx, [rbp+1C0h+var_68]; unsigned __int16 *
0x180009127  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000912c  mov     edi, eax
0x18000912e  test    eax, eax
0x180009130  jns     loc_1800091E7
0x180009136  mov     edx, 139h; void *
0x18000913b  mov     rcx, [rbp+1C8h]; this
0x180009142  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009149  mov     r9d, edi; char *
0x18000914c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009151  mov     rcx, [rbp+1C8h]; this
0x180009158  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000915f  mov     r9d, edi; char *
0x180009162  mov     edx, 1FDh; void *
0x180009167  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000916c  mov     rcx, [rsp+2C0h+var_280]
0x180009171  mov     [rsp+2C0h+var_280], r12
0x180009176  test    rcx, rcx
0x180009179  jz      short loc_180009181
0x18000917b  call    cs:__imp_SRCache_Free
0x180009181  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x180009186  mov     qword ptr [rsp+2C0h+var_2A0], r12
0x18000918b  test    rcx, rcx
0x18000918e  jz      short loc_180009196
0x180009190  call    cs:__imp_SRCacheContext_Close
0x180009196  mov     eax, edi
0x180009198  jmp     loc_180009337
0x18000919d  mov     rcx, [rbp+1C0h+var_78]
0x1800091a4  mov     r8, r12
0x1800091a7  mov     rax, [rbp+1C0h+var_68]
0x1800091ae  lea     rdx, [rax+rcx*2]
0x1800091b2  lea     rcx, [rbp+1C0h+Buffer]
0x1800091b9  test    rbx, rbx
0x1800091bc  jz      short loc_1800091E3
0x1800091be  cmp     word ptr [rcx], 5Eh ; '^'
0x1800091c2  jnz     short loc_1800091CD
0x1800091c4  mov     word ptr [rdx], 5Eh ; '^'
0x1800091c9  add     rdx, 2
0x1800091cd  movzx   eax, word ptr [rcx]
0x1800091d0  inc     r8
0x1800091d3  mov     [rdx], ax
0x1800091d6  add     rcx, 2
0x1800091da  add     rdx, 2
0x1800091de  cmp     r8, rbx
0x1800091e1  jb      short loc_1800091BE
0x1800091e3  mov     [rdx], r12w
0x1800091e7  mov     rdx, [rbp+1C0h+var_68]
0x1800091ee  lea     r9, [rsp+2C0h+var_290]
0x1800091f3  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x1800091f8  xor     r8d, r8d
0x1800091fb  add     [rbp+1C0h+var_78], rbx
0x180009202  mov     [rsp+2C0h+var_298], r14
0x180009207  mov     [rsp+2C0h+var_290], r12
0x18000920c  mov     [rsp+2C0h+var_288], 1
0x180009211  call    cs:__imp_SRCacheContext_OpenSubContext
0x180009217  mov     ebx, eax
0x180009219  cmp     [rsp+2C0h+var_288], r12b
0x18000921e  jz      short loc_18000923B
0x180009220  mov     r8, [rsp+2C0h+var_298]
0x180009225  mov     rdx, [rsp+2C0h+var_290]
0x18000922a  mov     rcx, [r8]
0x18000922d  mov     [r8], rdx
0x180009230  test    rcx, rcx
0x180009233  jz      short loc_18000923B
0x180009235  call    cs:__imp_SRCacheContext_Close
0x18000923b  test    ebx, ebx
0x18000923d  jns     short loc_180009286
0x18000923f  mov     rcx, [rbp+1C8h]; this
0x180009246  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000924d  mov     r9d, ebx; char *
0x180009250  mov     edx, 1B0h; void *
0x180009255  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000925a  mov     rcx, [rbp+1C8h]; this
0x180009261  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009268  mov     r9d, ebx; char *
0x18000926b  mov     edx, 1FEh; void *
0x180009270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009275  mov     rcx, [rsp+2C0h+var_280]
0x18000927a  mov     [rsp+2C0h+var_280], r12
0x18000927f  test    rcx, rcx
0x180009282  jnz     short loc_1800092EC
0x180009284  jmp     short loc_1800092F2
0x180009286  cmp     [r14], r12
0x180009289  lea     rdx, aApplicationuse; "ApplicationUser\\Data"
0x180009290  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x180009295  setnz   al
0x180009298  mov     [r15], al
0x18000929b  call    cs:__imp_SRCacheContext_AddToCache
0x1800092a1  mov     ebx, eax
0x1800092a3  test    eax, eax
0x1800092a5  jns     short loc_18000930B
0x1800092a7  mov     rcx, [rbp+1C8h]; this
0x1800092ae  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800092b5  mov     r9d, eax; char *
0x1800092b8  mov     edx, 1A6h; void *
0x1800092bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800092c2  mov     rcx, [rbp+1C8h]; this
0x1800092c9  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800092d0  mov     r9d, ebx; char *
0x1800092d3  mov     edx, 200h; void *
0x1800092d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800092dd  mov     rcx, [rsp+2C0h+var_280]
0x1800092e2  mov     [rsp+2C0h+var_280], r12
0x1800092e7  test    rcx, rcx
0x1800092ea  jz      short loc_1800092F2
0x1800092ec  call    cs:__imp_SRCache_Free
0x1800092f2  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x1800092f7  mov     qword ptr [rsp+2C0h+var_2A0], r12
0x1800092fc  test    rcx, rcx
0x1800092ff  jz      short loc_180009307
0x180009301  call    cs:__imp_SRCacheContext_Close
0x180009307  mov     eax, ebx
0x180009309  jmp     short loc_180009337
0x18000930b  mov     rcx, [rsp+2C0h+var_280]
0x180009310  mov     [rsp+2C0h+var_280], r12
0x180009315  test    rcx, rcx
0x180009318  jz      short loc_180009320
0x18000931a  call    cs:__imp_SRCache_Free
0x180009320  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x180009325  mov     qword ptr [rsp+2C0h+var_2A0], r12
0x18000932a  test    rcx, rcx
0x18000932d  jz      short loc_180009335
0x18000932f  call    cs:__imp_SRCacheContext_Close
0x180009335  xor     eax, eax
0x180009337  mov     rsi, [rsp+2C0h+var_30]
0x18000933f  mov     rcx, [rbp+1C0h+var_38]
0x180009346  xor     rcx, rsp; StackCookie
0x180009349  call    __security_check_cookie
0x18000934e  add     rsp, 298h
0x180009355  pop     r15
0x180009357  pop     r14
0x180009359  pop     r12
0x18000935b  pop     rdi
0x18000935c  pop     rbx
0x18000935d  pop     rbp
0x18000935e  retn
```
