# SystemSettings::BatteryUsageHandlers::UsageDataSingleton::SetAppSearchString(HSTRING__ *)

- ea: `0x18004640c`
- end: `0x180046571`
- name: `?SetAppSearchString@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@@Z`
- size: `357`
- prototype: `int(SystemSettings::BatteryUsageHandlers::UsageDataSingleton *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180037460`

## callees

- `0x1800028d0`
- `0x18000e8e8`
- `0x1800234f0`
- `0x1800248d4`
- `0x18002c520`
- `0x18002e2b0`
- `0x18004640c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringStart` at `0x18004648d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringStart` at `0x18004648d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046452`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800464ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004653b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004654d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046452`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800464ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004653b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004654d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x1800464e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x1800464e8`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton::SetAppSearchString(
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
                         this[41],
                         v5) )
    {
      v10 = string;
      InitResult = Microsoft::WRL::Wrappers::HString::Set(this + 41, &v10);
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
0x18004640c  mov     [rsp-18h+arg_10], rbx
0x180046411  push    rbp
0x180046412  push    rsi
0x180046413  push    rdi
0x180046414  mov     rbp, rsp
0x180046417  sub     rsp, 70h
0x18004641b  mov     rax, cs:__security_cookie
0x180046422  xor     rax, rsp
0x180046425  mov     [rbp+var_10], rax
0x180046429  mov     rsi, rdx
0x18004642c  mov     rdi, rcx
0x18004642f  mov     [rbp+string], 0
0x180046437  mov     [rbp+newString], 0
0x18004643f  call    ?GetInitResult@?$CSingletonHelper@W4BatteryGraphNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAJXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::GetInitResult(void)
0x180046444  mov     ebx, eax
0x180046446  test    eax, eax
0x180046448  js      loc_180046537
0x18004644e  mov     rcx, [rbp+string]; string
0x180046452  call    cs:__imp_WindowsDeleteString
0x180046458  mov     [rbp+string], 0
0x180046460  mov     [rbp+trimString], 0
0x180046468  mov     r9d, 1; unsigned int
0x18004646e  lea     r8d, [r9+1]; unsigned int
0x180046472  lea     rdx, asc_180069498; " "
0x180046479  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18004647d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180046482  lea     r8, [rbp+string]; newString
0x180046486  mov     rdx, [rbp+trimString]; trimString
0x18004648a  mov     rcx, rsi; string
0x18004648d  call    cs:__imp_WindowsTrimStringStart
0x180046493  mov     rax, [rbp+string]
0x180046497  mov     [rbp+var_40], rax
0x18004649b  lea     rdx, [rbp+var_40]; HSTRING *
0x18004649f  lea     rcx, [rbp+newString]; newString
0x1800464a3  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800464a8  mov     rcx, [rbp+string]; string
0x1800464ac  call    cs:__imp_WindowsDeleteString
0x1800464b2  mov     [rbp+string], 0
0x1800464ba  mov     [rbp+trimString], 0
0x1800464c2  mov     r9d, 1; unsigned int
0x1800464c8  lea     r8d, [r9+1]; unsigned int
0x1800464cc  lea     rdx, asc_180069498; " "
0x1800464d3  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800464d7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800464dc  lea     r8, [rbp+string]; newString
0x1800464e0  mov     rdx, [rbp+trimString]; trimString
0x1800464e4  mov     rcx, [rbp+newString]; string
0x1800464e8  call    cs:__imp_WindowsTrimStringEnd
0x1800464ee  lea     rsi, [rdi+148h]
0x1800464f5  mov     rdx, [rsi]; HSTRING
0x1800464f8  mov     rcx, [rbp+string]; this
0x1800464fc  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180046501  test    eax, eax
0x180046503  jz      short loc_180046537
0x180046505  mov     rax, [rbp+string]
0x180046509  mov     [rbp+var_40], rax
0x18004650d  lea     rdx, [rbp+var_40]; HSTRING *
0x180046511  mov     rcx, rsi; newString
0x180046514  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180046519  mov     ebx, eax
0x18004651b  mov     dword ptr [rbp+var_40], 0
0x180046522  lea     rax, [rbp+var_40]
0x180046526  mov     [rbp+var_38], rax
0x18004652a  lea     rdx, [rbp+var_38]
0x18004652e  mov     rcx, rdi
0x180046531  call    ??$_Notify@V_lambda_003ea7db14c545d4659f1dda1f06794d_@@@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_003ea7db14c545d4659f1dda1f06794d_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::_Notify<_lambda_003ea7db14c545d4659f1dda1f06794d_>(_lambda_003ea7db14c545d4659f1dda1f06794d_ const &)
0x180046536  nop
0x180046537  mov     rcx, [rbp+newString]; string
0x18004653b  call    cs:__imp_WindowsDeleteString
0x180046541  mov     [rbp+newString], 0
0x180046549  mov     rcx, [rbp+string]; string
0x18004654d  call    cs:__imp_WindowsDeleteString
0x180046553  mov     eax, ebx
0x180046555  mov     rcx, [rbp+var_10]
0x180046559  xor     rcx, rsp; StackCookie
0x18004655c  call    __security_check_cookie
0x180046561  mov     rbx, [rsp+70h+arg_10]
0x180046569  add     rsp, 70h
0x18004656d  pop     rdi
0x18004656e  pop     rsi
0x18004656f  pop     rbp
0x180046570  retn
```
