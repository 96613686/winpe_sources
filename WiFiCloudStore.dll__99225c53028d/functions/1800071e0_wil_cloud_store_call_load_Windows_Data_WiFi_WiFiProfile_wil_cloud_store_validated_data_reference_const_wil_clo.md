# wil::cloud_store::call_load<Windows::Data::WiFi::WiFiProfile>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800071e0`
- end: `0x18000755b`
- name: `??$call_load@UWiFiProfile@WiFi@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `891`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64 *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007810`

## callees

- `0x180003350`
- `0x1800062c0`
- `0x1800071e0`
- `0x180007564`
- `0x1800075bc`
- `0x180025308`
- `0x18002a030`
- `0x18002e2d0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800072ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000731b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007376`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800073d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800074e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800074f8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000750c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007520`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800072ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000731b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007376`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800073d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800074e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800074f8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000750c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007520`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800072ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000732f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000738e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800073f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800072ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000732f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000738e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800073f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::cloud_store::call_load<Windows::Data::WiFi::WiFiProfile>(
        _QWORD *a1,
        __int64 a2,
        __int64 *a3,
        unsigned int a4,
        __int64 a5)
{
  unsigned int v5; // esi
  __int64 v8; // rax
  const WCHAR *v9; // rcx
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // rdx
  signed int v12; // eax
  const WCHAR *v13; // rcx
  unsigned __int64 v14; // rdx
  signed int v15; // eax
  const WCHAR *v16; // rcx
  unsigned __int64 v17; // rdx
  signed int v18; // eax
  signed int v19; // eax
  _QWORD *v20; // rdx
  __int64 *v21; // rax
  __int64 v22; // r8
  int v23; // eax
  __int64 v26; // [rsp+60h] [rbp-A0h]
  __int64 *v28; // [rsp+80h] [rbp-80h]
  HSTRING_HEADER v29; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v30; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING_HEADER v31; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING v32; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER v33; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v34; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING string; // [rsp+100h] [rbp+0h] BYREF
  void *v37; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int64 v38; // [rsp+120h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v5 = a4;
  v28 = *(__int64 **)wil::details::shared_cloud_store_state::get_cloud_store(*a1);
  v26 = *v28;
  v8 = wil::cloud_store::widen_string(&v37, a5);
  v9 = (const WCHAR *)v8;
  if ( *(_QWORD *)(v8 + 24) > 7u )
    v9 = *(const WCHAR **)v8;
  string = 0;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( v9[v11] );
  if ( v11 > 0xFFFFFFFF || (int)v11 + 1 < (unsigned int)v11 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v12 = WindowsCreateStringReference(v9, v11, &hstringHeader, &string);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
LABEL_40:
    RaiseException(v15, 1u, 0, 0);
LABEL_41:
    RaiseException(v18, 1u, 0, 0);
LABEL_42:
    RaiseException(v19, 1u, 0, 0);
    goto LABEL_43;
  }
  wil::cloud_store::convert_cloud_store_load_options(v5);
  v13 = (const WCHAR *)(a3 + 8);
  if ( (unsigned __int64)a3[11] > 7 )
    v13 = *(const WCHAR **)v13;
  v34 = 0;
  v14 = -1;
  do
    ++v14;
  while ( v13[v14] );
  v5 = -1;
  if ( v14 > 0xFFFFFFFF || (int)v14 + 1 < (unsigned int)v14 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v15 = WindowsCreateStringReference(v13, v14, &v33, &v34);
  if ( v15 < 0 )
    goto LABEL_40;
  v16 = (const WCHAR *)(a3 + 4);
  if ( (unsigned __int64)a3[7] > 7 )
    v16 = *(const WCHAR **)v16;
  v32 = 0;
  v17 = -1;
  do
    ++v17;
  while ( v16[v17] );
  if ( v17 > 0xFFFFFFFF || (int)v17 + 1 < (unsigned int)v17 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v18 = WindowsCreateStringReference(v16, v17, &v31, &v32);
  if ( v18 < 0 )
    goto LABEL_41;
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (__int64 *)*a3;
  v30 = 0;
  do
    ++v10;
  while ( *((_WORD *)a3 + v10) );
  if ( v10 > 0xFFFFFFFF || (int)v10 + 1 < (unsigned int)v10 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v5 = (unsigned int)v32;
  v19 = WindowsCreateStringReference((PCWSTR)a3, v10, &v29, &v30);
  if ( v19 < 0 )
    goto LABEL_42;
  v20 = a1;
  v21 = (__int64 *)a1[3];
  v10 = 0;
  if ( !v21 )
  {
    v22 = 0;
    goto LABEL_35;
  }
LABEL_43:
  v22 = *v21;
LABEL_35:
  v23 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, HSTRING))(v26 + 72))(
          v28,
          *((unsigned int *)v20 + 4),
          v22,
          v30);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x588,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v23,
      v5);
  v30 = (HSTRING)v10;
  v32 = (HSTRING)v10;
  v34 = (HSTRING)v10;
  string = (HSTRING)v10;
  if ( v38 > 7 )
    std::_Deallocate<16>(v37, 2 * v38 + 2);
  wil::cloud_store::unmarshal<Windows::Data::WiFi::WiFiProfile>(a2, 0, a4);
  return a2;
}

```

## disassembly

```asm
0x1800071e0  push    rbp
0x1800071e2  push    rbx
0x1800071e3  push    rsi
0x1800071e4  push    rdi
0x1800071e5  push    r12
0x1800071e7  push    r13
0x1800071e9  push    r14
0x1800071eb  push    r15
0x1800071ed  lea     rbp, [rsp-38h]
0x1800071f2  sub     rsp, 138h
0x1800071f9  mov     rax, cs:__security_cookie
0x180007200  xor     rax, rsp
0x180007203  mov     [rbp+70h+var_48], rax
0x180007207  mov     esi, r9d
0x18000720a  mov     [rsp+170h+var_118], r9d
0x18000720f  mov     rdi, r8
0x180007212  mov     r13, rdx
0x180007215  mov     [rsp+170h+var_F8], rcx
0x18000721a  mov     [rsp+170h+var_110], rdx
0x18000721f  mov     rbx, [rbp+70h+arg_20]
0x180007226  xor     r14d, r14d
0x180007229  mov     [rsp+170h+var_120], r14
0x18000722e  mov     rcx, [rcx]
0x180007231  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180007236  mov     rax, [rax]
0x180007239  mov     [rbp+70h+var_F0], rax
0x18000723d  mov     rax, [rax]
0x180007240  mov     [rsp+170h+var_110], rax
0x180007245  mov     rcx, [rsp+170h+var_120]
0x18000724a  mov     [rsp+170h+var_120], r14
0x18000724f  test    rcx, rcx
0x180007252  jnz     loc_1800074C6
0x180007258  mov     rdx, rbx
0x18000725b  lea     rcx, [rbp+70h+var_68]
0x18000725f  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180007264  mov     rcx, rax
0x180007267  cmp     qword ptr [rax+18h], 7
0x18000726c  jbe     short loc_180007271
0x18000726e  mov     rcx, [rax]; sourceString
0x180007271  mov     [rbp+70h+string], r14
0x180007275  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000727c  mov     rdx, rbx
0x18000727f  nop
0x180007280  inc     rdx; length
0x180007283  cmp     word ptr [rcx+rdx*2], 0
0x180007288  jnz     short loc_180007280
0x18000728a  mov     eax, 0FFFFFFFFh
0x18000728f  cmp     rdx, rax
0x180007292  ja      short loc_18000729B
0x180007294  lea     eax, [rdx+1]
0x180007297  cmp     eax, edx
0x180007299  jnb     short loc_1800072B2
0x18000729b  xor     r9d, r9d; lpArguments
0x18000729e  xor     r8d, r8d; nNumberOfArguments
0x1800072a1  mov     edx, 1; dwExceptionFlags
0x1800072a6  mov     ecx, 80070216h; dwExceptionCode
0x1800072ab  call    cs:__imp_RaiseException
0x1800072b1  int     3; Trap to Debugger
0x1800072b2  lea     r9, [rbp+70h+string]; string
0x1800072b6  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x1800072ba  call    cs:__imp_WindowsCreateStringReference
0x1800072c0  test    eax, eax
0x1800072c2  js      loc_1800074D7
0x1800072c8  mov     r15, [rbp+70h+string]
0x1800072cc  mov     ecx, esi
0x1800072ce  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x1800072d3  mov     r12d, eax
0x1800072d6  lea     rcx, [rdi+40h]; sourceString
0x1800072da  cmp     qword ptr [rcx+18h], 7
0x1800072df  ja      short loc_180007322
0x1800072e1  mov     [rbp+70h+var_90], r14
0x1800072e5  mov     rdx, rbx
0x1800072e8  nop     dword ptr [rax+rax+00000000h]
0x1800072f0  inc     rdx; length
0x1800072f3  cmp     word ptr [rcx+rdx*2], 0
0x1800072f8  jnz     short loc_1800072F0
0x1800072fa  mov     esi, 0FFFFFFFFh
0x1800072ff  cmp     rdx, rsi
0x180007302  ja      short loc_18000730B
0x180007304  lea     eax, [rdx+1]
0x180007307  cmp     eax, edx
0x180007309  jnb     short loc_180007327
0x18000730b  xor     r9d, r9d; lpArguments
0x18000730e  xor     r8d, r8d; nNumberOfArguments
0x180007311  mov     edx, 1; dwExceptionFlags
0x180007316  mov     ecx, 80070216h; dwExceptionCode
0x18000731b  call    cs:__imp_RaiseException
0x180007321  int     3; Trap to Debugger
0x180007322  mov     rcx, [rcx]
0x180007325  jmp     short loc_1800072E1
0x180007327  lea     r9, [rbp+70h+var_90]; string
0x18000732b  lea     r8, [rbp+70h+var_A8]; hstringHeader
0x18000732f  call    cs:__imp_WindowsCreateStringReference
0x180007335  test    eax, eax
0x180007337  js      loc_1800074EB
0x18000733d  lea     rcx, [rdi+20h]; sourceString
0x180007341  cmp     qword ptr [rcx+18h], 7
0x180007346  ja      short loc_18000737D
0x180007348  mov     [rbp+70h+var_B0], r14
0x18000734c  mov     rdx, rbx
0x18000734f  nop
0x180007350  inc     rdx; length
0x180007353  cmp     word ptr [rcx+rdx*2], 0
0x180007358  jnz     short loc_180007350
0x18000735a  cmp     rdx, rsi
0x18000735d  ja      short loc_180007366
0x18000735f  lea     eax, [rdx+1]
0x180007362  cmp     eax, edx
0x180007364  jnb     short loc_180007382
0x180007366  xor     r9d, r9d; lpArguments
0x180007369  xor     r8d, r8d; nNumberOfArguments
0x18000736c  mov     edx, 1; dwExceptionFlags
0x180007371  mov     ecx, 80070216h; dwExceptionCode
0x180007376  call    cs:__imp_RaiseException
0x18000737c  int     3; Trap to Debugger
0x18000737d  mov     rcx, [rcx]
0x180007380  jmp     short loc_180007348
0x180007382  mov     r14, [rbp+70h+var_90]
0x180007386  lea     r9, [rbp+70h+var_B0]; string
0x18000738a  lea     r8, [rbp+70h+var_C8]; hstringHeader
0x18000738e  call    cs:__imp_WindowsCreateStringReference
0x180007394  test    eax, eax
0x180007396  js      loc_1800074FF
0x18000739c  cmp     qword ptr [rdi+18h], 7
0x1800073a1  ja      short loc_1800073DD
0x1800073a3  mov     [rbp+70h+var_D0], 0
0x1800073ab  nop     dword ptr [rax+rax+00h]
0x1800073b0  inc     rbx
0x1800073b3  cmp     word ptr [rdi+rbx*2], 0
0x1800073b8  jnz     short loc_1800073B0
0x1800073ba  cmp     rbx, rsi
0x1800073bd  ja      short loc_1800073C6
0x1800073bf  lea     eax, [rbx+1]
0x1800073c2  cmp     eax, ebx
0x1800073c4  jnb     short loc_1800073E2
0x1800073c6  xor     r9d, r9d; lpArguments
0x1800073c9  xor     r8d, r8d; nNumberOfArguments
0x1800073cc  mov     edx, 1; dwExceptionFlags
0x1800073d1  mov     ecx, 80070216h; dwExceptionCode
0x1800073d6  call    cs:__imp_RaiseException
0x1800073dc  int     3; Trap to Debugger
0x1800073dd  mov     rdi, [rdi]
0x1800073e0  jmp     short loc_1800073A3
0x1800073e2  mov     rsi, [rbp+70h+var_B0]
0x1800073e6  lea     r9, [rbp+70h+var_D0]; string
0x1800073ea  lea     r8, [rbp+70h+var_E8]; hstringHeader
0x1800073ee  mov     edx, ebx; length
0x1800073f0  mov     rcx, rdi; sourceString
0x1800073f3  call    cs:__imp_WindowsCreateStringReference
0x1800073f9  test    eax, eax
0x1800073fb  js      loc_180007513
0x180007401  mov     rdx, [rsp+170h+var_F8]
0x180007406  mov     rax, [rdx+18h]
0x18000740a  xor     ebx, ebx
0x18000740c  test    rax, rax
0x18000740f  jnz     loc_180007527
0x180007415  mov     r8d, ebx
0x180007418  lea     rax, [rsp+170h+var_120]
0x18000741d  mov     [rsp+170h+var_130], rax
0x180007422  mov     [rsp+170h+var_138], r15
0x180007427  mov     [rsp+170h+var_140], r12d
0x18000742c  mov     [rsp+170h+var_148], r14
0x180007431  mov     qword ptr [rsp+170h+var_150], rsi; int
0x180007436  mov     r9, [rbp+70h+var_D0]
0x18000743a  mov     edx, [rdx+10h]
0x18000743d  mov     rcx, [rbp+70h+var_F0]
0x180007441  mov     rax, [rsp+170h+var_110]
0x180007446  mov     rax, [rax+48h]
0x18000744a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000744f  mov     rcx, [rbp+78h]; this
0x180007453  test    eax, eax
0x180007455  js      loc_18000752F
0x18000745b  mov     [rbp+70h+var_D0], rbx
0x18000745f  mov     [rbp+70h+var_B0], rbx
0x180007463  mov     [rbp+70h+var_90], rbx
0x180007467  mov     [rbp+70h+string], rbx
0x18000746b  mov     rdx, [rbp+70h+var_50]
0x18000746f  cmp     rdx, 7
0x180007473  ja      loc_180007544
0x180007479  mov     r8d, [rsp+170h+var_118]
0x18000747e  mov     rdx, [rsp+170h+var_120]
0x180007483  mov     rcx, r13
0x180007486  call    ??$unmarshal@UWiFiProfile@WiFi@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z; wil::cloud_store::unmarshal<Windows::Data::WiFi::WiFiProfile>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)
0x18000748b  nop
0x18000748c  mov     rcx, [rsp+170h+var_120]
0x180007491  test    rcx, rcx
0x180007494  jz      short loc_1800074A3
0x180007496  mov     rdx, [rcx]
0x180007499  mov     rax, [rdx+10h]
0x18000749d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074a2  nop
0x1800074a3  mov     rax, r13
0x1800074a6  mov     rcx, [rbp+70h+var_48]
0x1800074aa  xor     rcx, rsp; StackCookie
0x1800074ad  call    __security_check_cookie
0x1800074b2  add     rsp, 138h
0x1800074b9  pop     r15
0x1800074bb  pop     r14
0x1800074bd  pop     r13
0x1800074bf  pop     r12
0x1800074c1  pop     rdi
0x1800074c2  pop     rsi
0x1800074c3  pop     rbx
0x1800074c4  pop     rbp
0x1800074c5  retn
0x1800074c6  mov     rax, [rcx]
0x1800074c9  mov     rax, [rax+10h]
0x1800074cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074d2  jmp     loc_180007258
0x1800074d7  xor     r9d, r9d; lpArguments
0x1800074da  xor     r8d, r8d; nNumberOfArguments
0x1800074dd  mov     edx, 1; dwExceptionFlags
0x1800074e2  mov     ecx, eax; dwExceptionCode
0x1800074e4  call    cs:__imp_RaiseException
0x1800074ea  nop
0x1800074eb  xor     r9d, r9d; lpArguments
0x1800074ee  xor     r8d, r8d; nNumberOfArguments
0x1800074f1  mov     edx, 1; dwExceptionFlags
0x1800074f6  mov     ecx, eax; dwExceptionCode
0x1800074f8  call    cs:__imp_RaiseException
0x1800074fe  nop
0x1800074ff  xor     r9d, r9d; lpArguments
0x180007502  xor     r8d, r8d; nNumberOfArguments
0x180007505  mov     edx, 1; dwExceptionFlags
0x18000750a  mov     ecx, eax; dwExceptionCode
0x18000750c  call    cs:__imp_RaiseException
0x180007512  nop
0x180007513  xor     r9d, r9d; lpArguments
0x180007516  xor     r8d, r8d; nNumberOfArguments
0x180007519  mov     edx, 1; dwExceptionFlags
0x18000751e  mov     ecx, eax; dwExceptionCode
0x180007520  call    cs:__imp_RaiseException
0x180007526  nop
0x180007527  mov     r8, [rax]
0x18000752a  jmp     loc_180007418
0x18000752f  mov     r9d, eax; char *
0x180007532  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180007539  mov     edx, 588h; void *
0x18000753e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007544  lea     rdx, ds:2[rdx*2]
0x18000754c  mov     rcx, [rbp+70h+var_68]
0x180007550  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180007555  jmp     loc_180007479
```
