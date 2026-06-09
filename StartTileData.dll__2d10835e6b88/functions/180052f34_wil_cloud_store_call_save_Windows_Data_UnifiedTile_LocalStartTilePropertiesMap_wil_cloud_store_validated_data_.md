# wil::cloud_store::call_save<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_data<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap> const &,unsigned __int64,wil::cloud_store_save_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180052f34`
- end: `0x180053351`
- name: `??$call_save@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@AEAA?AVcloud_store_save_result@1@AEBUvalidated_data_reference@01@AEBV?$cloud_store_data@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@1@_KW4cloud_store_save_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1053`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802d97fc`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x18002dde0`
- `0x180052f34`
- `0x180053358`
- `0x1800533b8`
- `0x18005467c`
- `0x180056798`
- `0x1800574a8`
- `0x180147be8`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800530a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053114`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005317d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800531de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053308`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005331e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053334`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005334a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800530a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053114`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005317d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800531de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053308`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005331e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053334`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005334a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005308e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800530fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053166`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800531c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005308e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800530fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053166`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800531c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
wil::cloud_store_save_result *__fastcall wil::cloud_store::call_save<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>(
        _QWORD *a1,
        wil::cloud_store_save_result *a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7)
{
  __int64 *started; // rax
  int v11; // ebx
  __int64 v12; // r14
  __int64 v13; // rax
  const WCHAR *v14; // rsi
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rbx
  unsigned int v17; // eax
  UINT32 v18; // edx
  HRESULT v19; // eax
  const WCHAR *v20; // rsi
  unsigned __int64 v21; // rbx
  unsigned int v22; // eax
  UINT32 v23; // edx
  HRESULT v24; // eax
  const WCHAR *v25; // rsi
  unsigned __int64 v26; // rbx
  unsigned int v27; // eax
  UINT32 v28; // edx
  HRESULT v29; // eax
  int v30; // ebx
  unsigned int v31; // eax
  UINT32 v32; // edx
  HRESULT v33; // eax
  __int64 *v34; // rax
  __int64 v35; // r8
  int v36; // eax
  wil::cloud_store_save_result *v37; // rbx
  __int64 *v39; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h]
  HSTRING v41; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v42; // [rsp+98h] [rbp-68h]
  wil::cloud_store_save_result *v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+A8h] [rbp-58h]
  HSTRING_HEADER v45; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v46; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING_HEADER v47; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING v48; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING_HEADER v49; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING v50; // [rsp+108h] [rbp+8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+110h] [rbp+10h] BYREF
  HSTRING string; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v53[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v54; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v43 = a2;
  v42 = a1;
  LODWORD(v40) = 0;
  wil::cloud_store::convert_cloud_store_save_options(a6);
  if ( (a6 & 8) != 0 )
  {
    v39 = 0;
    started = (__int64 *)&v39;
    v11 = 1;
    v12 = 0;
  }
  else
  {
    started = (__int64 *)wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>>(
                           &v41,
                           a4);
    v11 = 2;
    v12 = *started;
  }
  *started = 0;
  v44 = v12;
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    LODWORD(v40) = v11;
    if ( v41 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v41 + 16LL))(v41);
  }
  if ( (v11 & 1) != 0 )
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v39);
  v39 = *(__int64 **)wil::details::shared_cloud_store_state::get_cloud_store(*a1);
  v40 = *v39;
  v13 = wil::cloud_store::widen_string(v53, a7);
  v14 = (const WCHAR *)v13;
  if ( *(_QWORD *)(v13 + 24) > 7u )
    v14 = *(const WCHAR **)v13;
  string = 0;
  v15 = -1;
  v16 = -1;
  do
    ++v16;
  while ( v14[v16] );
  if ( v16 > 0xFFFFFFFF )
  {
LABEL_58:
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x180053350LL);
  }
  v17 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v16);
  v18 = v17 - 1;
  if ( (unsigned int)v16 < v17 )
    v18 = v16;
  v19 = WindowsCreateStringReference(v14, v18, &hstringHeader, &string);
  if ( v19 < 0 )
    RaiseException(v19, 1u, 0, 0);
  v20 = (const WCHAR *)(a3 + 8);
  if ( (unsigned __int64)a3[11] > 7 )
    v20 = *(const WCHAR **)v20;
  v50 = 0;
  v21 = -1;
  do
    ++v21;
  while ( v20[v21] );
  if ( v21 > 0xFFFFFFFF )
  {
LABEL_57:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_58;
  }
  v41 = string;
  v22 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v21);
  v23 = v22 - 1;
  if ( (unsigned int)v21 < v22 )
    v23 = v21;
  v24 = WindowsCreateStringReference(v20, v23, &v49, &v50);
  if ( v24 < 0 )
    RaiseException(v24, 1u, 0, 0);
  v25 = (const WCHAR *)(a3 + 4);
  if ( (unsigned __int64)a3[7] > 7 )
    v25 = *(const WCHAR **)v25;
  v48 = 0;
  v26 = -1;
  do
    ++v26;
  while ( v25[v26] );
  if ( v26 > 0xFFFFFFFF )
  {
LABEL_56:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_57;
  }
  v27 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v26);
  v28 = v27 - 1;
  if ( (unsigned int)v26 < v27 )
    v28 = v26;
  v29 = WindowsCreateStringReference(v25, v28, &v47, &v48);
  if ( v29 < 0 )
    RaiseException(v29, 1u, 0, 0);
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (__int64 *)*a3;
  v46 = 0;
  do
    ++v15;
  while ( *((_WORD *)a3 + v15) );
  if ( v15 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_56;
  }
  v30 = (int)v48;
  v31 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v15);
  v32 = v31 - 1;
  if ( (unsigned int)v15 < v31 )
    v32 = v15;
  v33 = WindowsCreateStringReference((PCWSTR)a3, v32, &v45, &v46);
  if ( v33 < 0 )
    RaiseException(v33, 1u, 0, 0);
  v34 = (__int64 *)v42[3];
  if ( v34 )
    v35 = *v34;
  else
    v35 = 0;
  v36 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, HSTRING))(v40 + 88))(
          v39,
          *((unsigned int *)v42 + 4),
          v35,
          v46);
  if ( v36 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5E4,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v36,
      v30);
  v46 = 0;
  v48 = 0;
  v50 = 0;
  string = 0;
  if ( v54 > 7 )
    std::_Deallocate<16>(v53[0], 2 * v54 + 2);
  v37 = v43;
  wil::cloud_store_save_result::cloud_store_save_result(v43, 0);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return v37;
}

```

## disassembly

```asm
0x180052f34  push    rbp
0x180052f36  push    rbx
0x180052f37  push    rsi
0x180052f38  push    rdi
0x180052f39  push    r12
0x180052f3b  push    r13
0x180052f3d  push    r14
0x180052f3f  push    r15
0x180052f41  lea     rbp, [rsp-68h]
0x180052f46  sub     rsp, 168h
0x180052f4d  mov     rax, cs:__security_cookie
0x180052f54  xor     rax, rsp
0x180052f57  mov     [rbp+0A0h+var_50], rax
0x180052f5b  mov     r13, r9
0x180052f5e  mov     r15, r8
0x180052f61  mov     [rbp+0A0h+var_100], rdx
0x180052f65  mov     rsi, rcx
0x180052f68  mov     [rbp+0A0h+var_108], rcx
0x180052f6c  mov     rdi, [rbp+0A0h+arg_30]
0x180052f73  xor     r12d, r12d
0x180052f76  mov     dword ptr [rbp+0A0h+var_118], r12d
0x180052f7a  mov     ecx, [rbp+0A0h+arg_28]
0x180052f80  call    ?convert_cloud_store_save_options@cloud_store@wil@@CA?AW4SaveOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_save_options@2@@Z; wil::cloud_store::convert_cloud_store_save_options(wil::cloud_store_save_options)
0x180052f85  mov     [rsp+1A0h+var_130], eax
0x180052f89  cmp     [r13+21h], r12b
0x180052f8d  jnz     short loc_180052F95
0x180052f8f  cmp     [r13+18h], r12
0x180052f93  jnz     short loc_180052F9C
0x180052f95  or      eax, 8
0x180052f98  mov     [rsp+1A0h+var_130], eax
0x180052f9c  test    byte ptr [rbp+0A0h+arg_28], 8
0x180052fa3  jz      short loc_180052FB7
0x180052fa5  mov     [rbp+0A0h+var_120], r12
0x180052fa9  lea     rax, [rbp+0A0h+var_120]
0x180052fad  mov     ebx, 1
0x180052fb2  mov     r14, r12
0x180052fb5  jmp     short loc_180052FCB
0x180052fb7  mov     rdx, r13
0x180052fba  lea     rcx, [rbp+0A0h+var_110]
0x180052fbe  call    ??$marshal@V?$cloud_store_data@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@wil@@@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@AEBV?$cloud_store_data@ULocalStartTilePropertiesMap@UnifiedTile@Data@Windows@@@1@@Z; wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap>>(wil::cloud_store_data<Windows::Data::UnifiedTile::LocalStartTilePropertiesMap> const &)
0x180052fc3  mov     ebx, 2
0x180052fc8  mov     r14, [rax]
0x180052fcb  mov     [rax], r12
0x180052fce  mov     [rbp+0A0h+var_F8], r14
0x180052fd2  test    bl, 2
0x180052fd5  jz      short loc_180052FF3
0x180052fd7  and     ebx, 0FFFFFFFDh
0x180052fda  mov     dword ptr [rbp+0A0h+var_118], ebx
0x180052fdd  mov     rcx, [rbp+0A0h+var_110]
0x180052fe1  test    rcx, rcx
0x180052fe4  jz      short loc_180052FF3
0x180052fe6  mov     rax, [rcx]
0x180052fe9  mov     rax, [rax+10h]
0x180052fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ff2  nop
0x180052ff3  test    bl, 1
0x180052ff6  jz      short loc_180053001
0x180052ff8  lea     rcx, [rbp+0A0h+var_120]; void *
0x180052ffc  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180053001  mov     [rsp+1A0h+var_128], r12
0x180053006  mov     rcx, [rsi]
0x180053009  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x18005300e  mov     rax, [rax]
0x180053011  mov     [rbp+0A0h+var_120], rax
0x180053015  mov     rax, [rax]
0x180053018  mov     [rbp+0A0h+var_118], rax
0x18005301c  mov     rcx, [rsp+1A0h+var_128]
0x180053021  mov     [rsp+1A0h+var_128], r12
0x180053026  test    rcx, rcx
0x180053029  jz      short loc_180053038
0x18005302b  mov     rax, [rcx]
0x18005302e  mov     rax, [rax+10h]
0x180053032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053037  nop
0x180053038  mov     rdx, rdi
0x18005303b  lea     rcx, [rbp+0A0h+var_70]
0x18005303f  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180053044  mov     rsi, rax
0x180053047  cmp     qword ptr [rax+18h], 7
0x18005304c  jbe     short loc_180053051
0x18005304e  mov     rsi, [rax]
0x180053051  mov     [rbp+0A0h+string], r12
0x180053055  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180053059  mov     rbx, rdi
0x18005305c  inc     rbx
0x18005305f  cmp     [rsi+rbx*2], r12w
0x180053064  jnz     short loc_18005305C
0x180053066  mov     eax, 0FFFFFFFFh
0x18005306b  cmp     rbx, rax
0x18005306e  ja      loc_18005333B
0x180053074  mov     ecx, ebx; unsigned int
0x180053076  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005307b  lea     edx, [rax-1]
0x18005307e  cmp     ebx, eax
0x180053080  cmovb   edx, ebx; length
0x180053083  lea     r9, [rbp+0A0h+string]; string
0x180053087  lea     r8, [rbp+0A0h+hstringHeader]; hstringHeader
0x18005308b  mov     rcx, rsi; sourceString
0x18005308e  call    cs:__imp_WindowsCreateStringReference
0x180053094  test    eax, eax
0x180053096  jns     short loc_1800530AB
0x180053098  xor     r9d, r9d; lpArguments
0x18005309b  xor     r8d, r8d; nNumberOfArguments
0x18005309e  lea     edx, [r9+1]; dwExceptionFlags
0x1800530a2  mov     ecx, eax; dwExceptionCode
0x1800530a4  call    cs:__imp_RaiseException
0x1800530aa  nop
0x1800530ab  lea     rsi, [r15+40h]
0x1800530af  cmp     qword ptr [rsi+18h], 7
0x1800530b4  jbe     short loc_1800530B9
0x1800530b6  mov     rsi, [rsi]
0x1800530b9  mov     [rbp+0A0h+var_98], r12
0x1800530bd  mov     rbx, rdi
0x1800530c0  inc     rbx
0x1800530c3  cmp     [rsi+rbx*2], r12w
0x1800530c8  jnz     short loc_1800530C0
0x1800530ca  mov     eax, 0FFFFFFFFh
0x1800530cf  cmp     rbx, rax
0x1800530d2  ja      loc_180053325
0x1800530d8  mov     rax, [rbp+0A0h+string]
0x1800530dc  mov     [rbp+0A0h+var_110], rax
0x1800530e0  mov     r13, [r13+18h]
0x1800530e4  mov     ecx, ebx; unsigned int
0x1800530e6  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800530eb  lea     edx, [rax-1]
0x1800530ee  cmp     ebx, eax
0x1800530f0  cmovb   edx, ebx; length
0x1800530f3  lea     r9, [rbp+0A0h+var_98]; string
0x1800530f7  lea     r8, [rbp+0A0h+var_B0]; hstringHeader
0x1800530fb  mov     rcx, rsi; sourceString
0x1800530fe  call    cs:__imp_WindowsCreateStringReference
0x180053104  test    eax, eax
0x180053106  jns     short loc_18005311B
0x180053108  xor     r9d, r9d; lpArguments
0x18005310b  xor     r8d, r8d; nNumberOfArguments
0x18005310e  lea     edx, [r9+1]; dwExceptionFlags
0x180053112  mov     ecx, eax; dwExceptionCode
0x180053114  call    cs:__imp_RaiseException
0x18005311a  nop
0x18005311b  lea     rsi, [r15+20h]
0x18005311f  cmp     qword ptr [rsi+18h], 7
0x180053124  jbe     short loc_180053129
0x180053126  mov     rsi, [rsi]
0x180053129  mov     [rbp+0A0h+var_B8], r12
0x18005312d  mov     rbx, rdi
0x180053130  inc     rbx
0x180053133  cmp     [rsi+rbx*2], r12w
0x180053138  jnz     short loc_180053130
0x18005313a  mov     eax, 0FFFFFFFFh
0x18005313f  cmp     rbx, rax
0x180053142  ja      loc_18005330F
0x180053148  mov     r12, [rbp+0A0h+var_98]
0x18005314c  mov     ecx, ebx; unsigned int
0x18005314e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180053153  lea     edx, [rax-1]
0x180053156  cmp     ebx, eax
0x180053158  cmovb   edx, ebx; length
0x18005315b  lea     r9, [rbp+0A0h+var_B8]; string
0x18005315f  lea     r8, [rbp+0A0h+var_D0]; hstringHeader
0x180053163  mov     rcx, rsi; sourceString
0x180053166  call    cs:__imp_WindowsCreateStringReference
0x18005316c  xor     esi, esi
0x18005316e  test    eax, eax
0x180053170  jns     short loc_180053184
0x180053172  xor     r9d, r9d; lpArguments
0x180053175  xor     r8d, r8d; nNumberOfArguments
0x180053178  lea     edx, [rsi+1]; dwExceptionFlags
0x18005317b  mov     ecx, eax; dwExceptionCode
0x18005317d  call    cs:__imp_RaiseException
0x180053183  nop
0x180053184  cmp     qword ptr [r15+18h], 7
0x180053189  jbe     short loc_18005318E
0x18005318b  mov     r15, [r15]
0x18005318e  mov     [rbp+0A0h+var_D8], rsi
0x180053192  inc     rdi
0x180053195  cmp     [r15+rdi*2], si
0x18005319a  jnz     short loc_180053192
0x18005319c  mov     eax, 0FFFFFFFFh
0x1800531a1  cmp     rdi, rax
0x1800531a4  ja      loc_1800532F9
0x1800531aa  mov     rbx, [rbp+0A0h+var_B8]
0x1800531ae  mov     ecx, edi; unsigned int
0x1800531b0  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800531b5  lea     edx, [rax-1]
0x1800531b8  cmp     edi, eax
0x1800531ba  cmovb   edx, edi; length
0x1800531bd  lea     r9, [rbp+0A0h+var_D8]; string
0x1800531c1  lea     r8, [rbp+0A0h+var_F0]; hstringHeader
0x1800531c5  mov     rcx, r15; sourceString
0x1800531c8  call    cs:__imp_WindowsCreateStringReference
0x1800531ce  test    eax, eax
0x1800531d0  jns     short loc_1800531E5
0x1800531d2  xor     r9d, r9d; lpArguments
0x1800531d5  xor     r8d, r8d; nNumberOfArguments
0x1800531d8  lea     edx, [r9+1]; dwExceptionFlags
0x1800531dc  mov     ecx, eax; dwExceptionCode
0x1800531de  call    cs:__imp_RaiseException
0x1800531e4  nop
0x1800531e5  mov     rdx, [rbp+0A0h+var_108]
0x1800531e9  mov     rax, [rdx+18h]
0x1800531ed  test    rax, rax
0x1800531f0  jz      short loc_1800531F7
0x1800531f2  mov     r8, [rax]
0x1800531f5  jmp     short loc_1800531FA
0x1800531f7  mov     r8, rsi
0x1800531fa  lea     rax, [rsp+1A0h+var_128]
0x1800531ff  mov     [rsp+1A0h+var_148], rax
0x180053204  mov     rax, [rbp+0A0h+var_110]
0x180053208  mov     [rsp+1A0h+var_150], rax
0x18005320d  mov     eax, [rsp+1A0h+var_130]
0x180053211  mov     [rsp+1A0h+var_158], eax
0x180053215  mov     [rsp+1A0h+var_160], r14
0x18005321a  mov     rax, [rbp+0A0h+arg_20]
0x180053221  mov     [rsp+1A0h+var_168], rax
0x180053226  mov     [rsp+1A0h+var_170], r13
0x18005322b  mov     [rsp+1A0h+var_178], r12
0x180053230  mov     qword ptr [rsp+1A0h+var_180], rbx; int
0x180053235  mov     r9, [rbp+0A0h+var_D8]
0x180053239  mov     edx, [rdx+10h]
0x18005323c  mov     rcx, [rbp+0A0h+var_120]
0x180053240  mov     rax, [rbp+0A0h+var_118]
0x180053244  mov     rax, [rax+58h]
0x180053248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005324d  mov     rcx, [rbp+0A8h]; this
0x180053254  test    eax, eax
0x180053256  jns     short loc_18005326D
0x180053258  mov     r9d, eax; char *
0x18005325b  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180053262  mov     edx, 5E4h; void *
0x180053267  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005326d  mov     [rbp+0A0h+var_D8], rsi
0x180053271  mov     [rbp+0A0h+var_B8], rsi
0x180053275  mov     [rbp+0A0h+var_98], rsi
0x180053279  mov     [rbp+0A0h+string], rsi
0x18005327d  mov     rdx, [rbp+0A0h+var_58]
0x180053281  cmp     rdx, 7
0x180053285  jbe     short loc_180053298
0x180053287  lea     rdx, ds:2[rdx*2]
0x18005328f  mov     rcx, [rbp+0A0h+var_70]
0x180053293  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180053298  mov     rdx, [rsp+1A0h+var_128]; struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *
0x18005329d  mov     rbx, [rbp+0A0h+var_100]
0x1800532a1  mov     rcx, rbx; this
0x1800532a4  call    ??0cloud_store_save_result@wil@@QEAA@PEAUICloudStoreSaveResult@Cloud@Storage@Internal@Windows@@@Z; wil::cloud_store_save_result::cloud_store_save_result(Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *)
0x1800532a9  nop
0x1800532aa  mov     rcx, [rsp+1A0h+var_128]
0x1800532af  test    rcx, rcx
0x1800532b2  jz      short loc_1800532C1
0x1800532b4  mov     rax, [rcx]
0x1800532b7  mov     rax, [rax+10h]
0x1800532bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532c0  nop
0x1800532c1  test    r14, r14
0x1800532c4  jz      short loc_1800532D6
0x1800532c6  mov     rdx, [r14]
0x1800532c9  mov     rcx, r14
0x1800532cc  mov     rax, [rdx+10h]
0x1800532d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532d5  nop
0x1800532d6  mov     rax, rbx
0x1800532d9  mov     rcx, [rbp+0A0h+var_50]
0x1800532dd  xor     rcx, rsp; StackCookie
0x1800532e0  call    __security_check_cookie
0x1800532e5  add     rsp, 168h
0x1800532ec  pop     r15
0x1800532ee  pop     r14
0x1800532f0  pop     r13
0x1800532f2  pop     r12
0x1800532f4  pop     rdi
0x1800532f5  pop     rsi
0x1800532f6  pop     rbx
0x1800532f7  pop     rbp
0x1800532f8  retn
0x1800532f9  xor     r9d, r9d; lpArguments
0x1800532fc  xor     r8d, r8d; nNumberOfArguments
0x1800532ff  lea     edx, [r9+1]; dwExceptionFlags
0x180053303  mov     ecx, 80070216h; dwExceptionCode
0x180053308  call    cs:__imp_RaiseException
0x18005330e  nop
0x18005330f  xor     r9d, r9d; lpArguments
0x180053312  xor     r8d, r8d; nNumberOfArguments
0x180053315  lea     edx, [r9+1]; dwExceptionFlags
0x180053319  mov     ecx, 80070216h; dwExceptionCode
0x18005331e  call    cs:__imp_RaiseException
0x180053324  nop
0x180053325  xor     r9d, r9d; lpArguments
0x180053328  xor     r8d, r8d; nNumberOfArguments
0x18005332b  lea     edx, [r9+1]; dwExceptionFlags
0x18005332f  mov     ecx, 80070216h; dwExceptionCode
0x180053334  call    cs:__imp_RaiseException
0x18005333a  nop
0x18005333b  xor     r9d, r9d; lpArguments
0x18005333e  xor     r8d, r8d; nNumberOfArguments
0x180053341  lea     edx, [r9+1]; dwExceptionFlags
0x180053345  mov     ecx, 80070216h; dwExceptionCode
0x18005334a  call    cs:__imp_RaiseException
```
