# CPipeManager::CreateWaitEvent(void)

- ea: `0x18008fd70`
- end: `0x180090222`
- name: `?CreateWaitEvent@CPipeManager@@IEAAJXZ`
- size: `1202`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180092c60`

## callees

- `0x18000116c`
- `0x18000146c`
- `0x18000202c`
- `0x180051870`
- `0x18007f3b4`
- `0x18008fd70`
- `0x180096750`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008fdf1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008fdf1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008fdcb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008fdcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008fdb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008fdb2`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18008fe4f`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18008fe4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008fde2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008fde2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008fe43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008fe43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fdd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fdfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fe33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fe59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fdd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fdfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fe33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fe59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090021`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008fe3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800900c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008fe3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800900c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180090018`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180090018`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008fe1e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008fe1e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800900ce`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800900ce`

## string_xrefs

- `0x18008fe95`: `CreateWaitEvent`
- `0x18008ff20`: `Failed to initialize Idd security attributes`
- `0x1800900ed`: `Failed to create wait event name string`
- `0x18009006d`: `CreateEvent failed`

## pseudocode

```c
__int64 __fastcall CPipeManager::CreateWaitEvent(CPipeManager *this)
{
  int v2; // r15d
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  unsigned int v7; // ebx
  int v8; // eax
  CPipeManager *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  int v12; // r8d
  int v13; // r9d
  int v14; // r8d
  int v15; // r9d
  const unsigned __int16 *v16; // r8
  int v17; // ecx
  int v18; // edi
  int v19; // r8d
  int v20; // r9d
  HANDLE EventW; // rsi
  signed int v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  __int16 *v26; // rdx
  void *TokenHandle; // [rsp+50h] [rbp-29h] BYREF
  const char *v29; // [rsp+58h] [rbp-21h] BYREF
  const char *v30; // [rsp+60h] [rbp-19h] BYREF
  const char *v31; // [rsp+68h] [rbp-11h] BYREF
  const char *v32; // [rsp+70h] [rbp-9h] BYREF
  DWORD pSessionId; // [rsp+78h] [rbp-1h] BYREF
  const char *v34; // [rsp+80h] [rbp+7h] BYREF
  _SECURITY_ATTRIBUTES v35; // [rsp+88h] [rbp+Fh] BYREF
  int v36; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int TokenInformation; // [rsp+F0h] [rbp+77h] BYREF
  const char *ReturnLength; // [rsp+F8h] [rbp+7Fh] BYREF

  pSessionId = 0;
  memset(&v35, 0, sizeof(v35));
  TokenInformation = 0;
  TokenHandle = 0;
  v2 = 0;
  LODWORD(ReturnLength) = 0;
  v36 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_47;
  if ( GetLastError() != 1008 )
    goto LABEL_10;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
LABEL_47:
    if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, (PDWORD)&ReturnLength) )
    {
      if ( TokenInformation )
        v2 = 1;
    }
    else
    {
      GetLastError();
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    GetLastError();
  }
LABEL_10:
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v7;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, int *))(**((_QWORD **)this + 1627) + 32LL))(
         *((_QWORD *)this + 1627),
         L"EnableWddmIdd",
         &v36);
  if ( v8 < 0 )
  {
    v9 = (CPipeManager *)(unsigned int)CallbackContext;
    if ( (unsigned int)CallbackContext > 3 )
    {
      TokenInformation = v8;
      ReturnLength = "CreateWaitEvent";
      TokenHandle = "CONN_PROPERTY_ENABLE_WDDM_IDD is not present. Not a fatal error.";
      v29 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)word_18027AC4A,
        v10,
        v11,
        (__int64)&v29,
        (__int64)&TokenHandle,
        (__int64)&TokenInformation,
        (__int64)&ReturnLength);
    }
  }
  if ( v36 )
  {
    v7 = CPipeManager::InitializeWaitEventSecurityAttr(v9, &v35);
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v29 = "CreateWaitEvent";
        TokenHandle = "Failed to initialize Idd security attributes";
        TokenInformation = 2559;
        v30 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v31 = "Error HResult failed";
        LODWORD(ReturnLength) = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&dword_18027ABFC,
          v12,
          v13,
          (__int64)&v31,
          (__int64)&ReturnLength,
          (__int64)&v30,
          (__int64)&TokenInformation,
          (__int64)&v29,
          (__int64)&TokenHandle);
      }
      return v7;
    }
  }
  while ( 1 )
  {
    TokenInformation = 0;
    LODWORD(ReturnLength) = 0;
    if ( (unsigned int)rand_s(&TokenInformation) )
    {
      v7 = -2147418113;
      if ( (unsigned int)CallbackContext <= 2 )
        return v7;
      LODWORD(TokenHandle) = 2569;
      v26 = &word_18027ABAE;
      goto LABEL_43;
    }
    if ( (unsigned int)rand_s(&ReturnLength) )
    {
      v7 = -2147418113;
      if ( (unsigned int)CallbackContext <= 2 )
        return v7;
      LODWORD(TokenHandle) = 2575;
      v26 = (__int16 *)qword_18027AB60;
LABEL_43:
      LODWORD(v29) = -2147418113;
      v34 = "rand_s failed";
      v31 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v30 = "Error HResult failed";
      v32 = "CreateWaitEvent";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147418113,
        (_DWORD)v26,
        v14,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v31,
        (__int64)&TokenHandle,
        (__int64)&v32,
        (__int64)&v34);
      return v7;
    }
    if ( pSessionId || (v16 = L"Global\\RDPSchedulerEvent%lld", v2) )
      v16 = L"Local\\RDPSchedulerEvent%lld";
    v18 = StringCchPrintfW(
            (unsigned __int16 *)this + 6208,
            0x104u,
            v16,
            (unsigned int)ReturnLength | ((unsigned __int64)TokenInformation << 32));
    if ( v18 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v31 = "CreateWaitEvent";
        v32 = "Failed to create wait event name string";
        LODWORD(TokenHandle) = 2589;
        v30 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v34 = "Error HResult failed";
        LODWORD(v29) = v18;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v17,
          (unsigned int)word_18027AB12,
          v19,
          v20,
          (__int64)&v34,
          (__int64)&v29,
          (__int64)&v30,
          (__int64)&TokenHandle,
          (__int64)&v31,
          (__int64)&v32);
      }
      return (unsigned int)v18;
    }
    EventW = CreateEventW(
               (LPSECURITY_ATTRIBUTES)((unsigned __int64)&v35 & -(__int64)(v36 != 0)),
               0,
               0,
               (LPCWSTR)this + 6208);
    v22 = GetLastError();
    v7 = v22;
    if ( !EventW )
      break;
    if ( v22 != 183 )
    {
      *((_QWORD *)this + 1617) = EventW;
      return (unsigned int)v18;
    }
    CloseHandle(EventW);
LABEL_34:
    Sleep(0x64u);
  }
  if ( v22 == 5 )
    goto LABEL_34;
  if ( v22 > 0 )
    v7 = (unsigned __int16)v22 | 0x80070000;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v31 = "CreateWaitEvent";
    v30 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    LODWORD(v29) = 2614;
    v32 = "CreateEvent failed";
    LODWORD(TokenHandle) = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v23,
      (unsigned int)&dword_18027AACC,
      v24,
      v25,
      (__int64)&v32,
      (__int64)&TokenHandle,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v31);
  }
  return v7;
}

```

## disassembly

```asm
0x18008fd70  push    rbp
0x18008fd72  push    rbx
0x18008fd73  push    rsi
0x18008fd74  push    rdi
0x18008fd75  push    r13
0x18008fd77  push    r14
0x18008fd79  push    r15
0x18008fd7b  lea     rbp, [rsp-27h]
0x18008fd80  sub     rsp, 0A0h
0x18008fd87  xor     eax, eax
0x18008fd89  mov     [rbp+57h+pSessionId], 0
0x18008fd90  xorps   xmm0, xmm0
0x18008fd93  mov     qword ptr [rbp+57h+var_48.bInheritHandle], rax
0x18008fd97  movups  xmmword ptr [rbp+57h+var_48.nLength], xmm0
0x18008fd9b  mov     [rbp+57h+TokenInformation], eax
0x18008fd9e  mov     r14, rcx
0x18008fda1  mov     [rbp+57h+TokenHandle], rax
0x18008fda5  xor     r15d, r15d
0x18008fda8  mov     dword ptr [rbp+57h+arg_18], eax
0x18008fdab  mov     [rbp+57h+arg_8], 0
0x18008fdb2  call    cs:__imp_GetCurrentThread
0x18008fdb8  lea     ebx, [r15+1]
0x18008fdbc  mov     rcx, rax; ThreadHandle
0x18008fdbf  lea     edi, [rbx+7]
0x18008fdc2  mov     r8d, ebx; OpenAsSelf
0x18008fdc5  mov     edx, edi; DesiredAccess
0x18008fdc7  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18008fdcb  call    cs:__imp_OpenThreadToken
0x18008fdd1  test    eax, eax
0x18008fdd3  jnz     short loc_18008FE03
0x18008fdd5  call    cs:__imp_GetLastError
0x18008fddb  cmp     eax, 3F0h
0x18008fde0  jnz     short loc_18008FE43
0x18008fde2  call    cs:__imp_GetCurrentProcess
0x18008fde8  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18008fdec  mov     edx, edi; DesiredAccess
0x18008fdee  mov     rcx, rax; ProcessHandle
0x18008fdf1  call    cs:__imp_OpenProcessToken
0x18008fdf7  test    eax, eax
0x18008fdf9  jnz     short loc_18008FE03
0x18008fdfb  call    cs:__imp_GetLastError
0x18008fe01  jmp     short loc_18008FE43
0x18008fe03  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18008fe07  lea     rax, [rbp+57h+arg_18]
0x18008fe0b  mov     r9d, 4; TokenInformationLength
0x18008fe11  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18008fe16  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18008fe1a  lea     edx, [r9+19h]; TokenInformationClass
0x18008fe1e  call    cs:__imp_GetTokenInformation
0x18008fe24  test    eax, eax
0x18008fe26  jz      short loc_18008FE33
0x18008fe28  cmp     [rbp+57h+TokenInformation], r15d
0x18008fe2c  jz      short loc_18008FE39
0x18008fe2e  mov     r15d, ebx
0x18008fe31  jmp     short loc_18008FE39
0x18008fe33  call    cs:__imp_GetLastError
0x18008fe39  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18008fe3d  call    cs:__imp_CloseHandle
0x18008fe43  call    cs:__imp_GetCurrentProcessId
0x18008fe49  mov     ecx, eax; dwProcessId
0x18008fe4b  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x18008fe4f  call    cs:__imp_ProcessIdToSessionId
0x18008fe55  test    eax, eax
0x18008fe57  jnz     short loc_18008FE77
0x18008fe59  call    cs:__imp_GetLastError
0x18008fe5f  mov     ebx, eax
0x18008fe61  test    eax, eax
0x18008fe63  jle     loc_18009020E
0x18008fe69  movzx   ebx, ax
0x18008fe6c  or      ebx, 80070000h
0x18008fe72  jmp     loc_18009020E
0x18008fe77  mov     rcx, [r14+32D8h]
0x18008fe7e  lea     r8, [rbp+57h+arg_8]
0x18008fe82  lea     rdx, aEnablewddmidd; "EnableWddmIdd"
0x18008fe89  mov     rax, [rcx]
0x18008fe8c  mov     rax, [rax+20h]
0x18008fe90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fe95  lea     r13, aCreatewaiteven_0; "CreateWaitEvent"
0x18008fe9c  test    eax, eax
0x18008fe9e  jns     short loc_18008FEF8
0x18008fea0  mov     ecx, cs:CallbackContext
0x18008fea6  cmp     ecx, 3
0x18008fea9  jbe     short loc_18008FEF8
0x18008feab  mov     [rbp+57h+TokenInformation], eax
0x18008feae  lea     rdx, word_18027AC4A
0x18008feb5  lea     rax, aConnPropertyEn; "CONN_PROPERTY_ENABLE_WDDM_IDD is not pr"...
0x18008febc  mov     [rbp+57h+arg_18], r13
0x18008fec0  mov     [rbp+57h+TokenHandle], rax
0x18008fec4  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18008fecb  mov     [rbp+57h+var_78], rax
0x18008fecf  lea     rax, [rbp+57h+arg_18]
0x18008fed3  mov     [rsp+0D0h+var_98], rax
0x18008fed8  lea     rax, [rbp+57h+TokenInformation]
0x18008fedc  mov     [rsp+0D0h+var_A0], rax
0x18008fee1  lea     rax, [rbp+57h+TokenHandle]
0x18008fee5  mov     [rsp+0D0h+var_A8], rax
0x18008feea  lea     rax, [rbp+57h+var_78]
0x18008feee  mov     [rsp+0D0h+ReturnLength], rax
0x18008fef3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18008fef8  cmp     [rbp+57h+arg_8], 0
0x18008fefc  jz      loc_18008FF8C
0x18008ff02  lea     rdx, [rbp+57h+var_48]; struct _SECURITY_ATTRIBUTES *
0x18008ff06  call    ?InitializeWaitEventSecurityAttr@CPipeManager@@IEAAJPEAU_SECURITY_ATTRIBUTES@@@Z; CPipeManager::InitializeWaitEventSecurityAttr(_SECURITY_ATTRIBUTES *)
0x18008ff0b  mov     ebx, eax
0x18008ff0d  test    eax, eax
0x18008ff0f  jns     short loc_18008FF8C
0x18008ff11  mov     ecx, cs:CallbackContext
0x18008ff17  cmp     ecx, 2
0x18008ff1a  jbe     loc_18009020E
0x18008ff20  lea     rax, aFailedToInitia_39; "Failed to initialize Idd security attri"...
0x18008ff27  mov     [rbp+57h+var_78], r13
0x18008ff2b  mov     [rbp+57h+TokenHandle], rax
0x18008ff2f  lea     rdx, dword_18027ABFC
0x18008ff36  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008ff3d  mov     [rbp+57h+TokenInformation], 9FFh
0x18008ff44  mov     [rbp+57h+var_70], rax
0x18008ff48  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008ff4f  mov     [rbp+57h+var_68], rax
0x18008ff53  lea     rax, [rbp+57h+TokenHandle]
0x18008ff57  mov     [rsp+0D0h+var_88], rax
0x18008ff5c  lea     rax, [rbp+57h+var_78]
0x18008ff60  mov     [rsp+0D0h+var_90], rax
0x18008ff65  lea     rax, [rbp+57h+TokenInformation]
0x18008ff69  mov     [rsp+0D0h+var_98], rax
0x18008ff6e  lea     rax, [rbp+57h+var_70]
0x18008ff72  mov     [rsp+0D0h+var_A0], rax
0x18008ff77  lea     rax, [rbp+57h+arg_18]
0x18008ff7b  mov     [rsp+0D0h+var_A8], rax
0x18008ff80  lea     rax, [rbp+57h+var_68]
0x18008ff84  mov     dword ptr [rbp+57h+arg_18], ebx
0x18008ff87  jmp     loc_180090204
0x18008ff8c  lea     rcx, [rbp+57h+TokenInformation]
0x18008ff90  mov     [rbp+57h+TokenInformation], 0
0x18008ff97  mov     dword ptr [rbp+57h+arg_18], 0
0x18008ff9e  call    rand_s
0x18008ffa3  test    eax, eax
0x18008ffa5  jnz     loc_18009018B
0x18008ffab  lea     rcx, [rbp+57h+arg_18]
0x18008ffaf  call    rand_s
0x18008ffb4  test    eax, eax
0x18008ffb6  jnz     loc_180090165
0x18008ffbc  mov     r9d, [rbp+57h+TokenInformation]
0x18008ffc0  mov     eax, dword ptr [rbp+57h+arg_18]
0x18008ffc3  shl     r9, 20h
0x18008ffc7  or      r9, rax
0x18008ffca  cmp     [rbp+57h+pSessionId], 0
0x18008ffce  jnz     short loc_18008FFDC
0x18008ffd0  lea     r8, aGlobalRdpsched; "Global\\RDPSchedulerEvent%lld"
0x18008ffd7  test    r15d, r15d
0x18008ffda  jz      short loc_18008FFE3
0x18008ffdc  lea     r8, aLocalRdpschedu; "Local\\RDPSchedulerEvent%lld"
0x18008ffe3  lea     rbx, [r14+3080h]
0x18008ffea  mov     edx, 104h; unsigned __int64
0x18008ffef  mov     rcx, rbx; unsigned __int16 *
0x18008fff2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008fff7  mov     edi, eax
0x18008fff9  test    eax, eax
0x18008fffb  js      loc_1800900E2
0x180090001  mov     ecx, [rbp+57h+arg_8]
0x180090004  lea     rax, [rbp+57h+var_48]
0x180090008  neg     ecx
0x18009000a  mov     r9, rbx; lpName
0x18009000d  sbb     rcx, rcx
0x180090010  xor     r8d, r8d; bInitialState
0x180090013  and     rcx, rax; lpEventAttributes
0x180090016  xor     edx, edx; bManualReset
0x180090018  call    cs:__imp_CreateEventW
0x18009001e  mov     rsi, rax
0x180090021  call    cs:__imp_GetLastError
0x180090027  mov     ebx, eax
0x180090029  test    rsi, rsi
0x18009002c  jnz     loc_1800900B9
0x180090032  cmp     eax, 5
0x180090035  jz      loc_1800900C9
0x18009003b  test    eax, eax
0x18009003d  jle     short loc_180090048
0x18009003f  movzx   ebx, ax
0x180090042  or      ebx, 80070000h
0x180090048  mov     eax, cs:CallbackContext
0x18009004e  cmp     eax, 2
0x180090051  jbe     loc_18009020E
0x180090057  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009005e  mov     [rbp+57h+var_68], r13
0x180090062  mov     [rbp+57h+var_70], rax
0x180090066  lea     rdx, dword_18027AACC
0x18009006d  lea     rax, aCreateeventFai; "CreateEvent failed"
0x180090074  mov     dword ptr [rbp+57h+var_78], 0A36h
0x18009007b  mov     [rbp+57h+var_60], rax
0x18009007f  lea     rax, [rbp+57h+var_68]
0x180090083  mov     [rsp+0D0h+var_90], rax
0x180090088  lea     rax, [rbp+57h+var_78]
0x18009008c  mov     [rsp+0D0h+var_98], rax
0x180090091  lea     rax, [rbp+57h+var_70]
0x180090095  mov     [rsp+0D0h+var_A0], rax
0x18009009a  lea     rax, [rbp+57h+TokenHandle]
0x18009009e  mov     [rsp+0D0h+var_A8], rax
0x1800900a3  lea     rax, [rbp+57h+var_60]
0x1800900a7  mov     [rsp+0D0h+ReturnLength], rax
0x1800900ac  mov     dword ptr [rbp+57h+TokenHandle], ebx
0x1800900af  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800900b4  jmp     loc_18009020E
0x1800900b9  cmp     eax, 0B7h
0x1800900be  jnz     short loc_1800900D9
0x1800900c0  mov     rcx, rsi; hObject
0x1800900c3  call    cs:__imp_CloseHandle
0x1800900c9  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800900ce  call    cs:__imp_Sleep
0x1800900d4  jmp     loc_18008FF8C
0x1800900d9  mov     [r14+3288h], rsi
0x1800900e0  jmp     short loc_18009015E
0x1800900e2  mov     eax, cs:CallbackContext
0x1800900e8  cmp     eax, 2
0x1800900eb  jbe     short loc_18009015E
0x1800900ed  lea     rax, aFailedToCreate_54; "Failed to create wait event name string"
0x1800900f4  mov     [rbp+57h+var_68], r13
0x1800900f8  mov     [rbp+57h+var_60], rax
0x1800900fc  lea     rdx, word_18027AB12
0x180090103  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009010a  mov     dword ptr [rbp+57h+TokenHandle], 0A1Dh
0x180090111  mov     [rbp+57h+var_70], rax
0x180090115  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009011c  mov     [rbp+57h+var_50], rax
0x180090120  lea     rax, [rbp+57h+var_60]
0x180090124  mov     [rsp+0D0h+var_88], rax
0x180090129  lea     rax, [rbp+57h+var_68]
0x18009012d  mov     [rsp+0D0h+var_90], rax
0x180090132  lea     rax, [rbp+57h+TokenHandle]
0x180090136  mov     [rsp+0D0h+var_98], rax
0x18009013b  lea     rax, [rbp+57h+var_70]
0x18009013f  mov     [rsp+0D0h+var_A0], rax
0x180090144  lea     rax, [rbp+57h+var_78]
0x180090148  mov     [rsp+0D0h+var_A8], rax
0x18009014d  lea     rax, [rbp+57h+var_50]
0x180090151  mov     [rsp+0D0h+ReturnLength], rax
0x180090156  mov     dword ptr [rbp+57h+var_78], edi
0x180090159  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009015e  mov     ebx, edi
0x180090160  jmp     loc_18009020E
0x180090165  mov     eax, cs:CallbackContext
0x18009016b  mov     ecx, 8000FFFFh
0x180090170  mov     ebx, ecx
0x180090172  cmp     eax, 2
0x180090175  jbe     loc_18009020E
0x18009017b  mov     dword ptr [rbp+57h+TokenHandle], 0A0Fh
0x180090182  lea     rdx, qword_18027AB60
0x180090189  jmp     short loc_1800901AB
0x18009018b  mov     eax, cs:CallbackContext
0x180090191  mov     ecx, 8000FFFFh
0x180090196  mov     ebx, ecx
0x180090198  cmp     eax, 2
0x18009019b  jbe     short loc_18009020E
0x18009019d  mov     dword ptr [rbp+57h+TokenHandle], 0A09h
0x1800901a4  lea     rdx, word_18027ABAE
0x1800901ab  lea     rax, aRandSFailed; "rand_s failed"
0x1800901b2  mov     dword ptr [rbp+57h+var_78], ecx
0x1800901b5  mov     [rbp+57h+var_50], rax
0x1800901b9  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x1800901c0  mov     [rbp+57h+var_68], rax
0x1800901c4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800901cb  mov     [rbp+57h+var_70], rax
0x1800901cf  lea     rax, [rbp+57h+var_50]
0x1800901d3  mov     [rsp+0D0h+var_88], rax
0x1800901d8  lea     rax, [rbp+57h+var_60]
0x1800901dc  mov     [rsp+0D0h+var_90], rax
0x1800901e1  lea     rax, [rbp+57h+TokenHandle]
0x1800901e5  mov     [rsp+0D0h+var_98], rax
0x1800901ea  lea     rax, [rbp+57h+var_68]
0x1800901ee  mov     [rsp+0D0h+var_A0], rax
0x1800901f3  lea     rax, [rbp+57h+var_78]
0x1800901f7  mov     [rsp+0D0h+var_A8], rax
0x1800901fc  lea     rax, [rbp+57h+var_70]
0x180090200  mov     [rbp+57h+var_60], r13
0x180090204  mov     [rsp+0D0h+ReturnLength], rax
0x180090209  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009020e  mov     eax, ebx
0x180090210  add     rsp, 0A0h
0x180090217  pop     r15
0x180090219  pop     r14
0x18009021b  pop     r13
0x18009021d  pop     rdi
0x18009021e  pop     rsi
0x18009021f  pop     rbx
0x180090220  pop     rbp
0x180090221  retn
```
