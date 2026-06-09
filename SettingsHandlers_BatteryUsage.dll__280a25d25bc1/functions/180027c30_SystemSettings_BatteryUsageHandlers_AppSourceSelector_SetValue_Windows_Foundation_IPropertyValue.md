# SystemSettings::BatteryUsageHandlers::AppSourceSelector::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x180027c30`
- end: `0x180027d39`
- name: `?SetValue@AppSourceSelector@BatteryUsageHandlers@SystemSettings@@MEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `265`
- prototype: `int(SystemSettings::BatteryUsageHandlers::AppSourceSelector *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a13c`
- `0x180027c30`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x180027cd7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x180027cd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027c5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027ca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027c5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027ca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027cb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027cb2`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::AppSourceSelector::SetValue(
        SystemSettings::BatteryUsageHandlers::AppSourceSelector *this,
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
    for ( i = 0; i < 3; ++i )
    {
      if ( !StrCmpLogicalW(
              *((PCWSTR *)&SystemSettings::BatteryUsageHandlers::AppSourceSelector::_sc_rgridpSourceValues + 2 * i),
              StringRawBuffer) )
      {
        *((_DWORD *)this + 76) = *((_DWORD *)&SystemSettings::BatteryUsageHandlers::AppSourceSelector::_sc_rgridpSourceValues
                                 + 4 * i
                                 + 2);
        (*(void (__fastcall **)(SystemSettings::BatteryUsageHandlers::AppSourceSelector *, SystemSettings::BatteryUsageHandlers::AppSourceSelector *))(*(_QWORD *)this + 192LL))(
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
      (void *)0x83,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\appsourceselector.cpp",
      (const char *)(unsigned int)v5,
      v10);
    WindowsDeleteString(string);
    return v6;
  }
}

```

## disassembly

```asm
0x180027c30  mov     [rsp+arg_0], rbx
0x180027c35  mov     [rsp+arg_10], rbp
0x180027c3a  push    rsi
0x180027c3b  push    rdi
0x180027c3c  push    r14; int
0x180027c3e  sub     rsp, 20h
0x180027c42  mov     rdi, rdx
0x180027c45  mov     rsi, rcx
0x180027c48  mov     [rsp+38h+string], 0
0x180027c51  mov     rax, [rdx]
0x180027c54  mov     rbx, [rax+98h]
0x180027c5b  xor     ecx, ecx; string
0x180027c5d  call    cs:__imp_WindowsDeleteString
0x180027c63  mov     [rsp+38h+string], 0
0x180027c6c  lea     rdx, [rsp+38h+string]
0x180027c71  mov     rcx, rdi
0x180027c74  mov     rax, rbx
0x180027c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c7c  mov     ebx, eax
0x180027c7e  test    eax, eax
0x180027c80  jns     short loc_180027CAB
0x180027c82  mov     rcx, [rsp+38h]; this
0x180027c87  mov     r9d, eax; char *
0x180027c8a  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\coresettinghandlers"...
0x180027c91  mov     edx, 83h; void *
0x180027c96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c9b  nop
0x180027c9c  mov     rcx, [rsp+38h+string]; string
0x180027ca1  call    cs:__imp_WindowsDeleteString
0x180027ca7  mov     eax, ebx
0x180027ca9  jmp     short loc_180027D26
0x180027cab  xor     edx, edx; length
0x180027cad  mov     rcx, [rsp+38h+string]; string
0x180027cb2  call    cs:__imp_WindowsGetStringRawBuffer
0x180027cb8  mov     rbp, rax
0x180027cbb  xor     ebx, ebx
0x180027cbd  lea     r14, ?_sc_rgridpSourceValues@AppSourceSelector@BatteryUsageHandlers@SystemSettings@@0QBUSOURCE_VALUE_PAIR@123@B; SystemSettings::BatteryUsageHandlers::AppSourceSelector::SOURCE_VALUE_PAIR const near * const SystemSettings::BatteryUsageHandlers::AppSourceSelector::_sc_rgridpSourceValues
0x180027cc4  cmp     rbx, 3
0x180027cc8  jnb     short loc_180027D16
0x180027cca  mov     rdi, rbx
0x180027ccd  add     rdi, rdi
0x180027cd0  mov     rdx, rbp; psz2
0x180027cd3  mov     rcx, [r14+rdi*8]; psz1
0x180027cd7  call    cs:__imp_StrCmpLogicalW
0x180027cdd  test    eax, eax
0x180027cdf  jz      short loc_180027CE6
0x180027ce1  inc     rbx
0x180027ce4  jmp     short loc_180027CC4
0x180027ce6  mov     eax, [r14+rdi*8+8]
0x180027ceb  mov     [rsi+130h], eax
0x180027cf1  mov     rax, [rsi]
0x180027cf4  mov     rdx, rsi
0x180027cf7  mov     rcx, rsi
0x180027cfa  mov     rax, [rax+0C0h]
0x180027d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d06  nop
0x180027d07  mov     rcx, [rsp+38h+string]; string
0x180027d0c  call    cs:__imp_WindowsDeleteString
0x180027d12  xor     eax, eax
0x180027d14  jmp     short loc_180027D26
0x180027d16  mov     rcx, [rsp+38h+string]; string
0x180027d1b  call    cs:__imp_WindowsDeleteString
0x180027d21  mov     eax, 80004005h
0x180027d26  mov     rbx, [rsp+38h+arg_0]
0x180027d2b  mov     rbp, [rsp+38h+arg_10]
0x180027d30  add     rsp, 20h
0x180027d34  pop     r14
0x180027d36  pop     rdi
0x180027d37  pop     rsi
0x180027d38  retn
```
