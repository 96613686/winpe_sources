# AggregatorsCommon::Utilities::ValidateText(winrt::hstring const &,uint)

- ea: `0x180021aa8`
- end: `0x180021bb3`
- name: `?ValidateText@Utilities@AggregatorsCommon@@YAXAEBUhstring@winrt@@I@Z`
- size: `267`
- prototype: `void __fastcall(AggregatorsCommon::Utilities *__hidden this, const struct winrt::hstring *, unsigned int)`
- caller_count: `9`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800142e8`
- `0x180014780`
- `0x180014dac`
- `0x18001554c`
- `0x180017e74`
- `0x180018080`
- `0x180018240`
- `0x180018470`
- `0x1800218dc`

## callees

- `0x180002250`
- `0x180003516`
- `0x180007e84`
- `0x180020548`
- `0x180020a24`
- `0x180020a78`
- `0x180021aa8`
- `0x180023594`

## string_xrefs

- `0x180021b25`: `onecoreuap\base\appmodel\aggregateddataplatform\service\dataaggregators\aggregatorscommon\utilities.cpp`
- `0x180021b6e`: `onecoreuap\base\appmodel\aggregateddataplatform\service\dataaggregators\aggregatorscommon\utilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AggregatorsCommon::Utilities::ValidateText(
        AggregatorsCommon::Utilities *this,
        const struct winrt::hstring *a2)
{
  const wchar_t *v2; // [rsp+40h] [rbp-29h] BYREF
  const char *v3; // [rsp+48h] [rbp-21h]
  __int64 v4; // [rsp+50h] [rbp-19h]
  _BYTE pExceptionObject[24]; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v6[32]; // [rsp+78h] [rbp+Fh] BYREF
  _BYTE Src[32]; // [rsp+98h] [rbp+2Fh] BYREF

  if ( !*(_QWORD *)this )
  {
    LODWORD(v2) = 28;
    v3 = "onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\dataaggregators\\aggregatorscommon\\utilities.cpp";
    v4 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)Src, L"Empty String Passed");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)Src,
      (const struct winrt::impl::slim_source_location *)&v2);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  if ( *(_DWORD *)(*(_QWORD *)this + 4LL) > (unsigned int)a2 )
  {
    winrt::hstring::size(this);
    v2 = L"String size {} is more than the maximum {}.";
    std::format<unsigned int,unsigned int &>(Src);
    LODWORD(v2) = 33;
    v3 = "onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\dataaggregators\\aggregatorscommon\\utilities.cpp";
    v4 = 0;
    winrt::param::hstring::hstring(v6, Src);
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v6,
      (const struct winrt::impl::slim_source_location *)&v2);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180021aa8  push    rbp
0x180021aaa  lea     rbp, [rsp-57h]
0x180021aaf  sub     rsp, 0C0h
0x180021ab6  mov     rax, cs:__security_cookie
0x180021abd  xor     rax, rsp
0x180021ac0  mov     [rbp+57h+var_8], rax
0x180021ac4  mov     [rbp+57h+var_A0], edx
0x180021ac7  mov     rax, [rcx]
0x180021aca  test    rax, rax
0x180021acd  jz      loc_180021B67
0x180021ad3  cmp     [rax+4], edx
0x180021ad6  ja      short loc_180021AED
0x180021ad8  mov     rcx, [rbp+57h+var_8]
0x180021adc  xor     rcx, rsp; StackCookie
0x180021adf  call    __security_check_cookie
0x180021ae4  add     rsp, 0C0h
0x180021aeb  pop     rbp
0x180021aec  retn
0x180021aed  call    ?size@hstring@winrt@@QEBAIXZ; winrt::hstring::size(void)
0x180021af2  mov     [rbp+57h+var_90], eax
0x180021af5  lea     rax, aStringSizeIsMo; "String size {} is more than the maximum"...
0x180021afc  mov     [rbp+57h+var_80], rax
0x180021b00  mov     [rbp+57h+var_78], 2Bh ; '+'
0x180021b08  lea     r9, [rbp+57h+var_A0]
0x180021b0c  lea     r8, [rbp+57h+var_90]
0x180021b10  lea     rdx, [rbp+57h+var_80]
0x180021b14  lea     rcx, [rbp+57h+Src]; Src
0x180021b18  call    ??$format@IAEAI@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@U?$basic_format_string@_WIAEAI@0@$$QEAIAEAI@Z; std::format<uint,uint &>(std::basic_format_string<wchar_t,uint,uint &>,uint &&,uint &)
0x180021b1d  nop
0x180021b1e  mov     dword ptr [rbp+57h+var_80], 21h ; '!'
0x180021b25  lea     rax, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180021b2c  mov     [rbp+57h+var_78], rax
0x180021b30  mov     [rbp+57h+var_70], 0
0x180021b38  lea     rdx, [rbp+57h+Src]
0x180021b3c  lea     rcx, [rbp+57h+var_48]
0x180021b40  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x180021b45  lea     r8, [rbp+57h+var_80]; struct winrt::impl::slim_source_location *
0x180021b49  lea     rdx, [rbp+57h+var_48]; struct winrt::param::hstring *
0x180021b4d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180021b51  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180021b56  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180021b5d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180021b61  call    _CxxThrowException_0
0x180021b67  mov     dword ptr [rbp+57h+var_80], 1Ch
0x180021b6e  lea     rax, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180021b75  mov     [rbp+57h+var_78], rax
0x180021b79  mov     [rbp+57h+var_70], 0
0x180021b81  lea     rdx, aEmptyStringPas; "Empty String Passed"
0x180021b88  lea     rcx, [rbp+57h+Src]; this
0x180021b8c  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180021b91  lea     r8, [rbp+57h+var_80]; struct winrt::impl::slim_source_location *
0x180021b95  lea     rdx, [rbp+57h+Src]; struct winrt::param::hstring *
0x180021b99  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180021b9d  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180021ba2  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180021ba9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180021bad  call    _CxxThrowException_0
```
