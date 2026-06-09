# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)

- ea: `0x18000a52c`
- end: `0x18000a90c`
- name: `?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z`
- size: `992`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a914`

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
- `0x18000a52c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a624`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a85b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a8bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a8e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a624`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a85b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a8bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a8e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a700`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a8d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a700`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a8d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000a5c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000a5c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000a7fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000a7fa`

## string_xrefs

- `0x18000a6a0`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x18000a72d`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x18000a789`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x18000a5e2`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18000a819`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18000a570`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18000a602`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18000a6de`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18000a839`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
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
  if ( !a3 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)0x80070057LL,
      v21[0]);
    return (unsigned int)v7;
  }
  v9 = *(_QWORD *)a1;
  *(_QWORD *)v28 = v21;
  *(_QWORD *)v21 = 0;
  v29 = 0;
  v30 = 1;
  v7 = SRCacheContext_Open(v9, L"PackageExternalLocation\\Index\\UserAndPackage", 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v28);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v7,
      v21[0]);
    v10 = 185;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExternalLocation.hpp",
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
    v10 = 186;
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
    v13 = 189;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExternalLocation.hpp",
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
    v13 = 190;
    goto LABEL_15;
  }
  *(_DWORD *)&v27[2 * v25++] = 94;
  if ( (unsigned int)o__ui64tow_s_0(a3, v28, 17) )
  {
    v7 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v21[0]);
LABEL_23:
    v13 = 191;
    goto LABEL_15;
  }
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, v28);
  if ( v7 < 0 )
    goto LABEL_23;
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
    v16 = 195;
    goto LABEL_26;
  }
  if ( v22 )
  {
    v7 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)&v22, 0, a4);
    if ( v7 < 0 )
    {
      v16 = 198;
      goto LABEL_26;
    }
  }
  v7 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v21,
         L"PackageExternalLocation\\Index\\UserAndPackage");
  if ( v7 < 0 )
  {
    v16 = 201;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExternalLocation.hpp",
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
0x18000a52c  push    rbp
0x18000a52e  push    rbx
0x18000a52f  push    rsi
0x18000a530  push    rdi
0x18000a531  push    r14
0x18000a533  push    r15
0x18000a535  lea     rbp, [rsp-188h]
0x18000a53d  sub     rsp, 288h
0x18000a544  mov     rax, cs:__security_cookie
0x18000a54b  xor     rax, rsp
0x18000a54e  mov     [rbp+1B0h+var_38], rax
0x18000a555  xor     r15d, r15d
0x18000a558  mov     rdi, r9
0x18000a55b  mov     [r9], r15
0x18000a55e  mov     rsi, r8
0x18000a561  mov     r14, rdx
0x18000a564  test    r8, r8
0x18000a567  jnz     short loc_18000A590
0x18000a569  mov     rcx, [rbp+1B8h]; this
0x18000a570  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a577  mov     ebx, 80070057h
0x18000a57c  mov     edx, 0B5h; void *
0x18000a581  mov     r9d, ebx; char *
0x18000a584  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a589  mov     eax, ebx
0x18000a58b  jmp     loc_18000A8ED
0x18000a590  mov     rcx, [rcx]
0x18000a593  lea     rax, [rsp+2B0h+var_290]
0x18000a598  lea     r9, [rbp+1B0h+var_58]
0x18000a59f  mov     qword ptr [rbp+1B0h+var_60], rax
0x18000a5a6  xor     r8d, r8d
0x18000a5a9  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x18000a5ae  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18000a5b5  mov     [rbp+1B0h+var_58], r15
0x18000a5bc  mov     [rbp+1B0h+var_50], 1
0x18000a5c3  call    cs:__imp_SRCacheContext_Open
0x18000a5c9  lea     rcx, [rbp+1B0h+var_60]
0x18000a5d0  mov     ebx, eax
0x18000a5d2  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18000a5d7  test    ebx, ebx
0x18000a5d9  jns     short loc_18000A62F
0x18000a5db  mov     rcx, [rbp+1B8h]; this
0x18000a5e2  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a5e9  mov     r9d, ebx; char *
0x18000a5ec  mov     edx, 18Ch; void *
0x18000a5f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5f6  mov     edx, 0B9h; void *
0x18000a5fb  mov     rcx, [rbp+1B8h]; this
0x18000a602  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a609  mov     r9d, ebx; char *
0x18000a60c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a611  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18000a616  mov     qword ptr [rsp+2B0h+var_290], r15
0x18000a61b  test    rcx, rcx
0x18000a61e  jz      loc_18000A589
0x18000a624  call    cs:__imp_SRCacheContext_Close
0x18000a62a  jmp     loc_18000A589
0x18000a62f  cmp     qword ptr [rsp+2B0h+var_290], r15
0x18000a634  setnz   al
0x18000a637  test    al, al
0x18000a639  jnz     short loc_18000A647
0x18000a63b  mov     ebx, 80670012h
0x18000a640  mov     edx, 0BAh
0x18000a645  jmp     short loc_18000A5FB
0x18000a647  xor     edx, edx; Val
0x18000a649  mov     [rsp+2B0h+var_280], r15
0x18000a64e  mov     r8d, 200h; Size
0x18000a654  lea     rcx, [rsp+2B0h+var_278]; void *
0x18000a659  call    memset_0
0x18000a65e  mov     r9d, 10h
0x18000a664  mov     [rbp+1B0h+var_78], r15
0x18000a66b  lea     rax, [rsp+2B0h+var_278]
0x18000a670  mov     [rbp+1B0h+var_70], 100h
0x18000a67b  lea     rdx, [rbp+1B0h+var_60]
0x18000a682  mov     [rbp+1B0h+var_68], rax
0x18000a689  mov     rcx, r14
0x18000a68c  lea     r8d, [r9+1]
0x18000a690  call    _o__ui64tow_s_0
0x18000a695  test    eax, eax
0x18000a697  jz      short loc_18000A6BB
0x18000a699  mov     rcx, [rbp+1B8h]; this
0x18000a6a0  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a6a7  mov     ebx, 8000FFFFh
0x18000a6ac  mov     edx, 166h; void *
0x18000a6b1  mov     r9d, ebx; char *
0x18000a6b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a6b9  jmp     short loc_18000A6D2
0x18000a6bb  lea     rdx, [rbp+1B0h+var_60]; unsigned __int16 *
0x18000a6c2  lea     rcx, [rsp+2B0h+var_280]; this
0x18000a6c7  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000a6cc  mov     ebx, eax
0x18000a6ce  test    eax, eax
0x18000a6d0  jns     short loc_18000A70B
0x18000a6d2  mov     edx, 0BDh; void *
0x18000a6d7  mov     rcx, [rbp+1B8h]; this
0x18000a6de  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a6e5  mov     r9d, ebx; char *
0x18000a6e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a6ed  mov     rcx, [rsp+2B0h+var_280]
0x18000a6f2  mov     [rsp+2B0h+var_280], r15
0x18000a6f7  test    rcx, rcx
0x18000a6fa  jz      loc_18000A611
0x18000a700  call    cs:__imp_SRCache_Free
0x18000a706  jmp     loc_18000A611
0x18000a70b  mov     rdx, [rbp+1B0h+var_78]
0x18000a712  lea     rcx, [rsp+2B0h+var_280]; this
0x18000a717  add     rdx, 2; unsigned __int64
0x18000a71b  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x18000a720  mov     ebx, eax
0x18000a722  test    eax, eax
0x18000a724  jns     short loc_18000A748
0x18000a726  mov     rcx, [rbp+1B8h]; this
0x18000a72d  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a734  mov     r9d, eax; char *
0x18000a737  mov     edx, 16Dh; void *
0x18000a73c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a741  mov     edx, 0BEh
0x18000a746  jmp     short loc_18000A6D7
0x18000a748  mov     r8, [rbp+1B0h+var_78]
0x18000a74f  mov     r9d, 10h
0x18000a755  mov     rdx, [rbp+1B0h+var_68]
0x18000a75c  mov     rcx, rsi
0x18000a75f  mov     dword ptr [rdx+r8*2], 5Eh ; '^'
0x18000a767  lea     r8d, [r9+1]
0x18000a76b  inc     [rbp+1B0h+var_78]
0x18000a772  lea     rdx, [rbp+1B0h+var_60]
0x18000a779  call    _o__ui64tow_s_0
0x18000a77e  test    eax, eax
0x18000a780  jz      short loc_18000A7A4
0x18000a782  mov     rcx, [rbp+1B8h]; this
0x18000a789  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a790  mov     ebx, 8000FFFFh
0x18000a795  mov     edx, 166h; void *
0x18000a79a  mov     r9d, ebx; char *
0x18000a79d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a7a2  jmp     short loc_18000A7BB
0x18000a7a4  lea     rdx, [rbp+1B0h+var_60]; unsigned __int16 *
0x18000a7ab  lea     rcx, [rsp+2B0h+var_280]; this
0x18000a7b0  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000a7b5  mov     ebx, eax
0x18000a7b7  test    eax, eax
0x18000a7b9  jns     short loc_18000A7C5
0x18000a7bb  mov     edx, 0BFh
0x18000a7c0  jmp     loc_18000A6D7
0x18000a7c5  mov     rdx, [rbp+1B0h+var_68]
0x18000a7cc  lea     rax, [rsp+2B0h+var_288]
0x18000a7d1  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18000a7d6  lea     r9, [rbp+1B0h+var_58]
0x18000a7dd  xor     r8d, r8d
0x18000a7e0  mov     qword ptr [rbp+1B0h+var_60], rax
0x18000a7e7  mov     [rsp+2B0h+var_288], r15
0x18000a7ec  mov     [rbp+1B0h+var_58], r15
0x18000a7f3  mov     [rbp+1B0h+var_50], 1
0x18000a7fa  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000a800  lea     rcx, [rbp+1B0h+var_60]
0x18000a807  mov     ebx, eax
0x18000a809  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18000a80e  test    ebx, ebx
0x18000a810  jns     short loc_18000A866
0x18000a812  mov     rcx, [rbp+1B8h]; this
0x18000a819  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a820  mov     r9d, ebx; char *
0x18000a823  mov     edx, 1B0h; void *
0x18000a828  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a82d  mov     edx, 0C3h; void *
0x18000a832  mov     rcx, [rbp+1B8h]; this
0x18000a839  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a840  mov     r9d, ebx; char *
0x18000a843  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a848  mov     rcx, [rsp+2B0h+var_288]
0x18000a84d  mov     [rsp+2B0h+var_288], r15
0x18000a852  test    rcx, rcx
0x18000a855  jz      loc_18000A6ED
0x18000a85b  call    cs:__imp_SRCacheContext_Close
0x18000a861  jmp     loc_18000A6ED
0x18000a866  cmp     [rsp+2B0h+var_288], r15
0x18000a86b  setnz   al
0x18000a86e  test    al, al
0x18000a870  jz      short loc_18000A88E
0x18000a872  mov     r8, rdi; __int64 *
0x18000a875  lea     rcx, [rsp+2B0h+var_288]; this
0x18000a87a  xor     edx, edx; int
0x18000a87c  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18000a881  mov     ebx, eax
0x18000a883  test    eax, eax
0x18000a885  jns     short loc_18000A88E
0x18000a887  mov     edx, 0C6h
0x18000a88c  jmp     short loc_18000A832
0x18000a88e  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18000a895  lea     rcx, [rsp+2B0h+var_290]; this
0x18000a89a  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18000a89f  mov     ebx, eax
0x18000a8a1  test    eax, eax
0x18000a8a3  jns     short loc_18000A8AC
0x18000a8a5  mov     edx, 0C9h
0x18000a8aa  jmp     short loc_18000A832
0x18000a8ac  mov     rcx, [rsp+2B0h+var_288]
0x18000a8b1  mov     [rsp+2B0h+var_288], r15
0x18000a8b6  test    rcx, rcx
0x18000a8b9  jz      short loc_18000A8C1
0x18000a8bb  call    cs:__imp_SRCacheContext_Close
0x18000a8c1  mov     rcx, [rsp+2B0h+var_280]
0x18000a8c6  mov     [rsp+2B0h+var_280], r15
0x18000a8cb  test    rcx, rcx
0x18000a8ce  jz      short loc_18000A8D6
0x18000a8d0  call    cs:__imp_SRCache_Free
0x18000a8d6  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18000a8db  mov     qword ptr [rsp+2B0h+var_290], r15
0x18000a8e0  test    rcx, rcx
0x18000a8e3  jz      short loc_18000A8EB
0x18000a8e5  call    cs:__imp_SRCacheContext_Close
0x18000a8eb  xor     eax, eax
0x18000a8ed  mov     rcx, [rbp+1B0h+var_38]
0x18000a8f4  xor     rcx, rsp; StackCookie
0x18000a8f7  call    __security_check_cookie
0x18000a8fc  add     rsp, 288h
0x18000a903  pop     r15
0x18000a905  pop     r14
0x18000a907  pop     rdi
0x18000a908  pop     rsi
0x18000a909  pop     rbx
0x18000a90a  pop     rbp
0x18000a90b  retn
```
