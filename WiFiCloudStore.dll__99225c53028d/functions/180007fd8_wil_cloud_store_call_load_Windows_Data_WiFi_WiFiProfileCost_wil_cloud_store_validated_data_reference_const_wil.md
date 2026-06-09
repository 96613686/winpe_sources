# wil::cloud_store::call_load<Windows::Data::WiFi::WiFiProfileCost>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180007fd8`
- end: `0x18000834d`
- name: `??$call_load@UWiFiProfileCost@WiFi@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `885`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64 *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800098b0`

## callees

- `0x1800062c0`
- `0x180007564`
- `0x1800075bc`
- `0x180007fd8`
- `0x180008354`
- `0x180025308`
- `0x18002a030`
- `0x18002e2d0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000809f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000810a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008162`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800081b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800082d9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800082ec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800082ff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008312`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000809f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000810a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008162`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800081b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800082d9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800082ec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800082ff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008312`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800080ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008119`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008175`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800081d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800080ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008119`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008175`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800081d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::cloud_store::call_load<Windows::Data::WiFi::WiFiProfileCost>(
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
  __int64 *v28; // [rsp+78h] [rbp-88h]
  HSTRING_HEADER v29; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v30; // [rsp+98h] [rbp-68h] BYREF
  HSTRING_HEADER v31; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING v32; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v33; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v34; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING string; // [rsp+F8h] [rbp-8h] BYREF
  void *v37; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v38; // [rsp+118h] [rbp+18h]
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
  v10 = 0;
  if ( v19 < 0 )
    goto LABEL_42;
  v20 = a1;
  v21 = (__int64 *)a1[3];
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
  wil::cloud_store::unmarshal<Windows::Data::WiFi::WiFiProfileCost>(a2, 0, a4);
  return a2;
}

```

## disassembly

```asm
0x180007fd8  push    rbp
0x180007fda  push    rbx
0x180007fdb  push    rsi
0x180007fdc  push    rdi
0x180007fdd  push    r12
0x180007fdf  push    r13
0x180007fe1  push    r14
0x180007fe3  push    r15
0x180007fe5  lea     rbp, [rsp-38h]
0x180007fea  sub     rsp, 138h
0x180007ff1  mov     rax, cs:__security_cookie
0x180007ff8  xor     rax, rsp
0x180007ffb  mov     [rbp+70h+var_50], rax
0x180007fff  mov     esi, r9d
0x180008002  mov     [rsp+170h+var_118], r9d
0x180008007  mov     rdi, r8
0x18000800a  mov     r15, rdx
0x18000800d  mov     [rsp+170h+var_100], rcx
0x180008012  mov     [rsp+170h+var_110], rdx
0x180008017  mov     rbx, [rbp+70h+arg_20]
0x18000801e  xor     r14d, r14d
0x180008021  mov     [rsp+170h+var_120], r14
0x180008026  mov     rcx, [rcx]
0x180008029  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x18000802e  mov     rax, [rax]
0x180008031  mov     [rsp+170h+var_F8], rax
0x180008036  mov     rax, [rax]
0x180008039  mov     [rsp+170h+var_110], rax
0x18000803e  mov     rcx, [rsp+170h+var_120]
0x180008043  mov     [rsp+170h+var_120], r14
0x180008048  test    rcx, rcx
0x18000804b  jnz     loc_1800082BC
0x180008051  mov     rdx, rbx
0x180008054  lea     rcx, [rbp+70h+var_70]
0x180008058  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x18000805d  mov     rcx, rax
0x180008060  cmp     qword ptr [rax+18h], 7
0x180008065  jbe     short loc_18000806A
0x180008067  mov     rcx, [rax]; sourceString
0x18000806a  mov     [rbp+70h+string], r14
0x18000806e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008072  mov     rdx, rbx
0x180008075  inc     rdx; length
0x180008078  cmp     [rcx+rdx*2], r14w
0x18000807d  jnz     short loc_180008075
0x18000807f  mov     eax, 0FFFFFFFFh
0x180008084  cmp     rdx, rax
0x180008087  ja      short loc_180008090
0x180008089  lea     eax, [rdx+1]
0x18000808c  cmp     eax, edx
0x18000808e  jnb     short loc_1800080A6
0x180008090  xor     r9d, r9d; lpArguments
0x180008093  xor     r8d, r8d; nNumberOfArguments
0x180008096  lea     edx, [r9+1]; dwExceptionFlags
0x18000809a  mov     ecx, 80070216h; dwExceptionCode
0x18000809f  call    cs:__imp_RaiseException
0x1800080a5  int     3; Trap to Debugger
0x1800080a6  lea     r9, [rbp+70h+string]; string
0x1800080aa  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x1800080ae  call    cs:__imp_WindowsCreateStringReference
0x1800080b4  test    eax, eax
0x1800080b6  js      loc_1800082CD
0x1800080bc  mov     r12, [rbp+70h+string]
0x1800080c0  mov     ecx, esi
0x1800080c2  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x1800080c7  mov     r13d, eax
0x1800080ca  lea     rcx, [rdi+40h]; sourceString
0x1800080ce  cmp     qword ptr [rcx+18h], 7
0x1800080d3  ja      loc_1800082A4
0x1800080d9  mov     [rbp+70h+var_98], r14
0x1800080dd  mov     rdx, rbx
0x1800080e0  inc     rdx; length
0x1800080e3  cmp     [rcx+rdx*2], r14w
0x1800080e8  jnz     short loc_1800080E0
0x1800080ea  mov     esi, 0FFFFFFFFh
0x1800080ef  cmp     rdx, rsi
0x1800080f2  ja      short loc_1800080FB
0x1800080f4  lea     eax, [rdx+1]
0x1800080f7  cmp     eax, edx
0x1800080f9  jnb     short loc_180008111
0x1800080fb  xor     r9d, r9d; lpArguments
0x1800080fe  xor     r8d, r8d; nNumberOfArguments
0x180008101  lea     edx, [r9+1]; dwExceptionFlags
0x180008105  mov     ecx, 80070216h; dwExceptionCode
0x18000810a  call    cs:__imp_RaiseException
0x180008110  int     3; Trap to Debugger
0x180008111  lea     r9, [rbp+70h+var_98]; string
0x180008115  lea     r8, [rbp+70h+var_B0]; hstringHeader
0x180008119  call    cs:__imp_WindowsCreateStringReference
0x18000811f  test    eax, eax
0x180008121  js      loc_1800082E0
0x180008127  lea     rcx, [rdi+20h]; sourceString
0x18000812b  cmp     qword ptr [rcx+18h], 7
0x180008130  ja      loc_1800082AC
0x180008136  mov     [rbp+70h+var_B8], r14
0x18000813a  mov     rdx, rbx
0x18000813d  inc     rdx; length
0x180008140  cmp     [rcx+rdx*2], r14w
0x180008145  jnz     short loc_18000813D
0x180008147  cmp     rdx, rsi
0x18000814a  ja      short loc_180008153
0x18000814c  lea     eax, [rdx+1]
0x18000814f  cmp     eax, edx
0x180008151  jnb     short loc_180008169
0x180008153  xor     r9d, r9d; lpArguments
0x180008156  xor     r8d, r8d; nNumberOfArguments
0x180008159  lea     edx, [r9+1]; dwExceptionFlags
0x18000815d  mov     ecx, 80070216h; dwExceptionCode
0x180008162  call    cs:__imp_RaiseException
0x180008168  int     3; Trap to Debugger
0x180008169  mov     r14, [rbp+70h+var_98]
0x18000816d  lea     r9, [rbp+70h+var_B8]; string
0x180008171  lea     r8, [rbp+70h+var_D0]; hstringHeader
0x180008175  call    cs:__imp_WindowsCreateStringReference
0x18000817b  xor     ecx, ecx
0x18000817d  test    eax, eax
0x18000817f  js      loc_1800082F3
0x180008185  cmp     qword ptr [rdi+18h], 7
0x18000818a  ja      loc_1800082B4
0x180008190  mov     [rbp+70h+var_D8], rcx
0x180008194  inc     rbx
0x180008197  cmp     [rdi+rbx*2], cx
0x18000819b  jnz     short loc_180008194
0x18000819d  cmp     rbx, rsi
0x1800081a0  ja      short loc_1800081A9
0x1800081a2  lea     eax, [rbx+1]
0x1800081a5  cmp     eax, ebx
0x1800081a7  jnb     short loc_1800081BF
0x1800081a9  xor     r9d, r9d; lpArguments
0x1800081ac  xor     r8d, r8d; nNumberOfArguments
0x1800081af  lea     edx, [r9+1]; dwExceptionFlags
0x1800081b3  mov     ecx, 80070216h; dwExceptionCode
0x1800081b8  call    cs:__imp_RaiseException
0x1800081be  int     3; Trap to Debugger
0x1800081bf  mov     rsi, [rbp+70h+var_B8]
0x1800081c3  lea     r9, [rbp+70h+var_D8]; string
0x1800081c7  lea     r8, [rbp+70h+var_F0]; hstringHeader
0x1800081cb  mov     edx, ebx; length
0x1800081cd  mov     rcx, rdi; sourceString
0x1800081d0  call    cs:__imp_WindowsCreateStringReference
0x1800081d6  xor     ebx, ebx
0x1800081d8  test    eax, eax
0x1800081da  js      loc_180008306
0x1800081e0  mov     rdx, [rsp+170h+var_100]
0x1800081e5  mov     rax, [rdx+18h]
0x1800081e9  test    rax, rax
0x1800081ec  jnz     loc_180008319
0x1800081f2  mov     r8d, ebx
0x1800081f5  lea     rax, [rsp+170h+var_120]
0x1800081fa  mov     [rsp+170h+var_130], rax
0x1800081ff  mov     [rsp+170h+var_138], r12
0x180008204  mov     [rsp+170h+var_140], r13d
0x180008209  mov     [rsp+170h+var_148], r14
0x18000820e  mov     qword ptr [rsp+170h+var_150], rsi; int
0x180008213  mov     r9, [rbp+70h+var_D8]
0x180008217  mov     edx, [rdx+10h]
0x18000821a  mov     rcx, [rsp+170h+var_F8]
0x18000821f  mov     rax, [rsp+170h+var_110]
0x180008224  mov     rax, [rax+48h]
0x180008228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000822d  mov     rcx, [rbp+78h]; this
0x180008231  test    eax, eax
0x180008233  js      loc_180008321
0x180008239  mov     [rbp+70h+var_D8], rbx
0x18000823d  mov     [rbp+70h+var_B8], rbx
0x180008241  mov     [rbp+70h+var_98], rbx
0x180008245  mov     [rbp+70h+string], rbx
0x180008249  mov     rdx, [rbp+70h+var_58]
0x18000824d  cmp     rdx, 7
0x180008251  ja      loc_180008336
0x180008257  mov     r8d, [rsp+170h+var_118]
0x18000825c  mov     rdx, [rsp+170h+var_120]
0x180008261  mov     rcx, r15
0x180008264  call    ??$unmarshal@UWiFiProfileCost@WiFi@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z; wil::cloud_store::unmarshal<Windows::Data::WiFi::WiFiProfileCost>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)
0x180008269  nop
0x18000826a  mov     rcx, [rsp+170h+var_120]
0x18000826f  test    rcx, rcx
0x180008272  jz      short loc_180008281
0x180008274  mov     rdx, [rcx]
0x180008277  mov     rax, [rdx+10h]
0x18000827b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008280  nop
0x180008281  mov     rax, r15
0x180008284  mov     rcx, [rbp+70h+var_50]
0x180008288  xor     rcx, rsp; StackCookie
0x18000828b  call    __security_check_cookie
0x180008290  add     rsp, 138h
0x180008297  pop     r15
0x180008299  pop     r14
0x18000829b  pop     r13
0x18000829d  pop     r12
0x18000829f  pop     rdi
0x1800082a0  pop     rsi
0x1800082a1  pop     rbx
0x1800082a2  pop     rbp
0x1800082a3  retn
0x1800082a4  mov     rcx, [rcx]
0x1800082a7  jmp     loc_1800080D9
0x1800082ac  mov     rcx, [rcx]
0x1800082af  jmp     loc_180008136
0x1800082b4  mov     rdi, [rdi]
0x1800082b7  jmp     loc_180008190
0x1800082bc  mov     rax, [rcx]
0x1800082bf  mov     rax, [rax+10h]
0x1800082c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082c8  jmp     loc_180008051
0x1800082cd  xor     r9d, r9d; lpArguments
0x1800082d0  xor     r8d, r8d; nNumberOfArguments
0x1800082d3  lea     edx, [r9+1]; dwExceptionFlags
0x1800082d7  mov     ecx, eax; dwExceptionCode
0x1800082d9  call    cs:__imp_RaiseException
0x1800082df  nop
0x1800082e0  xor     r9d, r9d; lpArguments
0x1800082e3  xor     r8d, r8d; nNumberOfArguments
0x1800082e6  lea     edx, [r9+1]; dwExceptionFlags
0x1800082ea  mov     ecx, eax; dwExceptionCode
0x1800082ec  call    cs:__imp_RaiseException
0x1800082f2  nop
0x1800082f3  xor     r9d, r9d; lpArguments
0x1800082f6  xor     r8d, r8d; nNumberOfArguments
0x1800082f9  lea     edx, [r9+1]; dwExceptionFlags
0x1800082fd  mov     ecx, eax; dwExceptionCode
0x1800082ff  call    cs:__imp_RaiseException
0x180008305  nop
0x180008306  xor     r9d, r9d; lpArguments
0x180008309  xor     r8d, r8d; nNumberOfArguments
0x18000830c  lea     edx, [r9+1]; dwExceptionFlags
0x180008310  mov     ecx, eax; dwExceptionCode
0x180008312  call    cs:__imp_RaiseException
0x180008318  nop
0x180008319  mov     r8, [rax]
0x18000831c  jmp     loc_1800081F5
0x180008321  mov     r9d, eax; char *
0x180008324  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18000832b  mov     edx, 588h; void *
0x180008330  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180008336  lea     rdx, ds:2[rdx*2]
0x18000833e  mov     rcx, [rbp+70h+var_70]
0x180008342  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180008347  jmp     loc_180008257
```
