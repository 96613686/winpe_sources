# StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::OpenByExtension(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x1803682bc`
- end: `0x1803685f8`
- name: `?OpenByExtension@FileTypeAssociationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `828`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180351598`

## callees

- `0x1800432f0`
- `0x1800a0e00`
- `0x18020b35c`
- `0x180291fc8`
- `0x1803682bc`
- `0x1803a4cb0`
- `0x1803a57e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180368469`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180368469`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180368510`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180368510`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1803684da`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18036859b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1803685b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1803684da`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18036859b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1803685b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18036832b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1803683c9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180368415`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1803685ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18036832b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1803683c9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180368415`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1803685ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18036836c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18036836c`

## string_xrefs

- `0x18036847a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18036838b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18036852f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180368300`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1803683a6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1803683e9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1803684b8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x180368574`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x180368348`: `FileTypeAssociation\Index\Extension`
- `0x180368556`: `FileTypeAssociation\Index\Extension`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::OpenByExtension(
        StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+238h] [rbp+138h]
  __int64 v26; // [rsp+240h] [rbp+140h]
  _BYTE *v27; // [rsp+248h] [rbp+148h]
  unsigned __int16 v28[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v29; // [rsp+258h] [rbp+158h] BYREF
  char v30; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x242,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)0x80070057LL,
      v22[0]);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8, a2);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v9 = *(_QWORD *)a2;
  *(_QWORD *)v28 = v22;
  *(_QWORD *)v22 = 0;
  v29 = 0;
  v30 = 1;
  v10 = SRCacheContext_Open(v9, L"FileTypeAssociation\\Index\\Extension", 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v28);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
LABEL_8:
    v12 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v11);
    return (unsigned int)v10;
  }
  if ( !*(_QWORD *)v22 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_13:
    v14 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v14 )
      SRCacheContext_Close(v14, v13);
    return v6;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v26 = 256;
  v27 = v24;
  if ( (unsigned int)_o__ui64tow_s(a3, v28, 17) )
  {
    v10 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v22[0]);
LABEL_18:
    v15 = 588;
    goto LABEL_19;
  }
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, v28);
  if ( v10 < 0 )
    goto LABEL_18;
  *(_QWORD *)v28 = this;
  v29 = 0;
  v30 = 1;
  v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v22, v27, 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v28);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    v15 = 591;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_8;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v17 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v22,
          L"FileTypeAssociation\\Index\\Extension");
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)(unsigned int)v17,
      v22[0]);
    v19 = v23;
    v23 = 0;
    if ( v19 )
      SRCache_Free();
    goto LABEL_13;
  }
  v20 = v23;
  v23 = 0;
  if ( v20 )
    SRCache_Free();
  v21 = *(_QWORD *)v22;
  *(_QWORD *)v22 = 0;
  if ( v21 )
    SRCacheContext_Close(v21, v18);
  return 0;
}

```

## disassembly

```asm
0x1803682bc  mov     [rsp-8+arg_18], rbx
0x1803682c1  push    rbp
0x1803682c2  push    rsi
0x1803682c3  push    rdi
0x1803682c4  push    r14
0x1803682c6  push    r15
0x1803682c8  lea     rbp, [rsp-180h]
0x1803682d0  sub     rsp, 280h
0x1803682d7  mov     rax, cs:__security_cookie
0x1803682de  xor     rax, rsp
0x1803682e1  mov     [rbp+1A0h+var_28], rax
0x1803682e8  xor     r15d, r15d
0x1803682eb  mov     r14, r8
0x1803682ee  mov     rsi, rdx
0x1803682f1  mov     rbx, rcx
0x1803682f4  test    r8, r8
0x1803682f7  jnz     short loc_180368320
0x1803682f9  mov     rcx, [rbp+1A8h]; this
0x180368300  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180368307  mov     ebx, 80070057h
0x18036830c  mov     edx, 242h; void *
0x180368311  mov     r9d, ebx; char *
0x180368314  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180368319  mov     eax, ebx
0x18036831b  jmp     loc_1803685D2
0x180368320  mov     rcx, [rcx]
0x180368323  mov     [rbx], r15
0x180368326  test    rcx, rcx
0x180368329  jz      short loc_180368331
0x18036832b  call    cs:__imp_SRCacheContext_Close
0x180368331  mov     [rbx+8], r15d
0x180368335  lea     rax, [rsp+2A0h+var_280]
0x18036833a  mov     [rbx+10h], r15
0x18036833e  lea     r9, [rbp+1A0h+var_48]
0x180368345  mov     rcx, [rsi]
0x180368348  lea     rdx, aFiletypeassoci_2; "FileTypeAssociation\\Index\\Extension"
0x18036834f  xor     r8d, r8d
0x180368352  mov     qword ptr [rbp+1A0h+var_50], rax
0x180368359  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x18036835e  mov     [rbp+1A0h+var_48], r15
0x180368365  mov     [rbp+1A0h+var_40], 1
0x18036836c  call    cs:__imp_SRCacheContext_Open
0x180368372  lea     rcx, [rbp+1A0h+var_50]
0x180368379  mov     edi, eax
0x18036837b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180368380  test    edi, edi
0x180368382  jns     short loc_1803683D6
0x180368384  mov     rcx, [rbp+1A8h]; this
0x18036838b  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180368392  mov     r9d, edi; char *
0x180368395  mov     edx, 18Ch; void *
0x18036839a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18036839f  mov     rcx, [rbp+1A8h]; this
0x1803683a6  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1803683ad  mov     r9d, edi; char *
0x1803683b0  mov     edx, 248h; void *
0x1803683b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803683ba  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1803683bf  mov     qword ptr [rsp+2A0h+var_280], r15
0x1803683c4  test    rcx, rcx
0x1803683c7  jz      short loc_1803683CF
0x1803683c9  call    cs:__imp_SRCacheContext_Close
0x1803683cf  mov     eax, edi
0x1803683d1  jmp     loc_1803685D2
0x1803683d6  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1803683db  setnz   al
0x1803683de  test    al, al
0x1803683e0  jnz     short loc_180368420
0x1803683e2  mov     rcx, [rbp+1A8h]; this
0x1803683e9  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1803683f0  mov     ebx, 80670012h
0x1803683f5  mov     edx, 249h; void *
0x1803683fa  mov     r9d, ebx; char *
0x1803683fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180368402  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180368407  mov     qword ptr [rsp+2A0h+var_280], r15
0x18036840c  test    rcx, rcx
0x18036840f  jz      loc_180368319
0x180368415  call    cs:__imp_SRCacheContext_Close
0x18036841b  jmp     loc_180368319
0x180368420  xor     edx, edx; Val
0x180368422  mov     [rsp+2A0h+var_270], r15
0x180368427  mov     r8d, 200h; Size
0x18036842d  lea     rcx, [rsp+2A0h+var_268]; void *
0x180368432  call    memset_0
0x180368437  mov     r9d, 10h
0x18036843d  mov     [rbp+1A0h+var_68], r15
0x180368444  lea     rax, [rsp+2A0h+var_268]
0x180368449  mov     [rbp+1A0h+var_60], 100h
0x180368454  lea     rdx, [rbp+1A0h+var_50]
0x18036845b  mov     [rbp+1A0h+var_58], rax
0x180368462  mov     rcx, r14
0x180368465  lea     r8d, [r9+1]
0x180368469  call    cs:__imp__o__ui64tow_s
0x18036846f  test    eax, eax
0x180368471  jz      short loc_180368495
0x180368473  mov     rcx, [rbp+1A8h]; this
0x18036847a  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180368481  mov     edi, 8000FFFFh
0x180368486  mov     edx, 166h; void *
0x18036848b  mov     r9d, edi; char *
0x18036848e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180368493  jmp     short loc_1803684AC
0x180368495  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x18036849c  lea     rcx, [rsp+2A0h+var_270]; this
0x1803684a1  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1803684a6  mov     edi, eax
0x1803684a8  test    eax, eax
0x1803684aa  jns     short loc_1803684E5
0x1803684ac  mov     edx, 24Ch; void *
0x1803684b1  mov     rcx, [rbp+1A8h]; this
0x1803684b8  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1803684bf  mov     r9d, edi; char *
0x1803684c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803684c7  mov     rcx, [rsp+2A0h+var_270]
0x1803684cc  mov     [rsp+2A0h+var_270], r15
0x1803684d1  test    rcx, rcx
0x1803684d4  jz      loc_1803683BA
0x1803684da  call    cs:__imp_SRCache_Free
0x1803684e0  jmp     loc_1803683BA
0x1803684e5  mov     rdx, [rbp+1A0h+var_58]
0x1803684ec  lea     r9, [rbp+1A0h+var_48]
0x1803684f3  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1803684f8  xor     r8d, r8d
0x1803684fb  mov     qword ptr [rbp+1A0h+var_50], rbx
0x180368502  mov     [rbp+1A0h+var_48], r15
0x180368509  mov     [rbp+1A0h+var_40], 1
0x180368510  call    cs:__imp_SRCacheContext_OpenSubContext
0x180368516  lea     rcx, [rbp+1A0h+var_50]
0x18036851d  mov     edi, eax
0x18036851f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180368524  test    edi, edi
0x180368526  jns     short loc_18036854D
0x180368528  mov     rcx, [rbp+1A8h]; this
0x18036852f  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180368536  mov     r9d, edi; char *
0x180368539  mov     edx, 1B0h; void *
0x18036853e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180368543  mov     edx, 24Fh
0x180368548  jmp     loc_1803684B1
0x18036854d  cmp     [rbx], r15
0x180368550  jz      short loc_180368556
0x180368552  mov     [rbx+10h], rsi
0x180368556  lea     rdx, aFiletypeassoci_2; "FileTypeAssociation\\Index\\Extension"
0x18036855d  lea     rcx, [rsp+2A0h+var_280]; this
0x180368562  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180368567  mov     ebx, eax
0x180368569  test    eax, eax
0x18036856b  jns     short loc_1803685A6
0x18036856d  mov     rcx, [rbp+1A8h]; this
0x180368574  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18036857b  mov     r9d, eax; char *
0x18036857e  mov     edx, 255h; void *
0x180368583  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180368588  mov     rcx, [rsp+2A0h+var_270]
0x18036858d  mov     [rsp+2A0h+var_270], r15
0x180368592  test    rcx, rcx
0x180368595  jz      loc_180368402
0x18036859b  call    cs:__imp_SRCache_Free
0x1803685a1  jmp     loc_180368402
0x1803685a6  mov     rcx, [rsp+2A0h+var_270]
0x1803685ab  mov     [rsp+2A0h+var_270], r15
0x1803685b0  test    rcx, rcx
0x1803685b3  jz      short loc_1803685BB
0x1803685b5  call    cs:__imp_SRCache_Free
0x1803685bb  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1803685c0  mov     qword ptr [rsp+2A0h+var_280], r15
0x1803685c5  test    rcx, rcx
0x1803685c8  jz      short loc_1803685D0
0x1803685ca  call    cs:__imp_SRCacheContext_Close
0x1803685d0  xor     eax, eax
0x1803685d2  mov     rcx, [rbp+1A0h+var_28]
0x1803685d9  xor     rcx, rsp; StackCookie
0x1803685dc  call    __security_check_cookie
0x1803685e1  mov     rbx, [rsp+2A0h+arg_18]
0x1803685e9  add     rsp, 280h
0x1803685f0  pop     r15
0x1803685f2  pop     r14
0x1803685f4  pop     rdi
0x1803685f5  pop     rsi
0x1803685f6  pop     rbp
0x1803685f7  retn
```
