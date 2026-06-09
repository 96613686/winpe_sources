# wil::cloud_store::call_load<Windows::Data::CuratedTileCollection::TileCollectionContainer>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180093ae0`
- end: `0x180093e58`
- name: `??$call_load@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `888`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180093a38`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x180056798`
- `0x1800574a8`
- `0x1800579bc`
- `0x180093ae0`
- `0x180094258`
- `0x180147be8`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093bcc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093c48`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093cb1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093d12`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093e0f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093e25`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093e3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093e51`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093bcc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093c48`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093cb1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093d12`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093e0f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093e25`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093e3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180093e51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180093bb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180093c32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180093c9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180093cfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180093bb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180093c32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180093c9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180093cfc`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::call_load<Windows::Data::CuratedTileCollection::TileCollectionContainer>(
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
    JUMPOUT(0x180093E57LL);
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
  wil::cloud_store::unmarshal<Windows::Data::CuratedTileCollection::TileCollectionContainer>(a2, 0, a4);
  return a2;
}

```

## disassembly

```asm
0x180093ae0  push    rbp
0x180093ae2  push    rbx
0x180093ae3  push    rsi
0x180093ae4  push    rdi
0x180093ae5  push    r12
0x180093ae7  push    r13
0x180093ae9  push    r14
0x180093aeb  push    r15
0x180093aed  lea     rbp, [rsp-38h]
0x180093af2  sub     rsp, 138h
0x180093af9  mov     rax, cs:__security_cookie
0x180093b00  xor     rax, rsp
0x180093b03  mov     [rbp+70h+var_50], rax
0x180093b07  mov     r12d, r9d
0x180093b0a  mov     [rsp+170h+var_114], r9d
0x180093b0f  mov     r14, r8
0x180093b12  mov     r15, rdx
0x180093b15  mov     r13, rcx
0x180093b18  mov     [rsp+170h+var_110], rdx
0x180093b1d  mov     rbx, [rbp+70h+arg_20]
0x180093b24  xor     edi, edi
0x180093b26  mov     [rsp+170h+var_120], rdi
0x180093b2b  mov     rcx, [rcx]
0x180093b2e  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180093b33  mov     rax, [rax]
0x180093b36  mov     [rsp+170h+var_F8], rax
0x180093b3b  mov     rax, [rax]
0x180093b3e  mov     [rsp+170h+var_110], rax
0x180093b43  mov     rcx, [rsp+170h+var_120]
0x180093b48  mov     [rsp+170h+var_120], rdi
0x180093b4d  test    rcx, rcx
0x180093b50  jz      short loc_180093B5F
0x180093b52  mov     rax, [rcx]
0x180093b55  mov     rax, [rax+10h]
0x180093b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093b5e  nop
0x180093b5f  mov     rdx, rbx
0x180093b62  lea     rcx, [rbp+70h+var_70]
0x180093b66  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180093b6b  mov     rsi, rax
0x180093b6e  cmp     qword ptr [rax+18h], 7
0x180093b73  jbe     short loc_180093B78
0x180093b75  mov     rsi, [rax]
0x180093b78  mov     [rbp+70h+string], rdi
0x180093b7c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180093b80  mov     rbx, rdi
0x180093b83  xor     eax, eax
0x180093b85  inc     rbx
0x180093b88  cmp     [rsi+rbx*2], ax
0x180093b8c  jnz     short loc_180093B85
0x180093b8e  mov     eax, 0FFFFFFFFh
0x180093b93  cmp     rbx, rax
0x180093b96  ja      loc_180093E42
0x180093b9c  mov     ecx, ebx; unsigned int
0x180093b9e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180093ba3  lea     edx, [rax-1]
0x180093ba6  cmp     ebx, eax
0x180093ba8  cmovb   edx, ebx; length
0x180093bab  lea     r9, [rbp+70h+string]; string
0x180093baf  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x180093bb3  mov     rcx, rsi; sourceString
0x180093bb6  call    cs:__imp_WindowsCreateStringReference
0x180093bbc  test    eax, eax
0x180093bbe  jns     short loc_180093BD3
0x180093bc0  xor     r9d, r9d; lpArguments
0x180093bc3  xor     r8d, r8d; nNumberOfArguments
0x180093bc6  lea     edx, [r9+1]; dwExceptionFlags
0x180093bca  mov     ecx, eax; dwExceptionCode
0x180093bcc  call    cs:__imp_RaiseException
0x180093bd2  nop
0x180093bd3  mov     rax, [rbp+70h+string]
0x180093bd7  mov     [rsp+170h+var_100], rax
0x180093bdc  mov     ecx, r12d
0x180093bdf  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x180093be4  mov     [rsp+170h+var_118], eax
0x180093be8  lea     rsi, [r14+40h]
0x180093bec  cmp     qword ptr [rsi+18h], 7
0x180093bf1  jbe     short loc_180093BF6
0x180093bf3  mov     rsi, [rsi]
0x180093bf6  xor     r12d, r12d
0x180093bf9  mov     [rbp+70h+var_98], r12
0x180093bfd  mov     rbx, rdi
0x180093c00  inc     rbx
0x180093c03  cmp     [rsi+rbx*2], r12w
0x180093c08  jnz     short loc_180093C00
0x180093c0a  mov     eax, 0FFFFFFFFh
0x180093c0f  cmp     rbx, rax
0x180093c12  ja      loc_180093E2C
0x180093c18  mov     ecx, ebx; unsigned int
0x180093c1a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180093c1f  lea     edx, [rax-1]
0x180093c22  cmp     ebx, eax
0x180093c24  cmovb   edx, ebx; length
0x180093c27  lea     r9, [rbp+70h+var_98]; string
0x180093c2b  lea     r8, [rbp+70h+var_B0]; hstringHeader
0x180093c2f  mov     rcx, rsi; sourceString
0x180093c32  call    cs:__imp_WindowsCreateStringReference
0x180093c38  test    eax, eax
0x180093c3a  jns     short loc_180093C4F
0x180093c3c  xor     r9d, r9d; lpArguments
0x180093c3f  xor     r8d, r8d; nNumberOfArguments
0x180093c42  lea     edx, [r9+1]; dwExceptionFlags
0x180093c46  mov     ecx, eax; dwExceptionCode
0x180093c48  call    cs:__imp_RaiseException
0x180093c4e  nop
0x180093c4f  lea     rsi, [r14+20h]
0x180093c53  cmp     qword ptr [rsi+18h], 7
0x180093c58  jbe     short loc_180093C5D
0x180093c5a  mov     rsi, [rsi]
0x180093c5d  mov     [rbp+70h+var_B8], r12
0x180093c61  mov     rbx, rdi
0x180093c64  inc     rbx
0x180093c67  cmp     [rsi+rbx*2], r12w
0x180093c6c  jnz     short loc_180093C64
0x180093c6e  mov     eax, 0FFFFFFFFh
0x180093c73  cmp     rbx, rax
0x180093c76  ja      loc_180093E16
0x180093c7c  mov     r12, [rbp+70h+var_98]
0x180093c80  mov     ecx, ebx; unsigned int
0x180093c82  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180093c87  lea     edx, [rax-1]
0x180093c8a  cmp     ebx, eax
0x180093c8c  cmovb   edx, ebx; length
0x180093c8f  lea     r9, [rbp+70h+var_B8]; string
0x180093c93  lea     r8, [rbp+70h+var_D0]; hstringHeader
0x180093c97  mov     rcx, rsi; sourceString
0x180093c9a  call    cs:__imp_WindowsCreateStringReference
0x180093ca0  xor     esi, esi
0x180093ca2  test    eax, eax
0x180093ca4  jns     short loc_180093CB8
0x180093ca6  xor     r9d, r9d; lpArguments
0x180093ca9  xor     r8d, r8d; nNumberOfArguments
0x180093cac  lea     edx, [rsi+1]; dwExceptionFlags
0x180093caf  mov     ecx, eax; dwExceptionCode
0x180093cb1  call    cs:__imp_RaiseException
0x180093cb7  nop
0x180093cb8  cmp     qword ptr [r14+18h], 7
0x180093cbd  jbe     short loc_180093CC2
0x180093cbf  mov     r14, [r14]
0x180093cc2  mov     [rbp+70h+var_D8], rsi
0x180093cc6  inc     rdi
0x180093cc9  cmp     [r14+rdi*2], si
0x180093cce  jnz     short loc_180093CC6
0x180093cd0  mov     eax, 0FFFFFFFFh
0x180093cd5  cmp     rdi, rax
0x180093cd8  ja      loc_180093E00
0x180093cde  mov     rbx, [rbp+70h+var_B8]
0x180093ce2  mov     ecx, edi; unsigned int
0x180093ce4  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180093ce9  lea     edx, [rax-1]
0x180093cec  cmp     edi, eax
0x180093cee  cmovb   edx, edi; length
0x180093cf1  lea     r9, [rbp+70h+var_D8]; string
0x180093cf5  lea     r8, [rbp+70h+var_F0]; hstringHeader
0x180093cf9  mov     rcx, r14; sourceString
0x180093cfc  call    cs:__imp_WindowsCreateStringReference
0x180093d02  test    eax, eax
0x180093d04  jns     short loc_180093D19
0x180093d06  xor     r9d, r9d; lpArguments
0x180093d09  xor     r8d, r8d; nNumberOfArguments
0x180093d0c  lea     edx, [r9+1]; dwExceptionFlags
0x180093d10  mov     ecx, eax; dwExceptionCode
0x180093d12  call    cs:__imp_RaiseException
0x180093d18  nop
0x180093d19  mov     rax, [r13+18h]
0x180093d1d  test    rax, rax
0x180093d20  jz      short loc_180093D27
0x180093d22  mov     r8, [rax]
0x180093d25  jmp     short loc_180093D2A
0x180093d27  mov     r8, rsi
0x180093d2a  lea     rax, [rsp+170h+var_120]
0x180093d2f  mov     [rsp+170h+var_130], rax
0x180093d34  mov     rax, [rsp+170h+var_100]
0x180093d39  mov     [rsp+170h+var_138], rax
0x180093d3e  mov     eax, [rsp+170h+var_118]
0x180093d42  mov     [rsp+170h+var_140], eax
0x180093d46  mov     [rsp+170h+var_148], r12
0x180093d4b  mov     qword ptr [rsp+170h+var_150], rbx; int
0x180093d50  mov     r9, [rbp+70h+var_D8]
0x180093d54  mov     edx, [r13+10h]
0x180093d58  mov     rcx, [rsp+170h+var_F8]
0x180093d5d  mov     rax, [rsp+170h+var_110]
0x180093d62  mov     rax, [rax+48h]
0x180093d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d6b  mov     rcx, [rbp+78h]; this
0x180093d6f  test    eax, eax
0x180093d71  jns     short loc_180093D88
0x180093d73  mov     r9d, eax; char *
0x180093d76  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180093d7d  mov     edx, 588h; void *
0x180093d82  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093d88  mov     [rbp+70h+var_D8], rsi
0x180093d8c  mov     [rbp+70h+var_B8], rsi
0x180093d90  mov     [rbp+70h+var_98], rsi
0x180093d94  mov     [rbp+70h+string], rsi
0x180093d98  mov     rdx, [rbp+70h+var_58]
0x180093d9c  cmp     rdx, 7
0x180093da0  jbe     short loc_180093DB3
0x180093da2  lea     rdx, ds:2[rdx*2]
0x180093daa  mov     rcx, [rbp+70h+var_70]
0x180093dae  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180093db3  mov     r8d, [rsp+170h+var_114]
0x180093db8  mov     rdx, [rsp+170h+var_120]
0x180093dbd  mov     rcx, r15
0x180093dc0  call    ??$unmarshal@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z; wil::cloud_store::unmarshal<Windows::Data::CuratedTileCollection::TileCollectionContainer>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)
0x180093dc5  nop
0x180093dc6  mov     rcx, [rsp+170h+var_120]
0x180093dcb  test    rcx, rcx
0x180093dce  jz      short loc_180093DDD
0x180093dd0  mov     rdx, [rcx]
0x180093dd3  mov     rax, [rdx+10h]
0x180093dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ddc  nop
0x180093ddd  mov     rax, r15
0x180093de0  mov     rcx, [rbp+70h+var_50]
0x180093de4  xor     rcx, rsp; StackCookie
0x180093de7  call    __security_check_cookie
0x180093dec  add     rsp, 138h
0x180093df3  pop     r15
0x180093df5  pop     r14
0x180093df7  pop     r13
0x180093df9  pop     r12
0x180093dfb  pop     rdi
0x180093dfc  pop     rsi
0x180093dfd  pop     rbx
0x180093dfe  pop     rbp
0x180093dff  retn
0x180093e00  xor     r9d, r9d; lpArguments
0x180093e03  xor     r8d, r8d; nNumberOfArguments
0x180093e06  lea     edx, [r9+1]; dwExceptionFlags
0x180093e0a  mov     ecx, 80070216h; dwExceptionCode
0x180093e0f  call    cs:__imp_RaiseException
0x180093e15  nop
0x180093e16  xor     r9d, r9d; lpArguments
0x180093e19  xor     r8d, r8d; nNumberOfArguments
0x180093e1c  lea     edx, [r9+1]; dwExceptionFlags
0x180093e20  mov     ecx, 80070216h; dwExceptionCode
0x180093e25  call    cs:__imp_RaiseException
0x180093e2b  nop
0x180093e2c  xor     r9d, r9d; lpArguments
0x180093e2f  xor     r8d, r8d; nNumberOfArguments
0x180093e32  lea     edx, [r9+1]; dwExceptionFlags
0x180093e36  mov     ecx, 80070216h; dwExceptionCode
0x180093e3b  call    cs:__imp_RaiseException
0x180093e41  nop
0x180093e42  xor     r9d, r9d; lpArguments
0x180093e45  xor     r8d, r8d; nNumberOfArguments
0x180093e48  lea     edx, [r9+1]; dwExceptionFlags
0x180093e4c  mov     ecx, 80070216h; dwExceptionCode
0x180093e51  call    cs:__imp_RaiseException
```
