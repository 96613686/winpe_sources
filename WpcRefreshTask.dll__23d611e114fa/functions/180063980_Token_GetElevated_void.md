# Token::GetElevated(void)

- ea: `0x180063980`
- end: `0x180063ba0`
- name: `?GetElevated@Token@@QEBA?AV1@XZ`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002aae4`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x18000ecc0`
- `0x180035e0c`
- `0x18006105c`
- `0x180063658`
- `0x1800636e4`
- `0x180063980`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063adb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063adb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063a93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063a93`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800639d7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180063a1d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800639d7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180063a1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Token::GetElevated(HANDLE *a1, __int64 a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  void *v6; // rax
  BOOL v7; // edi
  __int64 v8; // rdx
  signed int v10; // eax
  unsigned int v11; // ebx
  signed int LastError; // eax
  unsigned int v13; // ebx
  int TokenInformation; // [rsp+30h] [rbp-59h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-55h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v17[3]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v19; // [rsp+80h] [rbp-9h] BYREF
  char v20; // [rsp+88h] [rbp-1h] BYREF
  char *v21; // [rsp+C0h] [rbp+37h]

  v17[0] = a2;
  TokenInformation = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation(*a1, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v13);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v13);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( TokenInformation == 3 )
  {
    hObject = 0;
    v6 = (void *)stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(&v19, &hObject);
    v7 = GetTokenInformation(*a1, TokenLinkedToken, v6, 8u, &ReturnLength);
    if ( v21 )
    {
      v17[0] = v19;
      (*(void (__fastcall **)(char *, _QWORD *))(*(_QWORD *)v21 + 16LL))(v21, v17);
      if ( v21 )
      {
        LOBYTE(v8) = v21 != &v20;
        (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v21 + 32LL))(v21, v8);
      }
    }
    if ( !v7 )
    {
      v10 = GetLastError();
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v11);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v11);
      throw (ErrorCodeException *)pExceptionObject;
    }
    Token::Token(a2, &hObject);
    if ( hObject && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
  }
  else
  {
    v17[1] = 0;
    Token::Duplicate(a1, a2, v4, v5, (__int64)v17);
  }
  return a2;
}

```

## disassembly

```asm
0x180063980  mov     [rsp-8+arg_10], rbx
0x180063985  mov     [rsp-8+arg_18], rdi
0x18006398a  push    rbp
0x18006398b  lea     rbp, [rsp-57h]
0x180063990  sub     rsp, 0E0h
0x180063997  mov     rax, cs:__security_cookie
0x18006399e  xor     rax, rsp
0x1800639a1  mov     [rbp+57h+var_10], rax
0x1800639a5  mov     rbx, rdx
0x1800639a8  mov     rdi, rcx
0x1800639ab  mov     [rbp+57h+var_A0], rdx
0x1800639af  mov     [rbp+57h+TokenInformation], 0
0x1800639b6  mov     [rbp+57h+var_AC], 0
0x1800639bd  lea     rax, [rbp+57h+var_AC]
0x1800639c1  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800639c6  mov     r9d, 4; TokenInformationLength
0x1800639cc  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800639d0  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800639d4  mov     rcx, [rcx]; TokenHandle
0x1800639d7  call    cs:__imp_GetTokenInformation
0x1800639dd  test    eax, eax
0x1800639df  jz      loc_180063B3E
0x1800639e5  cmp     [rbp+57h+TokenInformation], 3
0x1800639e9  jnz     loc_180063A9B
0x1800639ef  mov     [rbp+57h+hObject], 0
0x1800639f7  lea     rdx, [rbp+57h+hObject]
0x1800639fb  lea     rcx, [rbp+57h+var_60]
0x1800639ff  call    ??$get_pointer@V?$unique_ptr@XUHandleClose@Private@@@std@@@stdext@@YA?AV?$GetPointer@PEAX@0@AEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(std::unique_ptr<void,Private::HandleClose> &)
0x180063a04  lea     rcx, [rbp+57h+var_AC]
0x180063a08  mov     [rsp+0E0h+ReturnLength], rcx; ReturnLength
0x180063a0d  mov     r9d, 8; TokenInformationLength
0x180063a13  mov     r8, rax; TokenInformation
0x180063a16  lea     edx, [r9+0Bh]; TokenInformationClass
0x180063a1a  mov     rcx, [rdi]; TokenHandle
0x180063a1d  call    cs:__imp_GetTokenInformation
0x180063a23  mov     edi, eax
0x180063a25  mov     r8, [rbp+57h+var_20]
0x180063a29  test    r8, r8
0x180063a2c  jz      short loc_180063A6C
0x180063a2e  mov     rcx, [rbp+57h+var_60]
0x180063a32  mov     [rbp+57h+var_A0], rcx
0x180063a36  mov     rcx, [r8]
0x180063a39  mov     rax, [rcx+10h]
0x180063a3d  lea     rdx, [rbp+57h+var_A0]
0x180063a41  mov     rcx, r8
0x180063a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a49  mov     r8, [rbp+57h+var_20]
0x180063a4d  test    r8, r8
0x180063a50  jz      short loc_180063A6C
0x180063a52  mov     rax, [r8]
0x180063a55  lea     rcx, [rbp+57h+var_58]
0x180063a59  cmp     r8, rcx
0x180063a5c  setnz   dl
0x180063a5f  mov     rcx, r8
0x180063a62  mov     rax, [rax+20h]
0x180063a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a6b  nop
0x180063a6c  test    edi, edi
0x180063a6e  jz      short loc_180063ADB
0x180063a70  lea     rdx, [rbp+57h+hObject]
0x180063a74  mov     rcx, rbx
0x180063a77  call    ??0Token@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Token::Token(std::unique_ptr<void,Private::HandleClose> &&)
0x180063a7c  nop
0x180063a7d  mov     rax, [rbp+57h+hObject]
0x180063a81  test    rax, rax
0x180063a84  jz      short loc_180063AB7
0x180063a86  lea     rcx, [rax-1]
0x180063a8a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180063a8e  ja      short loc_180063AB7
0x180063a90  mov     rcx, rax; hObject
0x180063a93  call    cs:__imp_CloseHandle
0x180063a99  jmp     short loc_180063AB7
0x180063a9b  mov     [rbp+57h+var_98], 0
0x180063aa3  lea     rax, [rbp+57h+var_A0]
0x180063aa7  mov     [rsp+0E0h+ReturnLength], rax
0x180063aac  mov     rdx, rbx
0x180063aaf  mov     rcx, rdi
0x180063ab2  call    ?Duplicate@Token@@QEBA?AV1@W4_TOKEN_TYPE@@W4_SECURITY_IMPERSONATION_LEVEL@@V?$Optional@W4IntegrityLevel@@@@@Z; Token::Duplicate(_TOKEN_TYPE,_SECURITY_IMPERSONATION_LEVEL,Optional<IntegrityLevel>)
0x180063ab7  mov     rax, rbx
0x180063aba  mov     rcx, [rbp+57h+var_10]
0x180063abe  xor     rcx, rsp; StackCookie
0x180063ac1  call    __security_check_cookie
0x180063ac6  lea     r11, [rsp+0E0h+var_s0]
0x180063ace  mov     rbx, [r11+20h]
0x180063ad2  mov     rdi, [r11+28h]
0x180063ad6  mov     rsp, r11
0x180063ad9  pop     rbp
0x180063ada  retn
0x180063adb  call    cs:__imp_GetLastError
0x180063ae1  nop
0x180063ae2  mov     ebx, eax
0x180063ae4  test    eax, eax
0x180063ae6  jle     short loc_180063AF1
0x180063ae8  movzx   ebx, ax
0x180063aeb  or      ebx, 80070000h
0x180063af1  lea     rax, WPP_GLOBAL_Control
0x180063af8  mov     rcx, cs:WPP_GLOBAL_Control
0x180063aff  cmp     rcx, rax
0x180063b02  jz      short loc_180063B22
0x180063b04  test    byte ptr [rcx+1Ch], 1
0x180063b08  jz      short loc_180063B22
0x180063b0a  mov     edx, 13h
0x180063b0f  mov     r9d, ebx
0x180063b12  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x180063b19  mov     rcx, [rcx+10h]
0x180063b1d  call    WPP_SF_d
0x180063b22  mov     edx, ebx; int
0x180063b24  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180063b28  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180063b2d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180063b34  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180063b38  call    _CxxThrowException_0
0x180063b3e  call    cs:__imp_GetLastError
0x180063b44  mov     ebx, eax
0x180063b46  test    eax, eax
0x180063b48  jle     short loc_180063B53
0x180063b4a  movzx   ebx, ax
0x180063b4d  or      ebx, 80070000h
0x180063b53  lea     rax, WPP_GLOBAL_Control
0x180063b5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180063b61  cmp     rcx, rax
0x180063b64  jz      short loc_180063B84
0x180063b66  test    byte ptr [rcx+1Ch], 1
0x180063b6a  jz      short loc_180063B84
0x180063b6c  mov     edx, 12h
0x180063b71  mov     r9d, ebx
0x180063b74  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x180063b7b  mov     rcx, [rcx+10h]
0x180063b7f  call    WPP_SF_d
0x180063b84  mov     edx, ebx; int
0x180063b86  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180063b8a  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180063b8f  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180063b96  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180063b9a  call    _CxxThrowException_0
```
