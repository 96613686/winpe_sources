# wil::cloud_store::call_load<Windows::Data::UnifiedTile::StartGlobalProperties>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180084004`
- end: `0x18008437c`
- name: `??$call_load@UStartGlobalProperties@UnifiedTile@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@UStartGlobalProperties@UnifiedTile@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `888`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180083f5c`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x180056798`
- `0x1800574a8`
- `0x1800579bc`
- `0x180084004`
- `0x180084384`
- `0x180147be8`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800840f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008416c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800841d5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180084236`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180084333`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180084349`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008435f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180084375`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800840f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008416c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800841d5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180084236`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180084333`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180084349`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008435f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180084375`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800840da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180084156`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800841be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180084220`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800840da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180084156`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800841be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180084220`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::call_load<Windows::Data::UnifiedTile::StartGlobalProperties>(
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
    JUMPOUT(0x18008437BLL);
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
  wil::cloud_store::unmarshal<Windows::Data::UnifiedTile::StartGlobalProperties>(a2, 0, a4);
  return a2;
}

```

## disassembly

```asm
0x180084004  push    rbp
0x180084006  push    rbx
0x180084007  push    rsi
0x180084008  push    rdi
0x180084009  push    r12
0x18008400b  push    r13
0x18008400d  push    r14
0x18008400f  push    r15
0x180084011  lea     rbp, [rsp-38h]
0x180084016  sub     rsp, 138h
0x18008401d  mov     rax, cs:__security_cookie
0x180084024  xor     rax, rsp
0x180084027  mov     [rbp+70h+var_50], rax
0x18008402b  mov     r12d, r9d
0x18008402e  mov     [rsp+170h+var_114], r9d
0x180084033  mov     r14, r8
0x180084036  mov     r15, rdx
0x180084039  mov     r13, rcx
0x18008403c  mov     [rsp+170h+var_110], rdx
0x180084041  mov     rbx, [rbp+70h+arg_20]
0x180084048  xor     edi, edi
0x18008404a  mov     [rsp+170h+var_120], rdi
0x18008404f  mov     rcx, [rcx]
0x180084052  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180084057  mov     rax, [rax]
0x18008405a  mov     [rsp+170h+var_F8], rax
0x18008405f  mov     rax, [rax]
0x180084062  mov     [rsp+170h+var_110], rax
0x180084067  mov     rcx, [rsp+170h+var_120]
0x18008406c  mov     [rsp+170h+var_120], rdi
0x180084071  test    rcx, rcx
0x180084074  jz      short loc_180084083
0x180084076  mov     rax, [rcx]
0x180084079  mov     rax, [rax+10h]
0x18008407d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084082  nop
0x180084083  mov     rdx, rbx
0x180084086  lea     rcx, [rbp+70h+var_70]
0x18008408a  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x18008408f  mov     rsi, rax
0x180084092  cmp     qword ptr [rax+18h], 7
0x180084097  jbe     short loc_18008409C
0x180084099  mov     rsi, [rax]
0x18008409c  mov     [rbp+70h+string], rdi
0x1800840a0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800840a4  mov     rbx, rdi
0x1800840a7  xor     eax, eax
0x1800840a9  inc     rbx
0x1800840ac  cmp     [rsi+rbx*2], ax
0x1800840b0  jnz     short loc_1800840A9
0x1800840b2  mov     eax, 0FFFFFFFFh
0x1800840b7  cmp     rbx, rax
0x1800840ba  ja      loc_180084366
0x1800840c0  mov     ecx, ebx; unsigned int
0x1800840c2  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800840c7  lea     edx, [rax-1]
0x1800840ca  cmp     ebx, eax
0x1800840cc  cmovb   edx, ebx; length
0x1800840cf  lea     r9, [rbp+70h+string]; string
0x1800840d3  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x1800840d7  mov     rcx, rsi; sourceString
0x1800840da  call    cs:__imp_WindowsCreateStringReference
0x1800840e0  test    eax, eax
0x1800840e2  jns     short loc_1800840F7
0x1800840e4  xor     r9d, r9d; lpArguments
0x1800840e7  xor     r8d, r8d; nNumberOfArguments
0x1800840ea  lea     edx, [r9+1]; dwExceptionFlags
0x1800840ee  mov     ecx, eax; dwExceptionCode
0x1800840f0  call    cs:__imp_RaiseException
0x1800840f6  nop
0x1800840f7  mov     rax, [rbp+70h+string]
0x1800840fb  mov     [rsp+170h+var_100], rax
0x180084100  mov     ecx, r12d
0x180084103  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x180084108  mov     [rsp+170h+var_118], eax
0x18008410c  lea     rsi, [r14+40h]
0x180084110  cmp     qword ptr [rsi+18h], 7
0x180084115  jbe     short loc_18008411A
0x180084117  mov     rsi, [rsi]
0x18008411a  xor     r12d, r12d
0x18008411d  mov     [rbp+70h+var_98], r12
0x180084121  mov     rbx, rdi
0x180084124  inc     rbx
0x180084127  cmp     [rsi+rbx*2], r12w
0x18008412c  jnz     short loc_180084124
0x18008412e  mov     eax, 0FFFFFFFFh
0x180084133  cmp     rbx, rax
0x180084136  ja      loc_180084350
0x18008413c  mov     ecx, ebx; unsigned int
0x18008413e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180084143  lea     edx, [rax-1]
0x180084146  cmp     ebx, eax
0x180084148  cmovb   edx, ebx; length
0x18008414b  lea     r9, [rbp+70h+var_98]; string
0x18008414f  lea     r8, [rbp+70h+var_B0]; hstringHeader
0x180084153  mov     rcx, rsi; sourceString
0x180084156  call    cs:__imp_WindowsCreateStringReference
0x18008415c  test    eax, eax
0x18008415e  jns     short loc_180084173
0x180084160  xor     r9d, r9d; lpArguments
0x180084163  xor     r8d, r8d; nNumberOfArguments
0x180084166  lea     edx, [r9+1]; dwExceptionFlags
0x18008416a  mov     ecx, eax; dwExceptionCode
0x18008416c  call    cs:__imp_RaiseException
0x180084172  nop
0x180084173  lea     rsi, [r14+20h]
0x180084177  cmp     qword ptr [rsi+18h], 7
0x18008417c  jbe     short loc_180084181
0x18008417e  mov     rsi, [rsi]
0x180084181  mov     [rbp+70h+var_B8], r12
0x180084185  mov     rbx, rdi
0x180084188  inc     rbx
0x18008418b  cmp     [rsi+rbx*2], r12w
0x180084190  jnz     short loc_180084188
0x180084192  mov     eax, 0FFFFFFFFh
0x180084197  cmp     rbx, rax
0x18008419a  ja      loc_18008433A
0x1800841a0  mov     r12, [rbp+70h+var_98]
0x1800841a4  mov     ecx, ebx; unsigned int
0x1800841a6  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800841ab  lea     edx, [rax-1]
0x1800841ae  cmp     ebx, eax
0x1800841b0  cmovb   edx, ebx; length
0x1800841b3  lea     r9, [rbp+70h+var_B8]; string
0x1800841b7  lea     r8, [rbp+70h+var_D0]; hstringHeader
0x1800841bb  mov     rcx, rsi; sourceString
0x1800841be  call    cs:__imp_WindowsCreateStringReference
0x1800841c4  xor     esi, esi
0x1800841c6  test    eax, eax
0x1800841c8  jns     short loc_1800841DC
0x1800841ca  xor     r9d, r9d; lpArguments
0x1800841cd  xor     r8d, r8d; nNumberOfArguments
0x1800841d0  lea     edx, [rsi+1]; dwExceptionFlags
0x1800841d3  mov     ecx, eax; dwExceptionCode
0x1800841d5  call    cs:__imp_RaiseException
0x1800841db  nop
0x1800841dc  cmp     qword ptr [r14+18h], 7
0x1800841e1  jbe     short loc_1800841E6
0x1800841e3  mov     r14, [r14]
0x1800841e6  mov     [rbp+70h+var_D8], rsi
0x1800841ea  inc     rdi
0x1800841ed  cmp     [r14+rdi*2], si
0x1800841f2  jnz     short loc_1800841EA
0x1800841f4  mov     eax, 0FFFFFFFFh
0x1800841f9  cmp     rdi, rax
0x1800841fc  ja      loc_180084324
0x180084202  mov     rbx, [rbp+70h+var_B8]
0x180084206  mov     ecx, edi; unsigned int
0x180084208  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18008420d  lea     edx, [rax-1]
0x180084210  cmp     edi, eax
0x180084212  cmovb   edx, edi; length
0x180084215  lea     r9, [rbp+70h+var_D8]; string
0x180084219  lea     r8, [rbp+70h+var_F0]; hstringHeader
0x18008421d  mov     rcx, r14; sourceString
0x180084220  call    cs:__imp_WindowsCreateStringReference
0x180084226  test    eax, eax
0x180084228  jns     short loc_18008423D
0x18008422a  xor     r9d, r9d; lpArguments
0x18008422d  xor     r8d, r8d; nNumberOfArguments
0x180084230  lea     edx, [r9+1]; dwExceptionFlags
0x180084234  mov     ecx, eax; dwExceptionCode
0x180084236  call    cs:__imp_RaiseException
0x18008423c  nop
0x18008423d  mov     rax, [r13+18h]
0x180084241  test    rax, rax
0x180084244  jz      short loc_18008424B
0x180084246  mov     r8, [rax]
0x180084249  jmp     short loc_18008424E
0x18008424b  mov     r8, rsi
0x18008424e  lea     rax, [rsp+170h+var_120]
0x180084253  mov     [rsp+170h+var_130], rax
0x180084258  mov     rax, [rsp+170h+var_100]
0x18008425d  mov     [rsp+170h+var_138], rax
0x180084262  mov     eax, [rsp+170h+var_118]
0x180084266  mov     [rsp+170h+var_140], eax
0x18008426a  mov     [rsp+170h+var_148], r12
0x18008426f  mov     qword ptr [rsp+170h+var_150], rbx; int
0x180084274  mov     r9, [rbp+70h+var_D8]
0x180084278  mov     edx, [r13+10h]
0x18008427c  mov     rcx, [rsp+170h+var_F8]
0x180084281  mov     rax, [rsp+170h+var_110]
0x180084286  mov     rax, [rax+48h]
0x18008428a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008428f  mov     rcx, [rbp+78h]; this
0x180084293  test    eax, eax
0x180084295  jns     short loc_1800842AC
0x180084297  mov     r9d, eax; char *
0x18008429a  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800842a1  mov     edx, 588h; void *
0x1800842a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800842ac  mov     [rbp+70h+var_D8], rsi
0x1800842b0  mov     [rbp+70h+var_B8], rsi
0x1800842b4  mov     [rbp+70h+var_98], rsi
0x1800842b8  mov     [rbp+70h+string], rsi
0x1800842bc  mov     rdx, [rbp+70h+var_58]
0x1800842c0  cmp     rdx, 7
0x1800842c4  jbe     short loc_1800842D7
0x1800842c6  lea     rdx, ds:2[rdx*2]
0x1800842ce  mov     rcx, [rbp+70h+var_70]
0x1800842d2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800842d7  mov     r8d, [rsp+170h+var_114]
0x1800842dc  mov     rdx, [rsp+170h+var_120]
0x1800842e1  mov     rcx, r15
0x1800842e4  call    ??$unmarshal@UStartGlobalProperties@UnifiedTile@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@UStartGlobalProperties@UnifiedTile@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z; wil::cloud_store::unmarshal<Windows::Data::UnifiedTile::StartGlobalProperties>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)
0x1800842e9  nop
0x1800842ea  mov     rcx, [rsp+170h+var_120]
0x1800842ef  test    rcx, rcx
0x1800842f2  jz      short loc_180084301
0x1800842f4  mov     rdx, [rcx]
0x1800842f7  mov     rax, [rdx+10h]
0x1800842fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084300  nop
0x180084301  mov     rax, r15
0x180084304  mov     rcx, [rbp+70h+var_50]
0x180084308  xor     rcx, rsp; StackCookie
0x18008430b  call    __security_check_cookie
0x180084310  add     rsp, 138h
0x180084317  pop     r15
0x180084319  pop     r14
0x18008431b  pop     r13
0x18008431d  pop     r12
0x18008431f  pop     rdi
0x180084320  pop     rsi
0x180084321  pop     rbx
0x180084322  pop     rbp
0x180084323  retn
0x180084324  xor     r9d, r9d; lpArguments
0x180084327  xor     r8d, r8d; nNumberOfArguments
0x18008432a  lea     edx, [r9+1]; dwExceptionFlags
0x18008432e  mov     ecx, 80070216h; dwExceptionCode
0x180084333  call    cs:__imp_RaiseException
0x180084339  nop
0x18008433a  xor     r9d, r9d; lpArguments
0x18008433d  xor     r8d, r8d; nNumberOfArguments
0x180084340  lea     edx, [r9+1]; dwExceptionFlags
0x180084344  mov     ecx, 80070216h; dwExceptionCode
0x180084349  call    cs:__imp_RaiseException
0x18008434f  nop
0x180084350  xor     r9d, r9d; lpArguments
0x180084353  xor     r8d, r8d; nNumberOfArguments
0x180084356  lea     edx, [r9+1]; dwExceptionFlags
0x18008435a  mov     ecx, 80070216h; dwExceptionCode
0x18008435f  call    cs:__imp_RaiseException
0x180084365  nop
0x180084366  xor     r9d, r9d; lpArguments
0x180084369  xor     r8d, r8d; nNumberOfArguments
0x18008436c  lea     edx, [r9+1]; dwExceptionFlags
0x180084370  mov     ecx, 80070216h; dwExceptionCode
0x180084375  call    cs:__imp_RaiseException
```
