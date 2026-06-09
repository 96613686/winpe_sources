# CConnectedSearchTransport::CConnectedEndpoint::_EnsureInitialized(void)

- ea: `0x1801b9bc8`
- end: `0x1801b9f87`
- name: `?_EnsureInitialized@CConnectedEndpoint@CConnectedSearchTransport@@AEAAJXZ`
- size: `959`
- prototype: `__int64 __fastcall(CConnectedSearchTransport::CConnectedEndpoint *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801b9418`
- `0x1801b9640`

## callees

- `0x18000e2b0`
- `0x18002fc18`
- `0x180041f54`
- `0x180062eac`
- `0x18006a010`
- `0x180076bec`
- `0x1801579d0`
- `0x1801b1db0`
- `0x1801b9bc8`
- `0x1801ba658`
- `0x1801ba8b8`
- `0x1801baa44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b9e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b9ea6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b9ed3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b9e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b9ea6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b9ed3`
- `WININET!InternetSetOptionW` at `0x1801b9dcc`
- `WININET!InternetSetOptionW` at `0x1801b9dcc`
- `WININET!InternetCloseHandle` at `0x1801b9e31`
- `WININET!InternetCloseHandle` at `0x1801b9e31`
- `WININET!InternetOpenW` at `0x1801b9d91`
- `WININET!InternetOpenW` at `0x1801b9d91`
- `WININET!InternetConnectW` at `0x1801b9e0f`
- `WININET!InternetConnectW` at `0x1801b9e0f`

## pseudocode

```c
__int64 __fastcall CConnectedSearchTransport::CConnectedEndpoint::_EnsureInitialized(
        CConnectedSearchTransport::CConnectedEndpoint *this)
{
  int UrlParts; // edi
  __int64 v3; // r9
  __int64 v4; // r9
  __int64 v5; // rdx
  const WCHAR *v6; // r15
  int v7; // eax
  INTERNET_PORT v8; // r14
  LPCWSTR v9; // r13
  void *v10; // rsi
  LPCWSTR v11; // r12
  HINTERNET v12; // r14
  void *v13; // rcx
  unsigned __int16 *v14; // rsi
  void *v15; // rcx
  void *v16; // rcx
  unsigned int v17; // eax
  LPCWSTR lpszServerName; // [rsp+40h] [rbp-69h] BYREF
  __int64 v20; // [rsp+48h] [rbp-61h]
  __int64 v21; // [rsp+50h] [rbp-59h]
  LPCWSTR pwzURI; // [rsp+58h] [rbp-51h] BYREF
  __int64 v23; // [rsp+60h] [rbp-49h]
  __int64 v24; // [rsp+68h] [rbp-41h]
  unsigned __int16 *v25; // [rsp+70h] [rbp-39h] BYREF
  __int64 v26; // [rsp+78h] [rbp-31h]
  __int64 v27; // [rsp+80h] [rbp-29h]
  LPCWSTR lpszAgent; // [rsp+88h] [rbp-21h] BYREF
  __int64 v29; // [rsp+90h] [rbp-19h]
  __int64 v30; // [rsp+98h] [rbp-11h]
  _QWORD v31[12]; // [rsp+A0h] [rbp-9h] BYREF
  unsigned int v32; // [rsp+110h] [rbp+67h] BYREF
  int Buffer; // [rsp+118h] [rbp+6Fh] BYREF
  char v34; // [rsp+120h] [rbp+77h] BYREF
  char v35; // [rsp+128h] [rbp+7Fh] BYREF

  UrlParts = 0;
  wil::AcquireSRWLockExclusive(&v35, (char *)this + 16);
  if ( !*((_BYTE *)this + 24) )
  {
    v3 = 200LL * *(unsigned int *)this;
    memset(v31, 0, 24);
    pwzURI = 0;
    v4 = *(__int64 *)((char *)&CConnectedSearchTransport::s_rgEndpointRegMap + v3 + 32);
    v23 = 0;
    v24 = 0;
    if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                v31,
                -2147483646,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\ConnectedSearch",
                v4) < 0 )
      v5 = (__int64)*(&CConnectedSearchTransport::s_rgEndpointRegMap + 25 * *(unsigned int *)this);
    else
      v5 = v31[0];
    UrlParts = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                 &pwzURI,
                 v5,
                 -1);
    if ( UrlParts < 0 )
      goto LABEL_34;
    lpszServerName = 0;
    v20 = 0;
    v21 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpszServerName);
    v6 = pwzURI;
    v20 = -1;
    v21 = -1;
    if ( CConnectedSearchTransport::CConnectedEndpoint::_UpdateDomain(
           this,
           pwzURI,
           (unsigned __int16 **)&lpszServerName) >= 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pwzURI);
      v23 = -1;
      v24 = -1;
      v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CopyTo(
             &lpszServerName,
             &pwzURI);
      v6 = pwzURI;
      UrlParts = v7;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpszServerName);
    if ( UrlParts < 0 )
      goto LABEL_34;
    lpszServerName = 0;
    v20 = 0;
    v21 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v32 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v25);
    v26 = -1;
    v27 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpszServerName);
    v20 = -1;
    v21 = -1;
    UrlParts = CConnectedSearchTransport::CConnectedEndpoint::s_GetUrlParts(
                 v6,
                 &v32,
                 (unsigned __int16 **)&lpszServerName,
                 &v25);
    if ( UrlParts < 0 )
    {
LABEL_33:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v25);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpszServerName);
LABEL_34:
      *((_BYTE *)this + 24) = UrlParts >= 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pwzURI);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v31);
      goto LABEL_35;
    }
    v8 = 443;
    if ( v32 != 11 )
      v8 = 80;
    lpszAgent = 0;
    v29 = 0;
    v30 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpszAgent);
    v29 = -1;
    v30 = -1;
    UrlParts = CConnectedSearchTransport::s_GetUserAgentString((unsigned __int16 **)&lpszAgent);
    if ( UrlParts < 0
      || (v9 = lpszAgent, (v10 = InternetOpenW(lpszAgent, 0, 0, 0, 0)) == 0)
      && (UrlParts = ResultFromKnownLastError(), UrlParts < 0) )
    {
LABEL_32:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpszAgent);
      goto LABEL_33;
    }
    Buffer = 1;
    if ( InternetSetOptionW(v10, 0x41u, &Buffer, 4u) || (UrlParts = ResultFromKnownLastError(), UrlParts >= 0) )
    {
      v11 = lpszServerName;
      v12 = InternetConnectW(v10, lpszServerName, v8, 0, 0, 3u, 0, 0);
      if ( v12 )
      {
        UrlParts = 0;
      }
      else
      {
        UrlParts = ResultFromKnownLastError();
        if ( UrlParts < 0 )
          goto LABEL_19;
      }
      wil::AcquireSRWLockExclusive(&v34, (char *)this + 32);
      *((_QWORD *)this + 5) = v12;
      *((_QWORD *)this + 1) = v10;
      v13 = (void *)*((_QWORD *)this + 7);
      pwzURI = 0;
      v24 = 0;
      v23 = 0;
      if ( v13 )
        CoTaskMemFree(v13);
      v14 = v25;
      *((_QWORD *)this + 7) = v6;
      *((_QWORD *)this + 9) = -1;
      *((_QWORD *)this + 8) = -1;
      v15 = (void *)*((_QWORD *)this + 10);
      v25 = 0;
      v27 = 0;
      v26 = 0;
      if ( v15 )
        CoTaskMemFree(v15);
      *((_QWORD *)this + 10) = v14;
      *((_QWORD *)this + 12) = -1;
      *((_QWORD *)this + 11) = -1;
      v16 = (void *)*((_QWORD *)this + 13);
      lpszServerName = 0;
      v21 = 0;
      v20 = 0;
      if ( v16 )
        CoTaskMemFree(v16);
      v17 = v32;
      *((_QWORD *)this + 13) = v11;
      *((_QWORD *)this + 15) = -1;
      *((_QWORD *)this + 14) = -1;
      *((_DWORD *)this + 32) = v17;
      if ( v17 == 11 )
        *((_DWORD *)this + 12) |= 0x800000u;
      if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
        McTemplateU0qzzz_EventWriteTransfer(
          (_DWORD)v16,
          (unsigned int)ConnectedSearch_ConnectionEstablished,
          *(_DWORD *)this,
          0,
          *((_QWORD *)this + 10),
          (__int64)v9);
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v34);
      goto LABEL_32;
    }
LABEL_19:
    InternetCloseHandle(v10);
    goto LABEL_32;
  }
LABEL_35:
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v35);
  return (unsigned int)UrlParts;
}

```

## disassembly

```asm
0x1801b9bc8  push    rbp
0x1801b9bca  push    rbx
0x1801b9bcb  push    rsi
0x1801b9bcc  push    rdi
0x1801b9bcd  push    r12
0x1801b9bcf  push    r13
0x1801b9bd1  push    r14
0x1801b9bd3  push    r15
0x1801b9bd5  lea     rbp, [rsp-1Fh]
0x1801b9bda  sub     rsp, 0C8h
0x1801b9be1  mov     rbx, rcx
0x1801b9be4  lea     rdx, [rcx+10h]
0x1801b9be8  xor     r12d, r12d
0x1801b9beb  lea     rcx, [rbp+57h+arg_18]
0x1801b9bef  mov     edi, r12d
0x1801b9bf2  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801b9bf7  cmp     [rbx+18h], r12b
0x1801b9bfb  jnz     loc_1801B9F67
0x1801b9c01  mov     eax, [rbx]
0x1801b9c03  lea     rdi, ?s_rgEndpointRegMap@CConnectedSearchTransport@@0PAUHTTP_ENDPOINT_REGISTRATION@1@A; CConnectedSearchTransport::HTTP_ENDPOINT_REGISTRATION near * CConnectedSearchTransport::s_rgEndpointRegMap
0x1801b9c0a  imul    r9, rax, 0C8h
0x1801b9c11  lea     r8, aSoftwareMicros_80; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801b9c18  mov     [rbp+57h+var_60], r12
0x1801b9c1c  mov     rdx, 0FFFFFFFF80000002h
0x1801b9c23  mov     [rbp+57h+var_58], r12
0x1801b9c27  lea     rcx, [rbp+57h+var_60]
0x1801b9c2b  mov     [rbp+57h+var_50], r12
0x1801b9c2f  mov     [rbp+57h+pwzURI], r12
0x1801b9c33  mov     r9, [r9+rdi+20h]
0x1801b9c38  mov     [rbp+57h+var_A0], r12
0x1801b9c3c  mov     [rbp+57h+var_98], r12
0x1801b9c40  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x1801b9c45  test    eax, eax
0x1801b9c47  js      short loc_1801B9C4F
0x1801b9c49  mov     rdx, [rbp+57h+var_60]
0x1801b9c4d  jmp     short loc_1801B9C5C
0x1801b9c4f  mov     eax, [rbx]
0x1801b9c51  imul    rcx, rax, 0C8h
0x1801b9c58  mov     rdx, [rcx+rdi]
0x1801b9c5c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801b9c60  lea     rcx, [rbp+57h+pwzURI]
0x1801b9c64  mov     r8, rsi
0x1801b9c67  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1801b9c6c  mov     edi, eax
0x1801b9c6e  test    eax, eax
0x1801b9c70  js      loc_1801B9F4B
0x1801b9c76  lea     rcx, [rbp+57h+lpszServerName]
0x1801b9c7a  mov     [rbp+57h+lpszServerName], r12
0x1801b9c7e  mov     [rbp+57h+var_B8], r12
0x1801b9c82  mov     [rbp+57h+var_B0], r12
0x1801b9c86  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b9c8b  mov     r15, [rbp+57h+pwzURI]
0x1801b9c8f  lea     r8, [rbp+57h+lpszServerName]; unsigned __int16 **
0x1801b9c93  mov     rdx, r15; unsigned __int16 *
0x1801b9c96  mov     [rbp+57h+var_B8], rsi
0x1801b9c9a  mov     rcx, rbx; this
0x1801b9c9d  mov     [rbp+57h+var_B0], rsi
0x1801b9ca1  call    ?_UpdateDomain@CConnectedEndpoint@CConnectedSearchTransport@@AEAAJPEBGPEAPEAG@Z; CConnectedSearchTransport::CConnectedEndpoint::_UpdateDomain(ushort const *,ushort * *)
0x1801b9ca6  test    eax, eax
0x1801b9ca8  js      short loc_1801B9CCE
0x1801b9caa  lea     rcx, [rbp+57h+pwzURI]
0x1801b9cae  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b9cb3  lea     rdx, [rbp+57h+pwzURI]
0x1801b9cb7  mov     [rbp+57h+var_A0], rsi
0x1801b9cbb  lea     rcx, [rbp+57h+lpszServerName]
0x1801b9cbf  mov     [rbp+57h+var_98], rsi
0x1801b9cc3  call    ?CopyTo@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CopyTo(ushort * *)
0x1801b9cc8  mov     r15, [rbp+57h+pwzURI]
0x1801b9ccc  mov     edi, eax
0x1801b9cce  lea     rcx, [rbp+57h+lpszServerName]
0x1801b9cd2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b9cd7  test    edi, edi
0x1801b9cd9  js      loc_1801B9F4B
0x1801b9cdf  lea     rcx, [rbp+57h+var_90]
0x1801b9ce3  mov     [rbp+57h+lpszServerName], r12
0x1801b9ce7  mov     [rbp+57h+var_B8], r12
0x1801b9ceb  mov     [rbp+57h+var_B0], r12
0x1801b9cef  mov     [rbp+57h+var_90], r12
0x1801b9cf3  mov     [rbp+57h+var_88], r12
0x1801b9cf7  mov     [rbp+57h+var_80], r12
0x1801b9cfb  mov     [rbp+57h+arg_0], r12d
0x1801b9cff  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b9d04  lea     rcx, [rbp+57h+lpszServerName]
0x1801b9d08  mov     [rbp+57h+var_88], rsi
0x1801b9d0c  mov     [rbp+57h+var_80], rsi
0x1801b9d10  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b9d15  lea     r9, [rbp+57h+var_90]; unsigned __int16 **
0x1801b9d19  mov     [rbp+57h+var_B8], rsi
0x1801b9d1d  lea     r8, [rbp+57h+lpszServerName]; unsigned __int16 **
0x1801b9d21  mov     [rbp+57h+var_B0], rsi
0x1801b9d25  lea     rdx, [rbp+57h+arg_0]; unsigned int *
0x1801b9d29  mov     rcx, r15; pwzURI
0x1801b9d2c  call    ?s_GetUrlParts@CConnectedEndpoint@CConnectedSearchTransport@@CAJPEBGPEAKPEAPEAG2@Z; CConnectedSearchTransport::CConnectedEndpoint::s_GetUrlParts(ushort const *,ulong *,ushort * *,ushort * *)
0x1801b9d31  mov     edi, eax
0x1801b9d33  test    eax, eax
0x1801b9d35  js      loc_1801B9F39
0x1801b9d3b  cmp     [rbp+57h+arg_0], 0Bh
0x1801b9d3f  mov     r14d, 1BBh
0x1801b9d45  jz      short loc_1801B9D4D
0x1801b9d47  mov     r14d, 50h ; 'P'
0x1801b9d4d  lea     rcx, [rbp+57h+lpszAgent]
0x1801b9d51  mov     [rbp+57h+lpszAgent], r12
0x1801b9d55  mov     [rbp+57h+var_70], r12
0x1801b9d59  mov     [rbp+57h+var_68], r12
0x1801b9d5d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b9d62  lea     rcx, [rbp+57h+lpszAgent]; unsigned __int16 **
0x1801b9d66  mov     [rbp+57h+var_70], rsi
0x1801b9d6a  mov     [rbp+57h+var_68], rsi
0x1801b9d6e  call    ?s_GetUserAgentString@CConnectedSearchTransport@@SAJPEAPEAG@Z; CConnectedSearchTransport::s_GetUserAgentString(ushort * *)
0x1801b9d73  mov     edi, eax
0x1801b9d75  test    eax, eax
0x1801b9d77  js      loc_1801B9F30
0x1801b9d7d  mov     r13, [rbp+57h+lpszAgent]
0x1801b9d81  xor     r9d, r9d; lpszProxyBypass
0x1801b9d84  mov     rcx, r13; lpszAgent
0x1801b9d87  mov     [rsp+100h+dwFlags], r12d; dwFlags
0x1801b9d8c  xor     r8d, r8d; lpszProxy
0x1801b9d8f  xor     edx, edx; dwAccessType
0x1801b9d91  call    cs:__imp_InternetOpenW
0x1801b9d98  nop     dword ptr [rax+rax+00h]
0x1801b9d9d  mov     rsi, rax
0x1801b9da0  test    rax, rax
0x1801b9da3  jnz     short loc_1801B9DB4
0x1801b9da5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801b9daa  mov     edi, eax
0x1801b9dac  test    eax, eax
0x1801b9dae  js      loc_1801B9F30
0x1801b9db4  mov     r9d, 4; dwBufferLength
0x1801b9dba  mov     [rbp+57h+Buffer], 1
0x1801b9dc1  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1801b9dc5  mov     rcx, rsi; hInternet
0x1801b9dc8  lea     edx, [r9+3Dh]; dwOption
0x1801b9dcc  call    cs:__imp_InternetSetOptionW
0x1801b9dd3  nop     dword ptr [rax+rax+00h]
0x1801b9dd8  test    eax, eax
0x1801b9dda  jnz     short loc_1801B9DE7
0x1801b9ddc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801b9de1  mov     edi, eax
0x1801b9de3  test    eax, eax
0x1801b9de5  js      short loc_1801B9E2E
0x1801b9de7  mov     [rsp+100h+dwContext], r12; dwContext
0x1801b9dec  xor     r9d, r9d; lpszUserName
0x1801b9def  mov     [rsp+100h+var_D0], r12d; dwFlags
0x1801b9df4  movzx   r8d, r14w; nServerPort
0x1801b9df8  mov     [rsp+100h+dwService], 3; dwService
0x1801b9e00  mov     rcx, rsi; hInternet
0x1801b9e03  mov     qword ptr [rsp+100h+dwFlags], r12; lpszPassword
0x1801b9e08  mov     r12, [rbp+57h+lpszServerName]
0x1801b9e0c  mov     rdx, r12; lpszServerName
0x1801b9e0f  call    cs:__imp_InternetConnectW
0x1801b9e16  nop     dword ptr [rax+rax+00h]
0x1801b9e1b  mov     r14, rax
0x1801b9e1e  test    rax, rax
0x1801b9e21  jnz     short loc_1801B9E42
0x1801b9e23  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801b9e28  mov     edi, eax
0x1801b9e2a  test    eax, eax
0x1801b9e2c  jns     short loc_1801B9E44
0x1801b9e2e  mov     rcx, rsi; hInternet
0x1801b9e31  call    cs:__imp_InternetCloseHandle
0x1801b9e38  nop     dword ptr [rax+rax+00h]
0x1801b9e3d  jmp     loc_1801B9F30
0x1801b9e42  xor     edi, edi
0x1801b9e44  lea     rdx, [rbx+20h]
0x1801b9e48  lea     rcx, [rbp+57h+arg_10]
0x1801b9e4c  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801b9e51  mov     [rbx+28h], r14
0x1801b9e55  xor     r14d, r14d
0x1801b9e58  mov     [rbx+8], rsi
0x1801b9e5c  mov     rcx, [rbx+38h]; pv
0x1801b9e60  mov     [rbp+57h+pwzURI], r14
0x1801b9e64  mov     [rbp+57h+var_98], r14
0x1801b9e68  mov     [rbp+57h+var_A0], r14
0x1801b9e6c  test    rcx, rcx
0x1801b9e6f  jz      short loc_1801B9E7D
0x1801b9e71  call    cs:__imp_CoTaskMemFree
0x1801b9e78  nop     dword ptr [rax+rax+00h]
0x1801b9e7d  mov     rsi, [rbp+57h+var_90]
0x1801b9e81  mov     [rbx+38h], r15
0x1801b9e85  or      r15, 0FFFFFFFFFFFFFFFFh
0x1801b9e89  mov     [rbx+48h], r15
0x1801b9e8d  mov     [rbx+40h], r15
0x1801b9e91  mov     rcx, [rbx+50h]; pv
0x1801b9e95  mov     [rbp+57h+var_90], r14
0x1801b9e99  mov     [rbp+57h+var_80], r14
0x1801b9e9d  mov     [rbp+57h+var_88], r14
0x1801b9ea1  test    rcx, rcx
0x1801b9ea4  jz      short loc_1801B9EB2
0x1801b9ea6  call    cs:__imp_CoTaskMemFree
0x1801b9ead  nop     dword ptr [rax+rax+00h]
0x1801b9eb2  mov     [rbx+50h], rsi
0x1801b9eb6  mov     [rbx+60h], r15
0x1801b9eba  mov     [rbx+58h], r15
0x1801b9ebe  mov     rcx, [rbx+68h]; pv
0x1801b9ec2  mov     [rbp+57h+lpszServerName], r14
0x1801b9ec6  mov     [rbp+57h+var_B0], r14
0x1801b9eca  mov     [rbp+57h+var_B8], r14
0x1801b9ece  test    rcx, rcx
0x1801b9ed1  jz      short loc_1801B9EDF
0x1801b9ed3  call    cs:__imp_CoTaskMemFree
0x1801b9eda  nop     dword ptr [rax+rax+00h]
0x1801b9edf  mov     eax, [rbp+57h+arg_0]
0x1801b9ee2  mov     [rbx+68h], r12
0x1801b9ee6  mov     [rbx+78h], r15
0x1801b9eea  mov     [rbx+70h], r15
0x1801b9eee  mov     [rbx+80h], eax
0x1801b9ef4  cmp     eax, 0Bh
0x1801b9ef7  jnz     short loc_1801B9EFE
0x1801b9ef9  bts     dword ptr [rbx+30h], 17h
0x1801b9efe  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x1801b9f05  jz      short loc_1801B9F27
0x1801b9f07  mov     rax, [rbx+50h]
0x1801b9f0b  lea     rdx, ConnectedSearch_ConnectionEstablished
0x1801b9f12  mov     r8d, [rbx]
0x1801b9f15  xor     r9d, r9d
0x1801b9f18  mov     qword ptr [rsp+100h+dwService], r13
0x1801b9f1d  mov     qword ptr [rsp+100h+dwFlags], rax
0x1801b9f22  call    McTemplateU0qzzz_EventWriteTransfer
0x1801b9f27  lea     rcx, [rbp+57h+arg_10]; this
0x1801b9f2b  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801b9f30  lea     rcx, [rbp+57h+lpszAgent]
0x1801b9f34  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b9f39  lea     rcx, [rbp+57h+var_90]
0x1801b9f3d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b9f42  lea     rcx, [rbp+57h+lpszServerName]
0x1801b9f46  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b9f4b  mov     eax, edi
0x1801b9f4d  lea     rcx, [rbp+57h+pwzURI]
0x1801b9f51  shr     eax, 1Fh
0x1801b9f54  xor     al, 1
0x1801b9f56  mov     [rbx+18h], al
0x1801b9f59  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b9f5e  lea     rcx, [rbp+57h+var_60]
0x1801b9f62  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b9f67  lea     rcx, [rbp+57h+arg_18]; this
0x1801b9f6b  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801b9f70  mov     eax, edi
0x1801b9f72  add     rsp, 0C8h
0x1801b9f79  pop     r15
0x1801b9f7b  pop     r14
0x1801b9f7d  pop     r13
0x1801b9f7f  pop     r12
0x1801b9f81  pop     rdi
0x1801b9f82  pop     rsi
0x1801b9f83  pop     rbx
0x1801b9f84  pop     rbp
0x1801b9f85  retn
```
