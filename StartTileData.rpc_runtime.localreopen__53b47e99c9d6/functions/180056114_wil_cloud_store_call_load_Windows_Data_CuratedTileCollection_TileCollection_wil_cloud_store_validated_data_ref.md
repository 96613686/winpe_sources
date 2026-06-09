# wil::cloud_store::call_load<Windows::Data::CuratedTileCollection::TileCollection>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180056114`
- end: `0x1800564ce`
- name: `??$call_load@UTileCollection@CuratedTileCollection@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@UTileCollection@CuratedTileCollection@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `954`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800558dc`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x180056114`
- `0x1800564d4`
- `0x180056798`
- `0x1800574a8`
- `0x1800579bc`
- `0x180147be8`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800563f2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056408`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005641e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056434`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056467`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005647a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005648d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800564a0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800563f2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056408`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005641e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056434`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056467`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005647a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005648d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800564a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800561e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005624f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800562a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800562fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800561e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005624f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800562a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800562fe`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::call_load<Windows::Data::CuratedTileCollection::TileCollection>(
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
  unsigned __int64 v16; // rbx
  unsigned int v17; // eax
  UINT32 v18; // edx
  HRESULT v19; // eax
  unsigned __int64 v20; // rbx
  unsigned int v21; // eax
  UINT32 v22; // edx
  HRESULT v23; // eax
  int v24; // ebx
  unsigned int v25; // eax
  UINT32 v26; // edx
  HRESULT v27; // eax
  __int64 *v28; // rax
  __int64 v29; // r8
  int v30; // eax
  wil::details::in1diag3 *v31; // rcx
  int v33; // [rsp+20h] [rbp-E0h]
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
    goto LABEL_41;
  v13 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v12);
  v14 = v13 - 1;
  if ( (unsigned int)v12 < v13 )
    v14 = v12;
  v15 = WindowsCreateStringReference(v10, v14, &hstringHeader, &string);
  if ( v15 < 0 )
  {
    RaiseException(v15, 1u, 0, 0);
LABEL_45:
    RaiseException(v19, 1u, 0, 0);
LABEL_46:
    RaiseException(v23, 1u, 0, 0);
    goto LABEL_47;
  }
  wil::cloud_store::convert_cloud_store_load_options(a4);
  v10 = (const WCHAR *)(a3 + 8);
  if ( (unsigned __int64)a3[11] > 7 )
    goto LABEL_42;
  while ( 1 )
  {
    v42 = 0;
    v16 = v11;
    do
      ++v16;
    while ( v10[v16] );
    if ( v16 > 0xFFFFFFFF )
      goto LABEL_40;
    v17 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v16);
    v18 = v17 - 1;
    if ( (unsigned int)v16 < v17 )
      v18 = v16;
    v19 = WindowsCreateStringReference(v10, v18, &v41, &v42);
    if ( v19 < 0 )
      goto LABEL_45;
    v10 = (const WCHAR *)(a3 + 4);
    if ( (unsigned __int64)a3[7] > 7 )
      v10 = *(const WCHAR **)v10;
    v40 = 0;
    v20 = v11;
    do
      ++v20;
    while ( v10[v20] );
    if ( v20 <= 0xFFFFFFFF )
      break;
LABEL_39:
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_40:
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_41:
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_42:
    v10 = *(const WCHAR **)v10;
  }
  v21 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v20);
  v22 = v21 - 1;
  if ( (unsigned int)v20 < v21 )
    v22 = v20;
  v23 = WindowsCreateStringReference(v10, v22, &v39, &v40);
  v10 = 0;
  if ( v23 < 0 )
    goto LABEL_46;
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (__int64 *)*a3;
  v38 = 0;
  do
    ++v11;
  while ( *((_WORD *)a3 + v11) );
  if ( v11 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_39;
  }
  v24 = (int)v40;
  v25 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  v26 = v25 - 1;
  if ( (unsigned int)v11 < v25 )
    v26 = v11;
  v27 = WindowsCreateStringReference((PCWSTR)a3, v26, &v37, &v38);
  if ( v27 < 0 )
  {
LABEL_47:
    RaiseException(v27, 1u, 0, 0);
    goto LABEL_48;
  }
  v28 = *(__int64 **)(a1 + 24);
  if ( v28 )
    v29 = *v28;
  else
    v29 = 0;
  v33 = v24;
  v30 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, HSTRING))(v35 + 72))(
          v36,
          *(unsigned int *)(a1 + 16),
          v29,
          v38);
  v31 = retaddr;
  if ( v30 < 0 )
LABEL_48:
    wil::details::in1diag3::Throw_Hr(
      v31,
      (void *)0x588,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v30,
      v33);
  v38 = 0;
  v40 = 0;
  v42 = 0;
  string = 0;
  if ( v46 > 7 )
    std::_Deallocate<16>(v45[0], 2 * v46 + 2);
  wil::cloud_store::unmarshal<Windows::Data::CuratedTileCollection::TileCollection>(a2, 0, a4);
  return a2;
}

```

## disassembly

```asm
0x180056114  push    rbp
0x180056116  push    rbx
0x180056117  push    rsi
0x180056118  push    rdi
0x180056119  push    r12
0x18005611b  push    r13
0x18005611d  push    r14
0x18005611f  push    r15
0x180056121  lea     rbp, [rsp-38h]
0x180056126  sub     rsp, 138h
0x18005612d  mov     rax, cs:__security_cookie
0x180056134  xor     rax, rsp
0x180056137  mov     [rbp+70h+var_50], rax
0x18005613b  mov     r12d, r9d
0x18005613e  mov     [rsp+170h+var_114], r9d
0x180056143  mov     r14, r8
0x180056146  mov     r15, rdx
0x180056149  mov     r13, rcx
0x18005614c  mov     [rsp+170h+var_110], rdx
0x180056151  mov     rbx, [rbp+70h+arg_20]
0x180056158  xor     edi, edi
0x18005615a  mov     [rsp+170h+var_120], rdi
0x18005615f  mov     rcx, [rcx]
0x180056162  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180056167  mov     rax, [rax]
0x18005616a  mov     [rsp+170h+var_F8], rax
0x18005616f  mov     rax, [rax]
0x180056172  mov     [rsp+170h+var_110], rax
0x180056177  mov     rcx, [rsp+170h+var_120]
0x18005617c  mov     [rsp+170h+var_120], rdi
0x180056181  test    rcx, rcx
0x180056184  jnz     loc_1800564BC
0x18005618a  mov     rdx, rbx
0x18005618d  lea     rcx, [rbp+70h+var_70]
0x180056191  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180056196  mov     rsi, rax
0x180056199  cmp     qword ptr [rax+18h], 7
0x18005619e  jbe     short loc_1800561A3
0x1800561a0  mov     rsi, [rax]
0x1800561a3  mov     [rbp+70h+string], rdi
0x1800561a7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800561ab  mov     rbx, rdi
0x1800561ae  xor     eax, eax
0x1800561b0  inc     rbx
0x1800561b3  cmp     [rsi+rbx*2], ax
0x1800561b7  jnz     short loc_1800561B0
0x1800561b9  mov     eax, 0FFFFFFFFh
0x1800561be  cmp     rbx, rax
0x1800561c1  ja      loc_180056425
0x1800561c7  mov     ecx, ebx; unsigned int
0x1800561c9  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800561ce  lea     edx, [rax-1]
0x1800561d1  cmp     ebx, eax
0x1800561d3  cmovb   edx, ebx; length
0x1800561d6  lea     r9, [rbp+70h+string]; string
0x1800561da  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x1800561de  mov     rcx, rsi; sourceString
0x1800561e1  call    cs:__imp_WindowsCreateStringReference
0x1800561e7  test    eax, eax
0x1800561e9  js      loc_18005645B
0x1800561ef  mov     rax, [rbp+70h+string]
0x1800561f3  mov     [rsp+170h+var_100], rax
0x1800561f8  mov     ecx, r12d
0x1800561fb  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x180056200  mov     [rsp+170h+var_118], eax
0x180056204  lea     rsi, [r14+40h]
0x180056208  cmp     qword ptr [rsi+18h], 7
0x18005620d  ja      loc_18005643B
0x180056213  xor     r12d, r12d
0x180056216  mov     [rbp+70h+var_98], r12
0x18005621a  mov     rbx, rdi
0x18005621d  inc     rbx
0x180056220  cmp     [rsi+rbx*2], r12w
0x180056225  jnz     short loc_18005621D
0x180056227  mov     eax, 0FFFFFFFFh
0x18005622c  cmp     rbx, rax
0x18005622f  ja      loc_18005640F
0x180056235  mov     ecx, ebx; unsigned int
0x180056237  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005623c  lea     edx, [rax-1]
0x18005623f  cmp     ebx, eax
0x180056241  cmovb   edx, ebx; length
0x180056244  lea     r9, [rbp+70h+var_98]; string
0x180056248  lea     r8, [rbp+70h+var_B0]; hstringHeader
0x18005624c  mov     rcx, rsi; sourceString
0x18005624f  call    cs:__imp_WindowsCreateStringReference
0x180056255  test    eax, eax
0x180056257  js      loc_18005646E
0x18005625d  lea     rsi, [r14+20h]
0x180056261  cmp     qword ptr [rsi+18h], 7
0x180056266  ja      loc_180056443
0x18005626c  mov     [rbp+70h+var_B8], r12
0x180056270  mov     rbx, rdi
0x180056273  inc     rbx
0x180056276  cmp     [rsi+rbx*2], r12w
0x18005627b  jnz     short loc_180056273
0x18005627d  mov     eax, 0FFFFFFFFh
0x180056282  cmp     rbx, rax
0x180056285  ja      loc_1800563F9
0x18005628b  mov     r12, [rbp+70h+var_98]
0x18005628f  mov     ecx, ebx; unsigned int
0x180056291  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180056296  lea     edx, [rax-1]
0x180056299  cmp     ebx, eax
0x18005629b  cmovb   edx, ebx; length
0x18005629e  lea     r9, [rbp+70h+var_B8]; string
0x1800562a2  lea     r8, [rbp+70h+var_D0]; hstringHeader
0x1800562a6  mov     rcx, rsi; sourceString
0x1800562a9  call    cs:__imp_WindowsCreateStringReference
0x1800562af  xor     esi, esi
0x1800562b1  test    eax, eax
0x1800562b3  js      loc_180056481
0x1800562b9  cmp     qword ptr [r14+18h], 7
0x1800562be  ja      loc_18005644B
0x1800562c4  mov     [rbp+70h+var_D8], rsi
0x1800562c8  inc     rdi
0x1800562cb  cmp     [r14+rdi*2], si
0x1800562d0  jnz     short loc_1800562C8
0x1800562d2  mov     eax, 0FFFFFFFFh
0x1800562d7  cmp     rdi, rax
0x1800562da  ja      loc_1800563E3
0x1800562e0  mov     rbx, [rbp+70h+var_B8]
0x1800562e4  mov     ecx, edi; unsigned int
0x1800562e6  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800562eb  lea     edx, [rax-1]
0x1800562ee  cmp     edi, eax
0x1800562f0  cmovb   edx, edi; length
0x1800562f3  lea     r9, [rbp+70h+var_D8]; string
0x1800562f7  lea     r8, [rbp+70h+var_F0]; hstringHeader
0x1800562fb  mov     rcx, r14; sourceString
0x1800562fe  call    cs:__imp_WindowsCreateStringReference
0x180056304  test    eax, eax
0x180056306  js      loc_180056494
0x18005630c  mov     rax, [r13+18h]
0x180056310  test    rax, rax
0x180056313  jz      loc_180056453
0x180056319  mov     r8, [rax]
0x18005631c  lea     rax, [rsp+170h+var_120]
0x180056321  mov     [rsp+170h+var_130], rax
0x180056326  mov     rax, [rsp+170h+var_100]
0x18005632b  mov     [rsp+170h+var_138], rax
0x180056330  mov     eax, [rsp+170h+var_118]
0x180056334  mov     [rsp+170h+var_140], eax
0x180056338  mov     [rsp+170h+var_148], r12
0x18005633d  mov     [rsp+170h+var_150], rbx
0x180056342  mov     r9, [rbp+70h+var_D8]
0x180056346  mov     edx, [r13+10h]
0x18005634a  mov     rcx, [rsp+170h+var_F8]
0x18005634f  mov     rax, [rsp+170h+var_110]
0x180056354  mov     rax, [rax+48h]
0x180056358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005635d  mov     rcx, [rbp+78h]
0x180056361  test    eax, eax
0x180056363  js      loc_1800564A7
0x180056369  mov     [rbp+70h+var_D8], rsi
0x18005636d  mov     [rbp+70h+var_B8], rsi
0x180056371  mov     [rbp+70h+var_98], rsi
0x180056375  mov     [rbp+70h+string], rsi
0x180056379  mov     rdx, [rbp+70h+var_58]
0x18005637d  cmp     rdx, 7
0x180056381  ja      short loc_1800563D0
0x180056383  mov     r8d, [rsp+170h+var_114]
0x180056388  mov     rdx, [rsp+170h+var_120]
0x18005638d  mov     rcx, r15
0x180056390  call    ??$unmarshal@UTileCollection@CuratedTileCollection@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@UTileCollection@CuratedTileCollection@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z; wil::cloud_store::unmarshal<Windows::Data::CuratedTileCollection::TileCollection>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)
0x180056395  nop
0x180056396  mov     rcx, [rsp+170h+var_120]
0x18005639b  test    rcx, rcx
0x18005639e  jz      short loc_1800563AD
0x1800563a0  mov     rdx, [rcx]
0x1800563a3  mov     rax, [rdx+10h]
0x1800563a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800563ac  nop
0x1800563ad  mov     rax, r15
0x1800563b0  mov     rcx, [rbp+70h+var_50]
0x1800563b4  xor     rcx, rsp; StackCookie
0x1800563b7  call    __security_check_cookie
0x1800563bc  add     rsp, 138h
0x1800563c3  pop     r15
0x1800563c5  pop     r14
0x1800563c7  pop     r13
0x1800563c9  pop     r12
0x1800563cb  pop     rdi
0x1800563cc  pop     rsi
0x1800563cd  pop     rbx
0x1800563ce  pop     rbp
0x1800563cf  retn
0x1800563d0  lea     rdx, ds:2[rdx*2]
0x1800563d8  mov     rcx, [rbp+70h+var_70]
0x1800563dc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800563e1  jmp     short loc_180056383
0x1800563e3  xor     r9d, r9d; lpArguments
0x1800563e6  xor     r8d, r8d; nNumberOfArguments
0x1800563e9  lea     edx, [r9+1]; dwExceptionFlags
0x1800563ed  mov     ecx, 80070216h; dwExceptionCode
0x1800563f2  call    cs:__imp_RaiseException
0x1800563f8  nop
0x1800563f9  xor     r9d, r9d; lpArguments
0x1800563fc  xor     r8d, r8d; nNumberOfArguments
0x1800563ff  lea     edx, [r9+1]; dwExceptionFlags
0x180056403  mov     ecx, 80070216h; dwExceptionCode
0x180056408  call    cs:__imp_RaiseException
0x18005640e  nop
0x18005640f  xor     r9d, r9d; lpArguments
0x180056412  xor     r8d, r8d; nNumberOfArguments
0x180056415  lea     edx, [r9+1]; dwExceptionFlags
0x180056419  mov     ecx, 80070216h; dwExceptionCode
0x18005641e  call    cs:__imp_RaiseException
0x180056424  nop
0x180056425  xor     r9d, r9d; lpArguments
0x180056428  xor     r8d, r8d; nNumberOfArguments
0x18005642b  lea     edx, [r9+1]; dwExceptionFlags
0x18005642f  mov     ecx, 80070216h; dwExceptionCode
0x180056434  call    cs:__imp_RaiseException
0x18005643a  nop
0x18005643b  mov     rsi, [rsi]
0x18005643e  jmp     loc_180056213
0x180056443  mov     rsi, [rsi]
0x180056446  jmp     loc_18005626C
0x18005644b  mov     r14, [r14]
0x18005644e  jmp     loc_1800562C4
0x180056453  mov     r8, rsi
0x180056456  jmp     loc_18005631C
0x18005645b  xor     r9d, r9d; lpArguments
0x18005645e  xor     r8d, r8d; nNumberOfArguments
0x180056461  lea     edx, [r9+1]; dwExceptionFlags
0x180056465  mov     ecx, eax; dwExceptionCode
0x180056467  call    cs:__imp_RaiseException
0x18005646d  nop
0x18005646e  xor     r9d, r9d; lpArguments
0x180056471  xor     r8d, r8d; nNumberOfArguments
0x180056474  lea     edx, [r9+1]; dwExceptionFlags
0x180056478  mov     ecx, eax; dwExceptionCode
0x18005647a  call    cs:__imp_RaiseException
0x180056480  nop
0x180056481  xor     r9d, r9d; lpArguments
0x180056484  xor     r8d, r8d; nNumberOfArguments
0x180056487  lea     edx, [r9+1]; dwExceptionFlags
0x18005648b  mov     ecx, eax; dwExceptionCode
0x18005648d  call    cs:__imp_RaiseException
0x180056493  nop
0x180056494  xor     r9d, r9d; lpArguments
0x180056497  xor     r8d, r8d; nNumberOfArguments
0x18005649a  lea     edx, [r9+1]; dwExceptionFlags
0x18005649e  mov     ecx, eax; dwExceptionCode
0x1800564a0  call    cs:__imp_RaiseException
0x1800564a6  nop
0x1800564a7  mov     r9d, eax; char *
0x1800564aa  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800564b1  mov     edx, 588h; void *
0x1800564b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800564bc  mov     rax, [rcx]
0x1800564bf  mov     rax, [rax+10h]
0x1800564c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800564c8  jmp     loc_18005618A
```
