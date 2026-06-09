# StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)

- ea: `0x18002ff94`
- end: `0x1800302ec`
- name: `?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z`
- size: `856`
- prototype: `int(StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18004da98`

## callees

- `0x180016b10`
- `0x180019780`
- `0x18001ffa0`
- `0x18002108c`
- `0x18002f59c`
- `0x18002ff94`
- `0x180030914`
- `0x18003e210`
- `0x18003eca8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18003020b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18003020b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18003003e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18003003e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030005`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030099`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800300e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800302c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030005`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030099`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800300e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800302c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030166`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030294`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800302ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030166`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030294`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800302ae`

## string_xrefs

- `0x180030193`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18003005b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180030228`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002ffda`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180030076`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800300b9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180030144`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18003026d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180030020`: `ApplicationExtension\Index\ApplicationAndCategory`
- `0x18003024f`: `ApplicationExtension\Index\ApplicationAndCategory`

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
  bool v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v24; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  char v26; // [rsp+38h] [rbp-C8h]
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v28[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+248h] [rbp+148h]
  __int64 v30; // [rsp+250h] [rbp+150h]
  _BYTE *v31; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a3 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80070057LL,
      v23[0]);
    return v8;
  }
  v10 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v10 )
    SRCacheContext_Close(v10);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v11 = *(_QWORD *)a2;
  v24 = v23;
  *(_QWORD *)v23 = 0;
  v25 = 0;
  v26 = 1;
  v12 = SRCacheContext_Open(v11, L"ApplicationExtension\\Index\\ApplicationAndCategory", 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v24);
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v12,
      v23[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F3,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v12,
      v23[0]);
LABEL_8:
    v13 = *(_QWORD *)v23;
    *(_QWORD *)v23 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    return (unsigned int)v12;
  }
  if ( !*(_QWORD *)v23 )
  {
    v8 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F4,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_13:
    v14 = *(_QWORD *)v23;
    *(_QWORD *)v23 = 0;
    if ( v14 )
      SRCacheContext_Close(v14);
    return v8;
  }
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v29 = 0;
  v31 = v28;
  v30 = 256;
  v12 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a3);
  if ( v12 < 0 )
  {
    v16 = 759;
    goto LABEL_17;
  }
  v18 = StateRepository::Cache::Key_NoThrow::EnsureCapacity((StateRepository::Cache::Key_NoThrow *)&v27, v29 + 2, v15);
  v12 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)(unsigned int)v18,
      v23[0]);
    v16 = 760;
    goto LABEL_17;
  }
  *(_DWORD *)&v31[2 * v29++] = 94;
  v12 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a4);
  if ( v12 < 0 )
  {
    v16 = 761;
    goto LABEL_17;
  }
  v24 = (int *)this;
  v25 = 0;
  v26 = 1;
  v12 = SRCacheContext_OpenSubContext(*(_QWORD *)v23, v31, 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v24);
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v12,
      v23[0]);
    v16 = 764;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v12,
      v23[0]);
    v17 = v27;
    v27 = 0;
    if ( v17 )
      SRCache_Free();
    goto LABEL_8;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v19 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v23,
          L"ApplicationExtension\\Index\\ApplicationAndCategory");
  v8 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x302,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v19,
      v23[0]);
    v20 = v27;
    v27 = 0;
    if ( v20 )
      SRCache_Free();
    goto LABEL_13;
  }
  v21 = v27;
  v27 = 0;
  if ( v21 )
    SRCache_Free();
  v22 = *(_QWORD *)v23;
  *(_QWORD *)v23 = 0;
  if ( v22 )
    SRCacheContext_Close(v22);
  return 0;
}

```

## disassembly

```asm
0x18002ff94  push    rbp
0x18002ff96  push    rbx
0x18002ff97  push    rsi
0x18002ff98  push    rdi
0x18002ff99  push    r12
0x18002ff9b  push    r14
0x18002ff9d  push    r15
0x18002ff9f  lea     rbp, [rsp-170h]
0x18002ffa7  sub     rsp, 270h
0x18002ffae  mov     rax, cs:__security_cookie
0x18002ffb5  xor     rax, rsp
0x18002ffb8  mov     [rbp+1A0h+var_40], rax
0x18002ffbf  xor     r12d, r12d
0x18002ffc2  mov     r15, r9
0x18002ffc5  mov     r14, r8
0x18002ffc8  mov     rsi, rdx
0x18002ffcb  mov     rbx, rcx
0x18002ffce  test    r8, r8
0x18002ffd1  jnz     short loc_18002FFFA
0x18002ffd3  mov     rcx, [rbp+1A8h]; this
0x18002ffda  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ffe1  mov     ebx, 80070057h
0x18002ffe6  mov     edx, 2EDh; void *
0x18002ffeb  mov     r9d, ebx; char *
0x18002ffee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fff3  mov     eax, ebx
0x18002fff5  jmp     loc_1800302CB
0x18002fffa  mov     rcx, [rcx]
0x18002fffd  mov     [rbx], r12
0x180030000  test    rcx, rcx
0x180030003  jz      short loc_18003000B
0x180030005  call    cs:__imp_SRCacheContext_Close
0x18003000b  mov     [rbx+8], r12d
0x18003000f  lea     rax, [rsp+2A0h+var_280]
0x180030014  mov     [rbx+10h], r12
0x180030018  lea     r9, [rsp+2A0h+var_270]
0x18003001d  mov     rcx, [rsi]
0x180030020  lea     rdx, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x180030027  xor     r8d, r8d
0x18003002a  mov     [rsp+2A0h+var_278], rax
0x18003002f  mov     qword ptr [rsp+2A0h+var_280], r12; int
0x180030034  mov     [rsp+2A0h+var_270], r12
0x180030039  mov     [rsp+2A0h+var_268], 1
0x18003003e  call    cs:__imp_SRCacheContext_Open
0x180030044  lea     rcx, [rsp+2A0h+var_278]
0x180030049  mov     edi, eax
0x18003004b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180030050  test    edi, edi
0x180030052  jns     short loc_1800300A6
0x180030054  mov     rcx, [rbp+1A8h]; this
0x18003005b  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030062  mov     r9d, edi; char *
0x180030065  mov     edx, 18Ch; void *
0x18003006a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003006f  mov     rcx, [rbp+1A8h]; this
0x180030076  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003007d  mov     r9d, edi; char *
0x180030080  mov     edx, 2F3h; void *
0x180030085  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003008a  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18003008f  mov     qword ptr [rsp+2A0h+var_280], r12
0x180030094  test    rcx, rcx
0x180030097  jz      short loc_18003009F
0x180030099  call    cs:__imp_SRCacheContext_Close
0x18003009f  mov     eax, edi
0x1800300a1  jmp     loc_1800302CB
0x1800300a6  cmp     qword ptr [rsp+2A0h+var_280], r12
0x1800300ab  setnz   al
0x1800300ae  test    al, al
0x1800300b0  jnz     short loc_1800300F0
0x1800300b2  mov     rcx, [rbp+1A8h]; this
0x1800300b9  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800300c0  mov     ebx, 80670012h
0x1800300c5  mov     edx, 2F4h; void *
0x1800300ca  mov     r9d, ebx; char *
0x1800300cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800300d2  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800300d7  mov     qword ptr [rsp+2A0h+var_280], r12
0x1800300dc  test    rcx, rcx
0x1800300df  jz      loc_18002FFF3
0x1800300e5  call    cs:__imp_SRCacheContext_Close
0x1800300eb  jmp     loc_18002FFF3
0x1800300f0  xor     edx, edx; Val
0x1800300f2  mov     [rsp+2A0h+var_260], r12
0x1800300f7  mov     r8d, 200h; Size
0x1800300fd  lea     rcx, [rsp+2A0h+var_258]; void *
0x180030102  call    memset_0
0x180030107  lea     rax, [rsp+2A0h+var_258]
0x18003010c  mov     [rbp+1A0h+var_58], r12
0x180030113  mov     rdx, r14; unsigned __int64
0x180030116  mov     [rbp+1A0h+var_48], rax
0x18003011d  lea     rcx, [rsp+2A0h+var_260]; this
0x180030122  mov     [rbp+1A0h+var_50], 100h
0x18003012d  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180030132  mov     edi, eax
0x180030134  test    eax, eax
0x180030136  jns     short loc_180030171
0x180030138  mov     edx, 2F7h; void *
0x18003013d  mov     rcx, [rbp+1A8h]; this
0x180030144  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003014b  mov     r9d, edi; char *
0x18003014e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030153  mov     rcx, [rsp+2A0h+var_260]
0x180030158  mov     [rsp+2A0h+var_260], r12
0x18003015d  test    rcx, rcx
0x180030160  jz      loc_18003008A
0x180030166  call    cs:__imp_SRCache_Free
0x18003016c  jmp     loc_18003008A
0x180030171  mov     rdx, [rbp+1A0h+var_58]
0x180030178  lea     rcx, [rsp+2A0h+var_260]; this
0x18003017d  add     rdx, 2; unsigned __int64
0x180030181  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x180030186  mov     edi, eax
0x180030188  test    eax, eax
0x18003018a  jns     short loc_1800301AE
0x18003018c  mov     rcx, [rbp+1A8h]; this
0x180030193  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003019a  mov     r9d, eax; char *
0x18003019d  mov     edx, 16Dh; void *
0x1800301a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800301a7  mov     edx, 2F8h
0x1800301ac  jmp     short loc_18003013D
0x1800301ae  mov     r8, [rbp+1A0h+var_58]
0x1800301b5  mov     rdx, r15; unsigned __int16 *
0x1800301b8  mov     rcx, [rbp+1A0h+var_48]
0x1800301bf  mov     dword ptr [rcx+r8*2], 5Eh ; '^'
0x1800301c7  lea     rcx, [rsp+2A0h+var_260]; this
0x1800301cc  inc     [rbp+1A0h+var_58]
0x1800301d3  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800301d8  mov     edi, eax
0x1800301da  test    eax, eax
0x1800301dc  jns     short loc_1800301E8
0x1800301de  mov     edx, 2F9h
0x1800301e3  jmp     loc_18003013D
0x1800301e8  mov     rdx, [rbp+1A0h+var_48]
0x1800301ef  lea     r9, [rsp+2A0h+var_270]
0x1800301f4  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800301f9  xor     r8d, r8d
0x1800301fc  mov     [rsp+2A0h+var_278], rbx
0x180030201  mov     [rsp+2A0h+var_270], r12
0x180030206  mov     [rsp+2A0h+var_268], 1
0x18003020b  call    cs:__imp_SRCacheContext_OpenSubContext
0x180030211  lea     rcx, [rsp+2A0h+var_278]
0x180030216  mov     edi, eax
0x180030218  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18003021d  test    edi, edi
0x18003021f  jns     short loc_180030246
0x180030221  mov     rcx, [rbp+1A8h]; this
0x180030228  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003022f  mov     r9d, edi; char *
0x180030232  mov     edx, 1B0h; void *
0x180030237  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003023c  mov     edx, 2FCh
0x180030241  jmp     loc_18003013D
0x180030246  cmp     [rbx], r12
0x180030249  jz      short loc_18003024F
0x18003024b  mov     [rbx+10h], rsi
0x18003024f  lea     rdx, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x180030256  lea     rcx, [rsp+2A0h+var_280]; this
0x18003025b  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180030260  mov     ebx, eax
0x180030262  test    eax, eax
0x180030264  jns     short loc_18003029F
0x180030266  mov     rcx, [rbp+1A8h]; this
0x18003026d  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030274  mov     r9d, eax; char *
0x180030277  mov     edx, 302h; void *
0x18003027c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030281  mov     rcx, [rsp+2A0h+var_260]
0x180030286  mov     [rsp+2A0h+var_260], r12
0x18003028b  test    rcx, rcx
0x18003028e  jz      loc_1800300D2
0x180030294  call    cs:__imp_SRCache_Free
0x18003029a  jmp     loc_1800300D2
0x18003029f  mov     rcx, [rsp+2A0h+var_260]
0x1800302a4  mov     [rsp+2A0h+var_260], r12
0x1800302a9  test    rcx, rcx
0x1800302ac  jz      short loc_1800302B4
0x1800302ae  call    cs:__imp_SRCache_Free
0x1800302b4  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800302b9  mov     qword ptr [rsp+2A0h+var_280], r12
0x1800302be  test    rcx, rcx
0x1800302c1  jz      short loc_1800302C9
0x1800302c3  call    cs:__imp_SRCacheContext_Close
0x1800302c9  xor     eax, eax
0x1800302cb  mov     rcx, [rbp+1A0h+var_40]
0x1800302d2  xor     rcx, rsp; StackCookie
0x1800302d5  call    __security_check_cookie
0x1800302da  add     rsp, 270h
0x1800302e1  pop     r15
0x1800302e3  pop     r14
0x1800302e5  pop     r12
0x1800302e7  pop     rdi
0x1800302e8  pop     rsi
0x1800302e9  pop     rbx
0x1800302ea  pop     rbp
0x1800302eb  retn
```
