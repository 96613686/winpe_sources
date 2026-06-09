# CWSConnection::ReadResponseFromServer(void)

- ea: `0x18007ab94`
- end: `0x18007afda`
- name: `?ReadResponseFromServer@CWSConnection@@AEAAJXZ`
- size: `1094`
- prototype: `__int64 __fastcall(CWSConnection *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18007afe0`

## callees

- `0x18001e3e0`
- `0x180022da4`
- `0x18007aa48`
- `0x18007ab94`
- `0x18009cc18`
- `0x1800a98c0`
- `0x1800a98e4`
- `0x1800a9dd0`
- `0x1800aa5ac`
- `0x1800d98e0`
- `0x1800f29ec`
- `0x1801255d8`
- `0x180125608`
- `0x1801256b4`
- `0x1801257fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ac1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ad1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ae65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007af37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ac1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ad1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ae65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007af37`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007af08`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007af08`
- `WINHTTP!WinHttpReceiveResponse` at `0x18007abf2`
- `WINHTTP!WinHttpReceiveResponse` at `0x18007abf2`
- `WINHTTP!WinHttpQueryHeaders` at `0x18007aced`
- `WINHTTP!WinHttpQueryHeaders` at `0x18007ad92`
- `WINHTTP!WinHttpQueryHeaders` at `0x18007adec`
- `WINHTTP!WinHttpQueryHeaders` at `0x18007aced`
- `WINHTTP!WinHttpQueryHeaders` at `0x18007ad92`
- `WINHTTP!WinHttpQueryHeaders` at `0x18007adec`
- `WINHTTP!WinHttpReadData` at `0x18007ae36`
- `WINHTTP!WinHttpReadData` at `0x18007ae36`

## string_xrefs

- `0x18007af1a`: `WriteFile(m_binaryFile, pResponseBuffer, dataSizeAlreadyRead, nullptr, nullptr)`
- `0x18007ac10`: `CWSConnection::ReadResponseFromServer`
- `0x18007ad0b`: `CWSConnection::ReadResponseFromServer`
- `0x18007ae54`: `CWSConnection::ReadResponseFromServer`
- `0x18007af26`: `CWSConnection::ReadResponseFromServer`
- `0x18007ae48`: `WinHttpReadData(m_hHttpRequestConnection, pResponseBuffer, fixedSizeReadBuffer, nullptr)`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CWSConnection::ReadResponseFromServer(CWSConnection *this)
{
  __int64 v2; // rax
  void *v3; // rcx
  __int64 v4; // r15
  unsigned int v5; // r8d
  signed int LastError; // eax
  int v7; // edx
  int v8; // ecx
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // edx
  int v12; // ecx
  unsigned int v13; // r8d
  signed int v14; // eax
  void *v15; // rsi
  unsigned int v16; // r8d
  signed int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  int v20; // edx
  int v21; // ecx
  __int64 v22; // rax
  DWORD v23; // r14d
  void *v24; // rcx
  unsigned int v25; // r8d
  signed int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  const char *lpdwIndex; // [rsp+28h] [rbp-270h]
  const char *lpdwIndexa; // [rsp+28h] [rbp-270h]
  DWORD lpdwBufferLength; // [rsp+40h] [rbp-258h] BYREF
  DWORD dwBufferLength; // [rsp+44h] [rbp-254h] BYREF
  int Buffer; // [rsp+48h] [rbp-250h] BYREF
  _BYTE v36[512]; // [rsp+50h] [rbp-248h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+298h] [rbp+0h]

  memset_0(v36, 0, sizeof(v36));
  lpdwBufferLength = 512;
  v2 = *((_QWORD *)this + 10);
  if ( !v2 )
    return (unsigned int)-2147024890;
  v3 = (void *)*((_QWORD *)this + 4);
  if ( !v3 )
    return (unsigned int)-2147024890;
  v4 = *(_QWORD *)(v2 + 56);
  if ( !WinHttpReceiveResponse(v3, 0) )
  {
    wil::details::in1diag5::_Log_GetLastError(
      retaddr,
      (void *)0x265,
      v5,
      "CWSConnection::ReadResponseFromServer",
      "WinHttpReceiveResponse(m_hHttpRequestConnection, nullptr)",
      lpdwIndex);
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (byte_1801E39C3 & 2) != 0 )
      McTemplateU0dqdqd_EventWriteTransfer(v8, v7, *((_DWORD *)this + 39), *((_DWORD *)this + 40), v4, 4, v9);
    return v9;
  }
  v10 = CWSConnection::DoWaitOnAsyncEvents(
          this,
          *(void **)(*((_QWORD *)this + 10) + 24LL),
          *((struct WINHTTP_ASYNC_CONTEXT **)this + 10));
  v9 = v10;
  if ( v10 < 0 )
  {
    if ( (byte_1801E39C3 & 2) != 0 )
      McTemplateU0dqdqq_EventWriteTransfer(v12, v11, *((_DWORD *)this + 39), *((_DWORD *)this + 40), v4, 1, v10);
    return v9;
  }
  Buffer = 0;
  dwBufferLength = 4;
  if ( !WinHttpQueryHeaders(*((HINTERNET *)this + 4), 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
  {
    wil::details::in1diag5::_Log_GetLastError(
      retaddr,
      (void *)0x288,
      v13,
      "CWSConnection::ReadResponseFromServer",
      "WinHttpQueryHeaders( m_hHttpRequestConnection, WINHTTP_QUERY_STATUS_CODE | WINHTTP_QUERY_FLAG_NUMBER, WINHTTP_HEAD"
      "ER_NAME_BY_INDEX, &statusCode, &cbStatusCode, WINHTTP_NO_HEADER_INDEX)",
      lpdwIndexa);
    v14 = GetLastError();
    v9 = v14;
    if ( v14 > 0 )
      return (unsigned __int16)v14 | 0x80070000;
    return v9;
  }
  *((_DWORD *)this + 18) = Buffer;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_OrionDeviceAuth>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Location_OrionDeviceAuth>::GetImpl'::`2'::impl) )
  {
    std::wstring::_Eos((char *)this + 168, 0);
    if ( WinHttpQueryHeaders(*((HINTERNET *)this + 4), 0xFFFFu, L"Authorization-Result", v36, &lpdwBufferLength, 0) )
      std::wstring::_Assign<unsigned short>((char *)this + 168, v36, (unsigned __int64)lpdwBufferLength >> 1);
    lpdwBufferLength = 512;
    std::wstring::_Eos((char *)this + 200, 0);
    if ( WinHttpQueryHeaders(*((HINTERNET *)this + 4), 0xFFFFu, L"Authorization-Debug", v36, &lpdwBufferLength, 0) )
      std::wstring::_Assign<unsigned short>((char *)this + 200, v36, (unsigned __int64)lpdwBufferLength >> 1);
  }
  v15 = operator new[](0x2000u);
  memset_0(v15, 0, 0x2000u);
  while ( 1 )
  {
    if ( !WinHttpReadData(*((HINTERNET *)this + 4), v15, 0x2000u, 0) )
    {
      wil::details::in1diag5::_Log_GetLastError(
        retaddr,
        (void *)0x2B1,
        v16,
        "CWSConnection::ReadResponseFromServer",
        "WinHttpReadData(m_hHttpRequestConnection, pResponseBuffer, fixedSizeReadBuffer, nullptr)",
        lpdwIndexa);
      v17 = GetLastError();
      v9 = v17;
      if ( v17 > 0 )
        v9 = (unsigned __int16)v17 | 0x80070000;
LABEL_35:
      if ( *((_QWORD *)this + 7) && !*((_QWORD *)this + 13) && (byte_1801E39C3 & 2) != 0 )
      {
        v27 = std::_String_val<std::_Simple_types<char>>::_Myptr((char *)this + 40, v18);
        McTemplateU0qsr0_EventWriteTransfer(v29, v28, *((unsigned int *)this + 14), v27);
      }
      goto LABEL_39;
    }
    v19 = CWSConnection::DoWaitOnAsyncEvents(
            this,
            **((void ***)this + 10),
            *((struct WINHTTP_ASYNC_CONTEXT **)this + 10));
    v9 = v19;
    if ( v19 < 0 )
    {
      if ( (byte_1801E39C3 & 2) != 0 )
        McTemplateU0dqdqq_EventWriteTransfer(v21, v20, *((_DWORD *)this + 39), *((_DWORD *)this + 40), v4, 2, v19);
      goto LABEL_39;
    }
    v22 = *((_QWORD *)this + 10);
    v23 = *(_DWORD *)(v22 + 44);
    if ( v23 > 0x2000 )
    {
      v9 = -2147418113;
      goto LABEL_39;
    }
    if ( v23 )
    {
      v24 = (void *)*((_QWORD *)this + 13);
      if ( !v24 )
      {
        std::string::_Append<char>((char *)this + 40, v15, *(unsigned int *)(v22 + 44));
        goto LABEL_34;
      }
      if ( !WriteFile(v24, v15, v23, 0, 0) )
        break;
    }
LABEL_34:
    memset_0(v15, 0, 0x2000u);
    if ( !v23 )
      goto LABEL_35;
  }
  wil::details::in1diag5::_Log_GetLastError(
    retaddr,
    (void *)0x2D4,
    v25,
    "CWSConnection::ReadResponseFromServer",
    "WriteFile(m_binaryFile, pResponseBuffer, dataSizeAlreadyRead, nullptr, nullptr)",
    lpdwIndexa);
  v26 = GetLastError();
  v9 = v26;
  if ( v26 > 0 )
    v9 = (unsigned __int16)v26 | 0x80070000;
LABEL_39:
  if ( v15 )
    operator delete(v15);
  return v9;
}

```

## disassembly

```asm
0x18007ab94  push    rbx
0x18007ab96  push    rsi
0x18007ab97  push    rdi
0x18007ab98  push    r13
0x18007ab9a  push    r14
0x18007ab9c  push    r15
0x18007ab9e  sub     rsp, 268h
0x18007aba5  mov     rax, cs:__security_cookie
0x18007abac  xor     rax, rsp
0x18007abaf  mov     [rsp+298h+var_48], rax
0x18007abb7  mov     rdi, rcx
0x18007abba  mov     esi, 200h
0x18007abbf  mov     r8d, esi; Size
0x18007abc2  xor     edx, edx; Val
0x18007abc4  lea     rcx, [rsp+298h+var_248]; void *
0x18007abc9  call    memset_0
0x18007abce  mov     [rsp+298h+var_258], esi
0x18007abd2  mov     rax, [rdi+50h]
0x18007abd6  test    rax, rax
0x18007abd9  jz      loc_18007AFAB
0x18007abdf  mov     rcx, [rdi+20h]; hRequest
0x18007abe3  test    rcx, rcx
0x18007abe6  jz      loc_18007AFAB
0x18007abec  mov     r15, [rax+38h]
0x18007abf0  xor     edx, edx; lpReserved
0x18007abf2  call    cs:__imp_WinHttpReceiveResponse
0x18007abf8  mov     rcx, [rsp+298h]; this
0x18007ac00  test    eax, eax
0x18007ac02  jnz     short loc_18007AC6A
0x18007ac04  lea     rax, aWinhttpreceive_0; "WinHttpReceiveResponse(m_hHttpRequestCo"...
0x18007ac0b  mov     [rsp+298h+lpdwBufferLength], rax; char *
0x18007ac10  lea     r9, aCwsconnectionR; "CWSConnection::ReadResponseFromServer"
0x18007ac17  lea     edx, [rsi+65h]; void *
0x18007ac1a  call    ?_Log_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_Log_GetLastError(void *,uint,char const *,char const *,char const *)
0x18007ac1f  call    cs:__imp_GetLastError
0x18007ac25  mov     ebx, eax
0x18007ac27  test    eax, eax
0x18007ac29  jle     short loc_18007AC34
0x18007ac2b  movzx   ebx, ax
0x18007ac2e  or      ebx, 80070000h
0x18007ac34  test    cs:byte_1801E39C3, 2
0x18007ac3b  jz      loc_18007AFB0
0x18007ac41  mov     [rsp+298h+var_268], ebx
0x18007ac45  mov     dword ptr [rsp+298h+lpdwIndex], 4
0x18007ac4d  mov     dword ptr [rsp+298h+lpdwBufferLength], r15d
0x18007ac52  mov     r9d, [rdi+0A0h]
0x18007ac59  mov     r8d, [rdi+9Ch]
0x18007ac60  call    McTemplateU0dqdqd_EventWriteTransfer
0x18007ac65  jmp     loc_18007AFB0
0x18007ac6a  mov     rdx, [rdi+50h]
0x18007ac6e  mov     r8, rdx; struct WINHTTP_ASYNC_CONTEXT *
0x18007ac71  mov     rdx, [rdx+18h]; void *
0x18007ac75  mov     rcx, rdi; this
0x18007ac78  call    ?DoWaitOnAsyncEvents@CWSConnection@@AEAAJPEAXPEAUWINHTTP_ASYNC_CONTEXT@@@Z; CWSConnection::DoWaitOnAsyncEvents(void *,WINHTTP_ASYNC_CONTEXT *)
0x18007ac7d  mov     ebx, eax
0x18007ac7f  test    eax, eax
0x18007ac81  jns     short loc_18007ACB9
0x18007ac83  test    cs:byte_1801E39C3, 2
0x18007ac8a  jz      loc_18007AFB0
0x18007ac90  mov     [rsp+298h+var_268], eax
0x18007ac94  mov     dword ptr [rsp+298h+lpdwIndex], 1
0x18007ac9c  mov     dword ptr [rsp+298h+lpdwBufferLength], r15d
0x18007aca1  mov     r9d, [rdi+0A0h]
0x18007aca8  mov     r8d, [rdi+9Ch]
0x18007acaf  call    McTemplateU0dqdqq_EventWriteTransfer
0x18007acb4  jmp     loc_18007AFB0
0x18007acb9  mov     [rsp+298h+Buffer], 0
0x18007acc1  mov     [rsp+298h+dwBufferLength], 4
0x18007acc9  mov     [rsp+298h+lpdwIndex], 0; char *
0x18007acd2  lea     rax, [rsp+298h+dwBufferLength]
0x18007acd7  mov     [rsp+298h+lpdwBufferLength], rax; lpdwBufferLength
0x18007acdc  lea     r9, [rsp+298h+Buffer]; lpBuffer
0x18007ace1  xor     r8d, r8d; pwszName
0x18007ace4  mov     edx, 20000013h; dwInfoLevel
0x18007ace9  mov     rcx, [rdi+20h]; hRequest
0x18007aced  call    cs:__imp_WinHttpQueryHeaders
0x18007acf3  mov     rcx, [rsp+298h]; this
0x18007acfb  test    eax, eax
0x18007acfd  jnz     short loc_18007AD3A
0x18007acff  lea     rax, aWinhttpqueryhe_0; "WinHttpQueryHeaders( m_hHttpRequestConn"...
0x18007ad06  mov     [rsp+298h+lpdwBufferLength], rax; char *
0x18007ad0b  lea     r9, aCwsconnectionR; "CWSConnection::ReadResponseFromServer"
0x18007ad12  mov     edx, 288h; void *
0x18007ad17  call    ?_Log_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_Log_GetLastError(void *,uint,char const *,char const *,char const *)
0x18007ad1c  call    cs:__imp_GetLastError
0x18007ad22  mov     ebx, eax
0x18007ad24  test    eax, eax
0x18007ad26  jle     loc_18007AFB0
0x18007ad2c  movzx   ebx, ax
0x18007ad2f  or      ebx, 80070000h
0x18007ad35  jmp     loc_18007AFB0
0x18007ad3a  mov     eax, [rsp+298h+Buffer]
0x18007ad3e  mov     [rdi+48h], eax
0x18007ad41  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Location_OrionDeviceAuth@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Location_OrionDeviceAuth@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_OrionDeviceAuth> `wil::Feature<__WilFeatureTraits_Feature_Location_OrionDeviceAuth>::GetImpl(void)'::`2'::impl
0x18007ad48  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Location_OrionDeviceAuth@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_OrionDeviceAuth>::__private_IsEnabled(void)
0x18007ad4d  test    al, al
0x18007ad4f  jz      loc_18007AE0B
0x18007ad55  lea     rbx, [rdi+0A8h]
0x18007ad5c  xor     edx, edx
0x18007ad5e  mov     rcx, rbx
0x18007ad61  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x18007ad66  mov     [rsp+298h+lpdwIndex], 0; lpdwIndex
0x18007ad6f  lea     rax, [rsp+298h+var_258]
0x18007ad74  mov     [rsp+298h+lpdwBufferLength], rax; lpdwBufferLength
0x18007ad79  lea     r9, [rsp+298h+var_248]; lpBuffer
0x18007ad7e  lea     r8, ?c_authResultHeader@@3QBGB; "Authorization-Result"
0x18007ad85  mov     r14d, 0FFFFh
0x18007ad8b  mov     edx, r14d; dwInfoLevel
0x18007ad8e  mov     rcx, [rdi+20h]; hRequest
0x18007ad92  call    cs:__imp_WinHttpQueryHeaders
0x18007ad98  test    eax, eax
0x18007ad9a  jz      short loc_18007ADB1
0x18007ad9c  mov     r8d, [rsp+298h+var_258]
0x18007ada1  shr     r8, 1
0x18007ada4  lea     rdx, [rsp+298h+var_248]
0x18007ada9  mov     rcx, rbx
0x18007adac  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007adb1  mov     [rsp+298h+var_258], esi
0x18007adb5  lea     rbx, [rdi+0C8h]
0x18007adbc  xor     edx, edx
0x18007adbe  mov     rcx, rbx
0x18007adc1  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x18007adc6  mov     [rsp+298h+lpdwIndex], 0; char *
0x18007adcf  lea     rax, [rsp+298h+var_258]
0x18007add4  mov     [rsp+298h+lpdwBufferLength], rax; lpdwBufferLength
0x18007add9  lea     r9, [rsp+298h+var_248]; lpBuffer
0x18007adde  lea     r8, ?c_authDebugHeader@@3QBGB; "Authorization-Debug"
0x18007ade5  mov     edx, r14d; dwInfoLevel
0x18007ade8  mov     rcx, [rdi+20h]; hRequest
0x18007adec  call    cs:__imp_WinHttpQueryHeaders
0x18007adf2  test    eax, eax
0x18007adf4  jz      short loc_18007AE0B
0x18007adf6  mov     r8d, [rsp+298h+var_258]
0x18007adfb  shr     r8, 1
0x18007adfe  lea     rdx, [rsp+298h+var_248]
0x18007ae03  mov     rcx, rbx
0x18007ae06  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007ae0b  mov     r13d, 2000h
0x18007ae11  mov     ecx, r13d; unsigned __int64
0x18007ae14  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007ae19  mov     rsi, rax
0x18007ae1c  mov     r8d, r13d; Size
0x18007ae1f  xor     edx, edx; Val
0x18007ae21  mov     rcx, rax; void *
0x18007ae24  call    memset_0
0x18007ae29  xor     r9d, r9d; lpdwNumberOfBytesRead
0x18007ae2c  mov     r8d, r13d; dwNumberOfBytesToRead
0x18007ae2f  mov     rdx, rsi; lpBuffer
0x18007ae32  mov     rcx, [rdi+20h]; hRequest
0x18007ae36  call    cs:__imp_WinHttpReadData
0x18007ae3c  mov     rcx, [rsp+298h]; this
0x18007ae44  test    eax, eax
0x18007ae46  jnz     short loc_18007AE83
0x18007ae48  lea     rax, aWinhttpreaddat_0; "WinHttpReadData(m_hHttpRequestConnectio"...
0x18007ae4f  mov     [rsp+298h+lpdwBufferLength], rax; char *
0x18007ae54  lea     r9, aCwsconnectionR; "CWSConnection::ReadResponseFromServer"
0x18007ae5b  mov     edx, 2B1h; void *
0x18007ae60  call    ?_Log_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_Log_GetLastError(void *,uint,char const *,char const *,char const *)
0x18007ae65  call    cs:__imp_GetLastError
0x18007ae6b  mov     ebx, eax
0x18007ae6d  test    eax, eax
0x18007ae6f  jle     loc_18007AF70
0x18007ae75  movzx   ebx, ax
0x18007ae78  or      ebx, 80070000h
0x18007ae7e  jmp     loc_18007AF70
0x18007ae83  mov     rdx, [rdi+50h]
0x18007ae87  mov     r8, rdx; struct WINHTTP_ASYNC_CONTEXT *
0x18007ae8a  mov     rdx, [rdx]; void *
0x18007ae8d  mov     rcx, rdi; this
0x18007ae90  call    ?DoWaitOnAsyncEvents@CWSConnection@@AEAAJPEAXPEAUWINHTTP_ASYNC_CONTEXT@@@Z; CWSConnection::DoWaitOnAsyncEvents(void *,WINHTTP_ASYNC_CONTEXT *)
0x18007ae95  mov     ebx, eax
0x18007ae97  test    eax, eax
0x18007ae99  jns     short loc_18007AED1
0x18007ae9b  test    cs:byte_1801E39C3, 2
0x18007aea2  jz      loc_18007AF9C
0x18007aea8  mov     [rsp+298h+var_268], eax
0x18007aeac  mov     dword ptr [rsp+298h+lpdwIndex], 2
0x18007aeb4  mov     dword ptr [rsp+298h+lpdwBufferLength], r15d
0x18007aeb9  mov     r9d, [rdi+0A0h]
0x18007aec0  mov     r8d, [rdi+9Ch]
0x18007aec7  call    McTemplateU0dqdqq_EventWriteTransfer
0x18007aecc  jmp     loc_18007AF9C
0x18007aed1  mov     rax, [rdi+50h]
0x18007aed5  mov     r14d, [rax+2Ch]
0x18007aed9  cmp     r14d, r13d
0x18007aedc  jbe     short loc_18007AEE8
0x18007aede  mov     ebx, 8000FFFFh
0x18007aee3  jmp     loc_18007AF9C
0x18007aee8  test    r14d, r14d
0x18007aeeb  jz      short loc_18007AF5A
0x18007aeed  mov     rcx, [rdi+68h]; hFile
0x18007aef1  mov     rdx, rsi; lpBuffer
0x18007aef4  test    rcx, rcx
0x18007aef7  jz      short loc_18007AF4E
0x18007aef9  mov     [rsp+298h+lpdwBufferLength], 0; lpOverlapped
0x18007af02  xor     r9d, r9d; lpNumberOfBytesWritten
0x18007af05  mov     r8d, r14d; nNumberOfBytesToWrite
0x18007af08  call    cs:__imp_WriteFile
0x18007af0e  mov     rcx, [rsp+298h]; this
0x18007af16  test    eax, eax
0x18007af18  jnz     short loc_18007AF5A
0x18007af1a  lea     rax, aWritefileMBina; "WriteFile(m_binaryFile, pResponseBuffer"...
0x18007af21  mov     [rsp+298h+lpdwBufferLength], rax; char *
0x18007af26  lea     r9, aCwsconnectionR; "CWSConnection::ReadResponseFromServer"
0x18007af2d  mov     edx, 2D4h; void *
0x18007af32  call    ?_Log_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_Log_GetLastError(void *,uint,char const *,char const *,char const *)
0x18007af37  call    cs:__imp_GetLastError
0x18007af3d  mov     ebx, eax
0x18007af3f  test    eax, eax
0x18007af41  jle     short loc_18007AF9C
0x18007af43  movzx   ebx, ax
0x18007af46  or      ebx, 80070000h
0x18007af4c  jmp     short loc_18007AF9C
0x18007af4e  lea     rcx, [rdi+28h]
0x18007af52  mov     r8, r14
0x18007af55  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x18007af5a  mov     r8, r13; Size
0x18007af5d  xor     edx, edx; Val
0x18007af5f  mov     rcx, rsi; void *
0x18007af62  call    memset_0
0x18007af67  test    r14d, r14d
0x18007af6a  jnz     loc_18007AE29
0x18007af70  cmp     qword ptr [rdi+38h], 0
0x18007af75  jz      short loc_18007AF9C
0x18007af77  cmp     qword ptr [rdi+68h], 0
0x18007af7c  jnz     short loc_18007AF9C
0x18007af7e  test    cs:byte_1801E39C3, 2
0x18007af85  jz      short loc_18007AF9C
0x18007af87  lea     rcx, [rdi+28h]
0x18007af8b  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18007af90  mov     r9, rax
0x18007af93  mov     r8d, [rdi+38h]
0x18007af97  call    McTemplateU0qsr0_EventWriteTransfer
0x18007af9c  test    rsi, rsi
0x18007af9f  jz      short loc_18007AFB0
0x18007afa1  mov     rcx, rsi; Block
0x18007afa4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007afa9  jmp     short loc_18007AFB0
0x18007afab  mov     ebx, 80070006h
0x18007afb0  mov     eax, ebx
0x18007afb2  jmp     short loc_18007AFB8
0x18007afb4  mov     eax, [rsp+298h+dwBufferLength]
0x18007afb8  mov     rcx, [rsp+298h+var_48]
0x18007afc0  xor     rcx, rsp; StackCookie
0x18007afc3  call    __security_check_cookie
0x18007afc8  add     rsp, 268h
0x18007afcf  pop     r15
0x18007afd1  pop     r14
0x18007afd3  pop     r13
0x18007afd5  pop     rdi
0x18007afd6  pop     rsi
0x18007afd7  pop     rbx
0x18007afd8  retn
```
