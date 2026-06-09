# AppReadiness::PackageInfo::SupportsMultipleUsers(void)

- ea: `0x180003ee0`
- end: `0x18000411c`
- name: `?SupportsMultipleUsers@PackageInfo@AppReadiness@@QEAA_NXZ`
- size: `572`
- prototype: `bool __fastcall(AppReadiness::PackageInfo *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005ac6c`

## callees

- `0x180002958`
- `0x180003ee0`
- `0x180027a4c`
- `0x18003e210`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003fcd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800040c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800040d7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003fcd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800040c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800040d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003f48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003fe1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003f48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003fe1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180003f71`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180003f71`

## string_xrefs

- `0x1800040e6`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x1800040f2`: `AppReadiness::PackageInfo::SupportsMultipleUsers`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall AppReadiness::PackageInfo::SupportsMultipleUsers(AppReadiness::PackageInfo *this)
{
  HRESULT v2; // eax
  HSTRING v3; // rbx
  _QWORD *v4; // rbx
  __int64 v5; // rsi
  const WCHAR *v6; // rcx
  unsigned __int64 v7; // rdx
  HRESULT v8; // eax
  __int64 v9; // rcx
  _QWORD *v10; // rcx
  int v12; // eax
  int v13; // [rsp+30h] [rbp-50h] BYREF
  __int64 v14; // [rsp+38h] [rbp-48h] BYREF
  _QWORD *v15; // [rsp+40h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string[2]; // [rsp+60h] [rbp-20h] BYREF

  if ( *((_DWORD *)this + 37) )
    return *((_DWORD *)this + 37) == 1;
  *((_DWORD *)this + 37) = 2;
  if ( !*((_QWORD *)this + 11) )
    return *((_DWORD *)this + 37) == 1;
  v15 = 0;
  string[0] = 0;
  v2 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, string);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    goto LABEL_24;
  }
  v3 = string[0];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  if ( (int)RoGetActivationFactory(v3, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v15) >= 0 )
  {
    v14 = 0;
    v4 = v15;
    v5 = *v15;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    v6 = (const WCHAR *)((char *)this + 72);
    if ( *((_QWORD *)this + 12) > 7u )
      v6 = *(const WCHAR **)v6;
    string[0] = 0;
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    if ( v7 > 0xFFFFFFFF || (int)v7 + 1 < (unsigned int)v7 )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v8 = WindowsCreateStringReference(v6, v7, &hstringHeader, string);
    if ( v8 >= 0 )
    {
      if ( (*(int (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v5 + 176))(v4, string[0], &v14) >= 0 )
      {
        v13 = 0;
        v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 1168LL))(v14, &v13);
        if ( v12 < 0 )
        {
          Windows::HResultException::HResultException(
            (Windows::HResultException *)&hstringHeader,
            v12,
            "spPackage->get_EffectiveSupportedUsers(&supportedUsers)",
            "AppReadiness::PackageInfo::SupportsMultipleUsers",
            "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
            345);
          throw (Windows::HResultException *)&hstringHeader;
        }
        if ( v13 == 2 )
          *((_DWORD *)this + 37) = 1;
      }
      v9 = v14;
      if ( v14 )
      {
        v14 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      goto LABEL_15;
    }
LABEL_24:
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
LABEL_15:
  v10 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
  }
  return *((_DWORD *)this + 37) == 1;
}

```

## disassembly

```asm
0x180003ee0  mov     [rsp-18h+arg_8], rbx
0x180003ee5  mov     [rsp-18h+arg_10], rsi
0x180003eea  push    rbp
0x180003eeb  push    rdi
0x180003eec  push    r14
0x180003eee  mov     rbp, rsp
0x180003ef1  sub     rsp, 80h
0x180003ef8  mov     rax, cs:__security_cookie
0x180003eff  xor     rax, rsp
0x180003f02  mov     [rbp+var_10], rax
0x180003f06  mov     rdi, rcx
0x180003f09  xor     r14d, r14d
0x180003f0c  cmp     [rcx+94h], r14d
0x180003f13  jnz     loc_180004042
0x180003f19  mov     dword ptr [rcx+94h], 2
0x180003f23  cmp     [rcx+58h], r14
0x180003f27  jz      loc_180004042
0x180003f2d  mov     [rbp+var_40], r14
0x180003f31  mov     [rbp+string], r14
0x180003f35  lea     r9, [rbp+string]; string
0x180003f39  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180003f3d  lea     edx, [r14+28h]; length
0x180003f41  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180003f48  call    cs:__imp_WindowsCreateStringReference
0x180003f4e  test    eax, eax
0x180003f50  js      loc_1800040B8
0x180003f56  mov     rbx, [rbp+string]
0x180003f5a  lea     rcx, [rbp+var_40]
0x180003f5e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003f63  lea     r8, [rbp+var_40]
0x180003f67  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x180003f6e  mov     rcx, rbx
0x180003f71  call    cs:__imp_RoGetActivationFactory
0x180003f77  test    eax, eax
0x180003f79  js      loc_180004028
0x180003f7f  mov     [rbp+var_48], r14
0x180003f83  mov     rbx, [rbp+var_40]
0x180003f87  mov     rsi, [rbx]
0x180003f8a  lea     rcx, [rbp+var_48]
0x180003f8e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003f93  lea     rcx, [rdi+48h]; sourceString
0x180003f97  cmp     qword ptr [rcx+18h], 7
0x180003f9c  ja      short loc_180003FD4
0x180003f9e  mov     [rbp+string], r14
0x180003fa2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180003fa6  inc     rdx; length
0x180003fa9  cmp     [rcx+rdx*2], r14w
0x180003fae  jnz     short loc_180003FA6
0x180003fb0  mov     eax, 0FFFFFFFFh
0x180003fb5  cmp     rdx, rax
0x180003fb8  jbe     loc_180004070
0x180003fbe  xor     r9d, r9d; lpArguments
0x180003fc1  xor     r8d, r8d; nNumberOfArguments
0x180003fc4  lea     edx, [r9+1]; dwExceptionFlags
0x180003fc8  mov     ecx, 80070216h; dwExceptionCode
0x180003fcd  call    cs:__imp_RaiseException
0x180003fd3  int     3; Trap to Debugger
0x180003fd4  mov     rcx, [rcx]
0x180003fd7  jmp     short loc_180003F9E
0x180003fd9  lea     r9, [rbp+string]; string
0x180003fdd  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180003fe1  call    cs:__imp_WindowsCreateStringReference
0x180003fe7  test    eax, eax
0x180003fe9  js      loc_1800040CB
0x180003fef  lea     r8, [rbp+var_48]
0x180003ff3  mov     rdx, [rbp+string]
0x180003ff7  mov     rcx, rbx
0x180003ffa  mov     rax, [rsi+0B0h]
0x180004001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004006  nop
0x180004007  shr     eax, 1Fh
0x18000400a  xor     al, 1
0x18000400c  jnz     short loc_180004080
0x18000400e  mov     rcx, [rbp+var_48]
0x180004012  test    rcx, rcx
0x180004015  jz      short loc_180004028
0x180004017  mov     [rbp+var_48], r14
0x18000401b  mov     rax, [rcx]
0x18000401e  mov     rax, [rax+10h]
0x180004022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004027  nop
0x180004028  mov     rcx, [rbp+var_40]
0x18000402c  test    rcx, rcx
0x18000402f  jz      short loc_180004042
0x180004031  mov     [rbp+var_40], r14
0x180004035  mov     rax, [rcx]
0x180004038  mov     rax, [rax+10h]
0x18000403c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004041  nop
0x180004042  cmp     dword ptr [rdi+94h], 1
0x180004049  setz    al
0x18000404c  mov     rcx, [rbp+var_10]
0x180004050  xor     rcx, rsp; StackCookie
0x180004053  call    __security_check_cookie
0x180004058  lea     r11, [rsp+80h+var_s0]
0x180004060  mov     rbx, [r11+28h]
0x180004064  mov     rsi, [r11+30h]
0x180004068  mov     rsp, r11
0x18000406b  pop     r14
0x18000406d  pop     rdi
0x18000406e  pop     rbp
0x18000406f  retn
0x180004070  lea     eax, [rdx+1]
0x180004073  cmp     eax, edx
0x180004075  jb      loc_180003FBE
0x18000407b  jmp     loc_180003FD9
0x180004080  mov     [rbp+var_50], r14d
0x180004084  mov     rcx, [rbp+var_48]
0x180004088  mov     rax, [rcx]
0x18000408b  lea     rdx, [rbp+var_50]
0x18000408f  mov     rax, [rax+490h]
0x180004096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000409b  test    eax, eax
0x18000409d  js      short loc_1800040DE
0x18000409f  cmp     [rbp+var_50], 2
0x1800040a3  jnz     loc_18000400E
0x1800040a9  mov     dword ptr [rdi+94h], 1
0x1800040b3  jmp     loc_18000400E
0x1800040b8  xor     r9d, r9d; lpArguments
0x1800040bb  xor     r8d, r8d; nNumberOfArguments
0x1800040be  lea     edx, [r9+1]; dwExceptionFlags
0x1800040c2  mov     ecx, eax; dwExceptionCode
0x1800040c4  call    cs:__imp_RaiseException
0x1800040ca  nop
0x1800040cb  xor     r9d, r9d; lpArguments
0x1800040ce  xor     r8d, r8d; nNumberOfArguments
0x1800040d1  lea     edx, [r9+1]; dwExceptionFlags
0x1800040d5  mov     ecx, eax; dwExceptionCode
0x1800040d7  call    cs:__imp_RaiseException
0x1800040dd  int     3; Trap to Debugger
0x1800040de  mov     [rsp+80h+var_58], 159h; int
0x1800040e6  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800040ed  mov     [rsp+80h+var_60], rcx; char *
0x1800040f2  lea     r9, aAppreadinessPa_0; "AppReadiness::PackageInfo::SupportsMult"...
0x1800040f9  lea     r8, aSppackageGetEf; "spPackage->get_EffectiveSupportedUsers("...
0x180004100  mov     edx, eax; int
0x180004102  lea     rcx, [rbp+hstringHeader]; this
0x180004106  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18000410b  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180004112  lea     rcx, [rbp+hstringHeader]; pExceptionObject
0x180004116  call    _CxxThrowException_0
```
