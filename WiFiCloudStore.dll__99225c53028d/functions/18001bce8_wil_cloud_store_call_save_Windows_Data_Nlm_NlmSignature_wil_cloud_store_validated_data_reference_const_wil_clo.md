# wil::cloud_store::call_save<Windows::Data::Nlm::NlmSignature>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature> const &,unsigned __int64,wil::cloud_store_save_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18001bce8`
- end: `0x18001c11f`
- name: `??$call_save@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@AEAA?AVcloud_store_save_result@1@AEBUvalidated_data_reference@01@AEBV?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@1@_KW4cloud_store_save_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1079`
- prototype: `wil::cloud_store_save_result *__fastcall(_QWORD *, wil::cloud_store_save_result *, HSTRING, __int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003019c`

## callees

- `0x1800062c0`
- `0x1800075bc`
- `0x1800169bc`
- `0x18001bce8`
- `0x180023680`
- `0x180025308`
- `0x180026304`
- `0x180028190`
- `0x18002a030`
- `0x18002e2d0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001be05`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001be5d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001bec3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001bf1d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c0ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c0be`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c0d1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c0e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001be05`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001be5d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001bec3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001bf1d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c0ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c0be`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c0d1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c0e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001be14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001be74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bed6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bf35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001be14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001be74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bed6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bf35`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
wil::cloud_store_save_result *__fastcall wil::cloud_store::call_save<Windows::Data::Nlm::NlmSignature>(
        _QWORD *a1,
        wil::cloud_store_save_result *a2,
        HSTRING a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7)
{
  __int64 *v10; // rax
  char v11; // bl
  __int64 v12; // rdi
  struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *v13; // rcx
  __int64 v14; // rax
  const WCHAR *v15; // rcx
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rdx
  int v18; // esi
  signed int v19; // eax
  const WCHAR *v20; // rcx
  unsigned __int64 v21; // rdx
  signed int v22; // eax
  const WCHAR *v23; // rcx
  unsigned __int64 v24; // rdx
  signed int v25; // eax
  signed int v26; // eax
  _QWORD *v27; // rdx
  __int64 *v28; // rax
  __int64 v29; // r8
  int v30; // eax
  wil::cloud_store_save_result *v31; // rbx
  __int64 v33; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *v34; // [rsp+80h] [rbp-80h]
  __int64 *v35; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v36; // [rsp+90h] [rbp-70h]
  wil::cloud_store_save_result *v37; // [rsp+98h] [rbp-68h]
  __int64 v38; // [rsp+A0h] [rbp-60h]
  HSTRING_HEADER v39; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING v40; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER v41; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v42; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER v43; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING v44; // [rsp+100h] [rbp+0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+108h] [rbp+8h] BYREF
  HSTRING string; // [rsp+120h] [rbp+20h] BYREF
  void *v47; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int64 v48; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v37 = a2;
  v36 = a1;
  LODWORD(v33) = 0;
  wil::cloud_store::convert_cloud_store_save_options(a6);
  if ( (a6 & 8) != 0 )
  {
    v33 = 0;
    v10 = &v33;
    v11 = 1;
    v12 = 0;
  }
  else
  {
    v10 = (__int64 *)wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>(&v35, a4);
    v11 = 2;
    v12 = *v10;
  }
  *v10 = 0;
  v38 = v12;
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v35);
  }
  if ( (v11 & 1) != 0 )
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v33);
  v34 = 0;
  v35 = *(__int64 **)wil::details::shared_cloud_store_state::get_cloud_store(*a1);
  v33 = *v35;
  v13 = v34;
  v34 = 0;
  if ( v13 )
    (*(void (__fastcall **)(struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = wil::cloud_store::widen_string(&v47, a7);
  v15 = (const WCHAR *)v14;
  if ( *(_QWORD *)(v14 + 24) > 7u )
    v15 = *(const WCHAR **)v14;
  string = 0;
  v16 = -1;
  v17 = -1;
  do
    ++v17;
  while ( v15[v17] );
  v18 = -1;
  if ( v17 > 0xFFFFFFFF || (int)v17 + 1 < (unsigned int)v17 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v19 = WindowsCreateStringReference(v15, v17, &hstringHeader, &string);
  if ( v19 < 0 )
  {
    RaiseException(v19, 1u, 0, 0);
LABEL_53:
    RaiseException(v22, 1u, 0, 0);
LABEL_54:
    RaiseException(v25, 1u, 0, 0);
LABEL_55:
    RaiseException(v26, 1u, 0, 0);
    goto LABEL_56;
  }
  v20 = (const WCHAR *)(a3 + 16);
  if ( *((_QWORD *)a3 + 11) > 7u )
    v20 = *(const WCHAR **)v20;
  v44 = 0;
  v21 = -1;
  do
    ++v21;
  while ( v20[v21] );
  if ( v21 > 0xFFFFFFFF || (int)v21 + 1 < (unsigned int)v21 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v22 = WindowsCreateStringReference(v20, v21, &v43, &v44);
  v18 = 0;
  if ( v22 < 0 )
    goto LABEL_53;
  v23 = (const WCHAR *)(a3 + 8);
  if ( *((_QWORD *)a3 + 7) > 7u )
    v23 = *(const WCHAR **)v23;
  v42 = 0;
  v24 = -1;
  do
    ++v24;
  while ( v23[v24] );
  if ( v24 > 0xFFFFFFFF || (int)v24 + 1 < (unsigned int)v24 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v25 = WindowsCreateStringReference(v23, v24, &v41, &v42);
  if ( v25 < 0 )
    goto LABEL_54;
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(HSTRING *)a3;
  v40 = 0;
  do
    ++v16;
  while ( *((_WORD *)a3 + v16) );
  if ( v16 > 0xFFFFFFFF || (int)v16 + 1 < (unsigned int)v16 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v18 = (int)v42;
  v26 = WindowsCreateStringReference((PCWSTR)a3, v16, &v39, &v40);
  a3 = 0;
  if ( v26 < 0 )
    goto LABEL_55;
  v27 = v36;
  v28 = (__int64 *)v36[3];
  if ( !v28 )
  {
    v29 = 0;
    goto LABEL_43;
  }
LABEL_56:
  v29 = *v28;
LABEL_43:
  v30 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, HSTRING))(v33 + 88))(
          v35,
          *((unsigned int *)v27 + 4),
          v29,
          v40);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5E4,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v30,
      v18);
  v40 = a3;
  v42 = a3;
  v44 = a3;
  string = a3;
  if ( v48 > 7 )
    std::_Deallocate<16>(v47, 2 * v48 + 2);
  v31 = v37;
  wil::cloud_store_save_result::cloud_store_save_result(v37, v34);
  if ( v34 )
    (*(void (__fastcall **)(struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return v31;
}

```

## disassembly

```asm
0x18001bce8  push    rbp
0x18001bcea  push    rbx
0x18001bceb  push    rsi
0x18001bcec  push    rdi
0x18001bced  push    r12
0x18001bcef  push    r13
0x18001bcf1  push    r14
0x18001bcf3  push    r15
0x18001bcf5  lea     rbp, [rsp-58h]
0x18001bcfa  sub     rsp, 158h
0x18001bd01  mov     rax, cs:__security_cookie
0x18001bd08  xor     rax, rsp
0x18001bd0b  mov     [rbp+90h+var_48], rax
0x18001bd0f  mov     r15, r9
0x18001bd12  mov     r14, r8
0x18001bd15  mov     [rbp+90h+var_F8], rdx
0x18001bd19  mov     r12, rcx
0x18001bd1c  mov     [rbp+90h+var_100], rcx
0x18001bd20  mov     rsi, [rbp+90h+arg_30]
0x18001bd27  xor     r13d, r13d
0x18001bd2a  mov     dword ptr [rsp+190h+var_118], r13d
0x18001bd2f  mov     ecx, [rbp+90h+arg_28]
0x18001bd35  call    ?convert_cloud_store_save_options@cloud_store@wil@@CA?AW4SaveOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_save_options@2@@Z; wil::cloud_store::convert_cloud_store_save_options(wil::cloud_store_save_options)
0x18001bd3a  mov     [rsp+190h+var_120], eax
0x18001bd3e  cmp     [r15+19h], r13b
0x18001bd42  jnz     short loc_18001BD4A
0x18001bd44  cmp     [r15+10h], r13
0x18001bd48  jnz     short loc_18001BD51
0x18001bd4a  or      eax, 8
0x18001bd4d  mov     [rsp+190h+var_120], eax
0x18001bd51  test    byte ptr [rbp+90h+arg_28], 8
0x18001bd58  jz      loc_18001C035
0x18001bd5e  mov     [rsp+190h+var_118], r13
0x18001bd63  lea     rax, [rsp+190h+var_118]
0x18001bd68  mov     ebx, 1
0x18001bd6d  mov     rdi, r13
0x18001bd70  mov     [rax], r13
0x18001bd73  mov     [rbp+90h+var_F0], rdi
0x18001bd77  test    bl, 2
0x18001bd7a  jnz     loc_18001C06E
0x18001bd80  test    bl, 1
0x18001bd83  jnz     loc_18001C07F
0x18001bd89  mov     [rbp+90h+var_110], r13
0x18001bd8d  mov     rcx, [r12]
0x18001bd91  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x18001bd96  mov     rax, [rax]
0x18001bd99  mov     [rbp+90h+var_108], rax
0x18001bd9d  mov     rax, [rax]
0x18001bda0  mov     [rsp+190h+var_118], rax
0x18001bda5  mov     rcx, [rbp+90h+var_110]
0x18001bda9  mov     [rbp+90h+var_110], r13
0x18001bdad  test    rcx, rcx
0x18001bdb0  jnz     loc_18001C08E
0x18001bdb6  mov     rdx, rsi
0x18001bdb9  lea     rcx, [rbp+90h+var_68]
0x18001bdbd  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x18001bdc2  mov     rcx, rax; sourceString
0x18001bdc5  cmp     qword ptr [rax+18h], 7
0x18001bdca  ja      loc_18001C04E
0x18001bdd0  mov     [rbp+90h+string], r13
0x18001bdd4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001bdd8  mov     rdx, rbx
0x18001bddb  inc     rdx; length
0x18001bdde  cmp     [rcx+rdx*2], r13w
0x18001bde3  jnz     short loc_18001BDDB
0x18001bde5  mov     esi, 0FFFFFFFFh
0x18001bdea  cmp     rdx, rsi
0x18001bded  ja      short loc_18001BDF6
0x18001bdef  lea     eax, [rdx+1]
0x18001bdf2  cmp     eax, edx
0x18001bdf4  jnb     short loc_18001BE0C
0x18001bdf6  xor     r9d, r9d; lpArguments
0x18001bdf9  xor     r8d, r8d; nNumberOfArguments
0x18001bdfc  lea     edx, [r9+1]; dwExceptionFlags
0x18001be00  mov     ecx, 80070216h; dwExceptionCode
0x18001be05  call    cs:__imp_RaiseException
0x18001be0b  int     3; Trap to Debugger
0x18001be0c  lea     r9, [rbp+90h+string]; string
0x18001be10  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x18001be14  call    cs:__imp_WindowsCreateStringReference
0x18001be1a  test    eax, eax
0x18001be1c  js      loc_18001C09F
0x18001be22  lea     rcx, [r14+40h]; sourceString
0x18001be26  cmp     qword ptr [rcx+18h], 7
0x18001be2b  ja      loc_18001C056
0x18001be31  mov     [rbp+90h+var_90], r13
0x18001be35  mov     rdx, rbx
0x18001be38  inc     rdx; length
0x18001be3b  cmp     [rcx+rdx*2], r13w
0x18001be40  jnz     short loc_18001BE38
0x18001be42  cmp     rdx, rsi
0x18001be45  ja      short loc_18001BE4E
0x18001be47  lea     eax, [rdx+1]
0x18001be4a  cmp     eax, edx
0x18001be4c  jnb     short loc_18001BE64
0x18001be4e  xor     r9d, r9d; lpArguments
0x18001be51  xor     r8d, r8d; nNumberOfArguments
0x18001be54  lea     edx, [r9+1]; dwExceptionFlags
0x18001be58  mov     ecx, 80070216h; dwExceptionCode
0x18001be5d  call    cs:__imp_RaiseException
0x18001be63  int     3; Trap to Debugger
0x18001be64  mov     r12, [rbp+90h+string]
0x18001be68  mov     r13, [r15+10h]
0x18001be6c  lea     r9, [rbp+90h+var_90]; string
0x18001be70  lea     r8, [rbp+90h+var_A8]; hstringHeader
0x18001be74  call    cs:__imp_WindowsCreateStringReference
0x18001be7a  xor     esi, esi
0x18001be7c  test    eax, eax
0x18001be7e  js      loc_18001C0B2
0x18001be84  lea     rcx, [r14+20h]; sourceString
0x18001be88  cmp     qword ptr [rcx+18h], 7
0x18001be8d  ja      loc_18001C05E
0x18001be93  mov     [rbp+90h+var_B0], rsi
0x18001be97  mov     rdx, rbx
0x18001be9a  inc     rdx; length
0x18001be9d  cmp     [rcx+rdx*2], si
0x18001bea1  jnz     short loc_18001BE9A
0x18001bea3  mov     eax, 0FFFFFFFFh
0x18001bea8  cmp     rdx, rax
0x18001beab  ja      short loc_18001BEB4
0x18001bead  lea     eax, [rdx+1]
0x18001beb0  cmp     eax, edx
0x18001beb2  jnb     short loc_18001BECA
0x18001beb4  xor     r9d, r9d; lpArguments
0x18001beb7  xor     r8d, r8d; nNumberOfArguments
0x18001beba  lea     edx, [r9+1]; dwExceptionFlags
0x18001bebe  mov     ecx, 80070216h; dwExceptionCode
0x18001bec3  call    cs:__imp_RaiseException
0x18001bec9  int     3; Trap to Debugger
0x18001beca  mov     r15, [rbp+90h+var_90]
0x18001bece  lea     r9, [rbp+90h+var_B0]; string
0x18001bed2  lea     r8, [rbp+90h+var_C8]; hstringHeader
0x18001bed6  call    cs:__imp_WindowsCreateStringReference
0x18001bedc  test    eax, eax
0x18001bede  js      loc_18001C0C5
0x18001bee4  cmp     qword ptr [r14+18h], 7
0x18001bee9  ja      loc_18001C066
0x18001beef  mov     [rbp+90h+var_D0], rsi
0x18001bef3  inc     rbx
0x18001bef6  cmp     [r14+rbx*2], si
0x18001befb  jnz     short loc_18001BEF3
0x18001befd  mov     eax, 0FFFFFFFFh
0x18001bf02  cmp     rbx, rax
0x18001bf05  ja      short loc_18001BF0E
0x18001bf07  lea     eax, [rbx+1]
0x18001bf0a  cmp     eax, ebx
0x18001bf0c  jnb     short loc_18001BF24
0x18001bf0e  xor     r9d, r9d; lpArguments
0x18001bf11  xor     r8d, r8d; nNumberOfArguments
0x18001bf14  lea     edx, [r9+1]; dwExceptionFlags
0x18001bf18  mov     ecx, 80070216h; dwExceptionCode
0x18001bf1d  call    cs:__imp_RaiseException
0x18001bf23  int     3; Trap to Debugger
0x18001bf24  mov     rsi, [rbp+90h+var_B0]
0x18001bf28  lea     r9, [rbp+90h+var_D0]; string
0x18001bf2c  lea     r8, [rbp+90h+var_E8]; hstringHeader
0x18001bf30  mov     edx, ebx; length
0x18001bf32  mov     rcx, r14; sourceString
0x18001bf35  call    cs:__imp_WindowsCreateStringReference
0x18001bf3b  xor     r14d, r14d
0x18001bf3e  test    eax, eax
0x18001bf40  js      loc_18001C0D8
0x18001bf46  mov     rdx, [rbp+90h+var_100]
0x18001bf4a  mov     rax, [rdx+18h]
0x18001bf4e  test    rax, rax
0x18001bf51  jnz     loc_18001C0EB
0x18001bf57  mov     r8d, r14d
0x18001bf5a  lea     rax, [rbp+90h+var_110]
0x18001bf5e  mov     [rsp+190h+var_138], rax
0x18001bf63  mov     [rsp+190h+var_140], r12
0x18001bf68  mov     eax, [rsp+190h+var_120]
0x18001bf6c  mov     [rsp+190h+var_148], eax
0x18001bf70  mov     [rsp+190h+var_150], rdi
0x18001bf75  mov     rax, [rbp+90h+arg_20]
0x18001bf7c  mov     [rsp+190h+var_158], rax
0x18001bf81  mov     [rsp+190h+var_160], r13
0x18001bf86  mov     [rsp+190h+var_168], r15
0x18001bf8b  mov     qword ptr [rsp+190h+var_170], rsi; int
0x18001bf90  mov     r9, [rbp+90h+var_D0]
0x18001bf94  mov     edx, [rdx+10h]
0x18001bf97  mov     rcx, [rbp+90h+var_108]
0x18001bf9b  mov     rax, [rsp+190h+var_118]
0x18001bfa0  mov     rax, [rax+58h]
0x18001bfa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfa9  mov     rcx, [rbp+98h]; this
0x18001bfb0  test    eax, eax
0x18001bfb2  js      loc_18001C0F3
0x18001bfb8  mov     [rbp+90h+var_D0], r14
0x18001bfbc  mov     [rbp+90h+var_B0], r14
0x18001bfc0  mov     [rbp+90h+var_90], r14
0x18001bfc4  mov     [rbp+90h+string], r14
0x18001bfc8  mov     rdx, [rbp+90h+var_50]
0x18001bfcc  cmp     rdx, 7
0x18001bfd0  ja      loc_18001C108
0x18001bfd6  mov     rdx, [rbp+90h+var_110]; struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *
0x18001bfda  mov     rbx, [rbp+90h+var_F8]
0x18001bfde  mov     rcx, rbx; this
0x18001bfe1  call    ??0cloud_store_save_result@wil@@QEAA@PEAUICloudStoreSaveResult@Cloud@Storage@Internal@Windows@@@Z; wil::cloud_store_save_result::cloud_store_save_result(Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *)
0x18001bfe6  nop
0x18001bfe7  mov     rcx, [rbp+90h+var_110]
0x18001bfeb  test    rcx, rcx
0x18001bfee  jz      short loc_18001BFFD
0x18001bff0  mov     rax, [rcx]
0x18001bff3  mov     rax, [rax+10h]
0x18001bff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bffc  nop
0x18001bffd  test    rdi, rdi
0x18001c000  jz      short loc_18001C012
0x18001c002  mov     rdx, [rdi]
0x18001c005  mov     rcx, rdi
0x18001c008  mov     rax, [rdx+10h]
0x18001c00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c011  nop
0x18001c012  mov     rax, rbx
0x18001c015  mov     rcx, [rbp+90h+var_48]
0x18001c019  xor     rcx, rsp; StackCookie
0x18001c01c  call    __security_check_cookie
0x18001c021  add     rsp, 158h
0x18001c028  pop     r15
0x18001c02a  pop     r14
0x18001c02c  pop     r13
0x18001c02e  pop     r12
0x18001c030  pop     rdi
0x18001c031  pop     rsi
0x18001c032  pop     rbx
0x18001c033  pop     rbp
0x18001c034  retn
0x18001c035  mov     rdx, r15
0x18001c038  lea     rcx, [rbp+90h+var_108]
0x18001c03c  call    ??$marshal@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@AEBV?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@1@@Z; wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>(wil::cloud_store_data<Windows::Data::Nlm::NlmSignature> const &)
0x18001c041  mov     ebx, 2
0x18001c046  mov     rdi, [rax]
0x18001c049  jmp     loc_18001BD70
0x18001c04e  mov     rcx, [rax]
0x18001c051  jmp     loc_18001BDD0
0x18001c056  mov     rcx, [rcx]
0x18001c059  jmp     loc_18001BE31
0x18001c05e  mov     rcx, [rcx]
0x18001c061  jmp     loc_18001BE93
0x18001c066  mov     r14, [r14]
0x18001c069  jmp     loc_18001BEEF
0x18001c06e  and     ebx, 0FFFFFFFDh
0x18001c071  lea     rcx, [rbp+90h+var_108]
0x18001c075  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18001c07a  jmp     loc_18001BD80
0x18001c07f  lea     rcx, [rsp+190h+var_118]
0x18001c084  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18001c089  jmp     loc_18001BD89
0x18001c08e  mov     rax, [rcx]
0x18001c091  mov     rax, [rax+10h]
0x18001c095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c09a  jmp     loc_18001BDB6
0x18001c09f  xor     r9d, r9d; lpArguments
0x18001c0a2  xor     r8d, r8d; nNumberOfArguments
0x18001c0a5  lea     edx, [r9+1]; dwExceptionFlags
0x18001c0a9  mov     ecx, eax; dwExceptionCode
0x18001c0ab  call    cs:__imp_RaiseException
0x18001c0b1  nop
0x18001c0b2  xor     r9d, r9d; lpArguments
0x18001c0b5  xor     r8d, r8d; nNumberOfArguments
0x18001c0b8  lea     edx, [r9+1]; dwExceptionFlags
0x18001c0bc  mov     ecx, eax; dwExceptionCode
0x18001c0be  call    cs:__imp_RaiseException
0x18001c0c4  nop
0x18001c0c5  xor     r9d, r9d; lpArguments
0x18001c0c8  xor     r8d, r8d; nNumberOfArguments
0x18001c0cb  lea     edx, [r9+1]; dwExceptionFlags
0x18001c0cf  mov     ecx, eax; dwExceptionCode
0x18001c0d1  call    cs:__imp_RaiseException
0x18001c0d7  nop
0x18001c0d8  xor     r9d, r9d; lpArguments
0x18001c0db  xor     r8d, r8d; nNumberOfArguments
0x18001c0de  lea     edx, [r9+1]; dwExceptionFlags
0x18001c0e2  mov     ecx, eax; dwExceptionCode
0x18001c0e4  call    cs:__imp_RaiseException
0x18001c0ea  nop
0x18001c0eb  mov     r8, [rax]
0x18001c0ee  jmp     loc_18001BF5A
0x18001c0f3  mov     r9d, eax; char *
0x18001c0f6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18001c0fd  mov     edx, 5E4h; void *
0x18001c102  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c108  lea     rdx, ds:2[rdx*2]
0x18001c110  mov     rcx, [rbp+90h+var_68]
0x18001c114  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c119  jmp     loc_18001BFD6
```
