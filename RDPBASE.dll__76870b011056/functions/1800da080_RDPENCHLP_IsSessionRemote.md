# RDPENCHLP_IsSessionRemote

- ea: `0x1800da080`
- end: `0x1800da1d1`
- name: `RDPENCHLP_IsSessionRemote`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x1800018a4`
- `0x180004970`
- `0x1800da080`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800da125`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800da125`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800da119`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800da119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da14d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da14d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800da090`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800da090`

## pseudocode

```c
__int64 RDPENCHLP_IsSessionRemote()
{
  unsigned int v0; // edi
  int v1; // ecx
  DWORD active; // ebx
  int v3; // r8d
  int v4; // r9d
  DWORD CurrentProcessId; // eax
  DWORD LastError; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  const char *v11; // [rsp+50h] [rbp-20h] BYREF
  const char *v12; // [rsp+58h] [rbp-18h] BYREF
  const char *v13; // [rsp+60h] [rbp-10h] BYREF
  DWORD pSessionId; // [rsp+90h] [rbp+20h] BYREF
  int v15; // [rsp+98h] [rbp+28h] BYREF
  int v16; // [rsp+A0h] [rbp+30h] BYREF
  const char *v17; // [rsp+A8h] [rbp+38h] BYREF

  v0 = 0;
  pSessionId = 0;
  active = WTSGetActiveConsoleSessionId();
  if ( active == -1 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v15 = 462;
      v17 = "RDPENCHLP_IsSessionRemote";
      v16 = -2147467259;
      v11 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enchlpr\\encdskhlp.cpp";
      v12 = "cannot determine state";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v1,
        (unsigned int)&word_1801BB90E,
        v3,
        v4,
        (__int64)&v12,
        (__int64)&v16,
        (__int64)&v11,
        (__int64)&v15,
        (__int64)&v17);
    }
  }
  else
  {
    CurrentProcessId = GetCurrentProcessId();
    if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    {
      return pSessionId != active;
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      LastError = GetLastError();
      v16 = 474;
      v15 = LastError;
      v12 = "RDPENCHLP_IsSessionRemote";
      v11 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enchlpr\\encdskhlp.cpp";
      v13 = "Failed to get the process session ID (%d)";
      LODWORD(v17) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)byte_1801BB8B9,
        v8,
        v9,
        (__int64)&v13,
        (__int64)&v17,
        (__int64)&v11,
        (__int64)&v16,
        (__int64)&v12,
        (__int64)&v15);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800da080  push    rbp
0x1800da082  push    rbx
0x1800da083  push    rdi
0x1800da084  mov     rbp, rsp
0x1800da087  sub     rsp, 70h
0x1800da08b  xor     edi, edi
0x1800da08d  mov     [rbp+pSessionId], edi
0x1800da090  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800da096  mov     ebx, eax
0x1800da098  cmp     eax, 0FFFFFFFFh
0x1800da09b  jnz     short loc_1800DA119
0x1800da09d  mov     eax, cs:CallbackContext
0x1800da0a3  cmp     eax, 2
0x1800da0a6  jbe     loc_1800DA1C7
0x1800da0ac  lea     rax, aRdpenchlpIsses_2; "RDPENCHLP_IsSessionRemote"
0x1800da0b3  mov     [rbp+arg_8], 1CEh
0x1800da0ba  mov     [rbp+arg_18], rax
0x1800da0be  lea     rdx, word_1801BB90E
0x1800da0c5  lea     rax, aOnecoreTermsrv_48; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800da0cc  mov     [rbp+arg_10], 80004005h
0x1800da0d3  mov     [rbp+var_20], rax
0x1800da0d7  lea     rax, aCannotDetermin; "cannot determine state"
0x1800da0de  mov     [rbp+var_18], rax
0x1800da0e2  lea     rax, [rbp+arg_18]
0x1800da0e6  mov     [rsp+70h+var_30], rax
0x1800da0eb  lea     rax, [rbp+arg_8]
0x1800da0ef  mov     [rsp+70h+var_38], rax
0x1800da0f4  lea     rax, [rbp+var_20]
0x1800da0f8  mov     [rsp+70h+var_40], rax
0x1800da0fd  lea     rax, [rbp+arg_10]
0x1800da101  mov     [rsp+70h+var_48], rax
0x1800da106  lea     rax, [rbp+var_18]
0x1800da10a  mov     [rsp+70h+var_50], rax
0x1800da10f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800da114  jmp     loc_1800DA1C7
0x1800da119  call    cs:__imp_GetCurrentProcessId
0x1800da11f  mov     ecx, eax; dwProcessId
0x1800da121  lea     rdx, [rbp+pSessionId]; pSessionId
0x1800da125  call    cs:__imp_ProcessIdToSessionId
0x1800da12b  test    eax, eax
0x1800da12d  jz      short loc_1800DA142
0x1800da12f  cmp     [rbp+pSessionId], ebx
0x1800da132  jz      loc_1800DA1C7
0x1800da138  mov     edi, 1
0x1800da13d  jmp     loc_1800DA1C7
0x1800da142  mov     eax, cs:CallbackContext
0x1800da148  cmp     eax, 2
0x1800da14b  jbe     short loc_1800DA1C7
0x1800da14d  call    cs:__imp_GetLastError
0x1800da153  lea     rdx, byte_1801BB8B9
0x1800da15a  mov     [rbp+arg_10], 1DAh
0x1800da161  mov     [rbp+arg_8], eax
0x1800da164  lea     rax, aRdpenchlpIsses_2; "RDPENCHLP_IsSessionRemote"
0x1800da16b  mov     [rbp+var_18], rax
0x1800da16f  lea     rax, aOnecoreTermsrv_48; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800da176  mov     [rbp+var_20], rax
0x1800da17a  lea     rax, aFailedToGetThe_9; "Failed to get the process session ID (%"...
0x1800da181  mov     [rbp+var_10], rax
0x1800da185  lea     rax, [rbp+arg_8]
0x1800da189  mov     [rsp+70h+var_28], rax
0x1800da18e  lea     rax, [rbp+var_18]
0x1800da192  mov     [rsp+70h+var_30], rax
0x1800da197  lea     rax, [rbp+arg_10]
0x1800da19b  mov     [rsp+70h+var_38], rax
0x1800da1a0  lea     rax, [rbp+var_20]
0x1800da1a4  mov     [rsp+70h+var_40], rax
0x1800da1a9  lea     rax, [rbp+arg_18]
0x1800da1ad  mov     [rsp+70h+var_48], rax
0x1800da1b2  lea     rax, [rbp+var_10]
0x1800da1b6  mov     [rsp+70h+var_50], rax
0x1800da1bb  mov     dword ptr [rbp+arg_18], 80004005h
0x1800da1c2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800da1c7  mov     eax, edi
0x1800da1c9  add     rsp, 70h
0x1800da1cd  pop     rdi
0x1800da1ce  pop     rbx
0x1800da1cf  pop     rbp
0x1800da1d0  retn
```
