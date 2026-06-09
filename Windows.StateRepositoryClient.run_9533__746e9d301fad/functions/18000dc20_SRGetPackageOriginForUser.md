# SRGetPackageOriginForUser

- ea: `0x18000dc20`
- end: `0x18000de7f`
- name: `SRGetPackageOriginForUser`
- size: `607`
- prototype: `__int64 __fastcall(PCWSTR sourceString, PSID Sid)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002980`
- `0x1800075e4`
- `0x180008a1c`
- `0x180008a68`
- `0x180008cb0`
- `0x180008cec`
- `0x18000956c`
- `0x18000b30c`
- `0x18000b348`
- `0x18000c408`
- `0x18000dc20`
- `0x180025ecc`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000dde8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000dde8`
- `ntdll!RtlLengthSid` at `0x18000dd04`
- `ntdll!RtlLengthSid` at `0x18000dd04`
- `ntdll!RtlValidSid` at `0x18000dc66`
- `ntdll!RtlValidSid` at `0x18000dc66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ddfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ddfc`

## pseudocode

```c
__int64 __fastcall SRGetPackageOriginForUser(PCWSTR sourceString, PSID Sid, _DWORD *a3)
{
  int v6; // eax
  const unsigned __int16 *v7; // rdx
  unsigned int v8; // ebx
  _QWORD *v9; // rax
  int v10; // eax
  ULONG v11; // r14d
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, PSID, __int64 *); // rbx
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  _QWORD *v16; // rax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rbx
  unsigned __int64 v20; // rcx
  __int64 (__fastcall *v21)(__int64, __int64, HSTRING, int *); // rdi
  int v23; // [rsp+20h] [rbp-60h]
  __int64 v24; // [rsp+30h] [rbp-50h] BYREF
  __int64 v25; // [rsp+38h] [rbp-48h] BYREF
  UINT32 length; // [rsp+40h] [rbp-40h] BYREF
  int v27; // [rsp+44h] [rbp-3Ch] BYREF
  int v28; // [rsp+48h] [rbp-38h] BYREF
  __int64 v29; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  if ( !sourceString )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( Sid && !RtlValidSid(Sid) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v28 = -2147221008;
  v6 = Common::AutoWinRTInitialize::Initialize(&v28);
  v8 = v6;
  if ( v6 >= 0 )
  {
    v25 = 0;
    v9 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[38])v7);
    v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(
            *v9,
            &v25);
    v8 = v10;
    if ( v10 >= 0 )
    {
      if ( Sid )
        v11 = RtlLengthSid(Sid);
      else
        v11 = 0;
      v12 = v25;
      v24 = 0;
      v13 = *(__int64 (__fastcall **)(__int64, _QWORD, PSID, __int64 *))(*(_QWORD *)v25 + 144LL);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v24);
      v14 = v13(v12, v11, Sid, &v24);
      v8 = v14;
      if ( v14 >= 0 )
      {
        v29 = 0;
        v16 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                          &string,
                          (const unsigned __int16 (*)[41])v15);
        v17 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
                *v16,
                &v29);
        v8 = v17;
        if ( v17 >= 0 )
        {
          v19 = v29;
          v20 = -1;
          v27 = 0;
          length = 0;
          v21 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, int *))(*(_QWORD *)v29 + 280LL);
          do
            ++v20;
          while ( sourceString[v20] );
          if ( (int)ULongLongToUInt(v20, &length) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          WindowsCreateStringReference(sourceString, length, &hstringHeader, &string);
          v17 = v21(v19, v24, string, &v27);
          v8 = v17;
          if ( v17 >= 0 )
          {
            *a3 = v27;
            Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v29);
            Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v24);
            Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v25);
            v8 = 0;
            goto LABEL_29;
          }
          v18 = 76;
        }
        else
        {
          v18 = 73;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
          (const char *)(unsigned int)v17,
          v23);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v29);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x44,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
          (const char *)(unsigned int)v14,
          v23);
      }
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v24);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
        (const char *)(unsigned int)v10,
        v23);
    }
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v25);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)(unsigned int)v6,
      v23);
  }
LABEL_29:
  Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v28);
  return v8;
}

```

## disassembly

```asm
0x18000dc20  mov     [rsp-38h+arg_18], rbx
0x18000dc25  push    rbp
0x18000dc26  push    rsi
0x18000dc27  push    rdi
0x18000dc28  push    r12
0x18000dc2a  push    r13
0x18000dc2c  push    r14
0x18000dc2e  push    r15
0x18000dc30  mov     rbp, rsp
0x18000dc33  sub     rsp, 80h
0x18000dc3a  mov     rax, cs:__security_cookie
0x18000dc41  xor     rax, rsp
0x18000dc44  mov     [rbp+var_8], rax
0x18000dc48  xor     r13d, r13d
0x18000dc4b  mov     r15, r8
0x18000dc4e  mov     rsi, rdx
0x18000dc51  mov     r12, rcx
0x18000dc54  test    rcx, rcx
0x18000dc57  jnz     short loc_18000DC5E
0x18000dc59  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000dc5e  test    rsi, rsi
0x18000dc61  jz      short loc_18000DC75
0x18000dc63  mov     rcx, rsi; Sid
0x18000dc66  call    cs:__imp_RtlValidSid
0x18000dc6c  test    al, al
0x18000dc6e  jnz     short loc_18000DC75
0x18000dc70  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000dc75  test    r15, r15
0x18000dc78  jnz     short loc_18000DC7F
0x18000dc7a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000dc7f  lea     rcx, [rbp+var_38]
0x18000dc83  mov     [rbp+var_38], 800401F0h
0x18000dc8a  call    ?Initialize@AutoWinRTInitialize@Common@@QEAAJW4RO_INIT_TYPE@@@Z; Common::AutoWinRTInitialize::Initialize(RO_INIT_TYPE)
0x18000dc8f  mov     ebx, eax
0x18000dc91  test    eax, eax
0x18000dc93  jns     short loc_18000DCB2
0x18000dc95  mov     rcx, [rbp+38h]; this
0x18000dc99  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000dca0  mov     r9d, eax; char *
0x18000dca3  mov     edx, 3Ah ; ':'; void *
0x18000dca8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dcad  jmp     loc_18000DE4D
0x18000dcb2  lea     rcx, [rbp+string]; string
0x18000dcb6  mov     [rbp+var_48], r13
0x18000dcba  call    ??$?0$0CG@@StringReference@Internal@Windows@@QEAA@AEAY0CG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[38])
0x18000dcbf  lea     rdx, [rbp+var_48]
0x18000dcc3  mov     rcx, [rax]
0x18000dcc6  call    ??$GetActivationFactory@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>)
0x18000dccb  mov     ebx, eax
0x18000dccd  test    eax, eax
0x18000dccf  jns     short loc_18000DCF7
0x18000dcd1  mov     rcx, [rbp+38h]; this
0x18000dcd5  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000dcdc  mov     r9d, eax; char *
0x18000dcdf  mov     edx, 3Fh ; '?'; void *
0x18000dce4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dce9  lea     rcx, [rbp+var_48]
0x18000dced  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000dcf2  jmp     loc_18000DE4D
0x18000dcf7  test    rsi, rsi
0x18000dcfa  jnz     short loc_18000DD01
0x18000dcfc  mov     r14d, r13d
0x18000dcff  jmp     short loc_18000DD0D
0x18000dd01  mov     rcx, rsi; Sid
0x18000dd04  call    cs:__imp_RtlLengthSid
0x18000dd0a  mov     r14d, eax
0x18000dd0d  mov     rdi, [rbp+var_48]
0x18000dd11  mov     [rbp+var_50], r13
0x18000dd15  mov     rcx, [rdi]
0x18000dd18  mov     rbx, [rcx+90h]
0x18000dd1f  lea     rcx, [rbp+var_50]
0x18000dd23  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000dd28  lea     r9, [rbp+var_50]
0x18000dd2c  mov     r8, rsi
0x18000dd2f  mov     edx, r14d
0x18000dd32  mov     rcx, rdi
0x18000dd35  mov     rax, rbx
0x18000dd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd3d  mov     ebx, eax
0x18000dd3f  test    eax, eax
0x18000dd41  jns     short loc_18000DD66
0x18000dd43  mov     rcx, [rbp+38h]; this
0x18000dd47  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000dd4e  mov     r9d, eax; char *
0x18000dd51  mov     edx, 44h ; 'D'; void *
0x18000dd56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd5b  lea     rcx, [rbp+var_50]
0x18000dd5f  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000dd64  jmp     short loc_18000DCE9
0x18000dd66  lea     rcx, [rbp+string]; string
0x18000dd6a  mov     [rbp+var_30], r13
0x18000dd6e  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x18000dd73  lea     rdx, [rbp+var_30]
0x18000dd77  mov     rcx, [rax]
0x18000dd7a  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x18000dd7f  mov     ebx, eax
0x18000dd81  test    eax, eax
0x18000dd83  jns     short loc_18000DDA8
0x18000dd85  mov     edx, 49h ; 'I'; void *
0x18000dd8a  mov     rcx, [rbp+38h]; this
0x18000dd8e  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000dd95  mov     r9d, eax; char *
0x18000dd98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd9d  lea     rcx, [rbp+var_30]
0x18000dda1  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000dda6  jmp     short loc_18000DD5B
0x18000dda8  mov     rbx, [rbp+var_30]
0x18000ddac  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ddb0  mov     [rbp+var_3C], r13d
0x18000ddb4  mov     [rbp+length], r13d
0x18000ddb8  mov     rax, [rbx]
0x18000ddbb  mov     rdi, [rax+118h]
0x18000ddc2  inc     rcx; unsigned __int64
0x18000ddc5  cmp     [r12+rcx*2], r13w
0x18000ddca  jnz     short loc_18000DDC2
0x18000ddcc  lea     rdx, [rbp+length]; unsigned int *
0x18000ddd0  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18000ddd5  test    eax, eax
0x18000ddd7  jns     short loc_18000DDEE
0x18000ddd9  xor     r9d, r9d; lpArguments
0x18000dddc  xor     r8d, r8d; nNumberOfArguments
0x18000dddf  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000dde4  lea     edx, [r9+1]; dwExceptionFlags
0x18000dde8  call    cs:__imp_RaiseException
0x18000ddee  mov     edx, [rbp+length]; length
0x18000ddf1  lea     r9, [rbp+string]; string
0x18000ddf5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000ddf9  mov     rcx, r12; sourceString
0x18000ddfc  call    cs:__imp_WindowsCreateStringReference
0x18000de02  mov     r8, [rbp+string]
0x18000de06  lea     r9, [rbp+var_3C]
0x18000de0a  mov     rdx, [rbp+var_50]
0x18000de0e  mov     rcx, rbx
0x18000de11  mov     rax, rdi
0x18000de14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de19  mov     ebx, eax
0x18000de1b  test    eax, eax
0x18000de1d  jns     short loc_18000DE29
0x18000de1f  mov     edx, 4Ch ; 'L'
0x18000de24  jmp     loc_18000DD8A
0x18000de29  mov     eax, [rbp+var_3C]
0x18000de2c  lea     rcx, [rbp+var_30]
0x18000de30  mov     [r15], eax
0x18000de33  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000de38  lea     rcx, [rbp+var_50]
0x18000de3c  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000de41  lea     rcx, [rbp+var_48]
0x18000de45  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000de4a  mov     ebx, r13d
0x18000de4d  lea     rcx, [rbp+var_38]; this
0x18000de51  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x18000de56  mov     eax, ebx
0x18000de58  mov     rcx, [rbp+var_8]
0x18000de5c  xor     rcx, rsp; StackCookie
0x18000de5f  call    __security_check_cookie
0x18000de64  mov     rbx, [rsp+80h+arg_18]
0x18000de6c  add     rsp, 80h
0x18000de73  pop     r15
0x18000de75  pop     r14
0x18000de77  pop     r13
0x18000de79  pop     r12
0x18000de7b  pop     rdi
0x18000de7c  pop     rsi
0x18000de7d  pop     rbp
0x18000de7e  retn
```
