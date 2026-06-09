# Token::FromComClient(bool)

- ea: `0x180027e70`
- end: `0x18002803b`
- name: `?FromComClient@Token@@SA?AV1@_N@Z`
- size: `459`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006960`
- `0x1800073e0`

## callees

- `0x1800032a0`
- `0x180003d20`
- `0x18000b29c`
- `0x1800194d4`
- `0x1800195c4`
- `0x180027790`
- `0x180027b00`
- `0x180027b3c`
- `0x180027e70`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f57`
- `ADVAPI32!OpenThreadToken` at `0x180027ee6`
- `ADVAPI32!OpenThreadToken` at `0x180027ee6`
- `KERNEL32!GetCurrentThread` at `0x180027ed1`
- `KERNEL32!GetCurrentThread` at `0x180027ed1`
- `ole32!CoImpersonateClient` at `0x180027e9d`
- `ole32!CoImpersonateClient` at `0x180027e9d`

## pseudocode

```c
__int64 __fastcall Token::FromComClient(__int64 a1)
{
  HRESULT v2; // ebx
  void **v3; // rbx
  HANDLE CurrentThread; // rax
  BOOL v5; // ebx
  _BYTE *v6; // rdx
  signed int LastError; // eax
  unsigned int v9; // ebx
  HANDLE hObject; // [rsp+20h] [rbp-89h] BYREF
  __int64 v11; // [rsp+28h] [rbp-81h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-71h] BYREF
  __int64 v13; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v14[56]; // [rsp+68h] [rbp-41h] BYREF
  _BYTE *v15; // [rsp+A0h] [rbp-9h]
  _BYTE v16[64]; // [rsp+B0h] [rbp+7h] BYREF

  v11 = a1;
  v2 = CoImpersonateClient();
  if ( v2 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        16,
        WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids,
        (unsigned int)v2);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v2);
    throw (ErrorCodeException *)pExceptionObject;
  }
  ScopeGuard::ScopeGuard__lambda_a7ab6a13f0bfb3b95a7935bc4bcdb838___(v16);
  hObject = 0;
  v3 = (void **)stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(&v13, &hObject);
  CurrentThread = GetCurrentThread();
  v5 = OpenThreadToken(CurrentThread, 0xAu, 1, v3);
  if ( v15 )
  {
    v11 = v13;
    (*(void (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)v15 + 16LL))(v15, &v11);
    if ( v15 )
    {
      v6 = v14;
      LOBYTE(v6) = v15 != v14;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v15 + 32LL))(v15, v6);
    }
  }
  if ( !v5 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v9);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v9);
    throw (ErrorCodeException *)pExceptionObject;
  }
  Token::Token(a1, &hObject);
  if ( hObject && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  ScopeGuard::~ScopeGuard((ScopeGuard *)v16);
  return a1;
}

```

## disassembly

```asm
0x180027e70  mov     [rsp-8+arg_8], rbx
0x180027e75  mov     [rsp-8+arg_10], rdi
0x180027e7a  push    rbp
0x180027e7b  lea     rbp, [rsp-57h]
0x180027e80  sub     rsp, 100h
0x180027e87  mov     rax, cs:__security_cookie
0x180027e8e  xor     rax, rsp
0x180027e91  mov     [rbp+57h+var_10], rax
0x180027e95  mov     rdi, rcx
0x180027e98  mov     [rsp+100h+var_D8], rcx
0x180027e9d  call    cs:__imp_CoImpersonateClient
0x180027ea3  mov     ebx, eax
0x180027ea5  test    eax, eax
0x180027ea7  js      loc_180027FEE
0x180027ead  lea     rcx, [rbp+57h+var_50]
0x180027eb1  call    ScopeGuard__ScopeGuard__lambda_a7ab6a13f0bfb3b95a7935bc4bcdb838___
0x180027eb6  nop
0x180027eb7  mov     [rsp+100h+hObject], 0
0x180027ec0  lea     rdx, [rsp+100h+hObject]
0x180027ec5  lea     rcx, [rbp+57h+var_A0]
0x180027ec9  call    ??$get_pointer@V?$unique_ptr@XUHandleClose@Private@@@std@@@stdext@@YA?AV?$GetPointer@PEAX@0@AEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(std::unique_ptr<void,Private::HandleClose> &)
0x180027ece  mov     rbx, rax
0x180027ed1  call    cs:__imp_GetCurrentThread
0x180027ed7  mov     r9, rbx; TokenHandle
0x180027eda  mov     edx, 0Ah; DesiredAccess
0x180027edf  lea     r8d, [rdx-9]; OpenAsSelf
0x180027ee3  mov     rcx, rax; ThreadHandle
0x180027ee6  call    cs:__imp_OpenThreadToken
0x180027eec  mov     ebx, eax
0x180027eee  mov     rcx, [rbp+57h+var_60]
0x180027ef2  test    rcx, rcx
0x180027ef5  jz      short loc_180027F31
0x180027ef7  mov     rax, [rbp+57h+var_A0]
0x180027efb  mov     [rsp+100h+var_D8], rax
0x180027f00  mov     rax, [rcx]
0x180027f03  lea     rdx, [rsp+100h+var_D8]
0x180027f08  mov     rax, [rax+10h]
0x180027f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f11  mov     rcx, [rbp+57h+var_60]
0x180027f15  test    rcx, rcx
0x180027f18  jz      short loc_180027F31
0x180027f1a  mov     rax, [rcx]
0x180027f1d  lea     rdx, [rbp+57h+var_98]
0x180027f21  cmp     rcx, rdx
0x180027f24  setnz   dl
0x180027f27  mov     rax, [rax+20h]
0x180027f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f30  nop
0x180027f31  test    ebx, ebx
0x180027f33  jz      short loc_180027F8B
0x180027f35  lea     rdx, [rsp+100h+hObject]
0x180027f3a  mov     rcx, rdi
0x180027f3d  call    ??0Token@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Token::Token(std::unique_ptr<void,Private::HandleClose> &&)
0x180027f42  nop
0x180027f43  mov     rcx, [rsp+100h+hObject]; hObject
0x180027f48  test    rcx, rcx
0x180027f4b  jz      short loc_180027F5E
0x180027f4d  lea     rdx, [rcx-1]
0x180027f51  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180027f55  ja      short loc_180027F5E
0x180027f57  call    cs:__imp_CloseHandle
0x180027f5d  nop
0x180027f5e  lea     rcx, [rbp+57h+var_50]; this
0x180027f62  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x180027f67  mov     rax, rdi
0x180027f6a  mov     rcx, [rbp+57h+var_10]
0x180027f6e  xor     rcx, rsp; StackCookie
0x180027f71  call    __security_check_cookie
0x180027f76  lea     r11, [rsp+100h+var_s0]
0x180027f7e  mov     rbx, [r11+18h]
0x180027f82  mov     rdi, [r11+20h]
0x180027f86  mov     rsp, r11
0x180027f89  pop     rbp
0x180027f8a  retn
0x180027f8b  call    cs:__imp_GetLastError
0x180027f91  nop
0x180027f92  mov     ebx, eax
0x180027f94  test    eax, eax
0x180027f96  jle     short loc_180027FA1
0x180027f98  movzx   ebx, ax
0x180027f9b  or      ebx, 80070000h
0x180027fa1  lea     rax, WPP_GLOBAL_Control
0x180027fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180027faf  cmp     rcx, rax
0x180027fb2  jz      short loc_180027FD2
0x180027fb4  test    byte ptr [rcx+1Ch], 1
0x180027fb8  jz      short loc_180027FD2
0x180027fba  mov     edx, 11h
0x180027fbf  mov     r9d, ebx
0x180027fc2  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x180027fc9  mov     rcx, [rcx+10h]
0x180027fcd  call    WPP_SF_d
0x180027fd2  mov     edx, ebx; int
0x180027fd4  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180027fd8  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180027fdd  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180027fe4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180027fe8  call    _CxxThrowException_0
0x180027fee  lea     rax, WPP_GLOBAL_Control
0x180027ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ffc  cmp     rcx, rax
0x180027fff  jz      short loc_18002801F
0x180028001  test    byte ptr [rcx+1Ch], 1
0x180028005  jz      short loc_18002801F
0x180028007  mov     edx, 10h
0x18002800c  mov     r9d, ebx
0x18002800f  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x180028016  mov     rcx, [rcx+10h]
0x18002801a  call    WPP_SF_d
0x18002801f  mov     edx, ebx; int
0x180028021  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180028025  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18002802a  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180028031  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180028035  call    _CxxThrowException_0
```
