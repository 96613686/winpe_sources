# EdpCredSvcQueryContextUserSid(unsigned __int64,ushort * *)

- ea: `0x180084d34`
- end: `0x180084f89`
- name: `?EdpCredSvcQueryContextUserSid@@YAJ_KPEAPEAG@Z`
- size: `597`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180083c44`
- `0x180086c60`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180084d34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180084e57`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180084e57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180084e46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180084f65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180084e46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180084f65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084f73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ed3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084f52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084f52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084f3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084f3b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180084e09`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180084e96`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180084e09`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180084e96`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180084ec9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180084ec9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180084d6d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180084d6d`

## pseudocode

```c
__int64 __fastcall EdpCredSvcQueryContextUserSid(__int64 a1, unsigned __int16 **a2)
{
  PSID *v2; // rbx
  int v4; // ecx
  unsigned int UserToken; // edi
  signed int v6; // eax
  int v7; // r8d
  DWORD v8; // ebx
  HANDLE ProcessHeap; // rax
  signed int v10; // eax
  signed int LastError; // eax
  HANDLE v12; // rax
  char ReturnLength; // [rsp+20h] [rbp-30h]
  HANDLE TokenHandle[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+78h] [rbp+28h] BYREF
  DWORD v17; // [rsp+80h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  TokenHandle[0] = 0;
  TokenInformationLength = 0;
  v17 = 0;
  StringSid = 0;
  if ( !a2 )
  {
    UserToken = -2147467261;
    ReturnLength = -50;
    v7 = -2147467261;
    goto LABEL_23;
  }
  *a2 = 0;
  UserToken = UMgrQueryUserToken(a1, TokenHandle);
  if ( UserToken == -2147023584 )
  {
    UserToken = 1;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 38, 220);
    goto LABEL_24;
  }
  fnEfsLogTrace1Strings(v4, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 224);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              UserToken,
              38,
              224) >= 0 )
  {
    if ( GetTokenInformation(TokenHandle[0], TokenUser, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
    {
      v8 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v2 = (PSID *)HeapAlloc(ProcessHeap, 8u, v8);
      if ( !v2 )
      {
        UserToken = -2147024882;
        ReturnLength = -11;
        v7 = -2147024882;
        goto LABEL_23;
      }
      if ( GetTokenInformation(TokenHandle[0], TokenUser, v2, TokenInformationLength, &v17) )
      {
        if ( ConvertSidToStringSidW(*v2, &StringSid) )
        {
          *a2 = StringSid;
          StringSid = 0;
          goto LABEL_24;
        }
        LastError = GetLastError();
        UserToken = LastError;
        if ( LastError > 0 )
          UserToken = (unsigned __int16)LastError | 0x80070000;
        ReturnLength = 6;
      }
      else
      {
        v10 = GetLastError();
        UserToken = v10;
        if ( v10 > 0 )
          UserToken = (unsigned __int16)v10 | 0x80070000;
        ReturnLength = -3;
      }
    }
    else
    {
      v6 = GetLastError();
      UserToken = v6;
      if ( v6 > 0 )
        UserToken = (unsigned __int16)v6 | 0x80070000;
      ReturnLength = -17;
    }
    v7 = UserToken;
LABEL_23:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v7, 38, ReturnLength);
  }
LABEL_24:
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( TokenHandle[0] )
  {
    CloseHandle(TokenHandle[0]);
    TokenHandle[0] = 0;
  }
  if ( v2 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v2);
  }
  return UserToken;
}

```

## disassembly

```asm
0x180084d34  mov     [rsp-18h+arg_0], rbx
0x180084d39  push    rbp
0x180084d3a  push    rdi
0x180084d3b  push    r15
0x180084d3d  mov     rbp, rsp
0x180084d40  sub     rsp, 50h
0x180084d44  xor     ebx, ebx
0x180084d46  mov     [rbp+TokenHandle], 0
0x180084d4e  mov     [rbp+TokenInformationLength], ebx
0x180084d51  mov     r15, rdx
0x180084d54  mov     [rbp+arg_10], ebx
0x180084d57  mov     [rbp+StringSid], rbx
0x180084d5b  test    rdx, rdx
0x180084d5e  jz      loc_180084F06
0x180084d64  xor     eax, eax
0x180084d66  mov     [rdx], rax
0x180084d69  lea     rdx, [rbp+TokenHandle]
0x180084d6d  call    cs:__imp_UMgrQueryUserToken
0x180084d73  lea     r9d, [rbx+26h]
0x180084d77  mov     edi, eax
0x180084d79  cmp     eax, 80070520h
0x180084d7e  jnz     short loc_180084D9A
0x180084d80  lea     edi, [rbx+1]
0x180084d83  mov     dword ptr [rsp+50h+ReturnLength], 9DCh
0x180084d8b  mov     r8d, edi
0x180084d8e  lea     rdx, EFS_TRACE_STATUS
0x180084d95  jmp     loc_180084F26
0x180084d9a  lea     r8, sourceString
0x180084da1  mov     dword ptr [rsp+50h+ReturnLength], 9E0h
0x180084da9  lea     rdx, EFS_TRACE_START_EVENT
0x180084db0  call    fnEfsLogTrace1Strings
0x180084db5  mov     rcx, cs:g_hPublisher
0x180084dbc  lea     r9, sourceString
0x180084dc3  mov     [rsp+50h+var_20], 9E0h
0x180084dcb  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180084dd2  mov     [rsp+50h+var_28], 26h ; '&'
0x180084dda  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180084de1  mov     dword ptr [rsp+50h+ReturnLength], edi
0x180084de5  call    fnEfsLogTrace1String1Dword
0x180084dea  test    eax, eax
0x180084dec  js      loc_180084F32
0x180084df2  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180084df6  lea     rax, [rbp+TokenInformationLength]
0x180084dfa  xor     r9d, r9d; TokenInformationLength
0x180084dfd  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180084e02  xor     r8d, r8d; TokenInformation
0x180084e05  lea     edx, [r9+1]; TokenInformationClass
0x180084e09  call    cs:__imp_GetTokenInformation
0x180084e0f  test    eax, eax
0x180084e11  jnz     short loc_180084E43
0x180084e13  call    cs:__imp_GetLastError
0x180084e19  cmp     eax, 7Ah ; 'z'
0x180084e1c  jz      short loc_180084E43
0x180084e1e  call    cs:__imp_GetLastError
0x180084e24  mov     edi, eax
0x180084e26  test    eax, eax
0x180084e28  jle     short loc_180084E33
0x180084e2a  movzx   edi, ax
0x180084e2d  or      edi, 80070000h
0x180084e33  mov     dword ptr [rsp+50h+ReturnLength], 9EFh
0x180084e3b  mov     r8d, edi
0x180084e3e  jmp     loc_180084F19
0x180084e43  mov     ebx, [rbp+TokenInformationLength]
0x180084e46  call    cs:__imp_GetProcessHeap
0x180084e4c  mov     r8d, ebx; dwBytes
0x180084e4f  mov     edx, 8; dwFlags
0x180084e54  mov     rcx, rax; hHeap
0x180084e57  call    cs:__imp_HeapAlloc
0x180084e5d  mov     rbx, rax
0x180084e60  test    rax, rax
0x180084e63  jnz     short loc_180084E7D
0x180084e65  mov     edi, 8007000Eh
0x180084e6a  mov     dword ptr [rsp+50h+ReturnLength], 9F5h
0x180084e72  mov     r8d, 8007000Eh
0x180084e78  jmp     loc_180084F19
0x180084e7d  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180084e81  lea     rax, [rbp+arg_10]
0x180084e85  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180084e89  mov     r8, rbx; TokenInformation
0x180084e8c  mov     edx, 1; TokenInformationClass
0x180084e91  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180084e96  call    cs:__imp_GetTokenInformation
0x180084e9c  test    eax, eax
0x180084e9e  jnz     short loc_180084EC2
0x180084ea0  call    cs:__imp_GetLastError
0x180084ea6  mov     edi, eax
0x180084ea8  test    eax, eax
0x180084eaa  jle     short loc_180084EB5
0x180084eac  movzx   edi, ax
0x180084eaf  or      edi, 80070000h
0x180084eb5  mov     dword ptr [rsp+50h+ReturnLength], 9FDh
0x180084ebd  jmp     loc_180084E3B
0x180084ec2  mov     rcx, [rbx]; Sid
0x180084ec5  lea     rdx, [rbp+StringSid]; StringSid
0x180084ec9  call    cs:__imp_ConvertSidToStringSidW
0x180084ecf  test    eax, eax
0x180084ed1  jnz     short loc_180084EF5
0x180084ed3  call    cs:__imp_GetLastError
0x180084ed9  mov     edi, eax
0x180084edb  test    eax, eax
0x180084edd  jle     short loc_180084EE8
0x180084edf  movzx   edi, ax
0x180084ee2  or      edi, 80070000h
0x180084ee8  mov     dword ptr [rsp+50h+ReturnLength], 0A06h
0x180084ef0  jmp     loc_180084E3B
0x180084ef5  mov     rax, [rbp+StringSid]
0x180084ef9  mov     [r15], rax
0x180084efc  mov     [rbp+StringSid], 0
0x180084f04  jmp     short loc_180084F32
0x180084f06  mov     edi, 80004003h
0x180084f0b  mov     dword ptr [rsp+50h+ReturnLength], 9CEh
0x180084f13  mov     r8d, 80004003h
0x180084f19  mov     r9d, 26h ; '&'
0x180084f1f  lea     rdx, EFS_TRACE_ERROR
0x180084f26  mov     rcx, cs:g_hPublisher
0x180084f2d  call    fnEfsLogTrace1
0x180084f32  mov     rcx, [rbp+StringSid]; hMem
0x180084f36  test    rcx, rcx
0x180084f39  jz      short loc_180084F49
0x180084f3b  call    cs:__imp_LocalFree
0x180084f41  mov     [rbp+StringSid], 0
0x180084f49  mov     rcx, [rbp+TokenHandle]; hObject
0x180084f4d  test    rcx, rcx
0x180084f50  jz      short loc_180084F60
0x180084f52  call    cs:__imp_CloseHandle
0x180084f58  mov     [rbp+TokenHandle], 0
0x180084f60  test    rbx, rbx
0x180084f63  jz      short loc_180084F79
0x180084f65  call    cs:__imp_GetProcessHeap
0x180084f6b  mov     r8, rbx; lpMem
0x180084f6e  xor     edx, edx; dwFlags
0x180084f70  mov     rcx, rax; hHeap
0x180084f73  call    cs:__imp_HeapFree
0x180084f79  mov     rbx, [rsp+50h+arg_0]
0x180084f7e  mov     eax, edi
0x180084f80  add     rsp, 50h
0x180084f84  pop     r15
0x180084f86  pop     rdi
0x180084f87  pop     rbp
0x180084f88  retn
```
