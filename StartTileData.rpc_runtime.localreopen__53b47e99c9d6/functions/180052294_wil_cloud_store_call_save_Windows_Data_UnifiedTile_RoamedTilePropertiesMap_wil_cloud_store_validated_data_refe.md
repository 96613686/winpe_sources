# wil::cloud_store::call_save<Windows::Data::UnifiedTile::RoamedTilePropertiesMap>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_data<Windows::Data::UnifiedTile::RoamedTilePropertiesMap> const &,unsigned __int64,wil::cloud_store_save_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180052294`
- end: `0x1800526a2`
- name: `??$call_save@URoamedTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@AEAA?AVcloud_store_save_result@1@AEBUvalidated_data_reference@01@AEBV?$cloud_store_data@URoamedTilePropertiesMap@UnifiedTile@Data@Windows@@@1@_KW4cloud_store_save_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1038`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802d96a8`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x18002dde0`
- `0x180052178`
- `0x180052294`
- `0x180053358`
- `0x1800533b8`
- `0x180056798`
- `0x1800574a8`
- `0x180147be8`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800523f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052467`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800524d0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052531`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052659`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005266f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052685`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005269b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800523f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052467`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800524d0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052531`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052659`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005266f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052685`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005269b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800523e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800524b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005251b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800523e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800524b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005251b`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
wil::cloud_store_save_result *__fastcall wil::cloud_store::call_save<Windows::Data::UnifiedTile::RoamedTilePropertiesMap>(
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
    v10 = (__int64 *)wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::UnifiedTile::RoamedTilePropertiesMap>>(
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
    JUMPOUT(0x1800526A1LL);
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
0x180052294  push    rbp
0x180052296  push    rbx
0x180052297  push    rsi
0x180052298  push    rdi
0x180052299  push    r12
0x18005229b  push    r13
0x18005229d  push    r14
0x18005229f  push    r15
0x1800522a1  lea     rbp, [rsp-68h]
0x1800522a6  sub     rsp, 168h
0x1800522ad  mov     rax, cs:__security_cookie
0x1800522b4  xor     rax, rsp
0x1800522b7  mov     [rbp+0A0h+var_50], rax
0x1800522bb  mov     r13, r9
0x1800522be  mov     r15, r8
0x1800522c1  mov     [rbp+0A0h+var_100], rdx
0x1800522c5  mov     rsi, rcx
0x1800522c8  mov     [rbp+0A0h+var_110], rcx
0x1800522cc  mov     rdi, [rbp+0A0h+arg_30]
0x1800522d3  xor     r12d, r12d
0x1800522d6  mov     dword ptr [rsp+1A0h+var_128], r12d
0x1800522db  mov     ecx, [rbp+0A0h+arg_28]
0x1800522e1  call    ?convert_cloud_store_save_options@cloud_store@wil@@CA?AW4SaveOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_save_options@2@@Z; wil::cloud_store::convert_cloud_store_save_options(wil::cloud_store_save_options)
0x1800522e6  mov     [rsp+1A0h+var_130], eax
0x1800522ea  cmp     [r13+21h], r12b
0x1800522ee  jnz     short loc_1800522F6
0x1800522f0  cmp     [r13+18h], r12
0x1800522f4  jnz     short loc_1800522FD
0x1800522f6  or      eax, 8
0x1800522f9  mov     [rsp+1A0h+var_130], eax
0x1800522fd  test    byte ptr [rbp+0A0h+arg_28], 8
0x180052304  jz      short loc_18005231A
0x180052306  mov     [rsp+1A0h+var_128], r12
0x18005230b  lea     rax, [rsp+1A0h+var_128]
0x180052310  mov     ebx, 1
0x180052315  mov     r14, r12
0x180052318  jmp     short loc_18005232E
0x18005231a  mov     rdx, r13
0x18005231d  lea     rcx, [rbp+0A0h+var_118]
0x180052321  call    ??$marshal@V?$cloud_store_data@URoamedTilePropertiesMap@UnifiedTile@Data@Windows@@@wil@@@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@AEBV?$cloud_store_data@URoamedTilePropertiesMap@UnifiedTile@Data@Windows@@@1@@Z; wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::UnifiedTile::RoamedTilePropertiesMap>>(wil::cloud_store_data<Windows::Data::UnifiedTile::RoamedTilePropertiesMap> const &)
0x180052326  mov     ebx, 2
0x18005232b  mov     r14, [rax]
0x18005232e  mov     [rax], r12
0x180052331  mov     [rbp+0A0h+var_F8], r14
0x180052335  test    bl, 2
0x180052338  jz      short loc_180052347
0x18005233a  and     ebx, 0FFFFFFFDh
0x18005233d  lea     rcx, [rbp+0A0h+var_118]; void *
0x180052341  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180052346  nop
0x180052347  test    bl, 1
0x18005234a  jz      short loc_180052356
0x18005234c  lea     rcx, [rsp+1A0h+var_128]; void *
0x180052351  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180052356  mov     [rbp+0A0h+var_120], r12
0x18005235a  mov     rcx, [rsi]
0x18005235d  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180052362  mov     rax, [rax]
0x180052365  mov     [rsp+1A0h+var_128], rax
0x18005236a  mov     rax, [rax]
0x18005236d  mov     [rbp+0A0h+var_108], rax
0x180052371  mov     rcx, [rbp+0A0h+var_120]
0x180052375  mov     [rbp+0A0h+var_120], r12
0x180052379  test    rcx, rcx
0x18005237c  jz      short loc_18005238B
0x18005237e  mov     rax, [rcx]
0x180052381  mov     rax, [rax+10h]
0x180052385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005238a  nop
0x18005238b  mov     rdx, rdi
0x18005238e  lea     rcx, [rbp+0A0h+var_70]
0x180052392  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180052397  mov     rsi, rax
0x18005239a  cmp     qword ptr [rax+18h], 7
0x18005239f  jbe     short loc_1800523A4
0x1800523a1  mov     rsi, [rax]
0x1800523a4  mov     [rbp+0A0h+string], r12
0x1800523a8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800523ac  mov     rbx, rdi
0x1800523af  inc     rbx
0x1800523b2  cmp     [rsi+rbx*2], r12w
0x1800523b7  jnz     short loc_1800523AF
0x1800523b9  mov     eax, 0FFFFFFFFh
0x1800523be  cmp     rbx, rax
0x1800523c1  ja      loc_18005268C
0x1800523c7  mov     ecx, ebx; unsigned int
0x1800523c9  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800523ce  lea     edx, [rax-1]
0x1800523d1  cmp     ebx, eax
0x1800523d3  cmovb   edx, ebx; length
0x1800523d6  lea     r9, [rbp+0A0h+string]; string
0x1800523da  lea     r8, [rbp+0A0h+hstringHeader]; hstringHeader
0x1800523de  mov     rcx, rsi; sourceString
0x1800523e1  call    cs:__imp_WindowsCreateStringReference
0x1800523e7  test    eax, eax
0x1800523e9  jns     short loc_1800523FE
0x1800523eb  xor     r9d, r9d; lpArguments
0x1800523ee  xor     r8d, r8d; nNumberOfArguments
0x1800523f1  lea     edx, [r9+1]; dwExceptionFlags
0x1800523f5  mov     ecx, eax; dwExceptionCode
0x1800523f7  call    cs:__imp_RaiseException
0x1800523fd  nop
0x1800523fe  lea     rsi, [r15+40h]
0x180052402  cmp     qword ptr [rsi+18h], 7
0x180052407  jbe     short loc_18005240C
0x180052409  mov     rsi, [rsi]
0x18005240c  mov     [rbp+0A0h+var_98], r12
0x180052410  mov     rbx, rdi
0x180052413  inc     rbx
0x180052416  cmp     [rsi+rbx*2], r12w
0x18005241b  jnz     short loc_180052413
0x18005241d  mov     eax, 0FFFFFFFFh
0x180052422  cmp     rbx, rax
0x180052425  ja      loc_180052676
0x18005242b  mov     rax, [rbp+0A0h+string]
0x18005242f  mov     [rbp+0A0h+var_118], rax
0x180052433  mov     r13, [r13+18h]
0x180052437  mov     ecx, ebx; unsigned int
0x180052439  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005243e  lea     edx, [rax-1]
0x180052441  cmp     ebx, eax
0x180052443  cmovb   edx, ebx; length
0x180052446  lea     r9, [rbp+0A0h+var_98]; string
0x18005244a  lea     r8, [rbp+0A0h+var_B0]; hstringHeader
0x18005244e  mov     rcx, rsi; sourceString
0x180052451  call    cs:__imp_WindowsCreateStringReference
0x180052457  test    eax, eax
0x180052459  jns     short loc_18005246E
0x18005245b  xor     r9d, r9d; lpArguments
0x18005245e  xor     r8d, r8d; nNumberOfArguments
0x180052461  lea     edx, [r9+1]; dwExceptionFlags
0x180052465  mov     ecx, eax; dwExceptionCode
0x180052467  call    cs:__imp_RaiseException
0x18005246d  nop
0x18005246e  lea     rsi, [r15+20h]
0x180052472  cmp     qword ptr [rsi+18h], 7
0x180052477  jbe     short loc_18005247C
0x180052479  mov     rsi, [rsi]
0x18005247c  mov     [rbp+0A0h+var_B8], r12
0x180052480  mov     rbx, rdi
0x180052483  inc     rbx
0x180052486  cmp     [rsi+rbx*2], r12w
0x18005248b  jnz     short loc_180052483
0x18005248d  mov     eax, 0FFFFFFFFh
0x180052492  cmp     rbx, rax
0x180052495  ja      loc_180052660
0x18005249b  mov     r12, [rbp+0A0h+var_98]
0x18005249f  mov     ecx, ebx; unsigned int
0x1800524a1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800524a6  lea     edx, [rax-1]
0x1800524a9  cmp     ebx, eax
0x1800524ab  cmovb   edx, ebx; length
0x1800524ae  lea     r9, [rbp+0A0h+var_B8]; string
0x1800524b2  lea     r8, [rbp+0A0h+var_D0]; hstringHeader
0x1800524b6  mov     rcx, rsi; sourceString
0x1800524b9  call    cs:__imp_WindowsCreateStringReference
0x1800524bf  xor     esi, esi
0x1800524c1  test    eax, eax
0x1800524c3  jns     short loc_1800524D7
0x1800524c5  xor     r9d, r9d; lpArguments
0x1800524c8  xor     r8d, r8d; nNumberOfArguments
0x1800524cb  lea     edx, [rsi+1]; dwExceptionFlags
0x1800524ce  mov     ecx, eax; dwExceptionCode
0x1800524d0  call    cs:__imp_RaiseException
0x1800524d6  nop
0x1800524d7  cmp     qword ptr [r15+18h], 7
0x1800524dc  jbe     short loc_1800524E1
0x1800524de  mov     r15, [r15]
0x1800524e1  mov     [rbp+0A0h+var_D8], rsi
0x1800524e5  inc     rdi
0x1800524e8  cmp     [r15+rdi*2], si
0x1800524ed  jnz     short loc_1800524E5
0x1800524ef  mov     eax, 0FFFFFFFFh
0x1800524f4  cmp     rdi, rax
0x1800524f7  ja      loc_18005264A
0x1800524fd  mov     rbx, [rbp+0A0h+var_B8]
0x180052501  mov     ecx, edi; unsigned int
0x180052503  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180052508  lea     edx, [rax-1]
0x18005250b  cmp     edi, eax
0x18005250d  cmovb   edx, edi; length
0x180052510  lea     r9, [rbp+0A0h+var_D8]; string
0x180052514  lea     r8, [rbp+0A0h+var_F0]; hstringHeader
0x180052518  mov     rcx, r15; sourceString
0x18005251b  call    cs:__imp_WindowsCreateStringReference
0x180052521  test    eax, eax
0x180052523  jns     short loc_180052538
0x180052525  xor     r9d, r9d; lpArguments
0x180052528  xor     r8d, r8d; nNumberOfArguments
0x18005252b  lea     edx, [r9+1]; dwExceptionFlags
0x18005252f  mov     ecx, eax; dwExceptionCode
0x180052531  call    cs:__imp_RaiseException
0x180052537  nop
0x180052538  mov     rdx, [rbp+0A0h+var_110]
0x18005253c  mov     rax, [rdx+18h]
0x180052540  test    rax, rax
0x180052543  jz      short loc_18005254A
0x180052545  mov     r8, [rax]
0x180052548  jmp     short loc_18005254D
0x18005254a  mov     r8, rsi
0x18005254d  lea     rax, [rbp+0A0h+var_120]
0x180052551  mov     [rsp+1A0h+var_148], rax
0x180052556  mov     rax, [rbp+0A0h+var_118]
0x18005255a  mov     [rsp+1A0h+var_150], rax
0x18005255f  mov     eax, [rsp+1A0h+var_130]
0x180052563  mov     [rsp+1A0h+var_158], eax
0x180052567  mov     [rsp+1A0h+var_160], r14
0x18005256c  mov     rax, [rbp+0A0h+arg_20]
0x180052573  mov     [rsp+1A0h+var_168], rax
0x180052578  mov     [rsp+1A0h+var_170], r13
0x18005257d  mov     [rsp+1A0h+var_178], r12
0x180052582  mov     qword ptr [rsp+1A0h+var_180], rbx; int
0x180052587  mov     r9, [rbp+0A0h+var_D8]
0x18005258b  mov     edx, [rdx+10h]
0x18005258e  mov     rcx, [rsp+1A0h+var_128]
0x180052593  mov     rax, [rbp+0A0h+var_108]
0x180052597  mov     rax, [rax+58h]
0x18005259b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800525a0  mov     rcx, [rbp+0A8h]; this
0x1800525a7  test    eax, eax
0x1800525a9  jns     short loc_1800525C0
0x1800525ab  mov     r9d, eax; char *
0x1800525ae  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800525b5  mov     edx, 5E4h; void *
0x1800525ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800525c0  mov     [rbp+0A0h+var_D8], rsi
0x1800525c4  mov     [rbp+0A0h+var_B8], rsi
0x1800525c8  mov     [rbp+0A0h+var_98], rsi
0x1800525cc  mov     [rbp+0A0h+string], rsi
0x1800525d0  mov     rdx, [rbp+0A0h+var_58]
0x1800525d4  cmp     rdx, 7
0x1800525d8  jbe     short loc_1800525EB
0x1800525da  lea     rdx, ds:2[rdx*2]
0x1800525e2  mov     rcx, [rbp+0A0h+var_70]
0x1800525e6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800525eb  mov     rdx, [rbp+0A0h+var_120]; struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *
0x1800525ef  mov     rbx, [rbp+0A0h+var_100]
0x1800525f3  mov     rcx, rbx; this
0x1800525f6  call    ??0cloud_store_save_result@wil@@QEAA@PEAUICloudStoreSaveResult@Cloud@Storage@Internal@Windows@@@Z; wil::cloud_store_save_result::cloud_store_save_result(Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *)
0x1800525fb  nop
0x1800525fc  mov     rcx, [rbp+0A0h+var_120]
0x180052600  test    rcx, rcx
0x180052603  jz      short loc_180052612
0x180052605  mov     rax, [rcx]
0x180052608  mov     rax, [rax+10h]
0x18005260c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052611  nop
0x180052612  test    r14, r14
0x180052615  jz      short loc_180052627
0x180052617  mov     rdx, [r14]
0x18005261a  mov     rcx, r14
0x18005261d  mov     rax, [rdx+10h]
0x180052621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052626  nop
0x180052627  mov     rax, rbx
0x18005262a  mov     rcx, [rbp+0A0h+var_50]
0x18005262e  xor     rcx, rsp; StackCookie
0x180052631  call    __security_check_cookie
0x180052636  add     rsp, 168h
0x18005263d  pop     r15
0x18005263f  pop     r14
0x180052641  pop     r13
0x180052643  pop     r12
0x180052645  pop     rdi
0x180052646  pop     rsi
0x180052647  pop     rbx
0x180052648  pop     rbp
0x180052649  retn
0x18005264a  xor     r9d, r9d; lpArguments
0x18005264d  xor     r8d, r8d; nNumberOfArguments
0x180052650  lea     edx, [r9+1]; dwExceptionFlags
0x180052654  mov     ecx, 80070216h; dwExceptionCode
0x180052659  call    cs:__imp_RaiseException
0x18005265f  nop
0x180052660  xor     r9d, r9d; lpArguments
0x180052663  xor     r8d, r8d; nNumberOfArguments
0x180052666  lea     edx, [r9+1]; dwExceptionFlags
0x18005266a  mov     ecx, 80070216h; dwExceptionCode
0x18005266f  call    cs:__imp_RaiseException
0x180052675  nop
0x180052676  xor     r9d, r9d; lpArguments
0x180052679  xor     r8d, r8d; nNumberOfArguments
0x18005267c  lea     edx, [r9+1]; dwExceptionFlags
0x180052680  mov     ecx, 80070216h; dwExceptionCode
0x180052685  call    cs:__imp_RaiseException
0x18005268b  nop
0x18005268c  xor     r9d, r9d; lpArguments
0x18005268f  xor     r8d, r8d; nNumberOfArguments
0x180052692  lea     edx, [r9+1]; dwExceptionFlags
0x180052696  mov     ecx, 80070216h; dwExceptionCode
0x18005269b  call    cs:__imp_RaiseException
```
