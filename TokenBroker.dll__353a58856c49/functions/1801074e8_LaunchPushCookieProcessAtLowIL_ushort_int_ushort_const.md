# LaunchPushCookieProcessAtLowIL(ushort *,int,ushort const *)

- ea: `0x1801074e8`
- end: `0x180107694`
- name: `?LaunchPushCookieProcessAtLowIL@@YAKPEAGHPEBG@Z`
- size: `428`
- prototype: `__int64 __fastcall(LPWSTR lpCommandLine, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180106908`

## callees

- `0x18005d6c0`
- `0x180063fc4`
- `0x1801072f4`
- `0x1801074e8`
- `0x180107b10`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180107596`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180107596`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180107511`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180107511`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180107529`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180107529`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180107554`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180107554`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180107542`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180107542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801075a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801075a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180107665`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010767c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180107665`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010767c`

## string_xrefs

- `0x1801075f2`: `Completed`
- `0x18010755e`: `OpenProcessTokenFailed`
- `0x18010756a`: `OpenThreadTokenFailed`
- `0x1801075a6`: `DuplicateTokenExFailed`
- `0x1801075be`: `LowerTokenIntegrityFailed`

## pseudocode

```c
__int64 __fastcall LaunchPushCookieProcessAtLowIL(LPWSTR lpCommandLine, __int64 a2, const unsigned __int16 *a3)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  const wchar_t *v8; // r8
  unsigned int v9; // edx
  DWORD v10; // eax
  void *v11; // r8
  void *TokenHandle[4]; // [rsp+40h] [rbp-20h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp+38h] BYREF

  TokenHandle[0] = 0;
  hObject = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, TokenHandle) )
    goto LABEL_22;
  LastError = GetLastError();
  if ( LastError != 1008 )
  {
    v8 = L"OpenThreadTokenFailed";
    goto LABEL_12;
  }
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x2000000u, TokenHandle) )
  {
LABEL_22:
    if ( DuplicateTokenEx(TokenHandle[0], 0, 0, SecurityImpersonation, TokenPrimary, &hObject) )
    {
      LastError = LowerTokenIntegrity(hObject, v9);
      if ( LastError )
      {
        v8 = L"LowerTokenIntegrityFailed";
        goto LABEL_12;
      }
      v10 = LaunchPushCookieProcess(hObject, lpCommandLine, 0, 0, 0, 0, 0);
      v8 = L"Completed";
    }
    else
    {
      v10 = GetLastError();
      v8 = L"DuplicateTokenExFailed";
    }
    LastError = v10;
    goto LABEL_12;
  }
  v8 = L"OpenProcessTokenFailed";
LABEL_12:
  if ( (unsigned int)dword_180175038 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180175038, 0x200000000000LL, v8) )
  {
    TokenHandle[2] = v11;
    TokenHandle[1] = (void *)a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      &dword_180175038,
      byte_180156FB5,
      0);
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( TokenHandle[0] )
    CloseHandle(TokenHandle[0]);
  return LastError;
}

```

## disassembly

```asm
0x1801074e8  mov     [rsp-18h+arg_0], rbx
0x1801074ed  mov     [rsp-18h+arg_8], edx
0x1801074f1  push    rbp
0x1801074f2  push    rsi
0x1801074f3  push    rdi
0x1801074f4  mov     rbp, rsp
0x1801074f7  sub     rsp, 60h
0x1801074fb  mov     rsi, r8
0x1801074fe  mov     [rbp+TokenHandle], 0
0x180107506  mov     rdi, rcx
0x180107509  mov     [rbp+hObject], 0
0x180107511  call    cs:__imp_GetCurrentThread
0x180107517  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18010751b  mov     edx, 0F01FFh; DesiredAccess
0x180107520  mov     rcx, rax; ThreadHandle
0x180107523  mov     r8d, 1; OpenAsSelf
0x180107529  call    cs:__imp_OpenThreadToken
0x18010752f  test    eax, eax
0x180107531  jnz     short loc_180107576
0x180107533  call    cs:__imp_GetLastError
0x180107539  mov     ebx, eax
0x18010753b  cmp     eax, 3F0h
0x180107540  jnz     short loc_18010756A
0x180107542  call    cs:__imp_GetCurrentProcess
0x180107548  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18010754c  mov     edx, 2000000h; DesiredAccess
0x180107551  mov     rcx, rax; ProcessHandle
0x180107554  call    cs:__imp_OpenProcessToken
0x18010755a  test    eax, eax
0x18010755c  jnz     short loc_180107576
0x18010755e  lea     r8, aOpenprocesstok; "OpenProcessTokenFailed"
0x180107565  jmp     loc_1801075FB
0x18010756a  lea     r8, aOpenthreadtoke; "OpenThreadTokenFailed"
0x180107571  jmp     loc_1801075FB
0x180107576  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x18010757a  lea     rax, [rbp+hObject]
0x18010757e  mov     [rsp+60h+phNewToken], rax; phNewToken
0x180107583  mov     r9d, 2; ImpersonationLevel
0x180107589  xor     r8d, r8d; lpTokenAttributes
0x18010758c  mov     [rsp+60h+TokenType], 1; TokenType
0x180107594  xor     edx, edx; dwDesiredAccess
0x180107596  call    cs:__imp_DuplicateTokenEx
0x18010759c  test    eax, eax
0x18010759e  jnz     short loc_1801075AF
0x1801075a0  call    cs:__imp_GetLastError
0x1801075a6  lea     r8, aDuplicatetoken; "DuplicateTokenExFailed"
0x1801075ad  jmp     short loc_1801075F9
0x1801075af  mov     rcx, [rbp+hObject]; TokenHandle
0x1801075b3  call    ?LowerTokenIntegrity@@YAKPEAXK@Z; LowerTokenIntegrity(void *,ulong)
0x1801075b8  mov     ebx, eax
0x1801075ba  test    eax, eax
0x1801075bc  jz      short loc_1801075C7
0x1801075be  lea     r8, aLowertokeninte; "LowerTokenIntegrityFailed"
0x1801075c5  jmp     short loc_1801075FB
0x1801075c7  mov     rcx, [rbp+hObject]; hToken
0x1801075cb  xor     r9d, r9d; struct _SID_AND_ATTRIBUTES *
0x1801075ce  mov     [rsp+60h+var_30], 0; int
0x1801075d6  xor     r8d, r8d; void *
0x1801075d9  mov     [rsp+60h+phNewToken], 0; void *
0x1801075e2  mov     rdx, rdi; lpCommandLine
0x1801075e5  mov     [rsp+60h+TokenType], 0; unsigned int
0x1801075ed  call    ?LaunchPushCookieProcess@@YAKPEAXPEAG0QEAU_SID_AND_ATTRIBUTES@@K0H@Z; LaunchPushCookieProcess(void *,ushort *,void *,_SID_AND_ATTRIBUTES * const,ulong,void *,int)
0x1801075f2  lea     r8, aCompleted_0; "Completed"
0x1801075f9  mov     ebx, eax
0x1801075fb  mov     eax, cs:dword_180175038
0x180107601  cmp     eax, 4
0x180107604  jbe     short loc_18010765C
0x180107606  mov     rdx, 200000000000h
0x180107610  lea     rcx, dword_180175038
0x180107617  call    _tlgKeywordOn
0x18010761c  test    al, al
0x18010761e  jz      short loc_18010765C
0x180107620  lea     rax, [rbp+var_18]
0x180107624  mov     [rbp+var_10], r8
0x180107628  mov     qword ptr [rsp+60h+var_30], rax
0x18010762d  lea     rdx, byte_180156FB5
0x180107634  lea     rax, [rbp+var_10]
0x180107638  mov     [rbp+var_18], rsi
0x18010763c  mov     [rsp+60h+phNewToken], rax
0x180107641  lea     rcx, dword_180175038
0x180107648  lea     rax, [rbp+arg_8]
0x18010764c  mov     [rbp+arg_8], ebx
0x18010764f  xor     r8d, r8d
0x180107652  mov     qword ptr [rsp+60h+TokenType], rax
0x180107657  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18010765c  mov     rcx, [rbp+hObject]; hObject
0x180107660  test    rcx, rcx
0x180107663  jz      short loc_180107673
0x180107665  call    cs:__imp_CloseHandle
0x18010766b  mov     [rbp+hObject], 0
0x180107673  mov     rcx, [rbp+TokenHandle]; hObject
0x180107677  test    rcx, rcx
0x18010767a  jz      short loc_180107682
0x18010767c  call    cs:__imp_CloseHandle
0x180107682  mov     eax, ebx
0x180107684  mov     rbx, [rsp+60h+arg_0]
0x18010768c  add     rsp, 60h
0x180107690  pop     rdi
0x180107691  pop     rsi
0x180107692  pop     rbp
0x180107693  retn
```
