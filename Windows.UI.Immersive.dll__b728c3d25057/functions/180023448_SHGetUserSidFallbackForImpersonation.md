# SHGetUserSidFallbackForImpersonation

- ea: `0x180023448`
- end: `0x18002364d`
- name: `SHGetUserSidFallbackForImpersonation`
- size: `517`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800227b4`
- `0x180022890`

## callees

- `0x180006538`
- `0x180023448`
- `0x180030ea4`
- `0x18003aa84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023591`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023488`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800234b7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023488`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800234b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800234a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800234a4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800234df`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800234df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800234d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800234d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800235c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800235c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023551`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800235ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023634`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023551`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800235ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023634`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023509`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023509`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800235d5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800235d5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002360a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002360a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023537`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023587`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023537`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023587`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002362b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002362b`

## pseudocode

```c
__int64 __fastcall SHGetUserSidFallbackForImpersonation(__int64 a1, _QWORD *a2)
{
  HANDLE CurrentThread; // rax
  int Error; // eax
  signed int v5; // ebx
  HANDLE v6; // rax
  HANDLE CurrentProcess; // rax
  void *v8; // r14
  PSID *v9; // rsi
  void *v10; // rdi
  signed int LastError; // eax
  void *v12; // rcx
  int v13; // eax
  DWORD LengthSid; // eax
  DWORD v15; // r14d
  void *v16; // rcx
  void *v17; // rdi
  __int64 TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF
  LPVOID TokenInformation; // [rsp+70h] [rbp+40h] BYREF

  TokenInformationLength = a1;
  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    Error = ResultFromKnownLastError();
    v5 = Error;
    if ( Error < 0 )
    {
      if ( Error == -2147024891 )
      {
        v6 = GetCurrentThread();
        if ( OpenThreadToken(v6, 8u, 1, &TokenHandle) )
          goto LABEL_10;
        v5 = ResultFromKnownLastError();
      }
      if ( v5 == -2147023888 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
          goto LABEL_10;
        v5 = ResultFromKnownLastError();
      }
      if ( v5 < 0 )
        return (unsigned int)v5;
    }
  }
LABEL_10:
  v8 = TokenHandle;
  v9 = 0;
  LODWORD(TokenInformationLength) = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v10 = TokenInformation;
  if ( TokenInformation )
  {
    v5 = 0;
    if ( !GetTokenInformation(v8, TokenUser, TokenInformation, TokenInformationLength, (PDWORD)&TokenInformationLength) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError == 122 )
      {
        LocalFree(v10);
        v13 = CTLocalAllocPolicy::Alloc(v12, 0x40u, (unsigned int)TokenInformationLength, &TokenInformation);
        v10 = TokenInformation;
        v5 = v13;
        if ( v13 < 0 )
        {
LABEL_19:
          LocalFree(v10);
          goto LABEL_22;
        }
        if ( GetTokenInformation(
               v8,
               TokenUser,
               TokenInformation,
               TokenInformationLength,
               (PDWORD)&TokenInformationLength) )
        {
          goto LABEL_20;
        }
        LastError = GetLastError();
        v5 = LastError;
      }
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 < 0 )
        goto LABEL_19;
    }
LABEL_20:
    v9 = (PSID *)v10;
    goto LABEL_22;
  }
  v5 = -2147024882;
LABEL_22:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v5 >= 0 )
  {
    LengthSid = GetLengthSid(*v9);
    TokenInformation = 0;
    v15 = LengthSid;
    v5 = CTCoAllocPolicy::Alloc(v16, 1u, LengthSid, &TokenInformation);
    if ( v5 < 0 )
    {
LABEL_31:
      LocalFree(v9);
      return (unsigned int)v5;
    }
    v17 = TokenInformation;
    if ( CopySid(v15, TokenInformation, *v9) )
    {
      v5 = 0;
    }
    else
    {
      v5 = ResultFromKnownLastError();
      if ( v5 < 0 )
      {
LABEL_30:
        CoTaskMemFree(v17);
        goto LABEL_31;
      }
    }
    *a2 = v17;
    v17 = 0;
    goto LABEL_30;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180023448  mov     [rsp-28h+arg_18], rbx
0x18002344d  mov     [rsp-28h+TokenInformationLength], rcx
0x180023452  push    rbp
0x180023453  push    rsi
0x180023454  push    rdi
0x180023455  push    r14
0x180023457  push    r15
0x180023459  mov     rbp, rsp
0x18002345c  sub     rsp, 30h
0x180023460  mov     r15, rdx
0x180023463  mov     qword ptr [rdx], 0
0x18002346a  mov     [rbp+TokenHandle], 0
0x180023472  call    cs:__imp_GetCurrentThread
0x180023478  xor     r8d, r8d; OpenAsSelf
0x18002347b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002347f  mov     rcx, rax; ThreadHandle
0x180023482  lea     edi, [r8+8]
0x180023486  mov     edx, edi; DesiredAccess
0x180023488  call    cs:__imp_OpenThreadToken
0x18002348e  test    eax, eax
0x180023490  jnz     short loc_1800234F8
0x180023492  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180023497  mov     ebx, eax
0x180023499  test    eax, eax
0x18002349b  jns     short loc_1800234F8
0x18002349d  cmp     eax, 80070005h
0x1800234a2  jnz     short loc_1800234C8
0x1800234a4  call    cs:__imp_GetCurrentThread
0x1800234aa  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800234ae  mov     edx, edi; DesiredAccess
0x1800234b0  mov     rcx, rax; ThreadHandle
0x1800234b3  lea     r8d, [rdi-7]; OpenAsSelf
0x1800234b7  call    cs:__imp_OpenThreadToken
0x1800234bd  test    eax, eax
0x1800234bf  jnz     short loc_1800234F8
0x1800234c1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800234c6  mov     ebx, eax
0x1800234c8  cmp     ebx, 800703F0h
0x1800234ce  jnz     short loc_1800234F0
0x1800234d0  call    cs:__imp_GetCurrentProcess
0x1800234d6  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800234da  mov     edx, edi; DesiredAccess
0x1800234dc  mov     rcx, rax; ProcessHandle
0x1800234df  call    cs:__imp_OpenProcessToken
0x1800234e5  test    eax, eax
0x1800234e7  jnz     short loc_1800234F8
0x1800234e9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800234ee  mov     ebx, eax
0x1800234f0  test    ebx, ebx
0x1800234f2  js      loc_18002363A
0x1800234f8  mov     r14, [rbp+TokenHandle]
0x1800234fc  mov     edx, 800h; uBytes
0x180023501  xor     esi, esi
0x180023503  mov     dword ptr [rbp+TokenInformationLength], edx
0x180023506  lea     ecx, [rsi+40h]; uFlags
0x180023509  call    cs:__imp_LocalAlloc
0x18002350f  mov     [rbp+TokenInformation], rax
0x180023513  mov     rdi, rax
0x180023516  test    rax, rax
0x180023519  jz      loc_1800235BA
0x18002351f  mov     r9d, dword ptr [rbp+TokenInformationLength]; TokenInformationLength
0x180023523  lea     rax, [rbp+TokenInformationLength]
0x180023527  mov     r8, rdi; TokenInformation
0x18002352a  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002352f  lea     edx, [rsi+1]; TokenInformationClass
0x180023532  mov     rcx, r14; TokenHandle
0x180023535  xor     ebx, ebx
0x180023537  call    cs:__imp_GetTokenInformation
0x18002353d  test    eax, eax
0x18002353f  jnz     short loc_1800235B5
0x180023541  call    cs:__imp_GetLastError
0x180023547  mov     ebx, eax
0x180023549  cmp     eax, 7Ah ; 'z'
0x18002354c  jnz     short loc_180023599
0x18002354e  mov     rcx, rdi; hMem
0x180023551  call    cs:__imp_LocalFree
0x180023557  mov     r8d, dword ptr [rbp+TokenInformationLength]; unsigned __int64
0x18002355b  lea     r9, [rbp+TokenInformation]; void **
0x18002355f  lea     edx, [rsi+40h]; unsigned int
0x180023562  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180023567  mov     rdi, [rbp+TokenInformation]
0x18002356b  mov     ebx, eax
0x18002356d  test    eax, eax
0x18002356f  js      short loc_1800235AA
0x180023571  mov     r9d, dword ptr [rbp+TokenInformationLength]; TokenInformationLength
0x180023575  lea     rax, [rbp+TokenInformationLength]
0x180023579  mov     r8, rdi; TokenInformation
0x18002357c  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180023581  lea     edx, [rsi+1]; TokenInformationClass
0x180023584  mov     rcx, r14; TokenHandle
0x180023587  call    cs:__imp_GetTokenInformation
0x18002358d  test    eax, eax
0x18002358f  jnz     short loc_1800235B5
0x180023591  call    cs:__imp_GetLastError
0x180023597  mov     ebx, eax
0x180023599  test    eax, eax
0x18002359b  jle     short loc_1800235A6
0x18002359d  movzx   ebx, ax
0x1800235a0  or      ebx, 80070000h
0x1800235a6  test    ebx, ebx
0x1800235a8  jns     short loc_1800235B5
0x1800235aa  mov     rcx, rdi; hMem
0x1800235ad  call    cs:__imp_LocalFree
0x1800235b3  jmp     short loc_1800235BF
0x1800235b5  mov     rsi, rdi
0x1800235b8  jmp     short loc_1800235BF
0x1800235ba  mov     ebx, 8007000Eh
0x1800235bf  mov     rcx, [rbp+TokenHandle]; hObject
0x1800235c3  test    rcx, rcx
0x1800235c6  jz      short loc_1800235CE
0x1800235c8  call    cs:__imp_CloseHandle
0x1800235ce  test    ebx, ebx
0x1800235d0  js      short loc_18002363A
0x1800235d2  mov     rcx, [rsi]; pSid
0x1800235d5  call    cs:__imp_GetLengthSid
0x1800235db  lea     r9, [rbp+TokenInformation]; void **
0x1800235df  mov     [rbp+TokenInformation], 0
0x1800235e7  mov     r8d, eax; unsigned __int64
0x1800235ea  mov     edx, 1; unsigned int
0x1800235ef  mov     r14d, eax
0x1800235f2  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800235f7  mov     ebx, eax
0x1800235f9  test    eax, eax
0x1800235fb  js      short loc_180023631
0x1800235fd  mov     rdi, [rbp+TokenInformation]
0x180023601  mov     ecx, r14d; nDestinationSidLength
0x180023604  mov     r8, [rsi]; pSourceSid
0x180023607  mov     rdx, rdi; pDestinationSid
0x18002360a  call    cs:__imp_CopySid
0x180023610  test    eax, eax
0x180023612  jz      short loc_180023618
0x180023614  xor     ebx, ebx
0x180023616  jmp     short loc_180023623
0x180023618  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002361d  mov     ebx, eax
0x18002361f  test    eax, eax
0x180023621  js      short loc_180023628
0x180023623  mov     [r15], rdi
0x180023626  xor     edi, edi
0x180023628  mov     rcx, rdi; pv
0x18002362b  call    cs:__imp_CoTaskMemFree
0x180023631  mov     rcx, rsi; hMem
0x180023634  call    cs:__imp_LocalFree
0x18002363a  mov     eax, ebx
0x18002363c  mov     rbx, [rsp+30h+arg_18]
0x180023641  add     rsp, 30h
0x180023645  pop     r15
0x180023647  pop     r14
0x180023649  pop     rdi
0x18002364a  pop     rsi
0x18002364b  pop     rbp
0x18002364c  retn
```
