# WpnConnectionManager::VerifyCallerUserId(void)

- ea: `0x18000abc0`
- end: `0x18000aed9`
- name: `?VerifyCallerUserId@WpnConnectionManager@@AEAAJXZ`
- size: `793`
- prototype: `__int64 __fastcall(WpnConnectionManager *__hidden this)`
- caller_count: `11`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003e60`
- `0x1800054a0`
- `0x180006eb0`
- `0x180008780`
- `0x180014710`
- `0x180021e50`
- `0x180024cd0`
- `0x180024ec0`
- `0x180025530`
- `0x180025730`
- `0x18002e580`

## callees

- `0x18000abc0`
- `0x18000aee0`
- `0x1800202bc`
- `0x180021048`
- `0x1800238d0`
- `0x180026200`
- `0x180026d3c`
- `0x180031da0`
- `0x180031dc4`
- `0x1800342bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ac08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ac08`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000ac5d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000ac5d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000ac20`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000ac20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ac4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ac4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aebf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aebf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ac7a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ac7a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000abeb`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000abeb`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18000ad4e`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18000ad4e`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000ad36`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000ad36`
- `ntdll!RtlInitializeSidEx` at `0x18000acbd`
- `ntdll!RtlInitializeSidEx` at `0x18000acbd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000acda`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000adb5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000acda`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000adb5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000adef`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000adef`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000ae0f`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000ae0f`

## string_xrefs

- `0x18000ad7a`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnusermgrutil.cpp`
- `0x18000ae59`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnusermgrutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall WpnConnectionManager::VerifyCallerUserId(WpnConnectionManager *this)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  HANDLE CurrentProcess; // rax
  const char *v6; // r9
  void *v7; // rbx
  int v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  unsigned __int64 UserIdForContext; // rbx
  bool v13; // di
  unsigned int v14; // r8d
  const char *v15; // r9
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  WINBOOL IsMember; // [rsp+20h] [rbp-49h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-41h] BYREF
  int v24; // [rsp+30h] [rbp-39h] BYREF
  DWORD cbSid; // [rsp+34h] [rbp-35h] BYREF
  __int16 v26; // [rsp+38h] [rbp-31h]
  _OWORD SidToCheck[4]; // [rsp+40h] [rbp-29h] BYREF
  int v28; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  CoImpersonateClient();
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_6;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 == -2147023888 || v4 >= 0 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      v4 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x25,
             (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnusermgrutil.cpp",
             v6);
      goto LABEL_7;
    }
LABEL_6:
    v4 = 0;
    goto LABEL_7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnusermgrutil.cpp",
    (const char *)(unsigned int)v4,
    IsMember);
LABEL_7:
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\wpnutils.cpp",
      (const char *)(unsigned int)v4,
      IsMember);
  CoRevertToSelf();
  v7 = TokenHandle;
  memset(SidToCheck, 0, sizeof(SidToCheck));
  v28 = 0;
  cbSid = 0;
  v26 = 1280;
  IsMember = 0;
  v8 = RtlInitializeSidEx(SidToCheck, &cbSid, 1, 18);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, v9, v10, (const char *)(unsigned int)v8, IsMember);
  if ( !CheckTokenMembership(v7, SidToCheck, &IsMember) )
  {
    if ( GetLastError() != 1309 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x69, v14, v15);
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x6B, v16, v17);
  }
  if ( IsMember )
    goto LABEL_11;
  IsMember = 0;
  RtlGetDeviceFamilyInfoEnum(0, &IsMember, 0);
  v13 = (unsigned int)(IsMember - 7) <= 1;
  if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() || v13 )
  {
    cbSid = 68;
    v24 = 0;
    if ( !CreateWellKnownSid(WinAccountProtectedUsersSid|WinCreatorGroupSid, 0, SidToCheck, &cbSid) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x93, v18, v19);
    if ( !(unsigned int)CheckTokenMembershipEx(v7, SidToCheck, 0, &v24) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x95, v20, v21);
    if ( v24 == 1 )
      goto LABEL_11;
  }
  if ( !(unsigned __int8)IsUMgrQueryUserContextPresent() )
LABEL_11:
    UserIdForContext = 0;
  else
    UserIdForContext = GetUserIdForContext(v7);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  if ( *((_QWORD *)this + 4) == UserIdForContext )
    return 0;
  MicrosoftTelemetryAssertTriggeredNoArgs();
  return 2147549183LL;
}

```

## disassembly

```asm
0x18000abc0  push    rbp
0x18000abc2  push    rbx
0x18000abc3  push    rsi
0x18000abc4  push    rdi
0x18000abc5  push    r14
0x18000abc7  lea     rbp, [rsp-37h]
0x18000abcc  sub     rsp, 0A0h
0x18000abd3  mov     rax, cs:__security_cookie
0x18000abda  xor     rax, rsp
0x18000abdd  mov     [rbp+57h+var_28], rax
0x18000abe1  mov     rsi, rcx
0x18000abe4  xor     r14d, r14d
0x18000abe7  mov     [rbp+57h+TokenHandle], r14
0x18000abeb  call    cs:__imp_CoImpersonateClient
0x18000abf1  nop
0x18000abf2  mov     rdi, [rbp+57h+TokenHandle]
0x18000abf6  lea     rax, [rdi-1]
0x18000abfa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000abfe  jbe     loc_18000AE2C
0x18000ac04  mov     [rbp+57h+TokenHandle], r14
0x18000ac08  call    cs:__imp_GetCurrentThread
0x18000ac0e  mov     rcx, rax; ThreadHandle
0x18000ac11  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000ac15  mov     edx, 8; DesiredAccess
0x18000ac1a  mov     r8d, 1; OpenAsSelf
0x18000ac20  call    cs:__imp_OpenThreadToken
0x18000ac26  test    eax, eax
0x18000ac28  jnz     short loc_18000AC6B
0x18000ac2a  call    cs:__imp_GetLastError
0x18000ac30  mov     ebx, eax
0x18000ac32  test    eax, eax
0x18000ac34  jle     short loc_18000AC3F
0x18000ac36  movzx   ebx, ax
0x18000ac39  or      ebx, 80070000h
0x18000ac3f  cmp     ebx, 800703F0h
0x18000ac45  jnz     loc_18000AE4A
0x18000ac4b  call    cs:__imp_GetCurrentProcess
0x18000ac51  mov     rcx, rax; ProcessHandle
0x18000ac54  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000ac58  mov     edx, 8; DesiredAccess
0x18000ac5d  call    cs:__imp_OpenProcessToken
0x18000ac63  test    eax, eax
0x18000ac65  jz      loc_18000AD76
0x18000ac6b  mov     ebx, r14d
0x18000ac6e  mov     rcx, [rbp+5Fh]; this
0x18000ac72  test    ebx, ebx
0x18000ac74  js      loc_18000AE6F
0x18000ac7a  call    cs:__imp_CoRevertToSelf
0x18000ac80  mov     rbx, [rbp+57h+TokenHandle]
0x18000ac84  xorps   xmm0, xmm0
0x18000ac87  xor     eax, eax
0x18000ac89  movups  [rbp+57h+SidToCheck], xmm0
0x18000ac8d  movups  [rbp+57h+var_70], xmm0
0x18000ac91  movups  [rbp+57h+var_60], xmm0
0x18000ac95  movups  [rbp+57h+var_50], xmm0
0x18000ac99  mov     [rbp+57h+var_40], eax
0x18000ac9c  mov     [rbp+57h+cbSid], eax
0x18000ac9f  mov     [rbp+57h+var_88], 500h
0x18000aca5  mov     [rbp+57h+IsMember], r14d
0x18000aca9  mov     r9d, 12h
0x18000acaf  mov     r8d, 1
0x18000acb5  lea     rdx, [rbp+57h+cbSid]
0x18000acb9  lea     rcx, [rbp+57h+SidToCheck]
0x18000acbd  call    cs:__imp_RtlInitializeSidEx
0x18000acc3  mov     rcx, [rbp+5Fh]; this
0x18000acc7  test    eax, eax
0x18000acc9  js      loc_18000AE84
0x18000accf  lea     r8, [rbp+57h+IsMember]; IsMember
0x18000acd3  lea     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18000acd7  mov     rcx, rbx; TokenHandle
0x18000acda  call    cs:__imp_CheckTokenMembership
0x18000ace0  test    eax, eax
0x18000ace2  jz      loc_18000AD92
0x18000ace8  cmp     [rbp+57h+IsMember], 0
0x18000acec  jz      short loc_18000AD29
0x18000acee  mov     rbx, r14
0x18000acf1  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000acf5  lea     rax, [rcx-1]
0x18000acf9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000acfd  jbe     loc_18000AEBF
0x18000ad03  cmp     [rsi+20h], rbx
0x18000ad07  jnz     loc_18000AECA
0x18000ad0d  xor     eax, eax
0x18000ad0f  mov     rcx, [rbp+57h+var_28]
0x18000ad13  xor     rcx, rsp; StackCookie
0x18000ad16  call    __security_check_cookie
0x18000ad1b  add     rsp, 0A0h
0x18000ad22  pop     r14
0x18000ad24  pop     rdi
0x18000ad25  pop     rsi
0x18000ad26  pop     rbx
0x18000ad27  pop     rbp
0x18000ad28  retn
0x18000ad29  mov     [rbp+57h+IsMember], r14d
0x18000ad2d  xor     r8d, r8d
0x18000ad30  lea     rdx, [rbp+57h+IsMember]
0x18000ad34  xor     ecx, ecx
0x18000ad36  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18000ad3c  mov     eax, [rbp+57h+IsMember]
0x18000ad3f  add     eax, 0FFFFFFF9h
0x18000ad42  cmp     eax, 1
0x18000ad45  ja      loc_18000AE9B
0x18000ad4b  mov     dil, 1
0x18000ad4e  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18000ad54  test    al, al
0x18000ad56  jnz     short loc_18000ADD1
0x18000ad58  test    dil, dil
0x18000ad5b  jnz     short loc_18000ADD1
0x18000ad5d  call    IsUMgrQueryUserContextPresent
0x18000ad62  test    al, al
0x18000ad64  jz      short loc_18000ACEE
0x18000ad66  mov     rcx, rbx; void *
0x18000ad69  call    ?GetUserIdForContext@@YA_KPEAX@Z; GetUserIdForContext(void *)
0x18000ad6e  mov     rbx, rax
0x18000ad71  jmp     loc_18000ACF1
0x18000ad76  mov     rcx, [rbp+5Fh]; this
0x18000ad7a  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000ad81  mov     edx, 25h ; '%'; void *
0x18000ad86  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ad8b  mov     ebx, eax
0x18000ad8d  jmp     loc_18000AC6E
0x18000ad92  mov     rdi, [rbp+5Fh]
0x18000ad96  call    cs:__imp_GetLastError
0x18000ad9c  cmp     eax, 51Dh
0x18000ada1  jnz     loc_18000AE8D
0x18000ada7  mov     rdi, [rbp+5Fh]
0x18000adab  lea     r8, [rbp+57h+IsMember]; IsMember
0x18000adaf  lea     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18000adb3  xor     ecx, ecx; TokenHandle
0x18000adb5  call    cs:__imp_CheckTokenMembership
0x18000adbb  test    eax, eax
0x18000adbd  jnz     loc_18000ACE8
0x18000adc3  mov     edx, 6Bh ; 'k'; void *
0x18000adc8  mov     rcx, rdi; this
0x18000adcb  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000add1  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18000add8  mov     [rbp+57h+var_90], r14d
0x18000addc  mov     rdi, [rbp+5Fh]
0x18000ade0  lea     r9, [rbp+57h+cbSid]; cbSid
0x18000ade4  lea     r8, [rbp+57h+SidToCheck]; pSid
0x18000ade8  xor     edx, edx; DomainSid
0x18000adea  mov     ecx, 6Fh ; 'o'; WellKnownSidType
0x18000adef  call    cs:__imp_CreateWellKnownSid
0x18000adf5  test    eax, eax
0x18000adf7  jz      loc_18000AEA3
0x18000adfd  mov     rdi, [rbp+5Fh]
0x18000ae01  lea     r9, [rbp+57h+var_90]
0x18000ae05  xor     r8d, r8d
0x18000ae08  lea     rdx, [rbp+57h+SidToCheck]
0x18000ae0c  mov     rcx, rbx
0x18000ae0f  call    cs:__imp_CheckTokenMembershipEx
0x18000ae15  test    eax, eax
0x18000ae17  jz      loc_18000AEB1
0x18000ae1d  cmp     [rbp+57h+var_90], 1
0x18000ae21  jz      loc_18000ACEE
0x18000ae27  jmp     loc_18000AD5D
0x18000ae2c  call    cs:__imp_GetLastError
0x18000ae32  mov     ebx, eax
0x18000ae34  mov     rcx, rdi; hObject
0x18000ae37  call    cs:__imp_CloseHandle
0x18000ae3d  mov     ecx, ebx; dwErrCode
0x18000ae3f  call    cs:__imp_SetLastError
0x18000ae45  jmp     loc_18000AC04
0x18000ae4a  test    ebx, ebx
0x18000ae4c  jns     loc_18000AC4B
0x18000ae52  mov     rcx, [rbp+5Fh]; this
0x18000ae56  mov     r9d, ebx; char *
0x18000ae59  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000ae60  mov     edx, 1Fh; void *
0x18000ae65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae6a  jmp     loc_18000AC6E
0x18000ae6f  mov     r9d, ebx; char *
0x18000ae72  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000ae79  mov     edx, 47h ; 'G'; void *
0x18000ae7e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000ae84  mov     r9d, eax; char *
0x18000ae87  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18000ae8d  mov     edx, 69h ; 'i'; void *
0x18000ae92  mov     rcx, rdi; this
0x18000ae95  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000ae9b  xor     dil, dil
0x18000ae9e  jmp     loc_18000AD4E
0x18000aea3  mov     edx, 93h; void *
0x18000aea8  mov     rcx, rdi; this
0x18000aeab  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000aeb1  mov     edx, 95h; void *
0x18000aeb6  mov     rcx, rdi; this
0x18000aeb9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000aebf  call    cs:__imp_CloseHandle
0x18000aec5  jmp     loc_18000AD03
0x18000aeca  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000aecf  mov     eax, 8000FFFFh
0x18000aed4  jmp     loc_18000AD0F
```
