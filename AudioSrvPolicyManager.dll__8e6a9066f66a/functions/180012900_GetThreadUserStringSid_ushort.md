# GetThreadUserStringSid(ushort * *)

- ea: `0x180012900`
- end: `0x180012a49`
- name: `?GetThreadUserStringSid@@YAJPEAPEAG@Z`
- size: `329`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012e64`

## callees

- `0x180012900`
- `0x18003a5fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129b9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012936`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012936`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012923`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012923`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012970`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012970`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129db`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012956`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001299e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012956`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001299e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800129af`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800129af`

## pseudocode

```c
__int64 __fastcall GetThreadUserStringSid(unsigned __int16 **a1)
{
  PSID *v1; // rdi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v5; // ebx
  int ReturnLength; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+38h] BYREF

  v1 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  StringSid = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError != 122 )
        goto LABEL_9;
      v1 = (PSID *)CoTaskMemAlloc(TokenInformationLength);
      if ( !v1 )
      {
        v5 = -2147024882;
LABEL_12:
        if ( StringSid )
        {
          LocalFree(StringSid);
          StringSid = 0;
        }
        goto LABEL_15;
      }
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v1, TokenInformationLength, &TokenInformationLength)
      && ConvertSidToStringSidW(*v1, &StringSid) )
    {
      v5 = 0;
      *a1 = StringSid;
      goto LABEL_15;
    }
  }
  LastError = GetLastError();
  v5 = LastError;
LABEL_9:
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_12;
LABEL_15:
  if ( v1 )
    CoTaskMemFree(v1);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)(unsigned int)v5,
      ReturnLength);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180012900  mov     [rsp-18h+arg_0], rbx
0x180012905  push    rbp
0x180012906  push    rsi
0x180012907  push    rdi
0x180012908  mov     rbp, rsp
0x18001290b  sub     rsp, 30h
0x18001290f  xor     edi, edi
0x180012911  mov     [rbp+TokenHandle], 0
0x180012919  mov     [rbp+TokenInformationLength], edi
0x18001291c  mov     rsi, rcx
0x18001291f  mov     [rbp+StringSid], rdi
0x180012923  call    cs:__imp_GetCurrentThread
0x180012929  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001292d  xor     r8d, r8d; OpenAsSelf
0x180012930  mov     rcx, rax; ThreadHandle
0x180012933  lea     edx, [rdi+8]; DesiredAccess
0x180012936  call    cs:__imp_OpenThreadToken
0x18001293c  test    eax, eax
0x18001293e  jz      short loc_1800129B9
0x180012940  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180012944  lea     rax, [rbp+TokenInformationLength]
0x180012948  xor     r9d, r9d; TokenInformationLength
0x18001294b  mov     qword ptr [rsp+30h+ReturnLength], rax; ReturnLength
0x180012950  xor     r8d, r8d; TokenInformation
0x180012953  lea     edx, [rdi+1]; TokenInformationClass
0x180012956  call    cs:__imp_GetTokenInformation
0x18001295c  test    eax, eax
0x18001295e  jnz     short loc_180012985
0x180012960  call    cs:__imp_GetLastError
0x180012966  mov     ebx, eax
0x180012968  cmp     eax, 7Ah ; 'z'
0x18001296b  jnz     short loc_1800129C1
0x18001296d  mov     ecx, [rbp+TokenInformationLength]; cb
0x180012970  call    cs:__imp_CoTaskMemAlloc
0x180012976  mov     rdi, rax
0x180012979  test    rax, rax
0x18001297c  jnz     short loc_180012985
0x18001297e  mov     ebx, 8007000Eh
0x180012983  jmp     short loc_1800129D2
0x180012985  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180012989  lea     rax, [rbp+TokenInformationLength]
0x18001298d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180012991  mov     r8, rdi; TokenInformation
0x180012994  mov     edx, 1; TokenInformationClass
0x180012999  mov     qword ptr [rsp+30h+ReturnLength], rax; int
0x18001299e  call    cs:__imp_GetTokenInformation
0x1800129a4  test    eax, eax
0x1800129a6  jz      short loc_1800129B9
0x1800129a8  mov     rcx, [rdi]; Sid
0x1800129ab  lea     rdx, [rbp+StringSid]; StringSid
0x1800129af  call    cs:__imp_ConvertSidToStringSidW
0x1800129b5  test    eax, eax
0x1800129b7  jnz     short loc_1800129EB
0x1800129b9  call    cs:__imp_GetLastError
0x1800129bf  mov     ebx, eax
0x1800129c1  test    eax, eax
0x1800129c3  jle     short loc_1800129CE
0x1800129c5  movzx   ebx, ax
0x1800129c8  or      ebx, 80070000h
0x1800129ce  test    ebx, ebx
0x1800129d0  jns     short loc_1800129F4
0x1800129d2  mov     rcx, [rbp+StringSid]; hMem
0x1800129d6  test    rcx, rcx
0x1800129d9  jz      short loc_1800129F4
0x1800129db  call    cs:__imp_LocalFree
0x1800129e1  mov     [rbp+StringSid], 0
0x1800129e9  jmp     short loc_1800129F4
0x1800129eb  mov     rax, [rbp+StringSid]
0x1800129ef  xor     ebx, ebx
0x1800129f1  mov     [rsi], rax
0x1800129f4  test    rdi, rdi
0x1800129f7  jz      short loc_180012A02
0x1800129f9  mov     rcx, rdi; pv
0x1800129fc  call    cs:__imp_CoTaskMemFree
0x180012a02  mov     rcx, [rbp+TokenHandle]; hObject
0x180012a06  lea     rax, [rcx-1]
0x180012a0a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012a0e  ja      short loc_180012A1E
0x180012a10  call    cs:__imp_CloseHandle
0x180012a16  mov     [rbp+TokenHandle], 0
0x180012a1e  test    ebx, ebx
0x180012a20  jns     short loc_180012A3A
0x180012a22  mov     rcx, [rbp+18h]; this
0x180012a26  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180012a2d  mov     r9d, ebx; char *
0x180012a30  mov     edx, 66h ; 'f'; void *
0x180012a35  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012a3a  mov     eax, ebx
0x180012a3c  mov     rbx, [rsp+30h+arg_0]
0x180012a41  add     rsp, 30h
0x180012a45  pop     rdi
0x180012a46  pop     rsi
0x180012a47  pop     rbp
0x180012a48  retn
```
