# wil::cloud_store::call_load<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800575fc`
- end: `0x1800579b4`
- name: `??$call_load@ULocalStartVolatileTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@ULocalStartVolatileTilePropertiesMap@UnifiedTile@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `952`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180056844`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x180056798`
- `0x1800574a8`
- `0x1800575fc`
- `0x1800579bc`
- `0x180057f68`
- `0x180147be8`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800578f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057906`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005791c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057932`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005794d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057960`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057973`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057986`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800578f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057906`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005791c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057932`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005794d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057960`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057973`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057986`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800576c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180057737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180057791`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800577e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800576c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180057737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180057791`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800577e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall wil::cloud_store::call_load<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap>(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 v9; // rax
  WCHAR *v10; // rsi
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rbx
  unsigned int v13; // eax
  UINT32 v14; // edx
  HRESULT v15; // eax
  unsigned int v16; // eax
  UINT32 v17; // edx
  HRESULT v18; // eax
  unsigned int v19; // eax
  UINT32 v20; // edx
  HRESULT v21; // eax
  unsigned int v22; // eax
  UINT32 v23; // edx
  HRESULT v24; // eax
  WCHAR **v25; // rax
  WCHAR *v26; // r8
  int v27; // eax
  wil::details::in1diag3 *v28; // rcx
  int v30; // [rsp+20h] [rbp-E0h]
  __int64 v32; // [rsp+60h] [rbp-A0h]
  __int64 *v33; // [rsp+78h] [rbp-88h]
  HSTRING_HEADER v34; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v35; // [rsp+98h] [rbp-68h] BYREF
  HSTRING_HEADER v36; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING v37; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v38; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v39; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING string; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v42[3]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v43; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v33 = *(__int64 **)wil::details::shared_cloud_store_state::get_cloud_store(*(_QWORD *)a1);
  v32 = *v33;
  v9 = wil::cloud_store::widen_string(v42, a5);
  v10 = (WCHAR *)v9;
  if ( *(_QWORD *)(v9 + 24) > 7u )
    v10 = *(WCHAR **)v9;
  string = 0;
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( v10[v12] );
  if ( v12 > 0xFFFFFFFF )
    goto LABEL_42;
  v13 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v12);
  v14 = v13 - 1;
  if ( (unsigned int)v12 < v13 )
    v14 = v12;
  v15 = WindowsCreateStringReference(v10, v14, &hstringHeader, &string);
  if ( v15 < 0 )
  {
    RaiseException(v15, 1u, 0, 0);
LABEL_45:
    RaiseException(v18, 1u, 0, 0);
    goto LABEL_46;
  }
  wil::cloud_store::convert_cloud_store_load_options(a4);
  v10 = (WCHAR *)(a3 + 8);
  if ( (unsigned __int64)a3[11] > 7 )
    v10 = *(WCHAR **)v10;
  v39 = 0;
  v12 = -1;
  do
    ++v12;
  while ( v10[v12] );
  if ( v12 > 0xFFFFFFFF )
    goto LABEL_41;
  v16 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v12);
  v17 = v16 - 1;
  if ( (unsigned int)v12 < v16 )
    v17 = v12;
  v18 = WindowsCreateStringReference(v10, v17, &v38, &v39);
  if ( v18 < 0 )
    goto LABEL_45;
  v10 = (WCHAR *)(a3 + 4);
  if ( (unsigned __int64)a3[7] > 7 )
    v10 = *(WCHAR **)v10;
  v37 = 0;
  v12 = -1;
  do
    ++v12;
  while ( v10[v12] );
  if ( v12 > 0xFFFFFFFF )
    goto LABEL_40;
  v19 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v12);
  v20 = v19 - 1;
  if ( (unsigned int)v12 < v19 )
    v20 = v12;
  v21 = WindowsCreateStringReference(v10, v20, &v36, &v37);
  v10 = 0;
  if ( v21 < 0 )
  {
LABEL_46:
    RaiseException(v21, 1u, 0, 0);
LABEL_47:
    RaiseException(v24, 1u, 0, 0);
LABEL_48:
    wil::details::in1diag3::Throw_Hr(
      v28,
      (void *)0x588,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v27,
      v30);
  }
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (__int64 *)*a3;
  v35 = 0;
  do
    ++v11;
  while ( *((_WORD *)a3 + v11) );
  if ( v11 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_40:
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_41:
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_42:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_43;
  }
  LODWORD(v12) = (_DWORD)v37;
  v22 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  v23 = v22 - 1;
  if ( (unsigned int)v11 < v22 )
    v23 = v11;
  v24 = WindowsCreateStringReference((PCWSTR)a3, v23, &v34, &v35);
  if ( v24 < 0 )
    goto LABEL_47;
  v25 = *(WCHAR ***)(a1 + 24);
  if ( v25 )
  {
    v26 = *v25;
    goto LABEL_35;
  }
LABEL_43:
  v26 = v10;
LABEL_35:
  v30 = v12;
  v27 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, WCHAR *, HSTRING))(v32 + 72))(
          v33,
          *(unsigned int *)(a1 + 16),
          v26,
          v35);
  v28 = retaddr;
  if ( v27 < 0 )
    goto LABEL_48;
  v35 = (HSTRING)v10;
  v37 = (HSTRING)v10;
  v39 = (HSTRING)v10;
  string = (HSTRING)v10;
  if ( v43 > 7 )
    std::_Deallocate<16>(v42[0], 2 * v43 + 2);
  wil::cloud_store::unmarshal<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap>(a2, 0, a4);
  return a2;
}

```

## disassembly

```asm
0x1800575fc  push    rbp
0x1800575fe  push    rbx
0x1800575ff  push    rsi
0x180057600  push    rdi
0x180057601  push    r12
0x180057603  push    r13
0x180057605  push    r14
0x180057607  push    r15
0x180057609  lea     rbp, [rsp-38h]
0x18005760e  sub     rsp, 138h
0x180057615  mov     rax, cs:__security_cookie
0x18005761c  xor     rax, rsp
0x18005761f  mov     [rbp+70h+var_50], rax
0x180057623  mov     r12d, r9d
0x180057626  mov     [rsp+170h+var_114], r9d
0x18005762b  mov     r14, r8
0x18005762e  mov     r15, rdx
0x180057631  mov     r13, rcx
0x180057634  mov     [rsp+170h+var_110], rdx
0x180057639  mov     rbx, [rbp+70h+arg_20]
0x180057640  xor     edi, edi
0x180057642  mov     [rsp+170h+var_120], rdi
0x180057647  mov     rcx, [rcx]
0x18005764a  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x18005764f  mov     rax, [rax]
0x180057652  mov     [rsp+170h+var_F8], rax
0x180057657  mov     rax, [rax]
0x18005765a  mov     [rsp+170h+var_110], rax
0x18005765f  mov     rcx, [rsp+170h+var_120]
0x180057664  mov     [rsp+170h+var_120], rdi
0x180057669  test    rcx, rcx
0x18005766c  jnz     loc_1800579A2
0x180057672  mov     rdx, rbx
0x180057675  lea     rcx, [rbp+70h+var_70]
0x180057679  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x18005767e  mov     rsi, rax
0x180057681  cmp     qword ptr [rax+18h], 7
0x180057686  jbe     short loc_18005768B
0x180057688  mov     rsi, [rax]
0x18005768b  mov     [rbp+70h+string], rdi
0x18005768f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180057693  mov     rbx, rdi
0x180057696  xor     eax, eax
0x180057698  inc     rbx
0x18005769b  cmp     [rsi+rbx*2], ax
0x18005769f  jnz     short loc_180057698
0x1800576a1  mov     eax, 0FFFFFFFFh
0x1800576a6  cmp     rbx, rax
0x1800576a9  ja      loc_180057923
0x1800576af  mov     ecx, ebx; unsigned int
0x1800576b1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800576b6  lea     edx, [rax-1]
0x1800576b9  cmp     ebx, eax
0x1800576bb  cmovb   edx, ebx; length
0x1800576be  lea     r9, [rbp+70h+string]; string
0x1800576c2  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x1800576c6  mov     rcx, rsi; sourceString
0x1800576c9  call    cs:__imp_WindowsCreateStringReference
0x1800576cf  test    eax, eax
0x1800576d1  js      loc_180057941
0x1800576d7  mov     rax, [rbp+70h+string]
0x1800576db  mov     [rsp+170h+var_100], rax
0x1800576e0  mov     ecx, r12d
0x1800576e3  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x1800576e8  mov     [rsp+170h+var_118], eax
0x1800576ec  lea     rsi, [r14+40h]
0x1800576f0  cmp     qword ptr [rsi+18h], 7
0x1800576f5  ja      loc_1800578C9
0x1800576fb  xor     r12d, r12d
0x1800576fe  mov     [rbp+70h+var_98], r12
0x180057702  mov     rbx, rdi
0x180057705  inc     rbx
0x180057708  cmp     [rsi+rbx*2], r12w
0x18005770d  jnz     short loc_180057705
0x18005770f  mov     eax, 0FFFFFFFFh
0x180057714  cmp     rbx, rax
0x180057717  ja      loc_18005790D
0x18005771d  mov     ecx, ebx; unsigned int
0x18005771f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180057724  lea     edx, [rax-1]
0x180057727  cmp     ebx, eax
0x180057729  cmovb   edx, ebx; length
0x18005772c  lea     r9, [rbp+70h+var_98]; string
0x180057730  lea     r8, [rbp+70h+var_B0]; hstringHeader
0x180057734  mov     rcx, rsi; sourceString
0x180057737  call    cs:__imp_WindowsCreateStringReference
0x18005773d  test    eax, eax
0x18005773f  js      loc_180057954
0x180057745  lea     rsi, [r14+20h]
0x180057749  cmp     qword ptr [rsi+18h], 7
0x18005774e  ja      loc_1800578D1
0x180057754  mov     [rbp+70h+var_B8], r12
0x180057758  mov     rbx, rdi
0x18005775b  inc     rbx
0x18005775e  cmp     [rsi+rbx*2], r12w
0x180057763  jnz     short loc_18005775B
0x180057765  mov     eax, 0FFFFFFFFh
0x18005776a  cmp     rbx, rax
0x18005776d  ja      loc_1800578F7
0x180057773  mov     r12, [rbp+70h+var_98]
0x180057777  mov     ecx, ebx; unsigned int
0x180057779  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005777e  lea     edx, [rax-1]
0x180057781  cmp     ebx, eax
0x180057783  cmovb   edx, ebx; length
0x180057786  lea     r9, [rbp+70h+var_B8]; string
0x18005778a  lea     r8, [rbp+70h+var_D0]; hstringHeader
0x18005778e  mov     rcx, rsi; sourceString
0x180057791  call    cs:__imp_WindowsCreateStringReference
0x180057797  xor     esi, esi
0x180057799  test    eax, eax
0x18005779b  js      loc_180057967
0x1800577a1  cmp     qword ptr [r14+18h], 7
0x1800577a6  ja      loc_1800578D9
0x1800577ac  mov     [rbp+70h+var_D8], rsi
0x1800577b0  inc     rdi
0x1800577b3  cmp     [r14+rdi*2], si
0x1800577b8  jnz     short loc_1800577B0
0x1800577ba  mov     eax, 0FFFFFFFFh
0x1800577bf  cmp     rdi, rax
0x1800577c2  ja      loc_1800578E1
0x1800577c8  mov     rbx, [rbp+70h+var_B8]
0x1800577cc  mov     ecx, edi; unsigned int
0x1800577ce  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800577d3  lea     edx, [rax-1]
0x1800577d6  cmp     edi, eax
0x1800577d8  cmovb   edx, edi; length
0x1800577db  lea     r9, [rbp+70h+var_D8]; string
0x1800577df  lea     r8, [rbp+70h+var_F0]; hstringHeader
0x1800577e3  mov     rcx, r14; sourceString
0x1800577e6  call    cs:__imp_WindowsCreateStringReference
0x1800577ec  test    eax, eax
0x1800577ee  js      loc_18005797A
0x1800577f4  mov     rax, [r13+18h]
0x1800577f8  test    rax, rax
0x1800577fb  jz      loc_180057939
0x180057801  mov     r8, [rax]
0x180057804  lea     rax, [rsp+170h+var_120]
0x180057809  mov     [rsp+170h+var_130], rax
0x18005780e  mov     rax, [rsp+170h+var_100]
0x180057813  mov     [rsp+170h+var_138], rax
0x180057818  mov     eax, [rsp+170h+var_118]
0x18005781c  mov     [rsp+170h+var_140], eax
0x180057820  mov     [rsp+170h+var_148], r12
0x180057825  mov     [rsp+170h+var_150], rbx
0x18005782a  mov     r9, [rbp+70h+var_D8]
0x18005782e  mov     edx, [r13+10h]
0x180057832  mov     rcx, [rsp+170h+var_F8]
0x180057837  mov     rax, [rsp+170h+var_110]
0x18005783c  mov     rax, [rax+48h]
0x180057840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057845  mov     rcx, [rbp+78h]
0x180057849  test    eax, eax
0x18005784b  js      loc_18005798D
0x180057851  mov     [rbp+70h+var_D8], rsi
0x180057855  mov     [rbp+70h+var_B8], rsi
0x180057859  mov     [rbp+70h+var_98], rsi
0x18005785d  mov     [rbp+70h+string], rsi
0x180057861  mov     rdx, [rbp+70h+var_58]
0x180057865  cmp     rdx, 7
0x180057869  jbe     short loc_18005787C
0x18005786b  lea     rdx, ds:2[rdx*2]
0x180057873  mov     rcx, [rbp+70h+var_70]
0x180057877  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005787c  mov     r8d, [rsp+170h+var_114]
0x180057881  mov     rdx, [rsp+170h+var_120]
0x180057886  mov     rcx, r15
0x180057889  call    ??$unmarshal@ULocalStartVolatileTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@ULocalStartVolatileTilePropertiesMap@UnifiedTile@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z; wil::cloud_store::unmarshal<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)
0x18005788e  nop
0x18005788f  mov     rcx, [rsp+170h+var_120]
0x180057894  test    rcx, rcx
0x180057897  jz      short loc_1800578A6
0x180057899  mov     rdx, [rcx]
0x18005789c  mov     rax, [rdx+10h]
0x1800578a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578a5  nop
0x1800578a6  mov     rax, r15
0x1800578a9  mov     rcx, [rbp+70h+var_50]
0x1800578ad  xor     rcx, rsp; StackCookie
0x1800578b0  call    __security_check_cookie
0x1800578b5  add     rsp, 138h
0x1800578bc  pop     r15
0x1800578be  pop     r14
0x1800578c0  pop     r13
0x1800578c2  pop     r12
0x1800578c4  pop     rdi
0x1800578c5  pop     rsi
0x1800578c6  pop     rbx
0x1800578c7  pop     rbp
0x1800578c8  retn
0x1800578c9  mov     rsi, [rsi]
0x1800578cc  jmp     loc_1800576FB
0x1800578d1  mov     rsi, [rsi]
0x1800578d4  jmp     loc_180057754
0x1800578d9  mov     r14, [r14]
0x1800578dc  jmp     loc_1800577AC
0x1800578e1  xor     r9d, r9d; lpArguments
0x1800578e4  xor     r8d, r8d; nNumberOfArguments
0x1800578e7  lea     edx, [r9+1]; dwExceptionFlags
0x1800578eb  mov     ecx, 80070216h; dwExceptionCode
0x1800578f0  call    cs:__imp_RaiseException
0x1800578f6  nop
0x1800578f7  xor     r9d, r9d; lpArguments
0x1800578fa  xor     r8d, r8d; nNumberOfArguments
0x1800578fd  lea     edx, [r9+1]; dwExceptionFlags
0x180057901  mov     ecx, 80070216h; dwExceptionCode
0x180057906  call    cs:__imp_RaiseException
0x18005790c  nop
0x18005790d  xor     r9d, r9d; lpArguments
0x180057910  xor     r8d, r8d; nNumberOfArguments
0x180057913  lea     edx, [r9+1]; dwExceptionFlags
0x180057917  mov     ecx, 80070216h; dwExceptionCode
0x18005791c  call    cs:__imp_RaiseException
0x180057922  nop
0x180057923  xor     r9d, r9d; lpArguments
0x180057926  xor     r8d, r8d; nNumberOfArguments
0x180057929  lea     edx, [r9+1]; dwExceptionFlags
0x18005792d  mov     ecx, 80070216h; dwExceptionCode
0x180057932  call    cs:__imp_RaiseException
0x180057938  nop
0x180057939  mov     r8, rsi
0x18005793c  jmp     loc_180057804
0x180057941  xor     r9d, r9d; lpArguments
0x180057944  xor     r8d, r8d; nNumberOfArguments
0x180057947  lea     edx, [r9+1]; dwExceptionFlags
0x18005794b  mov     ecx, eax; dwExceptionCode
0x18005794d  call    cs:__imp_RaiseException
0x180057953  nop
0x180057954  xor     r9d, r9d; lpArguments
0x180057957  xor     r8d, r8d; nNumberOfArguments
0x18005795a  lea     edx, [r9+1]; dwExceptionFlags
0x18005795e  mov     ecx, eax; dwExceptionCode
0x180057960  call    cs:__imp_RaiseException
0x180057966  nop
0x180057967  xor     r9d, r9d; lpArguments
0x18005796a  xor     r8d, r8d; nNumberOfArguments
0x18005796d  lea     edx, [r9+1]; dwExceptionFlags
0x180057971  mov     ecx, eax; dwExceptionCode
0x180057973  call    cs:__imp_RaiseException
0x180057979  nop
0x18005797a  xor     r9d, r9d; lpArguments
0x18005797d  xor     r8d, r8d; nNumberOfArguments
0x180057980  lea     edx, [r9+1]; dwExceptionFlags
0x180057984  mov     ecx, eax; dwExceptionCode
0x180057986  call    cs:__imp_RaiseException
0x18005798c  nop
0x18005798d  mov     r9d, eax; char *
0x180057990  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180057997  mov     edx, 588h; void *
0x18005799c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800579a2  mov     rax, [rcx]
0x1800579a5  mov     rax, [rax+10h]
0x1800579a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800579ae  jmp     loc_180057672
```
