# Token::GetElevated(void)

- ea: `0x180028044`
- end: `0x180028264`
- name: `?GetElevated@Token@@QEBA?AV1@XZ`
- size: `544`
- prototype: `_QWORD *__fastcall(HANDLE *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180006960`

## callees

- `0x1800032a0`
- `0x180003d20`
- `0x18000b29c`
- `0x1800195c4`
- `0x180027b00`
- `0x180027b3c`
- `0x180027bd4`
- `0x180028044`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002819f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002819f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028157`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028157`
- `ADVAPI32!GetTokenInformation` at `0x18002809b`
- `ADVAPI32!GetTokenInformation` at `0x1800280e1`
- `ADVAPI32!GetTokenInformation` at `0x18002809b`
- `ADVAPI32!GetTokenInformation` at `0x1800280e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Token::GetElevated(HANDLE *a1, _QWORD *a2)
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
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v13);
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
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v11);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v11);
      throw (ErrorCodeException *)pExceptionObject;
    }
    Token::Token(a2, (__int64 *)&hObject);
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
0x180028044  mov     [rsp-8+arg_10], rbx
0x180028049  mov     [rsp-8+arg_18], rdi
0x18002804e  push    rbp
0x18002804f  lea     rbp, [rsp-57h]
0x180028054  sub     rsp, 0E0h
0x18002805b  mov     rax, cs:__security_cookie
0x180028062  xor     rax, rsp
0x180028065  mov     [rbp+57h+var_10], rax
0x180028069  mov     rbx, rdx
0x18002806c  mov     rdi, rcx
0x18002806f  mov     [rbp+57h+var_A0], rdx
0x180028073  mov     [rbp+57h+TokenInformation], 0
0x18002807a  mov     [rbp+57h+var_AC], 0
0x180028081  lea     rax, [rbp+57h+var_AC]
0x180028085  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18002808a  mov     r9d, 4; TokenInformationLength
0x180028090  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180028094  lea     edx, [r9+0Eh]; TokenInformationClass
0x180028098  mov     rcx, [rcx]; TokenHandle
0x18002809b  call    cs:__imp_GetTokenInformation
0x1800280a1  test    eax, eax
0x1800280a3  jz      loc_180028202
0x1800280a9  cmp     [rbp+57h+TokenInformation], 3
0x1800280ad  jnz     loc_18002815F
0x1800280b3  mov     [rbp+57h+hObject], 0
0x1800280bb  lea     rdx, [rbp+57h+hObject]
0x1800280bf  lea     rcx, [rbp+57h+var_60]
0x1800280c3  call    ??$get_pointer@V?$unique_ptr@XUHandleClose@Private@@@std@@@stdext@@YA?AV?$GetPointer@PEAX@0@AEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(std::unique_ptr<void,Private::HandleClose> &)
0x1800280c8  lea     rcx, [rbp+57h+var_AC]
0x1800280cc  mov     [rsp+0E0h+ReturnLength], rcx; ReturnLength
0x1800280d1  mov     r9d, 8; TokenInformationLength
0x1800280d7  mov     r8, rax; TokenInformation
0x1800280da  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800280de  mov     rcx, [rdi]; TokenHandle
0x1800280e1  call    cs:__imp_GetTokenInformation
0x1800280e7  mov     edi, eax
0x1800280e9  mov     r8, [rbp+57h+var_20]
0x1800280ed  test    r8, r8
0x1800280f0  jz      short loc_180028130
0x1800280f2  mov     rcx, [rbp+57h+var_60]
0x1800280f6  mov     [rbp+57h+var_A0], rcx
0x1800280fa  mov     rcx, [r8]
0x1800280fd  mov     rax, [rcx+10h]
0x180028101  lea     rdx, [rbp+57h+var_A0]
0x180028105  mov     rcx, r8
0x180028108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002810d  mov     r8, [rbp+57h+var_20]
0x180028111  test    r8, r8
0x180028114  jz      short loc_180028130
0x180028116  mov     rax, [r8]
0x180028119  lea     rcx, [rbp+57h+var_58]
0x18002811d  cmp     r8, rcx
0x180028120  setnz   dl
0x180028123  mov     rcx, r8
0x180028126  mov     rax, [rax+20h]
0x18002812a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002812f  nop
0x180028130  test    edi, edi
0x180028132  jz      short loc_18002819F
0x180028134  lea     rdx, [rbp+57h+hObject]
0x180028138  mov     rcx, rbx
0x18002813b  call    ??0Token@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Token::Token(std::unique_ptr<void,Private::HandleClose> &&)
0x180028140  nop
0x180028141  mov     rax, [rbp+57h+hObject]
0x180028145  test    rax, rax
0x180028148  jz      short loc_18002817B
0x18002814a  lea     rcx, [rax-1]
0x18002814e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180028152  ja      short loc_18002817B
0x180028154  mov     rcx, rax; hObject
0x180028157  call    cs:__imp_CloseHandle
0x18002815d  jmp     short loc_18002817B
0x18002815f  mov     [rbp+57h+var_98], 0
0x180028167  lea     rax, [rbp+57h+var_A0]
0x18002816b  mov     [rsp+0E0h+ReturnLength], rax
0x180028170  mov     rdx, rbx
0x180028173  mov     rcx, rdi
0x180028176  call    ?Duplicate@Token@@QEBA?AV1@W4_TOKEN_TYPE@@W4_SECURITY_IMPERSONATION_LEVEL@@V?$Optional@W4IntegrityLevel@@@@@Z; Token::Duplicate(_TOKEN_TYPE,_SECURITY_IMPERSONATION_LEVEL,Optional<IntegrityLevel>)
0x18002817b  mov     rax, rbx
0x18002817e  mov     rcx, [rbp+57h+var_10]
0x180028182  xor     rcx, rsp; StackCookie
0x180028185  call    __security_check_cookie
0x18002818a  lea     r11, [rsp+0E0h+var_s0]
0x180028192  mov     rbx, [r11+20h]
0x180028196  mov     rdi, [r11+28h]
0x18002819a  mov     rsp, r11
0x18002819d  pop     rbp
0x18002819e  retn
0x18002819f  call    cs:__imp_GetLastError
0x1800281a5  nop
0x1800281a6  mov     ebx, eax
0x1800281a8  test    eax, eax
0x1800281aa  jle     short loc_1800281B5
0x1800281ac  movzx   ebx, ax
0x1800281af  or      ebx, 80070000h
0x1800281b5  lea     rax, WPP_GLOBAL_Control
0x1800281bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281c3  cmp     rcx, rax
0x1800281c6  jz      short loc_1800281E6
0x1800281c8  test    byte ptr [rcx+1Ch], 1
0x1800281cc  jz      short loc_1800281E6
0x1800281ce  mov     edx, 13h
0x1800281d3  mov     r9d, ebx
0x1800281d6  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x1800281dd  mov     rcx, [rcx+10h]
0x1800281e1  call    WPP_SF_d
0x1800281e6  mov     edx, ebx; int
0x1800281e8  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800281ec  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800281f1  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800281f8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800281fc  call    _CxxThrowException_0
0x180028202  call    cs:__imp_GetLastError
0x180028208  mov     ebx, eax
0x18002820a  test    eax, eax
0x18002820c  jle     short loc_180028217
0x18002820e  movzx   ebx, ax
0x180028211  or      ebx, 80070000h
0x180028217  lea     rax, WPP_GLOBAL_Control
0x18002821e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028225  cmp     rcx, rax
0x180028228  jz      short loc_180028248
0x18002822a  test    byte ptr [rcx+1Ch], 1
0x18002822e  jz      short loc_180028248
0x180028230  mov     edx, 12h
0x180028235  mov     r9d, ebx
0x180028238  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x18002823f  mov     rcx, [rcx+10h]
0x180028243  call    WPP_SF_d
0x180028248  mov     edx, ebx; int
0x18002824a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002824e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180028253  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18002825a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002825e  call    _CxxThrowException_0
```
