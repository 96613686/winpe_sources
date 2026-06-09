# Token::Duplicate(_TOKEN_TYPE,_SECURITY_IMPERSONATION_LEVEL,Optional<IntegrityLevel>)

- ea: `0x1800636e4`
- end: `0x180063978`
- name: `?Duplicate@Token@@QEBA?AV1@W4_TOKEN_TYPE@@W4_SECURITY_IMPERSONATION_LEVEL@@V?$Optional@W4IntegrityLevel@@@@@Z`
- size: `660`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002aae4`
- `0x180063980`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x180009a80`
- `0x18000ecc0`
- `0x180035e0c`
- `0x18006105c`
- `0x180062550`
- `0x180063658`
- `0x1800636e4`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006388e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800638f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006388e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800638f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063856`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063856`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180063821`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180063821`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180063768`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180063768`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180063808`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180063808`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x1800636e4  mov     [rsp-8+arg_10], rbx
0x1800636e9  push    rbp
0x1800636ea  push    rsi
0x1800636eb  push    rdi
0x1800636ec  lea     rbp, [rsp-70h]
0x1800636f1  sub     rsp, 170h
0x1800636f8  mov     rax, cs:__security_cookie
0x1800636ff  xor     rax, rsp
0x180063702  mov     [rbp+80h+var_20], rax
0x180063706  mov     rsi, rdx
0x180063709  mov     rbx, rcx
0x18006370c  mov     [rsp+180h+TokenInformation], rdx
0x180063711  mov     rdi, [rbp+80h+arg_20]
0x180063718  mov     [rbp+80h+var_F0], rdi
0x18006371c  mov     [rsp+180h+TokenHandle], 0
0x180063725  mov     qword ptr [rsp+180h+TokenAttributes.nLength], 18h
0x18006372e  xorps   xmm0, xmm0
0x180063731  movups  xmmword ptr [rsp+180h+TokenAttributes.lpSecurityDescriptor], xmm0
0x180063736  lea     rdx, [rsp+180h+TokenHandle]
0x18006373b  lea     rcx, [rbp+80h+var_E0]
0x18006373f  call    ??$get_pointer@V?$unique_ptr@XUHandleClose@Private@@@std@@@stdext@@YA?AV?$GetPointer@PEAX@0@AEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(std::unique_ptr<void,Private::HandleClose> &)
0x180063744  lea     rax, [rbp+80h+var_E0]
0x180063748  mov     [rsp+180h+phNewToken], rax; phNewToken
0x18006374d  mov     [rsp+180h+TokenType], 2; TokenType
0x180063755  mov     r9d, 1; ImpersonationLevel
0x18006375b  lea     r8, [rsp+180h+TokenAttributes]; lpTokenAttributes
0x180063760  mov     edx, 2000000h; dwDesiredAccess
0x180063765  mov     rcx, [rbx]; hExistingToken
0x180063768  call    cs:__imp_DuplicateTokenEx
0x18006376e  mov     ebx, eax
0x180063770  mov     rcx, [rbp+80h+var_A0]
0x180063774  test    rcx, rcx
0x180063777  jz      short loc_1800637B3
0x180063779  mov     rax, [rbp+80h+var_E0]
0x18006377d  mov     [rsp+180h+TokenInformation], rax
0x180063782  mov     rax, [rcx]
0x180063785  lea     rdx, [rsp+180h+TokenInformation]
0x18006378a  mov     rax, [rax+10h]
0x18006378e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063793  mov     rcx, [rbp+80h+var_A0]
0x180063797  test    rcx, rcx
0x18006379a  jz      short loc_1800637B3
0x18006379c  mov     rax, [rcx]
0x18006379f  lea     rdx, [rbp+80h+var_D8]
0x1800637a3  cmp     rcx, rdx
0x1800637a6  setnz   dl
0x1800637a9  mov     rax, [rax+20h]
0x1800637ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800637b2  nop
0x1800637b3  test    ebx, ebx
0x1800637b5  jz      loc_1800638F3
0x1800637bb  lea     rax, [rdi+1]
0x1800637bf  lea     rcx, [rax+7]
0x1800637c3  mov     edx, 8
0x1800637c8  test    rax, rax
0x1800637cb  cmovz   rcx, rdx
0x1800637cf  cmp     qword ptr [rcx], 0
0x1800637d3  jz      short loc_180063834
0x1800637d5  mov     rdx, [rdi+8]
0x1800637d9  test    rdx, rdx
0x1800637dc  jz      loc_180063957
0x1800637e2  mov     edx, [rdx]
0x1800637e4  lea     rcx, [rbp+80h+var_90]
0x1800637e8  call    ?FromIntegrityLevel@Sid@@SA?AV1@W4IntegrityLevel@@@Z; Sid::FromIntegrityLevel(IntegrityLevel)
0x1800637ed  nop
0x1800637ee  xor     eax, eax
0x1800637f0  mov     [rsp+180h+var_140], rax
0x1800637f5  mov     dword ptr [rsp+180h+var_140], 20h ; ' '
0x1800637fd  lea     rax, [rbp+80h+var_90]
0x180063801  mov     [rsp+180h+TokenInformation], rax
0x180063806  mov     cl, 1; nSubAuthorityCount
0x180063808  call    cs:__imp_GetSidLengthRequired
0x18006380e  lea     r9d, [rax+10h]; TokenInformationLength
0x180063812  lea     r8, [rsp+180h+TokenInformation]; TokenInformation
0x180063817  mov     edx, 19h; TokenInformationClass
0x18006381c  mov     rcx, [rsp+180h+TokenHandle]; TokenHandle
0x180063821  call    cs:__imp_SetTokenInformation
0x180063827  test    eax, eax
0x180063829  jz      short loc_18006388E
0x18006382b  lea     rcx, [rbp+80h+var_48]
0x18006382f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180063834  lea     rdx, [rsp+180h+TokenHandle]
0x180063839  mov     rcx, rsi
0x18006383c  call    ??0Token@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Token::Token(std::unique_ptr<void,Private::HandleClose> &&)
0x180063841  nop
0x180063842  mov     rcx, [rsp+180h+TokenHandle]; hObject
0x180063847  test    rcx, rcx
0x18006384a  jz      short loc_18006385D
0x18006384c  lea     rax, [rcx-1]
0x180063850  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180063854  ja      short loc_18006385D
0x180063856  call    cs:__imp_CloseHandle
0x18006385c  nop
0x18006385d  cmp     qword ptr [rdi+8], 0
0x180063862  jz      short loc_18006386C
0x180063864  mov     qword ptr [rdi+8], 0
0x18006386c  mov     rax, rsi
0x18006386f  mov     rcx, [rbp+80h+var_20]
0x180063873  xor     rcx, rsp; StackCookie
0x180063876  call    __security_check_cookie
0x18006387b  mov     rbx, [rsp+180h+arg_10]
0x180063883  add     rsp, 170h
0x18006388a  pop     rdi
0x18006388b  pop     rsi
0x18006388c  pop     rbp
0x18006388d  retn
0x18006388e  call    cs:__imp_GetLastError
0x180063894  nop
0x180063895  mov     ebx, eax
0x180063897  test    eax, eax
0x180063899  jle     short loc_1800638A4
0x18006389b  movzx   ebx, ax
0x18006389e  or      ebx, 80070000h
0x1800638a4  lea     rax, WPP_GLOBAL_Control
0x1800638ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800638b2  cmp     rcx, rax
0x1800638b5  jz      short loc_1800638D5
0x1800638b7  test    byte ptr [rcx+1Ch], 1
0x1800638bb  jz      short loc_1800638D5
0x1800638bd  mov     edx, 15h
0x1800638c2  mov     r9d, ebx
0x1800638c5  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x1800638cc  mov     rcx, [rcx+10h]
0x1800638d0  call    WPP_SF_d
0x1800638d5  mov     edx, ebx; int
0x1800638d7  lea     rcx, [rsp+180h+pExceptionObject]; this
0x1800638dc  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800638e1  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800638e8  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x1800638ed  call    _CxxThrowException_0
0x1800638f3  call    cs:__imp_GetLastError
0x1800638f9  mov     ebx, eax
0x1800638fb  test    eax, eax
0x1800638fd  jle     short loc_180063908
0x1800638ff  movzx   ebx, ax
0x180063902  or      ebx, 80070000h
0x180063908  lea     rax, WPP_GLOBAL_Control
0x18006390f  mov     rcx, cs:WPP_GLOBAL_Control
0x180063916  cmp     rcx, rax
0x180063919  jz      short loc_180063939
0x18006391b  test    byte ptr [rcx+1Ch], 1
0x18006391f  jz      short loc_180063939
0x180063921  mov     edx, 14h
0x180063926  mov     r9d, ebx
0x180063929  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x180063930  mov     rcx, [rcx+10h]
0x180063934  call    WPP_SF_d
0x180063939  mov     edx, ebx; int
0x18006393b  lea     rcx, [rsp+180h+pExceptionObject]; this
0x180063940  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180063945  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18006394c  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x180063951  call    _CxxThrowException_0
0x180063957  mov     edx, 80004003h; int
0x18006395c  lea     rcx, [rsp+180h+pExceptionObject]; this
0x180063961  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180063966  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18006396d  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x180063972  call    _CxxThrowException_0
```
