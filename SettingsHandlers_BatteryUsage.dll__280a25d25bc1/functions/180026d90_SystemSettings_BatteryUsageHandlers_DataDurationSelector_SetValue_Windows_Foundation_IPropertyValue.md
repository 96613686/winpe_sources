# SystemSettings::BatteryUsageHandlers::DataDurationSelector::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x180026d90`
- end: `0x180026ea7`
- name: `?SetValue@DataDurationSelector@BatteryUsageHandlers@SystemSettings@@MEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `279`
- prototype: `int(SystemSettings::BatteryUsageHandlers::DataDurationSelector *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a13c`
- `0x180026508`
- `0x180026d90`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x180026e3b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x180026e3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026dbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026e01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026e7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026dbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026e01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026e7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026e15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026e15`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::BatteryUsageHandlers::DataDurationSelector::SetValue(
        SystemSettings::BatteryUsageHandlers::DataDurationSelector *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  const WCHAR *StringRawBuffer; // rsi
  unsigned __int64 i; // rbx
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING string; // [rsp+48h] [rbp+10h] BYREF

  string = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)a2 + 152LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a2, &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    for ( i = 0; i < 2; ++i )
    {
      if ( !StrCmpLogicalW(
              *((PCWSTR *)&SystemSettings::BatteryUsageHandlers::DataDurationSelector::_sc_rgridpDurationValues + 2 * i),
              StringRawBuffer) )
      {
        *((_DWORD *)this + 76) = *((_DWORD *)&SystemSettings::BatteryUsageHandlers::DataDurationSelector::_sc_rgridpDurationValues
                                 + 4 * i
                                 + 2);
        (*(void (__fastcall **)(SystemSettings::BatteryUsageHandlers::DataDurationSelector *, SystemSettings::BatteryUsageHandlers::DataDurationSelector *))(*(_QWORD *)this + 192LL))(
          this,
          this);
        UsageGraphTelemetry::AppUsageDurationComboBoxSelectedValue<unsigned long &>((int *)this + 76);
        WindowsDeleteString(string);
        return 0;
      }
    }
    WindowsDeleteString(string);
    return 2147500037LL;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\datadurationselector.cpp",
      (const char *)(unsigned int)v5,
      v10);
    WindowsDeleteString(string);
    return v6;
  }
}

```

## disassembly

```asm
0x180026d90  mov     [rsp+arg_0], rbx
0x180026d95  mov     [rsp+arg_10], rbp
0x180026d9a  push    rsi
0x180026d9b  push    rdi
0x180026d9c  push    r14; int
0x180026d9e  sub     rsp, 20h
0x180026da2  mov     rdi, rdx
0x180026da5  mov     r14, rcx
0x180026da8  mov     [rsp+38h+string], 0
0x180026db1  mov     rax, [rdx]
0x180026db4  mov     rbx, [rax+98h]
0x180026dbb  xor     ecx, ecx; string
0x180026dbd  call    cs:__imp_WindowsDeleteString
0x180026dc3  mov     [rsp+38h+string], 0
0x180026dcc  lea     rdx, [rsp+38h+string]
0x180026dd1  mov     rcx, rdi
0x180026dd4  mov     rax, rbx
0x180026dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ddc  mov     ebx, eax
0x180026dde  test    eax, eax
0x180026de0  jns     short loc_180026E0E
0x180026de2  mov     rcx, [rsp+38h]; this
0x180026de7  mov     r9d, eax; char *
0x180026dea  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\coresettinghandlers"...
0x180026df1  mov     edx, 7Dh ; '}'; void *
0x180026df6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026dfb  nop
0x180026dfc  mov     rcx, [rsp+38h+string]; string
0x180026e01  call    cs:__imp_WindowsDeleteString
0x180026e07  mov     eax, ebx
0x180026e09  jmp     loc_180026E94
0x180026e0e  xor     edx, edx; length
0x180026e10  mov     rcx, [rsp+38h+string]; string
0x180026e15  call    cs:__imp_WindowsGetStringRawBuffer
0x180026e1b  mov     rsi, rax
0x180026e1e  xor     ebx, ebx
0x180026e20  lea     rbp, ?_sc_rgridpDurationValues@DataDurationSelector@BatteryUsageHandlers@SystemSettings@@0QBUDURATION_VALUE_PAIR@123@B; SystemSettings::BatteryUsageHandlers::DataDurationSelector::DURATION_VALUE_PAIR const near * const SystemSettings::BatteryUsageHandlers::DataDurationSelector::_sc_rgridpDurationValues
0x180026e27  cmp     rbx, 2
0x180026e2b  jnb     short loc_180026E84
0x180026e2d  mov     rdi, rbx
0x180026e30  add     rdi, rdi
0x180026e33  mov     rdx, rsi; psz2
0x180026e36  mov     rcx, [rbp+rdi*8+0]; psz1
0x180026e3b  call    cs:__imp_StrCmpLogicalW
0x180026e41  test    eax, eax
0x180026e43  jz      short loc_180026E4A
0x180026e45  inc     rbx
0x180026e48  jmp     short loc_180026E27
0x180026e4a  lea     rbx, [r14+130h]
0x180026e51  mov     eax, [rbp+rdi*8+8]
0x180026e55  mov     [rbx], eax
0x180026e57  mov     rax, [r14]
0x180026e5a  mov     rdx, r14
0x180026e5d  mov     rcx, r14
0x180026e60  mov     rax, [rax+0C0h]
0x180026e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e6c  mov     rcx, rbx
0x180026e6f  call    ??$AppUsageDurationComboBoxSelectedValue@AEAK@UsageGraphTelemetry@@SAXAEAK@Z; UsageGraphTelemetry::AppUsageDurationComboBoxSelectedValue<ulong &>(ulong &)
0x180026e74  nop
0x180026e75  mov     rcx, [rsp+38h+string]; string
0x180026e7a  call    cs:__imp_WindowsDeleteString
0x180026e80  xor     eax, eax
0x180026e82  jmp     short loc_180026E94
0x180026e84  mov     rcx, [rsp+38h+string]; string
0x180026e89  call    cs:__imp_WindowsDeleteString
0x180026e8f  mov     eax, 80004005h
0x180026e94  mov     rbx, [rsp+38h+arg_0]
0x180026e99  mov     rbp, [rsp+38h+arg_10]
0x180026e9e  add     rsp, 20h
0x180026ea2  pop     r14
0x180026ea4  pop     rdi
0x180026ea5  pop     rsi
0x180026ea6  retn
```
