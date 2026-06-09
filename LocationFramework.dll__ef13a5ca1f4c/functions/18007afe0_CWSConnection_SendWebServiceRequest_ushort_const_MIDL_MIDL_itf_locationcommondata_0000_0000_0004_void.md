# CWSConnection::SendWebServiceRequest(ushort const *,__MIDL___MIDL_itf_locationcommondata_0000_0000_0004,void *)

- ea: `0x18007afe0`
- end: `0x18007b25e`
- name: `?SendWebServiceRequest@CWSConnection@@QEAAJPEBGW4__MIDL___MIDL_itf_locationcommondata_0000_0000_0004@@PEAX@Z`
- size: `638`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18011de80`
- `0x18011f91c`

## callees

- `0x18003a940`
- `0x1800533a4`
- `0x18005fccc`
- `0x18007aa48`
- `0x18007ab94`
- `0x18007afe0`
- `0x1800a98e4`
- `0x1801255d8`
- `0x180125608`
- `0x1801256b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b0f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b1cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b0f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b1cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007b0a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007b0a0`
- `WINHTTP!WinHttpWriteData` at `0x18007b1a3`
- `WINHTTP!WinHttpWriteData` at `0x18007b1a3`
- `WINHTTP!WinHttpSendRequest` at `0x18007b0c7`
- `WINHTTP!WinHttpSendRequest` at `0x18007b0c7`

## string_xrefs

- `0x18007b0dd`: `CWSConnection::SendWebServiceRequest`
- `0x18007b1b9`: `CWSConnection::SendWebServiceRequest`
- `0x18007b1b2`: `WinHttpWriteData( m_hHttpRequestConnection, pbCompressedPayload, multibyteWSDataLengthInBytes, nullptr)`

## pseudocode

```c
__int64 __fastcall CWSConnection::SendWebServiceRequest(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        __int64 a4)
{
  DWORD v4; // ebp
  unsigned __int8 *v5; // rsi
  signed int ResponseFromServer; // ebx
  __int64 v10; // r14
  CWSConnection *v11; // rcx
  int v12; // eax
  unsigned int v13; // r8d
  signed int LastError; // eax
  int v15; // edx
  int v16; // ecx
  int v17; // eax
  int v18; // edx
  int v19; // ecx
  unsigned int v20; // r8d
  signed int v21; // eax
  int v22; // edx
  int v23; // ecx
  int v24; // eax
  int v25; // edx
  int v26; // ecx
  const char *dwTotalLength; // [rsp+28h] [rbp-40h]
  wil::details::in1diag5 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned __int8 *v30; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v31; // [rsp+88h] [rbp+20h] BYREF
  int v32; // [rsp+8Ch] [rbp+24h]

  v32 = HIDWORD(a4);
  v4 = 0;
  v5 = 0;
  ResponseFromServer = -2147024809;
  v31 = 0;
  v30 = 0;
  if ( *(_QWORD *)(a1 + 32) )
  {
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 56LL);
    if ( (unsigned int)dword_1801DDF30 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1801DDF30,
        &unk_1801B4BC0);
    ResponseFromServer = CWSConnection::SetRequirements(a1, a3);
    if ( ResponseFromServer >= 0 || !a3 )
    {
      if ( a2 )
      {
        v12 = CWSConnection::PreprocessPayload(v11, *(_DWORD *)(a1 + 164) != 7, a2, &v30, &v31);
        v5 = v30;
        ResponseFromServer = v12;
        if ( v12 < 0 )
          goto LABEL_29;
        v4 = v31;
      }
      GetSystemTimeAsFileTime((LPFILETIME)a1);
      if ( !WinHttpSendRequest(*(HINTERNET *)(a1 + 32), 0, 0, 0, 0, v4, *(_QWORD *)(a1 + 80)) )
      {
        wil::details::in1diag5::_Log_GetLastError(
          retaddr,
          (void *)0x32C,
          v13,
          "CWSConnection::SendWebServiceRequest",
          "WinHttpSendRequest( m_hHttpRequestConnection, WINHTTP_NO_ADDITIONAL_HEADERS, 0, WINHTTP_NO_REQUEST_DATA, 0, mu"
          "ltibyteWSDataLengthInBytes, (DWORD_PTR)m_pAsyncEventsContext)",
          dwTotalLength);
        LastError = GetLastError();
        ResponseFromServer = LastError;
        if ( LastError > 0 )
          ResponseFromServer = (unsigned __int16)LastError | 0x80070000;
        if ( (byte_1801E39C3 & 2) != 0 )
          McTemplateU0dqdqd_EventWriteTransfer(
            v16,
            v15,
            *(_DWORD *)(a1 + 156),
            *(_DWORD *)(a1 + 160),
            v10,
            2,
            ResponseFromServer);
        goto LABEL_29;
      }
      v17 = CWSConnection::DoWaitOnAsyncEvents(
              (CWSConnection *)a1,
              *(void **)(*(_QWORD *)(a1 + 80) + 32LL),
              *(struct WINHTTP_ASYNC_CONTEXT **)(a1 + 80));
      ResponseFromServer = v17;
      if ( v17 < 0 )
      {
        if ( (byte_1801E39C3 & 2) != 0 )
          McTemplateU0dqdqq_EventWriteTransfer(v19, v18, *(_DWORD *)(a1 + 156), *(_DWORD *)(a1 + 160), v10, 5, v17);
        goto LABEL_29;
      }
      if ( !v5 )
        goto LABEL_28;
      if ( !WinHttpWriteData(*(HINTERNET *)(a1 + 32), v5, v4, 0) )
      {
        wil::details::in1diag5::_Log_GetLastError(
          retaddr,
          (void *)0x34B,
          v20,
          "CWSConnection::SendWebServiceRequest",
          "WinHttpWriteData( m_hHttpRequestConnection, pbCompressedPayload, multibyteWSDataLengthInBytes, nullptr)",
          dwTotalLength);
        v21 = GetLastError();
        ResponseFromServer = v21;
        if ( v21 > 0 )
          ResponseFromServer = (unsigned __int16)v21 | 0x80070000;
        if ( (byte_1801E39C3 & 2) != 0 )
          McTemplateU0dqdqd_EventWriteTransfer(
            v23,
            v22,
            *(_DWORD *)(a1 + 156),
            *(_DWORD *)(a1 + 160),
            v10,
            3,
            ResponseFromServer);
        goto LABEL_29;
      }
      v24 = CWSConnection::DoWaitOnAsyncEvents(
              (CWSConnection *)a1,
              *(void **)(*(_QWORD *)(a1 + 80) + 8LL),
              *(struct WINHTTP_ASYNC_CONTEXT **)(a1 + 80));
      ResponseFromServer = v24;
      if ( v24 >= 0 )
      {
LABEL_28:
        ResponseFromServer = CWSConnection::ReadResponseFromServer((CWSConnection *)a1);
        goto LABEL_29;
      }
      if ( (byte_1801E39C3 & 2) != 0 )
        McTemplateU0dqdqq_EventWriteTransfer(v26, v25, *(_DWORD *)(a1 + 156), *(_DWORD *)(a1 + 160), v10, 3, v24);
    }
  }
LABEL_29:
  operator delete(v5);
  return (unsigned int)ResponseFromServer;
}

```

## disassembly

```asm
0x18007afe0  mov     rax, rsp
0x18007afe3  mov     [rax+10h], rbx
0x18007afe7  mov     [rax+18h], rbp
0x18007afeb  mov     [rax+20h], r9
0x18007afef  push    rsi
0x18007aff0  push    rdi
0x18007aff1  push    r12
0x18007aff3  push    r14
0x18007aff5  push    r15
0x18007aff7  sub     rsp, 40h
0x18007affb  xor     ebp, ebp
0x18007affd  xor     esi, esi
0x18007afff  mov     r15d, r8d
0x18007b002  mov     r12, rdx
0x18007b005  mov     rdi, rcx
0x18007b008  mov     ebx, 80070057h
0x18007b00d  mov     [rax+20h], ebp
0x18007b010  mov     [rax+8], rsi
0x18007b014  cmp     [rcx+20h], rsi
0x18007b018  jz      loc_18007B23B
0x18007b01e  mov     rax, [rcx+50h]
0x18007b022  mov     r14, [rax+38h]
0x18007b026  mov     eax, cs:dword_1801DDF30
0x18007b02c  cmp     eax, 5
0x18007b02f  jbe     short loc_18007B044
0x18007b031  lea     rdx, unk_1801B4BC0
0x18007b038  lea     rcx, dword_1801DDF30
0x18007b03f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007b044  mov     edx, r15d
0x18007b047  mov     rcx, rdi
0x18007b04a  call    ?SetRequirements@CWSConnection@@AEAAJW4__MIDL___MIDL_itf_locationcommondata_0000_0000_0004@@@Z; CWSConnection::SetRequirements(__MIDL___MIDL_itf_locationcommondata_0000_0000_0004)
0x18007b04f  mov     ebx, eax
0x18007b051  test    eax, eax
0x18007b053  jns     short loc_18007B05E
0x18007b055  test    r15d, r15d
0x18007b058  jnz     loc_18007B23B
0x18007b05e  test    r12, r12
0x18007b061  jz      short loc_18007B09D
0x18007b063  cmp     dword ptr [rdi+0A4h], 7
0x18007b06a  lea     rax, [rsp+68h+arg_18]
0x18007b072  lea     r9, [rsp+68h+arg_0]; unsigned __int8 **
0x18007b077  mov     qword ptr [rsp+68h+dwOptionalLength], rax; unsigned int *
0x18007b07c  setnz   dl; bool
0x18007b07f  mov     r8, r12; unsigned __int16 *
0x18007b082  call    ?PreprocessPayload@CWSConnection@@AEAAJ_NPEBGPEAPEAEPEAK@Z; CWSConnection::PreprocessPayload(bool,ushort const *,uchar * *,ulong *)
0x18007b087  mov     rsi, [rsp+68h+arg_0]
0x18007b08c  mov     ebx, eax
0x18007b08e  test    eax, eax
0x18007b090  js      loc_18007B23B
0x18007b096  mov     ebp, [rsp+68h+arg_18]
0x18007b09d  mov     rcx, rdi; lpSystemTimeAsFileTime
0x18007b0a0  call    cs:__imp_GetSystemTimeAsFileTime
0x18007b0a6  mov     rax, [rdi+50h]
0x18007b0aa  xor     r9d, r9d; lpOptional
0x18007b0ad  mov     rcx, [rdi+20h]; hRequest
0x18007b0b1  xor     r8d, r8d; dwHeadersLength
0x18007b0b4  mov     [rsp+68h+dwContext], rax; dwContext
0x18007b0b9  xor     edx, edx; lpszHeaders
0x18007b0bb  mov     dword ptr [rsp+68h+dwTotalLength], ebp; char *
0x18007b0bf  mov     [rsp+68h+dwOptionalLength], 0; dwOptionalLength
0x18007b0c7  call    cs:__imp_WinHttpSendRequest
0x18007b0cd  test    eax, eax
0x18007b0cf  jnz     short loc_18007B13E
0x18007b0d1  mov     rcx, [rsp+68h]; this
0x18007b0d6  lea     rax, aWinhttpsendreq_0; "WinHttpSendRequest( m_hHttpRequestConne"...
0x18007b0dd  lea     r9, aCwsconnectionS; "CWSConnection::SendWebServiceRequest"
0x18007b0e4  mov     qword ptr [rsp+68h+dwOptionalLength], rax; char *
0x18007b0e9  mov     edx, 32Ch; void *
0x18007b0ee  call    ?_Log_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_Log_GetLastError(void *,uint,char const *,char const *,char const *)
0x18007b0f3  call    cs:__imp_GetLastError
0x18007b0f9  mov     ebx, eax
0x18007b0fb  test    eax, eax
0x18007b0fd  jle     short loc_18007B108
0x18007b0ff  movzx   ebx, ax
0x18007b102  or      ebx, 80070000h
0x18007b108  test    cs:byte_1801E39C3, 2
0x18007b10f  jz      loc_18007B23B
0x18007b115  mov     dword ptr [rsp+68h+dwContext], ebx
0x18007b119  mov     dword ptr [rsp+68h+dwTotalLength], 2
0x18007b121  mov     r9d, [rdi+0A0h]
0x18007b128  mov     r8d, [rdi+9Ch]
0x18007b12f  mov     [rsp+68h+dwOptionalLength], r14d
0x18007b134  call    McTemplateU0dqdqd_EventWriteTransfer
0x18007b139  jmp     loc_18007B23B
0x18007b13e  mov     rdx, [rdi+50h]
0x18007b142  mov     rcx, rdi; this
0x18007b145  mov     r8, rdx; struct WINHTTP_ASYNC_CONTEXT *
0x18007b148  mov     rdx, [rdx+20h]; void *
0x18007b14c  call    ?DoWaitOnAsyncEvents@CWSConnection@@AEAAJPEAXPEAUWINHTTP_ASYNC_CONTEXT@@@Z; CWSConnection::DoWaitOnAsyncEvents(void *,WINHTTP_ASYNC_CONTEXT *)
0x18007b151  mov     ebx, eax
0x18007b153  test    eax, eax
0x18007b155  jns     short loc_18007B18D
0x18007b157  test    cs:byte_1801E39C3, 2
0x18007b15e  jz      loc_18007B23B
0x18007b164  mov     dword ptr [rsp+68h+dwContext], eax
0x18007b168  mov     dword ptr [rsp+68h+dwTotalLength], 5
0x18007b170  mov     r9d, [rdi+0A0h]
0x18007b177  mov     r8d, [rdi+9Ch]
0x18007b17e  mov     [rsp+68h+dwOptionalLength], r14d
0x18007b183  call    McTemplateU0dqdqq_EventWriteTransfer
0x18007b188  jmp     loc_18007B23B
0x18007b18d  test    rsi, rsi
0x18007b190  jz      loc_18007B231
0x18007b196  mov     rcx, [rdi+20h]; hRequest
0x18007b19a  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x18007b19d  mov     r8d, ebp; dwNumberOfBytesToWrite
0x18007b1a0  mov     rdx, rsi; lpBuffer
0x18007b1a3  call    cs:__imp_WinHttpWriteData
0x18007b1a9  test    eax, eax
0x18007b1ab  jnz     short loc_18007B1FE
0x18007b1ad  mov     rcx, [rsp+68h]; this
0x18007b1b2  lea     rax, aWinhttpwriteda_0; "WinHttpWriteData( m_hHttpRequestConnect"...
0x18007b1b9  lea     r9, aCwsconnectionS; "CWSConnection::SendWebServiceRequest"
0x18007b1c0  mov     qword ptr [rsp+68h+dwOptionalLength], rax; char *
0x18007b1c5  mov     edx, 34Bh; void *
0x18007b1ca  call    ?_Log_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_Log_GetLastError(void *,uint,char const *,char const *,char const *)
0x18007b1cf  call    cs:__imp_GetLastError
0x18007b1d5  mov     ebx, eax
0x18007b1d7  test    eax, eax
0x18007b1d9  jle     short loc_18007B1E4
0x18007b1db  movzx   ebx, ax
0x18007b1de  or      ebx, 80070000h
0x18007b1e4  test    cs:byte_1801E39C3, 2
0x18007b1eb  jz      short loc_18007B23B
0x18007b1ed  mov     dword ptr [rsp+68h+dwContext], ebx
0x18007b1f1  mov     dword ptr [rsp+68h+dwTotalLength], 3
0x18007b1f9  jmp     loc_18007B121
0x18007b1fe  mov     rdx, [rdi+50h]
0x18007b202  mov     rcx, rdi; this
0x18007b205  mov     r8, rdx; struct WINHTTP_ASYNC_CONTEXT *
0x18007b208  mov     rdx, [rdx+8]; void *
0x18007b20c  call    ?DoWaitOnAsyncEvents@CWSConnection@@AEAAJPEAXPEAUWINHTTP_ASYNC_CONTEXT@@@Z; CWSConnection::DoWaitOnAsyncEvents(void *,WINHTTP_ASYNC_CONTEXT *)
0x18007b211  mov     ebx, eax
0x18007b213  test    eax, eax
0x18007b215  jns     short loc_18007B231
0x18007b217  test    cs:byte_1801E39C3, 2
0x18007b21e  jz      short loc_18007B23B
0x18007b220  mov     dword ptr [rsp+68h+dwContext], eax
0x18007b224  mov     dword ptr [rsp+68h+dwTotalLength], 3
0x18007b22c  jmp     loc_18007B170
0x18007b231  mov     rcx, rdi; this
0x18007b234  call    ?ReadResponseFromServer@CWSConnection@@AEAAJXZ; CWSConnection::ReadResponseFromServer(void)
0x18007b239  mov     ebx, eax
0x18007b23b  mov     rcx, rsi; Block
0x18007b23e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007b243  lea     r11, [rsp+68h+var_28]
0x18007b248  mov     eax, ebx
0x18007b24a  mov     rbx, [r11+38h]
0x18007b24e  mov     rbp, [r11+40h]
0x18007b252  mov     rsp, r11
0x18007b255  pop     r15
0x18007b257  pop     r14
0x18007b259  pop     r12
0x18007b25b  pop     rdi
0x18007b25c  pop     rsi
0x18007b25d  retn
```
