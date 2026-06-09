# WIPGetAndParseResponse(_WIP_AAD_REQUEST_TYPE,void *,ushort * * *,ulong * *,ulong *)

- ea: `0x1800cfe1c`
- end: `0x1800d052d`
- name: `?WIPGetAndParseResponse@@YAJW4_WIP_AAD_REQUEST_TYPE@@PEAXPEAPEAPEAGPEAPEAKPEAK@Z`
- size: `1809`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ab620`
- `0x1800baeb0`

## callees

- `0x180001a7c`
- `0x180001aa8`
- `0x180001d84`
- `0x180002700`
- `0x18004844c`
- `0x180048740`
- `0x180048b80`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x18006fb14`
- `0x1800ab00c`
- `0x1800bd9d8`
- `0x1800cf720`
- `0x1800cfe1c`
- `0x1800d0840`
- `0x1800d086c`
- `0x1800d1214`
- `0x1800d149c`
- `0x1800d1854`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d02e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d031e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d034d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d02e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d031e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d034d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d02f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d032c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d035b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d02f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d032c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d035b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cff46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cffad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cff46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cffad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800d0375`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800d0375`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d048e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d048e`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800cffa3`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800cffa3`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800cff3c`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800cff3c`

## string_xrefs

- `0x1800d008a`: `error_key_already_exists`
- `0x1800d009b`: `error_key_already_exists`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WIPGetAndParseResponse(int a1, void *a2, unsigned __int16 ***a3, LPVOID *a4, unsigned int *a5)
{
  bool IsZero; // al
  GUID *p_ActivityId; // r9
  signed int LastError; // eax
  unsigned int JsonResponse; // ebx
  signed int v13; // eax
  int HResultFromHTTPStatus; // eax
  int v15; // ecx
  unsigned __int64 v16; // rax
  __int64 v17; // rdx
  const OLECHAR *v18; // rax
  __int64 v19; // rcx
  int v20; // ecx
  int v21; // ecx
  void *v22; // rdi
  HANDLE ProcessHeap; // rax
  unsigned int i; // edi
  unsigned __int16 *v25; // r15
  HANDLE v26; // rax
  unsigned __int16 **v27; // rdi
  HANDLE v28; // rax
  __int64 v29; // r9
  __int64 v30; // rdx
  char lpdwBufferLength; // [rsp+20h] [rbp-E0h]
  unsigned int v33; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 **v34; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int Buffer; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwBufferLength; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v38; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v39; // [rsp+78h] [rbp-88h] BYREF
  BOOL v40; // [rsp+7Ch] [rbp-84h] BYREF
  BOOL v41; // [rsp+80h] [rbp-80h] BYREF
  BOOL v42; // [rsp+84h] [rbp-7Ch] BYREF
  BOOL v43; // [rsp+88h] [rbp-78h] BYREF
  HSTRING string; // [rsp+90h] [rbp-70h] BYREF
  __int128 v45; // [rsp+98h] [rbp-68h] BYREF
  int v46; // [rsp+A8h] [rbp-58h] BYREF
  char v47; // [rsp+ACh] [rbp-54h]
  _BYTE v48[16]; // [rsp+B0h] [rbp-50h] BYREF
  GUID ActivityId; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v50[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v51; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v52; // [rsp+E8h] [rbp-18h]
  _BYTE v53[32]; // [rsp+F0h] [rbp-10h] BYREF
  const OLECHAR *v54; // [rsp+110h] [rbp+10h]
  int v55; // [rsp+118h] [rbp+18h]
  int v56; // [rsp+11Ch] [rbp+1Ch]

  Buffer = 0;
  dwBufferLength = 4;
  v45 = 0;
  string = 0;
  v34 = 0;
  lpMem = 0;
  v33 = 0;
  v52 = 7;
  v51 = 0;
  LOWORD(v50[0]) = 0;
  fnEfsLogTrace1Strings(a1, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 46, 89);
  v46 = 0;
  v47 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hEfsCoreTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v46);
  if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
  {
    if ( !v47 || (IsZero = _tlgGuidIsZero(&ActivityId), p_ActivityId = &ActivityId, IsZero) )
      p_ActivityId = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180114250,
      (__int64)&dword_180103A34,
      (__int64)v48,
      (__int64)p_ActivityId);
  }
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !WinHttpReceiveResponse(a2, 0) )
  {
    LastError = GetLastError();
    JsonResponse = LastError;
    if ( LastError > 0 )
      JsonResponse = (unsigned __int16)LastError | 0x80070000;
    lpdwBufferLength = 110;
LABEL_17:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, JsonResponse, 46, lpdwBufferLength);
    goto LABEL_58;
  }
  if ( !WinHttpQueryHeaders(a2, 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
  {
    v13 = GetLastError();
    JsonResponse = v13;
    if ( v13 > 0 )
      JsonResponse = (unsigned __int16)v13 | 0x80070000;
    lpdwBufferLength = 121;
    goto LABEL_17;
  }
  HResultFromHTTPStatus = GetHResultFromHTTPStatus(Buffer);
  JsonResponse = HResultFromHTTPStatus;
  if ( HResultFromHTTPStatus >= 0 )
  {
    fnEfsLogTrace1Strings(v15, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 46, 171);
    JsonResponse = WipJsonObject::LoadJsonResponse((WipJsonObject *)&v45, a2);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                JsonResponse,
                46,
                171) >= 0
      && (unsigned int)(a1 - 1) <= 1 )
    {
      fnEfsLogTrace1Strings(v21, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 46, 177);
      JsonResponse = WipJsonObject::GetArrayOfWipKeyObjects((WipJsonObject *)&v45, &v34, (unsigned int **)&lpMem, &v33);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  JsonResponse,
                  46,
                  177) >= 0 )
      {
        if ( a1 == 2 )
        {
          if ( !v33 )
            fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_MSG_TRACE_EVENT,
              (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
              (unsigned int)L"WIP auto-recovery: Get keys request returned less than 1 credential",
              0,
              46,
              187);
        }
        else if ( a1 == 1 && v33 != 1 )
        {
          fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
            (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
            (unsigned int)L"WIP auto-recovery: Get specific key request did not return exactly 1 credential",
            v33,
            46,
            198);
          JsonResponse = -2147418113;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 46, 199);
          goto LABEL_58;
        }
        if ( a5 )
          *a5 = v33;
        if ( a3 )
        {
          *a3 = v34;
          v34 = 0;
        }
        if ( a4 )
        {
          *a4 = lpMem;
          lpMem = 0;
        }
      }
    }
  }
  else if ( HResultFromHTTPStatus == -2147024883 || HResultFromHTTPStatus == -2147024637 )
  {
    if ( WipJsonObject::LoadJsonResponse((WipJsonObject *)&v45, a2) >= 0 )
    {
      WipJsonObject::ToString((WipJsonObject *)&v45, (struct Microsoft::WRL::Wrappers::HString *)&string);
      WipJsonObject::GetSubcodeString(&v45, v50);
      v16 = std::char_traits<unsigned short>::length(L"error_key_already_exists");
      if ( !(unsigned int)std::wstring::compare(v50, v17, v51, L"error_key_already_exists", v16) )
      {
        JsonResponse = 0;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 46, 144);
      }
      if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
      {
        v18 = (const OLECHAR *)v50;
        if ( v52 >= 8 )
          v18 = (const OLECHAR *)v50[0];
        if ( v18 )
        {
          v19 = -1;
          do
            ++v19;
          while ( v18[v19] );
          v20 = 2 * v19 + 2;
        }
        else
        {
          v18 = &sourceString;
          v20 = 2;
        }
        v54 = v18;
        v55 = v20;
        v56 = 0;
        tlgWriteTransfer_EventWriteTransfer(&dword_180114250, &word_180103A56, v48, 0, 3, v53);
      }
    }
  }
  else
  {
    switch ( a1 )
    {
      case 3:
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
          (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
          (unsigned int)L"WIP auto-recovery: Backup request failed",
          HResultFromHTTPStatus,
          46,
          156);
        break;
      case 1:
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
          (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
          (unsigned int)L"WIP auto-recovery: Get specific key request failed",
          HResultFromHTTPStatus,
          46,
          160);
        break;
      case 2:
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
          (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
          (unsigned int)L"WIP auto-recovery: Get all keys request failed",
          HResultFromHTTPStatus,
          46,
          164);
        break;
    }
  }
LABEL_58:
  v22 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
    lpMem = 0;
  }
  if ( v34 )
  {
    for ( i = 0; i < v33; ++i )
    {
      v25 = v34[i];
      if ( v25 )
      {
        v26 = GetProcessHeap();
        HeapFree(v26, 0, v25);
        v34[i] = 0;
      }
    }
    v27 = v34;
    if ( v34 )
    {
      v28 = GetProcessHeap();
      HeapFree(v28, 0, v27);
      v34 = 0;
    }
  }
  if ( v47 )
    EventActivityIdControl(4u, &ActivityId);
  v46 = 2;
  if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
  {
    v38 = JsonResponse;
    v39 = Buffer;
    v40 = a1 == 0;
    v41 = a1 == 3;
    v42 = a1 == 2;
    v43 = a1 == 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180114250,
      (__int64)byte_1801039B5,
      (__int64)v48,
      v29,
      (__int64)&v43,
      (__int64)&v42,
      (__int64)&v41,
      (__int64)&v40,
      (__int64)&v39,
      (__int64)&v38);
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    JsonResponse,
    46,
    245);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hEfsCoreTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hEfsCoreTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v46);
  LOBYTE(v30) = 1;
  std::wstring::_Tidy(v50, v30, 0);
  WindowsDeleteString(string);
  string = 0;
  WipJsonObject::~WipJsonObject((WipJsonObject *)&v45);
  return JsonResponse;
}

```

## disassembly

```asm
0x1800cfe1c  mov     [rsp-8+arg_0], rbx
0x1800cfe21  push    rbp
0x1800cfe22  push    rsi
0x1800cfe23  push    rdi
0x1800cfe24  push    r12
0x1800cfe26  push    r13
0x1800cfe28  push    r14
0x1800cfe2a  push    r15
0x1800cfe2c  lea     rbp, [rsp-30h]
0x1800cfe31  sub     rsp, 130h
0x1800cfe38  mov     rax, cs:__security_cookie
0x1800cfe3f  xor     rax, rsp
0x1800cfe42  mov     [rbp+60h+var_40], rax
0x1800cfe46  mov     r15, r9
0x1800cfe49  mov     r14, r8
0x1800cfe4c  mov     r12, rdx
0x1800cfe4f  mov     esi, ecx
0x1800cfe51  mov     rdi, [rbp+60h+arg_20]
0x1800cfe58  xor     r13d, r13d
0x1800cfe5b  mov     [rsp+160h+Buffer], r13d
0x1800cfe60  mov     [rsp+160h+dwBufferLength], 4
0x1800cfe68  xorps   xmm0, xmm0
0x1800cfe6b  movdqu  [rbp+60h+var_C8], xmm0
0x1800cfe70  mov     [rbp+60h+string], r13
0x1800cfe74  mov     [rsp+160h+var_108], r13
0x1800cfe79  mov     [rsp+160h+lpMem], r13
0x1800cfe7e  mov     [rsp+160h+var_110], r13d
0x1800cfe83  mov     [rbp+60h+var_78], 7
0x1800cfe8b  mov     [rbp+60h+var_80], r13
0x1800cfe8f  mov     word ptr [rbp+60h+var_90], r13w
0x1800cfe94  mov     dword ptr [rsp+160h+lpdwBufferLength], 559h
0x1800cfe9c  lea     r9d, [r13+2Eh]
0x1800cfea0  lea     r8, sourceString
0x1800cfea7  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800cfeae  call    fnEfsLogTrace1Strings
0x1800cfeb3  mov     [rbp+60h+var_B8], r13d
0x1800cfeb7  mov     [rbp+60h+var_B4], r13b
0x1800cfebb  lea     rcx, [rbp+60h+var_B8]
0x1800cfebf  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hEfsCoreTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hEfsCoreTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x1800cfec4  mov     eax, cs:dword_180114250
0x1800cfeca  cmp     eax, 5
0x1800cfecd  jbe     short loc_1800CFF1A
0x1800cfecf  mov     rdx, 400000000000h
0x1800cfed9  lea     rcx, dword_180114250
0x1800cfee0  call    _tlgKeywordOn
0x1800cfee5  test    al, al
0x1800cfee7  jz      short loc_1800CFF1A
0x1800cfee9  cmp     [rbp+60h+var_B4], r13b
0x1800cfeed  jz      short loc_1800CFF00
0x1800cfeef  lea     rcx, [rbp+60h+ActivityId]; struct _GUID *
0x1800cfef3  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800cfef8  test    al, al
0x1800cfefa  lea     r9, [rbp+60h+ActivityId]
0x1800cfefe  jz      short loc_1800CFF03
0x1800cff00  mov     r9, r13
0x1800cff03  lea     r8, [rbp+60h+var_B0]
0x1800cff07  lea     rdx, dword_180103A34
0x1800cff0e  lea     rcx, dword_180114250
0x1800cff15  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800cff1a  test    r14, r14
0x1800cff1d  jz      short loc_1800CFF24
0x1800cff1f  xor     eax, eax
0x1800cff21  mov     [r14], rax
0x1800cff24  test    r15, r15
0x1800cff27  jz      short loc_1800CFF2E
0x1800cff29  xor     eax, eax
0x1800cff2b  mov     [r15], rax
0x1800cff2e  test    rdi, rdi
0x1800cff31  jz      short loc_1800CFF37
0x1800cff33  xor     eax, eax
0x1800cff35  mov     [rdi], eax
0x1800cff37  xor     edx, edx; lpReserved
0x1800cff39  mov     rcx, r12; hRequest
0x1800cff3c  call    cs:__imp_WinHttpReceiveResponse
0x1800cff42  test    eax, eax
0x1800cff44  jnz     short loc_1800CFF84
0x1800cff46  call    cs:__imp_GetLastError
0x1800cff4c  mov     ebx, eax
0x1800cff4e  test    eax, eax
0x1800cff50  jle     short loc_1800CFF5B
0x1800cff52  movzx   ebx, ax
0x1800cff55  or      ebx, 80070000h
0x1800cff5b  mov     dword ptr [rsp+160h+lpdwBufferLength], 56Eh
0x1800cff63  mov     r8d, ebx
0x1800cff66  mov     r9d, 2Eh ; '.'
0x1800cff6c  lea     rdx, EFS_TRACE_ERROR
0x1800cff73  mov     rcx, cs:g_hPublisher
0x1800cff7a  call    fnEfsLogTrace1
0x1800cff7f  jmp     loc_1800D02D9
0x1800cff84  mov     [rsp+160h+lpdwIndex], r13; lpdwIndex
0x1800cff89  lea     rax, [rsp+160h+dwBufferLength]
0x1800cff8e  mov     [rsp+160h+lpdwBufferLength], rax; lpdwBufferLength
0x1800cff93  lea     r9, [rsp+160h+Buffer]; lpBuffer
0x1800cff98  xor     r8d, r8d; pwszName
0x1800cff9b  mov     edx, 20000013h; dwInfoLevel
0x1800cffa0  mov     rcx, r12; hRequest
0x1800cffa3  call    cs:__imp_WinHttpQueryHeaders
0x1800cffa9  test    eax, eax
0x1800cffab  jnz     short loc_1800CFFCC
0x1800cffad  call    cs:__imp_GetLastError
0x1800cffb3  mov     ebx, eax
0x1800cffb5  test    eax, eax
0x1800cffb7  jle     short loc_1800CFFC2
0x1800cffb9  movzx   ebx, ax
0x1800cffbc  or      ebx, 80070000h
0x1800cffc2  mov     dword ptr [rsp+160h+lpdwBufferLength], 579h
0x1800cffca  jmp     short loc_1800CFF63
0x1800cffcc  mov     ecx, [rsp+160h+Buffer]; unsigned int
0x1800cffd0  call    ?GetHResultFromHTTPStatus@@YAJK@Z; GetHResultFromHTTPStatus(ulong)
0x1800cffd5  mov     ebx, eax
0x1800cffd7  test    eax, eax
0x1800cffd9  jns     loc_1800D0176
0x1800cffdf  cmp     eax, 8007000Dh
0x1800cffe4  jz      short loc_1800D005C
0x1800cffe6  cmp     eax, 80070103h
0x1800cffeb  jz      short loc_1800D005C
0x1800cffed  cmp     esi, 3
0x1800cfff0  jnz     short loc_1800D0003
0x1800cfff2  mov     dword ptr [rsp+160h+var_130], 59Ch
0x1800cfffa  lea     r9, aWipAutoRecover_2; "WIP auto-recovery: Backup request faile"...
0x1800d0001  jmp     short loc_1800D0017
0x1800d0003  cmp     esi, 1
0x1800d0006  jnz     short loc_1800D0042
0x1800d0008  mov     dword ptr [rsp+160h+var_130], 5A0h
0x1800d0010  lea     r9, aWipAutoRecover_1; "WIP auto-recovery: Get specific key req"...
0x1800d0017  mov     dword ptr [rsp+160h+lpdwIndex], 2Eh ; '.'
0x1800d001f  mov     dword ptr [rsp+160h+lpdwBufferLength], eax
0x1800d0023  lea     r8, EFS_TRACE_MSG_ERROR_EVENT
0x1800d002a  lea     rdx, EFS_TRACE_MSG_ERROR_EVENT
0x1800d0031  mov     rcx, cs:g_hPublisher
0x1800d0038  call    fnEfsLogTrace1String1Dword
0x1800d003d  jmp     loc_1800D02D9
0x1800d0042  cmp     esi, 2
0x1800d0045  jnz     loc_1800D02D9
0x1800d004b  mov     dword ptr [rsp+160h+var_130], 5A4h
0x1800d0053  lea     r9, aWipAutoRecover; "WIP auto-recovery: Get all keys request"...
0x1800d005a  jmp     short loc_1800D0017
0x1800d005c  mov     rdx, r12; void *
0x1800d005f  lea     rcx, [rbp+60h+var_C8]; this
0x1800d0063  call    ?LoadJsonResponse@WipJsonObject@@QEAAJPEAX@Z; WipJsonObject::LoadJsonResponse(void *)
0x1800d0068  test    eax, eax
0x1800d006a  js      loc_1800D02D9
0x1800d0070  lea     rdx, [rbp+60h+string]; struct Microsoft::WRL::Wrappers::HString *
0x1800d0074  lea     rcx, [rbp+60h+var_C8]; this
0x1800d0078  call    ?ToString@WipJsonObject@@QEAAJAEAVHString@Wrappers@WRL@Microsoft@@@Z; WipJsonObject::ToString(Microsoft::WRL::Wrappers::HString &)
0x1800d007d  lea     rdx, [rbp+60h+var_90]
0x1800d0081  lea     rcx, [rbp+60h+var_C8]
0x1800d0085  call    ?GetSubcodeString@WipJsonObject@@QEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WipJsonObject::GetSubcodeString(std::wstring *)
0x1800d008a  lea     rcx, aErrorKeyAlread; "error_key_already_exists"
0x1800d0091  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1800d0096  mov     [rsp+160h+lpdwBufferLength], rax
0x1800d009b  lea     r9, aErrorKeyAlread; "error_key_already_exists"
0x1800d00a2  mov     r8, [rbp+60h+var_80]
0x1800d00a6  lea     rcx, [rbp+60h+var_90]
0x1800d00aa  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0PEBG0@Z; std::wstring::compare(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x1800d00af  test    eax, eax
0x1800d00b1  jnz     short loc_1800D00D8
0x1800d00b3  mov     ebx, r13d
0x1800d00b6  mov     dword ptr [rsp+160h+lpdwBufferLength], 590h
0x1800d00be  lea     r9d, [rax+2Eh]
0x1800d00c2  xor     r8d, r8d
0x1800d00c5  lea     rdx, EFS_TRACE_STATUS
0x1800d00cc  mov     rcx, cs:g_hPublisher
0x1800d00d3  call    fnEfsLogTrace1
0x1800d00d8  mov     eax, cs:dword_180114250
0x1800d00de  cmp     eax, 5
0x1800d00e1  jbe     loc_1800D02D9
0x1800d00e7  mov     rdx, 400000000000h
0x1800d00f1  lea     rcx, dword_180114250
0x1800d00f8  call    _tlgKeywordOn
0x1800d00fd  test    al, al
0x1800d00ff  jz      loc_1800D02D9
0x1800d0105  lea     rax, [rbp+60h+var_90]
0x1800d0109  cmp     [rbp+60h+var_78], 8
0x1800d010e  cmovnb  rax, [rbp+60h+var_90]
0x1800d0113  test    rax, rax
0x1800d0116  jz      short loc_1800D012F
0x1800d0118  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800d011c  inc     rcx
0x1800d011f  cmp     [rax+rcx*2], r13w
0x1800d0124  jnz     short loc_1800D011C
0x1800d0126  lea     ecx, ds:2[rcx*2]
0x1800d012d  jmp     short loc_1800D013B
0x1800d012f  lea     rax, sourceString
0x1800d0136  mov     ecx, 2
0x1800d013b  mov     [rbp+60h+var_50], rax
0x1800d013f  mov     [rbp+60h+var_48], ecx
0x1800d0142  mov     [rbp+60h+var_44], r13d
0x1800d0146  lea     rax, [rbp+60h+var_70]
0x1800d014a  mov     [rsp+160h+lpdwIndex], rax
0x1800d014f  mov     dword ptr [rsp+160h+lpdwBufferLength], 3
0x1800d0157  xor     r9d, r9d
0x1800d015a  lea     r8, [rbp+60h+var_B0]
0x1800d015e  lea     rdx, word_180103A56
0x1800d0165  lea     rcx, dword_180114250
0x1800d016c  call    _tlgWriteTransfer_EventWriteTransfer
0x1800d0171  jmp     loc_1800D02D9
0x1800d0176  mov     r13d, 5ABh
0x1800d017c  mov     dword ptr [rsp+160h+lpdwBufferLength], r13d
0x1800d0181  mov     r9d, 2Eh ; '.'
0x1800d0187  lea     r8, sourceString
0x1800d018e  lea     rdx, EFS_TRACE_START_EVENT
0x1800d0195  call    fnEfsLogTrace1Strings
0x1800d019a  mov     rdx, r12; void *
0x1800d019d  lea     rcx, [rbp+60h+var_C8]; this
0x1800d01a1  call    ?LoadJsonResponse@WipJsonObject@@QEAAJPEAX@Z; WipJsonObject::LoadJsonResponse(void *)
0x1800d01a6  mov     ebx, eax
0x1800d01a8  mov     dword ptr [rsp+160h+var_130], r13d
0x1800d01ad  mov     dword ptr [rsp+160h+lpdwIndex], 2Eh ; '.'
0x1800d01b5  mov     dword ptr [rsp+160h+lpdwBufferLength], eax
0x1800d01b9  lea     r9, sourceString
0x1800d01c0  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800d01c7  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800d01ce  mov     rcx, cs:g_hPublisher
0x1800d01d5  call    fnEfsLogTrace1String1Dword
0x1800d01da  xor     r13d, r13d
0x1800d01dd  test    eax, eax
0x1800d01df  js      loc_1800D02D9
0x1800d01e5  lea     eax, [rsi-1]
0x1800d01e8  cmp     eax, 1
0x1800d01eb  ja      loc_1800D02D9
0x1800d01f1  mov     r12d, 5B1h
0x1800d01f7  mov     dword ptr [rsp+160h+lpdwBufferLength], r12d
0x1800d01fc  lea     r9d, [r13+2Eh]
0x1800d0200  lea     r8, sourceString
0x1800d0207  lea     rdx, EFS_TRACE_START_EVENT
0x1800d020e  call    fnEfsLogTrace1Strings
0x1800d0213  lea     r9, [rsp+160h+var_110]; unsigned int *
0x1800d0218  lea     r8, [rsp+160h+lpMem]; unsigned int **
0x1800d021d  lea     rdx, [rsp+160h+var_108]; unsigned __int16 ***
0x1800d0222  lea     rcx, [rbp+60h+var_C8]; this
0x1800d0226  call    ?GetArrayOfWipKeyObjects@WipJsonObject@@QEAAJPEAPEAPEAGPEAPEAKPEAK@Z; WipJsonObject::GetArrayOfWipKeyObjects(ushort * * *,ulong * *,ulong *)
0x1800d022b  mov     ebx, eax
0x1800d022d  mov     dword ptr [rsp+160h+var_130], r12d
0x1800d0232  mov     dword ptr [rsp+160h+lpdwIndex], 2Eh ; '.'
0x1800d023a  mov     dword ptr [rsp+160h+lpdwBufferLength], eax
0x1800d023e  lea     r9, sourceString
0x1800d0245  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800d024c  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800d0253  mov     rcx, cs:g_hPublisher
0x1800d025a  call    fnEfsLogTrace1String1Dword
0x1800d025f  test    eax, eax
0x1800d0261  js      short loc_1800D02D9
0x1800d0263  cmp     esi, 2
0x1800d0266  jnz     loc_1800D04CA
0x1800d026c  mov     eax, [rsp+160h+var_110]
0x1800d0270  cmp     eax, 1
0x1800d0273  jnb     short loc_1800D02AA
0x1800d0275  mov     dword ptr [rsp+160h+var_130], 5BBh
0x1800d027d  mov     dword ptr [rsp+160h+lpdwIndex], 2Eh ; '.'
0x1800d0285  mov     dword ptr [rsp+160h+lpdwBufferLength], eax
0x1800d0289  lea     r9, aWipAutoRecover_3; "WIP auto-recovery: Get keys request ret"...
0x1800d0290  lea     r8, EFS_TRACE_MSG_ERROR_EVENT
0x1800d0297  lea     rdx, EFS_TRACE_MSG_TRACE_EVENT
0x1800d029e  mov     rcx, cs:g_hPublisher
0x1800d02a5  call    fnEfsLogTrace1String1Dword
0x1800d02aa  test    rdi, rdi
0x1800d02ad  jz      short loc_1800D02B5
0x1800d02af  mov     eax, [rsp+160h+var_110]
0x1800d02b3  mov     [rdi], eax
0x1800d02b5  test    r14, r14
0x1800d02b8  jz      short loc_1800D02C7
0x1800d02ba  mov     rax, [rsp+160h+var_108]
0x1800d02bf  mov     [r14], rax
0x1800d02c2  mov     [rsp+160h+var_108], r13
0x1800d02c7  test    r15, r15
0x1800d02ca  jz      short loc_1800D02D9
0x1800d02cc  mov     rax, [rsp+160h+lpMem]
0x1800d02d1  mov     [r15], rax
0x1800d02d4  mov     [rsp+160h+lpMem], r13
0x1800d02d9  mov     rdi, [rsp+160h+lpMem]
0x1800d02de  test    rdi, rdi
0x1800d02e1  jz      short loc_1800D02FC
0x1800d02e3  call    cs:__imp_GetProcessHeap
0x1800d02e9  mov     r8, rdi; lpMem
0x1800d02ec  xor     edx, edx; dwFlags
0x1800d02ee  mov     rcx, rax; hHeap
0x1800d02f1  call    cs:__imp_HeapFree
0x1800d02f7  mov     [rsp+160h+lpMem], r13
0x1800d02fc  cmp     [rsp+160h+var_108], r13
0x1800d0301  jz      short loc_1800D0366
0x1800d0303  mov     edi, r13d
0x1800d0306  cmp     [rsp+160h+var_110], r13d
0x1800d030b  jbe     short loc_1800D0343
0x1800d030d  mov     r14d, edi
0x1800d0310  mov     rax, [rsp+160h+var_108]
0x1800d0315  mov     r15, [rax+r14*8]
0x1800d0319  test    r15, r15
0x1800d031c  jz      short loc_1800D033B
0x1800d031e  call    cs:__imp_GetProcessHeap
0x1800d0324  mov     r8, r15; lpMem
0x1800d0327  xor     edx, edx; dwFlags
0x1800d0329  mov     rcx, rax; hHeap
0x1800d032c  call    cs:__imp_HeapFree
0x1800d0332  mov     rax, [rsp+160h+var_108]
0x1800d0337  mov     [rax+r14*8], r13
0x1800d033b  inc     edi
0x1800d033d  cmp     edi, [rsp+160h+var_110]
0x1800d0341  jb      short loc_1800D030D
0x1800d0343  mov     rdi, [rsp+160h+var_108]
  ... truncated ...
```
