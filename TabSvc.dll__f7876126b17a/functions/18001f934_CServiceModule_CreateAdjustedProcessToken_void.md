# CServiceModule::CreateAdjustedProcessToken(void)

- ea: `0x18001f934`
- end: `0x18001fb45`
- name: `?CreateAdjustedProcessToken@CServiceModule@@QEAAHXZ`
- size: `529`
- prototype: `__int64 __fastcall(CServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180025bbc`

## callees

- `0x1800016d4`
- `0x180012dc0`
- `0x180015630`
- `0x18001bbe0`
- `0x18001f934`
- `0x18002b404`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f960`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f960`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f972`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f972`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001f9de`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001f9de`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001f9a4`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001f9a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001faad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001faad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb05`

## string_xrefs

- `0x18001fa14`: `PENSERVICE_CServiceModule::CreateAdjustedProcessToken`
- `0x18001faba`: `PENSERVICE_CServiceModule::CreateAdjustedProcessToken`
- `0x18001fa54`: `DuplicateTokenEx failed.`
- `0x18001fafa`: `OpenProcessToken failed.`

## pseudocode

```c
__int64 __fastcall CServiceModule::CreateAdjustedProcessToken(CServiceModule *this)
{
  unsigned int v1; // ebx
  HANDLE CurrentProcess; // rax
  char LastError; // al
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  char v7; // al
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  DWORD v12; // [rsp+30h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-28h] BYREF
  const char *v14; // [rsp+40h] [rbp-20h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-18h] BYREF

  TokenHandle = 0;
  NewState = 0;
  v1 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x1ABu, &TokenHandle) )
  {
    if ( DuplicateTokenEx(TokenHandle, 0x1ABu, 0, SecurityImpersonation, TokenPrimary, &::TokenHandle) )
    {
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Luid = (LUID)7LL;
      NewState.Privileges[0].Attributes = 2;
      AdjustTokenPrivileges(::TokenHandle, 0, &NewState, 0, 0, 0);
      v1 = 1;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_sd(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          14,
          (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          (unsigned int)"PENSERVICE_CServiceModule::CreateAdjustedProcessToken",
          LastError);
      }
      if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
      {
        v14 = "DuplicateTokenEx failed.";
        v12 = GetLastError();
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v4,
          (int)byte_180039181,
          v5,
          v6,
          (__int64)&v12,
          (const unsigned __int16 **)&v14);
      }
    }
    SH<void *,SH_HANDLE>::Reset(&TokenHandle);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
    {
      v7 = GetLastError();
      WPP_SF_sd(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        15,
        (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
        (unsigned int)"PENSERVICE_CServiceModule::CreateAdjustedProcessToken",
        v7);
    }
    if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    {
      v14 = "OpenProcessToken failed.";
      v12 = GetLastError();
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v8,
        (int)byte_180039E43,
        v9,
        v10,
        (__int64)&v12,
        (const unsigned __int16 **)&v14);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001f934  mov     [rsp-8+arg_0], rbx
0x18001f939  push    rbp
0x18001f93a  mov     rbp, rsp
0x18001f93d  sub     rsp, 60h
0x18001f941  mov     rax, cs:__security_cookie
0x18001f948  xor     rax, rsp
0x18001f94b  mov     [rbp+var_8], rax
0x18001f94f  xorps   xmm0, xmm0
0x18001f952  mov     [rbp+TokenHandle], 0
0x18001f95a  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18001f95e  xor     ebx, ebx
0x18001f960  call    cs:__imp_GetCurrentProcess
0x18001f966  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001f96a  mov     edx, 1ABh; DesiredAccess
0x18001f96f  mov     rcx, rax; ProcessHandle
0x18001f972  call    cs:__imp_OpenProcessToken
0x18001f978  test    eax, eax
0x18001f97a  jz      loc_18001FA94
0x18001f980  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x18001f984  lea     rax, TokenHandle
0x18001f98b  mov     [rsp+60h+phNewToken], rax; phNewToken
0x18001f990  lea     r9d, [rbx+2]; ImpersonationLevel
0x18001f994  xor     r8d, r8d; lpTokenAttributes
0x18001f997  mov     [rsp+60h+TokenType], 1; TokenType
0x18001f99f  mov     edx, 1ABh; dwDesiredAccess
0x18001f9a4  call    cs:__imp_DuplicateTokenEx
0x18001f9aa  test    eax, eax
0x18001f9ac  jz      short loc_18001F9EE
0x18001f9ae  mov     rcx, qword ptr cs:TokenHandle; TokenHandle
0x18001f9b5  lea     r8, [rbp+NewState]; NewState
0x18001f9b9  mov     [rsp+60h+phNewToken], rbx; ReturnLength
0x18001f9be  xor     r9d, r9d; BufferLength
0x18001f9c1  xor     edx, edx; DisableAllPrivileges
0x18001f9c3  mov     qword ptr [rsp+60h+TokenType], rbx; PreviousState
0x18001f9c8  mov     [rbp+NewState.PrivilegeCount], 1
0x18001f9cf  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 7
0x18001f9d7  mov     [rbp+NewState.Privileges.Attributes], 2
0x18001f9de  call    cs:__imp_AdjustTokenPrivileges
0x18001f9e4  mov     ebx, 1
0x18001f9e9  jmp     loc_18001FA86
0x18001f9ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9f5  lea     rax, WPP_GLOBAL_Control
0x18001f9fc  cmp     rcx, rax
0x18001f9ff  jz      short loc_18001FA34
0x18001fa01  test    byte ptr [rcx+1Ch], 4
0x18001fa05  jz      short loc_18001FA34
0x18001fa07  call    cs:__imp_GetLastError
0x18001fa0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa14  lea     r9, aPenserviceCser_30; "PENSERVICE_CServiceModule::CreateAdjust"...
0x18001fa1b  mov     edx, 0Eh
0x18001fa20  mov     [rsp+60h+TokenType], eax
0x18001fa24  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18001fa2b  mov     rcx, [rcx+10h]
0x18001fa2f  call    WPP_SF_sd
0x18001fa34  mov     eax, cs:dword_1800411A8
0x18001fa3a  cmp     eax, 5
0x18001fa3d  jbe     short loc_18001FA86
0x18001fa3f  mov     edx, 4000000h
0x18001fa44  lea     rcx, dword_1800411A8
0x18001fa4b  call    _tlgKeywordOn
0x18001fa50  test    al, al
0x18001fa52  jz      short loc_18001FA86
0x18001fa54  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed."
0x18001fa5b  mov     [rbp+var_20], rax
0x18001fa5f  call    cs:__imp_GetLastError
0x18001fa65  mov     [rbp+var_30], eax
0x18001fa68  lea     rdx, byte_180039181
0x18001fa6f  lea     rax, [rbp+var_20]
0x18001fa73  mov     [rsp+60h+phNewToken], rax
0x18001fa78  lea     rax, [rbp+var_30]
0x18001fa7c  mov     qword ptr [rsp+60h+TokenType], rax
0x18001fa81  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001fa86  lea     rcx, [rbp+TokenHandle]
0x18001fa8a  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18001fa8f  jmp     loc_18001FB2C
0x18001fa94  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa9b  lea     rax, WPP_GLOBAL_Control
0x18001faa2  cmp     rcx, rax
0x18001faa5  jz      short loc_18001FADA
0x18001faa7  test    byte ptr [rcx+1Ch], 4
0x18001faab  jz      short loc_18001FADA
0x18001faad  call    cs:__imp_GetLastError
0x18001fab3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001faba  lea     r9, aPenserviceCser_30; "PENSERVICE_CServiceModule::CreateAdjust"...
0x18001fac1  mov     edx, 0Fh
0x18001fac6  mov     [rsp+60h+TokenType], eax
0x18001faca  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18001fad1  mov     rcx, [rcx+10h]
0x18001fad5  call    WPP_SF_sd
0x18001fada  mov     eax, cs:dword_1800411A8
0x18001fae0  cmp     eax, 5
0x18001fae3  jbe     short loc_18001FB2C
0x18001fae5  mov     edx, 4000000h
0x18001faea  lea     rcx, dword_1800411A8
0x18001faf1  call    _tlgKeywordOn
0x18001faf6  test    al, al
0x18001faf8  jz      short loc_18001FB2C
0x18001fafa  lea     rax, aOpenprocesstok; "OpenProcessToken failed."
0x18001fb01  mov     [rbp+var_20], rax
0x18001fb05  call    cs:__imp_GetLastError
0x18001fb0b  mov     [rbp+var_30], eax
0x18001fb0e  lea     rdx, byte_180039E43
0x18001fb15  lea     rax, [rbp+var_20]
0x18001fb19  mov     [rsp+60h+phNewToken], rax
0x18001fb1e  lea     rax, [rbp+var_30]
0x18001fb22  mov     qword ptr [rsp+60h+TokenType], rax
0x18001fb27  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001fb2c  mov     eax, ebx
0x18001fb2e  mov     rcx, [rbp+var_8]
0x18001fb32  xor     rcx, rsp; StackCookie
0x18001fb35  call    __security_check_cookie
0x18001fb3a  mov     rbx, [rsp+60h+arg_0]
0x18001fb3f  add     rsp, 60h
0x18001fb43  pop     rbp
0x18001fb44  retn
```
