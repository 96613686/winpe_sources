# wil::cloud_store::call_save<Windows::Data::PlaceholderTileCollection>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_data<Windows::Data::PlaceholderTileCollection> const &,unsigned __int64,wil::cloud_store_save_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800526a8`
- end: `0x180052ab6`
- name: `??$call_save@UPlaceholderTileCollection@Data@Windows@@@cloud_store@wil@@AEAA?AVcloud_store_save_result@1@AEBUvalidated_data_reference@01@AEBV?$cloud_store_data@UPlaceholderTileCollection@Data@Windows@@@1@_KW4cloud_store_save_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1038`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802d9d4c`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x18002dde0`
- `0x1800526a8`
- `0x180052b9c`
- `0x180053358`
- `0x1800533b8`
- `0x180056798`
- `0x1800574a8`
- `0x180147be8`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005280b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005287b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800528e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052945`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052a6d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052a83`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052a99`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052aaf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005280b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005287b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800528e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052945`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052a6d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052a83`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052a99`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052aaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800527f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052865`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800528cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005292f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800527f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052865`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800528cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005292f`

## pseudocode

```c
wil::cloud_store_save_result *__fastcall wil::cloud_store::call_save<Windows::Data::PlaceholderTileCollection>(
        _QWORD *a1,
        wil::cloud_store_save_result *a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7)
{
  __int64 *v10; // rax
  char v11; // bl
  __int64 v12; // r14
  struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *v13; // rcx
  __int64 v14; // rax
  const WCHAR *v15; // rsi
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rbx
  unsigned int v18; // eax
  UINT32 v19; // edx
  HRESULT v20; // eax
  const WCHAR *v21; // rsi
  unsigned __int64 v22; // rbx
  unsigned int v23; // eax
  UINT32 v24; // edx
  HRESULT v25; // eax
  const WCHAR *v26; // rsi
  unsigned __int64 v27; // rbx
  unsigned int v28; // eax
  UINT32 v29; // edx
  HRESULT v30; // eax
  int v31; // ebx
  unsigned int v32; // eax
  UINT32 v33; // edx
  HRESULT v34; // eax
  __int64 *v35; // rax
  __int64 v36; // r8
  int v37; // eax
  wil::cloud_store_save_result *v38; // rbx
  __int64 *v40; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *v41; // [rsp+80h] [rbp-80h]
  HSTRING v42; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v43; // [rsp+90h] [rbp-70h]
  __int64 v44; // [rsp+98h] [rbp-68h]
  wil::cloud_store_save_result *v45; // [rsp+A0h] [rbp-60h]
  __int64 v46; // [rsp+A8h] [rbp-58h]
  HSTRING_HEADER v47; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v48; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING_HEADER v49; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING v50; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING_HEADER v51; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING v52; // [rsp+108h] [rbp+8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+110h] [rbp+10h] BYREF
  HSTRING string; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v55[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v56; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v45 = a2;
  v43 = a1;
  LODWORD(v40) = 0;
  wil::cloud_store::convert_cloud_store_save_options(a6);
  if ( (a6 & 8) != 0 )
  {
    v40 = 0;
    v10 = (__int64 *)&v40;
    v11 = 1;
    v12 = 0;
  }
  else
  {
    v10 = (__int64 *)wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::PlaceholderTileCollection>>(
                       &v42,
                       a4);
    v11 = 2;
    v12 = *v10;
  }
  *v10 = 0;
  v46 = v12;
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v42);
  }
  if ( (v11 & 1) != 0 )
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v40);
  v41 = 0;
  v40 = *(__int64 **)wil::details::shared_cloud_store_state::get_cloud_store(*a1);
  v44 = *v40;
  v13 = v41;
  v41 = 0;
  if ( v13 )
    (*(void (__fastcall **)(struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = wil::cloud_store::widen_string(v55, a7);
  v15 = (const WCHAR *)v14;
  if ( *(_QWORD *)(v14 + 24) > 7u )
    v15 = *(const WCHAR **)v14;
  string = 0;
  v16 = -1;
  v17 = -1;
  do
    ++v17;
  while ( v15[v17] );
  if ( v17 > 0xFFFFFFFF )
  {
LABEL_61:
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x180052AB5LL);
  }
  v18 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v17);
  v19 = v18 - 1;
  if ( (unsigned int)v17 < v18 )
    v19 = v17;
  v20 = WindowsCreateStringReference(v15, v19, &hstringHeader, &string);
  if ( v20 < 0 )
    RaiseException(v20, 1u, 0, 0);
  v21 = (const WCHAR *)(a3 + 8);
  if ( (unsigned __int64)a3[11] > 7 )
    v21 = *(const WCHAR **)v21;
  v52 = 0;
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  if ( v22 > 0xFFFFFFFF )
  {
LABEL_60:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_61;
  }
  v42 = string;
  v23 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v22);
  v24 = v23 - 1;
  if ( (unsigned int)v22 < v23 )
    v24 = v22;
  v25 = WindowsCreateStringReference(v21, v24, &v51, &v52);
  if ( v25 < 0 )
    RaiseException(v25, 1u, 0, 0);
  v26 = (const WCHAR *)(a3 + 4);
  if ( (unsigned __int64)a3[7] > 7 )
    v26 = *(const WCHAR **)v26;
  v50 = 0;
  v27 = -1;
  do
    ++v27;
  while ( v26[v27] );
  if ( v27 > 0xFFFFFFFF )
  {
LABEL_59:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_60;
  }
  v28 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v27);
  v29 = v28 - 1;
  if ( (unsigned int)v27 < v28 )
    v29 = v27;
  v30 = WindowsCreateStringReference(v26, v29, &v49, &v50);
  if ( v30 < 0 )
    RaiseException(v30, 1u, 0, 0);
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (__int64 *)*a3;
  v48 = 0;
  do
    ++v16;
  while ( *((_WORD *)a3 + v16) );
  if ( v16 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_59;
  }
  v31 = (int)v50;
  v32 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v16);
  v33 = v32 - 1;
  if ( (unsigned int)v16 < v32 )
    v33 = v16;
  v34 = WindowsCreateStringReference((PCWSTR)a3, v33, &v47, &v48);
  if ( v34 < 0 )
    RaiseException(v34, 1u, 0, 0);
  v35 = (__int64 *)v43[3];
  if ( v35 )
    v36 = *v35;
  else
    v36 = 0;
  v37 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, HSTRING))(v44 + 88))(
          v40,
          *((unsigned int *)v43 + 4),
          v36,
          v48);
  if ( v37 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5E4,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v37,
      v31);
  v48 = 0;
  v50 = 0;
  v52 = 0;
  string = 0;
  if ( v56 > 7 )
    std::_Deallocate<16>(v55[0], 2 * v56 + 2);
  v38 = v45;
  wil::cloud_store_save_result::cloud_store_save_result(v45, v41);
  if ( v41 )
    (*(void (__fastcall **)(struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return v38;
}

```

## disassembly

```asm
0x1800526a8  push    rbp
0x1800526aa  push    rbx
0x1800526ab  push    rsi
0x1800526ac  push    rdi
0x1800526ad  push    r12
0x1800526af  push    r13
0x1800526b1  push    r14
0x1800526b3  push    r15
0x1800526b5  lea     rbp, [rsp-68h]
0x1800526ba  sub     rsp, 168h
0x1800526c1  mov     rax, cs:__security_cookie
0x1800526c8  xor     rax, rsp
0x1800526cb  mov     [rbp+0A0h+var_50], rax
0x1800526cf  mov     r13, r9
0x1800526d2  mov     r15, r8
0x1800526d5  mov     [rbp+0A0h+var_100], rdx
0x1800526d9  mov     rsi, rcx
0x1800526dc  mov     [rbp+0A0h+var_110], rcx
0x1800526e0  mov     rdi, [rbp+0A0h+arg_30]
0x1800526e7  xor     r12d, r12d
0x1800526ea  mov     dword ptr [rsp+1A0h+var_128], r12d
0x1800526ef  mov     ecx, [rbp+0A0h+arg_28]
0x1800526f5  call    ?convert_cloud_store_save_options@cloud_store@wil@@CA?AW4SaveOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_save_options@2@@Z; wil::cloud_store::convert_cloud_store_save_options(wil::cloud_store_save_options)
0x1800526fa  mov     [rsp+1A0h+var_130], eax
0x1800526fe  cmp     [r13+21h], r12b
0x180052702  jnz     short loc_18005270A
0x180052704  cmp     [r13+18h], r12
0x180052708  jnz     short loc_180052711
0x18005270a  or      eax, 8
0x18005270d  mov     [rsp+1A0h+var_130], eax
0x180052711  test    byte ptr [rbp+0A0h+arg_28], 8
0x180052718  jz      short loc_18005272E
0x18005271a  mov     [rsp+1A0h+var_128], r12
0x18005271f  lea     rax, [rsp+1A0h+var_128]
0x180052724  mov     ebx, 1
0x180052729  mov     r14, r12
0x18005272c  jmp     short loc_180052742
0x18005272e  mov     rdx, r13
0x180052731  lea     rcx, [rbp+0A0h+var_118]
0x180052735  call    ??$marshal@V?$cloud_store_data@UPlaceholderTileCollection@Data@Windows@@@wil@@@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@AEBV?$cloud_store_data@UPlaceholderTileCollection@Data@Windows@@@1@@Z; wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::PlaceholderTileCollection>>(wil::cloud_store_data<Windows::Data::PlaceholderTileCollection> const &)
0x18005273a  mov     ebx, 2
0x18005273f  mov     r14, [rax]
0x180052742  mov     [rax], r12
0x180052745  mov     [rbp+0A0h+var_F8], r14
0x180052749  test    bl, 2
0x18005274c  jz      short loc_18005275B
0x18005274e  and     ebx, 0FFFFFFFDh
0x180052751  lea     rcx, [rbp+0A0h+var_118]; void *
0x180052755  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18005275a  nop
0x18005275b  test    bl, 1
0x18005275e  jz      short loc_18005276A
0x180052760  lea     rcx, [rsp+1A0h+var_128]; void *
0x180052765  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18005276a  mov     [rbp+0A0h+var_120], r12
0x18005276e  mov     rcx, [rsi]
0x180052771  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180052776  mov     rax, [rax]
0x180052779  mov     [rsp+1A0h+var_128], rax
0x18005277e  mov     rax, [rax]
0x180052781  mov     [rbp+0A0h+var_108], rax
0x180052785  mov     rcx, [rbp+0A0h+var_120]
0x180052789  mov     [rbp+0A0h+var_120], r12
0x18005278d  test    rcx, rcx
0x180052790  jz      short loc_18005279F
0x180052792  mov     rax, [rcx]
0x180052795  mov     rax, [rax+10h]
0x180052799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005279e  nop
0x18005279f  mov     rdx, rdi
0x1800527a2  lea     rcx, [rbp+0A0h+var_70]
0x1800527a6  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x1800527ab  mov     rsi, rax
0x1800527ae  cmp     qword ptr [rax+18h], 7
0x1800527b3  jbe     short loc_1800527B8
0x1800527b5  mov     rsi, [rax]
0x1800527b8  mov     [rbp+0A0h+string], r12
0x1800527bc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800527c0  mov     rbx, rdi
0x1800527c3  inc     rbx
0x1800527c6  cmp     [rsi+rbx*2], r12w
0x1800527cb  jnz     short loc_1800527C3
0x1800527cd  mov     eax, 0FFFFFFFFh
0x1800527d2  cmp     rbx, rax
0x1800527d5  ja      loc_180052AA0
0x1800527db  mov     ecx, ebx; unsigned int
0x1800527dd  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800527e2  lea     edx, [rax-1]
0x1800527e5  cmp     ebx, eax
0x1800527e7  cmovb   edx, ebx; length
0x1800527ea  lea     r9, [rbp+0A0h+string]; string
0x1800527ee  lea     r8, [rbp+0A0h+hstringHeader]; hstringHeader
0x1800527f2  mov     rcx, rsi; sourceString
0x1800527f5  call    cs:__imp_WindowsCreateStringReference
0x1800527fb  test    eax, eax
0x1800527fd  jns     short loc_180052812
0x1800527ff  xor     r9d, r9d; lpArguments
0x180052802  xor     r8d, r8d; nNumberOfArguments
0x180052805  lea     edx, [r9+1]; dwExceptionFlags
0x180052809  mov     ecx, eax; dwExceptionCode
0x18005280b  call    cs:__imp_RaiseException
0x180052811  nop
0x180052812  lea     rsi, [r15+40h]
0x180052816  cmp     qword ptr [rsi+18h], 7
0x18005281b  jbe     short loc_180052820
0x18005281d  mov     rsi, [rsi]
0x180052820  mov     [rbp+0A0h+var_98], r12
0x180052824  mov     rbx, rdi
0x180052827  inc     rbx
0x18005282a  cmp     [rsi+rbx*2], r12w
0x18005282f  jnz     short loc_180052827
0x180052831  mov     eax, 0FFFFFFFFh
0x180052836  cmp     rbx, rax
0x180052839  ja      loc_180052A8A
0x18005283f  mov     rax, [rbp+0A0h+string]
0x180052843  mov     [rbp+0A0h+var_118], rax
0x180052847  mov     r13, [r13+18h]
0x18005284b  mov     ecx, ebx; unsigned int
0x18005284d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180052852  lea     edx, [rax-1]
0x180052855  cmp     ebx, eax
0x180052857  cmovb   edx, ebx; length
0x18005285a  lea     r9, [rbp+0A0h+var_98]; string
0x18005285e  lea     r8, [rbp+0A0h+var_B0]; hstringHeader
0x180052862  mov     rcx, rsi; sourceString
0x180052865  call    cs:__imp_WindowsCreateStringReference
0x18005286b  test    eax, eax
0x18005286d  jns     short loc_180052882
0x18005286f  xor     r9d, r9d; lpArguments
0x180052872  xor     r8d, r8d; nNumberOfArguments
0x180052875  lea     edx, [r9+1]; dwExceptionFlags
0x180052879  mov     ecx, eax; dwExceptionCode
0x18005287b  call    cs:__imp_RaiseException
0x180052881  nop
0x180052882  lea     rsi, [r15+20h]
0x180052886  cmp     qword ptr [rsi+18h], 7
0x18005288b  jbe     short loc_180052890
0x18005288d  mov     rsi, [rsi]
0x180052890  mov     [rbp+0A0h+var_B8], r12
0x180052894  mov     rbx, rdi
0x180052897  inc     rbx
0x18005289a  cmp     [rsi+rbx*2], r12w
0x18005289f  jnz     short loc_180052897
0x1800528a1  mov     eax, 0FFFFFFFFh
0x1800528a6  cmp     rbx, rax
0x1800528a9  ja      loc_180052A74
0x1800528af  mov     r12, [rbp+0A0h+var_98]
0x1800528b3  mov     ecx, ebx; unsigned int
0x1800528b5  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800528ba  lea     edx, [rax-1]
0x1800528bd  cmp     ebx, eax
0x1800528bf  cmovb   edx, ebx; length
0x1800528c2  lea     r9, [rbp+0A0h+var_B8]; string
0x1800528c6  lea     r8, [rbp+0A0h+var_D0]; hstringHeader
0x1800528ca  mov     rcx, rsi; sourceString
0x1800528cd  call    cs:__imp_WindowsCreateStringReference
0x1800528d3  xor     esi, esi
0x1800528d5  test    eax, eax
0x1800528d7  jns     short loc_1800528EB
0x1800528d9  xor     r9d, r9d; lpArguments
0x1800528dc  xor     r8d, r8d; nNumberOfArguments
0x1800528df  lea     edx, [rsi+1]; dwExceptionFlags
0x1800528e2  mov     ecx, eax; dwExceptionCode
0x1800528e4  call    cs:__imp_RaiseException
0x1800528ea  nop
0x1800528eb  cmp     qword ptr [r15+18h], 7
0x1800528f0  jbe     short loc_1800528F5
0x1800528f2  mov     r15, [r15]
0x1800528f5  mov     [rbp+0A0h+var_D8], rsi
0x1800528f9  inc     rdi
0x1800528fc  cmp     [r15+rdi*2], si
0x180052901  jnz     short loc_1800528F9
0x180052903  mov     eax, 0FFFFFFFFh
0x180052908  cmp     rdi, rax
0x18005290b  ja      loc_180052A5E
0x180052911  mov     rbx, [rbp+0A0h+var_B8]
0x180052915  mov     ecx, edi; unsigned int
0x180052917  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005291c  lea     edx, [rax-1]
0x18005291f  cmp     edi, eax
0x180052921  cmovb   edx, edi; length
0x180052924  lea     r9, [rbp+0A0h+var_D8]; string
0x180052928  lea     r8, [rbp+0A0h+var_F0]; hstringHeader
0x18005292c  mov     rcx, r15; sourceString
0x18005292f  call    cs:__imp_WindowsCreateStringReference
0x180052935  test    eax, eax
0x180052937  jns     short loc_18005294C
0x180052939  xor     r9d, r9d; lpArguments
0x18005293c  xor     r8d, r8d; nNumberOfArguments
0x18005293f  lea     edx, [r9+1]; dwExceptionFlags
0x180052943  mov     ecx, eax; dwExceptionCode
0x180052945  call    cs:__imp_RaiseException
0x18005294b  nop
0x18005294c  mov     rdx, [rbp+0A0h+var_110]
0x180052950  mov     rax, [rdx+18h]
0x180052954  test    rax, rax
0x180052957  jz      short loc_18005295E
0x180052959  mov     r8, [rax]
0x18005295c  jmp     short loc_180052961
0x18005295e  mov     r8, rsi
0x180052961  lea     rax, [rbp+0A0h+var_120]
0x180052965  mov     [rsp+1A0h+var_148], rax
0x18005296a  mov     rax, [rbp+0A0h+var_118]
0x18005296e  mov     [rsp+1A0h+var_150], rax
0x180052973  mov     eax, [rsp+1A0h+var_130]
0x180052977  mov     [rsp+1A0h+var_158], eax
0x18005297b  mov     [rsp+1A0h+var_160], r14
0x180052980  mov     rax, [rbp+0A0h+arg_20]
0x180052987  mov     [rsp+1A0h+var_168], rax
0x18005298c  mov     [rsp+1A0h+var_170], r13
0x180052991  mov     [rsp+1A0h+var_178], r12
0x180052996  mov     qword ptr [rsp+1A0h+var_180], rbx; int
0x18005299b  mov     r9, [rbp+0A0h+var_D8]
0x18005299f  mov     edx, [rdx+10h]
0x1800529a2  mov     rcx, [rsp+1A0h+var_128]
0x1800529a7  mov     rax, [rbp+0A0h+var_108]
0x1800529ab  mov     rax, [rax+58h]
0x1800529af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529b4  mov     rcx, [rbp+0A8h]; this
0x1800529bb  test    eax, eax
0x1800529bd  jns     short loc_1800529D4
0x1800529bf  mov     r9d, eax; char *
0x1800529c2  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800529c9  mov     edx, 5E4h; void *
0x1800529ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800529d4  mov     [rbp+0A0h+var_D8], rsi
0x1800529d8  mov     [rbp+0A0h+var_B8], rsi
0x1800529dc  mov     [rbp+0A0h+var_98], rsi
0x1800529e0  mov     [rbp+0A0h+string], rsi
0x1800529e4  mov     rdx, [rbp+0A0h+var_58]
0x1800529e8  cmp     rdx, 7
0x1800529ec  jbe     short loc_1800529FF
0x1800529ee  lea     rdx, ds:2[rdx*2]
0x1800529f6  mov     rcx, [rbp+0A0h+var_70]
0x1800529fa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800529ff  mov     rdx, [rbp+0A0h+var_120]; struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *
0x180052a03  mov     rbx, [rbp+0A0h+var_100]
0x180052a07  mov     rcx, rbx; this
0x180052a0a  call    ??0cloud_store_save_result@wil@@QEAA@PEAUICloudStoreSaveResult@Cloud@Storage@Internal@Windows@@@Z; wil::cloud_store_save_result::cloud_store_save_result(Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *)
0x180052a0f  nop
0x180052a10  mov     rcx, [rbp+0A0h+var_120]
0x180052a14  test    rcx, rcx
0x180052a17  jz      short loc_180052A26
0x180052a19  mov     rax, [rcx]
0x180052a1c  mov     rax, [rax+10h]
0x180052a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a25  nop
0x180052a26  test    r14, r14
0x180052a29  jz      short loc_180052A3B
0x180052a2b  mov     rdx, [r14]
0x180052a2e  mov     rcx, r14
0x180052a31  mov     rax, [rdx+10h]
0x180052a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a3a  nop
0x180052a3b  mov     rax, rbx
0x180052a3e  mov     rcx, [rbp+0A0h+var_50]
0x180052a42  xor     rcx, rsp; StackCookie
0x180052a45  call    __security_check_cookie
0x180052a4a  add     rsp, 168h
0x180052a51  pop     r15
0x180052a53  pop     r14
0x180052a55  pop     r13
0x180052a57  pop     r12
0x180052a59  pop     rdi
0x180052a5a  pop     rsi
0x180052a5b  pop     rbx
0x180052a5c  pop     rbp
0x180052a5d  retn
0x180052a5e  xor     r9d, r9d; lpArguments
0x180052a61  xor     r8d, r8d; nNumberOfArguments
0x180052a64  lea     edx, [r9+1]; dwExceptionFlags
0x180052a68  mov     ecx, 80070216h; dwExceptionCode
0x180052a6d  call    cs:__imp_RaiseException
0x180052a73  nop
0x180052a74  xor     r9d, r9d; lpArguments
0x180052a77  xor     r8d, r8d; nNumberOfArguments
0x180052a7a  lea     edx, [r9+1]; dwExceptionFlags
0x180052a7e  mov     ecx, 80070216h; dwExceptionCode
0x180052a83  call    cs:__imp_RaiseException
0x180052a89  nop
0x180052a8a  xor     r9d, r9d; lpArguments
0x180052a8d  xor     r8d, r8d; nNumberOfArguments
0x180052a90  lea     edx, [r9+1]; dwExceptionFlags
0x180052a94  mov     ecx, 80070216h; dwExceptionCode
0x180052a99  call    cs:__imp_RaiseException
0x180052a9f  nop
0x180052aa0  xor     r9d, r9d; lpArguments
0x180052aa3  xor     r8d, r8d; nNumberOfArguments
0x180052aa6  lea     edx, [r9+1]; dwExceptionFlags
0x180052aaa  mov     ecx, 80070216h; dwExceptionCode
0x180052aaf  call    cs:__imp_RaiseException
```
