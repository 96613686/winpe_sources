# ClassicAppManagerFactory::RuntimeClassInitialize(void)

- ea: `0x180041d24`
- end: `0x180041e08`
- name: `?RuntimeClassInitialize@ClassicAppManagerFactory@@QEAAJXZ`
- size: `228`
- prototype: `__int64 __fastcall(ClassicAppManagerFactory *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180040180`

## callees

- `0x180006ddc`
- `0x180007560`
- `0x180041d24`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180041d86`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180041d86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041d70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041d70`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180041d9c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180041d9c`

## string_xrefs

- `0x180041db2`: `shell\cpls\appwzdui\installedclassicappinfo.cpp`

## pseudocode

```c
__int64 __fastcall ClassicAppManagerFactory::RuntimeClassInitialize(ClassicAppManagerFactory *this)
{
  _QWORD *v1; // rdi
  HRESULT v3; // eax
  int ActivationFactory; // ebx
  __int64 v5; // rdx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = (_QWORD *)((char *)this + 80);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 80);
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Internal.Management.Deployment.Preview.ClassicAppInfoInternal",
         0x45u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_ac7ed533_3e39_4350_a0e3_ccb7d8043825, v1);
  if ( ActivationFactory < 0 )
  {
    v5 = 114;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"shell\\cpls\\appwzdui\\installedclassicappinfo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)hstringHeader.Reserved.Reserved1);
    return (unsigned int)ActivationFactory;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(*(_QWORD *)*v1 + 48LL))(
                        *v1,
                        (char *)this + 96,
                        (char *)this + 88);
  if ( ActivationFactory < 0 )
  {
    v5 = 119;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x180041d24  mov     [rsp+arg_8], rbx
0x180041d29  mov     [rsp+arg_10], rsi
0x180041d2e  push    rdi
0x180041d2f  sub     rsp, 50h
0x180041d33  mov     rax, cs:__security_cookie
0x180041d3a  xor     rax, rsp
0x180041d3d  mov     [rsp+58h+var_18], rax
0x180041d42  lea     rdi, [rcx+50h]
0x180041d46  mov     rsi, rcx
0x180041d49  mov     rcx, rdi
0x180041d4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041d51  lea     r9, [rsp+58h+string]; string
0x180041d56  mov     [rsp+58h+string], 0
0x180041d5f  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x180041d64  mov     edx, 45h ; 'E'; length
0x180041d69  lea     rcx, sourceString; "Windows.Internal.Management.Deployment."...
0x180041d70  call    cs:__imp_WindowsCreateStringReference
0x180041d76  test    eax, eax
0x180041d78  jns     short loc_180041D8D
0x180041d7a  xor     r9d, r9d; lpArguments
0x180041d7d  xor     r8d, r8d; nNumberOfArguments
0x180041d80  mov     ecx, eax; dwExceptionCode
0x180041d82  lea     edx, [r9+1]; dwExceptionFlags
0x180041d86  call    cs:__imp_RaiseException
0x180041d8c  int     3; Trap to Debugger
0x180041d8d  mov     rcx, [rsp+58h+string]
0x180041d92  lea     rdx, _GUID_ac7ed533_3e39_4350_a0e3_ccb7d8043825
0x180041d99  mov     r8, rdi
0x180041d9c  call    cs:__imp_RoGetActivationFactory
0x180041da2  mov     ebx, eax
0x180041da4  test    eax, eax
0x180041da6  jns     short loc_180041DC5
0x180041da8  mov     edx, 72h ; 'r'; void *
0x180041dad  mov     rcx, [rsp+58h]; this
0x180041db2  lea     r8, aShellCplsAppwz; "shell\\cpls\\appwzdui\\installedclassic"...
0x180041db9  mov     r9d, ebx; char *
0x180041dbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041dc1  mov     eax, ebx
0x180041dc3  jmp     short loc_180041DEB
0x180041dc5  mov     rcx, [rdi]
0x180041dc8  lea     r8, [rsi+58h]
0x180041dcc  lea     rdx, [rsi+60h]
0x180041dd0  mov     rax, [rcx]
0x180041dd3  mov     rax, [rax+30h]
0x180041dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ddc  mov     ebx, eax
0x180041dde  test    eax, eax
0x180041de0  jns     short loc_180041DE9
0x180041de2  mov     edx, 77h ; 'w'
0x180041de7  jmp     short loc_180041DAD
0x180041de9  xor     eax, eax
0x180041deb  mov     rcx, [rsp+58h+var_18]
0x180041df0  xor     rcx, rsp; StackCookie
0x180041df3  call    __security_check_cookie
0x180041df8  mov     rbx, [rsp+58h+arg_8]
0x180041dfd  mov     rsi, [rsp+58h+arg_10]
0x180041e02  add     rsp, 50h
0x180041e06  pop     rdi
0x180041e07  retn
```
