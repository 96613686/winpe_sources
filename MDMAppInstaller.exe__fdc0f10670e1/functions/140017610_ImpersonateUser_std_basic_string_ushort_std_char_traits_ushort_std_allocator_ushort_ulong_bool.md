# ImpersonateUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,bool &)

- ea: `0x140017610`
- end: `0x1400177b4`
- name: `?ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z`
- size: `420`
- prototype: `__int64 __fastcall(wchar_t *String2, ULONG SessionId, _BYTE *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14000a5e0`
- `0x140010a2c`
- `0x14001668c`
- `0x1400168b4`

## callees

- `0x140006480`
- `0x14000740c`
- `0x1400074d4`
- `0x14000775c`
- `0x140016ecc`
- `0x140017610`
- `0x140017a88`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x1400176e9`
- `ADVAPI32!GetTokenInformation` at `0x1400176e9`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14001771f`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14001771f`
- `KERNEL32!CloseHandle` at `0x140017790`
- `KERNEL32!CloseHandle` at `0x140017790`
- `KERNEL32!GetLastError` at `0x1400176f6`
- `KERNEL32!GetLastError` at `0x14001774e`
- `KERNEL32!GetLastError` at `0x14001776e`
- `KERNEL32!GetLastError` at `0x1400176f6`
- `KERNEL32!GetLastError` at `0x14001774e`
- `KERNEL32!GetLastError` at `0x14001776e`

## string_xrefs

- `0x14001763e`: `ImpersonateUser - a valid SID must be specified`
- `0x140017663`: `ImpersonateUser - IsRunningInSystemContext() failed - Error 0x%1!x!`
- `0x14001767c`: `ImpersonateUser - Cannot impersoante, not running as SYSTEM.`
- `0x1400176b3`: `ImpersonateUser - GetUserTokenFromSid() failed - Error 0x%1!x!`
- `0x14001770a`: `Failed to get an linked token :0x%1!x!`
- `0x14001773b`: `Impersonated User %1 in session %2!d!.`
- `0x140017762`: `ImpersonateUser - Failed to impersonate - Error 0x%1!x!`

## pseudocode

```c
__int64 __fastcall ImpersonateUser(wchar_t *String2, ULONG SessionId, _BYTE *a3)
{
  bool v3; // zf
  __int64 v7; // rdx
  signed int v8; // ebx
  int v9; // eax
  wchar_t *v10; // rcx
  int UserTokenFromSid; // eax
  HANDLE v12; // rsi
  BOOL v13; // r15d
  signed int LastError; // eax
  wchar_t *v15; // rdx
  signed int v16; // eax
  signed int v17; // eax
  bool v19; // [rsp+30h] [rbp-20h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-1Ch] BYREF
  HANDLE TokenInformation; // [rsp+38h] [rbp-18h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-10h] BYREF

  v3 = *((_QWORD *)String2 + 2) == 0;
  v19 = 0;
  TokenHandle = 0;
  if ( v3 )
  {
    LogError(L"ImpersonateUser - a valid SID must be specified");
    v8 = -2147024809;
    goto LABEL_30;
  }
  v9 = IsRunningInSystemContext(&v19);
  v8 = v9;
  if ( v9 < 0 )
  {
    LogError(L"ImpersonateUser - IsRunningInSystemContext() failed - Error 0x%1!x!", (unsigned int)v9);
    goto LABEL_30;
  }
  if ( !v19 )
  {
    LogError(L"ImpersonateUser - Cannot impersoante, not running as SYSTEM.");
    v8 = -2147467259;
    goto LABEL_30;
  }
  if ( *((_QWORD *)String2 + 3) < 8u )
    v10 = String2;
  else
    v10 = *(wchar_t **)String2;
  UserTokenFromSid = GetUserTokenFromSid(v10, SessionId, &TokenHandle);
  v8 = UserTokenFromSid;
  if ( UserTokenFromSid < 0 )
  {
    LogError(L"ImpersonateUser - GetUserTokenFromSid() failed - Error 0x%1!x!", (unsigned int)UserTokenFromSid);
    goto LABEL_30;
  }
  v12 = TokenHandle;
  ReturnLength = 0;
  TokenInformation = 0;
  v13 = GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength);
  if ( v13 )
  {
    v12 = TokenInformation;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    LogWarn(L"Failed to get an linked token :0x%1!x!", (unsigned int)LastError);
  }
  if ( ImpersonateLoggedOnUser(v12) )
  {
    if ( *((_QWORD *)String2 + 3) < 8u )
      v15 = String2;
    else
      v15 = *(wchar_t **)String2;
    LogInfo(L"Impersonated User %1 in session %2!d!.", v15, SessionId);
    *a3 = 1;
LABEL_28:
    if ( v13 )
      CloseHandle(TokenInformation);
    goto LABEL_30;
  }
  v16 = GetLastError();
  if ( v16 > 0 )
    v16 = (unsigned __int16)v16 | 0x80070000;
  LogError(L"ImpersonateUser - Failed to impersonate - Error 0x%1!x!", (unsigned int)v16);
  v17 = GetLastError();
  v8 = v17;
  if ( v17 > 0 )
    v8 = (unsigned __int16)v17 | 0x80070000;
  if ( v8 >= 0 )
    goto LABEL_28;
LABEL_30:
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(String2, v7, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140017610  push    rbp
0x140017612  push    rbx
0x140017613  push    rsi
0x140017614  push    rdi
0x140017615  push    r12
0x140017617  push    r14
0x140017619  push    r15
0x14001761b  mov     rbp, rsp
0x14001761e  sub     rsp, 50h
0x140017622  cmp     qword ptr [rcx+10h], 0
0x140017627  mov     r12, r8
0x14001762a  mov     r14d, edx
0x14001762d  mov     [rbp+var_20], 0
0x140017631  mov     rdi, rcx
0x140017634  mov     [rbp+TokenHandle], 0
0x14001763c  jnz     short loc_140017654
0x14001763e  lea     rcx, aImpersonateuse_1; "ImpersonateUser - a valid SID must be s"...
0x140017645  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001764a  mov     ebx, 80070057h
0x14001764f  jmp     loc_140017796
0x140017654  lea     rcx, [rbp+var_20]; bool *
0x140017658  call    ?IsRunningInSystemContext@@YAJAEA_N@Z; IsRunningInSystemContext(bool &)
0x14001765d  mov     ebx, eax
0x14001765f  test    eax, eax
0x140017661  jns     short loc_140017676
0x140017663  lea     rcx, aImpersonateuse_0; "ImpersonateUser - IsRunningInSystemCont"...
0x14001766a  mov     edx, eax
0x14001766c  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140017671  jmp     loc_140017796
0x140017676  cmp     [rbp+var_20], 0
0x14001767a  jnz     short loc_140017692
0x14001767c  lea     rcx, aImpersonateuse; "ImpersonateUser - Cannot impersoante, n"...
0x140017683  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140017688  mov     ebx, 80004005h
0x14001768d  jmp     loc_140017796
0x140017692  cmp     qword ptr [rdi+18h], 8
0x140017697  jb      short loc_14001769E
0x140017699  mov     rcx, [rdi]
0x14001769c  jmp     short loc_1400176A1
0x14001769e  mov     rcx, rdi; String2
0x1400176a1  lea     r8, [rbp+TokenHandle]; void **
0x1400176a5  mov     edx, r14d; SessionId
0x1400176a8  call    ?GetUserTokenFromSid@@YAJPEBGKPEAPEAX@Z; GetUserTokenFromSid(ushort const *,ulong,void * *)
0x1400176ad  mov     ebx, eax
0x1400176af  test    eax, eax
0x1400176b1  jns     short loc_1400176BC
0x1400176b3  lea     rcx, aImpersonateuse_2; "ImpersonateUser - GetUserTokenFromSid()"...
0x1400176ba  jmp     short loc_14001766A
0x1400176bc  mov     rsi, [rbp+TokenHandle]
0x1400176c0  lea     rax, [rbp+var_1C]
0x1400176c4  mov     r9d, 8; TokenInformationLength
0x1400176ca  mov     [rbp+var_1C], 0
0x1400176d1  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400176d5  mov     [rbp+TokenInformation], 0
0x1400176dd  mov     rcx, rsi; TokenHandle
0x1400176e0  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1400176e5  lea     edx, [r9+0Bh]; TokenInformationClass
0x1400176e9  call    cs:__imp_GetTokenInformation
0x1400176ef  mov     r15d, eax
0x1400176f2  test    eax, eax
0x1400176f4  jnz     short loc_140017718
0x1400176f6  call    cs:__imp_GetLastError
0x1400176fc  test    eax, eax
0x1400176fe  jle     short loc_140017708
0x140017700  movzx   eax, ax
0x140017703  or      eax, 80070000h
0x140017708  mov     edx, eax
0x14001770a  lea     rcx, aFailedToGetAnL; "Failed to get an linked token :0x%1!x!"
0x140017711  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x140017716  jmp     short loc_14001771C
0x140017718  mov     rsi, [rbp+TokenInformation]
0x14001771c  mov     rcx, rsi; hToken
0x14001771f  call    cs:__imp_ImpersonateLoggedOnUser
0x140017725  test    eax, eax
0x140017727  jz      short loc_14001774E
0x140017729  cmp     qword ptr [rdi+18h], 8
0x14001772e  jb      short loc_140017735
0x140017730  mov     rdx, [rdi]
0x140017733  jmp     short loc_140017738
0x140017735  mov     rdx, rdi
0x140017738  mov     r8d, r14d
0x14001773b  lea     rcx, aImpersonatedUs; "Impersonated User %1 in session %2!d!."
0x140017742  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140017747  mov     byte ptr [r12], 1
0x14001774c  jmp     short loc_140017787
0x14001774e  call    cs:__imp_GetLastError
0x140017754  test    eax, eax
0x140017756  jle     short loc_140017760
0x140017758  movzx   eax, ax
0x14001775b  or      eax, 80070000h
0x140017760  mov     edx, eax
0x140017762  lea     rcx, aImpersonateuse_3; "ImpersonateUser - Failed to impersonate"...
0x140017769  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001776e  call    cs:__imp_GetLastError
0x140017774  mov     ebx, eax
0x140017776  test    eax, eax
0x140017778  jle     short loc_140017783
0x14001777a  movzx   ebx, ax
0x14001777d  or      ebx, 80070000h
0x140017783  test    ebx, ebx
0x140017785  js      short loc_140017796
0x140017787  test    r15d, r15d
0x14001778a  jz      short loc_140017796
0x14001778c  mov     rcx, [rbp+TokenInformation]; hObject
0x140017790  call    cs:__imp_CloseHandle
0x140017796  xor     r8d, r8d
0x140017799  mov     dl, 1
0x14001779b  mov     rcx, rdi
0x14001779e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1400177a3  mov     eax, ebx
0x1400177a5  add     rsp, 50h
0x1400177a9  pop     r15
0x1400177ab  pop     r14
0x1400177ad  pop     r12
0x1400177af  pop     rdi
0x1400177b0  pop     rsi
0x1400177b1  pop     rbx
0x1400177b2  pop     rbp
0x1400177b3  retn
```
