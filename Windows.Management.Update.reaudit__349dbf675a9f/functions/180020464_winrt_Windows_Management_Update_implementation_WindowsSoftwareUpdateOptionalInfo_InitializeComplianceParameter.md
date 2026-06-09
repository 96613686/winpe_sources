# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo::InitializeComplianceParameters(winrt::Windows::Foundation::IReference<int> const &,winrt::Windows::Foundation::IReference<int> const &)

- ea: `0x180020464`
- end: `0x1800205c6`
- name: `?InitializeComplianceParameters@WindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@AEAAXAEBU?$IReference@H@Foundation@56@0@Z`
- size: `354`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013ab0`
- `0x18001f628`

## callees

- `0x1800035f0`
- `0x180011ffc`
- `0x180015ac0`
- `0x180017c3c`
- `0x180018f10`
- `0x18001d3c8`
- `0x180020464`
- `0x18002c010`

## string_xrefs

- `0x18002054c`: `complianceDeadlineInDays must be between 0 and 30`
- `0x18002058e`: `complianceGracePeriodInDays must be between 0 and 7`

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
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v13[24]; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v14[32]; // [rsp+50h] [rbp-28h] BYREF

  if ( *a2 )
  {
    if ( (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(a2) < 0
      || (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(a2) > 30 )
    {
      v10 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v13);
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
      v11 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v13);
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
0x180020464  mov     [rsp+arg_0], rbx
0x180020469  mov     [rsp+arg_8], rbp
0x18002046e  mov     [rsp+arg_10], rsi
0x180020473  push    rdi
0x180020474  sub     rsp, 70h
0x180020478  cmp     qword ptr [rdx], 0
0x18002047c  mov     rdi, r8
0x18002047f  mov     rbx, rdx
0x180020482  mov     rbp, rcx
0x180020485  jz      short loc_1800204D6
0x180020487  mov     rcx, rdx
0x18002048a  call    ?Major@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion@UIWindowsSoftwareUpdateVersion@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(void)
0x18002048f  test    eax, eax
0x180020491  js      loc_180020542
0x180020497  mov     rcx, rbx
0x18002049a  call    ?Major@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion@UIWindowsSoftwareUpdateVersion@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(void)
0x18002049f  cmp     eax, 1Eh
0x1800204a2  jg      loc_180020542
0x1800204a8  lea     rsi, [rbp+20h]
0x1800204ac  cmp     rsi, rbx
0x1800204af  jz      short loc_1800204D6
0x1800204b1  cmp     qword ptr [rsi], 0
0x1800204b5  jz      short loc_1800204BF
0x1800204b7  mov     rcx, rsi
0x1800204ba  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800204bf  mov     rcx, [rbx]
0x1800204c2  mov     [rsi], rcx
0x1800204c5  test    rcx, rcx
0x1800204c8  jz      short loc_1800204D6
0x1800204ca  mov     rax, [rcx]
0x1800204cd  mov     rax, [rax+8]
0x1800204d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204d6  cmp     qword ptr [rdi], 0
0x1800204da  jz      short loc_18002052B
0x1800204dc  mov     rcx, rdi
0x1800204df  call    ?Major@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion@UIWindowsSoftwareUpdateVersion@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(void)
0x1800204e4  test    eax, eax
0x1800204e6  js      loc_180020584
0x1800204ec  mov     rcx, rdi
0x1800204ef  call    ?Major@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion@UIWindowsSoftwareUpdateVersion@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(void)
0x1800204f4  cmp     eax, 7
0x1800204f7  jg      loc_180020584
0x1800204fd  lea     rbx, [rbp+28h]
0x180020501  cmp     rbx, rdi
0x180020504  jz      short loc_18002052B
0x180020506  cmp     qword ptr [rbx], 0
0x18002050a  jz      short loc_180020514
0x18002050c  mov     rcx, rbx
0x18002050f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020514  mov     rcx, [rdi]
0x180020517  mov     [rbx], rcx
0x18002051a  test    rcx, rcx
0x18002051d  jz      short loc_18002052B
0x18002051f  mov     rax, [rcx]
0x180020522  mov     rax, [rax+8]
0x180020526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002052b  lea     r11, [rsp+78h+var_8]
0x180020530  mov     rbx, [r11+10h]
0x180020534  mov     rbp, [r11+18h]
0x180020538  mov     rsi, [r11+20h]
0x18002053c  mov     rsp, r11
0x18002053f  pop     rdi
0x180020540  retn
0x180020542  lea     rcx, [rsp+78h+var_40]
0x180020547  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002054c  lea     rdx, aCompliancedead_2; "complianceDeadlineInDays must be betwee"...
0x180020553  mov     rbx, rax
0x180020556  lea     rcx, [rsp+78h+var_28]; this
0x18002055b  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180020560  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x180020563  lea     rdx, [rsp+78h+var_28]; struct winrt::param::hstring *
0x180020568  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18002056d  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180020572  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180020579  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18002057e  call    _CxxThrowException_0
0x180020584  lea     rcx, [rsp+78h+var_40]
0x180020589  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002058e  lea     rdx, aCompliancegrac; "complianceGracePeriodInDays must be bet"...
0x180020595  mov     rbx, rax
0x180020598  lea     rcx, [rsp+78h+var_28]; this
0x18002059d  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800205a2  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x1800205a5  lea     rdx, [rsp+78h+var_28]; struct winrt::param::hstring *
0x1800205aa  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800205af  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800205b4  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1800205bb  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800205c0  call    _CxxThrowException_0
```
