# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x180028f20`
- end: `0x180029029`
- name: `?SetValue@CBatterySaverSettingsThresholdValue@BatterySaverOneCoreDataModel@SystemSettings@@MEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `265`
- prototype: `int(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18000eacc`
- `0x180028f20`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028fa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028fa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028f4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028f91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028ffc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002900b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028f4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028f91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028ffc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002900b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x180028fc7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x180028fc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::SetValue(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue *this,
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
    for ( i = 0; i < 7; ++i )
    {
      if ( !StrCmpLogicalW(
              *((PCWSTR *)&SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::_thresholdValues
              + 2 * i),
              StringRawBuffer) )
      {
        *((_DWORD *)this + 92) = *((_DWORD *)&SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::_thresholdValues
                                 + 4 * i
                                 + 2);
        (*(void (__fastcall **)(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue *, SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue *))(*(_QWORD *)this + 192LL))(
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
      (void *)0xED3,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\batterysaver.cpp",
      (const char *)(unsigned int)v5,
      v10);
    WindowsDeleteString(string);
    return v6;
  }
}

```

## disassembly

```asm
0x180028f20  mov     [rsp+arg_0], rbx
0x180028f25  mov     [rsp+arg_10], rbp
0x180028f2a  push    rsi
0x180028f2b  push    rdi
0x180028f2c  push    r14; int
0x180028f2e  sub     rsp, 20h
0x180028f32  mov     rdi, rdx
0x180028f35  mov     rsi, rcx
0x180028f38  mov     [rsp+38h+string], 0
0x180028f41  mov     rax, [rdx]
0x180028f44  mov     rbx, [rax+98h]
0x180028f4b  xor     ecx, ecx; string
0x180028f4d  call    cs:__imp_WindowsDeleteString
0x180028f53  mov     [rsp+38h+string], 0
0x180028f5c  lea     rdx, [rsp+38h+string]
0x180028f61  mov     rcx, rdi
0x180028f64  mov     rax, rbx
0x180028f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f6c  mov     ebx, eax
0x180028f6e  test    eax, eax
0x180028f70  jns     short loc_180028F9B
0x180028f72  mov     rcx, [rsp+38h]; this
0x180028f77  mov     r9d, eax; char *
0x180028f7a  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x180028f81  mov     edx, 0ED3h; void *
0x180028f86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028f8b  nop
0x180028f8c  mov     rcx, [rsp+38h+string]; string
0x180028f91  call    cs:__imp_WindowsDeleteString
0x180028f97  mov     eax, ebx
0x180028f99  jmp     short loc_180029016
0x180028f9b  xor     edx, edx; length
0x180028f9d  mov     rcx, [rsp+38h+string]; string
0x180028fa2  call    cs:__imp_WindowsGetStringRawBuffer
0x180028fa8  mov     rbp, rax
0x180028fab  xor     ebx, ebx
0x180028fad  lea     r14, ?_thresholdValues@CBatterySaverSettingsThresholdValue@BatterySaverOneCoreDataModel@SystemSettings@@0QBUTHRESHOLD_VALUE_PAIR@123@B; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::THRESHOLD_VALUE_PAIR const near * const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::_thresholdValues
0x180028fb4  cmp     rbx, 7
0x180028fb8  jnb     short loc_180029006
0x180028fba  mov     rdi, rbx
0x180028fbd  add     rdi, rdi
0x180028fc0  mov     rdx, rbp; psz2
0x180028fc3  mov     rcx, [r14+rdi*8]; psz1
0x180028fc7  call    cs:__imp_StrCmpLogicalW
0x180028fcd  test    eax, eax
0x180028fcf  jz      short loc_180028FD6
0x180028fd1  inc     rbx
0x180028fd4  jmp     short loc_180028FB4
0x180028fd6  mov     eax, [r14+rdi*8+8]
0x180028fdb  mov     [rsi+170h], eax
0x180028fe1  mov     rax, [rsi]
0x180028fe4  mov     rdx, rsi
0x180028fe7  mov     rcx, rsi
0x180028fea  mov     rax, [rax+0C0h]
0x180028ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ff6  nop
0x180028ff7  mov     rcx, [rsp+38h+string]; string
0x180028ffc  call    cs:__imp_WindowsDeleteString
0x180029002  xor     eax, eax
0x180029004  jmp     short loc_180029016
0x180029006  mov     rcx, [rsp+38h+string]; string
0x18002900b  call    cs:__imp_WindowsDeleteString
0x180029011  mov     eax, 80004005h
0x180029016  mov     rbx, [rsp+38h+arg_0]
0x18002901b  mov     rbp, [rsp+38h+arg_10]
0x180029020  add     rsp, 20h
0x180029024  pop     r14
0x180029026  pop     rdi
0x180029027  pop     rsi
0x180029028  retn
```
