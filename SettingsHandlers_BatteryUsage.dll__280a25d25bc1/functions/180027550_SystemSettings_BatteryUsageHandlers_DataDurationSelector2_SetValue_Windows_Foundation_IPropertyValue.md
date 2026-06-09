# SystemSettings::BatteryUsageHandlers::DataDurationSelector2::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x180027550`
- end: `0x180027659`
- name: `?SetValue@DataDurationSelector2@BatteryUsageHandlers@SystemSettings@@MEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `265`
- prototype: `int(SystemSettings::BatteryUsageHandlers::DataDurationSelector2 *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a13c`
- `0x180027550`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x1800275f7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x1800275f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002757d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800275c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002762c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002763b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002757d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800275c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002762c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002763b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800275d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800275d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::BatteryUsageHandlers::DataDurationSelector2::SetValue(
        SystemSettings::BatteryUsageHandlers::DataDurationSelector2 *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  const WCHAR *StringRawBuffer; // rbp
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
              *((PCWSTR *)&SystemSettings::BatteryUsageHandlers::DataDurationSelector2::_sc_rgridpDurationValues + 2 * i),
              StringRawBuffer) )
      {
        *((_DWORD *)this + 76) = *((_DWORD *)&SystemSettings::BatteryUsageHandlers::DataDurationSelector2::_sc_rgridpDurationValues
                                 + 4 * i
                                 + 2);
        (*(void (__fastcall **)(SystemSettings::BatteryUsageHandlers::DataDurationSelector2 *, SystemSettings::BatteryUsageHandlers::DataDurationSelector2 *))(*(_QWORD *)this + 192LL))(
          this,
          this);
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
      (void *)0x7C,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\datadurationselector2.cpp",
      (const char *)(unsigned int)v5,
      v10);
    WindowsDeleteString(string);
    return v6;
  }
}

```

## disassembly

```asm
0x180027550  mov     [rsp+arg_0], rbx
0x180027555  mov     [rsp+arg_10], rbp
0x18002755a  push    rsi
0x18002755b  push    rdi
0x18002755c  push    r14; int
0x18002755e  sub     rsp, 20h
0x180027562  mov     rdi, rdx
0x180027565  mov     rsi, rcx
0x180027568  mov     [rsp+38h+string], 0
0x180027571  mov     rax, [rdx]
0x180027574  mov     rbx, [rax+98h]
0x18002757b  xor     ecx, ecx; string
0x18002757d  call    cs:__imp_WindowsDeleteString
0x180027583  mov     [rsp+38h+string], 0
0x18002758c  lea     rdx, [rsp+38h+string]
0x180027591  mov     rcx, rdi
0x180027594  mov     rax, rbx
0x180027597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002759c  mov     ebx, eax
0x18002759e  test    eax, eax
0x1800275a0  jns     short loc_1800275CB
0x1800275a2  mov     rcx, [rsp+38h]; this
0x1800275a7  mov     r9d, eax; char *
0x1800275aa  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800275b1  mov     edx, 7Ch ; '|'; void *
0x1800275b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800275bb  nop
0x1800275bc  mov     rcx, [rsp+38h+string]; string
0x1800275c1  call    cs:__imp_WindowsDeleteString
0x1800275c7  mov     eax, ebx
0x1800275c9  jmp     short loc_180027646
0x1800275cb  xor     edx, edx; length
0x1800275cd  mov     rcx, [rsp+38h+string]; string
0x1800275d2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800275d8  mov     rbp, rax
0x1800275db  xor     ebx, ebx
0x1800275dd  lea     r14, ?_sc_rgridpDurationValues@DataDurationSelector2@BatteryUsageHandlers@SystemSettings@@0QBUDURATION_VALUE_PAIR@123@B; SystemSettings::BatteryUsageHandlers::DataDurationSelector2::DURATION_VALUE_PAIR const near * const SystemSettings::BatteryUsageHandlers::DataDurationSelector2::_sc_rgridpDurationValues
0x1800275e4  cmp     rbx, 2
0x1800275e8  jnb     short loc_180027636
0x1800275ea  mov     rdi, rbx
0x1800275ed  add     rdi, rdi
0x1800275f0  mov     rdx, rbp; psz2
0x1800275f3  mov     rcx, [r14+rdi*8]; psz1
0x1800275f7  call    cs:__imp_StrCmpLogicalW
0x1800275fd  test    eax, eax
0x1800275ff  jz      short loc_180027606
0x180027601  inc     rbx
0x180027604  jmp     short loc_1800275E4
0x180027606  mov     eax, [r14+rdi*8+8]
0x18002760b  mov     [rsi+130h], eax
0x180027611  mov     rax, [rsi]
0x180027614  mov     rdx, rsi
0x180027617  mov     rcx, rsi
0x18002761a  mov     rax, [rax+0C0h]
0x180027621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027626  nop
0x180027627  mov     rcx, [rsp+38h+string]; string
0x18002762c  call    cs:__imp_WindowsDeleteString
0x180027632  xor     eax, eax
0x180027634  jmp     short loc_180027646
0x180027636  mov     rcx, [rsp+38h+string]; string
0x18002763b  call    cs:__imp_WindowsDeleteString
0x180027641  mov     eax, 80004005h
0x180027646  mov     rbx, [rsp+38h+arg_0]
0x18002764b  mov     rbp, [rsp+38h+arg_10]
0x180027650  add     rsp, 20h
0x180027654  pop     r14
0x180027656  pop     rdi
0x180027657  pop     rsi
0x180027658  retn
```
