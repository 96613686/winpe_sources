# WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_ActivateApplication(void)

- ea: `0x18000fce0`
- end: `0x18000fff4`
- name: `?_ActivateApplication@AppLauncherInternal@Calls@ApplicationModel@WindowsInternal@@MEAAJXZ`
- size: `788`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *this, __int64, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800012b8`
- `0x1800013f0`
- `0x180001dc0`
- `0x18000cf2c`
- `0x18000fce0`
- `0x180015864`
- `0x180019010`

## import_xrefs

- `PhoneUtil!GetSignedInUserForAppActivation` at `0x18000fd77`
- `PhoneUtil!GetSignedInUserForAppActivation` at `0x18000fd77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fea5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000feb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ffa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fea5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000feb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ffa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fdd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fdd7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fdf0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fdf0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000fe05`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000fe05`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_ActivateApplication(
        WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *this,
        __int64 a2,
        int a3,
        int a4)
{
  int v5; // eax
  int SignedInUserForAppActivation; // esi
  struct Windows::System::IUser *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  HSTRING v11; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // rcx
  PCWSTR v14; // rax
  const char *v15; // rax
  const unsigned __int16 *v16; // rax
  struct Windows::System::IUser *v17; // rcx
  _QWORD v18[7]; // [rsp+78h] [rbp-21h] BYREF
  HSTRING string; // [rsp+B0h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp+1Fh] BYREF
  __int64 v21; // [rsp+D0h] [rbp+37h] BYREF
  struct Windows::System::IUser *v22; // [rsp+D8h] [rbp+3Fh] BYREF
  unsigned int v23; // [rsp+E0h] [rbp+47h] BYREF

  if ( (unsigned int)dword_180025038 > 4 )
  {
    v18[0] = "AppLauncherInternal: Activate Application";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)this,
      (unsigned int)byte_180020755,
      a3,
      a4,
      (__int64)v18);
  }
  v5 = (*(__int64 (__fastcall **)(WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *))(*(_QWORD *)this
                                                                                                  + 184LL))(this);
  SignedInUserForAppActivation = v5;
  if ( v5 < 0 )
  {
    Log_HREvent_0((unsigned int)v5, 1, "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\applauncher.cpp");
    return (unsigned int)SignedInUserForAppActivation;
  }
  v22 = 0;
  SignedInUserForAppActivation = GetSignedInUserForAppActivation(&v22);
  if ( SignedInUserForAppActivation < 0 )
    goto LABEL_7;
  v21 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.ApplicationModel.Activation.Private.ApplicationActivation",
         0x41u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  SignedInUserForAppActivation = RoGetActivationFactory(string, &GUID_193d1b8e_e23f_4e26_b40f_3b91a99b383f, &v21);
  if ( SignedInUserForAppActivation < 0 )
    goto LABEL_7;
  if ( *((_DWORD *)this + 22) != 4 )
  {
    SignedInUserForAppActivation = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, struct Windows::System::IUser *))(*(_QWORD *)v21 + 48LL))(
                                     v21,
                                     *(_QWORD *)(*((_QWORD *)this + 4) + 16LL),
                                     *(_QWORD *)(*((_QWORD *)this + 5) + 16LL),
                                     0,
                                     0,
                                     v22);
    if ( SignedInUserForAppActivation >= 0 )
      goto LABEL_22;
LABEL_7:
    Log_HREvent_0(
      (unsigned int)SignedInUserForAppActivation,
      1,
      "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\applauncher.cpp");
    v8 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(struct Windows::System::IUser *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return (unsigned int)SignedInUserForAppActivation;
  }
  v9 = *(_QWORD *)this;
  v23 = 0;
  SignedInUserForAppActivation = (*(__int64 (__fastcall **)(WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *, unsigned int *))(v9 + 152))(
                                   this,
                                   &v23);
  if ( (unsigned int)dword_180025038 > 4
    && (qword_180025048 & 0x400000000000LL) != 0
    && (qword_180025050 & 0x400000000000LL) == qword_180025050 )
  {
    v10 = *((_QWORD *)this + 5);
    LODWORD(v18[0]) = *((_DWORD *)this + 20);
    v11 = *(HSTRING *)(v10 + 16);
    v18[1] = (char *)this + 64;
    StringRawBuffer = WindowsGetStringRawBuffer(v11, 0);
    v13 = *((_QWORD *)this + 4);
    v18[2] = StringRawBuffer;
    v14 = WindowsGetStringRawBuffer(*(HSTRING *)(v13 + 16), 0);
    v18[6] = 0x1000000;
    v18[3] = v14;
    v18[4] = v23;
    v15 = "App activation succeeded";
    if ( SignedInUserForAppActivation )
      v15 = "App activation failed";
    v18[5] = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      "App activation failed",
      word_1800206C2);
  }
  if ( SignedInUserForAppActivation < 0 )
    goto LABEL_7;
LABEL_22:
  v16 = WindowsGetStringRawBuffer(*(HSTRING *)(*((_QWORD *)this + 4) + 16LL), 0);
  TraceLogging::ApplicationActivated(v16);
  v17 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(struct Windows::System::IUser *))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x18000fce0  mov     [rsp-8+arg_8], rbx
0x18000fce5  mov     [rsp-8+arg_10], rsi
0x18000fcea  push    rbp
0x18000fceb  lea     rbp, [rsp-57h]
0x18000fcf0  sub     rsp, 0F0h
0x18000fcf7  mov     rax, cs:__security_cookie
0x18000fcfe  xor     rax, rsp
0x18000fd01  mov     [rbp+57h+var_8], rax
0x18000fd05  mov     eax, cs:dword_180025038
0x18000fd0b  mov     rbx, rcx
0x18000fd0e  cmp     eax, 4
0x18000fd11  jbe     short loc_18000FD33
0x18000fd13  lea     rax, aApplauncherint_6; "AppLauncherInternal: Activate Applicati"...
0x18000fd1a  mov     [rbp+57h+var_78], rax
0x18000fd1e  lea     rdx, byte_180020755
0x18000fd25  lea     rax, [rbp+57h+var_78]
0x18000fd29  mov     [rsp+0F0h+var_D0], rax
0x18000fd2e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000fd33  mov     rax, [rbx]
0x18000fd36  mov     rcx, rbx
0x18000fd39  mov     rax, [rax+0B8h]
0x18000fd40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd45  mov     esi, eax
0x18000fd47  test    eax, eax
0x18000fd49  jns     short loc_18000FD6B
0x18000fd4b  mov     r9d, 136h
0x18000fd51  lea     r8, aOnecoreuapNetP_3; "onecoreuap\\net\\phone\\telephonyintera"...
0x18000fd58  mov     edx, 1
0x18000fd5d  mov     ecx, eax
0x18000fd5f  call    Log_HREvent_0
0x18000fd64  mov     eax, esi
0x18000fd66  jmp     loc_18000FFD3
0x18000fd6b  lea     rcx, [rbp+57h+var_18]
0x18000fd6f  mov     [rbp+57h+var_18], 0
0x18000fd77  call    cs:__imp_?GetSignedInUserForAppActivation@@YAJPEAPEAUIUser@System@Windows@@@Z; GetSignedInUserForAppActivation(Windows::System::IUser * *)
0x18000fd7d  mov     esi, eax
0x18000fd7f  test    eax, eax
0x18000fd81  jns     short loc_18000FDBB
0x18000fd83  mov     r9d, 13Ah
0x18000fd89  lea     r8, aOnecoreuapNetP_3; "onecoreuap\\net\\phone\\telephonyintera"...
0x18000fd90  mov     edx, 1
0x18000fd95  mov     ecx, esi
0x18000fd97  call    Log_HREvent_0
0x18000fd9c  mov     rcx, [rbp+57h+var_18]
0x18000fda0  test    rcx, rcx
0x18000fda3  jz      short loc_18000FD64
0x18000fda5  mov     [rbp+57h+var_18], 0
0x18000fdad  mov     rax, [rcx]
0x18000fdb0  mov     rax, [rax+10h]
0x18000fdb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdb9  jmp     short loc_18000FD64
0x18000fdbb  lea     r9, [rbp+57h+string]; string
0x18000fdbf  mov     [rbp+57h+var_20], 0
0x18000fdc7  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000fdcb  mov     edx, 41h ; 'A'; length
0x18000fdd0  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Activation_Private_ApplicationActivation@@3QBGB; "Windows.ApplicationModel.Activation.Pri"...
0x18000fdd7  call    cs:__imp_WindowsCreateStringReference
0x18000fddd  test    eax, eax
0x18000fddf  jns     short loc_18000FDF6
0x18000fde1  xor     r9d, r9d; lpArguments
0x18000fde4  xor     r8d, r8d; nNumberOfArguments
0x18000fde7  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000fdec  lea     edx, [r9+1]; dwExceptionFlags
0x18000fdf0  call    cs:__imp_RaiseException
0x18000fdf6  mov     rcx, [rbp+57h+string]
0x18000fdfa  lea     r8, [rbp+57h+var_20]
0x18000fdfe  lea     rdx, _GUID_193d1b8e_e23f_4e26_b40f_3b91a99b383f
0x18000fe05  call    cs:__imp_RoGetActivationFactory
0x18000fe0b  mov     esi, eax
0x18000fe0d  test    eax, eax
0x18000fe0f  jns     short loc_18000FE1C
0x18000fe11  mov     r9d, 13Eh
0x18000fe17  jmp     loc_18000FD89
0x18000fe1c  cmp     dword ptr [rbx+58h], 4
0x18000fe20  jnz     loc_18000FF56
0x18000fe26  mov     rax, [rbx]
0x18000fe29  lea     rdx, [rbp+57h+var_10]
0x18000fe2d  mov     rcx, rbx
0x18000fe30  mov     [rbp+57h+var_10], 0
0x18000fe37  mov     rax, [rax+98h]
0x18000fe3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe43  mov     ecx, cs:dword_180025038
0x18000fe49  mov     esi, eax
0x18000fe4b  cmp     ecx, 4
0x18000fe4e  jbe     loc_18000FF47
0x18000fe54  mov     rax, cs:qword_180025050
0x18000fe5b  mov     rdx, 400000000000h
0x18000fe65  mov     rcx, cs:qword_180025048
0x18000fe6c  test    rdx, rcx
0x18000fe6f  jz      loc_18000FF47
0x18000fe75  mov     rcx, rax
0x18000fe78  and     rcx, rdx
0x18000fe7b  cmp     rcx, rax
0x18000fe7e  jnz     loc_18000FF47
0x18000fe84  mov     eax, [rbx+54h]
0x18000fe87  xor     edx, edx; length
0x18000fe89  mov     rcx, [rbx+28h]
0x18000fe8d  mov     [rbp+57h+var_7C], eax
0x18000fe90  mov     eax, [rbx+50h]
0x18000fe93  mov     dword ptr [rbp+57h+var_78], eax
0x18000fe96  lea     rax, [rbx+40h]
0x18000fe9a  mov     [rbp+57h+var_80], esi
0x18000fe9d  mov     rcx, [rcx+10h]; string
0x18000fea1  mov     [rbp+57h+var_70], rax
0x18000fea5  call    cs:__imp_WindowsGetStringRawBuffer
0x18000feab  mov     rcx, [rbx+20h]
0x18000feaf  xor     edx, edx; length
0x18000feb1  mov     [rbp+57h+var_68], rax
0x18000feb5  mov     rcx, [rcx+10h]; string
0x18000feb9  call    cs:__imp_WindowsGetStringRawBuffer
0x18000febf  test    esi, esi
0x18000fec1  mov     [rbp+57h+var_48], 1000000h
0x18000fec9  mov     [rbp+57h+var_60], rax
0x18000fecd  lea     rcx, aAppActivationF; "App activation failed"
0x18000fed4  mov     eax, [rbp+57h+var_10]
0x18000fed7  lea     rdx, word_1800206C2
0x18000fede  mov     [rbp+57h+var_58], rax
0x18000fee2  lea     rax, aAppActivationS; "App activation succeeded"
0x18000fee9  cmovnz  rax, rcx
0x18000feed  mov     [rbp+57h+var_50], rax
0x18000fef1  lea     rax, [rbp+57h+var_80]
0x18000fef5  mov     [rsp+0F0h+var_90], rax
0x18000fefa  lea     rax, [rbp+57h+var_7C]
0x18000fefe  mov     [rsp+0F0h+var_98], rax
0x18000ff03  lea     rax, [rbp+57h+var_78]
0x18000ff07  mov     [rsp+0F0h+var_A0], rax
0x18000ff0c  lea     rax, [rbp+57h+var_70]
0x18000ff10  mov     [rsp+0F0h+var_A8], rax
0x18000ff15  lea     rax, [rbp+57h+var_68]
0x18000ff19  mov     [rsp+0F0h+var_B0], rax
0x18000ff1e  lea     rax, [rbp+57h+var_60]
0x18000ff22  mov     [rsp+0F0h+var_B8], rax
0x18000ff27  lea     rax, [rbp+57h+var_58]
0x18000ff2b  mov     [rsp+0F0h+var_C0], rax
0x18000ff30  lea     rax, [rbp+57h+var_50]
0x18000ff34  mov     [rsp+0F0h+var_C8], rax
0x18000ff39  lea     rax, [rbp+57h+var_48]
0x18000ff3d  mov     [rsp+0F0h+var_D0], rax
0x18000ff42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U5@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@77@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000ff47  test    esi, esi
0x18000ff49  jns     short loc_18000FF9C
0x18000ff4b  mov     r9d, 155h
0x18000ff51  jmp     loc_18000FD89
0x18000ff56  mov     r9, [rbp+57h+var_18]
0x18000ff5a  mov     rcx, [rbp+57h+var_20]
0x18000ff5e  mov     r8, [rbx+28h]
0x18000ff62  mov     rdx, [rbx+20h]
0x18000ff66  mov     [rsp+0F0h+var_C8], r9
0x18000ff6b  xor     r9d, r9d
0x18000ff6e  mov     rax, [rcx]
0x18000ff71  mov     r8, [r8+10h]
0x18000ff75  mov     rdx, [rdx+10h]
0x18000ff79  mov     [rsp+0F0h+var_D0], 0
0x18000ff82  mov     rax, [rax+30h]
0x18000ff86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff8b  mov     esi, eax
0x18000ff8d  test    eax, eax
0x18000ff8f  jns     short loc_18000FF9C
0x18000ff91  mov     r9d, 15Ah
0x18000ff97  jmp     loc_18000FD89
0x18000ff9c  mov     rcx, [rbx+20h]
0x18000ffa0  xor     edx, edx; length
0x18000ffa2  mov     rcx, [rcx+10h]; string
0x18000ffa6  call    cs:__imp_WindowsGetStringRawBuffer
0x18000ffac  mov     rcx, rax; unsigned __int16 *
0x18000ffaf  call    ?ApplicationActivated@TraceLogging@@SAXPEBG@Z; TraceLogging::ApplicationActivated(ushort const *)
0x18000ffb4  mov     rcx, [rbp+57h+var_18]
0x18000ffb8  test    rcx, rcx
0x18000ffbb  jz      short loc_18000FFD1
0x18000ffbd  mov     [rbp+57h+var_18], 0
0x18000ffc5  mov     rax, [rcx]
0x18000ffc8  mov     rax, [rax+10h]
0x18000ffcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffd1  xor     eax, eax
0x18000ffd3  mov     rcx, [rbp+57h+var_8]
0x18000ffd7  xor     rcx, rsp; StackCookie
0x18000ffda  call    __security_check_cookie
0x18000ffdf  lea     r11, [rsp+0F0h+var_s0]
0x18000ffe7  mov     rbx, [r11+18h]
0x18000ffeb  mov     rsi, [r11+20h]
0x18000ffef  mov     rsp, r11
0x18000fff2  pop     rbp
0x18000fff3  retn
```
