# Token::Duplicate(_TOKEN_TYPE,_SECURITY_IMPERSONATION_LEVEL,Optional<IntegrityLevel>)

- ea: `0x180027bd4`
- end: `0x180027e68`
- name: `?Duplicate@Token@@QEBA?AV1@W4_TOKEN_TYPE@@W4_SECURITY_IMPERSONATION_LEVEL@@V?$Optional@W4IntegrityLevel@@@@@Z`
- size: `660`
- prototype: `_QWORD *__fastcall(HANDLE *, _QWORD *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006960`
- `0x180028044`

## callees

- `0x1800032a0`
- `0x180003d20`
- `0x180005f9c`
- `0x18000b29c`
- `0x1800195c4`
- `0x180027b00`
- `0x180027b3c`
- `0x180027bd4`
- `0x18002840c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027de3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027de3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027d46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027d46`
- `ADVAPI32!DuplicateTokenEx` at `0x180027c58`
- `ADVAPI32!DuplicateTokenEx` at `0x180027c58`
- `ADVAPI32!SetTokenInformation` at `0x180027d11`
- `ADVAPI32!SetTokenInformation` at `0x180027d11`
- `ADVAPI32!GetSidLengthRequired` at `0x180027cf8`
- `ADVAPI32!GetSidLengthRequired` at `0x180027cf8`

## pseudocode

```c
_QWORD *__fastcall Token::Duplicate(HANDLE *a1, _QWORD *a2, __int64 a3, __int64 a4, __int64 a5)
{
  BOOL v7; // ebx
  _BYTE *v8; // rdx
  __int64 v9; // rcx
  unsigned int *v10; // rdx
  DWORD SidLengthRequired; // eax
  signed int v13; // eax
  unsigned int v14; // ebx
  signed int LastError; // eax
  unsigned int v16; // ebx
  HANDLE TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD TokenInformation[3]; // [rsp+38h] [rbp-C8h] BYREF
  _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+90h] [rbp-70h]
  void *phNewToken; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v23[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE *v24; // [rsp+E0h] [rbp-20h]
  _BYTE v25[72]; // [rsp+F0h] [rbp-10h] BYREF
  char *v26; // [rsp+138h] [rbp+38h] BYREF

  TokenInformation[0] = a2;
  v21 = a5;
  TokenHandle = 0;
  *(_QWORD *)&TokenAttributes.nLength = 24;
  *(_OWORD *)&TokenAttributes.lpSecurityDescriptor = 0;
  stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(&phNewToken, &TokenHandle);
  v7 = DuplicateTokenEx(*a1, 0x2000000u, &TokenAttributes, SecurityIdentification, TokenImpersonation, &phNewToken);
  if ( v24 )
  {
    TokenInformation[0] = phNewToken;
    (*(void (__fastcall **)(_BYTE *, _QWORD *))(*(_QWORD *)v24 + 16LL))(v24, TokenInformation);
    if ( v24 )
    {
      v8 = v23;
      LOBYTE(v8) = v24 != v23;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v24 + 32LL))(v24, v8);
    }
  }
  if ( !v7 )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v16);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v16);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v9 = a5 + 8;
  if ( a5 == -1 )
    v9 = 8;
  if ( *(_QWORD *)v9 )
  {
    v10 = *(unsigned int **)(a5 + 8);
    if ( !v10 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
      throw (ErrorCodeException *)pExceptionObject;
    }
    Sid::FromIntegrityLevel(v25, *v10);
    TokenInformation[1] = 32;
    TokenInformation[0] = v25;
    SidLengthRequired = GetSidLengthRequired(1u);
    if ( !SetTokenInformation(TokenHandle, TokenIntegrityLevel, TokenInformation, SidLengthRequired + 16) )
    {
      v13 = GetLastError();
      v14 = v13;
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v14);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v14);
      throw (ErrorCodeException *)pExceptionObject;
    }
    std::wstring::~wstring(&v26);
  }
  Token::Token(a2, (__int64 *)&TokenHandle);
  if ( TokenHandle && (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  if ( *(_QWORD *)(a5 + 8) )
    *(_QWORD *)(a5 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x180027bd4  mov     [rsp-8+arg_10], rbx
0x180027bd9  push    rbp
0x180027bda  push    rsi
0x180027bdb  push    rdi
0x180027bdc  lea     rbp, [rsp-70h]
0x180027be1  sub     rsp, 170h
0x180027be8  mov     rax, cs:__security_cookie
0x180027bef  xor     rax, rsp
0x180027bf2  mov     [rbp+80h+var_20], rax
0x180027bf6  mov     rsi, rdx
0x180027bf9  mov     rbx, rcx
0x180027bfc  mov     [rsp+180h+TokenInformation], rdx
0x180027c01  mov     rdi, [rbp+80h+arg_20]
0x180027c08  mov     [rbp+80h+var_F0], rdi
0x180027c0c  mov     [rsp+180h+TokenHandle], 0
0x180027c15  mov     qword ptr [rsp+180h+TokenAttributes.nLength], 18h
0x180027c1e  xorps   xmm0, xmm0
0x180027c21  movups  xmmword ptr [rsp+180h+TokenAttributes.lpSecurityDescriptor], xmm0
0x180027c26  lea     rdx, [rsp+180h+TokenHandle]
0x180027c2b  lea     rcx, [rbp+80h+var_E0]
0x180027c2f  call    ??$get_pointer@V?$unique_ptr@XUHandleClose@Private@@@std@@@stdext@@YA?AV?$GetPointer@PEAX@0@AEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(std::unique_ptr<void,Private::HandleClose> &)
0x180027c34  lea     rax, [rbp+80h+var_E0]
0x180027c38  mov     [rsp+180h+phNewToken], rax; phNewToken
0x180027c3d  mov     [rsp+180h+TokenType], 2; TokenType
0x180027c45  mov     r9d, 1; ImpersonationLevel
0x180027c4b  lea     r8, [rsp+180h+TokenAttributes]; lpTokenAttributes
0x180027c50  mov     edx, 2000000h; dwDesiredAccess
0x180027c55  mov     rcx, [rbx]; hExistingToken
0x180027c58  call    cs:__imp_DuplicateTokenEx
0x180027c5e  mov     ebx, eax
0x180027c60  mov     rcx, [rbp+80h+var_A0]
0x180027c64  test    rcx, rcx
0x180027c67  jz      short loc_180027CA3
0x180027c69  mov     rax, [rbp+80h+var_E0]
0x180027c6d  mov     [rsp+180h+TokenInformation], rax
0x180027c72  mov     rax, [rcx]
0x180027c75  lea     rdx, [rsp+180h+TokenInformation]
0x180027c7a  mov     rax, [rax+10h]
0x180027c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c83  mov     rcx, [rbp+80h+var_A0]
0x180027c87  test    rcx, rcx
0x180027c8a  jz      short loc_180027CA3
0x180027c8c  mov     rax, [rcx]
0x180027c8f  lea     rdx, [rbp+80h+var_D8]
0x180027c93  cmp     rcx, rdx
0x180027c96  setnz   dl
0x180027c99  mov     rax, [rax+20h]
0x180027c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ca2  nop
0x180027ca3  test    ebx, ebx
0x180027ca5  jz      loc_180027DE3
0x180027cab  lea     rax, [rdi+1]
0x180027caf  lea     rcx, [rax+7]
0x180027cb3  mov     edx, 8
0x180027cb8  test    rax, rax
0x180027cbb  cmovz   rcx, rdx
0x180027cbf  cmp     qword ptr [rcx], 0
0x180027cc3  jz      short loc_180027D24
0x180027cc5  mov     rdx, [rdi+8]
0x180027cc9  test    rdx, rdx
0x180027ccc  jz      loc_180027E47
0x180027cd2  mov     edx, [rdx]
0x180027cd4  lea     rcx, [rbp+80h+var_90]
0x180027cd8  call    ?FromIntegrityLevel@Sid@@SA?AV1@W4IntegrityLevel@@@Z; Sid::FromIntegrityLevel(IntegrityLevel)
0x180027cdd  nop
0x180027cde  xor     eax, eax
0x180027ce0  mov     [rsp+180h+var_140], rax
0x180027ce5  mov     dword ptr [rsp+180h+var_140], 20h ; ' '
0x180027ced  lea     rax, [rbp+80h+var_90]
0x180027cf1  mov     [rsp+180h+TokenInformation], rax
0x180027cf6  mov     cl, 1; nSubAuthorityCount
0x180027cf8  call    cs:__imp_GetSidLengthRequired
0x180027cfe  lea     r9d, [rax+10h]; TokenInformationLength
0x180027d02  lea     r8, [rsp+180h+TokenInformation]; TokenInformation
0x180027d07  mov     edx, 19h; TokenInformationClass
0x180027d0c  mov     rcx, [rsp+180h+TokenHandle]; TokenHandle
0x180027d11  call    cs:__imp_SetTokenInformation
0x180027d17  test    eax, eax
0x180027d19  jz      short loc_180027D7E
0x180027d1b  lea     rcx, [rbp+80h+var_48]
0x180027d1f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027d24  lea     rdx, [rsp+180h+TokenHandle]
0x180027d29  mov     rcx, rsi
0x180027d2c  call    ??0Token@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Token::Token(std::unique_ptr<void,Private::HandleClose> &&)
0x180027d31  nop
0x180027d32  mov     rcx, [rsp+180h+TokenHandle]; hObject
0x180027d37  test    rcx, rcx
0x180027d3a  jz      short loc_180027D4D
0x180027d3c  lea     rax, [rcx-1]
0x180027d40  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180027d44  ja      short loc_180027D4D
0x180027d46  call    cs:__imp_CloseHandle
0x180027d4c  nop
0x180027d4d  cmp     qword ptr [rdi+8], 0
0x180027d52  jz      short loc_180027D5C
0x180027d54  mov     qword ptr [rdi+8], 0
0x180027d5c  mov     rax, rsi
0x180027d5f  mov     rcx, [rbp+80h+var_20]
0x180027d63  xor     rcx, rsp; StackCookie
0x180027d66  call    __security_check_cookie
0x180027d6b  mov     rbx, [rsp+180h+arg_10]
0x180027d73  add     rsp, 170h
0x180027d7a  pop     rdi
0x180027d7b  pop     rsi
0x180027d7c  pop     rbp
0x180027d7d  retn
0x180027d7e  call    cs:__imp_GetLastError
0x180027d84  nop
0x180027d85  mov     ebx, eax
0x180027d87  test    eax, eax
0x180027d89  jle     short loc_180027D94
0x180027d8b  movzx   ebx, ax
0x180027d8e  or      ebx, 80070000h
0x180027d94  lea     rax, WPP_GLOBAL_Control
0x180027d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027da2  cmp     rcx, rax
0x180027da5  jz      short loc_180027DC5
0x180027da7  test    byte ptr [rcx+1Ch], 1
0x180027dab  jz      short loc_180027DC5
0x180027dad  mov     edx, 15h
0x180027db2  mov     r9d, ebx
0x180027db5  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x180027dbc  mov     rcx, [rcx+10h]
0x180027dc0  call    WPP_SF_d
0x180027dc5  mov     edx, ebx; int
0x180027dc7  lea     rcx, [rsp+180h+pExceptionObject]; this
0x180027dcc  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180027dd1  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180027dd8  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x180027ddd  call    _CxxThrowException_0
0x180027de3  call    cs:__imp_GetLastError
0x180027de9  mov     ebx, eax
0x180027deb  test    eax, eax
0x180027ded  jle     short loc_180027DF8
0x180027def  movzx   ebx, ax
0x180027df2  or      ebx, 80070000h
0x180027df8  lea     rax, WPP_GLOBAL_Control
0x180027dff  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e06  cmp     rcx, rax
0x180027e09  jz      short loc_180027E29
0x180027e0b  test    byte ptr [rcx+1Ch], 1
0x180027e0f  jz      short loc_180027E29
0x180027e11  mov     edx, 14h
0x180027e16  mov     r9d, ebx
0x180027e19  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x180027e20  mov     rcx, [rcx+10h]
0x180027e24  call    WPP_SF_d
0x180027e29  mov     edx, ebx; int
0x180027e2b  lea     rcx, [rsp+180h+pExceptionObject]; this
0x180027e30  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180027e35  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180027e3c  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x180027e41  call    _CxxThrowException_0
0x180027e47  mov     edx, 80004003h; int
0x180027e4c  lea     rcx, [rsp+180h+pExceptionObject]; this
0x180027e51  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180027e56  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180027e5d  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x180027e62  call    _CxxThrowException_0
```
