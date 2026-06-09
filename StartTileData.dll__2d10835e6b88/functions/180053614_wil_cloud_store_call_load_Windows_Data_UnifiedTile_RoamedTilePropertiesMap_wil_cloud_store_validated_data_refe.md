# wil::cloud_store::call_load<Windows::Data::UnifiedTile::RoamedTilePropertiesMap>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180053614`
- end: `0x18005398c`
- name: `??$call_load@URoamedTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@URoamedTilePropertiesMap@UnifiedTile@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `888`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18005417c`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x180053614`
- `0x180056798`
- `0x1800574a8`
- `0x1800579bc`
- `0x18005c4e4`
- `0x180147be8`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053700`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005377c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800537e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053846`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053943`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053959`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005396f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053985`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053700`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005377c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800537e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053846`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053943`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053959`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005396f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053985`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800536ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800537ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800536ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800537ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053830`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall wil::cloud_store::call_load<Windows::Data::UnifiedTile::RoamedTilePropertiesMap>(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 v9; // rax
  const WCHAR *v10; // rsi
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rbx
  unsigned int v13; // eax
  UINT32 v14; // edx
  HRESULT v15; // eax
  const WCHAR *v16; // rsi
  unsigned __int64 v17; // rbx
  unsigned int v18; // eax
  UINT32 v19; // edx
  HRESULT v20; // eax
  const WCHAR *v21; // rsi
  unsigned __int64 v22; // rbx
  unsigned int v23; // eax
  UINT32 v24; // edx
  HRESULT v25; // eax
  int v26; // ebx
  unsigned int v27; // eax
  UINT32 v28; // edx
  HRESULT v29; // eax
  __int64 *v30; // rax
  __int64 v31; // r8
  int v32; // eax
  __int64 v35; // [rsp+60h] [rbp-A0h]
  __int64 *v36; // [rsp+78h] [rbp-88h]
  HSTRING_HEADER v37; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v38; // [rsp+98h] [rbp-68h] BYREF
  HSTRING_HEADER v39; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING v40; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v41; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v42; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING string; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v45[3]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v46; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v36 = *(__int64 **)wil::details::shared_cloud_store_state::get_cloud_store(*(_QWORD *)a1);
  v35 = *v36;
  v9 = wil::cloud_store::widen_string(v45, a5);
  v10 = (const WCHAR *)v9;
  if ( *(_QWORD *)(v9 + 24) > 7u )
    v10 = *(const WCHAR **)v9;
  string = 0;
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( v10[v12] );
  if ( v12 > 0xFFFFFFFF )
  {
LABEL_48:
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x18005398BLL);
  }
  v13 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v12);
  v14 = v13 - 1;
  if ( (unsigned int)v12 < v13 )
    v14 = v12;
  v15 = WindowsCreateStringReference(v10, v14, &hstringHeader, &string);
  if ( v15 < 0 )
    RaiseException(v15, 1u, 0, 0);
  wil::cloud_store::convert_cloud_store_load_options(a4);
  v16 = (const WCHAR *)(a3 + 8);
  if ( (unsigned __int64)a3[11] > 7 )
    v16 = *(const WCHAR **)v16;
  v42 = 0;
  v17 = -1;
  do
    ++v17;
  while ( v16[v17] );
  if ( v17 > 0xFFFFFFFF )
  {
LABEL_47:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_48;
  }
  v18 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v17);
  v19 = v18 - 1;
  if ( (unsigned int)v17 < v18 )
    v19 = v17;
  v20 = WindowsCreateStringReference(v16, v19, &v41, &v42);
  if ( v20 < 0 )
    RaiseException(v20, 1u, 0, 0);
  v21 = (const WCHAR *)(a3 + 4);
  if ( (unsigned __int64)a3[7] > 7 )
    v21 = *(const WCHAR **)v21;
  v40 = 0;
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  if ( v22 > 0xFFFFFFFF )
  {
LABEL_46:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_47;
  }
  v23 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v22);
  v24 = v23 - 1;
  if ( (unsigned int)v22 < v23 )
    v24 = v22;
  v25 = WindowsCreateStringReference(v21, v24, &v39, &v40);
  if ( v25 < 0 )
    RaiseException(v25, 1u, 0, 0);
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (__int64 *)*a3;
  v38 = 0;
  do
    ++v11;
  while ( *((_WORD *)a3 + v11) );
  if ( v11 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_46;
  }
  v26 = (int)v40;
  v27 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  v28 = v27 - 1;
  if ( (unsigned int)v11 < v27 )
    v28 = v11;
  v29 = WindowsCreateStringReference((PCWSTR)a3, v28, &v37, &v38);
  if ( v29 < 0 )
    RaiseException(v29, 1u, 0, 0);
  v30 = *(__int64 **)(a1 + 24);
  if ( v30 )
    v31 = *v30;
  else
    v31 = 0;
  v32 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, HSTRING))(v35 + 72))(
          v36,
          *(unsigned int *)(a1 + 16),
          v31,
          v38);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x588,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v32,
      v26);
  v38 = 0;
  v40 = 0;
  v42 = 0;
  string = 0;
  if ( v46 > 7 )
    std::_Deallocate<16>(v45[0], 2 * v46 + 2);
  wil::cloud_store::unmarshal<Windows::Data::UnifiedTile::RoamedTilePropertiesMap>(a2, 0, a4);
  return a2;
}

```

## disassembly

```asm
0x180053614  push    rbp
0x180053616  push    rbx
0x180053617  push    rsi
0x180053618  push    rdi
0x180053619  push    r12
0x18005361b  push    r13
0x18005361d  push    r14
0x18005361f  push    r15
0x180053621  lea     rbp, [rsp-38h]
0x180053626  sub     rsp, 138h
0x18005362d  mov     rax, cs:__security_cookie
0x180053634  xor     rax, rsp
0x180053637  mov     [rbp+70h+var_50], rax
0x18005363b  mov     r12d, r9d
0x18005363e  mov     [rsp+170h+var_114], r9d
0x180053643  mov     r14, r8
0x180053646  mov     r15, rdx
0x180053649  mov     r13, rcx
0x18005364c  mov     [rsp+170h+var_110], rdx
0x180053651  mov     rbx, [rbp+70h+arg_20]
0x180053658  xor     edi, edi
0x18005365a  mov     [rsp+170h+var_120], rdi
0x18005365f  mov     rcx, [rcx]
0x180053662  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180053667  mov     rax, [rax]
0x18005366a  mov     [rsp+170h+var_F8], rax
0x18005366f  mov     rax, [rax]
0x180053672  mov     [rsp+170h+var_110], rax
0x180053677  mov     rcx, [rsp+170h+var_120]
0x18005367c  mov     [rsp+170h+var_120], rdi
0x180053681  test    rcx, rcx
0x180053684  jz      short loc_180053693
0x180053686  mov     rax, [rcx]
0x180053689  mov     rax, [rax+10h]
0x18005368d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053692  nop
0x180053693  mov     rdx, rbx
0x180053696  lea     rcx, [rbp+70h+var_70]
0x18005369a  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x18005369f  mov     rsi, rax
0x1800536a2  cmp     qword ptr [rax+18h], 7
0x1800536a7  jbe     short loc_1800536AC
0x1800536a9  mov     rsi, [rax]
0x1800536ac  mov     [rbp+70h+string], rdi
0x1800536b0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800536b4  mov     rbx, rdi
0x1800536b7  xor     eax, eax
0x1800536b9  inc     rbx
0x1800536bc  cmp     [rsi+rbx*2], ax
0x1800536c0  jnz     short loc_1800536B9
0x1800536c2  mov     eax, 0FFFFFFFFh
0x1800536c7  cmp     rbx, rax
0x1800536ca  ja      loc_180053976
0x1800536d0  mov     ecx, ebx; unsigned int
0x1800536d2  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800536d7  lea     edx, [rax-1]
0x1800536da  cmp     ebx, eax
0x1800536dc  cmovb   edx, ebx; length
0x1800536df  lea     r9, [rbp+70h+string]; string
0x1800536e3  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x1800536e7  mov     rcx, rsi; sourceString
0x1800536ea  call    cs:__imp_WindowsCreateStringReference
0x1800536f0  test    eax, eax
0x1800536f2  jns     short loc_180053707
0x1800536f4  xor     r9d, r9d; lpArguments
0x1800536f7  xor     r8d, r8d; nNumberOfArguments
0x1800536fa  lea     edx, [r9+1]; dwExceptionFlags
0x1800536fe  mov     ecx, eax; dwExceptionCode
0x180053700  call    cs:__imp_RaiseException
0x180053706  nop
0x180053707  mov     rax, [rbp+70h+string]
0x18005370b  mov     [rsp+170h+var_100], rax
0x180053710  mov     ecx, r12d
0x180053713  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x180053718  mov     [rsp+170h+var_118], eax
0x18005371c  lea     rsi, [r14+40h]
0x180053720  cmp     qword ptr [rsi+18h], 7
0x180053725  jbe     short loc_18005372A
0x180053727  mov     rsi, [rsi]
0x18005372a  xor     r12d, r12d
0x18005372d  mov     [rbp+70h+var_98], r12
0x180053731  mov     rbx, rdi
0x180053734  inc     rbx
0x180053737  cmp     [rsi+rbx*2], r12w
0x18005373c  jnz     short loc_180053734
0x18005373e  mov     eax, 0FFFFFFFFh
0x180053743  cmp     rbx, rax
0x180053746  ja      loc_180053960
0x18005374c  mov     ecx, ebx; unsigned int
0x18005374e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180053753  lea     edx, [rax-1]
0x180053756  cmp     ebx, eax
0x180053758  cmovb   edx, ebx; length
0x18005375b  lea     r9, [rbp+70h+var_98]; string
0x18005375f  lea     r8, [rbp+70h+var_B0]; hstringHeader
0x180053763  mov     rcx, rsi; sourceString
0x180053766  call    cs:__imp_WindowsCreateStringReference
0x18005376c  test    eax, eax
0x18005376e  jns     short loc_180053783
0x180053770  xor     r9d, r9d; lpArguments
0x180053773  xor     r8d, r8d; nNumberOfArguments
0x180053776  lea     edx, [r9+1]; dwExceptionFlags
0x18005377a  mov     ecx, eax; dwExceptionCode
0x18005377c  call    cs:__imp_RaiseException
0x180053782  nop
0x180053783  lea     rsi, [r14+20h]
0x180053787  cmp     qword ptr [rsi+18h], 7
0x18005378c  jbe     short loc_180053791
0x18005378e  mov     rsi, [rsi]
0x180053791  mov     [rbp+70h+var_B8], r12
0x180053795  mov     rbx, rdi
0x180053798  inc     rbx
0x18005379b  cmp     [rsi+rbx*2], r12w
0x1800537a0  jnz     short loc_180053798
0x1800537a2  mov     eax, 0FFFFFFFFh
0x1800537a7  cmp     rbx, rax
0x1800537aa  ja      loc_18005394A
0x1800537b0  mov     r12, [rbp+70h+var_98]
0x1800537b4  mov     ecx, ebx; unsigned int
0x1800537b6  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800537bb  lea     edx, [rax-1]
0x1800537be  cmp     ebx, eax
0x1800537c0  cmovb   edx, ebx; length
0x1800537c3  lea     r9, [rbp+70h+var_B8]; string
0x1800537c7  lea     r8, [rbp+70h+var_D0]; hstringHeader
0x1800537cb  mov     rcx, rsi; sourceString
0x1800537ce  call    cs:__imp_WindowsCreateStringReference
0x1800537d4  xor     esi, esi
0x1800537d6  test    eax, eax
0x1800537d8  jns     short loc_1800537EC
0x1800537da  xor     r9d, r9d; lpArguments
0x1800537dd  xor     r8d, r8d; nNumberOfArguments
0x1800537e0  lea     edx, [rsi+1]; dwExceptionFlags
0x1800537e3  mov     ecx, eax; dwExceptionCode
0x1800537e5  call    cs:__imp_RaiseException
0x1800537eb  nop
0x1800537ec  cmp     qword ptr [r14+18h], 7
0x1800537f1  jbe     short loc_1800537F6
0x1800537f3  mov     r14, [r14]
0x1800537f6  mov     [rbp+70h+var_D8], rsi
0x1800537fa  inc     rdi
0x1800537fd  cmp     [r14+rdi*2], si
0x180053802  jnz     short loc_1800537FA
0x180053804  mov     eax, 0FFFFFFFFh
0x180053809  cmp     rdi, rax
0x18005380c  ja      loc_180053934
0x180053812  mov     rbx, [rbp+70h+var_B8]
0x180053816  mov     ecx, edi; unsigned int
0x180053818  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005381d  lea     edx, [rax-1]
0x180053820  cmp     edi, eax
0x180053822  cmovb   edx, edi; length
0x180053825  lea     r9, [rbp+70h+var_D8]; string
0x180053829  lea     r8, [rbp+70h+var_F0]; hstringHeader
0x18005382d  mov     rcx, r14; sourceString
0x180053830  call    cs:__imp_WindowsCreateStringReference
0x180053836  test    eax, eax
0x180053838  jns     short loc_18005384D
0x18005383a  xor     r9d, r9d; lpArguments
0x18005383d  xor     r8d, r8d; nNumberOfArguments
0x180053840  lea     edx, [r9+1]; dwExceptionFlags
0x180053844  mov     ecx, eax; dwExceptionCode
0x180053846  call    cs:__imp_RaiseException
0x18005384c  nop
0x18005384d  mov     rax, [r13+18h]
0x180053851  test    rax, rax
0x180053854  jz      short loc_18005385B
0x180053856  mov     r8, [rax]
0x180053859  jmp     short loc_18005385E
0x18005385b  mov     r8, rsi
0x18005385e  lea     rax, [rsp+170h+var_120]
0x180053863  mov     [rsp+170h+var_130], rax
0x180053868  mov     rax, [rsp+170h+var_100]
0x18005386d  mov     [rsp+170h+var_138], rax
0x180053872  mov     eax, [rsp+170h+var_118]
0x180053876  mov     [rsp+170h+var_140], eax
0x18005387a  mov     [rsp+170h+var_148], r12
0x18005387f  mov     qword ptr [rsp+170h+var_150], rbx; int
0x180053884  mov     r9, [rbp+70h+var_D8]
0x180053888  mov     edx, [r13+10h]
0x18005388c  mov     rcx, [rsp+170h+var_F8]
0x180053891  mov     rax, [rsp+170h+var_110]
0x180053896  mov     rax, [rax+48h]
0x18005389a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005389f  mov     rcx, [rbp+78h]; this
0x1800538a3  test    eax, eax
0x1800538a5  jns     short loc_1800538BC
0x1800538a7  mov     r9d, eax; char *
0x1800538aa  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800538b1  mov     edx, 588h; void *
0x1800538b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800538bc  mov     [rbp+70h+var_D8], rsi
0x1800538c0  mov     [rbp+70h+var_B8], rsi
0x1800538c4  mov     [rbp+70h+var_98], rsi
0x1800538c8  mov     [rbp+70h+string], rsi
0x1800538cc  mov     rdx, [rbp+70h+var_58]
0x1800538d0  cmp     rdx, 7
0x1800538d4  jbe     short loc_1800538E7
0x1800538d6  lea     rdx, ds:2[rdx*2]
0x1800538de  mov     rcx, [rbp+70h+var_70]
0x1800538e2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800538e7  mov     r8d, [rsp+170h+var_114]
0x1800538ec  mov     rdx, [rsp+170h+var_120]
0x1800538f1  mov     rcx, r15
0x1800538f4  call    ??$unmarshal@URoamedTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@URoamedTilePropertiesMap@UnifiedTile@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z; wil::cloud_store::unmarshal<Windows::Data::UnifiedTile::RoamedTilePropertiesMap>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)
0x1800538f9  nop
0x1800538fa  mov     rcx, [rsp+170h+var_120]
0x1800538ff  test    rcx, rcx
0x180053902  jz      short loc_180053911
0x180053904  mov     rdx, [rcx]
0x180053907  mov     rax, [rdx+10h]
0x18005390b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053910  nop
0x180053911  mov     rax, r15
0x180053914  mov     rcx, [rbp+70h+var_50]
0x180053918  xor     rcx, rsp; StackCookie
0x18005391b  call    __security_check_cookie
0x180053920  add     rsp, 138h
0x180053927  pop     r15
0x180053929  pop     r14
0x18005392b  pop     r13
0x18005392d  pop     r12
0x18005392f  pop     rdi
0x180053930  pop     rsi
0x180053931  pop     rbx
0x180053932  pop     rbp
0x180053933  retn
0x180053934  xor     r9d, r9d; lpArguments
0x180053937  xor     r8d, r8d; nNumberOfArguments
0x18005393a  lea     edx, [r9+1]; dwExceptionFlags
0x18005393e  mov     ecx, 80070216h; dwExceptionCode
0x180053943  call    cs:__imp_RaiseException
0x180053949  nop
0x18005394a  xor     r9d, r9d; lpArguments
0x18005394d  xor     r8d, r8d; nNumberOfArguments
0x180053950  lea     edx, [r9+1]; dwExceptionFlags
0x180053954  mov     ecx, 80070216h; dwExceptionCode
0x180053959  call    cs:__imp_RaiseException
0x18005395f  nop
0x180053960  xor     r9d, r9d; lpArguments
0x180053963  xor     r8d, r8d; nNumberOfArguments
0x180053966  lea     edx, [r9+1]; dwExceptionFlags
0x18005396a  mov     ecx, 80070216h; dwExceptionCode
0x18005396f  call    cs:__imp_RaiseException
0x180053975  nop
0x180053976  xor     r9d, r9d; lpArguments
0x180053979  xor     r8d, r8d; nNumberOfArguments
0x18005397c  lea     edx, [r9+1]; dwExceptionFlags
0x180053980  mov     ecx, 80070216h; dwExceptionCode
0x180053985  call    cs:__imp_RaiseException
```
