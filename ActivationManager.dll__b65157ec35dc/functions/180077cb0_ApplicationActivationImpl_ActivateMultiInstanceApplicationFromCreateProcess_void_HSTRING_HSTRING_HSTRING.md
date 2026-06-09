# ApplicationActivationImpl::ActivateMultiInstanceApplicationFromCreateProcess(void *,HSTRING__ *,HSTRING__ *,HSTRING__ *)

- ea: `0x180077cb0`
- end: `0x180077f4f`
- name: `?ActivateMultiInstanceApplicationFromCreateProcess@ApplicationActivationImpl@@UEAAJPEAXPEAUHSTRING__@@11@Z`
- size: `671`
- prototype: `__int64 __fastcall(ApplicationActivationImpl *this, void *, HSTRING, HSTRING, HSTRING string)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x180029028`
- `0x180031540`
- `0x180033200`
- `0x1800374c8`
- `0x1800445ac`
- `0x18004ff24`
- `0x18005ae90`
- `0x1800634cc`
- `0x180077cb0`
- `0x1800780a4`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180077e37`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180077e37`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180077d4d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180077dac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180077d4d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180077dac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077d2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077d8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077d2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077d8f`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x180077dd0`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x180077dd0`

## string_xrefs

- `0x180077d44`: `Windows.CommandLineLaunch`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ApplicationActivationImpl::ActivateMultiInstanceApplicationFromCreateProcess(
        ApplicationActivationImpl *this,
        void *a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING string)
{
  int v7; // eax
  unsigned int v8; // ebx
  const WCHAR *StringRawBuffer; // rax
  unsigned __int64 v10; // rbx
  int v11; // eax
  __int64 v12; // rdx
  const WCHAR *v13; // rax
  unsigned int v14; // eax
  signed int v15; // eax
  unsigned int v16; // eax
  ApplicationActivationImpl *v17; // rcx
  __int64 v18; // r9
  int v19; // eax
  __int64 v20; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  struct IInspectable *v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 applicationUserModelIdLength[2]; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v29; // [rsp+68h] [rbp-98h]
  WCHAR applicationUserModelId[136]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  *(_QWORD *)v25 = a3;
  *(_QWORD *)applicationUserModelIdLength = a4;
  v7 = ApplicationActivationImpl::CheckCallerCapabilities((ApplicationActivationImpl *)((char *)this - 32));
  v8 = v7;
  if ( v7 >= 0 )
  {
    v24 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v10 = -1;
    if ( CompareStringOrdinal(StringRawBuffer, -1, L"Windows.CommandLineLaunch", -1, 1) == 2 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
      v11 = Microsoft::WRL::Details::MakeAndInitialize<CommandLineActivatedEventArgsImpl,IInspectable,HSTRING__ * &,HSTRING__ * &>(
              &v24,
              v25,
              applicationUserModelIdLength);
      v8 = v11;
      if ( v11 < 0 )
      {
        v12 = 519;
LABEL_15:
        v18 = (unsigned int)v11;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
          (const char *)v18,
          bIgnoreCasea);
        goto LABEL_24;
      }
    }
    else
    {
      v13 = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(v13, -1, L"Windows.Launch", -1, 1) != 2 )
      {
        v8 = -2147024809;
        v18 = 2147942487LL;
        v12 = 530;
        goto LABEL_23;
      }
      applicationUserModelIdLength[0] = 130;
      v14 = GetApplicationUserModelId(a2, applicationUserModelIdLength, applicationUserModelId);
      if ( v14 )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x20D,
               (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
               (const char *)v14,
               bIgnoreCasea);
LABEL_24:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
        return v8;
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
      v25[0] = 0;
      do
        ++v10;
      while ( applicationUserModelId[v10] );
      v15 = ULongLongToUInt(v10, v25);
      if ( v15 < 0 )
      {
        RaiseException(v15, 1u, 0, 0);
        __debugbreak();
      }
      v16 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v25[0]);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, applicationUserModelId, v16, v25[0]);
      v11 = ApplicationActivationImpl::ConstructLaunchActivatedEventArgs(v17, v29, a3, &v24);
      v8 = v11;
      if ( v11 < 0 )
      {
        v12 = 526;
        goto LABEL_15;
      }
    }
    v26 = 0;
    v19 = Microsoft::WRL::Details::MakeAndInitialize<Execution::ActivationManagerShim,IApplicationActivationManagerPriv,>(&v26);
    v8 = v19;
    if ( v19 >= 0 )
    {
      v19 = (*(__int64 (__fastcall **)(__int64, void *, struct IInspectable *, HSTRING))(*(_QWORD *)v26 + 80LL))(
              v26,
              a2,
              v24,
              string);
      v8 = v19;
      if ( v19 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
        return 0;
      }
      v20 = 536;
    }
    else
    {
      v20 = 534;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)(unsigned int)v19,
      bIgnoreCasea);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x202,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
    (const char *)(unsigned int)v7,
    bIgnoreCase);
  return v8;
}

```

## disassembly

```asm
0x180077cb0  push    rbp
0x180077cb2  push    rbx
0x180077cb3  push    rsi
0x180077cb4  push    rdi
0x180077cb5  push    r14
0x180077cb7  push    r15
0x180077cb9  lea     rbp, [rsp-98h]
0x180077cc1  sub     rsp, 198h
0x180077cc8  mov     rax, cs:__security_cookie
0x180077ccf  xor     rax, rsp
0x180077cd2  mov     [rbp+0C0h+var_40], rax
0x180077cd9  mov     r14, r8
0x180077cdc  mov     rsi, rdx
0x180077cdf  mov     qword ptr [rsp+1C0h+var_188], r8
0x180077ce4  mov     qword ptr [rsp+1C0h+applicationUserModelIdLength], r9
0x180077ce9  mov     rdi, [rbp+0C0h+string]
0x180077cf0  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x180077cf4  call    ?CheckCallerCapabilities@ApplicationActivationImpl@@AEAAJXZ; ApplicationActivationImpl::CheckCallerCapabilities(void)
0x180077cf9  mov     ebx, eax
0x180077cfb  xor     r15d, r15d
0x180077cfe  test    eax, eax
0x180077d00  jns     short loc_180077D22
0x180077d02  mov     rcx, [rbp+0C8h]; this
0x180077d09  mov     r9d, eax; char *
0x180077d0c  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180077d13  mov     edx, 202h; void *
0x180077d18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077d1d  jmp     loc_180077F2E
0x180077d22  mov     [rsp+1C0h+var_190], r15
0x180077d27  xor     edx, edx; length
0x180077d29  mov     rcx, rdi; string
0x180077d2c  call    cs:__imp_WindowsGetStringRawBuffer
0x180077d32  mov     rcx, rax; lpString1
0x180077d35  mov     [rsp+1C0h+bIgnoreCase], 1; int
0x180077d3d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180077d41  mov     r9d, ebx; cchCount2
0x180077d44  lea     r8, aWindowsCommand; "Windows.CommandLineLaunch"
0x180077d4b  mov     edx, ebx; cchCount1
0x180077d4d  call    cs:__imp_CompareStringOrdinal
0x180077d53  cmp     eax, 2
0x180077d56  jnz     short loc_180077D8A
0x180077d58  lea     rcx, [rsp+1C0h+var_190]
0x180077d5d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077d62  lea     r8, [rsp+1C0h+applicationUserModelIdLength]
0x180077d67  lea     rdx, [rsp+1C0h+var_188]
0x180077d6c  lea     rcx, [rsp+1C0h+var_190]
0x180077d71  call    ??$MakeAndInitialize@VCommandLineActivatedEventArgsImpl@@UIInspectable@@AEAPEAUHSTRING__@@AEAPEAU3@@Details@WRL@Microsoft@@YAJPEAPEAUIInspectable@@AEAPEAUHSTRING__@@1@Z; Microsoft::WRL::Details::MakeAndInitialize<CommandLineActivatedEventArgsImpl,IInspectable,HSTRING__ * &,HSTRING__ * &>(IInspectable * *,HSTRING__ * &,HSTRING__ * &)
0x180077d76  mov     ebx, eax
0x180077d78  test    eax, eax
0x180077d7a  jns     loc_180077E84
0x180077d80  mov     edx, 207h
0x180077d85  jmp     loc_180077E7C
0x180077d8a  xor     edx, edx; length
0x180077d8c  mov     rcx, rdi; string
0x180077d8f  call    cs:__imp_WindowsGetStringRawBuffer
0x180077d95  mov     rcx, rax; lpString1
0x180077d98  mov     [rsp+1C0h+bIgnoreCase], 1; int
0x180077da0  mov     r9d, ebx; cchCount2
0x180077da3  lea     r8, String2; "Windows.Launch"
0x180077daa  mov     edx, ebx; cchCount1
0x180077dac  call    cs:__imp_CompareStringOrdinal
0x180077db2  cmp     eax, 2
0x180077db5  jnz     loc_180077F03
0x180077dbb  mov     [rsp+1C0h+applicationUserModelIdLength], 82h
0x180077dc3  lea     r8, [rsp+1C0h+applicationUserModelId]; applicationUserModelId
0x180077dc8  lea     rdx, [rsp+1C0h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180077dcd  mov     rcx, rsi; hProcess
0x180077dd0  call    cs:__imp_GetApplicationUserModelId
0x180077dd6  test    eax, eax
0x180077dd8  jz      short loc_180077DFC
0x180077dda  mov     rcx, [rbp+0C8h]; this
0x180077de1  mov     r9d, eax; char *
0x180077de4  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180077deb  mov     edx, 20Dh; void *
0x180077df0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180077df5  mov     ebx, eax
0x180077df7  jmp     loc_180077F24
0x180077dfc  lea     rcx, [rsp+1C0h+var_190]
0x180077e01  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077e06  mov     [rsp+1C0h+var_188], r15d
0x180077e0b  lea     rax, [rsp+1C0h+applicationUserModelId]
0x180077e10  inc     rbx
0x180077e13  cmp     [rax+rbx*2], r15w
0x180077e18  jnz     short loc_180077E10
0x180077e1a  lea     rdx, [rsp+1C0h+var_188]; unsigned int *
0x180077e1f  mov     rcx, rbx; unsigned __int64
0x180077e22  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180077e27  test    eax, eax
0x180077e29  jns     short loc_180077E3E
0x180077e2b  xor     r9d, r9d; lpArguments
0x180077e2e  xor     r8d, r8d; nNumberOfArguments
0x180077e31  lea     edx, [r9+1]; dwExceptionFlags
0x180077e35  mov     ecx, eax; dwExceptionCode
0x180077e37  call    cs:__imp_RaiseException
0x180077e3d  int     3; Trap to Debugger
0x180077e3e  mov     ecx, [rsp+1C0h+var_188]; unsigned int
0x180077e42  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180077e47  mov     r9d, [rsp+1C0h+var_188]; unsigned int
0x180077e4c  mov     r8d, eax; unsigned int
0x180077e4f  lea     rdx, [rsp+1C0h+applicationUserModelId]; sourceString
0x180077e54  lea     rcx, [rsp+1C0h+hstringHeader]; hstringHeader
0x180077e59  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180077e5e  nop
0x180077e5f  lea     r9, [rsp+1C0h+var_190]; struct IInspectable **
0x180077e64  mov     r8, r14; HSTRING
0x180077e67  mov     rdx, [rsp+1C0h+var_158]; HSTRING
0x180077e6c  call    ?ConstructLaunchActivatedEventArgs@ApplicationActivationImpl@@AEAAJPEAUHSTRING__@@0PEAPEAUIInspectable@@@Z; ApplicationActivationImpl::ConstructLaunchActivatedEventArgs(HSTRING__ *,HSTRING__ *,IInspectable * *)
0x180077e71  mov     ebx, eax
0x180077e73  test    eax, eax
0x180077e75  jns     short loc_180077E84
0x180077e77  mov     edx, 20Eh
0x180077e7c  mov     r9d, eax
0x180077e7f  jmp     loc_180077F10
0x180077e84  mov     [rsp+1C0h+var_180], r15
0x180077e89  lea     rcx, [rsp+1C0h+var_180]
0x180077e8e  call    ??$MakeAndInitialize@VActivationManagerShim@Execution@@UIApplicationActivationManagerPriv@@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIApplicationActivationManagerPriv@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<Execution::ActivationManagerShim,IApplicationActivationManagerPriv,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IApplicationActivationManagerPriv>>)
0x180077e93  mov     ebx, eax
0x180077e95  test    eax, eax
0x180077e97  jns     short loc_180077EA0
0x180077e99  mov     edx, 216h
0x180077e9e  jmp     short loc_180077EC7
0x180077ea0  mov     rcx, [rsp+1C0h+var_180]
0x180077ea5  mov     rax, [rcx]
0x180077ea8  mov     r9, rdi
0x180077eab  mov     r8, [rsp+1C0h+var_190]
0x180077eb0  mov     rdx, rsi
0x180077eb3  mov     rax, [rax+50h]
0x180077eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077ebc  mov     ebx, eax
0x180077ebe  test    eax, eax
0x180077ec0  jns     short loc_180077EEA
0x180077ec2  mov     edx, 218h; void *
0x180077ec7  mov     r9d, eax; char *
0x180077eca  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180077ed1  mov     rcx, [rbp+0C8h]; this
0x180077ed8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077edd  nop
0x180077ede  lea     rcx, [rsp+1C0h+var_180]
0x180077ee3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077ee8  jmp     short loc_180077F24
0x180077eea  lea     rcx, [rsp+1C0h+var_180]
0x180077eef  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077ef4  nop
0x180077ef5  lea     rcx, [rsp+1C0h+var_190]
0x180077efa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077eff  xor     eax, eax
0x180077f01  jmp     short loc_180077F30
0x180077f03  mov     ebx, 80070057h
0x180077f08  mov     r9d, ebx; char *
0x180077f0b  mov     edx, 212h; void *
0x180077f10  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180077f17  mov     rcx, [rbp+0C8h]; this
0x180077f1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077f23  nop
0x180077f24  lea     rcx, [rsp+1C0h+var_190]
0x180077f29  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077f2e  mov     eax, ebx
0x180077f30  mov     rcx, [rbp+0C0h+var_40]
0x180077f37  xor     rcx, rsp; StackCookie
0x180077f3a  call    __security_check_cookie
0x180077f3f  add     rsp, 198h
0x180077f46  pop     r15
0x180077f48  pop     r14
0x180077f4a  pop     rdi
0x180077f4b  pop     rsi
0x180077f4c  pop     rbx
0x180077f4d  pop     rbp
0x180077f4e  retn
```
