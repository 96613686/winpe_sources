# DeviceP2PCertificateRequest::GetDeviceAssertionPayloadClaims(KeyValueList &)

- ea: `0x180069c40`
- end: `0x18006a152`
- name: `?GetDeviceAssertionPayloadClaims@DeviceP2PCertificateRequest@@MEAAJAEAVKeyValueList@@@Z`
- size: `1298`
- prototype: `__int64 __fastcall(DeviceP2PCertificateRequest *__hidden this, struct KeyValueList *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180003c20`
- `0x180006380`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x180018ac8`
- `0x18003d390`
- `0x18005b370`
- `0x180069c40`
- `0x18006a158`
- `0x180071e14`
- `0x1800794f0`
- `0x18007953c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069d6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069d6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069dd0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180069cdf`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180069d61`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180069dc6`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180069cdf`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180069d61`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180069dc6`

## string_xrefs

- `0x180069eb2`: `cert_token_use`
- `0x180069ef4`: `http://schemas.microsoft.com/windows/pki/2009/01/enrollment#PKCS10`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DeviceP2PCertificateRequest::GetDeviceAssertionPayloadClaims(
        DeviceP2PCertificateRequest *this,
        struct KeyValueList *a2)
{
  signed int LastError; // eax
  signed int v5; // ecx
  signed int v6; // eax
  signed int v7; // ecx
  signed int v8; // eax
  signed int v9; // ecx
  __int64 v10; // rcx
  WCHAR *v11; // rax
  int v12; // r8d
  int v13; // ecx
  unsigned int v14; // ebx
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  int DeviceAssertionPayloadClaims; // [rsp+60h] [rbp-A0h] BYREF
  DWORD nSize; // [rsp+64h] [rbp-9Ch] BYREF
  __int128 v20; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h]
  __int128 v22; // [rsp+80h] [rbp-80h]
  int v23; // [rsp+90h] [rbp-70h]
  const char *v24[7]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR v25[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR v26[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR Buffer[264]; // [rsp+4F0h] [rbp+3F0h] BYREF

  DeviceAssertionPayloadClaims = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 10;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v24,
    (int)"devicep2pcertificaterequest.cpp",
    (int)"DeviceP2PCertificateRequest::GetDeviceAssertionPayloadClaims",
    (int)&DeviceAssertionPayloadClaims);
  Buffer[0] = 0;
  v26[0] = 0;
  v25[0] = 0;
  nSize = 261;
  if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    DeviceAssertionPayloadClaims = v5;
    if ( v5 < 0 )
      goto LABEL_5;
  }
  nSize = 261;
  if ( !GetComputerNameExW(ComputerNameDnsHostname, v25, &nSize) )
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    DeviceAssertionPayloadClaims = v7;
    if ( v7 < 0 )
      goto LABEL_5;
  }
  nSize = 261;
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, v26, &nSize) )
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    DeviceAssertionPayloadClaims = v9;
    if ( v9 < 0 )
      goto LABEL_5;
  }
  DeviceAssertionPayloadClaims = OAuthTokenRequest::GetDeviceAssertionPayloadClaims(this, a2);
  if ( DeviceAssertionPayloadClaims < 0 )
    goto LABEL_5;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v16,
    (__int64)L"device_auth");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v17,
    (__int64)L"grant_type");
  KeyValueList::Add((__int64)a2, (__int64)&v17, (__int64)&v16);
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v17,
    (__int64)L"device_cert");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v16,
    (__int64)L"cert_token_use");
  KeyValueList::Add((__int64)a2, (__int64)&v16, (__int64)&v17);
  ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v17,
    (__int64)L"http://schemas.microsoft.com/windows/pki/2009/01/enrollment#PKCS10");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v16,
    (__int64)L"csr_type");
  KeyValueList::Add((__int64)a2, (__int64)&v16, (__int64)&v17);
  ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v17,
    *((_QWORD *)this + 25));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v16,
    (__int64)L"csr");
  KeyValueList::Add((__int64)a2, (__int64)&v16, (__int64)&v17);
  ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v17,
    (__int64)Buffer);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v16,
    (__int64)L"netbios_name");
  KeyValueList::Add((__int64)a2, (__int64)&v16, (__int64)&v17);
  ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  if ( !v25[0]
    || (ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          &v20,
          v25),
        DeviceAssertionPayloadClaims = DeviceP2PCertificateRequest::GetIPAddresses(v10, v25, &v20),
        DeviceAssertionPayloadClaims >= 0) )
  {
    if ( v26[0] )
    {
      v11 = v26;
      do
      {
        v12 = *(v11 - 264);
        v13 = *v11 - v12;
        if ( v13 )
          break;
        ++v11;
      }
      while ( v12 );
      if ( v13 )
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          &v20,
          v26);
    }
    if ( v21 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v16,
        (__int64)L"dns_names");
      KeyValueList::Add(a2, &v16, &v20);
      ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v17,
      (__int64)L"10.0.29599.1000");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v16,
      (__int64)L"win_ver");
    KeyValueList::Add((__int64)a2, (__int64)&v16, (__int64)&v17);
    ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  }
  else
  {
LABEL_5:
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws");
  }
  v14 = DeviceAssertionPayloadClaims;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v24);
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v20);
  return v14;
}

```

## disassembly

```asm
0x180069c40  mov     [rsp-8+arg_10], rbx
0x180069c45  mov     [rsp-8+arg_18], rsi
0x180069c4a  push    rbp
0x180069c4b  push    rdi
0x180069c4c  push    r14
0x180069c4e  lea     rbp, [rsp-610h]
0x180069c56  sub     rsp, 710h
0x180069c5d  mov     rax, cs:__security_cookie
0x180069c64  xor     rax, rsp
0x180069c67  mov     [rbp+620h+var_20], rax
0x180069c6e  mov     rbx, rdx
0x180069c71  mov     rdi, rcx
0x180069c74  xor     esi, esi
0x180069c76  mov     [rsp+720h+var_6C0], esi
0x180069c7a  xorps   xmm0, xmm0
0x180069c7d  movdqu  [rsp+720h+var_6B8], xmm0
0x180069c83  mov     [rsp+720h+var_6A8], rsi
0x180069c88  xorps   xmm1, xmm1
0x180069c8b  movdqu  [rbp+620h+var_6A0], xmm1
0x180069c90  mov     [rbp+620h+var_690], 0Ah
0x180069c97  lea     r9, [rsp+720h+var_6C0]
0x180069c9c  lea     r8, aDevicep2pcerti_2; "DeviceP2PCertificateRequest::GetDeviceA"...
0x180069ca3  lea     r14, aOnecoreuapDsEx_35+21h; "devicep2pcertificaterequest.cpp"
0x180069caa  mov     rdx, r14
0x180069cad  lea     rcx, [rbp+620h+var_688]
0x180069cb1  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180069cb6  nop
0x180069cb7  mov     [rbp+620h+Buffer], si
0x180069cbe  mov     [rbp+620h+var_440], si
0x180069cc5  mov     [rbp+620h+var_650], si
0x180069cc9  mov     [rsp+720h+nSize], 105h
0x180069cd1  lea     r8, [rsp+720h+nSize]; nSize
0x180069cd6  lea     rdx, [rbp+620h+Buffer]; lpBuffer
0x180069cdd  xor     ecx, ecx; NameType
0x180069cdf  call    cs:__imp_GetComputerNameExW
0x180069ce5  test    eax, eax
0x180069ce7  jnz     short loc_180069D4B
0x180069ce9  call    cs:__imp_GetLastError
0x180069cef  mov     ecx, eax
0x180069cf1  test    eax, eax
0x180069cf3  jle     short loc_180069CFE
0x180069cf5  movzx   ecx, ax
0x180069cf8  or      ecx, 80070000h
0x180069cfe  mov     [rsp+720h+var_6C0], ecx
0x180069d02  test    ecx, ecx
0x180069d04  jns     short loc_180069D4B
0x180069d06  lea     rax, base
0x180069d0d  mov     [rsp+720h+var_6E0], rax
0x180069d12  lea     rax, aHresult; "HRESULT"
0x180069d19  mov     [rsp+720h+var_6E8], rax
0x180069d1e  mov     [rsp+720h+var_6F0], 28h ; '('
0x180069d26  mov     [rsp+720h+var_6F8], r14
0x180069d2b  mov     [rsp+720h+var_700], ecx
0x180069d2f  mov     r9d, 2
0x180069d35  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180069d3c  xor     edx, edx
0x180069d3e  mov     ecx, r9d
0x180069d41  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180069d46  jmp     loc_18006A111
0x180069d4b  mov     [rsp+720h+nSize], 105h
0x180069d53  lea     r8, [rsp+720h+nSize]; nSize
0x180069d58  lea     rdx, [rbp+620h+var_650]; lpBuffer
0x180069d5c  mov     ecx, 1; NameType
0x180069d61  call    cs:__imp_GetComputerNameExW
0x180069d67  test    eax, eax
0x180069d69  jnz     short loc_180069DAD
0x180069d6b  call    cs:__imp_GetLastError
0x180069d71  mov     ecx, eax
0x180069d73  test    eax, eax
0x180069d75  jle     short loc_180069D80
0x180069d77  movzx   ecx, ax
0x180069d7a  or      ecx, 80070000h
0x180069d80  mov     [rsp+720h+var_6C0], ecx
0x180069d84  test    ecx, ecx
0x180069d86  jns     short loc_180069DAD
0x180069d88  lea     rax, base
0x180069d8f  mov     [rsp+720h+var_6E0], rax
0x180069d94  lea     rax, aHresult; "HRESULT"
0x180069d9b  mov     [rsp+720h+var_6E8], rax
0x180069da0  mov     [rsp+720h+var_6F0], 2Eh ; '.'
0x180069da8  jmp     loc_180069D26
0x180069dad  mov     [rsp+720h+nSize], 105h
0x180069db5  lea     r8, [rsp+720h+nSize]; nSize
0x180069dba  lea     rdx, [rbp+620h+var_440]; lpBuffer
0x180069dc1  mov     ecx, 3; NameType
0x180069dc6  call    cs:__imp_GetComputerNameExW
0x180069dcc  test    eax, eax
0x180069dce  jnz     short loc_180069E12
0x180069dd0  call    cs:__imp_GetLastError
0x180069dd6  mov     ecx, eax
0x180069dd8  test    eax, eax
0x180069dda  jle     short loc_180069DE5
0x180069ddc  movzx   ecx, ax
0x180069ddf  or      ecx, 80070000h
0x180069de5  mov     [rsp+720h+var_6C0], ecx
0x180069de9  test    ecx, ecx
0x180069deb  jns     short loc_180069E12
0x180069ded  lea     rax, base
0x180069df4  mov     [rsp+720h+var_6E0], rax
0x180069df9  lea     rax, aHresult; "HRESULT"
0x180069e00  mov     [rsp+720h+var_6E8], rax
0x180069e05  mov     [rsp+720h+var_6F0], 34h ; '4'
0x180069e0d  jmp     loc_180069D26
0x180069e12  mov     rdx, rbx; struct KeyValueList *
0x180069e15  mov     rcx, rdi; this
0x180069e18  call    ?GetDeviceAssertionPayloadClaims@OAuthTokenRequest@@MEAAJAEAVKeyValueList@@@Z; OAuthTokenRequest::GetDeviceAssertionPayloadClaims(KeyValueList &)
0x180069e1d  mov     ecx, eax
0x180069e1f  mov     [rsp+720h+var_6C0], eax
0x180069e23  test    eax, eax
0x180069e25  jns     short loc_180069E4C
0x180069e27  lea     rax, base
0x180069e2e  mov     [rsp+720h+var_6E0], rax
0x180069e33  lea     rax, aHresult; "HRESULT"
0x180069e3a  mov     [rsp+720h+var_6E8], rax
0x180069e3f  mov     [rsp+720h+var_6F0], 37h ; '7'
0x180069e47  jmp     loc_180069D26
0x180069e4c  lea     rdx, aDeviceAuth; "device_auth"
0x180069e53  lea     rcx, [rsp+720h+var_6D0]
0x180069e58  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180069e5d  nop
0x180069e5e  lea     rdx, aGrantType; "grant_type"
0x180069e65  lea     rcx, [rsp+720h+var_6C8]
0x180069e6a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180069e6f  nop
0x180069e70  lea     r8, [rsp+720h+var_6D0]
0x180069e75  lea     rdx, [rsp+720h+var_6C8]
0x180069e7a  mov     rcx, rbx
0x180069e7d  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180069e82  nop
0x180069e83  mov     rcx, [rsp+720h+var_6C8]
0x180069e88  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180069e8c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180069e91  nop
0x180069e92  mov     rcx, [rsp+720h+var_6D0]
0x180069e97  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180069e9b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180069ea0  lea     rdx, aDeviceCert; "device_cert"
0x180069ea7  lea     rcx, [rsp+720h+var_6C8]
0x180069eac  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180069eb1  nop
0x180069eb2  lea     rdx, aCertTokenUse; "cert_token_use"
0x180069eb9  lea     rcx, [rsp+720h+var_6D0]
0x180069ebe  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180069ec3  nop
0x180069ec4  lea     r8, [rsp+720h+var_6C8]
0x180069ec9  lea     rdx, [rsp+720h+var_6D0]
0x180069ece  mov     rcx, rbx
0x180069ed1  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180069ed6  nop
0x180069ed7  mov     rcx, [rsp+720h+var_6D0]
0x180069edc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180069ee0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180069ee5  nop
0x180069ee6  mov     rcx, [rsp+720h+var_6C8]
0x180069eeb  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180069eef  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180069ef4  lea     rdx, aHttpSchemasMic_1; "http://schemas.microsoft.com/windows/pk"...
0x180069efb  lea     rcx, [rsp+720h+var_6C8]
0x180069f00  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180069f05  nop
0x180069f06  lea     rdx, aCsrType; "csr_type"
0x180069f0d  lea     rcx, [rsp+720h+var_6D0]
0x180069f12  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180069f17  nop
0x180069f18  lea     r8, [rsp+720h+var_6C8]
0x180069f1d  lea     rdx, [rsp+720h+var_6D0]
0x180069f22  mov     rcx, rbx
0x180069f25  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180069f2a  nop
0x180069f2b  mov     rcx, [rsp+720h+var_6D0]
0x180069f30  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180069f34  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180069f39  nop
0x180069f3a  mov     rcx, [rsp+720h+var_6C8]
0x180069f3f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180069f43  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180069f48  mov     rdx, [rdi+0C8h]
0x180069f4f  lea     rcx, [rsp+720h+var_6C8]
0x180069f54  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180069f59  nop
0x180069f5a  lea     rdx, aCsr; "csr"
0x180069f61  lea     rcx, [rsp+720h+var_6D0]
0x180069f66  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180069f6b  nop
0x180069f6c  lea     r8, [rsp+720h+var_6C8]
0x180069f71  lea     rdx, [rsp+720h+var_6D0]
0x180069f76  mov     rcx, rbx
0x180069f79  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180069f7e  nop
0x180069f7f  mov     rcx, [rsp+720h+var_6D0]
0x180069f84  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180069f88  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180069f8d  nop
0x180069f8e  mov     rcx, [rsp+720h+var_6C8]
0x180069f93  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180069f97  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180069f9c  lea     rdx, [rbp+620h+Buffer]
0x180069fa3  lea     rcx, [rsp+720h+var_6C8]
0x180069fa8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180069fad  nop
0x180069fae  lea     rdx, aNetbiosName; "netbios_name"
0x180069fb5  lea     rcx, [rsp+720h+var_6D0]
0x180069fba  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180069fbf  nop
0x180069fc0  lea     r8, [rsp+720h+var_6C8]
0x180069fc5  lea     rdx, [rsp+720h+var_6D0]
0x180069fca  mov     rcx, rbx
0x180069fcd  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180069fd2  nop
0x180069fd3  mov     rcx, [rsp+720h+var_6D0]
0x180069fd8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180069fdc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180069fe1  nop
0x180069fe2  mov     rcx, [rsp+720h+var_6C8]
0x180069fe7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180069feb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180069ff0  cmp     [rbp+620h+var_650], si
0x180069ff4  jz      short loc_18006A041
0x180069ff6  lea     rdx, [rbp+620h+var_650]
0x180069ffa  lea     rcx, [rsp+720h+var_6B8]
0x180069fff  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x18006a004  lea     r8, [rsp+720h+var_6B8]
0x18006a009  lea     rdx, [rbp+620h+var_650]
0x18006a00d  call    ?GetIPAddresses@DeviceP2PCertificateRequest@@AEAAJPEBGAEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; DeviceP2PCertificateRequest::GetIPAddresses(ushort const *,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x18006a012  mov     ecx, eax
0x18006a014  mov     [rsp+720h+var_6C0], eax
0x18006a018  test    eax, eax
0x18006a01a  jns     short loc_18006A041
0x18006a01c  lea     rax, base
0x18006a023  mov     [rsp+720h+var_6E0], rax
0x18006a028  lea     rax, aHresult; "HRESULT"
0x18006a02f  mov     [rsp+720h+var_6E8], rax
0x18006a034  mov     [rsp+720h+var_6F0], 43h ; 'C'
0x18006a03c  jmp     loc_180069D26
0x18006a041  cmp     [rbp+620h+var_440], si
0x18006a048  jz      short loc_18006A083
0x18006a04a  lea     rax, [rbp+620h+var_440]
0x18006a051  lea     rdx, [rbp+620h+var_650]
0x18006a055  sub     rdx, rax
0x18006a058  movzx   ecx, word ptr [rax]
0x18006a05b  movzx   r8d, word ptr [rax+rdx]
0x18006a060  sub     ecx, r8d
0x18006a063  jnz     short loc_18006A06E
0x18006a065  add     rax, 2
0x18006a069  test    r8d, r8d
0x18006a06c  jnz     short loc_18006A058
0x18006a06e  test    ecx, ecx
0x18006a070  jz      short loc_18006A083
0x18006a072  lea     rdx, [rbp+620h+var_440]
0x18006a079  lea     rcx, [rsp+720h+var_6B8]
0x18006a07e  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x18006a083  cmp     [rsp+720h+var_6A8], rsi
0x18006a088  jz      short loc_18006A0BD
0x18006a08a  lea     rdx, aDnsNames; "dns_names"
0x18006a091  lea     rcx, [rsp+720h+var_6D0]
0x18006a096  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18006a09b  nop
0x18006a09c  lea     r8, [rsp+720h+var_6B8]
0x18006a0a1  lea     rdx, [rsp+720h+var_6D0]
0x18006a0a6  mov     rcx, rbx
0x18006a0a9  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x18006a0ae  nop
0x18006a0af  mov     rcx, [rsp+720h+var_6D0]
0x18006a0b4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18006a0b8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18006a0bd  lea     rdx, a100295991000; "10.0.29599.1000"
0x18006a0c4  lea     rcx, [rsp+720h+var_6C8]
0x18006a0c9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18006a0ce  nop
0x18006a0cf  lea     rdx, aWinVer; "win_ver"
0x18006a0d6  lea     rcx, [rsp+720h+var_6D0]
0x18006a0db  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18006a0e0  nop
0x18006a0e1  lea     r8, [rsp+720h+var_6C8]
0x18006a0e6  lea     rdx, [rsp+720h+var_6D0]
0x18006a0eb  mov     rcx, rbx
0x18006a0ee  call    ?Add@KeyValueList@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; KeyValueList::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18006a0f3  nop
0x18006a0f4  mov     rcx, [rsp+720h+var_6D0]
0x18006a0f9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18006a0fd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18006a102  nop
0x18006a103  mov     rcx, [rsp+720h+var_6C8]
0x18006a108  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18006a10c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18006a111  mov     ebx, [rsp+720h+var_6C0]
0x18006a115  lea     rcx, [rbp+620h+var_688]
0x18006a119  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18006a11e  nop
0x18006a11f  lea     rcx, [rsp+720h+var_6B8]
0x18006a124  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x18006a129  mov     eax, ebx
0x18006a12b  mov     rcx, [rbp+620h+var_20]
0x18006a132  xor     rcx, rsp; StackCookie
0x18006a135  call    __security_check_cookie
0x18006a13a  lea     r11, [rsp+720h+var_10]
0x18006a142  mov     rbx, [r11+30h]
0x18006a146  mov     rsi, [r11+38h]
0x18006a14a  mov     rsp, r11
0x18006a14d  pop     r14
  ... truncated ...
```
