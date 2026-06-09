# StateRepository::Cache::Entity::PackageUser_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)

- ea: `0x180013264`
- end: `0x180013650`
- name: `?GetByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z`
- size: `1004`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180013658`

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
- `0x180013264`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013368`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001359f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800135ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013629`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013368`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001359f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800135ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013629`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180013444`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180013614`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180013444`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180013614`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180013307`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180013307`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001353e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001353e`

## string_xrefs

- `0x1800133e4`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x180013471`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x1800134cd`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x180013326`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18001355d`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x1800132ad`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUser.hpp`
- `0x180013346`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUser.hpp`
- `0x180013422`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUser.hpp`
- `0x18001357d`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUser_NoThrow::GetByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4)
{
  __int64 v7; // rdx
  int v8; // ebx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  bool v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v25[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+238h] [rbp+138h]
  __int64 v27; // [rsp+240h] [rbp+140h]
  _BYTE *v28; // [rsp+248h] [rbp+148h]
  unsigned __int16 v29[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v30; // [rsp+258h] [rbp+158h] BYREF
  char v31; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( !a2 )
  {
    v7 = 222;
LABEL_3:
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUser.hpp",
      (const char *)0x80070057LL,
      v22[0]);
    return (unsigned int)v8;
  }
  if ( !a3 )
  {
    v7 = 223;
    goto LABEL_3;
  }
  v10 = *(_QWORD *)a1;
  *(_QWORD *)v29 = v22;
  *(_QWORD *)v22 = 0;
  v30 = 0;
  v31 = 1;
  v8 = SRCacheContext_Open(v10, L"PackageUser\\Index\\UserAndPackage", 0, &v30);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v29);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v22[0]);
    v11 = 227;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v22[0]);
LABEL_10:
    v12 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v22 )
  {
    v8 = -2140733422;
    v11 = 228;
    goto LABEL_9;
  }
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v26 = 0;
  v27 = 256;
  v28 = v25;
  if ( (unsigned int)o__ui64tow_s_0(a2, v29, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v22[0]);
LABEL_17:
    v14 = 231;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v22[0]);
LABEL_19:
    v15 = v24;
    v24 = 0;
    if ( v15 )
      SRCache_Free();
    goto LABEL_10;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, v29);
  if ( v8 < 0 )
    goto LABEL_17;
  v16 = StateRepository::Cache::Key_NoThrow::EnsureCapacity((StateRepository::Cache::Key_NoThrow *)&v24, v26 + 2, v13);
  v8 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Key.hpp",
      (const char *)(unsigned int)v16,
      v22[0]);
    v14 = 232;
    goto LABEL_18;
  }
  *(_DWORD *)&v28[2 * v26++] = 94;
  if ( (unsigned int)o__ui64tow_s_0(a3, v29, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v22[0]);
LABEL_26:
    v14 = 233;
    goto LABEL_18;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, v29);
  if ( v8 < 0 )
    goto LABEL_26;
  *(_QWORD *)v29 = &v23;
  v23 = 0;
  v30 = 0;
  v31 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v22, v28, 0, &v30);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v29);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v22[0]);
    v17 = 237;
    goto LABEL_29;
  }
  if ( v23 )
  {
    v8 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)&v23, 0, a4);
    if ( v8 < 0 )
    {
      v17 = 240;
      goto LABEL_29;
    }
  }
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v22,
         L"PackageUser\\Index\\UserAndPackage");
  if ( v8 < 0 )
  {
    v17 = 243;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v22[0]);
    v18 = v23;
    v23 = 0;
    if ( v18 )
      SRCacheContext_Close(v18);
    goto LABEL_19;
  }
  v19 = v23;
  v23 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  v20 = v24;
  v24 = 0;
  if ( v20 )
    SRCache_Free();
  v21 = *(_QWORD *)v22;
  *(_QWORD *)v22 = 0;
  if ( v21 )
    SRCacheContext_Close(v21);
  return 0;
}

```

## disassembly

```asm
0x180013264  push    rbp
0x180013266  push    rbx
0x180013267  push    rsi
0x180013268  push    rdi
0x180013269  push    r14
0x18001326b  push    r15
0x18001326d  lea     rbp, [rsp-188h]
0x180013275  sub     rsp, 288h
0x18001327c  mov     rax, cs:__security_cookie
0x180013283  xor     rax, rsp
0x180013286  mov     [rbp+1B0h+var_38], rax
0x18001328d  xor     r15d, r15d
0x180013290  mov     r14, r9
0x180013293  mov     [r9], r15
0x180013296  mov     rdi, r8
0x180013299  mov     rsi, rdx
0x18001329c  test    rdx, rdx
0x18001329f  jnz     short loc_1800132C8
0x1800132a1  mov     edx, 0DEh; void *
0x1800132a6  mov     rcx, [rbp+1B8h]; this
0x1800132ad  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\StateRepositor"...
0x1800132b4  mov     ebx, 80070057h
0x1800132b9  mov     r9d, ebx; char *
0x1800132bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800132c1  mov     eax, ebx
0x1800132c3  jmp     loc_180013631
0x1800132c8  test    rdi, rdi
0x1800132cb  jnz     short loc_1800132D4
0x1800132cd  mov     edx, 0DFh
0x1800132d2  jmp     short loc_1800132A6
0x1800132d4  mov     rcx, [rcx]
0x1800132d7  lea     rax, [rsp+2B0h+var_290]
0x1800132dc  lea     r9, [rbp+1B0h+var_58]
0x1800132e3  mov     qword ptr [rbp+1B0h+var_60], rax
0x1800132ea  xor     r8d, r8d
0x1800132ed  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x1800132f2  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x1800132f9  mov     [rbp+1B0h+var_58], r15
0x180013300  mov     [rbp+1B0h+var_50], 1
0x180013307  call    cs:__imp_SRCacheContext_Open
0x18001330d  lea     rcx, [rbp+1B0h+var_60]
0x180013314  mov     ebx, eax
0x180013316  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001331b  test    ebx, ebx
0x18001331d  jns     short loc_180013373
0x18001331f  mov     rcx, [rbp+1B8h]; this
0x180013326  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18001332d  mov     r9d, ebx; char *
0x180013330  mov     edx, 18Ch; void *
0x180013335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001333a  mov     edx, 0E3h; void *
0x18001333f  mov     rcx, [rbp+1B8h]; this
0x180013346  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\StateRepositor"...
0x18001334d  mov     r9d, ebx; char *
0x180013350  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013355  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001335a  mov     qword ptr [rsp+2B0h+var_290], r15
0x18001335f  test    rcx, rcx
0x180013362  jz      loc_1800132C1
0x180013368  call    cs:__imp_SRCacheContext_Close
0x18001336e  jmp     loc_1800132C1
0x180013373  cmp     qword ptr [rsp+2B0h+var_290], r15
0x180013378  setnz   al
0x18001337b  test    al, al
0x18001337d  jnz     short loc_18001338B
0x18001337f  mov     ebx, 80670012h
0x180013384  mov     edx, 0E4h
0x180013389  jmp     short loc_18001333F
0x18001338b  xor     edx, edx; Val
0x18001338d  mov     [rsp+2B0h+var_280], r15
0x180013392  mov     r8d, 200h; Size
0x180013398  lea     rcx, [rsp+2B0h+var_278]; void *
0x18001339d  call    memset_0
0x1800133a2  mov     r9d, 10h
0x1800133a8  mov     [rbp+1B0h+var_78], r15
0x1800133af  lea     rax, [rsp+2B0h+var_278]
0x1800133b4  mov     [rbp+1B0h+var_70], 100h
0x1800133bf  lea     rdx, [rbp+1B0h+var_60]
0x1800133c6  mov     [rbp+1B0h+var_68], rax
0x1800133cd  mov     rcx, rsi
0x1800133d0  lea     r8d, [r9+1]
0x1800133d4  call    _o__ui64tow_s_0
0x1800133d9  test    eax, eax
0x1800133db  jz      short loc_1800133FF
0x1800133dd  mov     rcx, [rbp+1B8h]; this
0x1800133e4  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x1800133eb  mov     ebx, 8000FFFFh
0x1800133f0  mov     edx, 166h; void *
0x1800133f5  mov     r9d, ebx; char *
0x1800133f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800133fd  jmp     short loc_180013416
0x1800133ff  lea     rdx, [rbp+1B0h+var_60]; unsigned __int16 *
0x180013406  lea     rcx, [rsp+2B0h+var_280]; this
0x18001340b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180013410  mov     ebx, eax
0x180013412  test    eax, eax
0x180013414  jns     short loc_18001344F
0x180013416  mov     edx, 0E7h; void *
0x18001341b  mov     rcx, [rbp+1B8h]; this
0x180013422  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\StateRepositor"...
0x180013429  mov     r9d, ebx; char *
0x18001342c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013431  mov     rcx, [rsp+2B0h+var_280]
0x180013436  mov     [rsp+2B0h+var_280], r15
0x18001343b  test    rcx, rcx
0x18001343e  jz      loc_180013355
0x180013444  call    cs:__imp_SRCache_Free
0x18001344a  jmp     loc_180013355
0x18001344f  mov     rdx, [rbp+1B0h+var_78]
0x180013456  lea     rcx, [rsp+2B0h+var_280]; this
0x18001345b  add     rdx, 2; unsigned __int64
0x18001345f  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x180013464  mov     ebx, eax
0x180013466  test    eax, eax
0x180013468  jns     short loc_18001348C
0x18001346a  mov     rcx, [rbp+1B8h]; this
0x180013471  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x180013478  mov     r9d, eax; char *
0x18001347b  mov     edx, 16Dh; void *
0x180013480  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013485  mov     edx, 0E8h
0x18001348a  jmp     short loc_18001341B
0x18001348c  mov     r8, [rbp+1B0h+var_78]
0x180013493  mov     r9d, 10h
0x180013499  mov     rdx, [rbp+1B0h+var_68]
0x1800134a0  mov     rcx, rdi
0x1800134a3  mov     dword ptr [rdx+r8*2], 5Eh ; '^'
0x1800134ab  lea     r8d, [r9+1]
0x1800134af  inc     [rbp+1B0h+var_78]
0x1800134b6  lea     rdx, [rbp+1B0h+var_60]
0x1800134bd  call    _o__ui64tow_s_0
0x1800134c2  test    eax, eax
0x1800134c4  jz      short loc_1800134E8
0x1800134c6  mov     rcx, [rbp+1B8h]; this
0x1800134cd  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x1800134d4  mov     ebx, 8000FFFFh
0x1800134d9  mov     edx, 166h; void *
0x1800134de  mov     r9d, ebx; char *
0x1800134e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800134e6  jmp     short loc_1800134FF
0x1800134e8  lea     rdx, [rbp+1B0h+var_60]; unsigned __int16 *
0x1800134ef  lea     rcx, [rsp+2B0h+var_280]; this
0x1800134f4  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800134f9  mov     ebx, eax
0x1800134fb  test    eax, eax
0x1800134fd  jns     short loc_180013509
0x1800134ff  mov     edx, 0E9h
0x180013504  jmp     loc_18001341B
0x180013509  mov     rdx, [rbp+1B0h+var_68]
0x180013510  lea     rax, [rsp+2B0h+var_288]
0x180013515  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001351a  lea     r9, [rbp+1B0h+var_58]
0x180013521  xor     r8d, r8d
0x180013524  mov     qword ptr [rbp+1B0h+var_60], rax
0x18001352b  mov     [rsp+2B0h+var_288], r15
0x180013530  mov     [rbp+1B0h+var_58], r15
0x180013537  mov     [rbp+1B0h+var_50], 1
0x18001353e  call    cs:__imp_SRCacheContext_OpenSubContext
0x180013544  lea     rcx, [rbp+1B0h+var_60]
0x18001354b  mov     ebx, eax
0x18001354d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180013552  test    ebx, ebx
0x180013554  jns     short loc_1800135AA
0x180013556  mov     rcx, [rbp+1B8h]; this
0x18001355d  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180013564  mov     r9d, ebx; char *
0x180013567  mov     edx, 1B0h; void *
0x18001356c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013571  mov     edx, 0EDh; void *
0x180013576  mov     rcx, [rbp+1B8h]; this
0x18001357d  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\StateRepositor"...
0x180013584  mov     r9d, ebx; char *
0x180013587  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001358c  mov     rcx, [rsp+2B0h+var_288]
0x180013591  mov     [rsp+2B0h+var_288], r15
0x180013596  test    rcx, rcx
0x180013599  jz      loc_180013431
0x18001359f  call    cs:__imp_SRCacheContext_Close
0x1800135a5  jmp     loc_180013431
0x1800135aa  cmp     [rsp+2B0h+var_288], r15
0x1800135af  setnz   al
0x1800135b2  test    al, al
0x1800135b4  jz      short loc_1800135D2
0x1800135b6  mov     r8, r14; __int64 *
0x1800135b9  lea     rcx, [rsp+2B0h+var_288]; this
0x1800135be  xor     edx, edx; int
0x1800135c0  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x1800135c5  mov     ebx, eax
0x1800135c7  test    eax, eax
0x1800135c9  jns     short loc_1800135D2
0x1800135cb  mov     edx, 0F0h
0x1800135d0  jmp     short loc_180013576
0x1800135d2  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x1800135d9  lea     rcx, [rsp+2B0h+var_290]; this
0x1800135de  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800135e3  mov     ebx, eax
0x1800135e5  test    eax, eax
0x1800135e7  jns     short loc_1800135F0
0x1800135e9  mov     edx, 0F3h
0x1800135ee  jmp     short loc_180013576
0x1800135f0  mov     rcx, [rsp+2B0h+var_288]
0x1800135f5  mov     [rsp+2B0h+var_288], r15
0x1800135fa  test    rcx, rcx
0x1800135fd  jz      short loc_180013605
0x1800135ff  call    cs:__imp_SRCacheContext_Close
0x180013605  mov     rcx, [rsp+2B0h+var_280]
0x18001360a  mov     [rsp+2B0h+var_280], r15
0x18001360f  test    rcx, rcx
0x180013612  jz      short loc_18001361A
0x180013614  call    cs:__imp_SRCache_Free
0x18001361a  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001361f  mov     qword ptr [rsp+2B0h+var_290], r15
0x180013624  test    rcx, rcx
0x180013627  jz      short loc_18001362F
0x180013629  call    cs:__imp_SRCacheContext_Close
0x18001362f  xor     eax, eax
0x180013631  mov     rcx, [rbp+1B0h+var_38]
0x180013638  xor     rcx, rsp; StackCookie
0x18001363b  call    __security_check_cookie
0x180013640  add     rsp, 288h
0x180013647  pop     r15
0x180013649  pop     r14
0x18001364b  pop     rdi
0x18001364c  pop     rsi
0x18001364d  pop     rbx
0x18001364e  pop     rbp
0x18001364f  retn
```
