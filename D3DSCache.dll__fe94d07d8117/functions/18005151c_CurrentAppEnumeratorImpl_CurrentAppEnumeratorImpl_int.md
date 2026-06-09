# CurrentAppEnumeratorImpl::CurrentAppEnumeratorImpl(int)

- ea: `0x18005151c`
- end: `0x1800515fe`
- name: `??0CurrentAppEnumeratorImpl@@QEAA@H@Z`
- size: `226`
- prototype: `CurrentAppEnumeratorImpl *__fastcall(CurrentAppEnumeratorImpl *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d70`

## callees

- `0x180003210`
- `0x180003350`
- `0x1800449f0`
- `0x18005151c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180051561`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180051561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005154e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005154e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005158e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005158e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800515be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800515be`

## pseudocode

```c
CurrentAppEnumeratorImpl *__fastcall CurrentAppEnumeratorImpl::CurrentAppEnumeratorImpl(
        CurrentAppEnumeratorImpl *this,
        int a2)
{
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-78h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-70h] BYREF
  PSID TokenInformation[10]; // [rsp+40h] [rbp-68h] BYREF

  *(_BYTE *)this = 0;
  if ( a2 )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      ReturnLength = 76;
      if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, TokenInformation, 0x4Cu, &ReturnLength) )
        *(_BYTE *)this = (int)GetFilenameInAppContainerStorage(
                                (unsigned __int16 *)this + 1,
                                0x104u,
                                TokenInformation[0],
                                &qword_1800ACF70) >= 0;
      CloseHandle(TokenHandle);
    }
  }
  else
  {
    *(_BYTE *)this = (int)GetFilenameInAppDataStorageForCurrentApp(
                            (unsigned __int16 *)this + 1,
                            0x104u,
                            &qword_1800ACF70) >= 0;
  }
  return this;
}

```

## disassembly

```asm
0x18005151c  push    rbx
0x18005151e  sub     rsp, 0A0h
0x180051525  mov     rax, cs:__security_cookie
0x18005152c  xor     rax, rsp
0x18005152f  mov     [rsp+0A8h+var_18], rax
0x180051537  mov     byte ptr [rcx], 0
0x18005153a  mov     rbx, rcx
0x18005153d  test    edx, edx
0x18005153f  jz      loc_1800515C6
0x180051545  mov     [rsp+0A8h+TokenHandle], 0
0x18005154e  call    cs:__imp_GetCurrentProcess
0x180051554  lea     r8, [rsp+0A8h+TokenHandle]; TokenHandle
0x180051559  mov     edx, 8; DesiredAccess
0x18005155e  mov     rcx, rax; ProcessHandle
0x180051561  call    cs:__imp_OpenProcessToken
0x180051567  test    eax, eax
0x180051569  jz      short loc_1800515E2
0x18005156b  mov     rcx, [rsp+0A8h+TokenHandle]; TokenHandle
0x180051570  lea     rax, [rsp+0A8h+var_70]
0x180051575  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x18005157b  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x180051580  lea     r8, [rsp+0A8h+TokenInformation]; TokenInformation
0x180051585  mov     [rsp+0A8h+var_70], r9d
0x18005158a  lea     edx, [r9-2Dh]; TokenInformationClass
0x18005158e  call    cs:__imp_GetTokenInformation
0x180051594  test    eax, eax
0x180051596  jz      short loc_1800515B9
0x180051598  mov     r8, [rsp+0A8h+TokenInformation]; Sid
0x18005159d  lea     rcx, [rbx+2]; unsigned __int16 *
0x1800515a1  lea     r9, qword_1800ACF70; unsigned __int16 *
0x1800515a8  mov     edx, 104h; unsigned int
0x1800515ad  call    ?GetFilenameInAppContainerStorage@@YAJPEAGIPEAXPEBGZZ
0x1800515b2  shr     eax, 1Fh
0x1800515b5  xor     al, 1
0x1800515b7  mov     [rbx], al
0x1800515b9  mov     rcx, [rsp+0A8h+TokenHandle]; hObject
0x1800515be  call    cs:__imp_CloseHandle
0x1800515c4  jmp     short loc_1800515E2
0x1800515c6  add     rcx, 2; unsigned __int16 *
0x1800515ca  lea     r8, qword_1800ACF70; unsigned __int16 *
0x1800515d1  mov     edx, 104h; unsigned int
0x1800515d6  call    ?GetFilenameInAppDataStorageForCurrentApp@@YAJPEAGIPEBGZZ
0x1800515db  shr     eax, 1Fh
0x1800515de  xor     al, 1
0x1800515e0  mov     [rbx], al
0x1800515e2  mov     rax, rbx
0x1800515e5  mov     rcx, [rsp+0A8h+var_18]
0x1800515ed  xor     rcx, rsp; StackCookie
0x1800515f0  call    __security_check_cookie
0x1800515f5  add     rsp, 0A0h
0x1800515fc  pop     rbx
0x1800515fd  retn
```
