# Container::Manager::Core::Details::BaseImage::Initialize(_GUID const &,_CMS_CLIENT_ID,Csl::Path const &,Csl::Path const &,ulong,utl::optional<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,Container::Manager::Core::Details::BaseImageFlags,Container::Manager::Core::Details::BaseImageState,Csl::RegistryKey const &)

- ea: `0x1800ed4ec`
- end: `0x1800ed983`
- name: `?Initialize@BaseImage@Details@Core@Manager@Container@@QEAAJAEBU_GUID@@W4_CMS_CLIENT_ID@@AEBVPath@Csl@@2KV?$optional@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@W4BaseImageFlags@2345@W4BaseImageState@2345@AEBVRegistryKey@9@@Z`
- size: `1175`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, __int64, int, __int64, int, int, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x1800ec07c`
- `0x1800ee910`

## callees

- `0x180004fc4`
- `0x180006cac`
- `0x180008bf0`
- `0x18000da68`
- `0x18000da88`
- `0x180016774`
- `0x180032d70`
- `0x1800ecf4c`
- `0x1800ed4ec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ed51e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ed51e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ed5de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ed68d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ed765`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ed890`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ed945`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ed5de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ed68d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ed765`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ed890`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ed945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed87f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed8cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed87f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed8cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ed89e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ed8eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ed89e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ed8eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ed7f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ed8dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ed907`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ed7f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ed8dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ed907`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::BaseImage::Initialize(
        char *pv,
        __int128 *a2,
        int a3,
        __int64 *a4,
        _QWORD *a5,
        int a6,
        __int64 a7,
        int a8,
        int a9,
        __int64 a10)
{
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v15; // r9
  unsigned int LastError; // ebx
  __int64 v18; // r8
  __int64 v19; // rdx
  void *v20; // rcx
  bool v21; // zf
  __int64 v22; // rdx
  int WimOsVersion; // eax
  unsigned int v24; // edi
  int v25; // eax
  __int128 v26; // xmm0
  struct _TP_WORK **v27; // r12
  struct _TP_WORK *v28; // r13
  DWORD v29; // edi
  HKEY *v30; // r15
  HKEY v31; // r12
  HKEY v32; // r13
  DWORD v33; // edi
  HKEY v34; // rcx
  HKEY hKey; // [rsp+20h] [rbp-71h] BYREF
  char v36; // [rsp+28h] [rbp-69h] BYREF
  void *v37[2]; // [rsp+30h] [rbp-61h] BYREF
  _WORD v38[8]; // [rsp+40h] [rbp-51h] BYREF
  void *v39[2]; // [rsp+50h] [rbp-41h] BYREF
  _WORD v40[8]; // [rsp+60h] [rbp-31h] BYREF
  void *v41[2]; // [rsp+70h] [rbp-21h] BYREF
  _WORD v42[40]; // [rsp+80h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+47h]

  ThreadpoolWork = CreateThreadpoolWork(Container::Manager::Core::Details::BaseImage::MaterializeWork, pv, 0);
  if ( !ThreadpoolWork )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xDA,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
                  v15);
    if ( *(_BYTE *)(a7 + 32) )
    {
      if ( *(_QWORD *)a7 != a7 + 16 )
        operator delete(*(void **)a7, (const struct std::nothrow_t *)&std::nothrow);
    }
    return LastError;
  }
  v18 = a4[1] - *a4;
  v19 = *a4;
  v37[0] = v38;
  v37[1] = v38;
  v38[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v37,
                           v19,
                           v18 >> 1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
      (const char *)0x8007000ELL,
      (int)hKey);
    if ( v37[0] != v38 )
      operator delete(v37[0], (const struct std::nothrow_t *)&std::nothrow);
    CloseThreadpoolWork(ThreadpoolWork);
    if ( !*(_BYTE *)(a7 + 32) )
      return 2147942414LL;
    v20 = *(void **)a7;
    v21 = *(_QWORD *)a7 == a7 + 16;
LABEL_18:
    if ( !v21 )
      operator delete(v20, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  v40[0] = 0;
  v39[0] = v40;
  v39[1] = v40;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v39,
                           *a5,
                           (__int64)(a5[1] - *a5) >> 1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
      (const char *)0x8007000ELL,
      (int)hKey);
    if ( v39[0] != v40 )
      operator delete(v39[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v37[0] != v38 )
      operator delete(v37[0], (const struct std::nothrow_t *)&std::nothrow);
    CloseThreadpoolWork(ThreadpoolWork);
    if ( !*(_BYTE *)(a7 + 32) )
      return 2147942414LL;
    v20 = *(void **)a7;
    v21 = *(_QWORD *)a7 == a7 + 16;
    goto LABEL_18;
  }
  if ( !*(_BYTE *)(a7 + 32) )
  {
    v41[0] = v42;
    v41[1] = v42;
    v42[0] = 0;
    WimOsVersion = Container::Manager::Core::Details::BaseImage::GetWimOsVersion(v39, v41);
    v24 = WimOsVersion;
    if ( WimOsVersion < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
        (const char *)(unsigned int)WimOsVersion,
        (int)hKey);
      if ( v41[0] != v42 )
        operator delete(v41[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_25:
      if ( v39[0] != v40 )
        operator delete(v39[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v37[0] != v38 )
        operator delete(v37[0], (const struct std::nothrow_t *)&std::nothrow);
      CloseThreadpoolWork(ThreadpoolWork);
      if ( *(_BYTE *)(a7 + 32) && *(_QWORD *)a7 != a7 + 16 )
        operator delete(*(void **)a7, (const struct std::nothrow_t *)&std::nothrow);
      return v24;
    }
    utl::optional<Csl::Path>::operator=<Csl::Path,0>(a7, v41);
    if ( v41[0] != v42 )
      operator delete(v41[0], (const struct std::nothrow_t *)&std::nothrow);
  }
  hKey = 0;
  v25 = Csl::RegistryKey::Duplicate(a10, v22, &hKey);
  v24 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
      (const char *)(unsigned int)v25,
      (int)hKey);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_25;
  }
  v26 = *a2;
  *((_DWORD *)pv + 4) = a3;
  *(_OWORD *)pv = v26;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    pv + 24,
    v37);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    pv + 56,
    v39);
  *((_DWORD *)pv + 22) = a6;
  if ( !*(_BYTE *)(a7 + 32) )
    __int2c();
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    pv + 96,
    a7);
  v27 = (struct _TP_WORK **)(pv + 144);
  *((_DWORD *)pv + 35) = a8;
  *((_DWORD *)pv + 34) = a9;
  if ( pv + 144 != &v36 )
  {
    v28 = *v27;
    if ( *v27 )
    {
      v29 = GetLastError();
      CloseThreadpoolWork(v28);
      SetLastError(v29);
    }
    *v27 = ThreadpoolWork;
    ThreadpoolWork = 0;
  }
  v30 = (HKEY *)(pv + 168);
  if ( v30 == &hKey )
  {
    v34 = hKey;
  }
  else
  {
    v31 = *v30;
    v32 = hKey;
    if ( *v30 )
    {
      v33 = GetLastError();
      RegCloseKey(v31);
      SetLastError(v33);
    }
    *v30 = v32;
    v34 = 0;
  }
  if ( v34 )
    RegCloseKey(v34);
  if ( v39[0] != v40 )
    operator delete(v39[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v37[0] != v38 )
    operator delete(v37[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  if ( *(_BYTE *)(a7 + 32) && *(_QWORD *)a7 != a7 + 16 )
    operator delete(*(void **)a7, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x1800ed4ec  push    rbp
0x1800ed4ee  push    rbx
0x1800ed4ef  push    rsi
0x1800ed4f0  push    rdi
0x1800ed4f1  push    r12
0x1800ed4f3  push    r13
0x1800ed4f5  push    r14
0x1800ed4f7  push    r15
0x1800ed4f9  lea     rbp, [rsp-7]
0x1800ed4fe  sub     rsp, 98h
0x1800ed505  mov     r13, rdx
0x1800ed508  mov     r12d, r8d
0x1800ed50b  mov     rdx, rcx; pv
0x1800ed50e  mov     r15, rcx
0x1800ed511  lea     rcx, ?MaterializeWork@BaseImage@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ed518  xor     r8d, r8d; pcbe
0x1800ed51b  mov     rdi, r9
0x1800ed51e  call    cs:__imp_CreateThreadpoolWork
0x1800ed525  nop     dword ptr [rax+rax+00h]
0x1800ed52a  xor     r14d, r14d
0x1800ed52d  mov     rbx, rax
0x1800ed530  test    rax, rax
0x1800ed533  jnz     short loc_1800ED575
0x1800ed535  mov     rcx, [rbp+47h]; this
0x1800ed539  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ed540  mov     edx, 0DAh; void *
0x1800ed545  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ed54a  mov     rdx, [rbp+3Fh+arg_30]
0x1800ed54e  mov     ebx, eax
0x1800ed550  cmp     [rdx+20h], r14b
0x1800ed554  jz      short loc_1800ED56E
0x1800ed556  mov     rcx, [rdx]; void *
0x1800ed559  add     rdx, 10h
0x1800ed55d  cmp     rcx, rdx
0x1800ed560  jz      short loc_1800ED56E
0x1800ed562  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ed569  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed56e  mov     eax, ebx
0x1800ed570  jmp     loc_1800ED96E
0x1800ed575  mov     r8, [rdi+8]
0x1800ed579  lea     rax, [rbp+3Fh+var_90]
0x1800ed57d  sub     r8, [rdi]
0x1800ed580  lea     rcx, [rbp+3Fh+var_A0]
0x1800ed584  mov     rdx, [rdi]
0x1800ed587  mov     [rbp+3Fh+var_A0], rax
0x1800ed58b  lea     rax, [rbp+3Fh+var_90]
0x1800ed58f  sar     r8, 1
0x1800ed592  mov     [rbp+3Fh+var_98], rax
0x1800ed596  mov     [rbp+3Fh+var_90], r14w
0x1800ed59b  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800ed5a0  test    al, al
0x1800ed5a2  jnz     short loc_1800ED607
0x1800ed5a4  mov     rcx, [rbp+47h]; this
0x1800ed5a8  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ed5af  mov     r9d, 8007000Eh; char *
0x1800ed5b5  mov     edx, 0DDh; void *
0x1800ed5ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed5bf  mov     rcx, [rbp+3Fh+var_A0]; void *
0x1800ed5c3  lea     rax, [rbp+3Fh+var_90]
0x1800ed5c7  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800ed5ce  cmp     rcx, rax
0x1800ed5d1  jz      short loc_1800ED5DB
0x1800ed5d3  mov     rdx, rsi; struct std::nothrow_t *
0x1800ed5d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed5db  mov     rcx, rbx; pwk
0x1800ed5de  call    cs:__imp_CloseThreadpoolWork
0x1800ed5e5  nop     dword ptr [rax+rax+00h]
0x1800ed5ea  mov     rax, [rbp+3Fh+arg_30]
0x1800ed5ee  cmp     [rax+20h], r14b
0x1800ed5f2  jz      loc_1800ED6B7
0x1800ed5f8  mov     rcx, [rax]
0x1800ed5fb  add     rax, 10h
0x1800ed5ff  cmp     rcx, rax
0x1800ed602  jmp     loc_1800ED6AD
0x1800ed607  lea     rax, [rbp+3Fh+var_70]
0x1800ed60b  mov     [rbp+3Fh+var_70], r14w
0x1800ed610  mov     [rbp+3Fh+var_80], rax
0x1800ed614  lea     rcx, [rbp+3Fh+var_80]
0x1800ed618  lea     rax, [rbp+3Fh+var_70]
0x1800ed61c  mov     [rbp+3Fh+var_78], rax
0x1800ed620  mov     rax, [rbp+3Fh+arg_20]
0x1800ed624  mov     r8, [rax+8]
0x1800ed628  sub     r8, [rax]
0x1800ed62b  mov     rdx, [rax]
0x1800ed62e  sar     r8, 1
0x1800ed631  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800ed636  test    al, al
0x1800ed638  jnz     loc_1800ED6C1
0x1800ed63e  mov     rcx, [rbp+47h]; this
0x1800ed642  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ed649  mov     r9d, 8007000Eh; char *
0x1800ed64f  mov     edx, 0E0h; void *
0x1800ed654  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed659  mov     rcx, [rbp+3Fh+var_80]; void *
0x1800ed65d  lea     rax, [rbp+3Fh+var_70]
0x1800ed661  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800ed668  cmp     rcx, rax
0x1800ed66b  jz      short loc_1800ED675
0x1800ed66d  mov     rdx, rsi; struct std::nothrow_t *
0x1800ed670  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed675  mov     rcx, [rbp+3Fh+var_A0]; void *
0x1800ed679  lea     rax, [rbp+3Fh+var_90]
0x1800ed67d  cmp     rcx, rax
0x1800ed680  jz      short loc_1800ED68A
0x1800ed682  mov     rdx, rsi; struct std::nothrow_t *
0x1800ed685  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed68a  mov     rcx, rbx; pwk
0x1800ed68d  call    cs:__imp_CloseThreadpoolWork
0x1800ed694  nop     dword ptr [rax+rax+00h]
0x1800ed699  mov     rdx, [rbp+3Fh+arg_30]
0x1800ed69d  cmp     [rdx+20h], r14b
0x1800ed6a1  jz      short loc_1800ED6B7
0x1800ed6a3  mov     rcx, [rdx]; void *
0x1800ed6a6  add     rdx, 10h
0x1800ed6aa  cmp     rcx, rdx
0x1800ed6ad  jz      short loc_1800ED6B7
0x1800ed6af  mov     rdx, rsi; struct std::nothrow_t *
0x1800ed6b2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed6b7  mov     eax, 8007000Eh
0x1800ed6bc  jmp     loc_1800ED96E
0x1800ed6c1  mov     r14, [rbp+3Fh+arg_30]
0x1800ed6c5  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800ed6cc  cmp     byte ptr [r14+20h], 0
0x1800ed6d1  jnz     loc_1800ED7B4
0x1800ed6d7  lea     rax, [rbp+3Fh+var_50]
0x1800ed6db  mov     [rbp+3Fh+var_60], rax
0x1800ed6df  lea     rdx, [rbp+3Fh+var_60]
0x1800ed6e3  lea     rax, [rbp+3Fh+var_50]
0x1800ed6e7  mov     [rbp+3Fh+var_58], rax
0x1800ed6eb  lea     rcx, [rbp+3Fh+var_80]
0x1800ed6ef  xor     eax, eax
0x1800ed6f1  mov     [rbp+3Fh+var_50], ax
0x1800ed6f5  call    ?GetWimOsVersion@BaseImage@Details@Core@Manager@Container@@SAJAEBVPath@Csl@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Container::Manager::Core::Details::BaseImage::GetWimOsVersion(Csl::Path const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800ed6fa  mov     edi, eax
0x1800ed6fc  test    eax, eax
0x1800ed6fe  jns     loc_1800ED793
0x1800ed704  mov     rcx, [rbp+47h]; this
0x1800ed708  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ed70f  mov     r9d, eax; char *
0x1800ed712  mov     edx, 0E6h; void *
0x1800ed717  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed71c  mov     rcx, [rbp+3Fh+var_60]; void *
0x1800ed720  lea     rax, [rbp+3Fh+var_50]
0x1800ed724  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800ed72b  cmp     rcx, rax
0x1800ed72e  jz      short loc_1800ED738
0x1800ed730  mov     rdx, rsi; struct std::nothrow_t *
0x1800ed733  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed738  mov     rcx, [rbp+3Fh+var_80]; void *
0x1800ed73c  lea     rax, [rbp+3Fh+var_70]
0x1800ed740  cmp     rcx, rax
0x1800ed743  jz      short loc_1800ED74D
0x1800ed745  mov     rdx, rsi; struct std::nothrow_t *
0x1800ed748  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed74d  mov     rcx, [rbp+3Fh+var_A0]; void *
0x1800ed751  lea     rax, [rbp+3Fh+var_90]
0x1800ed755  cmp     rcx, rax
0x1800ed758  jz      short loc_1800ED762
0x1800ed75a  mov     rdx, rsi; struct std::nothrow_t *
0x1800ed75d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed762  mov     rcx, rbx; pwk
0x1800ed765  call    cs:__imp_CloseThreadpoolWork
0x1800ed76c  nop     dword ptr [rax+rax+00h]
0x1800ed771  cmp     byte ptr [r14+20h], 0
0x1800ed776  jz      short loc_1800ED78C
0x1800ed778  lea     rax, [r14+10h]
0x1800ed77c  cmp     [r14], rax
0x1800ed77f  jz      short loc_1800ED78C
0x1800ed781  mov     rcx, [r14]; void *
0x1800ed784  mov     rdx, rsi; struct std::nothrow_t *
0x1800ed787  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed78c  mov     eax, edi
0x1800ed78e  jmp     loc_1800ED96E
0x1800ed793  lea     rdx, [rbp+3Fh+var_60]
0x1800ed797  mov     rcx, r14
0x1800ed79a  call    ??$?4VPath@Csl@@$0A@@?$optional@VPath@Csl@@@utl@@QEAAAEAV01@$$QEAVPath@Csl@@@Z; utl::optional<Csl::Path>::operator=<Csl::Path,0>(Csl::Path &&)
0x1800ed79f  mov     rcx, [rbp+3Fh+var_60]; void *
0x1800ed7a3  lea     rax, [rbp+3Fh+var_50]
0x1800ed7a7  cmp     rcx, rax
0x1800ed7aa  jz      short loc_1800ED7B4
0x1800ed7ac  mov     rdx, rsi; struct std::nothrow_t *
0x1800ed7af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed7b4  mov     rcx, [rbp+3Fh+arg_48]
0x1800ed7bb  lea     r8, [rbp+3Fh+hKey]
0x1800ed7bf  mov     [rbp+3Fh+hKey], 0
0x1800ed7c7  call    ?Duplicate@RegistryKey@Csl@@QEBAJW4RegistryKeyAccess@2@AEAV12@@Z; Csl::RegistryKey::Duplicate(Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x1800ed7cc  mov     edi, eax
0x1800ed7ce  test    eax, eax
0x1800ed7d0  jns     short loc_1800ED808
0x1800ed7d2  mov     rcx, [rbp+47h]; this
0x1800ed7d6  lea     r8, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ed7dd  mov     r9d, eax; char *
0x1800ed7e0  mov     edx, 0EDh; void *
0x1800ed7e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ed7ea  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800ed7ee  test    rcx, rcx
0x1800ed7f1  jz      loc_1800ED738
0x1800ed7f7  call    cs:__imp_RegCloseKey
0x1800ed7fe  nop     dword ptr [rax+rax+00h]
0x1800ed803  jmp     loc_1800ED738
0x1800ed808  movups  xmm0, xmmword ptr [r13+0]
0x1800ed80d  lea     rcx, [r15+18h]
0x1800ed811  mov     [r15+10h], r12d
0x1800ed815  lea     rdx, [rbp+3Fh+var_A0]
0x1800ed819  movdqu  xmmword ptr [r15], xmm0
0x1800ed81e  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1800ed823  lea     rcx, [r15+38h]
0x1800ed827  lea     rdx, [rbp+3Fh+var_80]
0x1800ed82b  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1800ed830  mov     eax, [rbp+3Fh+arg_28]
0x1800ed833  mov     [r15+58h], eax
0x1800ed837  cmp     byte ptr [r14+20h], 0
0x1800ed83c  jnz     short loc_1800ED840
0x1800ed83e  int     2Ch; Windows NT - assertion failure
0x1800ed840  lea     rcx, [r15+60h]
0x1800ed844  mov     rdx, r14
0x1800ed847  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1800ed84c  mov     eax, [rbp+3Fh+arg_38]
0x1800ed852  lea     r12, [r15+90h]
0x1800ed859  mov     [r15+8Ch], eax
0x1800ed860  mov     eax, [rbp+3Fh+arg_40]
0x1800ed866  mov     [r15+88h], eax
0x1800ed86d  lea     rax, [rbp+3Fh+var_A8]
0x1800ed871  cmp     r12, rax
0x1800ed874  jz      short loc_1800ED8B0
0x1800ed876  mov     r13, [r12]
0x1800ed87a  test    r13, r13
0x1800ed87d  jz      short loc_1800ED8AA
0x1800ed87f  call    cs:__imp_GetLastError
0x1800ed886  nop     dword ptr [rax+rax+00h]
0x1800ed88b  mov     rcx, r13; pwk
0x1800ed88e  mov     edi, eax
0x1800ed890  call    cs:__imp_CloseThreadpoolWork
0x1800ed897  nop     dword ptr [rax+rax+00h]
0x1800ed89c  mov     ecx, edi; dwErrCode
0x1800ed89e  call    cs:__imp_SetLastError
0x1800ed8a5  nop     dword ptr [rax+rax+00h]
0x1800ed8aa  mov     [r12], rbx
0x1800ed8ae  xor     ebx, ebx
0x1800ed8b0  add     r15, 0A8h
0x1800ed8b7  lea     rax, [rbp+3Fh+hKey]
0x1800ed8bb  cmp     r15, rax
0x1800ed8be  jz      short loc_1800ED8FE
0x1800ed8c0  mov     r12, [r15]
0x1800ed8c3  mov     r13, [rbp+3Fh+hKey]
0x1800ed8c7  test    r12, r12
0x1800ed8ca  jz      short loc_1800ED8F7
0x1800ed8cc  call    cs:__imp_GetLastError
0x1800ed8d3  nop     dword ptr [rax+rax+00h]
0x1800ed8d8  mov     rcx, r12; hKey
0x1800ed8db  mov     edi, eax
0x1800ed8dd  call    cs:__imp_RegCloseKey
0x1800ed8e4  nop     dword ptr [rax+rax+00h]
0x1800ed8e9  mov     ecx, edi; dwErrCode
0x1800ed8eb  call    cs:__imp_SetLastError
0x1800ed8f2  nop     dword ptr [rax+rax+00h]
0x1800ed8f7  mov     [r15], r13
0x1800ed8fa  xor     ecx, ecx
0x1800ed8fc  jmp     short loc_1800ED902
0x1800ed8fe  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800ed902  test    rcx, rcx
0x1800ed905  jz      short loc_1800ED913
0x1800ed907  call    cs:__imp_RegCloseKey
0x1800ed90e  nop     dword ptr [rax+rax+00h]
0x1800ed913  mov     rcx, [rbp+3Fh+var_80]; void *
0x1800ed917  lea     rax, [rbp+3Fh+var_70]
0x1800ed91b  cmp     rcx, rax
0x1800ed91e  jz      short loc_1800ED928
0x1800ed920  mov     rdx, rsi; struct std::nothrow_t *
0x1800ed923  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed928  mov     rcx, [rbp+3Fh+var_A0]; void *
0x1800ed92c  lea     rax, [rbp+3Fh+var_90]
0x1800ed930  cmp     rcx, rax
0x1800ed933  jz      short loc_1800ED93D
0x1800ed935  mov     rdx, rsi; struct std::nothrow_t *
0x1800ed938  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed93d  test    rbx, rbx
0x1800ed940  jz      short loc_1800ED951
0x1800ed942  mov     rcx, rbx; pwk
0x1800ed945  call    cs:__imp_CloseThreadpoolWork
0x1800ed94c  nop     dword ptr [rax+rax+00h]
0x1800ed951  cmp     byte ptr [r14+20h], 0
0x1800ed956  jz      short loc_1800ED96C
0x1800ed958  lea     rax, [r14+10h]
0x1800ed95c  cmp     [r14], rax
0x1800ed95f  jz      short loc_1800ED96C
0x1800ed961  mov     rcx, [r14]; void *
0x1800ed964  mov     rdx, rsi; struct std::nothrow_t *
0x1800ed967  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ed96c  xor     eax, eax
0x1800ed96e  add     rsp, 98h
0x1800ed975  pop     r15
0x1800ed977  pop     r14
0x1800ed979  pop     r13
0x1800ed97b  pop     r12
0x1800ed97d  pop     rdi
0x1800ed97e  pop     rsi
0x1800ed97f  pop     rbx
0x1800ed980  pop     rbp
0x1800ed981  retn
  ... truncated ...
```
