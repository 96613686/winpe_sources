# AreThereAnyStagedAIFabricPackages(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x180078fd0`
- end: `0x180079428`
- name: `?AreThereAnyStagedAIFabricPackages@@YA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `1112`
- prototype: `char __fastcall(const wchar_t **)`
- caller_count: `2`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026bc0`
- `0x18007a7fc`

## callees

- `0x1800058cb`
- `0x18000591f`
- `0x18000b064`
- `0x18000c350`
- `0x18000c478`
- `0x18000c634`
- `0x1800189b8`
- `0x180019c3c`
- `0x18005fc04`
- `0x180078ab4`
- `0x180078b28`
- `0x180078bd8`
- `0x180078fd0`
- `0x1800797c8`
- `0x180079a98`
- `0x180079e24`
- `0x18007a4e4`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180079375`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180079375`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180079033`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180079367`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800793af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180079033`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180079367`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800793af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18007900f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18007900f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007934d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079395`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007934d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079395`

## string_xrefs

- `0x180079047`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x18007909f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x1800793d7`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\registerstagedaifabricpackages.cpp`
- `0x1800793ec`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\registerstagedaifabricpackages.cpp`
- `0x180079401`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\registerstagedaifabricpackages.cpp`
- `0x180079416`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\registerstagedaifabricpackages.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
char __fastcall AreThereAnyStagedAIFabricPackages(const wchar_t **a1)
{
  int v2; // ebx
  __int64 v3; // rcx
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  __int64 v7; // r8
  __int64 v8; // r8
  unsigned int v9; // edx
  const void *v10; // r14
  __int64 v11; // rdi
  volatile signed __int32 *v12; // rbx
  int v13; // eax
  int v14; // eax
  HANDLE ProcessHeap; // rax
  int v16; // eax
  int v17; // esi
  HANDLE v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+38h] [rbp-C8h]
  __int64 v27; // [rsp+40h] [rbp-C0h]
  __int64 *v28; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v30; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h]
  __int128 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+90h] [rbp-70h]
  _OWORD v35[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v36; // [rsp+D0h] [rbp-30h]
  int v37; // [rsp+E0h] [rbp-20h]
  void *Source[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v39; // [rsp+100h] [rbp+0h]
  __int128 v40; // [rsp+108h] [rbp+8h]
  __int64 v41; // [rsp+118h] [rbp+18h]
  __int64 v42; // [rsp+120h] [rbp+20h]
  __int64 v43; // [rsp+128h] [rbp+28h]
  __int128 v44; // [rsp+130h] [rbp+30h]
  int v45; // [rsp+140h] [rbp+40h]
  __int64 v46; // [rsp+148h] [rbp+48h]
  __int64 v47; // [rsp+150h] [rbp+50h]
  volatile signed __int32 *v48; // [rsp+160h] [rbp+60h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]
  int v50; // [rsp+1B0h] [rbp+B0h] BYREF
  char v51; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v52; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v53; // [rsp+1C8h] [rbp+C8h] BYREF

  v52 = 0;
  v28 = &v52;
  *(_QWORD *)&v29 = 0;
  BYTE8(v29) = 1;
  v2 = SRCacheManager_Open(0, &v29);
  if ( BYTE8(v29) )
  {
    v3 = *v28;
    *v28 = v29;
    if ( v3 )
      SRCacheManager_Close();
  }
  if ( v2 >= 0 )
    v2 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v2,
      v24);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\registerstagedaifabricpackages.cpp",
      (const char *)(unsigned int)v2,
      v24);
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v4 = StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::OpenByName(
         (StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow *)&v25,
         (struct StateRepository::Cache::Manager_NoThrow *)&v52,
         *a1);
  v5 = v4;
  if ( v4 >= 0 )
    v5 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C2,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v4,
      v24);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\registerstagedaifabricpackages.cpp",
      (const char *)(unsigned int)v5,
      v24);
  memset(v35, 0, sizeof(v35));
  v36 = 0;
  v37 = 0;
  LOBYTE(v50) = 0;
  v6 = StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::Get(&v25, 32, v35, &v50);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\registerstagedaifabricpackages.cpp",
      (const char *)(unsigned int)v6,
      v24);
  while ( 1 )
  {
    if ( !(_BYTE)v50 )
    {
      StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((StateRepository::Cache::Entity::PkgExtension_NoThrow *)v35);
      v22 = v25;
      v25 = 0;
      if ( v22 )
        SRCacheContext_Close();
      v23 = v52;
      v52 = 0;
      if ( v23 )
        SRCacheManager_Close();
      return 0;
    }
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    StateRepository::Cache::Entity::PackageExtension_NoThrow::Get(&v52, v36, v7, &v30);
    if ( (_BYTE)v50 )
      break;
LABEL_30:
    StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)&v30);
    ++v26;
    v16 = StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::Get(&v25, 0, v35, &v50);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\registerstagedaifabricpackages.cpp",
        (const char *)(unsigned int)v16,
        (int)&v50);
  }
  *(_OWORD *)Source = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  StateRepository::Cache::Entity::Package_NoThrow::Get(&v52, *((_QWORD *)&v30 + 1), v8, Source);
  if ( !(_BYTE)v50 )
  {
LABEL_29:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)Source);
    goto LABEL_30;
  }
  v10 = Source[1];
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)Source[1] + v11) );
  if ( (_DWORD)v11 )
  {
    v12 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v11, v9);
    memcpy_s((void *const)(v12 + 7), 2LL * (unsigned int)v11, v10, 2LL * (unsigned int)v11);
  }
  else
  {
    v12 = 0;
  }
  v48 = v12;
  winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager::GetDefault();
  v51 = 0;
  LODWORD(v28) = 0;
  v29 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *, char *))(*(_QWORD *)v53 + 48LL))(v53, v12, &v51);
  if ( v13 < 0 )
    winrt::throw_hresult((unsigned int)v13, &v28);
  if ( v51 )
  {
    if ( v53 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v53);
    if ( v12 )
    {
      v14 = _InterlockedDecrement(v12 + 6);
      if ( v14 )
      {
        if ( v14 < 0 )
          goto LABEL_43;
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v12);
      }
    }
    goto LABEL_29;
  }
  if ( v53 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v53);
  if ( v12 )
  {
    v17 = _InterlockedDecrement(v12 + 6);
    if ( v17 )
    {
      if ( v17 < 0 )
LABEL_43:
        abort();
    }
    else
    {
      v18 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v18, 0, (LPVOID)v12);
    }
  }
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)Source);
  StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)&v30);
  StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((StateRepository::Cache::Entity::PkgExtension_NoThrow *)v35);
  v19 = v25;
  v25 = 0;
  if ( v19 )
    SRCacheContext_Close();
  v20 = v52;
  v52 = 0;
  if ( v20 )
    SRCacheManager_Close();
  return 1;
}

```

## disassembly

```asm
0x180078fd0  push    rbp
0x180078fd2  push    rbx
0x180078fd3  push    rsi
0x180078fd4  push    rdi
0x180078fd5  push    r14
0x180078fd7  push    r15
0x180078fd9  lea     rbp, [rsp-78h]
0x180078fde  sub     rsp, 178h
0x180078fe5  mov     rdi, rcx
0x180078fe8  xor     r15d, r15d
0x180078feb  mov     [rbp+0A0h+arg_10], r15
0x180078ff2  lea     rax, [rbp+0A0h+arg_10]
0x180078ff9  mov     [rsp+1A0h+var_158], rax
0x180078ffe  mov     qword ptr [rsp+1A0h+var_150], r15
0x180079003  mov     byte ptr [rsp+1A0h+var_150+8], 1
0x180079008  lea     rdx, [rsp+1A0h+var_150]
0x18007900d  xor     ecx, ecx
0x18007900f  call    cs:__imp_SRCacheManager_Open
0x180079015  mov     ebx, eax
0x180079017  cmp     byte ptr [rsp+1A0h+var_150+8], r15b
0x18007901c  jz      short loc_180079039
0x18007901e  mov     rdx, [rsp+1A0h+var_158]
0x180079023  mov     rcx, [rdx]
0x180079026  mov     rax, qword ptr [rsp+1A0h+var_150]
0x18007902b  mov     [rdx], rax
0x18007902e  test    rcx, rcx
0x180079031  jz      short loc_180079039
0x180079033  call    cs:__imp_SRCacheManager_Close
0x180079039  test    ebx, ebx
0x18007903b  jns     short loc_18007905A
0x18007903d  mov     rcx, [rbp+0A8h]; this
0x180079044  mov     r9d, ebx; char *
0x180079047  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007904e  mov     edx, 0A5h; void *
0x180079053  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079058  jmp     short loc_18007905D
0x18007905a  mov     ebx, r15d
0x18007905d  mov     rcx, [rbp+0A8h]; this
0x180079064  test    ebx, ebx
0x180079066  js      loc_1800793E9
0x18007906c  mov     [rsp+1A0h+var_170], r15
0x180079071  mov     [rsp+1A0h+var_168], r15d
0x180079076  mov     [rsp+1A0h+var_160], r15
0x18007907b  mov     r8, [rdi]; wchar_t *
0x18007907e  lea     rdx, [rbp+0A0h+arg_10]; struct StateRepository::Cache::Manager_NoThrow *
0x180079085  lea     rcx, [rsp+1A0h+var_170]; this
0x18007908a  call    ?OpenByName@PkgExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEB_W@Z; StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::OpenByName(StateRepository::Cache::Manager_NoThrow &,wchar_t const *)
0x18007908f  mov     ebx, eax
0x180079091  test    eax, eax
0x180079093  jns     short loc_1800790B2
0x180079095  mov     rcx, [rbp+0A8h]; this
0x18007909c  mov     r9d, eax; char *
0x18007909f  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800790a6  mov     edx, 2C2h; void *
0x1800790ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800790b0  jmp     short loc_1800790B5
0x1800790b2  mov     ebx, r15d
0x1800790b5  mov     rcx, [rbp+0A8h]; this
0x1800790bc  test    ebx, ebx
0x1800790be  js      loc_1800793FE
0x1800790c4  xorps   xmm0, xmm0
0x1800790c7  movdqa  [rbp+0A0h+var_100], xmm0
0x1800790cc  xorps   xmm1, xmm1
0x1800790cf  movdqa  [rbp+0A0h+var_F0], xmm1
0x1800790d4  movdqa  [rbp+0A0h+var_E0], xmm0
0x1800790d9  movdqa  [rbp+0A0h+var_D0], xmm1
0x1800790de  mov     [rbp+0A0h+var_C0], r15d
0x1800790e2  mov     byte ptr [rbp+0A0h+arg_0], r15b
0x1800790e9  lea     r9, [rbp+0A0h+arg_0]
0x1800790f0  lea     r8, [rbp+0A0h+var_100]
0x1800790f4  mov     edx, 20h ; ' '
0x1800790f9  lea     rcx, [rsp+1A0h+var_170]
0x1800790fe  call    ?Get@PkgExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PkgExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PkgExtension_NoThrow &,bool &)
0x180079103  mov     rcx, [rbp+0A8h]; this
0x18007910a  test    eax, eax
0x18007910c  js      loc_180079413
0x180079112  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180079116  cmp     byte ptr [rbp+0A0h+arg_0], r15b
0x18007911d  jz      loc_18007937C
0x180079123  xorps   xmm0, xmm0
0x180079126  movdqa  [rsp+1A0h+var_140], xmm0
0x18007912c  mov     [rsp+1A0h+var_130], r15
0x180079131  mov     [rsp+1A0h+var_128], r15
0x180079136  movdqa  [rbp+0A0h+var_120], xmm0
0x18007913b  xorps   xmm1, xmm1
0x18007913e  movdqa  [rbp+0A0h+var_110], xmm1
0x180079143  lea     rax, [rbp+0A0h+arg_0]
0x18007914a  mov     qword ptr [rsp+1A0h+var_180], rax
0x18007914f  lea     r9, [rsp+1A0h+var_140]
0x180079154  mov     rdx, qword ptr [rbp+0A0h+var_D0]
0x180079158  lea     rcx, [rbp+0A0h+arg_10]
0x18007915f  call    ?Get@PackageExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)
0x180079164  cmp     byte ptr [rbp+0A0h+arg_0], r15b
0x18007916b  jz      loc_1800792AD
0x180079171  xorps   xmm0, xmm0
0x180079174  movdqa  xmmword ptr [rbp+0A0h+Source], xmm0
0x180079179  mov     [rbp+0A0h+var_A0], r15
0x18007917d  xorps   xmm1, xmm1
0x180079180  movups  [rbp+0A0h+var_98], xmm1
0x180079184  mov     [rbp+0A0h+var_88], r15
0x180079188  mov     [rbp+0A0h+var_80], r15
0x18007918c  mov     [rbp+0A0h+var_78], r15
0x180079190  movdqa  [rbp+0A0h+var_70], xmm0
0x180079195  mov     [rbp+0A0h+var_60], r15d
0x180079199  mov     [rbp+0A0h+var_58], r15
0x18007919d  mov     [rbp+0A0h+var_50], r15
0x1800791a1  lea     rax, [rbp+0A0h+arg_0]
0x1800791a8  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x1800791ad  lea     r9, [rbp+0A0h+Source]
0x1800791b1  mov     rdx, qword ptr [rsp+1A0h+var_140+8]
0x1800791b6  lea     rcx, [rbp+0A0h+arg_10]
0x1800791bd  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x1800791c2  cmp     byte ptr [rbp+0A0h+arg_0], r15b
0x1800791c9  jz      loc_1800792A3
0x1800791cf  mov     r14, [rbp+0A0h+Source+8]
0x1800791d3  mov     rdi, rsi
0x1800791d6  inc     rdi
0x1800791d9  cmp     [r14+rdi*2], r15w
0x1800791de  jnz     short loc_1800791D6
0x1800791e0  test    edi, edi
0x1800791e2  jnz     short loc_1800791E9
0x1800791e4  mov     rbx, r15
0x1800791e7  jmp     short loc_180079207
0x1800791e9  mov     ecx, edi; this
0x1800791eb  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800791f0  mov     rbx, rax
0x1800791f3  mov     edx, edi
0x1800791f5  add     rdx, rdx; DestinationSize
0x1800791f8  lea     rcx, [rax+1Ch]; Destination
0x1800791fc  mov     r9, rdx; SourceSize
0x1800791ff  mov     r8, r14; Source
0x180079202  call    memcpy_s
0x180079207  mov     [rbp+0A0h+var_40], rbx
0x18007920b  lea     rcx, [rbp+0A0h+arg_18]
0x180079212  call    ?GetDefault@PackageDeploymentManager@Deployment@Management@Windows@Microsoft@winrt@@SA@XZ; winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager::GetDefault(void)
0x180079217  nop
0x180079218  mov     [rbp+0A0h+arg_8], r15b
0x18007921f  mov     rcx, [rbp+0A0h+arg_18]
0x180079226  mov     dword ptr [rsp+1A0h+var_158], r15d
0x18007922b  xorps   xmm0, xmm0
0x18007922e  movdqu  [rsp+1A0h+var_150], xmm0
0x180079234  mov     rax, [rcx]
0x180079237  lea     r8, [rbp+0A0h+arg_8]
0x18007923e  mov     rdx, rbx
0x180079241  mov     rax, [rax+30h]
0x180079245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007924a  test    eax, eax
0x18007924c  js      loc_1800793C7
0x180079252  cmp     [rbp+0A0h+arg_8], r15b
0x180079259  jz      loc_1800792E6
0x18007925f  cmp     [rbp+0A0h+arg_18], r15
0x180079266  jz      short loc_180079275
0x180079268  lea     rcx, [rbp+0A0h+arg_18]
0x18007926f  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180079274  nop
0x180079275  test    rbx, rbx
0x180079278  jz      short loc_1800792A3
0x18007927a  mov     eax, esi
0x18007927c  lock xadd [rbx+18h], eax
0x180079281  sub     eax, 1
0x180079284  jnz     short loc_18007929B
0x180079286  nop
0x180079287  call    WINRT_IMPL_GetProcessHeap
0x18007928c  mov     rcx, rax; hHeap
0x18007928f  mov     r8, rbx; lpMem
0x180079292  xor     edx, edx; dwFlags
0x180079294  call    WINRT_IMPL_HeapFree
0x180079299  jmp     short loc_1800792A3
0x18007929b  test    eax, eax
0x18007929d  js      loc_180079375
0x1800792a3  lea     rcx, [rbp+0A0h+Source]; this
0x1800792a7  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800792ac  nop
0x1800792ad  lea     rcx, [rsp+1A0h+var_140]; this
0x1800792b2  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x1800792b7  inc     [rsp+1A0h+var_168]
0x1800792bb  lea     r9, [rbp+0A0h+arg_0]
0x1800792c2  lea     r8, [rbp+0A0h+var_100]
0x1800792c6  xor     edx, edx
0x1800792c8  lea     rcx, [rsp+1A0h+var_170]
0x1800792cd  call    ?Get@PkgExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PkgExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PkgExtension_NoThrow &,bool &)
0x1800792d2  mov     rcx, [rbp+0A8h]; this
0x1800792d9  test    eax, eax
0x1800792db  js      loc_1800793D4
0x1800792e1  jmp     loc_180079116
0x1800792e6  cmp     [rbp+0A0h+arg_18], r15
0x1800792ed  jz      short loc_1800792FC
0x1800792ef  lea     rcx, [rbp+0A0h+arg_18]
0x1800792f6  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800792fb  nop
0x1800792fc  test    rbx, rbx
0x1800792ff  jz      short loc_18007931F
0x180079301  lock xadd [rbx+18h], esi
0x180079306  sub     esi, 1
0x180079309  jnz     short loc_180079371
0x18007930b  nop
0x18007930c  call    WINRT_IMPL_GetProcessHeap
0x180079311  mov     rcx, rax; hHeap
0x180079314  mov     r8, rbx; lpMem
0x180079317  xor     edx, edx; dwFlags
0x180079319  call    WINRT_IMPL_HeapFree
0x18007931e  nop
0x18007931f  lea     rcx, [rbp+0A0h+Source]; this
0x180079323  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180079328  nop
0x180079329  lea     rcx, [rsp+1A0h+var_140]; this
0x18007932e  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x180079333  nop
0x180079334  lea     rcx, [rbp+0A0h+var_100]; this
0x180079338  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x18007933d  nop
0x18007933e  mov     rcx, [rsp+1A0h+var_170]
0x180079343  mov     [rsp+1A0h+var_170], r15
0x180079348  test    rcx, rcx
0x18007934b  jz      short loc_180079354
0x18007934d  call    cs:__imp_SRCacheContext_Close
0x180079353  nop
0x180079354  mov     rcx, [rbp+0A0h+arg_10]
0x18007935b  mov     [rbp+0A0h+arg_10], r15
0x180079362  test    rcx, rcx
0x180079365  jz      short loc_18007936D
0x180079367  call    cs:__imp_SRCacheManager_Close
0x18007936d  mov     al, 1
0x18007936f  jmp     short loc_1800793B7
0x180079371  test    esi, esi
0x180079373  jns     short loc_18007931F
0x180079375  call    cs:__imp_abort
0x18007937c  lea     rcx, [rbp+0A0h+var_100]; this
0x180079380  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x180079385  nop
0x180079386  mov     rcx, [rsp+1A0h+var_170]
0x18007938b  mov     [rsp+1A0h+var_170], r15
0x180079390  test    rcx, rcx
0x180079393  jz      short loc_18007939C
0x180079395  call    cs:__imp_SRCacheContext_Close
0x18007939b  nop
0x18007939c  mov     rcx, [rbp+0A0h+arg_10]
0x1800793a3  mov     [rbp+0A0h+arg_10], r15
0x1800793aa  test    rcx, rcx
0x1800793ad  jz      short loc_1800793B5
0x1800793af  call    cs:__imp_SRCacheManager_Close
0x1800793b5  xor     al, al
0x1800793b7  add     rsp, 178h
0x1800793be  pop     r15
0x1800793c0  pop     r14
0x1800793c2  pop     rdi
0x1800793c3  pop     rsi
0x1800793c4  pop     rbx
0x1800793c5  pop     rbp
0x1800793c6  retn
0x1800793c7  lea     rdx, [rsp+1A0h+var_158]
0x1800793cc  mov     ecx, eax
0x1800793ce  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800793d4  mov     r9d, eax; char *
0x1800793d7  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800793de  mov     edx, 40h ; '@'; void *
0x1800793e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800793e9  mov     r9d, ebx; char *
0x1800793ec  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800793f3  mov     edx, 36h ; '6'; void *
0x1800793f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800793fe  mov     r9d, ebx; char *
0x180079401  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x180079408  mov     edx, 39h ; '9'; void *
0x18007940d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180079413  mov     r9d, eax; char *
0x180079416  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x18007941d  mov     edx, 3Eh ; '>'; void *
0x180079422  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
