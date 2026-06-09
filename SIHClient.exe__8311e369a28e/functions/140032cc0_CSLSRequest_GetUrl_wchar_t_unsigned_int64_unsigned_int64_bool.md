# CSLSRequest::GetUrl(wchar_t *,unsigned __int64,unsigned __int64 *,bool *)

- ea: `0x140032cc0`
- end: `0x140032fca`
- name: `?GetUrl@CSLSRequest@@QEBAJPEA_W_KPEA_KPEA_N@Z`
- size: `778`
- prototype: `__int64 __fastcall(const wchar_t **this, wchar_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14003401c`

## callees

- `0x140003de4`
- `0x140007610`
- `0x1400154b4`
- `0x140017934`
- `0x140017bd0`
- `0x140018170`
- `0x140018394`
- `0x14002e080`
- `0x140032cc0`
- `0x140032fd0`
- `0x140033160`
- `0x140045dc0`
- `0x14004cc90`
- `0x14004cd80`

## string_xrefs

- `0x140032d71`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x140032ed0`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x140032ec9`: `SLSWriteRequestToRegistry`
- `0x140032e50`: `tas02.sls.update.microsoft.com`
- `0x140032e59`: `slscr.update.microsoft.com`
- `0x140032f2f`: `Failed to set String value in registry for key %ws/%ws and url =>%ws<=CSLSRequest::GetUrl`

## pseudocode

```c
__int64 __fastcall CSLSRequest::GetUrl(const wchar_t **this, wchar_t *a2, __int64 a3, unsigned __int64 *a4, bool *a5)
{
  wchar_t *v6; // rdi
  signed int v8; // ebx
  CSLSRequest *v9; // rcx
  __int64 v10; // r9
  const wchar_t *v11; // rax
  bool v12; // zf
  CSLSRequest *v13; // rcx
  const wchar_t *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  wchar_t **v18; // r9
  __int64 RegKeyPath; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  wchar_t **v22; // r9
  __int64 v23; // rcx
  unsigned int v25; // [rsp+30h] [rbp-D0h]
  unsigned int v26[2]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v27; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v28[8]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v29[2088]; // [rsp+70h] [rbp-90h] BYREF

  v27 = a2;
  wcscpy(v28, L"://");
  *(_QWORD *)v26 = 2085;
  v6 = a2;
  if ( a2 && a4 )
  {
    *a4 = 0;
    memset(v29, 0, 0x104Au);
    if ( (unsigned int)AreTestKeysAllowed()
      && (int)RegQueryStringValue(
                v9,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                L"SLSFixedURL",
                v29,
                2085) >= 0 )
    {
      v8 = StringCchCatW(v6, 0x825u, v29);
      v10 = 4;
      v11 = L"Test override Fixed URL ==>%ws<== - ";
LABEL_14:
      WUTrace(0, 0, 4, v10, 0, v11);
      goto LABEL_15;
    }
    v8 = CSLSRequest::AppendFromTestKeyOverrideWithDefault(
           v9,
           v6,
           0x825u,
           L"SLSScheme",
           L"HTTPS",
           &v27,
           (unsigned __int64 *)v26,
           a5);
    if ( v8 >= 0 )
    {
      v8 = StringCchCatNExW(v27, *(unsigned __int64 *)v26, v28, 4u, &v27, (unsigned __int64 *)v26, v25);
      if ( v8 >= 0 )
      {
        v12 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl) == 0;
        v14 = L"tas02.sls.update.microsoft.com";
        if ( v12 )
          v14 = L"slscr.update.microsoft.com";
        v8 = CSLSRequest::AppendFromTestKeyOverrideWithDefault(
               v13,
               v27,
               *(unsigned __int64 *)v26,
               L"SLSHost",
               v14,
               &v27,
               (unsigned __int64 *)v26,
               0);
        if ( v8 >= 0 )
        {
          v8 = StringCchCatW(v27, *(unsigned __int64 *)v26, this[4]);
          if ( v8 >= 0 )
          {
            v11 = L"URL ==>%ws<== - CSLSRequest::GetUrl";
            v10 = 5;
            goto LABEL_14;
          }
        }
      }
    }
  }
  else
  {
    v8 = -2147467261;
  }
LABEL_15:
  if ( (unsigned int)AreTestKeysAllowed() )
  {
    if ( (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                         v15,
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                         L"SLSWriteRequestToRegistry",
                         0) == 1 )
    {
      RegKeyPath = GetRegKeyPath(17, v16, v17, v18);
      if ( (int)RegSetStringValue(-2147483646, RegKeyPath, (__int64)L"Request", (__int64)v6) < 0 )
      {
        GetRegKeyPath(17, v20, v21, v22);
        WUTrace(
          0,
          0,
          4,
          3,
          0,
          L"Failed to set String value in registry for key %ws/%ws and url =>%ws<=CSLSRequest::GetUrl");
      }
    }
  }
  if ( v8 >= 0 )
  {
    if ( !v6 )
    {
      v8 = -2147024809;
LABEL_31:
      if ( a4 )
        *a4 = 0;
      return (unsigned int)v8;
    }
    v23 = 2085;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v23;
    }
    while ( v23 );
    v8 = v23 == 0 ? 0x80070057 : 0;
    if ( a4 )
    {
      if ( v23 )
        *a4 = 2085 - v23;
      else
        *a4 = 0;
    }
    if ( !v23 )
      goto LABEL_31;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140032cc0  mov     [rsp-8+arg_0], rbx
0x140032cc5  push    rbp
0x140032cc6  push    rsi
0x140032cc7  push    rdi
0x140032cc8  push    r12
0x140032cca  push    r13
0x140032ccc  push    r14
0x140032cce  push    r15
0x140032cd0  lea     rbp, [rsp-0FD0h]
0x140032cd8  mov     eax, 10D0h
0x140032cdd  call    _alloca_probe
0x140032ce2  sub     rsp, rax
0x140032ce5  mov     rax, cs:__security_cookie
0x140032cec  xor     rax, rsp
0x140032cef  mov     [rbp+1000h+var_40], rax
0x140032cf6  mov     rbx, [rbp+1000h+arg_20]
0x140032cfd  xor     r12d, r12d
0x140032d00  mov     [rsp+1100h+var_10A8], rdx
0x140032d05  mov     rax, 2F002F003Ah
0x140032d0f  mov     qword ptr [rsp+1100h+var_10A0], rax
0x140032d14  mov     r14d, 825h
0x140032d1a  mov     qword ptr [rsp+1100h+var_10B0], r14
0x140032d1f  mov     rsi, r9
0x140032d22  mov     rdi, rdx
0x140032d25  mov     r15, rcx
0x140032d28  mov     r13d, 4
0x140032d2e  test    rdx, rdx
0x140032d31  jnz     short loc_140032D3D
0x140032d33  mov     ebx, 80004003h
0x140032d38  jmp     loc_140032EB1
0x140032d3d  test    rsi, rsi
0x140032d40  jz      short loc_140032D33
0x140032d42  xor     edx, edx; Val
0x140032d44  mov     [r9], r12
0x140032d47  mov     r8d, 104Ah; Size
0x140032d4d  lea     rcx, [rsp+1100h+var_1090]; void *
0x140032d52  call    memset
0x140032d57  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x140032d5c  test    eax, eax
0x140032d5e  jz      short loc_140032DA2
0x140032d60  lea     r9, [rsp+1100h+var_1090]
0x140032d65  mov     dword ptr [rsp+1100h+var_10E0], r14d
0x140032d6a  lea     r8, ?c_szRegSLSFixedURL@@3QB_WB; "SLSFixedURL"
0x140032d71  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140032d78  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEA_WKW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong,RegistryHiveType)
0x140032d7d  test    eax, eax
0x140032d7f  js      short loc_140032DA2
0x140032d81  lea     r8, [rsp+1100h+var_1090]; wchar_t *
0x140032d86  mov     rdx, r14; unsigned __int64
0x140032d89  mov     rcx, rdi; wchar_t *
0x140032d8c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140032d91  mov     ebx, eax
0x140032d93  mov     r9d, r13d
0x140032d96  lea     rax, aTestOverrideFi; "Test override Fixed URL ==>%ws<== - "
0x140032d9d  jmp     loc_140032E96
0x140032da2  mov     [rsp+1100h+var_10C8], rbx; bool *
0x140032da7  lea     rax, [rsp+1100h+var_10B0]
0x140032dac  mov     [rsp+1100h+var_10D0], rax; unsigned int
0x140032db1  lea     r9, ?c_szRegSLSScheme@@3QB_WB; "SLSScheme"
0x140032db8  lea     rax, [rsp+1100h+var_10A8]
0x140032dbd  mov     r8, r14; unsigned __int64
0x140032dc0  mov     [rsp+1100h+var_10D8], rax; wchar_t **
0x140032dc5  mov     rdx, rdi; wchar_t *
0x140032dc8  lea     rax, aHttps; "HTTPS"
0x140032dcf  mov     [rsp+1100h+var_10E0], rax; wchar_t *
0x140032dd4  call    ?AppendFromTestKeyOverrideWithDefault@CSLSRequest@@AEBAJPEA_W_KPEB_W2PEAPEA_WPEA_KPEA_N@Z; CSLSRequest::AppendFromTestKeyOverrideWithDefault(wchar_t *,unsigned __int64,wchar_t const *,wchar_t const *,wchar_t * *,unsigned __int64 *,bool *)
0x140032dd9  mov     ebx, eax
0x140032ddb  test    eax, eax
0x140032ddd  js      loc_140032EB1
0x140032de3  mov     rdx, qword ptr [rsp+1100h+var_10B0]; unsigned __int64
0x140032de8  lea     rax, [rsp+1100h+var_10B0]
0x140032ded  mov     rcx, [rsp+1100h+var_10A8]; wchar_t *
0x140032df2  lea     r8, [rsp+1100h+var_10A0]; wchar_t *
0x140032df7  mov     [rsp+1100h+var_10D8], rax; unsigned __int64 *
0x140032dfc  mov     r9, r13; unsigned __int64
0x140032dff  lea     rax, [rsp+1100h+var_10A8]
0x140032e04  mov     [rsp+1100h+var_10E0], rax; wchar_t **
0x140032e09  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140032e0e  mov     ebx, eax
0x140032e10  test    eax, eax
0x140032e12  js      loc_140032EB1
0x140032e18  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x140032e1f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x140032e24  mov     r8, qword ptr [rsp+1100h+var_10B0]; unsigned __int64
0x140032e29  lea     r9, ?c_szRegSLSHost@@3QB_WB; "SLSHost"
0x140032e30  mov     rdx, [rsp+1100h+var_10A8]; wchar_t *
0x140032e35  test    al, al
0x140032e37  lea     rax, [rsp+1100h+var_10B0]
0x140032e3c  mov     [rsp+1100h+var_10C8], r12; bool *
0x140032e41  mov     [rsp+1100h+var_10D0], rax; unsigned __int64 *
0x140032e46  lea     rax, [rsp+1100h+var_10A8]
0x140032e4b  mov     [rsp+1100h+var_10D8], rax; wchar_t **
0x140032e50  lea     rax, aTas02SlsUpdate; "tas02.sls.update.microsoft.com"
0x140032e57  jnz     short loc_140032E60
0x140032e59  lea     rax, aSlscrUpdateMic; "slscr.update.microsoft.com"
0x140032e60  mov     [rsp+1100h+var_10E0], rax; wchar_t *
0x140032e65  call    ?AppendFromTestKeyOverrideWithDefault@CSLSRequest@@AEBAJPEA_W_KPEB_W2PEAPEA_WPEA_KPEA_N@Z; CSLSRequest::AppendFromTestKeyOverrideWithDefault(wchar_t *,unsigned __int64,wchar_t const *,wchar_t const *,wchar_t * *,unsigned __int64 *,bool *)
0x140032e6a  mov     ebx, eax
0x140032e6c  test    eax, eax
0x140032e6e  js      short loc_140032EB1
0x140032e70  mov     r8, [r15+20h]; wchar_t *
0x140032e74  mov     rdx, qword ptr [rsp+1100h+var_10B0]; unsigned __int64
0x140032e79  mov     rcx, [rsp+1100h+var_10A8]; wchar_t *
0x140032e7e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140032e83  mov     ebx, eax
0x140032e85  test    eax, eax
0x140032e87  js      short loc_140032EB1
0x140032e89  lea     rax, aUrlWsCslsreque; "URL ==>%ws<== - CSLSRequest::GetUrl"
0x140032e90  mov     r9d, 5
0x140032e96  mov     [rsp+1100h+var_10D0], rdi
0x140032e9b  mov     r8d, r13d
0x140032e9e  mov     [rsp+1100h+var_10D8], rax
0x140032ea3  xor     edx, edx
0x140032ea5  xor     ecx, ecx
0x140032ea7  mov     [rsp+1100h+var_10E0], r12
0x140032eac  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140032eb1  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x140032eb6  test    eax, eax
0x140032eb8  jz      loc_140032F49
0x140032ebe  xor     r9d, r9d
0x140032ec1  mov     dword ptr [rsp+1100h+var_10D8], 0FFFFFFFFh
0x140032ec9  lea     r8, ?c_szRegSLSWriteRequestToRegistry@@3QB_WB; "SLSWriteRequestToRegistry"
0x140032ed0  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140032ed7  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x140032edc  cmp     eax, 1
0x140032edf  jnz     short loc_140032F49
0x140032ee1  lea     r15d, [rax+10h]
0x140032ee5  mov     ecx, r15d
0x140032ee8  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x140032eed  mov     rdx, rax
0x140032ef0  lea     r8, ?c_szRegSLSRequest@@3QB_WB; "Request"
0x140032ef7  mov     r9, rdi
0x140032efa  mov     rcx, 0FFFFFFFF80000002h
0x140032f01  call    ?RegSetStringValue@@YAJPEAUHKEY__@@PEB_W11W4RegistryHiveType@@@Z; RegSetStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x140032f06  test    eax, eax
0x140032f08  jns     short loc_140032F49
0x140032f0a  mov     ecx, r15d
0x140032f0d  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x140032f12  mov     [rsp+1100h+var_10C0], rdi
0x140032f17  lea     rcx, ?c_szRegSLSRequest@@3QB_WB; "Request"
0x140032f1e  mov     [rsp+1100h+var_10C8], rcx
0x140032f23  lea     r9d, [r15-0Eh]
0x140032f27  mov     [rsp+1100h+var_10D0], rax
0x140032f2c  mov     r8d, r13d
0x140032f2f  lea     rax, aFailedToSetStr; "Failed to set String value in registry "...
0x140032f36  xor     edx, edx
0x140032f38  mov     [rsp+1100h+var_10D8], rax
0x140032f3d  xor     ecx, ecx
0x140032f3f  mov     [rsp+1100h+var_10E0], r12
0x140032f44  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140032f49  test    ebx, ebx
0x140032f4b  js      short loc_140032F9E
0x140032f4d  test    rdi, rdi
0x140032f50  jz      short loc_140032F91
0x140032f52  mov     rcx, r14
0x140032f55  cmp     [rdi], r12w
0x140032f59  jz      short loc_140032F65
0x140032f5b  add     rdi, 2
0x140032f5f  sub     rcx, 1
0x140032f63  jnz     short loc_140032F55
0x140032f65  mov     rax, rcx
0x140032f68  neg     rax
0x140032f6b  sbb     ebx, ebx
0x140032f6d  not     ebx
0x140032f6f  and     ebx, 80070057h
0x140032f75  test    rsi, rsi
0x140032f78  jz      short loc_140032F8A
0x140032f7a  test    rcx, rcx
0x140032f7d  jz      short loc_140032F87
0x140032f7f  sub     r14, rcx
0x140032f82  mov     [rsi], r14
0x140032f85  jmp     short loc_140032F8A
0x140032f87  mov     [rsi], r12
0x140032f8a  test    rcx, rcx
0x140032f8d  jnz     short loc_140032F9E
0x140032f8f  jmp     short loc_140032F96
0x140032f91  mov     ebx, 80070057h
0x140032f96  test    rsi, rsi
0x140032f99  jz      short loc_140032F9E
0x140032f9b  mov     [rsi], r12
0x140032f9e  mov     eax, ebx
0x140032fa0  mov     rcx, [rbp+1000h+var_40]
0x140032fa7  xor     rcx, rsp; StackCookie
0x140032faa  call    __security_check_cookie
0x140032faf  mov     rbx, [rsp+1100h+arg_0]
0x140032fb7  add     rsp, 10D0h
0x140032fbe  pop     r15
0x140032fc0  pop     r14
0x140032fc2  pop     r13
0x140032fc4  pop     r12
0x140032fc6  pop     rdi
0x140032fc7  pop     rsi
0x140032fc8  pop     rbp
0x140032fc9  retn
```
