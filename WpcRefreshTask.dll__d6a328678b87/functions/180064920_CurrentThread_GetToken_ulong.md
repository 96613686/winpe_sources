# CurrentThread::GetToken(ulong)

- ea: `0x180064920`
- end: `0x180064a0f`
- name: `?GetToken@CurrentThread@@YA?AVToken@@K@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180062d28`

## callees

- `0x180006ee0`
- `0x18000ecc0`
- `0x180035e0c`
- `0x180063658`
- `0x180064920`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180064953`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180064953`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180064966`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180064966`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180064949`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180064949`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180064932`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180064932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800649ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800649ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006499c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006499c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CurrentThread::GetToken(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  _BYTE pExceptionObject[48]; // [rsp+28h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_921fc3043960359be1fe4e548f998926_Traceguids, v6);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v6);
      throw (ErrorCodeException *)pExceptionObject;
    }
  }
  hObject = TokenHandle;
  Token::Token(a1, (__int64 *)&hObject);
  if ( hObject && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return a1;
}

```

## disassembly

```asm
0x180064920  push    rbx
0x180064922  sub     rsp, 50h
0x180064926  mov     rbx, rcx
0x180064929  mov     [rsp+58h+TokenHandle], 0
0x180064932  call    cs:__imp_GetCurrentThread
0x180064938  mov     rcx, rax; ThreadHandle
0x18006493b  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180064940  mov     edx, 8; DesiredAccess
0x180064945  lea     r8d, [rdx-7]; OpenAsSelf
0x180064949  call    cs:__imp_OpenThreadToken
0x18006494f  test    eax, eax
0x180064951  jnz     short loc_180064970
0x180064953  call    cs:__imp_GetCurrentProcess
0x180064959  mov     rcx, rax; ProcessHandle
0x18006495c  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180064961  mov     edx, 8; DesiredAccess
0x180064966  call    cs:__imp_OpenProcessToken
0x18006496c  test    eax, eax
0x18006496e  jz      short loc_1800649AB
0x180064970  mov     rax, [rsp+58h+TokenHandle]
0x180064975  mov     [rsp+58h+hObject], rax
0x18006497a  lea     rdx, [rsp+58h+hObject]
0x18006497f  mov     rcx, rbx
0x180064982  call    ??0Token@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Token::Token(std::unique_ptr<void,Private::HandleClose> &&)
0x180064987  nop
0x180064988  mov     rcx, [rsp+58h+hObject]; hObject
0x18006498d  test    rcx, rcx
0x180064990  jz      short loc_1800649A2
0x180064992  lea     rax, [rcx-1]
0x180064996  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006499a  ja      short loc_1800649A2
0x18006499c  call    cs:__imp_CloseHandle
0x1800649a2  mov     rax, rbx
0x1800649a5  add     rsp, 50h
0x1800649a9  pop     rbx
0x1800649aa  retn
0x1800649ab  call    cs:__imp_GetLastError
0x1800649b1  mov     ebx, eax
0x1800649b3  test    eax, eax
0x1800649b5  jle     short loc_1800649C0
0x1800649b7  movzx   ebx, ax
0x1800649ba  or      ebx, 80070000h
0x1800649c0  lea     rax, WPP_GLOBAL_Control
0x1800649c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800649ce  cmp     rcx, rax
0x1800649d1  jz      short loc_1800649F1
0x1800649d3  test    byte ptr [rcx+1Ch], 1
0x1800649d7  jz      short loc_1800649F1
0x1800649d9  mov     edx, 0Ah
0x1800649de  mov     r9d, ebx
0x1800649e1  lea     r8, WPP_921fc3043960359be1fe4e548f998926_Traceguids
0x1800649e8  mov     rcx, [rcx+10h]
0x1800649ec  call    WPP_SF_d
0x1800649f1  mov     edx, ebx; int
0x1800649f3  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800649f8  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800649fd  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180064a04  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180064a09  call    _CxxThrowException_0
```
