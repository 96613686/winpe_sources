# WOSCOneSettings::GetSettingValue(ushort const *,CSpDynamicString &)

- ea: `0x180012e08`
- end: `0x180012fc0`
- name: `?GetSettingValue@WOSCOneSettings@@QEAAJPEBGAEAVCSpDynamicString@@@Z`
- size: `440`
- prototype: `__int64 __fastcall(WOSCOneSettings *__hidden this, const unsigned __int16 *, struct CSpDynamicString *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e620`
- `0x18001592c`

## callees

- `0x1800069fc`
- `0x180006e28`
- `0x18000efec`
- `0x180012e08`
- `0x180019760`
- `0x18001b010`

## import_xrefs

- `msvcrt!_wcsupr_s` at `0x180012ed0`
- `msvcrt!_wcsupr_s` at `0x180012ed0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012f59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012f8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012f59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012f8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012ec1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012ec1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012ee0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012f64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012f95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012ee0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012f64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012f95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012f75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012f75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012f19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012f19`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WOSCOneSettings::GetSettingValue(
        __int64 **this,
        const unsigned __int16 *a2,
        struct CSpDynamicString *a3)
{
  unsigned int v5; // ebx
  unsigned __int64 v7; // rbx
  wchar_t *v8; // rdi
  int v9; // ecx
  __int64 v10; // rax
  __int64 *v11; // rsi
  __int64 v12; // r14
  int v13; // edx
  unsigned int v14; // r8d
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  int v18; // eax
  PCWSTR StringRawBuffer; // rax
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  wchar_t *String; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING v23; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  if ( !*this )
  {
    v5 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
      (const char *)0x8000FFFFLL,
      (int)string);
    return v5;
  }
  string = 0;
  String = 0;
  CSpDynamicString::operator=(&String, a2);
  v7 = -1;
  v8 = String;
  if ( String )
  {
    v10 = -1;
    do
      ++v10;
    while ( String[v10] );
    v9 = v10;
    if ( (unsigned int)v10 != v10 )
    {
      SetLastError(0x216u);
      v9 = -1;
    }
  }
  else
  {
    v9 = 0;
  }
  _wcsupr_s(v8, (unsigned int)(v9 + 1));
  v11 = *this;
  v12 = *v11;
  WindowsDeleteString(string);
  string = 0;
  v23 = 0;
  do
    ++v7;
  while ( v8[v7] );
  if ( v7 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v13, v14);
    __debugbreak();
  }
  if ( (int)v7 + 1 < (unsigned int)v7 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v13, v14);
    JUMPOUT(0x180012FBFLL);
  }
  v15 = WindowsCreateStringReference(v8, v7, &hstringHeader, &v23);
  if ( v15 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
    __debugbreak();
  }
  v18 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING *))(v12 + 80))(v11, v23, &string);
  v5 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
      (const char *)(unsigned int)v18,
      (int)string);
    CoTaskMemFree(v8);
    WindowsDeleteString(string);
    return v5;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  CSpDynamicString::operator=(a3, StringRawBuffer);
  CoTaskMemFree(v8);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x180012e08  mov     [rsp-38h+arg_18], rbx
0x180012e0d  push    rbp
0x180012e0e  push    rsi
0x180012e0f  push    rdi
0x180012e10  push    r12
0x180012e12  push    r13
0x180012e14  push    r14
0x180012e16  push    r15
0x180012e18  mov     rbp, rsp
0x180012e1b  sub     rsp, 60h
0x180012e1f  mov     rax, cs:__security_cookie
0x180012e26  xor     rax, rsp
0x180012e29  mov     [rbp+var_10], rax
0x180012e2d  mov     r15, r8
0x180012e30  mov     rsi, rcx
0x180012e33  xor     r12d, r12d
0x180012e36  cmp     [rcx], r12
0x180012e39  jnz     short loc_180012E7E
0x180012e3b  mov     rcx, [rbp+38h]; this
0x180012e3f  mov     ebx, 8000FFFFh
0x180012e44  mov     r9d, ebx; char *
0x180012e47  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x180012e4e  mov     edx, 87h; void *
0x180012e53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e58  mov     eax, ebx
0x180012e5a  mov     rcx, [rbp+var_10]
0x180012e5e  xor     rcx, rsp; StackCookie
0x180012e61  call    __security_check_cookie
0x180012e66  mov     rbx, [rsp+60h+arg_18]
0x180012e6e  add     rsp, 60h
0x180012e72  pop     r15
0x180012e74  pop     r14
0x180012e76  pop     r13
0x180012e78  pop     r12
0x180012e7a  pop     rdi
0x180012e7b  pop     rsi
0x180012e7c  pop     rbp
0x180012e7d  retn
0x180012e7e  mov     [rbp+string], r12
0x180012e82  mov     [rbp+String], r12
0x180012e86  lea     rcx, [rbp+String]
0x180012e8a  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x180012e8f  nop
0x180012e90  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012e94  mov     r13d, 0FFFFFFFFh
0x180012e9a  mov     rdi, [rbp+String]
0x180012e9e  test    rdi, rdi
0x180012ea1  jnz     short loc_180012EA8
0x180012ea3  mov     ecx, r12d
0x180012ea6  jmp     short loc_180012ECA
0x180012ea8  mov     rax, rbx
0x180012eab  inc     rax
0x180012eae  cmp     [rdi+rax*2], r12w
0x180012eb3  jnz     short loc_180012EAB
0x180012eb5  mov     ecx, eax
0x180012eb7  cmp     rcx, rax
0x180012eba  jz      short loc_180012ECA
0x180012ebc  mov     ecx, 216h; dwErrCode
0x180012ec1  call    cs:__imp_SetLastError
0x180012ec7  mov     ecx, r13d
0x180012eca  lea     edx, [rcx+1]; Size
0x180012ecd  mov     rcx, rdi; String
0x180012ed0  call    cs:__imp__wcsupr_s
0x180012ed6  mov     rsi, [rsi]
0x180012ed9  mov     r14, [rsi]
0x180012edc  mov     rcx, [rbp+string]; string
0x180012ee0  call    cs:__imp_WindowsDeleteString
0x180012ee6  mov     [rbp+string], r12
0x180012eea  mov     [rbp+var_18], r12
0x180012eee  inc     rbx
0x180012ef1  cmp     [rdi+rbx*2], r12w
0x180012ef6  jnz     short loc_180012EEE
0x180012ef8  cmp     rbx, r13
0x180012efb  ja      loc_180012FAA
0x180012f01  lea     eax, [rbx+1]
0x180012f04  cmp     eax, ebx
0x180012f06  jb      loc_180012FB5
0x180012f0c  lea     r9, [rbp+var_18]; string
0x180012f10  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180012f14  mov     edx, ebx; length
0x180012f16  mov     rcx, rdi; sourceString
0x180012f19  call    cs:__imp_WindowsCreateStringReference
0x180012f1f  test    eax, eax
0x180012f21  js      short loc_180012FA2
0x180012f23  lea     r8, [rbp+string]
0x180012f27  mov     rdx, [rbp+var_18]
0x180012f2b  mov     rcx, rsi
0x180012f2e  mov     rax, [r14+50h]
0x180012f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f37  mov     ebx, eax
0x180012f39  test    eax, eax
0x180012f3b  jns     short loc_180012F6F
0x180012f3d  mov     rcx, [rbp+38h]; this
0x180012f41  mov     r9d, eax; char *
0x180012f44  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x180012f4b  mov     edx, 8Eh; void *
0x180012f50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f55  nop
0x180012f56  mov     rcx, rdi; pv
0x180012f59  call    cs:__imp_CoTaskMemFree
0x180012f5f  nop
0x180012f60  mov     rcx, [rbp+string]; string
0x180012f64  call    cs:__imp_WindowsDeleteString
0x180012f6a  jmp     loc_180012E58
0x180012f6f  xor     edx, edx; length
0x180012f71  mov     rcx, [rbp+string]; string
0x180012f75  call    cs:__imp_WindowsGetStringRawBuffer
0x180012f7b  mov     rdx, rax
0x180012f7e  mov     rcx, r15
0x180012f81  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x180012f86  nop
0x180012f87  mov     rcx, rdi; pv
0x180012f8a  call    cs:__imp_CoTaskMemFree
0x180012f90  nop
0x180012f91  mov     rcx, [rbp+string]; string
0x180012f95  call    cs:__imp_WindowsDeleteString
0x180012f9b  xor     eax, eax
0x180012f9d  jmp     loc_180012E5A
0x180012fa2  mov     ecx, eax; this
0x180012fa4  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180012fa9  int     3; Trap to Debugger
0x180012faa  mov     ecx, 80070216h; this
0x180012faf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180012fb4  int     3; Trap to Debugger
0x180012fb5  mov     ecx, 80070216h; this
0x180012fba  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
