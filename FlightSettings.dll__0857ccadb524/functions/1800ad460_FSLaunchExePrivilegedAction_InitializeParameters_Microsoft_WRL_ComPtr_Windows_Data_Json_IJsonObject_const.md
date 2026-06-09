# FSLaunchExePrivilegedAction::InitializeParameters(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x1800ad460`
- end: `0x1800ad744`
- name: `?InitializeParameters@FSLaunchExePrivilegedAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `740`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x18001ec78`
- `0x1800a579c`
- `0x1800ad460`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad4d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad58e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad686`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad4d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad58e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad686`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ad4e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ad5a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ad69a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ad4e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ad5a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ad69a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad5c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad6bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad5c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad6bd`

## string_xrefs

- `0x1800ad534`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fslaunchexeprivilegedaction.cpp`
- `0x1800ad5e5`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fslaunchexeprivilegedaction.cpp`
- `0x1800ad6df`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fslaunchexeprivilegedaction.cpp`

## pseudocode

```c
__int64 __fastcall FSLaunchExePrivilegedAction::InitializeParameters(__int64 a1, __int64 *a2)
{
  __int64 v4; // r14
  __int64 (__fastcall *v5)(__int64, HSTRING, HSTRING *); // r15
  unsigned __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // r14
  int (__fastcall *v12)(__int64, HSTRING, HSTRING *); // r15
  unsigned __int64 v13; // rcx
  PCWSTR v14; // rax
  int inited; // eax
  __int64 v16; // rdx
  __int64 v17; // rdi
  int (__fastcall *v18)(__int64, HSTRING, HSTRING *); // r14
  unsigned __int64 v19; // rcx
  PCWSTR v20; // rax
  int v21; // eax
  UINT32 length; // [rsp+20h] [rbp-50h] BYREF
  HSTRING v24; // [rsp+28h] [rbp-48h] BYREF
  HSTRING v25; // [rsp+30h] [rbp-40h] BYREF
  HSTRING v26; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v26 = 0;
  v4 = *a2;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)*a2 + 80LL);
  length = 0;
  v6 = -1;
  do
    ++v6;
  while ( FSLaunchExePrivilegedAction::s_exeNameTag[v6] );
  if ( (int)ULongLongToUInt(v6, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(FSLaunchExePrivilegedAction::s_exeNameTag, length, &hstringHeader, &string);
  v7 = v5(v4, string, &v26);
  v8 = v7;
  if ( v7 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v26, 0);
    v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
           a1 + 56,
           StringRawBuffer,
           -1);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 50;
      goto LABEL_9;
    }
    v24 = 0;
    v11 = *a2;
    v12 = *(int (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)*a2 + 80LL);
    length = 0;
    v13 = -1;
    do
      ++v13;
    while ( FSLaunchExePrivilegedAction::s_argumentTag[v13] );
    if ( (int)ULongLongToUInt(v13, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSLaunchExePrivilegedAction::s_argumentTag, length, &hstringHeader, &string);
    if ( v12(v11, string, &v24) < 0
      || (v14 = WindowsGetStringRawBuffer(v24, 0),
          inited = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                     a1 + 80,
                     v14,
                     -1),
          v8 = inited,
          inited >= 0) )
    {
      length = 0;
      FSServiceDrivenAction::InitDwordFromJson(a2, L"Options", &length);
      *(_DWORD *)(a1 + 104) = length;
      inited = FSServiceDrivenAction::InitDwordFromJson(a2, L"Timeout", a1 + 108);
      v8 = inited;
      if ( inited >= 0 )
      {
        v25 = 0;
        v17 = *a2;
        v18 = *(int (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v17 + 80LL);
        length = 0;
        v19 = -1;
        do
          ++v19;
        while ( FSLaunchExePrivilegedAction::s_expiryTag[v19] );
        if ( (int)ULongLongToUInt(v19, &length) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        WindowsCreateStringReference(FSLaunchExePrivilegedAction::s_expiryTag, length, &hstringHeader, &string);
        if ( v18(v17, string, &v25) < 0
          || (v20 = WindowsGetStringRawBuffer(v25, 0),
              v21 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                      a1 + 112,
                      v20,
                      -1),
              v8 = v21,
              v21 >= 0) )
        {
          Windows::Internal::String::~String((Windows::Internal::String *)&v25);
          Windows::Internal::String::~String((Windows::Internal::String *)&v24);
          v8 = 0;
          goto LABEL_29;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x47,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fslaunchexeprivilegedaction.cpp",
          (const char *)(unsigned int)v21,
          length);
        Windows::Internal::String::~String((Windows::Internal::String *)&v25);
        goto LABEL_18;
      }
      v16 = 65;
    }
    else
    {
      v16 = 56;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fslaunchexeprivilegedaction.cpp",
      (const char *)(unsigned int)inited,
      length);
LABEL_18:
    Windows::Internal::String::~String((Windows::Internal::String *)&v24);
    goto LABEL_29;
  }
  v9 = 49;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fslaunchexeprivilegedaction.cpp",
    (const char *)(unsigned int)v7,
    length);
LABEL_29:
  Windows::Internal::String::~String((Windows::Internal::String *)&v26);
  return v8;
}

```

## disassembly

```asm
0x1800ad460  mov     [rsp-38h+arg_10], rbx
0x1800ad465  push    rbp
0x1800ad466  push    rsi
0x1800ad467  push    rdi
0x1800ad468  push    r12
0x1800ad46a  push    r13
0x1800ad46c  push    r14
0x1800ad46e  push    r15
0x1800ad470  mov     rbp, rsp
0x1800ad473  sub     rsp, 70h
0x1800ad477  mov     rax, cs:__security_cookie
0x1800ad47e  xor     rax, rsp
0x1800ad481  mov     [rbp+var_10], rax
0x1800ad485  mov     rdi, rdx
0x1800ad488  mov     rsi, rcx
0x1800ad48b  xor     r12d, r12d
0x1800ad48e  mov     [rbp+var_38], r12
0x1800ad492  mov     r14, [rdx]
0x1800ad495  mov     rax, [r14]
0x1800ad498  mov     r15, [rax+50h]
0x1800ad49c  mov     rbx, cs:?s_exeNameTag@FSLaunchExePrivilegedAction@@0QEBGEB; ushort const * const FSLaunchExePrivilegedAction::s_exeNameTag
0x1800ad4a3  mov     [rbp+length], r12d
0x1800ad4a7  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800ad4ab  mov     rcx, r13
0x1800ad4ae  inc     rcx; unsigned __int64
0x1800ad4b1  cmp     [rbx+rcx*2], r12w
0x1800ad4b6  jnz     short loc_1800AD4AE
0x1800ad4b8  lea     rdx, [rbp+length]; unsigned int *
0x1800ad4bc  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ad4c1  test    eax, eax
0x1800ad4c3  jns     short loc_1800AD4DA
0x1800ad4c5  xor     r9d, r9d; lpArguments
0x1800ad4c8  xor     r8d, r8d; nNumberOfArguments
0x1800ad4cb  lea     edx, [r9+1]; dwExceptionFlags
0x1800ad4cf  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ad4d4  call    cs:__imp_RaiseException
0x1800ad4da  lea     r9, [rbp+string]; string
0x1800ad4de  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ad4e2  mov     edx, [rbp+length]; length
0x1800ad4e5  mov     rcx, rbx; sourceString
0x1800ad4e8  call    cs:__imp_WindowsCreateStringReference
0x1800ad4ee  lea     r8, [rbp+var_38]
0x1800ad4f2  mov     rdx, [rbp+string]
0x1800ad4f6  mov     rcx, r14
0x1800ad4f9  mov     rax, r15
0x1800ad4fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad501  mov     ebx, eax
0x1800ad503  test    eax, eax
0x1800ad505  jns     short loc_1800AD50E
0x1800ad507  mov     edx, 31h ; '1'
0x1800ad50c  jmp     short loc_1800AD534
0x1800ad50e  xor     edx, edx; length
0x1800ad510  mov     rcx, [rbp+var_38]; string
0x1800ad514  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad51a  lea     rcx, [rsi+38h]
0x1800ad51e  mov     r8, r13
0x1800ad521  mov     rdx, rax
0x1800ad524  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800ad529  mov     ebx, eax
0x1800ad52b  test    eax, eax
0x1800ad52d  jns     short loc_1800AD54C
0x1800ad52f  mov     edx, 32h ; '2'; void *
0x1800ad534  lea     r8, aOnecoreBaseFli_89; "onecore\\base\\flighting\\flightsetting"...
0x1800ad53b  mov     r9d, eax; char *
0x1800ad53e  mov     rcx, [rbp+38h]; this
0x1800ad542  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad547  jmp     loc_1800AD715
0x1800ad54c  mov     [rbp+var_48], r12
0x1800ad550  mov     r14, [rdi]
0x1800ad553  mov     rax, [r14]
0x1800ad556  mov     r15, [rax+50h]
0x1800ad55a  mov     rbx, cs:?s_argumentTag@FSLaunchExePrivilegedAction@@0QEBGEB; ushort const * const FSLaunchExePrivilegedAction::s_argumentTag
0x1800ad561  mov     [rbp+length], r12d
0x1800ad565  mov     rcx, r13
0x1800ad568  inc     rcx; unsigned __int64
0x1800ad56b  cmp     [rbx+rcx*2], r12w
0x1800ad570  jnz     short loc_1800AD568
0x1800ad572  lea     rdx, [rbp+length]; unsigned int *
0x1800ad576  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ad57b  test    eax, eax
0x1800ad57d  jns     short loc_1800AD594
0x1800ad57f  xor     r9d, r9d; lpArguments
0x1800ad582  xor     r8d, r8d; nNumberOfArguments
0x1800ad585  lea     edx, [r9+1]; dwExceptionFlags
0x1800ad589  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ad58e  call    cs:__imp_RaiseException
0x1800ad594  lea     r9, [rbp+string]; string
0x1800ad598  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ad59c  mov     edx, [rbp+length]; length
0x1800ad59f  mov     rcx, rbx; sourceString
0x1800ad5a2  call    cs:__imp_WindowsCreateStringReference
0x1800ad5a8  lea     r8, [rbp+var_48]
0x1800ad5ac  mov     rdx, [rbp+string]
0x1800ad5b0  mov     rcx, r14
0x1800ad5b3  mov     rax, r15
0x1800ad5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad5bb  test    eax, eax
0x1800ad5bd  js      short loc_1800AD607
0x1800ad5bf  xor     edx, edx; length
0x1800ad5c1  mov     rcx, [rbp+var_48]; string
0x1800ad5c5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad5cb  lea     rcx, [rsi+50h]
0x1800ad5cf  mov     r8, r13
0x1800ad5d2  mov     rdx, rax
0x1800ad5d5  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800ad5da  mov     ebx, eax
0x1800ad5dc  test    eax, eax
0x1800ad5de  jns     short loc_1800AD607
0x1800ad5e0  mov     edx, 38h ; '8'; void *
0x1800ad5e5  lea     r8, aOnecoreBaseFli_89; "onecore\\base\\flighting\\flightsetting"...
0x1800ad5ec  mov     r9d, eax; char *
0x1800ad5ef  mov     rcx, [rbp+38h]; this
0x1800ad5f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad5f8  nop
0x1800ad5f9  lea     rcx, [rbp+var_48]; this
0x1800ad5fd  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ad602  jmp     loc_1800AD715
0x1800ad607  mov     [rbp+length], r12d
0x1800ad60b  lea     r8, [rbp+length]
0x1800ad60f  lea     rdx, aOptions; "Options"
0x1800ad616  mov     rcx, rdi
0x1800ad619  call    ?InitDwordFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAK@Z; FSServiceDrivenAction::InitDwordFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,ulong &)
0x1800ad61e  mov     eax, [rbp+length]
0x1800ad621  mov     [rsi+68h], eax
0x1800ad624  lea     r8, [rsi+6Ch]
0x1800ad628  lea     rdx, aTimeout; "Timeout"
0x1800ad62f  mov     rcx, rdi
0x1800ad632  call    ?InitDwordFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAK@Z; FSServiceDrivenAction::InitDwordFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,ulong &)
0x1800ad637  mov     ebx, eax
0x1800ad639  test    eax, eax
0x1800ad63b  jns     short loc_1800AD644
0x1800ad63d  mov     edx, 41h ; 'A'
0x1800ad642  jmp     short loc_1800AD5E5
0x1800ad644  mov     [rbp+var_40], r12
0x1800ad648  mov     rdi, [rdi]
0x1800ad64b  mov     rax, [rdi]
0x1800ad64e  mov     r14, [rax+50h]
0x1800ad652  mov     rbx, cs:?s_expiryTag@FSLaunchExePrivilegedAction@@0QEBGEB; ushort const * const FSLaunchExePrivilegedAction::s_expiryTag
0x1800ad659  mov     [rbp+length], r12d
0x1800ad65d  mov     rcx, r13
0x1800ad660  inc     rcx; unsigned __int64
0x1800ad663  cmp     [rbx+rcx*2], r12w
0x1800ad668  jnz     short loc_1800AD660
0x1800ad66a  lea     rdx, [rbp+length]; unsigned int *
0x1800ad66e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ad673  test    eax, eax
0x1800ad675  jns     short loc_1800AD68C
0x1800ad677  xor     r9d, r9d; lpArguments
0x1800ad67a  xor     r8d, r8d; nNumberOfArguments
0x1800ad67d  lea     edx, [r9+1]; dwExceptionFlags
0x1800ad681  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ad686  call    cs:__imp_RaiseException
0x1800ad68c  lea     r9, [rbp+string]; string
0x1800ad690  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ad694  mov     edx, [rbp+length]; length
0x1800ad697  mov     rcx, rbx; sourceString
0x1800ad69a  call    cs:__imp_WindowsCreateStringReference
0x1800ad6a0  lea     r8, [rbp+var_40]
0x1800ad6a4  mov     rdx, [rbp+string]
0x1800ad6a8  mov     rcx, rdi
0x1800ad6ab  mov     rax, r14
0x1800ad6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad6b3  test    eax, eax
0x1800ad6b5  js      short loc_1800AD6FF
0x1800ad6b7  xor     edx, edx; length
0x1800ad6b9  mov     rcx, [rbp+var_40]; string
0x1800ad6bd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad6c3  lea     rcx, [rsi+70h]
0x1800ad6c7  mov     r8, r13
0x1800ad6ca  mov     rdx, rax
0x1800ad6cd  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800ad6d2  mov     ebx, eax
0x1800ad6d4  test    eax, eax
0x1800ad6d6  jns     short loc_1800AD6FF
0x1800ad6d8  mov     rcx, [rbp+38h]; this
0x1800ad6dc  mov     r9d, eax; char *
0x1800ad6df  lea     r8, aOnecoreBaseFli_89; "onecore\\base\\flighting\\flightsetting"...
0x1800ad6e6  mov     edx, 47h ; 'G'; void *
0x1800ad6eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad6f0  nop
0x1800ad6f1  lea     rcx, [rbp+var_40]; this
0x1800ad6f5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ad6fa  jmp     loc_1800AD5F9
0x1800ad6ff  lea     rcx, [rbp+var_40]; this
0x1800ad703  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ad708  nop
0x1800ad709  lea     rcx, [rbp+var_48]; this
0x1800ad70d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ad712  mov     ebx, r12d
0x1800ad715  lea     rcx, [rbp+var_38]; this
0x1800ad719  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ad71e  mov     eax, ebx
0x1800ad720  mov     rcx, [rbp+var_10]
0x1800ad724  xor     rcx, rsp; StackCookie
0x1800ad727  call    __security_check_cookie
0x1800ad72c  mov     rbx, [rsp+70h+arg_10]
0x1800ad734  add     rsp, 70h
0x1800ad738  pop     r15
0x1800ad73a  pop     r14
0x1800ad73c  pop     r13
0x1800ad73e  pop     r12
0x1800ad740  pop     rdi
0x1800ad741  pop     rsi
0x1800ad742  pop     rbp
0x1800ad743  retn
```
