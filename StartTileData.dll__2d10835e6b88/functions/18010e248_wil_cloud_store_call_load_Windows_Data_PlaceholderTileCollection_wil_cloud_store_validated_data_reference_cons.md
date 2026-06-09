# wil::cloud_store::call_load<Windows::Data::PlaceholderTileCollection>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18010e248`
- end: `0x18010e5c0`
- name: `??$call_load@UPlaceholderTileCollection@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@UPlaceholderTileCollection@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `888`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18010e1a0`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x180056798`
- `0x1800574a8`
- `0x1800579bc`
- `0x18005c230`
- `0x18010e248`
- `0x180147be8`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e334`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e3b0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e419`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e47a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e577`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e58d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e5a3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e5b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e334`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e3b0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e419`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e47a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e577`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e58d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e5a3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010e5b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18010e31e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18010e39a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18010e402`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18010e464`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18010e31e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18010e39a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18010e402`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18010e464`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::call_load<Windows::Data::PlaceholderTileCollection>(
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
    JUMPOUT(0x18010E5BFLL);
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
  wil::cloud_store::unmarshal<Windows::Data::PlaceholderTileCollection>(a2, 0, a4);
  return a2;
}

```

## disassembly

```asm
0x18010e248  push    rbp
0x18010e24a  push    rbx
0x18010e24b  push    rsi
0x18010e24c  push    rdi
0x18010e24d  push    r12
0x18010e24f  push    r13
0x18010e251  push    r14
0x18010e253  push    r15
0x18010e255  lea     rbp, [rsp-38h]
0x18010e25a  sub     rsp, 138h
0x18010e261  mov     rax, cs:__security_cookie
0x18010e268  xor     rax, rsp
0x18010e26b  mov     [rbp+70h+var_50], rax
0x18010e26f  mov     r12d, r9d
0x18010e272  mov     [rsp+170h+var_114], r9d
0x18010e277  mov     r14, r8
0x18010e27a  mov     r15, rdx
0x18010e27d  mov     r13, rcx
0x18010e280  mov     [rsp+170h+var_110], rdx
0x18010e285  mov     rbx, [rbp+70h+arg_20]
0x18010e28c  xor     edi, edi
0x18010e28e  mov     [rsp+170h+var_120], rdi
0x18010e293  mov     rcx, [rcx]
0x18010e296  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x18010e29b  mov     rax, [rax]
0x18010e29e  mov     [rsp+170h+var_F8], rax
0x18010e2a3  mov     rax, [rax]
0x18010e2a6  mov     [rsp+170h+var_110], rax
0x18010e2ab  mov     rcx, [rsp+170h+var_120]
0x18010e2b0  mov     [rsp+170h+var_120], rdi
0x18010e2b5  test    rcx, rcx
0x18010e2b8  jz      short loc_18010E2C7
0x18010e2ba  mov     rax, [rcx]
0x18010e2bd  mov     rax, [rax+10h]
0x18010e2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e2c6  nop
0x18010e2c7  mov     rdx, rbx
0x18010e2ca  lea     rcx, [rbp+70h+var_70]
0x18010e2ce  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x18010e2d3  mov     rsi, rax
0x18010e2d6  cmp     qword ptr [rax+18h], 7
0x18010e2db  jbe     short loc_18010E2E0
0x18010e2dd  mov     rsi, [rax]
0x18010e2e0  mov     [rbp+70h+string], rdi
0x18010e2e4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18010e2e8  mov     rbx, rdi
0x18010e2eb  xor     eax, eax
0x18010e2ed  inc     rbx
0x18010e2f0  cmp     [rsi+rbx*2], ax
0x18010e2f4  jnz     short loc_18010E2ED
0x18010e2f6  mov     eax, 0FFFFFFFFh
0x18010e2fb  cmp     rbx, rax
0x18010e2fe  ja      loc_18010E5AA
0x18010e304  mov     ecx, ebx; unsigned int
0x18010e306  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18010e30b  lea     edx, [rax-1]
0x18010e30e  cmp     ebx, eax
0x18010e310  cmovb   edx, ebx; length
0x18010e313  lea     r9, [rbp+70h+string]; string
0x18010e317  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x18010e31b  mov     rcx, rsi; sourceString
0x18010e31e  call    cs:__imp_WindowsCreateStringReference
0x18010e324  test    eax, eax
0x18010e326  jns     short loc_18010E33B
0x18010e328  xor     r9d, r9d; lpArguments
0x18010e32b  xor     r8d, r8d; nNumberOfArguments
0x18010e32e  lea     edx, [r9+1]; dwExceptionFlags
0x18010e332  mov     ecx, eax; dwExceptionCode
0x18010e334  call    cs:__imp_RaiseException
0x18010e33a  nop
0x18010e33b  mov     rax, [rbp+70h+string]
0x18010e33f  mov     [rsp+170h+var_100], rax
0x18010e344  mov     ecx, r12d
0x18010e347  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x18010e34c  mov     [rsp+170h+var_118], eax
0x18010e350  lea     rsi, [r14+40h]
0x18010e354  cmp     qword ptr [rsi+18h], 7
0x18010e359  jbe     short loc_18010E35E
0x18010e35b  mov     rsi, [rsi]
0x18010e35e  xor     r12d, r12d
0x18010e361  mov     [rbp+70h+var_98], r12
0x18010e365  mov     rbx, rdi
0x18010e368  inc     rbx
0x18010e36b  cmp     [rsi+rbx*2], r12w
0x18010e370  jnz     short loc_18010E368
0x18010e372  mov     eax, 0FFFFFFFFh
0x18010e377  cmp     rbx, rax
0x18010e37a  ja      loc_18010E594
0x18010e380  mov     ecx, ebx; unsigned int
0x18010e382  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18010e387  lea     edx, [rax-1]
0x18010e38a  cmp     ebx, eax
0x18010e38c  cmovb   edx, ebx; length
0x18010e38f  lea     r9, [rbp+70h+var_98]; string
0x18010e393  lea     r8, [rbp+70h+var_B0]; hstringHeader
0x18010e397  mov     rcx, rsi; sourceString
0x18010e39a  call    cs:__imp_WindowsCreateStringReference
0x18010e3a0  test    eax, eax
0x18010e3a2  jns     short loc_18010E3B7
0x18010e3a4  xor     r9d, r9d; lpArguments
0x18010e3a7  xor     r8d, r8d; nNumberOfArguments
0x18010e3aa  lea     edx, [r9+1]; dwExceptionFlags
0x18010e3ae  mov     ecx, eax; dwExceptionCode
0x18010e3b0  call    cs:__imp_RaiseException
0x18010e3b6  nop
0x18010e3b7  lea     rsi, [r14+20h]
0x18010e3bb  cmp     qword ptr [rsi+18h], 7
0x18010e3c0  jbe     short loc_18010E3C5
0x18010e3c2  mov     rsi, [rsi]
0x18010e3c5  mov     [rbp+70h+var_B8], r12
0x18010e3c9  mov     rbx, rdi
0x18010e3cc  inc     rbx
0x18010e3cf  cmp     [rsi+rbx*2], r12w
0x18010e3d4  jnz     short loc_18010E3CC
0x18010e3d6  mov     eax, 0FFFFFFFFh
0x18010e3db  cmp     rbx, rax
0x18010e3de  ja      loc_18010E57E
0x18010e3e4  mov     r12, [rbp+70h+var_98]
0x18010e3e8  mov     ecx, ebx; unsigned int
0x18010e3ea  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18010e3ef  lea     edx, [rax-1]
0x18010e3f2  cmp     ebx, eax
0x18010e3f4  cmovb   edx, ebx; length
0x18010e3f7  lea     r9, [rbp+70h+var_B8]; string
0x18010e3fb  lea     r8, [rbp+70h+var_D0]; hstringHeader
0x18010e3ff  mov     rcx, rsi; sourceString
0x18010e402  call    cs:__imp_WindowsCreateStringReference
0x18010e408  xor     esi, esi
0x18010e40a  test    eax, eax
0x18010e40c  jns     short loc_18010E420
0x18010e40e  xor     r9d, r9d; lpArguments
0x18010e411  xor     r8d, r8d; nNumberOfArguments
0x18010e414  lea     edx, [rsi+1]; dwExceptionFlags
0x18010e417  mov     ecx, eax; dwExceptionCode
0x18010e419  call    cs:__imp_RaiseException
0x18010e41f  nop
0x18010e420  cmp     qword ptr [r14+18h], 7
0x18010e425  jbe     short loc_18010E42A
0x18010e427  mov     r14, [r14]
0x18010e42a  mov     [rbp+70h+var_D8], rsi
0x18010e42e  inc     rdi
0x18010e431  cmp     [r14+rdi*2], si
0x18010e436  jnz     short loc_18010E42E
0x18010e438  mov     eax, 0FFFFFFFFh
0x18010e43d  cmp     rdi, rax
0x18010e440  ja      loc_18010E568
0x18010e446  mov     rbx, [rbp+70h+var_B8]
0x18010e44a  mov     ecx, edi; unsigned int
0x18010e44c  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18010e451  lea     edx, [rax-1]
0x18010e454  cmp     edi, eax
0x18010e456  cmovb   edx, edi; length
0x18010e459  lea     r9, [rbp+70h+var_D8]; string
0x18010e45d  lea     r8, [rbp+70h+var_F0]; hstringHeader
0x18010e461  mov     rcx, r14; sourceString
0x18010e464  call    cs:__imp_WindowsCreateStringReference
0x18010e46a  test    eax, eax
0x18010e46c  jns     short loc_18010E481
0x18010e46e  xor     r9d, r9d; lpArguments
0x18010e471  xor     r8d, r8d; nNumberOfArguments
0x18010e474  lea     edx, [r9+1]; dwExceptionFlags
0x18010e478  mov     ecx, eax; dwExceptionCode
0x18010e47a  call    cs:__imp_RaiseException
0x18010e480  nop
0x18010e481  mov     rax, [r13+18h]
0x18010e485  test    rax, rax
0x18010e488  jz      short loc_18010E48F
0x18010e48a  mov     r8, [rax]
0x18010e48d  jmp     short loc_18010E492
0x18010e48f  mov     r8, rsi
0x18010e492  lea     rax, [rsp+170h+var_120]
0x18010e497  mov     [rsp+170h+var_130], rax
0x18010e49c  mov     rax, [rsp+170h+var_100]
0x18010e4a1  mov     [rsp+170h+var_138], rax
0x18010e4a6  mov     eax, [rsp+170h+var_118]
0x18010e4aa  mov     [rsp+170h+var_140], eax
0x18010e4ae  mov     [rsp+170h+var_148], r12
0x18010e4b3  mov     qword ptr [rsp+170h+var_150], rbx; int
0x18010e4b8  mov     r9, [rbp+70h+var_D8]
0x18010e4bc  mov     edx, [r13+10h]
0x18010e4c0  mov     rcx, [rsp+170h+var_F8]
0x18010e4c5  mov     rax, [rsp+170h+var_110]
0x18010e4ca  mov     rax, [rax+48h]
0x18010e4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e4d3  mov     rcx, [rbp+78h]; this
0x18010e4d7  test    eax, eax
0x18010e4d9  jns     short loc_18010E4F0
0x18010e4db  mov     r9d, eax; char *
0x18010e4de  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18010e4e5  mov     edx, 588h; void *
0x18010e4ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010e4f0  mov     [rbp+70h+var_D8], rsi
0x18010e4f4  mov     [rbp+70h+var_B8], rsi
0x18010e4f8  mov     [rbp+70h+var_98], rsi
0x18010e4fc  mov     [rbp+70h+string], rsi
0x18010e500  mov     rdx, [rbp+70h+var_58]
0x18010e504  cmp     rdx, 7
0x18010e508  jbe     short loc_18010E51B
0x18010e50a  lea     rdx, ds:2[rdx*2]
0x18010e512  mov     rcx, [rbp+70h+var_70]
0x18010e516  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18010e51b  mov     r8d, [rsp+170h+var_114]
0x18010e520  mov     rdx, [rsp+170h+var_120]
0x18010e525  mov     rcx, r15
0x18010e528  call    ??$unmarshal@UPlaceholderTileCollection@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@UPlaceholderTileCollection@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z; wil::cloud_store::unmarshal<Windows::Data::PlaceholderTileCollection>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)
0x18010e52d  nop
0x18010e52e  mov     rcx, [rsp+170h+var_120]
0x18010e533  test    rcx, rcx
0x18010e536  jz      short loc_18010E545
0x18010e538  mov     rdx, [rcx]
0x18010e53b  mov     rax, [rdx+10h]
0x18010e53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e544  nop
0x18010e545  mov     rax, r15
0x18010e548  mov     rcx, [rbp+70h+var_50]
0x18010e54c  xor     rcx, rsp; StackCookie
0x18010e54f  call    __security_check_cookie
0x18010e554  add     rsp, 138h
0x18010e55b  pop     r15
0x18010e55d  pop     r14
0x18010e55f  pop     r13
0x18010e561  pop     r12
0x18010e563  pop     rdi
0x18010e564  pop     rsi
0x18010e565  pop     rbx
0x18010e566  pop     rbp
0x18010e567  retn
0x18010e568  xor     r9d, r9d; lpArguments
0x18010e56b  xor     r8d, r8d; nNumberOfArguments
0x18010e56e  lea     edx, [r9+1]; dwExceptionFlags
0x18010e572  mov     ecx, 80070216h; dwExceptionCode
0x18010e577  call    cs:__imp_RaiseException
0x18010e57d  nop
0x18010e57e  xor     r9d, r9d; lpArguments
0x18010e581  xor     r8d, r8d; nNumberOfArguments
0x18010e584  lea     edx, [r9+1]; dwExceptionFlags
0x18010e588  mov     ecx, 80070216h; dwExceptionCode
0x18010e58d  call    cs:__imp_RaiseException
0x18010e593  nop
0x18010e594  xor     r9d, r9d; lpArguments
0x18010e597  xor     r8d, r8d; nNumberOfArguments
0x18010e59a  lea     edx, [r9+1]; dwExceptionFlags
0x18010e59e  mov     ecx, 80070216h; dwExceptionCode
0x18010e5a3  call    cs:__imp_RaiseException
0x18010e5a9  nop
0x18010e5aa  xor     r9d, r9d; lpArguments
0x18010e5ad  xor     r8d, r8d; nNumberOfArguments
0x18010e5b0  lea     edx, [r9+1]; dwExceptionFlags
0x18010e5b4  mov     ecx, 80070216h; dwExceptionCode
0x18010e5b9  call    cs:__imp_RaiseException
```
