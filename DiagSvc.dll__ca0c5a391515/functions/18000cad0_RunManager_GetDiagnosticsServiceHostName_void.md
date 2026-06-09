# RunManager::GetDiagnosticsServiceHostName(void)

- ea: `0x18000cad0`
- end: `0x18000ccc5`
- name: `?GetDiagnosticsServiceHostName@RunManager@@MEAAJXZ`
- size: `501`
- prototype: `__int64 __fastcall(HSTRING *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001720`
- `0x18000216c`
- `0x180003fc0`
- `0x18000a998`
- `0x18000ade0`
- `0x18000cad0`
- `0x18000ec48`
- `0x180010c18`
- `0x180011a20`
- `0x180012874`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cb59`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cb59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000cbfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000cbfb`

## string_xrefs

- `0x18000cb17`: `diagnostics.support.services.microsoft.com`
- `0x18000cb4b`: `SYSTEM\CurrentControlSet\Services\diagsvc\Settings`
- `0x18000cb79`: `diagnostics-dev.support.services.microsoft.com`
- `0x18000cb70`: `diagnostics-uat.support.services.microsoft.com`
- `0x18000cc26`: `RunManager::GetDiagnosticsServiceHostName`
- `0x18000cc31`: `Get Diagnostic Service Uri`

## pseudocode

```c
__int64 __fastcall RunManager::GetDiagnosticsServiceHostName(HSTRING *this)
{
  const WCHAR *v2; // rbx
  unsigned __int64 v3; // rcx
  int v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  unsigned int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // r8
  PCWSTR StringRawBuffer; // rax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  unsigned int v16; // [rsp+60h] [rbp-29h] BYREF
  int pvData; // [rsp+64h] [rbp-25h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-21h] BYREF
  HSTRING v19; // [rsp+70h] [rbp-19h] BYREF
  PCWSTR v20; // [rsp+78h] [rbp-11h] BYREF
  char *v21; // [rsp+80h] [rbp-9h] BYREF
  const char *v22; // [rsp+88h] [rbp-1h] BYREF
  const char *v23; // [rsp+90h] [rbp+7h] BYREF
  const char *v24; // [rsp+98h] [rbp+Fh] BYREF
  char *v25; // [rsp+A0h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp+1Fh] BYREF
  HSTRING v27; // [rsp+C0h] [rbp+37h]

  pcbData = 4;
  pvData = 0;
  v2 = L"diagnostics.windows.cloud.microsoft";
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ChangeDiagDomain>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ChangeDiagDomain>::GetImpl'::`2'::impl) )
    v2 = L"diagnostics.support.services.microsoft.com";
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\diagsvc\\Settings",
          L"EndpointType",
          0x10u,
          0,
          &pvData,
          &pcbData) )
  {
    if ( pvData == 1 )
    {
      v2 = L"diagnostics-dev.support.services.microsoft.com";
    }
    else if ( pvData == 2 )
    {
      v2 = L"diagnostics-uat.support.services.microsoft.com";
    }
  }
  v27 = 0;
  v3 = -1;
  v16 = 0;
  do
    ++v3;
  while ( v2[v3] );
  v4 = ULongLongToUInt(v3, &v16);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x18000CCC4LL);
  }
  v7 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v16);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v2, v7, v16);
  v19 = v27;
  v9 = Microsoft::WRL::Wrappers::HString::Set(this + 11, &v19);
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v8, (unsigned int)dword_180039000, v10) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(this[11], 0);
    v16 = 143;
    v20 = StringRawBuffer;
    v21 = (char *)(this + 14);
    v22 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\runmanager\\lib\\runmanager.cpp";
    v23 = "RunManager::GetDiagnosticsServiceHostName";
    v24 = "Get Diagnostic Service Uri";
    v25 = (char *)this + 241;
    LODWORD(v19) = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      v12,
      (unsigned int)&byte_1800300FF,
      v13,
      v14,
      (__int64)&v25,
      (__int64)&v19,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v16,
      (__int64)&v21,
      (__int64)&v20);
  }
  return v9;
}

```

## disassembly

```asm
0x18000cad0  mov     [rsp-8+arg_8], rbx
0x18000cad5  mov     [rsp-8+arg_10], rsi
0x18000cada  push    rbp
0x18000cadb  push    rdi
0x18000cadc  push    r14
0x18000cade  lea     rbp, [rsp-47h]
0x18000cae3  sub     rsp, 0D0h
0x18000caea  mov     rax, cs:__security_cookie
0x18000caf1  xor     rax, rsp
0x18000caf4  mov     [rbp+57h+var_18], rax
0x18000caf8  xor     r14d, r14d
0x18000cafb  mov     [rbp+57h+var_78], 4
0x18000cb02  mov     [rbp+57h+var_7C], r14d
0x18000cb06  mov     rsi, rcx
0x18000cb09  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ChangeDiagDomain@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ChangeDiagDomain@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ChangeDiagDomain> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ChangeDiagDomain>::GetImpl(void)'::`2'::impl
0x18000cb10  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ChangeDiagDomain@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ChangeDiagDomain>::__private_IsEnabled(void)
0x18000cb15  test    al, al
0x18000cb17  lea     rcx, sourceString; "diagnostics.support.services.microsoft."...
0x18000cb1e  lea     rax, [rbp+57h+var_78]
0x18000cb22  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18000cb27  lea     rbx, aDiagnosticsWin; "diagnostics.windows.cloud.microsoft"
0x18000cb2e  lea     rax, [rbp+57h+var_7C]
0x18000cb32  cmovz   rbx, rcx
0x18000cb36  mov     [rsp+0E0h+pvData], rax; pvData
0x18000cb3b  lea     r9d, [r14+10h]; dwFlags
0x18000cb3f  lea     r8, aEndpointtype; "EndpointType"
0x18000cb46  mov     [rsp+0E0h+pdwType], r14; pdwType
0x18000cb4b  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\di"...
0x18000cb52  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000cb59  call    cs:__imp_RegGetValueW
0x18000cb5f  test    eax, eax
0x18000cb61  jnz     short loc_18000CB80
0x18000cb63  mov     ecx, [rbp+57h+var_7C]
0x18000cb66  sub     ecx, 1
0x18000cb69  jz      short loc_18000CB79
0x18000cb6b  cmp     ecx, 1
0x18000cb6e  jnz     short loc_18000CB80
0x18000cb70  lea     rbx, aDiagnosticsUat; "diagnostics-uat.support.services.micros"...
0x18000cb77  jmp     short loc_18000CB80
0x18000cb79  lea     rbx, aDiagnosticsDev; "diagnostics-dev.support.services.micros"...
0x18000cb80  mov     [rbp+57h+var_20], r14
0x18000cb84  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000cb88  mov     [rbp+57h+var_80], r14d
0x18000cb8c  inc     rcx; unsigned __int64
0x18000cb8f  cmp     [rbx+rcx*2], r14w
0x18000cb94  jnz     short loc_18000CB8C
0x18000cb96  lea     rdx, [rbp+57h+var_80]; unsigned int *
0x18000cb9a  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18000cb9f  test    eax, eax
0x18000cba1  js      loc_18000CCBD
0x18000cba7  mov     ecx, [rbp+57h+var_80]; unsigned int
0x18000cbaa  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000cbaf  mov     r9d, [rbp+57h+var_80]; unsigned int
0x18000cbb3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18000cbb7  mov     r8d, eax; unsigned int
0x18000cbba  mov     rdx, rbx; sourceString
0x18000cbbd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000cbc2  mov     rax, [rbp+57h+var_20]
0x18000cbc6  lea     rdx, [rbp+57h+var_70]; HSTRING *
0x18000cbca  lea     rcx, [rsi+58h]; newString
0x18000cbce  mov     [rbp+57h+var_70], rax
0x18000cbd2  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18000cbd7  mov     edx, cs:dword_180039000
0x18000cbdd  mov     ebx, eax
0x18000cbdf  cmp     edx, 5
0x18000cbe2  jbe     loc_18000CC97
0x18000cbe8  call    _tlgKeywordOn
0x18000cbed  test    al, al
0x18000cbef  jz      loc_18000CC97
0x18000cbf5  mov     rcx, [rsi+58h]; string
0x18000cbf9  xor     edx, edx; length
0x18000cbfb  call    cs:__imp_WindowsGetStringRawBuffer
0x18000cc01  lea     rdx, byte_1800300FF
0x18000cc08  mov     [rbp+57h+var_80], 8Fh
0x18000cc0f  mov     [rbp+57h+var_68], rax
0x18000cc13  lea     rax, [rsi+70h]
0x18000cc17  mov     [rbp+57h+var_60], rax
0x18000cc1b  lea     rax, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18000cc22  mov     [rbp+57h+var_58], rax
0x18000cc26  lea     rax, aRunmanagerGetd; "RunManager::GetDiagnosticsServiceHostNa"...
0x18000cc2d  mov     [rbp+57h+var_50], rax
0x18000cc31  lea     rax, aGetDiagnosticS; "Get Diagnostic Service Uri"
0x18000cc38  mov     [rbp+57h+var_48], rax
0x18000cc3c  lea     rax, [rsi+0F1h]
0x18000cc43  mov     [rbp+57h+var_40], rax
0x18000cc47  lea     rax, [rbp+57h+var_68]
0x18000cc4b  mov     [rsp+0E0h+var_88], rax
0x18000cc50  lea     rax, [rbp+57h+var_60]
0x18000cc54  mov     [rsp+0E0h+var_90], rax
0x18000cc59  lea     rax, [rbp+57h+var_80]
0x18000cc5d  mov     [rsp+0E0h+var_98], rax
0x18000cc62  lea     rax, [rbp+57h+var_58]
0x18000cc66  mov     [rsp+0E0h+var_A0], rax
0x18000cc6b  lea     rax, [rbp+57h+var_50]
0x18000cc6f  mov     [rsp+0E0h+var_A8], rax
0x18000cc74  lea     rax, [rbp+57h+var_48]
0x18000cc78  mov     [rsp+0E0h+pcbData], rax
0x18000cc7d  lea     rax, [rbp+57h+var_70]
0x18000cc81  mov     [rsp+0E0h+pvData], rax
0x18000cc86  lea     rax, [rbp+57h+var_40]
0x18000cc8a  mov     [rsp+0E0h+pdwType], rax
0x18000cc8f  mov     dword ptr [rbp+57h+var_70], ebx
0x18000cc92  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000cc97  mov     eax, ebx
0x18000cc99  mov     rcx, [rbp+57h+var_18]
0x18000cc9d  xor     rcx, rsp; StackCookie
0x18000cca0  call    __security_check_cookie
0x18000cca5  lea     r11, [rsp+0E0h+var_10]
0x18000ccad  mov     rbx, [r11+28h]
0x18000ccb1  mov     rsi, [r11+30h]
0x18000ccb5  mov     rsp, r11
0x18000ccb8  pop     r14
0x18000ccba  pop     rdi
0x18000ccbb  pop     rbp
0x18000ccbc  retn
0x18000ccbd  mov     ecx, eax; this
0x18000ccbf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
