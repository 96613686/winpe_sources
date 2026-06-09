# wil::cloud_store::call_load<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180053a2c`
- end: `0x180053da4`
- name: `??$call_load@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `888`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180054438`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x180053a2c`
- `0x180056798`
- `0x1800574a8`
- `0x1800579bc`
- `0x1800583e8`
- `0x180147be8`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053b18`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053b94`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053bfd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053c5e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053d5b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053d71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053d87`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053d9d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053b18`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053b94`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053bfd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053c5e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053d5b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053d71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053d87`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053b02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053b7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053be6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053c48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053b02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053b7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053be6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053c48`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::call_load<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>(
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
    JUMPOUT(0x180053DA3LL);
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
  wil::cloud_store::unmarshal<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>(a2, 0, a4);
  return a2;
}

```

## disassembly

```asm
0x180053a2c  push    rbp
0x180053a2e  push    rbx
0x180053a2f  push    rsi
0x180053a30  push    rdi
0x180053a31  push    r12
0x180053a33  push    r13
0x180053a35  push    r14
0x180053a37  push    r15
0x180053a39  lea     rbp, [rsp-38h]
0x180053a3e  sub     rsp, 138h
0x180053a45  mov     rax, cs:__security_cookie
0x180053a4c  xor     rax, rsp
0x180053a4f  mov     [rbp+70h+var_50], rax
0x180053a53  mov     r12d, r9d
0x180053a56  mov     [rsp+170h+var_114], r9d
0x180053a5b  mov     r14, r8
0x180053a5e  mov     r15, rdx
0x180053a61  mov     r13, rcx
0x180053a64  mov     [rsp+170h+var_110], rdx
0x180053a69  mov     rbx, [rbp+70h+arg_20]
0x180053a70  xor     edi, edi
0x180053a72  mov     [rsp+170h+var_120], rdi
0x180053a77  mov     rcx, [rcx]
0x180053a7a  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180053a7f  mov     rax, [rax]
0x180053a82  mov     [rsp+170h+var_F8], rax
0x180053a87  mov     rax, [rax]
0x180053a8a  mov     [rsp+170h+var_110], rax
0x180053a8f  mov     rcx, [rsp+170h+var_120]
0x180053a94  mov     [rsp+170h+var_120], rdi
0x180053a99  test    rcx, rcx
0x180053a9c  jz      short loc_180053AAB
0x180053a9e  mov     rax, [rcx]
0x180053aa1  mov     rax, [rax+10h]
0x180053aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053aaa  nop
0x180053aab  mov     rdx, rbx
0x180053aae  lea     rcx, [rbp+70h+var_70]
0x180053ab2  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180053ab7  mov     rsi, rax
0x180053aba  cmp     qword ptr [rax+18h], 7
0x180053abf  jbe     short loc_180053AC4
0x180053ac1  mov     rsi, [rax]
0x180053ac4  mov     [rbp+70h+string], rdi
0x180053ac8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180053acc  mov     rbx, rdi
0x180053acf  xor     eax, eax
0x180053ad1  inc     rbx
0x180053ad4  cmp     [rsi+rbx*2], ax
0x180053ad8  jnz     short loc_180053AD1
0x180053ada  mov     eax, 0FFFFFFFFh
0x180053adf  cmp     rbx, rax
0x180053ae2  ja      loc_180053D8E
0x180053ae8  mov     ecx, ebx; unsigned int
0x180053aea  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180053aef  lea     edx, [rax-1]
0x180053af2  cmp     ebx, eax
0x180053af4  cmovb   edx, ebx; length
0x180053af7  lea     r9, [rbp+70h+string]; string
0x180053afb  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x180053aff  mov     rcx, rsi; sourceString
0x180053b02  call    cs:__imp_WindowsCreateStringReference
0x180053b08  test    eax, eax
0x180053b0a  jns     short loc_180053B1F
0x180053b0c  xor     r9d, r9d; lpArguments
0x180053b0f  xor     r8d, r8d; nNumberOfArguments
0x180053b12  lea     edx, [r9+1]; dwExceptionFlags
0x180053b16  mov     ecx, eax; dwExceptionCode
0x180053b18  call    cs:__imp_RaiseException
0x180053b1e  nop
0x180053b1f  mov     rax, [rbp+70h+string]
0x180053b23  mov     [rsp+170h+var_100], rax
0x180053b28  mov     ecx, r12d
0x180053b2b  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x180053b30  mov     [rsp+170h+var_118], eax
0x180053b34  lea     rsi, [r14+40h]
0x180053b38  cmp     qword ptr [rsi+18h], 7
0x180053b3d  jbe     short loc_180053B42
0x180053b3f  mov     rsi, [rsi]
0x180053b42  xor     r12d, r12d
0x180053b45  mov     [rbp+70h+var_98], r12
0x180053b49  mov     rbx, rdi
0x180053b4c  inc     rbx
0x180053b4f  cmp     [rsi+rbx*2], r12w
0x180053b54  jnz     short loc_180053B4C
0x180053b56  mov     eax, 0FFFFFFFFh
0x180053b5b  cmp     rbx, rax
0x180053b5e  ja      loc_180053D78
0x180053b64  mov     ecx, ebx; unsigned int
0x180053b66  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180053b6b  lea     edx, [rax-1]
0x180053b6e  cmp     ebx, eax
0x180053b70  cmovb   edx, ebx; length
0x180053b73  lea     r9, [rbp+70h+var_98]; string
0x180053b77  lea     r8, [rbp+70h+var_B0]; hstringHeader
0x180053b7b  mov     rcx, rsi; sourceString
0x180053b7e  call    cs:__imp_WindowsCreateStringReference
0x180053b84  test    eax, eax
0x180053b86  jns     short loc_180053B9B
0x180053b88  xor     r9d, r9d; lpArguments
0x180053b8b  xor     r8d, r8d; nNumberOfArguments
0x180053b8e  lea     edx, [r9+1]; dwExceptionFlags
0x180053b92  mov     ecx, eax; dwExceptionCode
0x180053b94  call    cs:__imp_RaiseException
0x180053b9a  nop
0x180053b9b  lea     rsi, [r14+20h]
0x180053b9f  cmp     qword ptr [rsi+18h], 7
0x180053ba4  jbe     short loc_180053BA9
0x180053ba6  mov     rsi, [rsi]
0x180053ba9  mov     [rbp+70h+var_B8], r12
0x180053bad  mov     rbx, rdi
0x180053bb0  inc     rbx
0x180053bb3  cmp     [rsi+rbx*2], r12w
0x180053bb8  jnz     short loc_180053BB0
0x180053bba  mov     eax, 0FFFFFFFFh
0x180053bbf  cmp     rbx, rax
0x180053bc2  ja      loc_180053D62
0x180053bc8  mov     r12, [rbp+70h+var_98]
0x180053bcc  mov     ecx, ebx; unsigned int
0x180053bce  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180053bd3  lea     edx, [rax-1]
0x180053bd6  cmp     ebx, eax
0x180053bd8  cmovb   edx, ebx; length
0x180053bdb  lea     r9, [rbp+70h+var_B8]; string
0x180053bdf  lea     r8, [rbp+70h+var_D0]; hstringHeader
0x180053be3  mov     rcx, rsi; sourceString
0x180053be6  call    cs:__imp_WindowsCreateStringReference
0x180053bec  xor     esi, esi
0x180053bee  test    eax, eax
0x180053bf0  jns     short loc_180053C04
0x180053bf2  xor     r9d, r9d; lpArguments
0x180053bf5  xor     r8d, r8d; nNumberOfArguments
0x180053bf8  lea     edx, [rsi+1]; dwExceptionFlags
0x180053bfb  mov     ecx, eax; dwExceptionCode
0x180053bfd  call    cs:__imp_RaiseException
0x180053c03  nop
0x180053c04  cmp     qword ptr [r14+18h], 7
0x180053c09  jbe     short loc_180053C0E
0x180053c0b  mov     r14, [r14]
0x180053c0e  mov     [rbp+70h+var_D8], rsi
0x180053c12  inc     rdi
0x180053c15  cmp     [r14+rdi*2], si
0x180053c1a  jnz     short loc_180053C12
0x180053c1c  mov     eax, 0FFFFFFFFh
0x180053c21  cmp     rdi, rax
0x180053c24  ja      loc_180053D4C
0x180053c2a  mov     rbx, [rbp+70h+var_B8]
0x180053c2e  mov     ecx, edi; unsigned int
0x180053c30  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180053c35  lea     edx, [rax-1]
0x180053c38  cmp     edi, eax
0x180053c3a  cmovb   edx, edi; length
0x180053c3d  lea     r9, [rbp+70h+var_D8]; string
0x180053c41  lea     r8, [rbp+70h+var_F0]; hstringHeader
0x180053c45  mov     rcx, r14; sourceString
0x180053c48  call    cs:__imp_WindowsCreateStringReference
0x180053c4e  test    eax, eax
0x180053c50  jns     short loc_180053C65
0x180053c52  xor     r9d, r9d; lpArguments
0x180053c55  xor     r8d, r8d; nNumberOfArguments
0x180053c58  lea     edx, [r9+1]; dwExceptionFlags
0x180053c5c  mov     ecx, eax; dwExceptionCode
0x180053c5e  call    cs:__imp_RaiseException
0x180053c64  nop
0x180053c65  mov     rax, [r13+18h]
0x180053c69  test    rax, rax
0x180053c6c  jz      short loc_180053C73
0x180053c6e  mov     r8, [rax]
0x180053c71  jmp     short loc_180053C76
0x180053c73  mov     r8, rsi
0x180053c76  lea     rax, [rsp+170h+var_120]
0x180053c7b  mov     [rsp+170h+var_130], rax
0x180053c80  mov     rax, [rsp+170h+var_100]
0x180053c85  mov     [rsp+170h+var_138], rax
0x180053c8a  mov     eax, [rsp+170h+var_118]
0x180053c8e  mov     [rsp+170h+var_140], eax
0x180053c92  mov     [rsp+170h+var_148], r12
0x180053c97  mov     qword ptr [rsp+170h+var_150], rbx; int
0x180053c9c  mov     r9, [rbp+70h+var_D8]
0x180053ca0  mov     edx, [r13+10h]
0x180053ca4  mov     rcx, [rsp+170h+var_F8]
0x180053ca9  mov     rax, [rsp+170h+var_110]
0x180053cae  mov     rax, [rax+48h]
0x180053cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cb7  mov     rcx, [rbp+78h]; this
0x180053cbb  test    eax, eax
0x180053cbd  jns     short loc_180053CD4
0x180053cbf  mov     r9d, eax; char *
0x180053cc2  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180053cc9  mov     edx, 588h; void *
0x180053cce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053cd4  mov     [rbp+70h+var_D8], rsi
0x180053cd8  mov     [rbp+70h+var_B8], rsi
0x180053cdc  mov     [rbp+70h+var_98], rsi
0x180053ce0  mov     [rbp+70h+string], rsi
0x180053ce4  mov     rdx, [rbp+70h+var_58]
0x180053ce8  cmp     rdx, 7
0x180053cec  jbe     short loc_180053CFF
0x180053cee  lea     rdx, ds:2[rdx*2]
0x180053cf6  mov     rcx, [rbp+70h+var_70]
0x180053cfa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180053cff  mov     r8d, [rsp+170h+var_114]
0x180053d04  mov     rdx, [rsp+170h+var_120]
0x180053d09  mov     rcx, r15
0x180053d0c  call    ??$unmarshal@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z; wil::cloud_store::unmarshal<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)
0x180053d11  nop
0x180053d12  mov     rcx, [rsp+170h+var_120]
0x180053d17  test    rcx, rcx
0x180053d1a  jz      short loc_180053D29
0x180053d1c  mov     rdx, [rcx]
0x180053d1f  mov     rax, [rdx+10h]
0x180053d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d28  nop
0x180053d29  mov     rax, r15
0x180053d2c  mov     rcx, [rbp+70h+var_50]
0x180053d30  xor     rcx, rsp; StackCookie
0x180053d33  call    __security_check_cookie
0x180053d38  add     rsp, 138h
0x180053d3f  pop     r15
0x180053d41  pop     r14
0x180053d43  pop     r13
0x180053d45  pop     r12
0x180053d47  pop     rdi
0x180053d48  pop     rsi
0x180053d49  pop     rbx
0x180053d4a  pop     rbp
0x180053d4b  retn
0x180053d4c  xor     r9d, r9d; lpArguments
0x180053d4f  xor     r8d, r8d; nNumberOfArguments
0x180053d52  lea     edx, [r9+1]; dwExceptionFlags
0x180053d56  mov     ecx, 80070216h; dwExceptionCode
0x180053d5b  call    cs:__imp_RaiseException
0x180053d61  nop
0x180053d62  xor     r9d, r9d; lpArguments
0x180053d65  xor     r8d, r8d; nNumberOfArguments
0x180053d68  lea     edx, [r9+1]; dwExceptionFlags
0x180053d6c  mov     ecx, 80070216h; dwExceptionCode
0x180053d71  call    cs:__imp_RaiseException
0x180053d77  nop
0x180053d78  xor     r9d, r9d; lpArguments
0x180053d7b  xor     r8d, r8d; nNumberOfArguments
0x180053d7e  lea     edx, [r9+1]; dwExceptionFlags
0x180053d82  mov     ecx, 80070216h; dwExceptionCode
0x180053d87  call    cs:__imp_RaiseException
0x180053d8d  nop
0x180053d8e  xor     r9d, r9d; lpArguments
0x180053d91  xor     r8d, r8d; nNumberOfArguments
0x180053d94  lea     edx, [r9+1]; dwExceptionFlags
0x180053d98  mov     ecx, 80070216h; dwExceptionCode
0x180053d9d  call    cs:__imp_RaiseException
```
