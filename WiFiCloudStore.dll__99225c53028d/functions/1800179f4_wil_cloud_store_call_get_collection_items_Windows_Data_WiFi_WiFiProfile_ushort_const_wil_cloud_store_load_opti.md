# wil::cloud_store::call_get_collection_items<Windows::Data::WiFi::WiFiProfile>(ushort const *,wil::cloud_store_load_options,wil::cloud_store_collection_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800179f4`
- end: `0x180017d25`
- name: `??$call_get_collection_items@UWiFiProfile@WiFi@Data@Windows@@@cloud_store@wil@@AEAA?AV?$vector@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@PEBGW4cloud_store_load_options@1@W4cloud_store_collection_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z`
- size: `817`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001792c`

## callees

- `0x1800062c0`
- `0x180006cd0`
- `0x180007564`
- `0x1800075bc`
- `0x180008cb0`
- `0x1800179f4`
- `0x180025308`
- `0x18002a030`
- `0x18002e2d0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017abb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017b26`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017b71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017caf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017cc2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017cd5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017abb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017b26`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017b71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017caf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017cc2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017cd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017ad1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017b3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017b90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017ad1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017b3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017b90`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall wil::cloud_store::call_get_collection_items<Windows::Data::WiFi::WiFiProfile>(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v10; // rax
  const WCHAR *v11; // rcx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rdx
  signed int v14; // eax
  const WCHAR *v15; // rcx
  unsigned __int64 v16; // rdx
  signed int v17; // eax
  signed int v18; // eax
  __int64 *v19; // rax
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // rcx
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h]
  __int64 *v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  char v28; // [rsp+70h] [rbp-90h]
  __int64 *v29; // [rsp+80h] [rbp-80h]
  PCWSTR sourceString[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v31; // [rsp+A0h] [rbp-60h]
  HSTRING_HEADER v32; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING v33; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER v34; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v35; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING string; // [rsp+100h] [rbp+0h] BYREF
  void *v38; // [rsp+108h] [rbp+8h] BYREF
  __m128i si128; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v25 = a2;
  wil::cloud_store::get_type_name_wide_string<Windows::Data::WiFi::WiFiProfile>(sourceString);
  v24 = 0;
  v29 = *(__int64 **)wil::details::shared_cloud_store_state::get_cloud_store(*(_QWORD *)a1);
  v25 = *v29;
  v26 = &v24;
  v27 = 0;
  v28 = 1;
  v10 = wil::cloud_store::widen_string(&v38, a6);
  v11 = (const WCHAR *)v10;
  if ( *(_QWORD *)(v10 + 24) > 7u )
    v11 = *(const WCHAR **)v10;
  string = 0;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( v11[v13] );
  if ( v13 > 0xFFFFFFFF || (int)v13 + 1 < (unsigned int)v13 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v14 = WindowsCreateStringReference(v11, v13, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    RaiseException(v14, 1u, 0, 0);
LABEL_37:
    RaiseException(v17, 1u, 0, 0);
LABEL_38:
    RaiseException(v18, 1u, 0, 0);
    goto LABEL_39;
  }
  wil::cloud_store::convert_cloud_store_load_options(a4);
  v15 = (const WCHAR *)sourceString;
  if ( v31 > 7 )
    v15 = sourceString[0];
  a4 = 0;
  v35 = 0;
  v16 = -1;
  do
    ++v16;
  while ( v15[v16] );
  if ( v16 > 0xFFFFFFFF || (int)v16 + 1 < (unsigned int)v16 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v17 = WindowsCreateStringReference(v15, v16, &v34, &v35);
  if ( v17 < 0 )
    goto LABEL_37;
  v33 = 0;
  do
    ++v12;
  while ( a3[v12] );
  if ( v12 > 0xFFFFFFFF || (int)v12 + 1 < (unsigned int)v12 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  a4 = (unsigned int)v35;
  v18 = WindowsCreateStringReference(a3, v12, &v32, &v33);
  v12 = 0;
  if ( v18 < 0 )
    goto LABEL_38;
  v19 = *(__int64 **)(a1 + 24);
  if ( !v19 )
  {
    v20 = 0;
    goto LABEL_25;
  }
LABEL_39:
  v20 = *v19;
LABEL_25:
  v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, HSTRING))(v25 + 80))(
          v29,
          *(unsigned int *)(a1 + 16),
          v20,
          v33);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x553,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v21,
      a4);
  v33 = (HSTRING)v12;
  v35 = (HSTRING)v12;
  string = (HSTRING)v12;
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v38, 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v38) = v12;
  if ( v28 != (_BYTE)v12 )
  {
    v22 = *v26;
    *v26 = v27;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::WiFi::WiFiProfile>(a2, v24);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v31 > 7 )
    std::_Deallocate<16>((void *)sourceString[0], 2 * v31 + 2);
  return a2;
}

```

## disassembly

```asm
0x1800179f4  push    rbp
0x1800179f6  push    rbx
0x1800179f7  push    rsi
0x1800179f8  push    rdi
0x1800179f9  push    r12
0x1800179fb  push    r13
0x1800179fd  push    r14
0x1800179ff  push    r15
0x180017a01  lea     rbp, [rsp-38h]
0x180017a06  sub     rsp, 138h
0x180017a0d  mov     rax, cs:__security_cookie
0x180017a14  xor     rax, rsp
0x180017a17  mov     [rbp+70h+var_48], rax
0x180017a1b  mov     edi, r9d
0x180017a1e  mov     r14, r8
0x180017a21  mov     rsi, rdx
0x180017a24  mov     r15, rcx
0x180017a27  mov     [rsp+170h+var_118], rdx
0x180017a2c  mov     rbx, [rbp+70h+arg_28]
0x180017a33  xor     r12d, r12d
0x180017a36  lea     rcx, [rbp+70h+sourceString]
0x180017a3a  call    ??$get_type_name_wide_string@UWiFiProfile@WiFi@Data@Windows@@@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::cloud_store::get_type_name_wide_string<Windows::Data::WiFi::WiFiProfile>(void)
0x180017a3f  nop
0x180017a40  mov     [rsp+170h+var_120], r12
0x180017a45  mov     rcx, [r15]
0x180017a48  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180017a4d  mov     rax, [rax]
0x180017a50  mov     [rbp+70h+var_F0], rax
0x180017a54  mov     rax, [rax]
0x180017a57  mov     [rsp+170h+var_118], rax
0x180017a5c  lea     rcx, [rsp+170h+var_120]
0x180017a61  mov     [rsp+170h+var_110], rcx
0x180017a66  mov     [rsp+170h+var_108], r12
0x180017a6b  lea     r13d, [r12+1]
0x180017a70  mov     [rsp+170h+var_100], r13b
0x180017a75  mov     rdx, rbx
0x180017a78  lea     rcx, [rbp+70h+var_68]
0x180017a7c  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180017a81  mov     rcx, rax
0x180017a84  cmp     qword ptr [rax+18h], 7
0x180017a89  jbe     short loc_180017A8E
0x180017a8b  mov     rcx, [rax]; sourceString
0x180017a8e  mov     [rbp+70h+string], r12
0x180017a92  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180017a96  mov     rdx, rbx
0x180017a99  inc     rdx; length
0x180017a9c  cmp     [rcx+rdx*2], r12w
0x180017aa1  jnz     short loc_180017A99
0x180017aa3  mov     eax, 0FFFFFFFFh
0x180017aa8  cmp     rdx, rax
0x180017aab  jbe     short loc_180017AC2
0x180017aad  xor     r9d, r9d; lpArguments
0x180017ab0  xor     r8d, r8d; nNumberOfArguments
0x180017ab3  mov     edx, r13d; dwExceptionFlags
0x180017ab6  mov     ecx, 80070216h; dwExceptionCode
0x180017abb  call    cs:__imp_RaiseException
0x180017ac1  int     3; Trap to Debugger
0x180017ac2  lea     eax, [rdx+1]
0x180017ac5  cmp     eax, edx
0x180017ac7  jb      short loc_180017AAD
0x180017ac9  lea     r9, [rbp+70h+string]; string
0x180017acd  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x180017ad1  call    cs:__imp_WindowsCreateStringReference
0x180017ad7  test    eax, eax
0x180017ad9  js      loc_180017CA4
0x180017adf  mov     r12, [rbp+70h+string]
0x180017ae3  mov     ecx, edi
0x180017ae5  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x180017aea  mov     r13d, eax
0x180017aed  lea     rcx, [rbp+70h+sourceString]
0x180017af1  cmp     [rbp+70h+var_D0], 7
0x180017af6  cmova   rcx, [rbp+70h+sourceString]; sourceString
0x180017afb  xor     edi, edi
0x180017afd  mov     [rbp+70h+var_90], rdi
0x180017b01  mov     rdx, rbx
0x180017b04  inc     rdx; length
0x180017b07  cmp     [rcx+rdx*2], di
0x180017b0b  jnz     short loc_180017B04
0x180017b0d  mov     eax, 0FFFFFFFFh
0x180017b12  cmp     rdx, rax
0x180017b15  jbe     short loc_180017B2D
0x180017b17  xor     r9d, r9d; lpArguments
0x180017b1a  xor     r8d, r8d; nNumberOfArguments
0x180017b1d  lea     edx, [r9+1]; dwExceptionFlags
0x180017b21  mov     ecx, 80070216h; dwExceptionCode
0x180017b26  call    cs:__imp_RaiseException
0x180017b2c  int     3; Trap to Debugger
0x180017b2d  lea     eax, [rdx+1]
0x180017b30  cmp     eax, edx
0x180017b32  jb      short loc_180017B17
0x180017b34  lea     r9, [rbp+70h+var_90]; string
0x180017b38  lea     r8, [rbp+70h+var_A8]; hstringHeader
0x180017b3c  call    cs:__imp_WindowsCreateStringReference
0x180017b42  test    eax, eax
0x180017b44  js      loc_180017CB6
0x180017b4a  mov     [rbp+70h+var_B0], rdi
0x180017b4e  inc     rbx
0x180017b51  cmp     [r14+rbx*2], di
0x180017b56  jnz     short loc_180017B4E
0x180017b58  mov     eax, 0FFFFFFFFh
0x180017b5d  cmp     rbx, rax
0x180017b60  jbe     short loc_180017B78
0x180017b62  xor     r9d, r9d; lpArguments
0x180017b65  xor     r8d, r8d; nNumberOfArguments
0x180017b68  lea     edx, [r9+1]; dwExceptionFlags
0x180017b6c  mov     ecx, 80070216h; dwExceptionCode
0x180017b71  call    cs:__imp_RaiseException
0x180017b77  int     3; Trap to Debugger
0x180017b78  lea     eax, [rbx+1]
0x180017b7b  cmp     eax, ebx
0x180017b7d  jb      short loc_180017B62
0x180017b7f  mov     rdi, [rbp+70h+var_90]
0x180017b83  lea     r9, [rbp+70h+var_B0]; string
0x180017b87  lea     r8, [rbp+70h+var_C8]; hstringHeader
0x180017b8b  mov     edx, ebx; length
0x180017b8d  mov     rcx, r14; sourceString
0x180017b90  call    cs:__imp_WindowsCreateStringReference
0x180017b96  xor     ebx, ebx
0x180017b98  test    eax, eax
0x180017b9a  js      loc_180017CC9
0x180017ba0  mov     rax, [r15+18h]
0x180017ba4  test    rax, rax
0x180017ba7  jnz     loc_180017CDC
0x180017bad  mov     r8d, ebx
0x180017bb0  lea     rax, [rsp+170h+var_108]
0x180017bb5  mov     [rsp+170h+var_130], rax
0x180017bba  mov     [rsp+170h+var_138], r12
0x180017bbf  mov     r10d, [rbp+70h+arg_20]
0x180017bc6  mov     [rsp+170h+var_140], r10d
0x180017bcb  mov     [rsp+170h+var_148], r13d
0x180017bd0  mov     qword ptr [rsp+170h+var_150], rdi; int
0x180017bd5  mov     r9, [rbp+70h+var_B0]
0x180017bd9  mov     edx, [r15+10h]
0x180017bdd  mov     rcx, [rbp+70h+var_F0]
0x180017be1  mov     rax, [rsp+170h+var_118]
0x180017be6  mov     rax, [rax+50h]
0x180017bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bef  mov     rcx, [rbp+78h]; this
0x180017bf3  test    eax, eax
0x180017bf5  js      loc_180017CE4
0x180017bfb  mov     [rbp+70h+var_B0], rbx
0x180017bff  mov     [rbp+70h+var_90], rbx
0x180017c03  mov     [rbp+70h+string], rbx
0x180017c07  mov     rdx, [rbp+70h+var_50]
0x180017c0b  cmp     rdx, 7
0x180017c0f  ja      loc_180017CF9
0x180017c15  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180017c1d  movdqu  xmmword ptr [rbp+18h], xmm0
0x180017c22  mov     word ptr [rbp+70h+var_68], bx
0x180017c26  cmp     [rsp+170h+var_100], bl
0x180017c2a  jz      short loc_180017C4E
0x180017c2c  mov     rdx, [rsp+170h+var_108]
0x180017c31  mov     rax, [rsp+170h+var_110]
0x180017c36  mov     rcx, [rax]
0x180017c39  mov     [rax], rdx
0x180017c3c  test    rcx, rcx
0x180017c3f  jz      short loc_180017C4E
0x180017c41  mov     rax, [rcx]
0x180017c44  mov     rax, [rax+10h]
0x180017c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c4d  nop
0x180017c4e  mov     rdx, [rsp+170h+var_120]
0x180017c53  mov     rcx, rsi
0x180017c56  call    ??$make_cloud_store_reference_vector@UWiFiProfile@WiFi@Data@Windows@@@cloud_store@wil@@CA?AV?$vector@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@PEAU?$IVectorView@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@@Collections@Foundation@Windows@@@Z; wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::WiFi::WiFiProfile>(Windows::Foundation::Collections::IVectorView<Windows::Internal::Storage::Cloud::CloudStoreItemName *> *)
0x180017c5b  nop
0x180017c5c  mov     rcx, [rsp+170h+var_120]
0x180017c61  test    rcx, rcx
0x180017c64  jz      short loc_180017C73
0x180017c66  mov     rax, [rcx]
0x180017c69  mov     rax, [rax+10h]
0x180017c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c72  nop
0x180017c73  mov     rdx, [rbp+70h+var_D0]
0x180017c77  cmp     rdx, 7
0x180017c7b  ja      loc_180017D0F
0x180017c81  mov     rax, rsi
0x180017c84  mov     rcx, [rbp+70h+var_48]
0x180017c88  xor     rcx, rsp; StackCookie
0x180017c8b  call    __security_check_cookie
0x180017c90  add     rsp, 138h
0x180017c97  pop     r15
0x180017c99  pop     r14
0x180017c9b  pop     r13
0x180017c9d  pop     r12
0x180017c9f  pop     rdi
0x180017ca0  pop     rsi
0x180017ca1  pop     rbx
0x180017ca2  pop     rbp
0x180017ca3  retn
0x180017ca4  xor     r9d, r9d; lpArguments
0x180017ca7  xor     r8d, r8d; nNumberOfArguments
0x180017caa  mov     edx, r13d; dwExceptionFlags
0x180017cad  mov     ecx, eax; dwExceptionCode
0x180017caf  call    cs:__imp_RaiseException
0x180017cb5  nop
0x180017cb6  xor     r9d, r9d; lpArguments
0x180017cb9  xor     r8d, r8d; nNumberOfArguments
0x180017cbc  lea     edx, [r9+1]; dwExceptionFlags
0x180017cc0  mov     ecx, eax; dwExceptionCode
0x180017cc2  call    cs:__imp_RaiseException
0x180017cc8  nop
0x180017cc9  xor     r9d, r9d; lpArguments
0x180017ccc  xor     r8d, r8d; nNumberOfArguments
0x180017ccf  lea     edx, [r9+1]; dwExceptionFlags
0x180017cd3  mov     ecx, eax; dwExceptionCode
0x180017cd5  call    cs:__imp_RaiseException
0x180017cdb  nop
0x180017cdc  mov     r8, [rax]
0x180017cdf  jmp     loc_180017BB0
0x180017ce4  mov     r9d, eax; char *
0x180017ce7  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180017cee  mov     edx, 553h; void *
0x180017cf3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017cf9  lea     rdx, ds:2[rdx*2]
0x180017d01  mov     rcx, [rbp+70h+var_68]
0x180017d05  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017d0a  jmp     loc_180017C15
0x180017d0f  lea     rdx, ds:2[rdx*2]
0x180017d17  mov     rcx, [rbp+70h+sourceString]
0x180017d1b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017d20  jmp     loc_180017C81
```
