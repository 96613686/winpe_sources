# FSStartWindowsUpdateScanAction::InitializeParameters(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x1800abd70`
- end: `0x1800abf2b`
- name: `?InitializeParameters@FSStartWindowsUpdateScanAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `443`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x1800168c8`
- `0x1800a5884`
- `0x1800abd70`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800abe17`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800abeae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800abe17`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800abeae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800abe2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800abec2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800abe2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800abec2`

## string_xrefs

- `0x1800abe51`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsstartwindowsupdatescanaction.cpp`
- `0x1800abef6`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsstartwindowsupdatescanaction.cpp`

## pseudocode

```c
__int64 __fastcall FSStartWindowsUpdateScanAction::InitializeParameters(__int64 a1, __int64 *a2)
{
  int inited; // ebx
  __int64 v5; // rdx
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  __int64 v8; // r12
  __int64 (__fastcall *v9)(__int64, HSTRING, __int64); // r13
  const ULONG_PTR *v10; // r9
  int v11; // eax
  unsigned int v12; // edi
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, HSTRING, __int64); // r15
  UINT32 length; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string; // [rsp+28h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  length = 0;
  inited = FSServiceDrivenAction::InitLongFromJson(a2, a2, &length);
  if ( inited < 0 )
  {
    v5 = 40;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsstartwindowsupdatescanaction.cpp",
      (const char *)(unsigned int)inited,
      length);
    return (unsigned int)inited;
  }
  if ( length - 1 > 2 )
  {
    inited = -2146698740;
    v5 = 44;
    goto LABEL_17;
  }
  *(_DWORD *)(a1 + 56) = length;
  v6 = -1;
  *(_BYTE *)(a1 + 60) = 0;
  v7 = -1;
  v8 = *a2;
  length = 0;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v8 + 96LL);
  do
    ++v7;
  while ( FSStartWindowsUpdateScanAction::s_interactiveTag[v7] );
  if ( (int)ULongLongToUInt(v7, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, v10);
  WindowsCreateStringReference(FSStartWindowsUpdateScanAction::s_interactiveTag, length, &hstringHeader, &string);
  v11 = v9(v8, string, a1 + 60);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsstartwindowsupdatescanaction.cpp",
      (const char *)(unsigned int)v11,
      length);
    return v12;
  }
  *(_BYTE *)(a1 + 61) = 0;
  v14 = *a2;
  length = 0;
  v15 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v14 + 96LL);
  do
    ++v6;
  while ( FSStartWindowsUpdateScanAction::s_useMsUpdateServiceOnlyTag[v6] );
  if ( (int)ULongLongToUInt(v6, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(
    FSStartWindowsUpdateScanAction::s_useMsUpdateServiceOnlyTag,
    length,
    &hstringHeader,
    &string);
  inited = v15(v14, string, a1 + 61);
  if ( inited < 0 )
  {
    v5 = 54;
    goto LABEL_17;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800abd70  mov     [rsp-38h+arg_10], rbx
0x1800abd75  push    rbp
0x1800abd76  push    rsi
0x1800abd77  push    rdi
0x1800abd78  push    r12
0x1800abd7a  push    r13
0x1800abd7c  push    r14
0x1800abd7e  push    r15
0x1800abd80  mov     rbp, rsp
0x1800abd83  sub     rsp, 50h
0x1800abd87  mov     rax, cs:__security_cookie
0x1800abd8e  xor     rax, rsp
0x1800abd91  mov     [rbp+var_8], rax
0x1800abd95  mov     r14, rcx
0x1800abd98  mov     [rbp+length], 0
0x1800abd9f  mov     rcx, rdx
0x1800abda2  lea     r8, [rbp+length]
0x1800abda6  mov     rsi, rdx
0x1800abda9  call    ?InitLongFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAJ@Z; FSServiceDrivenAction::InitLongFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,long &)
0x1800abdae  xor     r9d, r9d
0x1800abdb1  mov     ebx, eax
0x1800abdb3  test    eax, eax
0x1800abdb5  jns     short loc_1800ABDC0
0x1800abdb7  lea     edx, [r9+28h]
0x1800abdbb  jmp     loc_1800ABEF2
0x1800abdc0  mov     ecx, [rbp+length]
0x1800abdc3  lea     eax, [rcx-1]
0x1800abdc6  cmp     eax, 2
0x1800abdc9  ja      loc_1800ABEE8
0x1800abdcf  mov     [r14+38h], ecx
0x1800abdd3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800abdd7  mov     [r14+3Ch], r9b
0x1800abddb  mov     rcx, rbx
0x1800abdde  mov     r12, [rsi]
0x1800abde1  mov     rdi, cs:?s_interactiveTag@FSStartWindowsUpdateScanAction@@0QEBGEB; ushort const * const FSStartWindowsUpdateScanAction::s_interactiveTag
0x1800abde8  mov     [rbp+length], r9d
0x1800abdec  mov     rax, [r12]
0x1800abdf0  mov     r13, [rax+60h]
0x1800abdf4  inc     rcx; unsigned __int64
0x1800abdf7  cmp     [rdi+rcx*2], r9w
0x1800abdfc  jnz     short loc_1800ABDF4
0x1800abdfe  lea     rdx, [rbp+length]; unsigned int *
0x1800abe02  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800abe07  test    eax, eax
0x1800abe09  jns     short loc_1800ABE1D
0x1800abe0b  xor     r8d, r8d; nNumberOfArguments
0x1800abe0e  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800abe13  lea     edx, [r8+1]; dwExceptionFlags
0x1800abe17  call    cs:__imp_RaiseException
0x1800abe1d  mov     edx, [rbp+length]; length
0x1800abe20  lea     r9, [rbp+string]; string
0x1800abe24  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800abe28  mov     rcx, rdi; sourceString
0x1800abe2b  call    cs:__imp_WindowsCreateStringReference
0x1800abe31  mov     rdx, [rbp+string]
0x1800abe35  lea     r8, [r14+3Ch]
0x1800abe39  mov     rcx, r12
0x1800abe3c  mov     rax, r13
0x1800abe3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abe44  xor     r12d, r12d
0x1800abe47  mov     edi, eax
0x1800abe49  test    eax, eax
0x1800abe4b  jns     short loc_1800ABE6C
0x1800abe4d  mov     rcx, [rbp+38h]; this
0x1800abe51  lea     r8, aOnecoreBaseFli_19; "onecore\\base\\flighting\\flightsetting"...
0x1800abe58  mov     r9d, eax; char *
0x1800abe5b  lea     edx, [r12+32h]; void *
0x1800abe60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800abe65  mov     eax, edi
0x1800abe67  jmp     loc_1800ABF07
0x1800abe6c  mov     [r14+3Dh], r12b
0x1800abe70  mov     rsi, [rsi]
0x1800abe73  mov     rdi, cs:?s_useMsUpdateServiceOnlyTag@FSStartWindowsUpdateScanAction@@0QEBGEB; ushort const * const FSStartWindowsUpdateScanAction::s_useMsUpdateServiceOnlyTag
0x1800abe7a  mov     [rbp+length], r12d
0x1800abe7e  mov     rax, [rsi]
0x1800abe81  mov     r15, [rax+60h]
0x1800abe85  inc     rbx
0x1800abe88  cmp     [rdi+rbx*2], r12w
0x1800abe8d  jnz     short loc_1800ABE85
0x1800abe8f  lea     rdx, [rbp+length]; unsigned int *
0x1800abe93  mov     rcx, rbx; unsigned __int64
0x1800abe96  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800abe9b  test    eax, eax
0x1800abe9d  jns     short loc_1800ABEB4
0x1800abe9f  xor     r9d, r9d; lpArguments
0x1800abea2  xor     r8d, r8d; nNumberOfArguments
0x1800abea5  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800abeaa  lea     edx, [r9+1]; dwExceptionFlags
0x1800abeae  call    cs:__imp_RaiseException
0x1800abeb4  mov     edx, [rbp+length]; length
0x1800abeb7  lea     r9, [rbp+string]; string
0x1800abebb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800abebf  mov     rcx, rdi; sourceString
0x1800abec2  call    cs:__imp_WindowsCreateStringReference
0x1800abec8  mov     rdx, [rbp+string]
0x1800abecc  lea     r8, [r14+3Dh]
0x1800abed0  mov     rcx, rsi
0x1800abed3  mov     rax, r15
0x1800abed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abedb  mov     ebx, eax
0x1800abedd  test    eax, eax
0x1800abedf  jns     short loc_1800ABF05
0x1800abee1  mov     edx, 36h ; '6'
0x1800abee6  jmp     short loc_1800ABEF2
0x1800abee8  mov     ebx, 800BFA0Ch
0x1800abeed  mov     edx, 2Ch ; ','; void *
0x1800abef2  mov     rcx, [rbp+38h]; this
0x1800abef6  lea     r8, aOnecoreBaseFli_19; "onecore\\base\\flighting\\flightsetting"...
0x1800abefd  mov     r9d, ebx; char *
0x1800abf00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800abf05  mov     eax, ebx
0x1800abf07  mov     rcx, [rbp+var_8]
0x1800abf0b  xor     rcx, rsp; StackCookie
0x1800abf0e  call    __security_check_cookie
0x1800abf13  mov     rbx, [rsp+50h+arg_10]
0x1800abf1b  add     rsp, 50h
0x1800abf1f  pop     r15
0x1800abf21  pop     r14
0x1800abf23  pop     r13
0x1800abf25  pop     r12
0x1800abf27  pop     rdi
0x1800abf28  pop     rsi
0x1800abf29  pop     rbp
0x1800abf2a  retn
```
