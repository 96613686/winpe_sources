# wil::cloud_store::call_load<Windows::Data::UnifiedTile::LocalStartGlobalProperties>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1801037ec`
- end: `0x180103ba6`
- name: `??$call_load@ULocalStartGlobalProperties@UnifiedTile@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@ULocalStartGlobalProperties@UnifiedTile@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `954`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180103744`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x180056798`
- `0x1800574a8`
- `0x1800579bc`
- `0x1801037ec`
- `0x180103bac`
- `0x180147be8`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103ae2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103af8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103b0e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103b24`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103b3f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103b52`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103b65`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103b78`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103ae2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103af8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103b0e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103b24`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103b3f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103b52`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103b65`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180103b78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801038b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180103927`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180103981`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801039d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801038b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180103927`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180103981`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801039d6`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::call_load<Windows::Data::UnifiedTile::LocalStartGlobalProperties>(
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
  wil::cloud_store::unmarshal<Windows::Data::UnifiedTile::LocalStartGlobalProperties>(a2, 0, a4);
  return a2;
}

```

## disassembly

```asm
0x1801037ec  push    rbp
0x1801037ee  push    rbx
0x1801037ef  push    rsi
0x1801037f0  push    rdi
0x1801037f1  push    r12
0x1801037f3  push    r13
0x1801037f5  push    r14
0x1801037f7  push    r15
0x1801037f9  lea     rbp, [rsp-38h]
0x1801037fe  sub     rsp, 138h
0x180103805  mov     rax, cs:__security_cookie
0x18010380c  xor     rax, rsp
0x18010380f  mov     [rbp+70h+var_50], rax
0x180103813  mov     r12d, r9d
0x180103816  mov     [rsp+170h+var_114], r9d
0x18010381b  mov     r14, r8
0x18010381e  mov     r15, rdx
0x180103821  mov     r13, rcx
0x180103824  mov     [rsp+170h+var_110], rdx
0x180103829  mov     rbx, [rbp+70h+arg_20]
0x180103830  xor     edi, edi
0x180103832  mov     [rsp+170h+var_120], rdi
0x180103837  mov     rcx, [rcx]
0x18010383a  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x18010383f  mov     rax, [rax]
0x180103842  mov     [rsp+170h+var_F8], rax
0x180103847  mov     rax, [rax]
0x18010384a  mov     [rsp+170h+var_110], rax
0x18010384f  mov     rcx, [rsp+170h+var_120]
0x180103854  mov     [rsp+170h+var_120], rdi
0x180103859  test    rcx, rcx
0x18010385c  jnz     loc_180103B94
0x180103862  mov     rdx, rbx
0x180103865  lea     rcx, [rbp+70h+var_70]
0x180103869  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x18010386e  mov     rsi, rax
0x180103871  cmp     qword ptr [rax+18h], 7
0x180103876  jbe     short loc_18010387B
0x180103878  mov     rsi, [rax]
0x18010387b  mov     [rbp+70h+string], rdi
0x18010387f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180103883  mov     rbx, rdi
0x180103886  xor     eax, eax
0x180103888  inc     rbx
0x18010388b  cmp     [rsi+rbx*2], ax
0x18010388f  jnz     short loc_180103888
0x180103891  mov     eax, 0FFFFFFFFh
0x180103896  cmp     rbx, rax
0x180103899  ja      loc_180103B15
0x18010389f  mov     ecx, ebx; unsigned int
0x1801038a1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1801038a6  lea     edx, [rax-1]
0x1801038a9  cmp     ebx, eax
0x1801038ab  cmovb   edx, ebx; length
0x1801038ae  lea     r9, [rbp+70h+string]; string
0x1801038b2  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x1801038b6  mov     rcx, rsi; sourceString
0x1801038b9  call    cs:__imp_WindowsCreateStringReference
0x1801038bf  test    eax, eax
0x1801038c1  js      loc_180103B33
0x1801038c7  mov     rax, [rbp+70h+string]
0x1801038cb  mov     [rsp+170h+var_100], rax
0x1801038d0  mov     ecx, r12d
0x1801038d3  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x1801038d8  mov     [rsp+170h+var_118], eax
0x1801038dc  lea     rsi, [r14+40h]
0x1801038e0  cmp     qword ptr [rsi+18h], 7
0x1801038e5  ja      loc_180103AA8
0x1801038eb  xor     r12d, r12d
0x1801038ee  mov     [rbp+70h+var_98], r12
0x1801038f2  mov     rbx, rdi
0x1801038f5  inc     rbx
0x1801038f8  cmp     [rsi+rbx*2], r12w
0x1801038fd  jnz     short loc_1801038F5
0x1801038ff  mov     eax, 0FFFFFFFFh
0x180103904  cmp     rbx, rax
0x180103907  ja      loc_180103AFF
0x18010390d  mov     ecx, ebx; unsigned int
0x18010390f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180103914  lea     edx, [rax-1]
0x180103917  cmp     ebx, eax
0x180103919  cmovb   edx, ebx; length
0x18010391c  lea     r9, [rbp+70h+var_98]; string
0x180103920  lea     r8, [rbp+70h+var_B0]; hstringHeader
0x180103924  mov     rcx, rsi; sourceString
0x180103927  call    cs:__imp_WindowsCreateStringReference
0x18010392d  test    eax, eax
0x18010392f  js      loc_180103B46
0x180103935  lea     rsi, [r14+20h]
0x180103939  cmp     qword ptr [rsi+18h], 7
0x18010393e  ja      loc_180103AB0
0x180103944  mov     [rbp+70h+var_B8], r12
0x180103948  mov     rbx, rdi
0x18010394b  inc     rbx
0x18010394e  cmp     [rsi+rbx*2], r12w
0x180103953  jnz     short loc_18010394B
0x180103955  mov     eax, 0FFFFFFFFh
0x18010395a  cmp     rbx, rax
0x18010395d  ja      loc_180103AE9
0x180103963  mov     r12, [rbp+70h+var_98]
0x180103967  mov     ecx, ebx; unsigned int
0x180103969  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18010396e  lea     edx, [rax-1]
0x180103971  cmp     ebx, eax
0x180103973  cmovb   edx, ebx; length
0x180103976  lea     r9, [rbp+70h+var_B8]; string
0x18010397a  lea     r8, [rbp+70h+var_D0]; hstringHeader
0x18010397e  mov     rcx, rsi; sourceString
0x180103981  call    cs:__imp_WindowsCreateStringReference
0x180103987  xor     esi, esi
0x180103989  test    eax, eax
0x18010398b  js      loc_180103B59
0x180103991  cmp     qword ptr [r14+18h], 7
0x180103996  ja      loc_180103AB8
0x18010399c  mov     [rbp+70h+var_D8], rsi
0x1801039a0  inc     rdi
0x1801039a3  cmp     [r14+rdi*2], si
0x1801039a8  jnz     short loc_1801039A0
0x1801039aa  mov     eax, 0FFFFFFFFh
0x1801039af  cmp     rdi, rax
0x1801039b2  ja      loc_180103AD3
0x1801039b8  mov     rbx, [rbp+70h+var_B8]
0x1801039bc  mov     ecx, edi; unsigned int
0x1801039be  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1801039c3  lea     edx, [rax-1]
0x1801039c6  cmp     edi, eax
0x1801039c8  cmovb   edx, edi; length
0x1801039cb  lea     r9, [rbp+70h+var_D8]; string
0x1801039cf  lea     r8, [rbp+70h+var_F0]; hstringHeader
0x1801039d3  mov     rcx, r14; sourceString
0x1801039d6  call    cs:__imp_WindowsCreateStringReference
0x1801039dc  test    eax, eax
0x1801039de  js      loc_180103B6C
0x1801039e4  mov     rax, [r13+18h]
0x1801039e8  test    rax, rax
0x1801039eb  jz      loc_180103B2B
0x1801039f1  mov     r8, [rax]
0x1801039f4  lea     rax, [rsp+170h+var_120]
0x1801039f9  mov     [rsp+170h+var_130], rax
0x1801039fe  mov     rax, [rsp+170h+var_100]
0x180103a03  mov     [rsp+170h+var_138], rax
0x180103a08  mov     eax, [rsp+170h+var_118]
0x180103a0c  mov     [rsp+170h+var_140], eax
0x180103a10  mov     [rsp+170h+var_148], r12
0x180103a15  mov     [rsp+170h+var_150], rbx
0x180103a1a  mov     r9, [rbp+70h+var_D8]
0x180103a1e  mov     edx, [r13+10h]
0x180103a22  mov     rcx, [rsp+170h+var_F8]
0x180103a27  mov     rax, [rsp+170h+var_110]
0x180103a2c  mov     rax, [rax+48h]
0x180103a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103a35  mov     rcx, [rbp+78h]
0x180103a39  test    eax, eax
0x180103a3b  js      loc_180103B7F
0x180103a41  mov     [rbp+70h+var_D8], rsi
0x180103a45  mov     [rbp+70h+var_B8], rsi
0x180103a49  mov     [rbp+70h+var_98], rsi
0x180103a4d  mov     [rbp+70h+string], rsi
0x180103a51  mov     rdx, [rbp+70h+var_58]
0x180103a55  cmp     rdx, 7
0x180103a59  ja      short loc_180103AC0
0x180103a5b  mov     r8d, [rsp+170h+var_114]
0x180103a60  mov     rdx, [rsp+170h+var_120]
0x180103a65  mov     rcx, r15
0x180103a68  call    ??$unmarshal@ULocalStartGlobalProperties@UnifiedTile@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@ULocalStartGlobalProperties@UnifiedTile@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z; wil::cloud_store::unmarshal<Windows::Data::UnifiedTile::LocalStartGlobalProperties>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)
0x180103a6d  nop
0x180103a6e  mov     rcx, [rsp+170h+var_120]
0x180103a73  test    rcx, rcx
0x180103a76  jz      short loc_180103A85
0x180103a78  mov     rdx, [rcx]
0x180103a7b  mov     rax, [rdx+10h]
0x180103a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103a84  nop
0x180103a85  mov     rax, r15
0x180103a88  mov     rcx, [rbp+70h+var_50]
0x180103a8c  xor     rcx, rsp; StackCookie
0x180103a8f  call    __security_check_cookie
0x180103a94  add     rsp, 138h
0x180103a9b  pop     r15
0x180103a9d  pop     r14
0x180103a9f  pop     r13
0x180103aa1  pop     r12
0x180103aa3  pop     rdi
0x180103aa4  pop     rsi
0x180103aa5  pop     rbx
0x180103aa6  pop     rbp
0x180103aa7  retn
0x180103aa8  mov     rsi, [rsi]
0x180103aab  jmp     loc_1801038EB
0x180103ab0  mov     rsi, [rsi]
0x180103ab3  jmp     loc_180103944
0x180103ab8  mov     r14, [r14]
0x180103abb  jmp     loc_18010399C
0x180103ac0  lea     rdx, ds:2[rdx*2]
0x180103ac8  mov     rcx, [rbp+70h+var_70]
0x180103acc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180103ad1  jmp     short loc_180103A5B
0x180103ad3  xor     r9d, r9d; lpArguments
0x180103ad6  xor     r8d, r8d; nNumberOfArguments
0x180103ad9  lea     edx, [r9+1]; dwExceptionFlags
0x180103add  mov     ecx, 80070216h; dwExceptionCode
0x180103ae2  call    cs:__imp_RaiseException
0x180103ae8  nop
0x180103ae9  xor     r9d, r9d; lpArguments
0x180103aec  xor     r8d, r8d; nNumberOfArguments
0x180103aef  lea     edx, [r9+1]; dwExceptionFlags
0x180103af3  mov     ecx, 80070216h; dwExceptionCode
0x180103af8  call    cs:__imp_RaiseException
0x180103afe  nop
0x180103aff  xor     r9d, r9d; lpArguments
0x180103b02  xor     r8d, r8d; nNumberOfArguments
0x180103b05  lea     edx, [r9+1]; dwExceptionFlags
0x180103b09  mov     ecx, 80070216h; dwExceptionCode
0x180103b0e  call    cs:__imp_RaiseException
0x180103b14  nop
0x180103b15  xor     r9d, r9d; lpArguments
0x180103b18  xor     r8d, r8d; nNumberOfArguments
0x180103b1b  lea     edx, [r9+1]; dwExceptionFlags
0x180103b1f  mov     ecx, 80070216h; dwExceptionCode
0x180103b24  call    cs:__imp_RaiseException
0x180103b2a  nop
0x180103b2b  mov     r8, rsi
0x180103b2e  jmp     loc_1801039F4
0x180103b33  xor     r9d, r9d; lpArguments
0x180103b36  xor     r8d, r8d; nNumberOfArguments
0x180103b39  lea     edx, [r9+1]; dwExceptionFlags
0x180103b3d  mov     ecx, eax; dwExceptionCode
0x180103b3f  call    cs:__imp_RaiseException
0x180103b45  nop
0x180103b46  xor     r9d, r9d; lpArguments
0x180103b49  xor     r8d, r8d; nNumberOfArguments
0x180103b4c  lea     edx, [r9+1]; dwExceptionFlags
0x180103b50  mov     ecx, eax; dwExceptionCode
0x180103b52  call    cs:__imp_RaiseException
0x180103b58  nop
0x180103b59  xor     r9d, r9d; lpArguments
0x180103b5c  xor     r8d, r8d; nNumberOfArguments
0x180103b5f  lea     edx, [r9+1]; dwExceptionFlags
0x180103b63  mov     ecx, eax; dwExceptionCode
0x180103b65  call    cs:__imp_RaiseException
0x180103b6b  nop
0x180103b6c  xor     r9d, r9d; lpArguments
0x180103b6f  xor     r8d, r8d; nNumberOfArguments
0x180103b72  lea     edx, [r9+1]; dwExceptionFlags
0x180103b76  mov     ecx, eax; dwExceptionCode
0x180103b78  call    cs:__imp_RaiseException
0x180103b7e  nop
0x180103b7f  mov     r9d, eax; char *
0x180103b82  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180103b89  mov     edx, 588h; void *
0x180103b8e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180103b94  mov     rax, [rcx]
0x180103b97  mov     rax, [rax+10h]
0x180103b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103ba0  jmp     loc_180103862
```
