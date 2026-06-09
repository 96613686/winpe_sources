# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::SetAppSearchString(HSTRING__ *)

- ea: `0x1800462a0`
- end: `0x180046405`
- name: `?SetAppSearchString@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@@Z`
- size: `357`
- prototype: `int(SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180037400`

## callees

- `0x1800028d0`
- `0x18000e8e8`
- `0x1800234f0`
- `0x1800248d4`
- `0x18002c520`
- `0x18002e2b0`
- `0x1800462a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringStart` at `0x180046321`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringStart` at `0x180046321`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800462e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046340`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800463cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800463e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800462e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046340`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800463cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800463e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x18004637c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x18004637c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::SetAppSearchString(
        HSTRING *this,
        HSTRING a2)
{
  int InitResult; // ebx
  HSTRING v5; // r8
  __int64 v6; // r8
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  HSTRING newString; // [rsp+28h] [rbp-48h] BYREF
  HSTRING v10; // [rsp+30h] [rbp-40h] BYREF
  HSTRING *v11; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING trimString; // [rsp+58h] [rbp-18h]

  string = 0;
  newString = 0;
  InitResult = SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::GetInitResult();
  if ( InitResult >= 0 )
  {
    WindowsDeleteString(string);
    string = 0;
    trimString = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L" ", 2u, 1u);
    WindowsTrimStringStart(a2, trimString, &string);
    v10 = string;
    Microsoft::WRL::Wrappers::HString::Set(&newString, &v10);
    WindowsDeleteString(string);
    string = 0;
    trimString = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L" ", 2u, 1u);
    WindowsTrimStringEnd(newString, trimString, &string);
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                         (Microsoft::WRL::Wrappers::Details *)string,
                         this[40],
                         v5) )
    {
      v10 = string;
      InitResult = Microsoft::WRL::Wrappers::HString::Set(this + 40, &v10);
      LODWORD(v10) = 0;
      v11 = &v10;
      SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::_Notify<_lambda_003ea7db14c545d4659f1dda1f06794d_>(
        (__int64)this,
        (unsigned int **)&v11,
        v6);
    }
  }
  WindowsDeleteString(newString);
  newString = 0;
  WindowsDeleteString(string);
  return (unsigned int)InitResult;
}

```

## disassembly

```asm
0x1800462a0  mov     [rsp-18h+arg_10], rbx
0x1800462a5  push    rbp
0x1800462a6  push    rsi
0x1800462a7  push    rdi
0x1800462a8  mov     rbp, rsp
0x1800462ab  sub     rsp, 70h
0x1800462af  mov     rax, cs:__security_cookie
0x1800462b6  xor     rax, rsp
0x1800462b9  mov     [rbp+var_10], rax
0x1800462bd  mov     rsi, rdx
0x1800462c0  mov     rdi, rcx
0x1800462c3  mov     [rbp+string], 0
0x1800462cb  mov     [rbp+newString], 0
0x1800462d3  call    ?GetInitResult@?$CSingletonHelper@W4BatteryGraphNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAJXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::GetInitResult(void)
0x1800462d8  mov     ebx, eax
0x1800462da  test    eax, eax
0x1800462dc  js      loc_1800463CB
0x1800462e2  mov     rcx, [rbp+string]; string
0x1800462e6  call    cs:__imp_WindowsDeleteString
0x1800462ec  mov     [rbp+string], 0
0x1800462f4  mov     [rbp+trimString], 0
0x1800462fc  mov     r9d, 1; unsigned int
0x180046302  lea     r8d, [r9+1]; unsigned int
0x180046306  lea     rdx, asc_180069498; " "
0x18004630d  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180046311  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180046316  lea     r8, [rbp+string]; newString
0x18004631a  mov     rdx, [rbp+trimString]; trimString
0x18004631e  mov     rcx, rsi; string
0x180046321  call    cs:__imp_WindowsTrimStringStart
0x180046327  mov     rax, [rbp+string]
0x18004632b  mov     [rbp+var_40], rax
0x18004632f  lea     rdx, [rbp+var_40]; HSTRING *
0x180046333  lea     rcx, [rbp+newString]; newString
0x180046337  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18004633c  mov     rcx, [rbp+string]; string
0x180046340  call    cs:__imp_WindowsDeleteString
0x180046346  mov     [rbp+string], 0
0x18004634e  mov     [rbp+trimString], 0
0x180046356  mov     r9d, 1; unsigned int
0x18004635c  lea     r8d, [r9+1]; unsigned int
0x180046360  lea     rdx, asc_180069498; " "
0x180046367  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18004636b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180046370  lea     r8, [rbp+string]; newString
0x180046374  mov     rdx, [rbp+trimString]; trimString
0x180046378  mov     rcx, [rbp+newString]; string
0x18004637c  call    cs:__imp_WindowsTrimStringEnd
0x180046382  lea     rsi, [rdi+140h]
0x180046389  mov     rdx, [rsi]; HSTRING
0x18004638c  mov     rcx, [rbp+string]; this
0x180046390  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180046395  test    eax, eax
0x180046397  jz      short loc_1800463CB
0x180046399  mov     rax, [rbp+string]
0x18004639d  mov     [rbp+var_40], rax
0x1800463a1  lea     rdx, [rbp+var_40]; HSTRING *
0x1800463a5  mov     rcx, rsi; newString
0x1800463a8  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800463ad  mov     ebx, eax
0x1800463af  mov     dword ptr [rbp+var_40], 0
0x1800463b6  lea     rax, [rbp+var_40]
0x1800463ba  mov     [rbp+var_38], rax
0x1800463be  lea     rdx, [rbp+var_38]
0x1800463c2  mov     rcx, rdi
0x1800463c5  call    ??$_Notify@V_lambda_003ea7db14c545d4659f1dda1f06794d_@@@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_003ea7db14c545d4659f1dda1f06794d_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::_Notify<_lambda_003ea7db14c545d4659f1dda1f06794d_>(_lambda_003ea7db14c545d4659f1dda1f06794d_ const &)
0x1800463ca  nop
0x1800463cb  mov     rcx, [rbp+newString]; string
0x1800463cf  call    cs:__imp_WindowsDeleteString
0x1800463d5  mov     [rbp+newString], 0
0x1800463dd  mov     rcx, [rbp+string]; string
0x1800463e1  call    cs:__imp_WindowsDeleteString
0x1800463e7  mov     eax, ebx
0x1800463e9  mov     rcx, [rbp+var_10]
0x1800463ed  xor     rcx, rsp; StackCookie
0x1800463f0  call    __security_check_cookie
0x1800463f5  mov     rbx, [rsp+70h+arg_10]
0x1800463fd  add     rsp, 70h
0x180046401  pop     rdi
0x180046402  pop     rsi
0x180046403  pop     rbp
0x180046404  retn
```
