# StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)

- ea: `0x180056fe8`
- end: `0x18005729e`
- name: `?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z`
- size: `694`
- prototype: `int(StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18004d174`

## callees

- `0x180008be0`
- `0x18000a980`
- `0x18000b5c0`
- `0x18000cb80`
- `0x18002ec54`
- `0x18002f830`
- `0x1800304a0`
- `0x180056fe8`
- `0x18005ae90`
- `0x18005ba40`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180057059`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800570bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180057106`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180057275`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180057059`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800570bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180057106`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180057275`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180057187`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180057246`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180057260`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180057187`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180057246`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180057260`

## string_xrefs

- `0x18005702e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18005709c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800570da`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180057165`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18005721f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180057068`: `ApplicationExtension\Index\ApplicationAndCategory`
- `0x180057201`: `ApplicationExtension\Index\ApplicationAndCategory`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(
        StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80070057LL,
      v13);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v15 = 0;
  LOBYTE(v14) = 0;
  v9 = StateRepository::Cache::Context_NoThrow::Open(&v15, a2, L"ApplicationExtension\\Index\\ApplicationAndCategory");
  v10 = v9;
  if ( v9 >= 0 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F4,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80670012LL,
      (int)&v14);
    v12 = v15;
    v15 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return v6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2F3,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
    (const char *)(unsigned int)v9,
    (int)&v14);
  v11 = v15;
  v15 = 0;
  if ( v11 )
    SRCacheContext_Close(v11);
  return v10;
}

```

## disassembly

```asm
0x180056fe8  push    rbp
0x180056fea  push    rbx
0x180056feb  push    rsi
0x180056fec  push    rdi
0x180056fed  push    r12
0x180056fef  push    r14
0x180056ff1  push    r15
0x180056ff3  lea     rbp, [rsp-170h]
0x180056ffb  sub     rsp, 270h
0x180057002  mov     rax, cs:__security_cookie
0x180057009  xor     rax, rsp
0x18005700c  mov     [rbp+1A0h+var_40], rax
0x180057013  xor     r12d, r12d
0x180057016  mov     r15, r9
0x180057019  mov     r14, r8
0x18005701c  mov     rsi, rdx
0x18005701f  mov     rbx, rcx
0x180057022  test    r8, r8
0x180057025  jnz     short loc_18005704E
0x180057027  mov     rcx, [rbp+1A8h]; this
0x18005702e  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180057035  mov     ebx, 80070057h
0x18005703a  mov     edx, 2EDh; void *
0x18005703f  mov     r9d, ebx; char *
0x180057042  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057047  mov     eax, ebx
0x180057049  jmp     loc_18005727D
0x18005704e  mov     rcx, [rcx]
0x180057051  mov     [rbx], r12
0x180057054  test    rcx, rcx
0x180057057  jz      short loc_18005705F
0x180057059  call    cs:__imp_SRCacheContext_Close
0x18005705f  lea     rax, [rsp+2A0h+var_270]
0x180057064  mov     [rbx+8], r12d
0x180057068  lea     r8, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x18005706f  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x180057074  mov     rdx, rsi
0x180057077  mov     [rbx+10h], r12
0x18005707b  lea     rcx, [rsp+2A0h+var_268]
0x180057080  mov     [rsp+2A0h+var_268], r12
0x180057085  mov     byte ptr [rsp+2A0h+var_270], r12b
0x18005708a  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18005708f  mov     edi, eax
0x180057091  test    eax, eax
0x180057093  jns     short loc_1800570CC
0x180057095  mov     rcx, [rbp+1A8h]; this
0x18005709c  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800570a3  mov     r9d, eax; char *
0x1800570a6  mov     edx, 2F3h; void *
0x1800570ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800570b0  mov     rcx, [rsp+2A0h+var_268]
0x1800570b5  mov     [rsp+2A0h+var_268], r12
0x1800570ba  test    rcx, rcx
0x1800570bd  jz      short loc_1800570C5
0x1800570bf  call    cs:__imp_SRCacheContext_Close
0x1800570c5  mov     eax, edi
0x1800570c7  jmp     loc_18005727D
0x1800570cc  cmp     byte ptr [rsp+2A0h+var_270], r12b
0x1800570d1  jnz     short loc_180057111
0x1800570d3  mov     rcx, [rbp+1A8h]; this
0x1800570da  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800570e1  mov     ebx, 80670012h
0x1800570e6  mov     edx, 2F4h; void *
0x1800570eb  mov     r9d, ebx; char *
0x1800570ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800570f3  mov     rcx, [rsp+2A0h+var_268]
0x1800570f8  mov     [rsp+2A0h+var_268], r12
0x1800570fd  test    rcx, rcx
0x180057100  jz      loc_180057047
0x180057106  call    cs:__imp_SRCacheContext_Close
0x18005710c  jmp     loc_180057047
0x180057111  xor     edx, edx; Val
0x180057113  mov     [rsp+2A0h+var_260], r12
0x180057118  mov     r8d, 200h; Size
0x18005711e  lea     rcx, [rsp+2A0h+var_258]; void *
0x180057123  call    memset_0
0x180057128  lea     rax, [rsp+2A0h+var_258]
0x18005712d  mov     [rbp+1A0h+var_58], r12
0x180057134  mov     rdx, r14; unsigned __int64
0x180057137  mov     [rbp+1A0h+var_48], rax
0x18005713e  lea     rcx, [rsp+2A0h+var_260]; this
0x180057143  mov     [rbp+1A0h+var_50], 100h
0x18005714e  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180057153  mov     edi, eax
0x180057155  test    eax, eax
0x180057157  jns     short loc_180057192
0x180057159  mov     edx, 2F7h; void *
0x18005715e  mov     rcx, [rbp+1A8h]; this
0x180057165  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18005716c  mov     r9d, edi; char *
0x18005716f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057174  mov     rcx, [rsp+2A0h+var_260]
0x180057179  mov     [rsp+2A0h+var_260], r12
0x18005717e  test    rcx, rcx
0x180057181  jz      loc_1800570B0
0x180057187  call    cs:__imp_SRCache_Free
0x18005718d  jmp     loc_1800570B0
0x180057192  lea     rcx, [rsp+2A0h+var_260]; this
0x180057197  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18005719c  mov     edi, eax
0x18005719e  test    eax, eax
0x1800571a0  jns     short loc_1800571A9
0x1800571a2  mov     edx, 2F8h
0x1800571a7  jmp     short loc_18005715E
0x1800571a9  mov     rdx, r15; unsigned __int16 *
0x1800571ac  lea     rcx, [rsp+2A0h+var_260]; this
0x1800571b1  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800571b6  mov     edi, eax
0x1800571b8  test    eax, eax
0x1800571ba  jns     short loc_1800571C3
0x1800571bc  mov     edx, 2F9h
0x1800571c1  jmp     short loc_18005715E
0x1800571c3  mov     r8, [rbp+1A0h+var_48]
0x1800571ca  lea     rax, [rsp+2A0h+var_270]
0x1800571cf  lea     rdx, [rsp+2A0h+var_268]
0x1800571d4  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x1800571d9  mov     rcx, rbx
0x1800571dc  mov     byte ptr [rsp+2A0h+var_270], r12b
0x1800571e1  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800571e6  mov     edi, eax
0x1800571e8  test    eax, eax
0x1800571ea  jns     short loc_1800571F6
0x1800571ec  mov     edx, 2FCh
0x1800571f1  jmp     loc_18005715E
0x1800571f6  cmp     byte ptr [rsp+2A0h+var_270], r12b
0x1800571fb  jz      short loc_180057201
0x1800571fd  mov     [rbx+10h], rsi
0x180057201  lea     rdx, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x180057208  lea     rcx, [rsp+2A0h+var_268]; this
0x18005720d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180057212  mov     ebx, eax
0x180057214  test    eax, eax
0x180057216  jns     short loc_180057251
0x180057218  mov     rcx, [rbp+1A8h]; this
0x18005721f  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180057226  mov     r9d, eax; char *
0x180057229  mov     edx, 302h; void *
0x18005722e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057233  mov     rcx, [rsp+2A0h+var_260]
0x180057238  mov     [rsp+2A0h+var_260], r12
0x18005723d  test    rcx, rcx
0x180057240  jz      loc_1800570F3
0x180057246  call    cs:__imp_SRCache_Free
0x18005724c  jmp     loc_1800570F3
0x180057251  mov     rcx, [rsp+2A0h+var_260]
0x180057256  mov     [rsp+2A0h+var_260], r12
0x18005725b  test    rcx, rcx
0x18005725e  jz      short loc_180057266
0x180057260  call    cs:__imp_SRCache_Free
0x180057266  mov     rcx, [rsp+2A0h+var_268]
0x18005726b  mov     [rsp+2A0h+var_268], r12
0x180057270  test    rcx, rcx
0x180057273  jz      short loc_18005727B
0x180057275  call    cs:__imp_SRCacheContext_Close
0x18005727b  xor     eax, eax
0x18005727d  mov     rcx, [rbp+1A0h+var_40]
0x180057284  xor     rcx, rsp; StackCookie
0x180057287  call    __security_check_cookie
0x18005728c  add     rsp, 270h
0x180057293  pop     r15
0x180057295  pop     r14
0x180057297  pop     r12
0x180057299  pop     rdi
0x18005729a  pop     rsi
0x18005729b  pop     rbx
0x18005729c  pop     rbp
0x18005729d  retn
```
