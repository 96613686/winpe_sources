# PhoneController::_DetermineAudioRoutingOverrideFromSettings(PhoneAudioEndpoint *)

- ea: `0x1800370b4`
- end: `0x180037235`
- name: `?_DetermineAudioRoutingOverrideFromSettings@PhoneController@@AEAAJPEAW4PhoneAudioEndpoint@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, enum PhoneAudioEndpoint *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800380bc`

## callees

- `0x18000151c`
- `0x1800271f4`
- `0x18002c574`
- `0x18002c580`
- `0x1800370b4`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800370d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800370f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800371af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800371cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800370d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800370f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800371af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800371cf`

## string_xrefs

- `0x1800370eb`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037132`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037194`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800371c3`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037150`: `PhoneController: Attempting audio routing`

## pseudocode

```c
__int64 __fastcall PhoneController::_DetermineAudioRoutingOverrideFromSettings(
        PhoneController *this,
        enum PhoneAudioEndpoint *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // ebx
  int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v15; // [rsp+30h] [rbp-20h] BYREF
  const char *v16; // [rsp+38h] [rbp-18h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3868);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v5 = *((_QWORD *)this + 61) + 696LL;
  v15 = 0;
  v6 = ConfigValueWithDefault<unsigned long>::Get(v5, &v15);
  if ( v6 < 0 )
    Log_HREvent_7((unsigned int)v6, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3872);
  v10 = v15;
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    v16 = "PhoneController: Attempting audio routing";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v7,
      (int)&dword_1800A8324,
      v8,
      v9,
      (const unsigned __int16 **)&v16,
      (__int64)&v15);
  }
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 == 1 )
      {
        *(_DWORD *)a2 = 1;
      }
      else
      {
        Log_AssertionEvent_3(v7, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3908);
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
    }
    else
    {
      if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      {
        Log_AssertionEvent_3(v12, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3855);
        if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
          MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      v13 = *((_QWORD *)this + 59);
      LODWORD(v16) = 0;
      v15 = 0;
      (*(void (__fastcall **)(__int64, const char **, int *))(*(_QWORD *)v13 + 48LL))(v13, &v16, &v15);
      if ( (v15 & 4) != 0 )
        *(_DWORD *)a2 = 2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800370b4  mov     [rsp-18h+arg_10], rbx
0x1800370b9  push    rbp
0x1800370ba  push    rsi
0x1800370bb  push    rdi
0x1800370bc  mov     rbp, rsp
0x1800370bf  sub     rsp, 50h
0x1800370c3  mov     rax, cs:__security_cookie
0x1800370ca  xor     rax, rsp
0x1800370cd  mov     [rbp+var_10], rax
0x1800370d1  mov     rsi, rdx
0x1800370d4  mov     rdi, rcx
0x1800370d7  call    cs:__imp_GetCurrentThreadId
0x1800370dd  cmp     [rdi+0F0h], eax
0x1800370e3  jz      short loc_18003710A
0x1800370e5  mov     r8d, 0F1Ch
0x1800370eb  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800370f2  call    Log_AssertionEvent_3
0x1800370f7  call    cs:__imp_GetCurrentThreadId
0x1800370fd  cmp     [rdi+0F0h], eax
0x180037103  jz      short loc_18003710A
0x180037105  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003710a  mov     rcx, [rdi+1E8h]
0x180037111  lea     rdx, [rbp+var_20]
0x180037115  add     rcx, 2B8h
0x18003711c  mov     [rbp+var_20], 0
0x180037123  call    ?Get@?$ConfigValueWithDefault@K@@QEAAJPEAK@Z; ConfigValueWithDefault<ulong>::Get(ulong *)
0x180037128  test    eax, eax
0x18003712a  jns     short loc_180037142
0x18003712c  mov     r9d, 0F20h
0x180037132  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180037139  xor     edx, edx
0x18003713b  mov     ecx, eax
0x18003713d  call    Log_HREvent_7
0x180037142  mov     eax, cs:dword_1800B3200
0x180037148  mov     ebx, [rbp+var_20]
0x18003714b  cmp     eax, 4
0x18003714e  jbe     short loc_18003717C
0x180037150  lea     rax, aPhonecontrolle_122; "PhoneController: Attempting audio routi"...
0x180037157  mov     [rbp+var_20], ebx
0x18003715a  mov     [rbp+var_18], rax
0x18003715e  lea     rdx, dword_1800A8324
0x180037165  lea     rax, [rbp+var_20]
0x180037169  mov     [rsp+50h+var_28], rax
0x18003716e  lea     rax, [rbp+var_18]
0x180037172  mov     [rsp+50h+var_30], rax
0x180037177  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003717c  test    ebx, ebx
0x18003717e  jz      loc_180037217
0x180037184  sub     ebx, 1
0x180037187  jz      short loc_1800371AF
0x180037189  cmp     ebx, 1
0x18003718c  jz      short loc_1800371A7
0x18003718e  mov     r8d, 0F44h
0x180037194  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003719b  call    Log_AssertionEvent_3
0x1800371a0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800371a5  jmp     short loc_180037217
0x1800371a7  mov     dword ptr [rsi], 1
0x1800371ad  jmp     short loc_180037217
0x1800371af  call    cs:__imp_GetCurrentThreadId
0x1800371b5  cmp     [rdi+0F0h], eax
0x1800371bb  jz      short loc_1800371E2
0x1800371bd  mov     r8d, 0F0Fh
0x1800371c3  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800371ca  call    Log_AssertionEvent_3
0x1800371cf  call    cs:__imp_GetCurrentThreadId
0x1800371d5  cmp     [rdi+0F0h], eax
0x1800371db  jz      short loc_1800371E2
0x1800371dd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800371e2  mov     rcx, [rdi+1D8h]
0x1800371e9  lea     r8, [rbp+var_20]
0x1800371ed  mov     dword ptr [rbp+var_18], 0
0x1800371f4  lea     rdx, [rbp+var_18]
0x1800371f8  mov     [rbp+var_20], 0
0x1800371ff  mov     rax, [rcx]
0x180037202  mov     rax, [rax+30h]
0x180037206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003720b  test    byte ptr [rbp+var_20], 4
0x18003720f  jz      short loc_180037217
0x180037211  mov     dword ptr [rsi], 2
0x180037217  xor     eax, eax
0x180037219  mov     rcx, [rbp+var_10]
0x18003721d  xor     rcx, rsp; StackCookie
0x180037220  call    __security_check_cookie
0x180037225  mov     rbx, [rsp+50h+arg_10]
0x18003722d  add     rsp, 50h
0x180037231  pop     rdi
0x180037232  pop     rsi
0x180037233  pop     rbp
0x180037234  retn
```
