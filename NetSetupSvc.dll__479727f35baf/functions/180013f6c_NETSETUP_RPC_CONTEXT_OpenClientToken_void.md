# NETSETUP_RPC_CONTEXT::OpenClientToken(void *)

- ea: `0x180013f6c`
- end: `0x18001407c`
- name: `?OpenClientToken@NETSETUP_RPC_CONTEXT@@QEAAPEAXPEAX@Z`
- size: `272`
- prototype: `void *__fastcall(NETSETUP_RPC_CONTEXT *this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180011f30`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008854`
- `0x18001238c`
- `0x180013f6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013fc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013fc8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013fe0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013fe0`
- `RPCRT4!RpcImpersonateClient` at `0x180013f8a`
- `RPCRT4!RpcImpersonateClient` at `0x180013f8a`

## pseudocode

```c
void *__fastcall NETSETUP_RPC_CONTEXT::OpenClientToken(NETSETUP_RPC_CONTEXT *this, void *a2)
{
  RPC_STATUS v2; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  void *v5; // rbx
  char v7[8]; // [rsp+20h] [rbp-F8h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+28h] [rbp-F0h] BYREF
  void *TokenHandle; // [rsp+F8h] [rbp-20h] BYREF

  v2 = RpcImpersonateClient(a2);
  if ( v2 )
  {
    HResultException::HResultException((HResultException *)pExceptionObject, v2 | 0x80010000);
    throw (HResultException *)pExceptionObject;
  }
  v7[0] = 1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_d7c9c24d725337bc8e6af9dd6d1b553a_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
  v5 = TokenHandle;
  NetSetupAutoImpersonate::~NetSetupAutoImpersonate((NetSetupAutoImpersonate *)v7);
  return v5;
}

```

## disassembly

```asm
0x180013f6c  push    rbx
0x180013f6e  sub     rsp, 110h
0x180013f75  mov     rax, cs:__security_cookie
0x180013f7c  xor     rax, rsp
0x180013f7f  mov     [rsp+118h+var_18], rax
0x180013f87  mov     rcx, rdx; BindingHandle
0x180013f8a  call    cs:__imp_RpcImpersonateClient
0x180013f90  test    eax, eax
0x180013f92  jz      short loc_180013FB7
0x180013f94  or      eax, 80010000h
0x180013f99  mov     edx, eax; int
0x180013f9b  lea     rcx, [rsp+118h+pExceptionObject]; this
0x180013fa0  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180013fa5  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180013fac  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180013fb1  call    _CxxThrowException_0
0x180013fb7  mov     [rsp+118h+var_F8], 1
0x180013fbc  mov     [rsp+118h+TokenHandle], 0
0x180013fc8  call    cs:__imp_GetCurrentThread
0x180013fce  mov     rcx, rax; ThreadHandle
0x180013fd1  lea     r9, [rsp+118h+TokenHandle]; TokenHandle
0x180013fd9  xor     r8d, r8d; OpenAsSelf
0x180013fdc  lea     edx, [r8+8]; DesiredAccess
0x180013fe0  call    cs:__imp_OpenThreadToken
0x180013fe6  test    eax, eax
0x180013fe8  jnz     short loc_18001404E
0x180013fea  call    cs:__imp_GetLastError
0x180013ff0  mov     ebx, eax
0x180013ff2  lea     rax, WPP_GLOBAL_Control
0x180013ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x180014000  cmp     rcx, rax
0x180014003  jz      short loc_180014023
0x180014005  cmp     byte ptr [rcx+19h], 2
0x180014009  jb      short loc_180014023
0x18001400b  mov     edx, 0Bh
0x180014010  mov     r9d, ebx
0x180014013  lea     r8, WPP_d7c9c24d725337bc8e6af9dd6d1b553a_Traceguids
0x18001401a  mov     rcx, [rcx+10h]
0x18001401e  call    WPP_SF_d
0x180014023  test    ebx, ebx
0x180014025  jle     short loc_180014030
0x180014027  movzx   ebx, bx
0x18001402a  or      ebx, 80070000h
0x180014030  mov     edx, ebx; int
0x180014032  lea     rcx, [rsp+118h+pExceptionObject]; this
0x180014037  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18001403c  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180014043  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180014048  call    _CxxThrowException_0
0x18001404e  mov     rbx, [rsp+118h+TokenHandle]
0x180014056  lea     rcx, [rsp+118h+var_F8]; this
0x18001405b  call    ??1NetSetupAutoImpersonate@@QEAA@XZ; NetSetupAutoImpersonate::~NetSetupAutoImpersonate(void)
0x180014060  mov     rax, rbx
0x180014063  mov     rcx, [rsp+118h+var_18]
0x18001406b  xor     rcx, rsp; StackCookie
0x18001406e  call    __security_check_cookie
0x180014073  add     rsp, 110h
0x18001407a  pop     rbx
0x18001407b  retn
```
