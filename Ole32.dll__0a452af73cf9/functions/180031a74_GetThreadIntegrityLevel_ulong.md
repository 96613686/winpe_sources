# GetThreadIntegrityLevel(ulong *)

- ea: `0x180031a74`
- end: `0x180031bb6`
- name: `?GetThreadIntegrityLevel@@YAJPEAK@Z`
- size: `322`
- prototype: `HRESULT __fastcall(unsigned int *pdwIntegrityLevel)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010afc`
- `0x18009000c`

## callees

- `0x180019454`
- `0x180031a74`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180031af3`
- `KERNELBASE!LocalAlloc` at `0x180031af3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b8d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031aa9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031aa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031a92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031a92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031b58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031b58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b4d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180031b3e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180031b3e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180031b2e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180031b2e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031ad0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031b21`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031ad0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031b21`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180031bae`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180031bae`

## pseudocode

```c
__int64 __fastcall GetThreadIntegrityLevel(unsigned int *pdwIntegrityLevel)
{
  HANDLE CurrentThread; // rax
  PSID *v3; // rdi
  PUCHAR SidSubAuthorityCount; // rax
  HRESULT LastError; // ebx
  bool v6; // sf
  unsigned int dwLengthNeeded; // [rsp+48h] [rbp+10h] BYREF
  void *hToken; // [rsp+50h] [rbp+18h] BYREF

  hToken = 0;
  dwLengthNeeded = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x18u, 1, &hToken) )
  {
    if ( GetTokenInformation(hToken, TokenIntegrityLevel, 0, 0, &dwLengthNeeded) || GetLastError() != 122 )
    {
      LastError = GetLastError();
    }
    else
    {
      v3 = (PSID *)LocalAlloc(0, dwLengthNeeded);
      if ( v3 )
      {
        if ( GetTokenInformation(hToken, TokenIntegrityLevel, v3, dwLengthNeeded, &dwLengthNeeded) )
        {
          SidSubAuthorityCount = GetSidSubAuthorityCount(*v3);
          *pdwIntegrityLevel = *GetSidSubAuthority(*v3, (unsigned __int8)(*SidSubAuthorityCount - 1));
          LastError = 0;
        }
        else
        {
          LastError = GetLastError();
        }
        LocalFree(v3);
      }
      else
      {
        LastError = 14;
      }
    }
    CloseHandle(hToken);
    v6 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v6 = LastError < 0;
    }
    if ( v6 )
      OleInternalOriginateError(LastError, 0x13Au);
  }
  else
  {
    LastError = -2147418113;
    RoOriginateError(2147549183LL, 0);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180031a74  mov     [rsp+arg_0], rbx
0x180031a79  push    rdi
0x180031a7a  sub     rsp, 30h
0x180031a7e  mov     rbx, pdwIntegrityLevel
0x180031a81  mov     [rsp+38h+hToken], 0
0x180031a8a  mov     [rsp+38h+dwLengthNeeded], 0
0x180031a92  call    cs:__imp_GetCurrentThread
0x180031a98  mov     edx, 18h; DesiredAccess
0x180031a9d  lea     r9, [rsp+38h+hToken]; TokenHandle
0x180031aa2  mov     pdwIntegrityLevel, rax; ThreadHandle
0x180031aa5  lea     r8d, [rdx-17h]; OpenAsSelf
0x180031aa9  call    cs:__imp_OpenThreadToken
0x180031aaf  test    eax, eax
0x180031ab1  jz      loc_180031BA5
0x180031ab7  mov     pdwIntegrityLevel, [rsp+38h+hToken]; TokenHandle
0x180031abc  lea     rax, [rsp+38h+dwLengthNeeded]
0x180031ac1  xor     r9d, r9d; TokenInformationLength
0x180031ac4  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180031ac9  xor     r8d, r8d; TokenInformation
0x180031acc  lea     edx, [r9+19h]; TokenInformationClass
0x180031ad0  call    cs:__imp_GetTokenInformation
0x180031ad6  test    eax, eax
0x180031ad8  jnz     loc_180031B8D
0x180031ade  call    cs:__imp_GetLastError
0x180031ae4  cmp     eax, 7Ah ; 'z'
0x180031ae7  jnz     loc_180031B8D
0x180031aed  mov     edx, [rsp+38h+dwLengthNeeded]; uBytes
0x180031af1  xor     ecx, ecx; uFlags
0x180031af3  call    cs:__imp_LocalAlloc
0x180031af9  mov     rdi, rax
0x180031afc  test    rax, rax
0x180031aff  jz      loc_180031B86
0x180031b05  mov     r9d, [rsp+38h+dwLengthNeeded]; TokenInformationLength
0x180031b0a  lea     rax, [rsp+38h+dwLengthNeeded]
0x180031b0f  mov     pdwIntegrityLevel, [rsp+38h+hToken]; TokenHandle
0x180031b14  mov     r8, rdi; TokenInformation
0x180031b17  mov     edx, 19h; TokenInformationClass
0x180031b1c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180031b21  call    cs:__imp_GetTokenInformation
0x180031b27  test    eax, eax
0x180031b29  jz      short loc_180031B7C
0x180031b2b  mov     pdwIntegrityLevel, [rdi]; pSid
0x180031b2e  call    cs:__imp_GetSidSubAuthorityCount
0x180031b34  mov     cl, [rax]
0x180031b36  dec     cl
0x180031b38  movzx   edx, cl; nSubAuthority
0x180031b3b  mov     pdwIntegrityLevel, [rdi]; pSid
0x180031b3e  call    cs:__imp_GetSidSubAuthority
0x180031b44  mov     ecx, [rax]
0x180031b46  mov     [rbx], ecx
0x180031b48  xor     ebx, ebx
0x180031b4a  mov     pdwIntegrityLevel, rdi; hMem
0x180031b4d  call    cs:__imp_LocalFree
0x180031b53  mov     pdwIntegrityLevel, [rsp+38h+hToken]; hObject
0x180031b58  call    cs:__imp_CloseHandle
0x180031b5e  test    ebx, ebx
0x180031b60  jle     short loc_180031B6D
0x180031b62  movzx   ebx, bx
0x180031b65  or      ebx, 80070000h
0x180031b6b  test    ebx, ebx
0x180031b6d  js      short loc_180031B97
0x180031b6f  mov     eax, ebx
0x180031b71  mov     rbx, [rsp+38h+arg_0]
0x180031b76  add     rsp, 30h
0x180031b7a  pop     rdi
0x180031b7b  retn
0x180031b7c  call    cs:__imp_GetLastError
0x180031b82  mov     ebx, eax
0x180031b84  jmp     short loc_180031B4A
0x180031b86  mov     ebx, 0Eh
0x180031b8b  jmp     short loc_180031B53
0x180031b8d  call    cs:__imp_GetLastError
0x180031b93  mov     ebx, eax
0x180031b95  jmp     short loc_180031B53
0x180031b97  mov     edx, 13Ah; messageID
0x180031b9c  mov     ecx, ebx; hr
0x180031b9e  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x180031ba3  jmp     short loc_180031B6F
0x180031ba5  mov     ebx, 8000FFFFh
0x180031baa  xor     edx, edx
0x180031bac  mov     ecx, ebx
0x180031bae  call    cs:__imp_RoOriginateError
0x180031bb4  jmp     short loc_180031B6F
```
