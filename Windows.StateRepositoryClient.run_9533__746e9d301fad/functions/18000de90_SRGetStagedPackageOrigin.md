# SRGetStagedPackageOrigin

- ea: `0x18000de90`
- end: `0x18000dfff`
- name: `SRGetStagedPackageOrigin`
- size: `367`
- prototype: `__int64 __fastcall(PCWSTR sourceString)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180002980`
- `0x1800075e4`
- `0x180008a68`
- `0x180008cb0`
- `0x18000956c`
- `0x18000b30c`
- `0x18000b348`
- `0x18000c408`
- `0x18000de90`
- `0x180025ecc`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000df86`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000df86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000df9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000df9a`

## pseudocode

```c
__int64 __fastcall SRGetStagedPackageOrigin(PCWSTR sourceString, _DWORD *a2)
{
  int v4; // eax
  const unsigned __int16 *v5; // rdx
  unsigned int v6; // ebx
  _QWORD *v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rbx
  unsigned __int64 v11; // rcx
  __int64 (__fastcall *v12)(__int64, HSTRING, int *); // r14
  UINT32 length; // [rsp+20h] [rbp-40h] BYREF
  int v15; // [rsp+24h] [rbp-3Ch] BYREF
  int v16; // [rsp+28h] [rbp-38h] BYREF
  __int64 v17; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  if ( !sourceString )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v16 = -2147221008;
  v4 = Common::AutoWinRTInitialize::Initialize(&v16);
  v6 = v4;
  if ( v4 >= 0 )
  {
    v17 = 0;
    v7 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[41])v5);
    v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
           *v7,
           &v17);
    v6 = v8;
    if ( v8 >= 0 )
    {
      v10 = v17;
      v11 = -1;
      v15 = 0;
      length = 0;
      v12 = *(__int64 (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)v17 + 288LL);
      do
        ++v11;
      while ( sourceString[v11] );
      if ( (int)ULongLongToUInt(v11, &length) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(sourceString, length, &hstringHeader, &string);
      v8 = v12(v10, string, &v15);
      v6 = v8;
      if ( v8 >= 0 )
      {
        *a2 = v15;
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v17);
        v6 = 0;
        goto LABEL_17;
      }
      v9 = 101;
    }
    else
    {
      v9 = 98;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)(unsigned int)v8,
      length);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v17);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)(unsigned int)v4,
      length);
  }
LABEL_17:
  Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v16);
  return v6;
}

```

## disassembly

```asm
0x18000de90  mov     [rsp-28h+arg_10], rbx
0x18000de95  push    rbp
0x18000de96  push    rsi
0x18000de97  push    rdi
0x18000de98  push    r14
0x18000de9a  push    r15
0x18000de9c  mov     rbp, rsp
0x18000de9f  sub     rsp, 60h
0x18000dea3  mov     rax, cs:__security_cookie
0x18000deaa  xor     rax, rsp
0x18000dead  mov     [rbp+var_8], rax
0x18000deb1  xor     r15d, r15d
0x18000deb4  mov     rdi, rdx
0x18000deb7  mov     rsi, rcx
0x18000deba  test    rcx, rcx
0x18000debd  jnz     short loc_18000DEC4
0x18000debf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000dec4  test    rdi, rdi
0x18000dec7  jnz     short loc_18000DECE
0x18000dec9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000dece  lea     rcx, [rbp+var_38]
0x18000ded2  mov     [rbp+var_38], 800401F0h
0x18000ded9  call    ?Initialize@AutoWinRTInitialize@Common@@QEAAJW4RO_INIT_TYPE@@@Z; Common::AutoWinRTInitialize::Initialize(RO_INIT_TYPE)
0x18000dede  mov     ebx, eax
0x18000dee0  test    eax, eax
0x18000dee2  jns     short loc_18000DF01
0x18000dee4  mov     rcx, [rbp+28h]; this
0x18000dee8  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000deef  mov     r9d, eax; char *
0x18000def2  mov     edx, 5Dh ; ']'; void *
0x18000def7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000defc  jmp     loc_18000DFD4
0x18000df01  lea     rcx, [rbp+string]; string
0x18000df05  mov     [rbp+var_30], r15
0x18000df09  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x18000df0e  lea     rdx, [rbp+var_30]
0x18000df12  mov     rcx, [rax]
0x18000df15  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x18000df1a  mov     ebx, eax
0x18000df1c  test    eax, eax
0x18000df1e  jns     short loc_18000DF46
0x18000df20  mov     edx, 62h ; 'b'; void *
0x18000df25  mov     rcx, [rbp+28h]; this
0x18000df29  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000df30  mov     r9d, eax; char *
0x18000df33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df38  lea     rcx, [rbp+var_30]
0x18000df3c  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000df41  jmp     loc_18000DFD4
0x18000df46  mov     rbx, [rbp+var_30]
0x18000df4a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000df4e  mov     [rbp+var_3C], r15d
0x18000df52  mov     [rbp+length], r15d
0x18000df56  mov     rax, [rbx]
0x18000df59  mov     r14, [rax+120h]
0x18000df60  inc     rcx; unsigned __int64
0x18000df63  cmp     [rsi+rcx*2], r15w
0x18000df68  jnz     short loc_18000DF60
0x18000df6a  lea     rdx, [rbp+length]; unsigned int *
0x18000df6e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18000df73  test    eax, eax
0x18000df75  jns     short loc_18000DF8C
0x18000df77  xor     r9d, r9d; lpArguments
0x18000df7a  xor     r8d, r8d; nNumberOfArguments
0x18000df7d  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000df82  lea     edx, [r9+1]; dwExceptionFlags
0x18000df86  call    cs:__imp_RaiseException
0x18000df8c  mov     edx, [rbp+length]; length
0x18000df8f  lea     r9, [rbp+string]; string
0x18000df93  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000df97  mov     rcx, rsi; sourceString
0x18000df9a  call    cs:__imp_WindowsCreateStringReference
0x18000dfa0  mov     rdx, [rbp+string]
0x18000dfa4  lea     r8, [rbp+var_3C]
0x18000dfa8  mov     rcx, rbx
0x18000dfab  mov     rax, r14
0x18000dfae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfb3  mov     ebx, eax
0x18000dfb5  test    eax, eax
0x18000dfb7  jns     short loc_18000DFC3
0x18000dfb9  mov     edx, 65h ; 'e'
0x18000dfbe  jmp     loc_18000DF25
0x18000dfc3  mov     eax, [rbp+var_3C]
0x18000dfc6  lea     rcx, [rbp+var_30]
0x18000dfca  mov     [rdi], eax
0x18000dfcc  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000dfd1  mov     ebx, r15d
0x18000dfd4  lea     rcx, [rbp+var_38]; this
0x18000dfd8  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x18000dfdd  mov     eax, ebx
0x18000dfdf  mov     rcx, [rbp+var_8]
0x18000dfe3  xor     rcx, rsp; StackCookie
0x18000dfe6  call    __security_check_cookie
0x18000dfeb  mov     rbx, [rsp+60h+arg_10]
0x18000dff3  add     rsp, 60h
0x18000dff7  pop     r15
0x18000dff9  pop     r14
0x18000dffb  pop     rdi
0x18000dffc  pop     rsi
0x18000dffd  pop     rbp
0x18000dffe  retn
```
