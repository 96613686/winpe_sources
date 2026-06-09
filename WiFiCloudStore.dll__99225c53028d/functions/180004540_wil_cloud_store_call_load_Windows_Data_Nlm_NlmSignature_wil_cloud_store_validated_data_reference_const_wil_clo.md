# wil::cloud_store::call_load<Windows::Data::Nlm::NlmSignature>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180004540`
- end: `0x1800049ad`
- name: `??$call_load@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1133`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64 *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180003850`

## callees

- `0x180004050`
- `0x180004540`
- `0x1800062c0`
- `0x18001ea20`
- `0x180025308`
- `0x18002a030`
- `0x18002c138`
- `0x18002d124`
- `0x18002e2d0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800045db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800045db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800045f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800045f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004685`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000470f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000476e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800047ca`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004912`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000494a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000495e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004972`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004685`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000470f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000476e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800047ca`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004912`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000494a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000495e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004972`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800046a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000472e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000478d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800047ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800046a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000472e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000478d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800047ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::cloud_store::call_load<Windows::Data::Nlm::NlmSignature>(
        _QWORD *a1,
        __int64 a2,
        __int64 *a3,
        unsigned int a4,
        __int64 a5)
{
  int v7; // esi
  __int64 v8; // r14
  __int64 **v9; // rbx
  _QWORD *v10; // rcx
  RTL_SRWLOCK *v11; // r14
  __int64 v12; // rax
  const WCHAR *v13; // rcx
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rdx
  signed int v16; // eax
  const char *v17; // r9
  const WCHAR *v18; // rcx
  unsigned __int64 v19; // rdx
  signed int v20; // eax
  const WCHAR *v21; // rcx
  unsigned __int64 v22; // rdx
  signed int v23; // eax
  signed int v24; // eax
  _QWORD *v25; // rdx
  __int64 *v26; // rax
  __int64 v27; // r8
  int v28; // eax
  __int64 v29; // rbx
  __int64 *v31; // rdx
  wil::details::in1diag3 *v32; // rcx
  __int64 *v33; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A0h]
  _QWORD *v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+78h] [rbp-88h]
  HSTRING_HEADER v37; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v38; // [rsp+98h] [rbp-68h] BYREF
  HSTRING_HEADER v39; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING v40; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v41; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v42; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING string; // [rsp+F8h] [rbp-8h] BYREF
  void *v45; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v46; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v36 = a2;
  v35 = a1;
  v34 = a2;
  v7 = a5;
  v8 = *a1;
  v9 = (__int64 **)(*a1 + 72LL);
  if ( !*v9 )
  {
    v10 = (_QWORD *)(v8 + 24);
    if ( *(_QWORD *)(v8 + 48) > 7u )
      v10 = (_QWORD *)*v10;
    wil::details::CreateCloudStoreDefaultWithWaitTime(
      (unsigned int)&v33,
      *(_DWORD *)v8,
      *(_QWORD *)(v8 + 8),
      *(_QWORD *)(v8 + 16),
      (__int64)v10,
      v8 + 56);
    v11 = (RTL_SRWLOCK *)(v8 + 64);
    AcquireSRWLockExclusive(v11);
    if ( !*v9 )
    {
      v31 = v33;
      v33 = 0;
      wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>::attach(v9, v31);
    }
    if ( v11 )
      ReleaseSRWLockExclusive(v11);
    if ( v33 )
      (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
  }
  v33 = *v9;
  v34 = *v33;
  v12 = wil::cloud_store::widen_string(&v45, a5);
  v13 = (const WCHAR *)v12;
  if ( *(_QWORD *)(v12 + 24) > 7u )
    v13 = *(const WCHAR **)v12;
  string = 0;
  v14 = -1;
  v15 = -1;
  do
    ++v15;
  while ( v13[v15] );
  if ( v15 > 0xFFFFFFFF || (int)v15 + 1 < (unsigned int)v15 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v16 = WindowsCreateStringReference(v13, v15, &hstringHeader, &string);
  if ( v16 < 0 )
  {
    RaiseException(v16, 1u, 0, 0);
    goto LABEL_52;
  }
  if ( (a4 & 4) != 0 )
  {
    v32 = retaddr;
    if ( (a4 & 1) == 0 )
LABEL_52:
      wil::details::in1diag3::_FailFast_Unexpected(
        v32,
        (void *)0x70D,
        (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
        v17);
  }
  v18 = (const WCHAR *)(a3 + 8);
  if ( (unsigned __int64)a3[11] > 7 )
    v18 = *(const WCHAR **)v18;
  v42 = 0;
  v19 = -1;
  do
    ++v19;
  while ( v18[v19] );
  if ( v19 > 0xFFFFFFFF || (int)v19 + 1 < (unsigned int)v19 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v20 = WindowsCreateStringReference(v18, v19, &v41, &v42);
  if ( v20 < 0 )
  {
    RaiseException(v20, 1u, 0, 0);
LABEL_54:
    RaiseException(v23, 1u, 0, 0);
LABEL_55:
    RaiseException(v24, 1u, 0, 0);
    goto LABEL_56;
  }
  v21 = (const WCHAR *)(a3 + 4);
  if ( (unsigned __int64)a3[7] > 7 )
    v21 = *(const WCHAR **)v21;
  v7 = 0;
  v40 = 0;
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  if ( v22 > 0xFFFFFFFF || (int)v22 + 1 < (unsigned int)v22 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v23 = WindowsCreateStringReference(v21, v22, &v39, &v40);
  if ( v23 < 0 )
    goto LABEL_54;
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (__int64 *)*a3;
  v38 = 0;
  do
    ++v14;
  while ( *((_WORD *)a3 + v14) );
  if ( v14 > 0xFFFFFFFF || (int)v14 + 1 < (unsigned int)v14 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v7 = (int)v40;
  v24 = WindowsCreateStringReference((PCWSTR)a3, v14, &v37, &v38);
  if ( v24 < 0 )
    goto LABEL_55;
  v25 = v35;
  v26 = (__int64 *)v35[3];
  v14 = 0;
  if ( !v26 )
  {
    v27 = 0;
    goto LABEL_45;
  }
LABEL_56:
  v27 = *v26;
LABEL_45:
  v28 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, HSTRING))(v34 + 72))(
          v33,
          *((unsigned int *)v25 + 4),
          v27,
          v38);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x588,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v28,
      v7);
  v38 = (HSTRING)v14;
  v40 = (HSTRING)v14;
  v42 = (HSTRING)v14;
  string = (HSTRING)v14;
  if ( v46 > 7 )
    std::_Deallocate<16>(v45, 2 * v46 + 2);
  v29 = v36;
  wil::cloud_store::unmarshal<Windows::Data::Nlm::NlmSignature>(v36, 0, a4);
  return v29;
}

```

## disassembly

```asm
0x180004540  mov     [rsp-8+arg_18], rbx
0x180004545  push    rbp
0x180004546  push    rsi
0x180004547  push    rdi
0x180004548  push    r12
0x18000454a  push    r13
0x18000454c  push    r14
0x18000454e  push    r15
0x180004550  lea     rbp, [rsp-30h]
0x180004555  sub     rsp, 130h
0x18000455c  mov     rax, cs:__security_cookie
0x180004563  xor     rax, rsp
0x180004566  mov     [rbp+60h+var_40], rax
0x18000456a  mov     r12d, r9d
0x18000456d  mov     rdi, r8
0x180004570  mov     rax, rdx
0x180004573  mov     [rsp+160h+var_E8], rdx
0x180004578  mov     rdx, rcx
0x18000457b  mov     [rsp+160h+var_F0], rcx
0x180004580  mov     [rsp+160h+var_100], rax
0x180004585  mov     rsi, [rbp+60h+arg_20]
0x18000458c  xor     r15d, r15d
0x18000458f  mov     ecx, r15d
0x180004592  mov     [rsp+160h+var_110], rcx
0x180004597  mov     r14, [rdx]
0x18000459a  lea     rbx, [r14+48h]
0x18000459e  cmp     [rbx], r15
0x1800045a1  jnz     short loc_180004616
0x1800045a3  lea     rcx, [r14+18h]
0x1800045a7  cmp     qword ptr [rcx+18h], 7
0x1800045ac  jbe     short loc_1800045B1
0x1800045ae  mov     rcx, [rcx]
0x1800045b1  lea     rax, [r14+38h]
0x1800045b5  mov     [rsp+160h+var_138], rax
0x1800045ba  mov     qword ptr [rsp+160h+var_140], rcx
0x1800045bf  mov     r9, [r14+10h]
0x1800045c3  mov     r8, [r14+8]
0x1800045c7  mov     edx, [r14]
0x1800045ca  lea     rcx, [rsp+160h+var_108]
0x1800045cf  call    ?CreateCloudStoreDefaultWithWaitTime@details@wil@@YA?AV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@2@W4CloudStoreOptions@Cloud@Storage@Internal@Windows@@PEAUIUser@System@8@PEAUIWebAccount@Credentials@Security@8@PEBGAEBUWaitTimes@5678@@Z; wil::details::CreateCloudStoreDefaultWithWaitTime(Windows::Internal::Storage::Cloud::CloudStoreOptions,Windows::System::IUser *,Windows::Security::Credentials::IWebAccount *,ushort const *,Windows::Internal::Storage::Cloud::WaitTimes const &)
0x1800045d4  add     r14, 40h ; '@'
0x1800045d8  mov     rcx, r14; SRWLock
0x1800045db  call    cs:__imp_AcquireSRWLockExclusive
0x1800045e1  cmp     qword ptr [rbx], 0
0x1800045e5  jz      loc_1800048CC
0x1800045eb  test    r14, r14
0x1800045ee  jz      short loc_1800045FA
0x1800045f0  mov     rcx, r14; SRWLock
0x1800045f3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800045f9  nop
0x1800045fa  mov     rcx, [rsp+160h+var_108]
0x1800045ff  test    rcx, rcx
0x180004602  jz      short loc_180004611
0x180004604  mov     rax, [rcx]
0x180004607  mov     rax, [rax+10h]
0x18000460b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004610  nop
0x180004611  mov     rcx, [rsp+160h+var_110]
0x180004616  mov     rax, [rbx]
0x180004619  mov     [rsp+160h+var_108], rax
0x18000461e  mov     rax, [rax]
0x180004621  mov     [rsp+160h+var_100], rax
0x180004626  mov     [rsp+160h+var_110], r15
0x18000462b  test    rcx, rcx
0x18000462e  jnz     loc_1800048F4
0x180004634  mov     rdx, rsi
0x180004637  lea     rcx, [rbp+60h+var_60]
0x18000463b  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180004640  mov     rcx, rax; sourceString
0x180004643  cmp     qword ptr [rax+18h], 7
0x180004648  ja      short loc_18000468C
0x18000464a  mov     [rbp+60h+string], r15
0x18000464e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180004655  mov     rdx, rbx
0x180004658  nop     dword ptr [rax+rax+00000000h]
0x180004660  inc     rdx; length
0x180004663  cmp     word ptr [rcx+rdx*2], 0
0x180004668  jnz     short loc_180004660
0x18000466a  mov     r14d, 0FFFFFFFFh
0x180004670  cmp     rdx, r14
0x180004673  jbe     short loc_180004691
0x180004675  xor     r9d, r9d; lpArguments
0x180004678  xor     r8d, r8d; nNumberOfArguments
0x18000467b  mov     edx, 1; dwExceptionFlags
0x180004680  mov     ecx, 80070216h; dwExceptionCode
0x180004685  call    cs:__imp_RaiseException
0x18000468b  int     3; Trap to Debugger
0x18000468c  mov     rcx, [rax]
0x18000468f  jmp     short loc_18000464A
0x180004691  lea     eax, [rdx+1]
0x180004694  cmp     eax, edx
0x180004696  jb      short loc_180004675
0x180004698  lea     r9, [rbp+60h+string]; string
0x18000469c  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x1800046a0  call    cs:__imp_WindowsCreateStringReference
0x1800046a6  test    eax, eax
0x1800046a8  js      loc_180004905
0x1800046ae  mov     r13d, r15d
0x1800046b1  mov     eax, r12d
0x1800046b4  and     eax, 1
0x1800046b7  jz      short loc_1800046BF
0x1800046b9  mov     r13d, 1
0x1800046bf  test    r12b, 4
0x1800046c3  jnz     loc_1800048E3
0x1800046c9  test    r12b, 8
0x1800046cd  jnz     loc_18000492B
0x1800046d3  test    r12b, 10h
0x1800046d7  jnz     loc_180004934
0x1800046dd  lea     rcx, [rdi+40h]; sourceString
0x1800046e1  cmp     qword ptr [rcx+18h], 7
0x1800046e6  ja      short loc_180004716
0x1800046e8  mov     [rbp+60h+var_88], r15
0x1800046ec  mov     rdx, rbx
0x1800046ef  nop
0x1800046f0  inc     rdx; length
0x1800046f3  cmp     word ptr [rcx+rdx*2], 0
0x1800046f8  jnz     short loc_1800046F0
0x1800046fa  cmp     rdx, r14
0x1800046fd  jbe     short loc_18000471B
0x1800046ff  xor     r9d, r9d; lpArguments
0x180004702  xor     r8d, r8d; nNumberOfArguments
0x180004705  mov     edx, 1; dwExceptionFlags
0x18000470a  mov     ecx, 80070216h; dwExceptionCode
0x18000470f  call    cs:__imp_RaiseException
0x180004715  int     3; Trap to Debugger
0x180004716  mov     rcx, [rcx]
0x180004719  jmp     short loc_1800046E8
0x18000471b  lea     eax, [rdx+1]
0x18000471e  cmp     eax, edx
0x180004720  jb      short loc_1800046FF
0x180004722  mov     r15, [rbp+60h+string]
0x180004726  lea     r9, [rbp+60h+var_88]; string
0x18000472a  lea     r8, [rbp+60h+var_A0]; hstringHeader
0x18000472e  call    cs:__imp_WindowsCreateStringReference
0x180004734  test    eax, eax
0x180004736  js      loc_18000493D
0x18000473c  lea     rcx, [rdi+20h]; sourceString
0x180004740  cmp     qword ptr [rcx+18h], 7
0x180004745  ja      short loc_180004775
0x180004747  xor     esi, esi
0x180004749  mov     [rbp+60h+var_A8], rsi
0x18000474d  mov     rdx, rbx
0x180004750  inc     rdx; length
0x180004753  cmp     [rcx+rdx*2], si
0x180004757  jnz     short loc_180004750
0x180004759  cmp     rdx, r14
0x18000475c  jbe     short loc_18000477A
0x18000475e  xor     r9d, r9d; lpArguments
0x180004761  xor     r8d, r8d; nNumberOfArguments
0x180004764  mov     edx, 1; dwExceptionFlags
0x180004769  mov     ecx, 80070216h; dwExceptionCode
0x18000476e  call    cs:__imp_RaiseException
0x180004774  int     3; Trap to Debugger
0x180004775  mov     rcx, [rcx]
0x180004778  jmp     short loc_180004747
0x18000477a  lea     eax, [rdx+1]
0x18000477d  cmp     eax, edx
0x18000477f  jb      short loc_18000475E
0x180004781  mov     r14, [rbp+60h+var_88]
0x180004785  lea     r9, [rbp+60h+var_A8]; string
0x180004789  lea     r8, [rbp+60h+var_C0]; hstringHeader
0x18000478d  call    cs:__imp_WindowsCreateStringReference
0x180004793  test    eax, eax
0x180004795  js      loc_180004951
0x18000479b  cmp     qword ptr [rdi+18h], 7
0x1800047a0  ja      short loc_1800047D1
0x1800047a2  mov     [rbp+60h+var_C8], rsi
0x1800047a6  inc     rbx
0x1800047a9  cmp     word ptr [rdi+rbx*2], 0
0x1800047ae  jnz     short loc_1800047A6
0x1800047b0  mov     eax, 0FFFFFFFFh
0x1800047b5  cmp     rbx, rax
0x1800047b8  jbe     short loc_1800047D6
0x1800047ba  xor     r9d, r9d; lpArguments
0x1800047bd  xor     r8d, r8d; nNumberOfArguments
0x1800047c0  mov     edx, 1; dwExceptionFlags
0x1800047c5  mov     ecx, 80070216h; dwExceptionCode
0x1800047ca  call    cs:__imp_RaiseException
0x1800047d0  int     3; Trap to Debugger
0x1800047d1  mov     rdi, [rdi]
0x1800047d4  jmp     short loc_1800047A2
0x1800047d6  lea     eax, [rbx+1]
0x1800047d9  cmp     eax, ebx
0x1800047db  jb      short loc_1800047BA
0x1800047dd  mov     rsi, [rbp+60h+var_A8]
0x1800047e1  lea     r9, [rbp+60h+var_C8]; string
0x1800047e5  lea     r8, [rbp+60h+var_E0]; hstringHeader
0x1800047e9  mov     edx, ebx; length
0x1800047eb  mov     rcx, rdi; sourceString
0x1800047ee  call    cs:__imp_WindowsCreateStringReference
0x1800047f4  test    eax, eax
0x1800047f6  js      loc_180004965
0x1800047fc  mov     rdx, [rsp+160h+var_F0]
0x180004801  mov     rax, [rdx+18h]
0x180004805  xor     ebx, ebx
0x180004807  test    rax, rax
0x18000480a  jnz     loc_180004979
0x180004810  mov     r8d, ebx
0x180004813  lea     rax, [rsp+160h+var_110]
0x180004818  mov     [rsp+160h+var_120], rax
0x18000481d  mov     [rsp+160h+var_128], r15
0x180004822  mov     [rsp+160h+var_130], r13d
0x180004827  mov     [rsp+160h+var_138], r14
0x18000482c  mov     qword ptr [rsp+160h+var_140], rsi; int
0x180004831  mov     r9, [rbp+60h+var_C8]
0x180004835  mov     edx, [rdx+10h]
0x180004838  mov     rcx, [rsp+160h+var_108]
0x18000483d  mov     rax, [rsp+160h+var_100]
0x180004842  mov     rax, [rax+48h]
0x180004846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000484b  mov     rcx, [rbp+68h]; this
0x18000484f  test    eax, eax
0x180004851  js      loc_180004981
0x180004857  mov     [rbp+60h+var_C8], rbx
0x18000485b  mov     [rbp+60h+var_A8], rbx
0x18000485f  mov     [rbp+60h+var_88], rbx
0x180004863  mov     [rbp+60h+string], rbx
0x180004867  mov     rdx, [rbp+60h+var_48]
0x18000486b  cmp     rdx, 7
0x18000486f  ja      loc_180004996
0x180004875  mov     r8d, r12d
0x180004878  mov     rdx, [rsp+160h+var_110]
0x18000487d  mov     rbx, [rsp+160h+var_E8]
0x180004882  mov     rcx, rbx
0x180004885  call    ??$unmarshal@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z; wil::cloud_store::unmarshal<Windows::Data::Nlm::NlmSignature>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)
0x18000488a  nop
0x18000488b  mov     rcx, [rsp+160h+var_110]
0x180004890  test    rcx, rcx
0x180004893  jz      short loc_1800048A2
0x180004895  mov     rdx, [rcx]
0x180004898  mov     rax, [rdx+10h]
0x18000489c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048a1  nop
0x1800048a2  mov     rax, rbx
0x1800048a5  mov     rcx, [rbp+60h+var_40]
0x1800048a9  xor     rcx, rsp; StackCookie
0x1800048ac  call    __security_check_cookie
0x1800048b1  mov     rbx, [rsp+160h+arg_18]
0x1800048b9  add     rsp, 130h
0x1800048c0  pop     r15
0x1800048c2  pop     r14
0x1800048c4  pop     r13
0x1800048c6  pop     r12
0x1800048c8  pop     rdi
0x1800048c9  pop     rsi
0x1800048ca  pop     rbp
0x1800048cb  retn
0x1800048cc  mov     rdx, [rsp+160h+var_108]
0x1800048d1  mov     [rsp+160h+var_108], r15
0x1800048d6  mov     rcx, rbx
0x1800048d9  call    ?attach@?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAUICloudStore@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>::attach(Windows::Internal::Storage::Cloud::ICloudStore *)
0x1800048de  jmp     loc_1800045EB
0x1800048e3  mov     rcx, [rbp+68h]
0x1800048e7  xor     al, 1
0x1800048e9  jnz     short loc_180004919
0x1800048eb  or      r13d, 2
0x1800048ef  jmp     loc_1800046C9
0x1800048f4  mov     rax, [rcx]
0x1800048f7  mov     rax, [rax+10h]
0x1800048fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004900  jmp     loc_180004634
0x180004905  xor     r9d, r9d; lpArguments
0x180004908  xor     r8d, r8d; nNumberOfArguments
0x18000490b  mov     edx, 1; dwExceptionFlags
0x180004910  mov     ecx, eax; dwExceptionCode
0x180004912  call    cs:__imp_RaiseException
0x180004918  nop
0x180004919  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180004920  mov     edx, 70Dh; void *
0x180004925  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000492b  or      r13d, 4
0x18000492f  jmp     loc_1800046D3
0x180004934  or      r13d, 8
0x180004938  jmp     loc_1800046DD
0x18000493d  xor     r9d, r9d; lpArguments
0x180004940  xor     r8d, r8d; nNumberOfArguments
0x180004943  mov     edx, 1; dwExceptionFlags
0x180004948  mov     ecx, eax; dwExceptionCode
0x18000494a  call    cs:__imp_RaiseException
0x180004950  nop
0x180004951  xor     r9d, r9d; lpArguments
0x180004954  xor     r8d, r8d; nNumberOfArguments
0x180004957  mov     edx, 1; dwExceptionFlags
0x18000495c  mov     ecx, eax; dwExceptionCode
0x18000495e  call    cs:__imp_RaiseException
0x180004964  nop
0x180004965  xor     r9d, r9d; lpArguments
0x180004968  xor     r8d, r8d; nNumberOfArguments
0x18000496b  mov     edx, 1; dwExceptionFlags
0x180004970  mov     ecx, eax; dwExceptionCode
0x180004972  call    cs:__imp_RaiseException
0x180004978  nop
0x180004979  mov     r8, [rax]
0x18000497c  jmp     loc_180004813
0x180004981  mov     r9d, eax; char *
0x180004984  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18000498b  mov     edx, 588h; void *
0x180004990  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180004996  lea     rdx, ds:2[rdx*2]
0x18000499e  mov     rcx, [rbp+60h+var_60]
  ... truncated ...
```
