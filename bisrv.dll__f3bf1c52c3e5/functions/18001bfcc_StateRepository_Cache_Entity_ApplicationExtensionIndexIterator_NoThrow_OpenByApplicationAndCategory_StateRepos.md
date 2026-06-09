# StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)

- ea: `0x18001bfcc`
- end: `0x18001c30e`
- name: `?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z`
- size: `834`
- prototype: `int(StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180051030`

## callees

- `0x180018be0`
- `0x180019f90`
- `0x18001a1f0`
- `0x18001bee4`
- `0x18001bfcc`
- `0x18004b094`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001c076`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001c076`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c03d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c09a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c0e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c135`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c239`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c2e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c03d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c09a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c0e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c135`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c239`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c2e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001c215`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001c215`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c1b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c2b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c2d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c1b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c2b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c2d0`

## string_xrefs

- `0x18001c0ab`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001c24a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001c012`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18001c0c6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18001c109`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18001c194`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18001c28f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18001c058`: `ApplicationExtension\Index\ApplicationAndCategory`
- `0x18001c271`: `ApplicationExtension\Index\ApplicationAndCategory`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(
        StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3,
        const unsigned __int16 *a4)
{
  unsigned int v8; // ebx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // edi
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned __int16 v16; // dx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v25; // [rsp+28h] [rbp-D8h]
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  char v27; // [rsp+38h] [rbp-C8h]
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v29[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+248h] [rbp+148h]
  __int64 v31; // [rsp+250h] [rbp+150h]
  _BYTE *v32; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a3 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80070057LL,
      v24[0]);
    return v8;
  }
  v10 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v10 )
    SRCacheContext_Close(v10);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v11 = *(_QWORD *)a2;
  v25 = v24;
  *(_QWORD *)v24 = 0;
  v26 = 0;
  v27 = 1;
  v12 = SRCacheContext_Open(v11, L"ApplicationExtension\\Index\\ApplicationAndCategory", 0, &v26);
  if ( v27 )
  {
    v13 = *(_QWORD *)v25;
    *(_QWORD *)v25 = v26;
    if ( v13 )
      SRCacheContext_Close(v13);
  }
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v12,
      v24[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F3,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v12,
      v24[0]);
LABEL_11:
    v14 = *(_QWORD *)v24;
    *(_QWORD *)v24 = 0;
    if ( v14 )
      SRCacheContext_Close(v14);
    return (unsigned int)v12;
  }
  if ( !*(_QWORD *)v24 )
  {
    v8 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F4,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_16:
    v15 = *(_QWORD *)v24;
    *(_QWORD *)v24 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
    return v8;
  }
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v30 = 0;
  v32 = v29;
  v31 = 256;
  v12 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, a3);
  if ( v12 < 0 )
  {
    v17 = 759;
    goto LABEL_20;
  }
  v12 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, v16);
  if ( v12 < 0 )
  {
    v17 = 760;
    goto LABEL_20;
  }
  v12 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, a4);
  if ( v12 < 0 )
  {
    v17 = 761;
    goto LABEL_20;
  }
  v25 = (int *)this;
  v26 = 0;
  v27 = 1;
  v12 = SRCacheContext_OpenSubContext(*(_QWORD *)v24, v32, 0, &v26);
  if ( v27 )
  {
    v19 = *(_QWORD *)v25;
    *(_QWORD *)v25 = v26;
    if ( v19 )
      SRCacheContext_Close(v19);
  }
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v12,
      v24[0]);
    v17 = 764;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v12,
      v24[0]);
    v18 = v28;
    v28 = 0;
    if ( v18 )
      SRCache_Free(v18);
    goto LABEL_11;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v20 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v24,
          L"ApplicationExtension\\Index\\ApplicationAndCategory");
  v8 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x302,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v20,
      v24[0]);
    v21 = v28;
    v28 = 0;
    if ( v21 )
      SRCache_Free(v21);
    goto LABEL_16;
  }
  v22 = v28;
  v28 = 0;
  if ( v22 )
    SRCache_Free(v22);
  v23 = *(_QWORD *)v24;
  *(_QWORD *)v24 = 0;
  if ( v23 )
    SRCacheContext_Close(v23);
  return 0;
}

```

## disassembly

```asm
0x18001bfcc  push    rbp
0x18001bfce  push    rbx
0x18001bfcf  push    rsi
0x18001bfd0  push    rdi
0x18001bfd1  push    r12
0x18001bfd3  push    r14
0x18001bfd5  push    r15
0x18001bfd7  lea     rbp, [rsp-170h]
0x18001bfdf  sub     rsp, 270h
0x18001bfe6  mov     rax, cs:__security_cookie
0x18001bfed  xor     rax, rsp
0x18001bff0  mov     [rbp+1A0h+var_40], rax
0x18001bff7  xor     r12d, r12d
0x18001bffa  mov     r15, r9
0x18001bffd  mov     r14, r8
0x18001c000  mov     rsi, rdx
0x18001c003  mov     rbx, rcx
0x18001c006  test    r8, r8
0x18001c009  jnz     short loc_18001C032
0x18001c00b  mov     rcx, [rbp+1A8h]; this
0x18001c012  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c019  mov     ebx, 80070057h
0x18001c01e  mov     edx, 2EDh; void *
0x18001c023  mov     r9d, ebx; char *
0x18001c026  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c02b  mov     eax, ebx
0x18001c02d  jmp     loc_18001C2ED
0x18001c032  mov     rcx, [rcx]
0x18001c035  mov     [rbx], r12
0x18001c038  test    rcx, rcx
0x18001c03b  jz      short loc_18001C043
0x18001c03d  call    cs:__imp_SRCacheContext_Close
0x18001c043  mov     [rbx+8], r12d
0x18001c047  lea     rax, [rsp+2A0h+var_280]
0x18001c04c  mov     [rbx+10h], r12
0x18001c050  lea     r9, [rsp+2A0h+var_270]
0x18001c055  mov     rcx, [rsi]
0x18001c058  lea     rdx, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x18001c05f  xor     r8d, r8d
0x18001c062  mov     [rsp+2A0h+var_278], rax
0x18001c067  mov     qword ptr [rsp+2A0h+var_280], r12; int
0x18001c06c  mov     [rsp+2A0h+var_270], r12
0x18001c071  mov     [rsp+2A0h+var_268], 1
0x18001c076  call    cs:__imp_SRCacheContext_Open
0x18001c07c  mov     edi, eax
0x18001c07e  cmp     [rsp+2A0h+var_268], r12b
0x18001c083  jz      short loc_18001C0A0
0x18001c085  mov     r8, [rsp+2A0h+var_278]
0x18001c08a  mov     rdx, [rsp+2A0h+var_270]
0x18001c08f  mov     rcx, [r8]
0x18001c092  mov     [r8], rdx
0x18001c095  test    rcx, rcx
0x18001c098  jz      short loc_18001C0A0
0x18001c09a  call    cs:__imp_SRCacheContext_Close
0x18001c0a0  test    edi, edi
0x18001c0a2  jns     short loc_18001C0F6
0x18001c0a4  mov     rcx, [rbp+1A8h]; this
0x18001c0ab  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c0b2  mov     r9d, edi; char *
0x18001c0b5  mov     edx, 18Ch; void *
0x18001c0ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c0bf  mov     rcx, [rbp+1A8h]; this
0x18001c0c6  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c0cd  mov     r9d, edi; char *
0x18001c0d0  mov     edx, 2F3h; void *
0x18001c0d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c0da  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001c0df  mov     qword ptr [rsp+2A0h+var_280], r12
0x18001c0e4  test    rcx, rcx
0x18001c0e7  jz      short loc_18001C0EF
0x18001c0e9  call    cs:__imp_SRCacheContext_Close
0x18001c0ef  mov     eax, edi
0x18001c0f1  jmp     loc_18001C2ED
0x18001c0f6  cmp     qword ptr [rsp+2A0h+var_280], r12
0x18001c0fb  setnz   al
0x18001c0fe  test    al, al
0x18001c100  jnz     short loc_18001C140
0x18001c102  mov     rcx, [rbp+1A8h]; this
0x18001c109  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c110  mov     ebx, 80670012h
0x18001c115  mov     edx, 2F4h; void *
0x18001c11a  mov     r9d, ebx; char *
0x18001c11d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c122  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001c127  mov     qword ptr [rsp+2A0h+var_280], r12
0x18001c12c  test    rcx, rcx
0x18001c12f  jz      loc_18001C02B
0x18001c135  call    cs:__imp_SRCacheContext_Close
0x18001c13b  jmp     loc_18001C02B
0x18001c140  xor     edx, edx; Val
0x18001c142  mov     [rsp+2A0h+var_260], r12
0x18001c147  mov     r8d, 200h; Size
0x18001c14d  lea     rcx, [rsp+2A0h+var_258]; void *
0x18001c152  call    memset_0
0x18001c157  lea     rax, [rsp+2A0h+var_258]
0x18001c15c  mov     [rbp+1A0h+var_58], r12
0x18001c163  mov     rdx, r14; unsigned __int64
0x18001c166  mov     [rbp+1A0h+var_48], rax
0x18001c16d  lea     rcx, [rsp+2A0h+var_260]; this
0x18001c172  mov     [rbp+1A0h+var_50], 100h
0x18001c17d  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001c182  mov     edi, eax
0x18001c184  test    eax, eax
0x18001c186  jns     short loc_18001C1C1
0x18001c188  mov     edx, 2F7h; void *
0x18001c18d  mov     rcx, [rbp+1A8h]; this
0x18001c194  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c19b  mov     r9d, edi; char *
0x18001c19e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c1a3  mov     rcx, [rsp+2A0h+var_260]
0x18001c1a8  mov     [rsp+2A0h+var_260], r12
0x18001c1ad  test    rcx, rcx
0x18001c1b0  jz      loc_18001C0DA
0x18001c1b6  call    cs:__imp_SRCache_Free
0x18001c1bc  jmp     loc_18001C0DA
0x18001c1c1  lea     rcx, [rsp+2A0h+var_260]; this
0x18001c1c6  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18001c1cb  mov     edi, eax
0x18001c1cd  test    eax, eax
0x18001c1cf  jns     short loc_18001C1D8
0x18001c1d1  mov     edx, 2F8h
0x18001c1d6  jmp     short loc_18001C18D
0x18001c1d8  mov     rdx, r15; unsigned __int16 *
0x18001c1db  lea     rcx, [rsp+2A0h+var_260]; this
0x18001c1e0  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18001c1e5  mov     edi, eax
0x18001c1e7  test    eax, eax
0x18001c1e9  jns     short loc_18001C1F2
0x18001c1eb  mov     edx, 2F9h
0x18001c1f0  jmp     short loc_18001C18D
0x18001c1f2  mov     rdx, [rbp+1A0h+var_48]
0x18001c1f9  lea     r9, [rsp+2A0h+var_270]
0x18001c1fe  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001c203  xor     r8d, r8d
0x18001c206  mov     [rsp+2A0h+var_278], rbx
0x18001c20b  mov     [rsp+2A0h+var_270], r12
0x18001c210  mov     [rsp+2A0h+var_268], 1
0x18001c215  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001c21b  mov     edi, eax
0x18001c21d  cmp     [rsp+2A0h+var_268], r12b
0x18001c222  jz      short loc_18001C23F
0x18001c224  mov     r8, [rsp+2A0h+var_278]
0x18001c229  mov     rdx, [rsp+2A0h+var_270]
0x18001c22e  mov     rcx, [r8]
0x18001c231  mov     [r8], rdx
0x18001c234  test    rcx, rcx
0x18001c237  jz      short loc_18001C23F
0x18001c239  call    cs:__imp_SRCacheContext_Close
0x18001c23f  test    edi, edi
0x18001c241  jns     short loc_18001C268
0x18001c243  mov     rcx, [rbp+1A8h]; this
0x18001c24a  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c251  mov     r9d, edi; char *
0x18001c254  mov     edx, 1B0h; void *
0x18001c259  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c25e  mov     edx, 2FCh
0x18001c263  jmp     loc_18001C18D
0x18001c268  cmp     [rbx], r12
0x18001c26b  jz      short loc_18001C271
0x18001c26d  mov     [rbx+10h], rsi
0x18001c271  lea     rdx, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x18001c278  lea     rcx, [rsp+2A0h+var_280]; this
0x18001c27d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001c282  mov     ebx, eax
0x18001c284  test    eax, eax
0x18001c286  jns     short loc_18001C2C1
0x18001c288  mov     rcx, [rbp+1A8h]; this
0x18001c28f  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c296  mov     r9d, eax; char *
0x18001c299  mov     edx, 302h; void *
0x18001c29e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c2a3  mov     rcx, [rsp+2A0h+var_260]
0x18001c2a8  mov     [rsp+2A0h+var_260], r12
0x18001c2ad  test    rcx, rcx
0x18001c2b0  jz      loc_18001C122
0x18001c2b6  call    cs:__imp_SRCache_Free
0x18001c2bc  jmp     loc_18001C122
0x18001c2c1  mov     rcx, [rsp+2A0h+var_260]
0x18001c2c6  mov     [rsp+2A0h+var_260], r12
0x18001c2cb  test    rcx, rcx
0x18001c2ce  jz      short loc_18001C2D6
0x18001c2d0  call    cs:__imp_SRCache_Free
0x18001c2d6  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001c2db  mov     qword ptr [rsp+2A0h+var_280], r12
0x18001c2e0  test    rcx, rcx
0x18001c2e3  jz      short loc_18001C2EB
0x18001c2e5  call    cs:__imp_SRCacheContext_Close
0x18001c2eb  xor     eax, eax
0x18001c2ed  mov     rcx, [rbp+1A0h+var_40]
0x18001c2f4  xor     rcx, rsp; StackCookie
0x18001c2f7  call    __security_check_cookie
0x18001c2fc  add     rsp, 270h
0x18001c303  pop     r15
0x18001c305  pop     r14
0x18001c307  pop     r12
0x18001c309  pop     rdi
0x18001c30a  pop     rsi
0x18001c30b  pop     rbx
0x18001c30c  pop     rbp
0x18001c30d  retn
```
