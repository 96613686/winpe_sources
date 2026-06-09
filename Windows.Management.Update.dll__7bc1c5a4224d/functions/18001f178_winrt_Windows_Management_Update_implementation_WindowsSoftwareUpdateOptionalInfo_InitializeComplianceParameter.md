# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::InitializeComplianceParameters(winrt::Windows::Foundation::IReference<int> const &,winrt::Windows::Foundation::IReference<int> const &)

- ea: `0x18001f178`
- end: `0x18001f2bd`
- name: `?InitializeComplianceParameters@WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@AEAAXAEBU?$IReference@H@Foundation@56@0@Z`
- size: `325`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012ed0`
- `0x18001e414`

## callees

- `0x18000340c`
- `0x180011464`
- `0x180014eb4`
- `0x180016fe4`
- `0x180018238`
- `0x18001c174`
- `0x18001f178`
- `0x18002a010`

## string_xrefs

- `0x18001f243`: `complianceDeadlineInDays must be between 0 and 30`
- `0x18001f285`: `complianceGracePeriodInDays must be between 0 and 7`

## pseudocode

```c
void __fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::InitializeComplianceParameters(
        __int64 a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 *v6; // rsi
  __int64 v7; // rcx
  __int64 *v8; // rbx
  __int64 v9; // rcx
  const struct winrt::impl::slim_source_location *v10; // rbx
  const struct winrt::impl::slim_source_location *v11; // rbx
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v13[24]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v14[72]; // [rsp+50h] [rbp-48h] BYREF

  if ( *a2 )
  {
    if ( (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(a2) < 0
      || (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(a2) > 30 )
    {
      v10 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v13);
      winrt::param::hstring::hstring((winrt::param::hstring *)v14, L"complianceDeadlineInDays must be between 0 and 30");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)pExceptionObject,
        (const struct winrt::param::hstring *)v14,
        v10);
      throw (winrt::hresult_invalid_argument *)pExceptionObject;
    }
    v6 = (__int64 *)(a1 + 32);
    if ( (__int64 *)(a1 + 32) != a2 )
    {
      if ( *v6 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 32);
      v7 = *a2;
      *v6 = *a2;
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  if ( *a3 )
  {
    if ( (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(a3) < 0
      || (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(a3) > 7 )
    {
      v11 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v13);
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)v14,
        L"complianceGracePeriodInDays must be between 0 and 7");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)pExceptionObject,
        (const struct winrt::param::hstring *)v14,
        v11);
      throw (winrt::hresult_invalid_argument *)pExceptionObject;
    }
    v8 = (__int64 *)(a1 + 40);
    if ( (__int64 *)(a1 + 40) != a3 )
    {
      if ( *v8 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 40);
      v9 = *a3;
      *v8 = *a3;
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
}

```

## disassembly

```asm
0x18001f178  push    rbx
0x18001f17a  push    rbp
0x18001f17b  push    rsi
0x18001f17c  push    rdi
0x18001f17d  sub     rsp, 78h
0x18001f181  cmp     qword ptr [rdx], 0
0x18001f185  mov     rdi, r8
0x18001f188  mov     rbx, rdx
0x18001f18b  mov     rbp, rcx
0x18001f18e  jz      short loc_18001F1DF
0x18001f190  mov     rcx, rdx
0x18001f193  call    ?Major@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion@UIWindowsSoftwareUpdateVersion@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(void)
0x18001f198  test    eax, eax
0x18001f19a  js      loc_18001F239
0x18001f1a0  mov     rcx, rbx
0x18001f1a3  call    ?Major@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion@UIWindowsSoftwareUpdateVersion@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(void)
0x18001f1a8  cmp     eax, 1Eh
0x18001f1ab  jg      loc_18001F239
0x18001f1b1  lea     rsi, [rbp+20h]
0x18001f1b5  cmp     rsi, rbx
0x18001f1b8  jz      short loc_18001F1DF
0x18001f1ba  cmp     qword ptr [rsi], 0
0x18001f1be  jz      short loc_18001F1C8
0x18001f1c0  mov     rcx, rsi
0x18001f1c3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f1c8  mov     rcx, [rbx]
0x18001f1cb  mov     [rsi], rcx
0x18001f1ce  test    rcx, rcx
0x18001f1d1  jz      short loc_18001F1DF
0x18001f1d3  mov     rax, [rcx]
0x18001f1d6  mov     rax, [rax+8]
0x18001f1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1df  cmp     qword ptr [rdi], 0
0x18001f1e3  jz      short loc_18001F230
0x18001f1e5  mov     rcx, rdi
0x18001f1e8  call    ?Major@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion@UIWindowsSoftwareUpdateVersion@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(void)
0x18001f1ed  test    eax, eax
0x18001f1ef  js      loc_18001F27B
0x18001f1f5  mov     rcx, rdi
0x18001f1f8  call    ?Major@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion@UIWindowsSoftwareUpdateVersion@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(void)
0x18001f1fd  cmp     eax, 7
0x18001f200  jg      short loc_18001F27B
0x18001f202  lea     rbx, [rbp+28h]
0x18001f206  cmp     rbx, rdi
0x18001f209  jz      short loc_18001F230
0x18001f20b  cmp     qword ptr [rbx], 0
0x18001f20f  jz      short loc_18001F219
0x18001f211  mov     rcx, rbx
0x18001f214  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f219  mov     rcx, [rdi]
0x18001f21c  mov     [rbx], rcx
0x18001f21f  test    rcx, rcx
0x18001f222  jz      short loc_18001F230
0x18001f224  mov     rax, [rcx]
0x18001f227  mov     rax, [rax+8]
0x18001f22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f230  add     rsp, 78h
0x18001f234  pop     rdi
0x18001f235  pop     rsi
0x18001f236  pop     rbp
0x18001f237  pop     rbx
0x18001f238  retn
0x18001f239  lea     rcx, [rsp+98h+var_60]
0x18001f23e  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001f243  lea     rdx, aCompliancedead_2; "complianceDeadlineInDays must be betwee"...
0x18001f24a  mov     rbx, rax
0x18001f24d  lea     rcx, [rsp+98h+var_48]; this
0x18001f252  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001f257  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x18001f25a  lea     rdx, [rsp+98h+var_48]; struct winrt::param::hstring *
0x18001f25f  lea     rcx, [rsp+98h+pExceptionObject]; this
0x18001f264  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18001f269  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18001f270  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18001f275  call    _CxxThrowException_0
0x18001f27b  lea     rcx, [rsp+98h+var_60]
0x18001f280  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001f285  lea     rdx, aCompliancegrac; "complianceGracePeriodInDays must be bet"...
0x18001f28c  mov     rbx, rax
0x18001f28f  lea     rcx, [rsp+98h+var_48]; this
0x18001f294  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001f299  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x18001f29c  lea     rdx, [rsp+98h+var_48]; struct winrt::param::hstring *
0x18001f2a1  lea     rcx, [rsp+98h+pExceptionObject]; this
0x18001f2a6  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18001f2ab  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18001f2b2  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18001f2b7  call    _CxxThrowException_0
```
