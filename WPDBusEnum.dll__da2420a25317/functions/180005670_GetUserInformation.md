# GetUserInformation

- ea: `0x180005670`
- end: `0x180005893`
- name: `GetUserInformation`
- size: `547`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013038`
- `0x18001396c`

## callees

- `0x180005670`
- `0x180012ca8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005886`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005745`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005745`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000571a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005865`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000571a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005865`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005705`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005705`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800057e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800057e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005831`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005831`
- `KERNEL32!RegOpenCurrentUser` at `0x1800056d9`
- `KERNEL32!RegOpenCurrentUser` at `0x1800056d9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000572a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000572a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000576f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000576f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800057b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005818`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800057b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005818`
- `WTSAPI32!WTSQueryUserToken` at `0x1800056ab`
- `WTSAPI32!WTSQueryUserToken` at `0x1800056ab`

## pseudocode

```c
DWORD __fastcall GetUserInformation(ULONG a1, const WCHAR *a2, _QWORD *a3, DWORD *a4, LSTATUS *a5)
{
  LSTATUS *v5; // rsi
  DWORD LastError; // ebx
  LSTATUS AccessRights; // ebx
  void *v12; // r15
  HLOCAL v13; // rbp
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-40h] BYREF
  void *phToken; // [rsp+40h] [rbp-38h] BYREF
  DWORD ReturnLength; // [rsp+98h] [rbp+20h] BYREF

  v5 = a5;
  phkResult = 0;
  phToken = 0;
  if ( a4 )
  {
    *a4 = 0;
    *v5 = 0;
  }
  if ( !WTSQueryUserToken(a1, &phToken) )
    return GetLastError();
  if ( !ImpersonateLoggedOnUser(phToken) )
  {
    LastError = GetLastError();
    goto LABEL_12;
  }
  v12 = phToken;
  ReturnLength = 0;
  if ( GetTokenInformation(phToken, TokenUser, 0, 0, &ReturnLength) )
    goto LABEL_10;
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v13 = LocalAlloc(0x40u, ReturnLength);
    if ( !v13 )
    {
      LastError = 8;
      goto LABEL_11;
    }
    if ( !GetTokenInformation(v12, TokenUser, v13, ReturnLength, &ReturnLength) )
    {
      LastError = GetLastError();
      LocalFree(v13);
      goto LABEL_11;
    }
    *a3 = v13;
    LastError = 0;
    if ( a4 )
    {
      AccessRights = RegOpenCurrentUser(0x20019u, &phkResult);
      if ( !AccessRights )
      {
        hKey = 0;
        AccessRights = RegOpenKeyExW(phkResult, a2, 0, 0x20019u, &hKey);
        if ( !AccessRights )
        {
          ReturnLength = 0;
          AccessRights = GetAccessRights(hKey);
          RegCloseKey(hKey);
          hKey = 0;
          if ( !AccessRights )
            *a4 = ReturnLength;
        }
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      *v5 = AccessRights;
LABEL_10:
      LastError = 0;
    }
  }
LABEL_11:
  RevertToSelf();
LABEL_12:
  CloseHandle(phToken);
  return LastError;
}

```

## disassembly

```asm
0x180005670  push    rsi
0x180005672  push    rdi
0x180005673  push    r12
0x180005675  push    r13
0x180005677  push    r14
0x180005679  sub     rsp, 50h
0x18000567d  mov     rsi, [rsp+78h+arg_20]
0x180005685  xor     r13d, r13d
0x180005688  mov     [rsp+78h+phkResult], r13
0x18000568d  mov     rdi, r9
0x180005690  mov     [rsp+78h+phToken], r13
0x180005695  mov     r14, r8
0x180005698  mov     r12, rdx
0x18000569b  test    r9, r9
0x18000569e  jz      short loc_1800056A6
0x1800056a0  mov     [r9], r13d
0x1800056a3  mov     [rsi], r13d
0x1800056a6  lea     rdx, [rsp+78h+phToken]; phToken
0x1800056ab  call    cs:__imp_WTSQueryUserToken
0x1800056b1  test    eax, eax
0x1800056b3  jnz     loc_180005762
0x1800056b9  call    cs:__imp_GetLastError
0x1800056bf  jmp     loc_180005755
0x1800056c4  mov     [r14], rbp
0x1800056c7  mov     ebx, r13d
0x1800056ca  test    rdi, rdi
0x1800056cd  jz      short loc_18000572A
0x1800056cf  lea     rdx, [rsp+78h+phkResult]; phkResult
0x1800056d4  mov     ecx, 20019h; samDesired
0x1800056d9  call    cs:__imp_RegOpenCurrentUser
0x1800056df  mov     ebx, eax
0x1800056e1  test    eax, eax
0x1800056e3  jnz     short loc_180005725
0x1800056e5  mov     rcx, [rsp+78h+phkResult]; hKey
0x1800056ea  lea     rax, [rsp+78h+hKey]
0x1800056ef  mov     r9d, 20019h; samDesired
0x1800056f5  mov     [rsp+78h+var_58], rax; phkResult
0x1800056fa  xor     r8d, r8d; ulOptions
0x1800056fd  mov     [rsp+78h+hKey], r13
0x180005702  mov     rdx, r12; lpSubKey
0x180005705  call    cs:__imp_RegOpenKeyExW
0x18000570b  mov     ebx, eax
0x18000570d  test    eax, eax
0x18000570f  jz      loc_18000583C
0x180005715  mov     rcx, [rsp+78h+phkResult]; hKey
0x18000571a  call    cs:__imp_RegCloseKey
0x180005720  mov     [rsp+78h+phkResult], r13
0x180005725  mov     [rsi], ebx
0x180005727  mov     ebx, r13d
0x18000572a  call    cs:__imp_RevertToSelf
0x180005730  mov     r15, [rsp+78h+arg_10]
0x180005738  mov     rbp, [rsp+78h+arg_8]
0x180005740  mov     rcx, [rsp+78h+phToken]; hObject
0x180005745  call    cs:__imp_CloseHandle
0x18000574b  mov     eax, ebx
0x18000574d  mov     rbx, [rsp+78h+arg_0]
0x180005755  add     rsp, 50h
0x180005759  pop     r14
0x18000575b  pop     r13
0x18000575d  pop     r12
0x18000575f  pop     rdi
0x180005760  pop     rsi
0x180005761  retn
0x180005762  mov     rcx, [rsp+78h+phToken]; hToken
0x180005767  mov     [rsp+78h+arg_0], rbx
0x18000576f  call    cs:__imp_ImpersonateLoggedOnUser
0x180005775  test    eax, eax
0x180005777  jz      loc_180005886
0x18000577d  mov     [rsp+78h+arg_10], r15
0x180005785  lea     rax, [rsp+78h+ReturnLength]
0x18000578d  mov     r15, [rsp+78h+phToken]
0x180005792  xor     r9d, r9d; TokenInformationLength
0x180005795  mov     rcx, r15; TokenHandle
0x180005798  mov     [rsp+78h+arg_8], rbp
0x1800057a0  xor     r8d, r8d; TokenInformation
0x1800057a3  mov     [rsp+78h+ReturnLength], r13d
0x1800057ab  mov     edx, 1; TokenInformationClass
0x1800057b0  mov     [rsp+78h+var_58], rax; ReturnLength
0x1800057b5  call    cs:__imp_GetTokenInformation
0x1800057bb  test    eax, eax
0x1800057bd  jnz     loc_180005727
0x1800057c3  call    cs:__imp_GetLastError
0x1800057c9  mov     ebx, eax
0x1800057cb  cmp     eax, 7Ah ; 'z'
0x1800057ce  jnz     loc_18000572A
0x1800057d4  mov     edx, [rsp+78h+ReturnLength]; uBytes
0x1800057db  mov     ecx, 40h ; '@'; uFlags
0x1800057e0  call    cs:__imp_LocalAlloc
0x1800057e6  mov     rbp, rax
0x1800057e9  test    rax, rax
0x1800057ec  jnz     short loc_1800057F8
0x1800057ee  mov     ebx, 8
0x1800057f3  jmp     loc_18000572A
0x1800057f8  mov     r9d, [rsp+78h+ReturnLength]; TokenInformationLength
0x180005800  lea     rax, [rsp+78h+ReturnLength]
0x180005808  mov     r8, rbp; TokenInformation
0x18000580b  mov     [rsp+78h+var_58], rax; ReturnLength
0x180005810  mov     edx, 1; TokenInformationClass
0x180005815  mov     rcx, r15; TokenHandle
0x180005818  call    cs:__imp_GetTokenInformation
0x18000581e  test    eax, eax
0x180005820  jnz     loc_1800056C4
0x180005826  call    cs:__imp_GetLastError
0x18000582c  mov     rcx, rbp; hMem
0x18000582f  mov     ebx, eax
0x180005831  call    cs:__imp_LocalFree
0x180005837  jmp     loc_18000572A
0x18000583c  mov     r8d, [rsp+78h+arg_28]
0x180005844  lea     rdx, [rsp+78h+ReturnLength]
0x18000584c  mov     rcx, [rsp+78h+hKey]; hKey
0x180005851  mov     [rsp+78h+ReturnLength], r13d
0x180005859  call    GetAccessRights
0x18000585e  mov     rcx, [rsp+78h+hKey]; hKey
0x180005863  mov     ebx, eax
0x180005865  call    cs:__imp_RegCloseKey
0x18000586b  mov     [rsp+78h+hKey], r13
0x180005870  test    ebx, ebx
0x180005872  jnz     loc_180005715
0x180005878  mov     eax, [rsp+78h+ReturnLength]
0x18000587f  mov     [rdi], eax
0x180005881  jmp     loc_180005715
0x180005886  call    cs:__imp_GetLastError
0x18000588c  mov     ebx, eax
0x18000588e  jmp     loc_180005740
```
