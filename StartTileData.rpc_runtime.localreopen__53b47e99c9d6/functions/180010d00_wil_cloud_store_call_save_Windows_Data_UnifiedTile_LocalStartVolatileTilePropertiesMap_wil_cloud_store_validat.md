# wil::cloud_store::call_save<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_data<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap> const &,unsigned __int64,wil::cloud_store_save_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180010d00`
- end: `0x18001117f`
- name: `??$call_save@ULocalStartVolatileTilePropertiesMap@UnifiedTile@Data@Windows@@@cloud_store@wil@@AEAA?AVcloud_store_save_result@1@AEBUvalidated_data_reference@01@AEBV?$cloud_store_data@ULocalStartVolatileTilePropertiesMap@UnifiedTile@Data@Windows@@@1@_KW4cloud_store_save_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1151`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802d9950`

## callees

- `0x180010d00`
- `0x180011188`
- `0x18001dac0`
- `0x18002dde0`
- `0x180053358`
- `0x1800533b8`
- `0x180054798`
- `0x180056798`
- `0x1800574a8`
- `0x180147be8`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011082`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011098`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800110ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800110c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800110df`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800110f2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011105`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011118`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011082`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011098`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800110ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800110c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800110df`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800110f2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011105`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010e3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010ea1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010efb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010f50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010e3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010ea1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010efb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010f50`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
wil::cloud_store_save_result *__fastcall wil::cloud_store::call_save<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap>(
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
  WCHAR *v14; // rsi
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rbx
  unsigned int v17; // eax
  UINT32 v18; // edx
  HRESULT v19; // eax
  unsigned int v20; // eax
  UINT32 v21; // edx
  HRESULT v22; // eax
  unsigned int v23; // eax
  UINT32 v24; // edx
  HRESULT v25; // eax
  unsigned int v26; // eax
  UINT32 v27; // edx
  HRESULT v28; // eax
  _QWORD *v29; // rdx
  WCHAR **v30; // rax
  WCHAR *v31; // r8
  int v32; // eax
  wil::details::in1diag3 *v33; // rcx
  wil::cloud_store_save_result *v34; // rbx
  int v36; // [rsp+20h] [rbp-E0h]
  __int64 *v37; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h]
  HSTRING v39; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v40; // [rsp+98h] [rbp-68h]
  wil::cloud_store_save_result *v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  HSTRING_HEADER v43; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v44; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING_HEADER v45; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING v46; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING_HEADER v47; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING v48; // [rsp+108h] [rbp+8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+110h] [rbp+10h] BYREF
  HSTRING string; // [rsp+128h] [rbp+28h] BYREF
  __int64 v51[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v52; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v41 = a2;
  v40 = a1;
  LODWORD(v38) = 0;
  wil::cloud_store::convert_cloud_store_save_options(a6);
  if ( (a6 & 8) != 0 )
  {
    v37 = 0;
    started = (__int64 *)&v37;
    v11 = 1;
    v12 = 0;
  }
  else
  {
    started = (__int64 *)wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap>>(
                           &v39,
                           a4);
    v11 = 2;
    v12 = *started;
  }
  *started = 0;
  v42 = v12;
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    LODWORD(v38) = v11;
    if ( v39 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v39 + 16LL))(v39);
  }
  if ( (v11 & 1) != 0 )
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v37);
  v37 = *(__int64 **)wil::details::shared_cloud_store_state::get_cloud_store(*a1);
  v38 = *v37;
  v13 = wil::cloud_store::widen_string(v51, a7);
  v14 = (WCHAR *)v13;
  if ( *(_QWORD *)(v13 + 24) > 7u )
    v14 = *(WCHAR **)v13;
  string = 0;
  v15 = -1;
  v16 = -1;
  do
    ++v16;
  while ( v14[v16] );
  if ( v16 > 0xFFFFFFFF )
    goto LABEL_51;
  v17 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v16);
  v18 = v17 - 1;
  if ( (unsigned int)v16 < v17 )
    v18 = v16;
  v19 = WindowsCreateStringReference(v14, v18, &hstringHeader, &string);
  if ( v19 < 0 )
  {
    RaiseException(v19, 1u, 0, 0);
LABEL_54:
    RaiseException(v22, 1u, 0, 0);
    goto LABEL_55;
  }
  v14 = (WCHAR *)(a3 + 8);
  if ( (unsigned __int64)a3[11] > 7 )
    v14 = *(WCHAR **)v14;
  v48 = 0;
  v16 = -1;
  do
    ++v16;
  while ( v14[v16] );
  if ( v16 > 0xFFFFFFFF )
    goto LABEL_50;
  v39 = string;
  v20 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v16);
  v21 = v20 - 1;
  if ( (unsigned int)v16 < v20 )
    v21 = v16;
  v22 = WindowsCreateStringReference(v14, v21, &v47, &v48);
  if ( v22 < 0 )
    goto LABEL_54;
  v14 = (WCHAR *)(a3 + 4);
  if ( (unsigned __int64)a3[7] > 7 )
    v14 = *(WCHAR **)v14;
  v46 = 0;
  v16 = -1;
  do
    ++v16;
  while ( v14[v16] );
  if ( v16 > 0xFFFFFFFF )
    goto LABEL_49;
  v23 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v16);
  v24 = v23 - 1;
  if ( (unsigned int)v16 < v23 )
    v24 = v16;
  v25 = WindowsCreateStringReference(v14, v24, &v45, &v46);
  v14 = 0;
  if ( v25 < 0 )
  {
LABEL_55:
    RaiseException(v25, 1u, 0, 0);
LABEL_56:
    RaiseException(v28, 1u, 0, 0);
LABEL_57:
    wil::details::in1diag3::Throw_Hr(
      v33,
      (void *)0x5E4,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v32,
      v36);
  }
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (__int64 *)*a3;
  v44 = 0;
  do
    ++v15;
  while ( *((_WORD *)a3 + v15) );
  if ( v15 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_49:
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_50:
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_51:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_52;
  }
  LODWORD(v16) = (_DWORD)v46;
  v26 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v15);
  v27 = v26 - 1;
  if ( (unsigned int)v15 < v26 )
    v27 = v15;
  v28 = WindowsCreateStringReference((PCWSTR)a3, v27, &v43, &v44);
  if ( v28 < 0 )
    goto LABEL_56;
  v29 = v40;
  v30 = (WCHAR **)v40[3];
  if ( v30 )
  {
    v31 = *v30;
    goto LABEL_42;
  }
LABEL_52:
  v31 = v14;
LABEL_42:
  v36 = v16;
  v32 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, WCHAR *, HSTRING))(v38 + 88))(
          v37,
          *((unsigned int *)v29 + 4),
          v31,
          v44);
  v33 = retaddr;
  if ( v32 < 0 )
    goto LABEL_57;
  v44 = (HSTRING)v14;
  v46 = (HSTRING)v14;
  v48 = (HSTRING)v14;
  string = (HSTRING)v14;
  if ( v52 > 7 )
    std::_Deallocate<16>(v51[0], 2 * v52 + 2);
  v34 = v41;
  wil::cloud_store_save_result::cloud_store_save_result(v41, 0);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return v34;
}

```

## disassembly

```asm
0x180010d00  push    rbp
0x180010d02  push    rbx
0x180010d03  push    rsi
0x180010d04  push    rdi
0x180010d05  push    r12
0x180010d07  push    r13
0x180010d09  push    r14
0x180010d0b  push    r15
0x180010d0d  lea     rbp, [rsp-68h]
0x180010d12  sub     rsp, 168h
0x180010d19  mov     rax, cs:__security_cookie
0x180010d20  xor     rax, rsp
0x180010d23  mov     [rbp+0A0h+var_50], rax
0x180010d27  mov     r13, r9
0x180010d2a  mov     r15, r8
0x180010d2d  mov     [rbp+0A0h+var_100], rdx
0x180010d31  mov     rsi, rcx
0x180010d34  mov     [rbp+0A0h+var_108], rcx
0x180010d38  mov     rdi, [rbp+0A0h+arg_30]
0x180010d3f  xor     r12d, r12d
0x180010d42  mov     dword ptr [rbp+0A0h+var_118], r12d
0x180010d46  mov     ecx, [rbp+0A0h+arg_28]
0x180010d4c  call    ?convert_cloud_store_save_options@cloud_store@wil@@CA?AW4SaveOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_save_options@2@@Z; wil::cloud_store::convert_cloud_store_save_options(wil::cloud_store_save_options)
0x180010d51  mov     [rsp+1A0h+var_130], eax
0x180010d55  cmp     [r13+21h], r12b
0x180010d59  jnz     short loc_180010D61
0x180010d5b  cmp     [r13+18h], r12
0x180010d5f  jnz     short loc_180010D68
0x180010d61  or      eax, 8
0x180010d64  mov     [rsp+1A0h+var_130], eax
0x180010d68  test    byte ptr [rbp+0A0h+arg_28], 8
0x180010d6f  jnz     loc_180011134
0x180010d75  mov     rdx, r13
0x180010d78  lea     rcx, [rbp+0A0h+var_110]
0x180010d7c  call    ??$marshal@V?$cloud_store_data@ULocalStartVolatileTilePropertiesMap@UnifiedTile@Data@Windows@@@wil@@@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@AEBV?$cloud_store_data@ULocalStartVolatileTilePropertiesMap@UnifiedTile@Data@Windows@@@1@@Z; wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap>>(wil::cloud_store_data<Windows::Data::UnifiedTile::LocalStartVolatileTilePropertiesMap> const &)
0x180010d81  mov     ebx, 2
0x180010d86  mov     r14, [rax]
0x180010d89  mov     [rax], r12
0x180010d8c  mov     [rbp+0A0h+var_F8], r14
0x180010d90  test    bl, 2
0x180010d93  jz      short loc_180010DB1
0x180010d95  and     ebx, 0FFFFFFFDh
0x180010d98  mov     dword ptr [rbp+0A0h+var_118], ebx
0x180010d9b  mov     rcx, [rbp+0A0h+var_110]
0x180010d9f  test    rcx, rcx
0x180010da2  jz      short loc_180010DB1
0x180010da4  mov     rax, [rcx]
0x180010da7  mov     rax, [rax+10h]
0x180010dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010db0  nop
0x180010db1  test    bl, 1
0x180010db4  jnz     loc_18001115F
0x180010dba  mov     [rsp+1A0h+var_128], r12
0x180010dbf  mov     rcx, [rsi]
0x180010dc2  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180010dc7  mov     rax, [rax]
0x180010dca  mov     [rbp+0A0h+var_120], rax
0x180010dce  mov     rax, [rax]
0x180010dd1  mov     [rbp+0A0h+var_118], rax
0x180010dd5  mov     rcx, [rsp+1A0h+var_128]
0x180010dda  mov     [rsp+1A0h+var_128], r12
0x180010ddf  test    rcx, rcx
0x180010de2  jnz     loc_18001116D
0x180010de8  mov     rdx, rdi
0x180010deb  lea     rcx, [rbp+0A0h+var_70]
0x180010def  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180010df4  mov     rsi, rax
0x180010df7  cmp     qword ptr [rax+18h], 7
0x180010dfc  ja      loc_180011053
0x180010e02  mov     [rbp+0A0h+string], r12
0x180010e06  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180010e0a  mov     rbx, rdi
0x180010e0d  inc     rbx
0x180010e10  cmp     [rsi+rbx*2], r12w
0x180010e15  jnz     short loc_180010E0D
0x180010e17  mov     eax, 0FFFFFFFFh
0x180010e1c  cmp     rbx, rax
0x180010e1f  ja      loc_1800110B5
0x180010e25  mov     ecx, ebx; unsigned int
0x180010e27  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180010e2c  lea     edx, [rax-1]
0x180010e2f  cmp     ebx, eax
0x180010e31  cmovb   edx, ebx; length
0x180010e34  lea     r9, [rbp+0A0h+string]; string
0x180010e38  lea     r8, [rbp+0A0h+hstringHeader]; hstringHeader
0x180010e3c  mov     rcx, rsi; sourceString
0x180010e3f  call    cs:__imp_WindowsCreateStringReference
0x180010e45  test    eax, eax
0x180010e47  js      loc_1800110D3
0x180010e4d  lea     rsi, [r15+40h]
0x180010e51  cmp     qword ptr [rsi+18h], 7
0x180010e56  ja      loc_18001105B
0x180010e5c  mov     [rbp+0A0h+var_98], r12
0x180010e60  mov     rbx, rdi
0x180010e63  inc     rbx
0x180010e66  cmp     [rsi+rbx*2], r12w
0x180010e6b  jnz     short loc_180010E63
0x180010e6d  mov     eax, 0FFFFFFFFh
0x180010e72  cmp     rbx, rax
0x180010e75  ja      loc_18001109F
0x180010e7b  mov     rax, [rbp+0A0h+string]
0x180010e7f  mov     [rbp+0A0h+var_110], rax
0x180010e83  mov     r13, [r13+18h]
0x180010e87  mov     ecx, ebx; unsigned int
0x180010e89  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180010e8e  lea     edx, [rax-1]
0x180010e91  cmp     ebx, eax
0x180010e93  cmovb   edx, ebx; length
0x180010e96  lea     r9, [rbp+0A0h+var_98]; string
0x180010e9a  lea     r8, [rbp+0A0h+var_B0]; hstringHeader
0x180010e9e  mov     rcx, rsi; sourceString
0x180010ea1  call    cs:__imp_WindowsCreateStringReference
0x180010ea7  test    eax, eax
0x180010ea9  js      loc_1800110E6
0x180010eaf  lea     rsi, [r15+20h]
0x180010eb3  cmp     qword ptr [rsi+18h], 7
0x180010eb8  ja      loc_180011063
0x180010ebe  mov     [rbp+0A0h+var_B8], r12
0x180010ec2  mov     rbx, rdi
0x180010ec5  inc     rbx
0x180010ec8  cmp     [rsi+rbx*2], r12w
0x180010ecd  jnz     short loc_180010EC5
0x180010ecf  mov     eax, 0FFFFFFFFh
0x180010ed4  cmp     rbx, rax
0x180010ed7  ja      loc_180011089
0x180010edd  mov     r12, [rbp+0A0h+var_98]
0x180010ee1  mov     ecx, ebx; unsigned int
0x180010ee3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180010ee8  lea     edx, [rax-1]
0x180010eeb  cmp     ebx, eax
0x180010eed  cmovb   edx, ebx; length
0x180010ef0  lea     r9, [rbp+0A0h+var_B8]; string
0x180010ef4  lea     r8, [rbp+0A0h+var_D0]; hstringHeader
0x180010ef8  mov     rcx, rsi; sourceString
0x180010efb  call    cs:__imp_WindowsCreateStringReference
0x180010f01  xor     esi, esi
0x180010f03  test    eax, eax
0x180010f05  js      loc_1800110F9
0x180010f0b  cmp     qword ptr [r15+18h], 7
0x180010f10  ja      loc_18001106B
0x180010f16  mov     [rbp+0A0h+var_D8], rsi
0x180010f1a  inc     rdi
0x180010f1d  cmp     [r15+rdi*2], si
0x180010f22  jnz     short loc_180010F1A
0x180010f24  mov     eax, 0FFFFFFFFh
0x180010f29  cmp     rdi, rax
0x180010f2c  ja      loc_180011073
0x180010f32  mov     rbx, [rbp+0A0h+var_B8]
0x180010f36  mov     ecx, edi; unsigned int
0x180010f38  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180010f3d  lea     edx, [rax-1]
0x180010f40  cmp     edi, eax
0x180010f42  cmovb   edx, edi; length
0x180010f45  lea     r9, [rbp+0A0h+var_D8]; string
0x180010f49  lea     r8, [rbp+0A0h+var_F0]; hstringHeader
0x180010f4d  mov     rcx, r15; sourceString
0x180010f50  call    cs:__imp_WindowsCreateStringReference
0x180010f56  test    eax, eax
0x180010f58  js      loc_18001110C
0x180010f5e  mov     rdx, [rbp+0A0h+var_108]
0x180010f62  mov     rax, [rdx+18h]
0x180010f66  test    rax, rax
0x180010f69  jz      loc_1800110CB
0x180010f6f  mov     r8, [rax]
0x180010f72  lea     rax, [rsp+1A0h+var_128]
0x180010f77  mov     [rsp+1A0h+var_148], rax
0x180010f7c  mov     rax, [rbp+0A0h+var_110]
0x180010f80  mov     [rsp+1A0h+var_150], rax
0x180010f85  mov     eax, [rsp+1A0h+var_130]
0x180010f89  mov     [rsp+1A0h+var_158], eax
0x180010f8d  mov     [rsp+1A0h+var_160], r14
0x180010f92  mov     rax, [rbp+0A0h+arg_20]
0x180010f99  mov     [rsp+1A0h+var_168], rax
0x180010f9e  mov     [rsp+1A0h+var_170], r13
0x180010fa3  mov     [rsp+1A0h+var_178], r12
0x180010fa8  mov     [rsp+1A0h+var_180], rbx
0x180010fad  mov     r9, [rbp+0A0h+var_D8]
0x180010fb1  mov     edx, [rdx+10h]
0x180010fb4  mov     rcx, [rbp+0A0h+var_120]
0x180010fb8  mov     rax, [rbp+0A0h+var_118]
0x180010fbc  mov     rax, [rax+58h]
0x180010fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fc5  mov     rcx, [rbp+0A8h]
0x180010fcc  test    eax, eax
0x180010fce  js      loc_18001111F
0x180010fd4  mov     [rbp+0A0h+var_D8], rsi
0x180010fd8  mov     [rbp+0A0h+var_B8], rsi
0x180010fdc  mov     [rbp+0A0h+var_98], rsi
0x180010fe0  mov     [rbp+0A0h+string], rsi
0x180010fe4  mov     rdx, [rbp+0A0h+var_58]
0x180010fe8  cmp     rdx, 7
0x180010fec  ja      loc_180011149
0x180010ff2  mov     rdx, [rsp+1A0h+var_128]; struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *
0x180010ff7  mov     rbx, [rbp+0A0h+var_100]
0x180010ffb  mov     rcx, rbx; this
0x180010ffe  call    ??0cloud_store_save_result@wil@@QEAA@PEAUICloudStoreSaveResult@Cloud@Storage@Internal@Windows@@@Z; wil::cloud_store_save_result::cloud_store_save_result(Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *)
0x180011003  nop
0x180011004  mov     rcx, [rsp+1A0h+var_128]
0x180011009  test    rcx, rcx
0x18001100c  jz      short loc_18001101B
0x18001100e  mov     rax, [rcx]
0x180011011  mov     rax, [rax+10h]
0x180011015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001101a  nop
0x18001101b  test    r14, r14
0x18001101e  jz      short loc_180011030
0x180011020  mov     rdx, [r14]
0x180011023  mov     rcx, r14
0x180011026  mov     rax, [rdx+10h]
0x18001102a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001102f  nop
0x180011030  mov     rax, rbx
0x180011033  mov     rcx, [rbp+0A0h+var_50]
0x180011037  xor     rcx, rsp; StackCookie
0x18001103a  call    __security_check_cookie
0x18001103f  add     rsp, 168h
0x180011046  pop     r15
0x180011048  pop     r14
0x18001104a  pop     r13
0x18001104c  pop     r12
0x18001104e  pop     rdi
0x18001104f  pop     rsi
0x180011050  pop     rbx
0x180011051  pop     rbp
0x180011052  retn
0x180011053  mov     rsi, [rax]
0x180011056  jmp     loc_180010E02
0x18001105b  mov     rsi, [rsi]
0x18001105e  jmp     loc_180010E5C
0x180011063  mov     rsi, [rsi]
0x180011066  jmp     loc_180010EBE
0x18001106b  mov     r15, [r15]
0x18001106e  jmp     loc_180010F16
0x180011073  xor     r9d, r9d; lpArguments
0x180011076  xor     r8d, r8d; nNumberOfArguments
0x180011079  lea     edx, [r9+1]; dwExceptionFlags
0x18001107d  mov     ecx, 80070216h; dwExceptionCode
0x180011082  call    cs:__imp_RaiseException
0x180011088  nop
0x180011089  xor     r9d, r9d; lpArguments
0x18001108c  xor     r8d, r8d; nNumberOfArguments
0x18001108f  lea     edx, [r9+1]; dwExceptionFlags
0x180011093  mov     ecx, 80070216h; dwExceptionCode
0x180011098  call    cs:__imp_RaiseException
0x18001109e  nop
0x18001109f  xor     r9d, r9d; lpArguments
0x1800110a2  xor     r8d, r8d; nNumberOfArguments
0x1800110a5  lea     edx, [r9+1]; dwExceptionFlags
0x1800110a9  mov     ecx, 80070216h; dwExceptionCode
0x1800110ae  call    cs:__imp_RaiseException
0x1800110b4  nop
0x1800110b5  xor     r9d, r9d; lpArguments
0x1800110b8  xor     r8d, r8d; nNumberOfArguments
0x1800110bb  lea     edx, [r9+1]; dwExceptionFlags
0x1800110bf  mov     ecx, 80070216h; dwExceptionCode
0x1800110c4  call    cs:__imp_RaiseException
0x1800110ca  nop
0x1800110cb  mov     r8, rsi
0x1800110ce  jmp     loc_180010F72
0x1800110d3  xor     r9d, r9d; lpArguments
0x1800110d6  xor     r8d, r8d; nNumberOfArguments
0x1800110d9  lea     edx, [r9+1]; dwExceptionFlags
0x1800110dd  mov     ecx, eax; dwExceptionCode
0x1800110df  call    cs:__imp_RaiseException
0x1800110e5  nop
0x1800110e6  xor     r9d, r9d; lpArguments
0x1800110e9  xor     r8d, r8d; nNumberOfArguments
0x1800110ec  lea     edx, [r9+1]; dwExceptionFlags
0x1800110f0  mov     ecx, eax; dwExceptionCode
0x1800110f2  call    cs:__imp_RaiseException
0x1800110f8  nop
0x1800110f9  xor     r9d, r9d; lpArguments
0x1800110fc  xor     r8d, r8d; nNumberOfArguments
0x1800110ff  lea     edx, [r9+1]; dwExceptionFlags
0x180011103  mov     ecx, eax; dwExceptionCode
0x180011105  call    cs:__imp_RaiseException
0x18001110b  nop
0x18001110c  xor     r9d, r9d; lpArguments
0x18001110f  xor     r8d, r8d; nNumberOfArguments
0x180011112  lea     edx, [r9+1]; dwExceptionFlags
0x180011116  mov     ecx, eax; dwExceptionCode
0x180011118  call    cs:__imp_RaiseException
0x18001111e  nop
0x18001111f  mov     r9d, eax; char *
0x180011122  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180011129  mov     edx, 5E4h; void *
0x18001112e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011134  mov     [rbp+0A0h+var_120], r12
0x180011138  lea     rax, [rbp+0A0h+var_120]
0x18001113c  mov     ebx, 1
0x180011141  mov     r14, r12
0x180011144  jmp     loc_180010D89
0x180011149  lea     rdx, ds:2[rdx*2]
0x180011151  mov     rcx, [rbp+0A0h+var_70]
0x180011155  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001115a  jmp     loc_180010FF2
0x18001115f  lea     rcx, [rbp+0A0h+var_120]; void *
0x180011163  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180011168  jmp     loc_180010DBA
0x18001116d  mov     rax, [rcx]
  ... truncated ...
```
