# StateRepository::Cache::Entity::PackageUserStatus_NoThrow::GetByUserAndPackageFullName(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)

- ea: `0x180015190`
- end: `0x18001552d`
- name: `?GetByUserAndPackageFullName@PackageUserStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z`
- size: `925`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180015534`

## callees

- `0x180002980`
- `0x1800035c4`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x180009d34`
- `0x180009f64`
- `0x180015190`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015288`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001547c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800154dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015506`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015288`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001547c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800154dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015506`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015364`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800154f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015364`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800154f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180015227`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180015227`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001541b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001541b`

## string_xrefs

- `0x180015304`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x180015391`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x180015246`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18001543a`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x1800151d4`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUserStatus.hpp`
- `0x180015266`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUserStatus.hpp`
- `0x180015342`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUserStatus.hpp`
- `0x18001545a`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUserStatus.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUserStatus_NoThrow::GetByUserAndPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 *a4)
{
  int v7; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  bool v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+238h] [rbp+138h]
  __int64 v26; // [rsp+240h] [rbp+140h]
  _BYTE *v27; // [rsp+248h] [rbp+148h]
  unsigned __int16 v28[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v29; // [rsp+258h] [rbp+158h] BYREF
  char v30; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUserStatus.hpp",
      (const char *)0x80070057LL,
      v21[0]);
    return (unsigned int)v7;
  }
  v9 = *(_QWORD *)a1;
  *(_QWORD *)v28 = v21;
  *(_QWORD *)v21 = 0;
  v29 = 0;
  v30 = 1;
  v7 = SRCacheContext_Open(v9, L"PackageUserStatus\\Index\\UserAndPackageFullName", 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v28);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v7,
      v21[0]);
    v10 = 224;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUserStatus.hpp",
      (const char *)(unsigned int)v7,
      v21[0]);
LABEL_7:
    v11 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v7;
  }
  if ( !*(_QWORD *)v21 )
  {
    v7 = -2140733422;
    v10 = 225;
    goto LABEL_6;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v26 = 256;
  v27 = v24;
  if ( (unsigned int)o__ui64tow_s_0(a2, v28, 17) )
  {
    v7 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v21[0]);
LABEL_14:
    v13 = 228;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUserStatus.hpp",
      (const char *)(unsigned int)v7,
      v21[0]);
LABEL_16:
    v14 = v23;
    v23 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_7;
  }
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, v28);
  if ( v7 < 0 )
    goto LABEL_14;
  v15 = StateRepository::Cache::Key_NoThrow::EnsureCapacity((StateRepository::Cache::Key_NoThrow *)&v23, v25 + 2, v12);
  v7 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Key.hpp",
      (const char *)(unsigned int)v15,
      v21[0]);
    v13 = 229;
    goto LABEL_15;
  }
  *(_DWORD *)&v27[2 * v25++] = 94;
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
  if ( v7 < 0 )
  {
    v13 = 230;
    goto LABEL_15;
  }
  *(_QWORD *)v28 = &v22;
  v22 = 0;
  v29 = 0;
  v30 = 1;
  v7 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v27, 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v28);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v7,
      v21[0]);
    v16 = 234;
    goto LABEL_24;
  }
  if ( v22 )
  {
    v7 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)&v22, 0, a4);
    if ( v7 < 0 )
    {
      v16 = 237;
      goto LABEL_24;
    }
  }
  v7 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v21,
         L"PackageUserStatus\\Index\\UserAndPackageFullName");
  if ( v7 < 0 )
  {
    v16 = 240;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUserStatus.hpp",
      (const char *)(unsigned int)v7,
      v21[0]);
    v17 = v22;
    v22 = 0;
    if ( v17 )
      SRCacheContext_Close(v17);
    goto LABEL_16;
  }
  v18 = v22;
  v22 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  v19 = v23;
  v23 = 0;
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
0x180015190  push    rbp
0x180015192  push    rbx
0x180015193  push    rsi
0x180015194  push    rdi
0x180015195  push    r14
0x180015197  push    r15
0x180015199  lea     rbp, [rsp-188h]
0x1800151a1  sub     rsp, 288h
0x1800151a8  mov     rax, cs:__security_cookie
0x1800151af  xor     rax, rsp
0x1800151b2  mov     [rbp+1B0h+var_38], rax
0x1800151b9  xor     r15d, r15d
0x1800151bc  mov     rsi, r9
0x1800151bf  mov     [r9], r15
0x1800151c2  mov     r14, r8
0x1800151c5  mov     rdi, rdx
0x1800151c8  test    rdx, rdx
0x1800151cb  jnz     short loc_1800151F4
0x1800151cd  mov     rcx, [rbp+1B8h]; this
0x1800151d4  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\StateRepositor"...
0x1800151db  mov     ebx, 80070057h
0x1800151e0  mov     edx, 0DCh; void *
0x1800151e5  mov     r9d, ebx; char *
0x1800151e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800151ed  mov     eax, ebx
0x1800151ef  jmp     loc_18001550E
0x1800151f4  mov     rcx, [rcx]
0x1800151f7  lea     rax, [rsp+2B0h+var_290]
0x1800151fc  lea     r9, [rbp+1B0h+var_58]
0x180015203  mov     qword ptr [rbp+1B0h+var_60], rax
0x18001520a  xor     r8d, r8d
0x18001520d  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x180015212  lea     rdx, aPackageusersta_0; "PackageUserStatus\\Index\\UserAndPackag"...
0x180015219  mov     [rbp+1B0h+var_58], r15
0x180015220  mov     [rbp+1B0h+var_50], 1
0x180015227  call    cs:__imp_SRCacheContext_Open
0x18001522d  lea     rcx, [rbp+1B0h+var_60]
0x180015234  mov     ebx, eax
0x180015236  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001523b  test    ebx, ebx
0x18001523d  jns     short loc_180015293
0x18001523f  mov     rcx, [rbp+1B8h]; this
0x180015246  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18001524d  mov     r9d, ebx; char *
0x180015250  mov     edx, 18Ch; void *
0x180015255  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001525a  mov     edx, 0E0h; void *
0x18001525f  mov     rcx, [rbp+1B8h]; this
0x180015266  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\StateRepositor"...
0x18001526d  mov     r9d, ebx; char *
0x180015270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015275  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001527a  mov     qword ptr [rsp+2B0h+var_290], r15
0x18001527f  test    rcx, rcx
0x180015282  jz      loc_1800151ED
0x180015288  call    cs:__imp_SRCacheContext_Close
0x18001528e  jmp     loc_1800151ED
0x180015293  cmp     qword ptr [rsp+2B0h+var_290], r15
0x180015298  setnz   al
0x18001529b  test    al, al
0x18001529d  jnz     short loc_1800152AB
0x18001529f  mov     ebx, 80670012h
0x1800152a4  mov     edx, 0E1h
0x1800152a9  jmp     short loc_18001525F
0x1800152ab  xor     edx, edx; Val
0x1800152ad  mov     [rsp+2B0h+var_280], r15
0x1800152b2  mov     r8d, 200h; Size
0x1800152b8  lea     rcx, [rsp+2B0h+var_278]; void *
0x1800152bd  call    memset_0
0x1800152c2  mov     r9d, 10h
0x1800152c8  mov     [rbp+1B0h+var_78], r15
0x1800152cf  lea     rax, [rsp+2B0h+var_278]
0x1800152d4  mov     [rbp+1B0h+var_70], 100h
0x1800152df  lea     rdx, [rbp+1B0h+var_60]
0x1800152e6  mov     [rbp+1B0h+var_68], rax
0x1800152ed  mov     rcx, rdi
0x1800152f0  lea     r8d, [r9+1]
0x1800152f4  call    _o__ui64tow_s_0
0x1800152f9  test    eax, eax
0x1800152fb  jz      short loc_18001531F
0x1800152fd  mov     rcx, [rbp+1B8h]; this
0x180015304  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x18001530b  mov     ebx, 8000FFFFh
0x180015310  mov     edx, 166h; void *
0x180015315  mov     r9d, ebx; char *
0x180015318  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001531d  jmp     short loc_180015336
0x18001531f  lea     rdx, [rbp+1B0h+var_60]; unsigned __int16 *
0x180015326  lea     rcx, [rsp+2B0h+var_280]; this
0x18001532b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180015330  mov     ebx, eax
0x180015332  test    eax, eax
0x180015334  jns     short loc_18001536F
0x180015336  mov     edx, 0E4h; void *
0x18001533b  mov     rcx, [rbp+1B8h]; this
0x180015342  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\StateRepositor"...
0x180015349  mov     r9d, ebx; char *
0x18001534c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015351  mov     rcx, [rsp+2B0h+var_280]
0x180015356  mov     [rsp+2B0h+var_280], r15
0x18001535b  test    rcx, rcx
0x18001535e  jz      loc_180015275
0x180015364  call    cs:__imp_SRCache_Free
0x18001536a  jmp     loc_180015275
0x18001536f  mov     rdx, [rbp+1B0h+var_78]
0x180015376  lea     rcx, [rsp+2B0h+var_280]; this
0x18001537b  add     rdx, 2; unsigned __int64
0x18001537f  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x180015384  mov     ebx, eax
0x180015386  test    eax, eax
0x180015388  jns     short loc_1800153AC
0x18001538a  mov     rcx, [rbp+1B8h]; this
0x180015391  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x180015398  mov     r9d, eax; char *
0x18001539b  mov     edx, 16Dh; void *
0x1800153a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800153a5  mov     edx, 0E5h
0x1800153aa  jmp     short loc_18001533B
0x1800153ac  mov     r8, [rbp+1B0h+var_78]
0x1800153b3  mov     rdx, r14; unsigned __int16 *
0x1800153b6  mov     rcx, [rbp+1B0h+var_68]
0x1800153bd  mov     dword ptr [rcx+r8*2], 5Eh ; '^'
0x1800153c5  lea     rcx, [rsp+2B0h+var_280]; this
0x1800153ca  inc     [rbp+1B0h+var_78]
0x1800153d1  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800153d6  mov     ebx, eax
0x1800153d8  test    eax, eax
0x1800153da  jns     short loc_1800153E6
0x1800153dc  mov     edx, 0E6h
0x1800153e1  jmp     loc_18001533B
0x1800153e6  mov     rdx, [rbp+1B0h+var_68]
0x1800153ed  lea     rax, [rsp+2B0h+var_288]
0x1800153f2  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800153f7  lea     r9, [rbp+1B0h+var_58]
0x1800153fe  xor     r8d, r8d
0x180015401  mov     qword ptr [rbp+1B0h+var_60], rax
0x180015408  mov     [rsp+2B0h+var_288], r15
0x18001540d  mov     [rbp+1B0h+var_58], r15
0x180015414  mov     [rbp+1B0h+var_50], 1
0x18001541b  call    cs:__imp_SRCacheContext_OpenSubContext
0x180015421  lea     rcx, [rbp+1B0h+var_60]
0x180015428  mov     ebx, eax
0x18001542a  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001542f  test    ebx, ebx
0x180015431  jns     short loc_180015487
0x180015433  mov     rcx, [rbp+1B8h]; this
0x18001543a  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180015441  mov     r9d, ebx; char *
0x180015444  mov     edx, 1B0h; void *
0x180015449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001544e  mov     edx, 0EAh; void *
0x180015453  mov     rcx, [rbp+1B8h]; this
0x18001545a  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\StateRepositor"...
0x180015461  mov     r9d, ebx; char *
0x180015464  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015469  mov     rcx, [rsp+2B0h+var_288]
0x18001546e  mov     [rsp+2B0h+var_288], r15
0x180015473  test    rcx, rcx
0x180015476  jz      loc_180015351
0x18001547c  call    cs:__imp_SRCacheContext_Close
0x180015482  jmp     loc_180015351
0x180015487  cmp     [rsp+2B0h+var_288], r15
0x18001548c  setnz   al
0x18001548f  test    al, al
0x180015491  jz      short loc_1800154AF
0x180015493  mov     r8, rsi; __int64 *
0x180015496  lea     rcx, [rsp+2B0h+var_288]; this
0x18001549b  xor     edx, edx; int
0x18001549d  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x1800154a2  mov     ebx, eax
0x1800154a4  test    eax, eax
0x1800154a6  jns     short loc_1800154AF
0x1800154a8  mov     edx, 0EDh
0x1800154ad  jmp     short loc_180015453
0x1800154af  lea     rdx, aPackageusersta_0; "PackageUserStatus\\Index\\UserAndPackag"...
0x1800154b6  lea     rcx, [rsp+2B0h+var_290]; this
0x1800154bb  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800154c0  mov     ebx, eax
0x1800154c2  test    eax, eax
0x1800154c4  jns     short loc_1800154CD
0x1800154c6  mov     edx, 0F0h
0x1800154cb  jmp     short loc_180015453
0x1800154cd  mov     rcx, [rsp+2B0h+var_288]
0x1800154d2  mov     [rsp+2B0h+var_288], r15
0x1800154d7  test    rcx, rcx
0x1800154da  jz      short loc_1800154E2
0x1800154dc  call    cs:__imp_SRCacheContext_Close
0x1800154e2  mov     rcx, [rsp+2B0h+var_280]
0x1800154e7  mov     [rsp+2B0h+var_280], r15
0x1800154ec  test    rcx, rcx
0x1800154ef  jz      short loc_1800154F7
0x1800154f1  call    cs:__imp_SRCache_Free
0x1800154f7  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800154fc  mov     qword ptr [rsp+2B0h+var_290], r15
0x180015501  test    rcx, rcx
0x180015504  jz      short loc_18001550C
0x180015506  call    cs:__imp_SRCacheContext_Close
0x18001550c  xor     eax, eax
0x18001550e  mov     rcx, [rbp+1B0h+var_38]
0x180015515  xor     rcx, rsp; StackCookie
0x180015518  call    __security_check_cookie
0x18001551d  add     rsp, 288h
0x180015524  pop     r15
0x180015526  pop     r14
0x180015528  pop     rdi
0x180015529  pop     rsi
0x18001552a  pop     rbx
0x18001552b  pop     rbp
0x18001552c  retn
```
