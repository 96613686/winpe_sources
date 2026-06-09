# CSession::~CSession(void)

- ea: `0x18000cb00`
- end: `0x18000cc59`
- name: `??1CSession@@QEAA@XZ`
- size: `345`
- prototype: `void __fastcall(CSession *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bf40`

## callees

- `0x180009010`
- `0x18000c8e4`
- `0x18000c9c4`
- `0x18000cb00`
- `0x18000d220`
- `0x18000db50`
- `0x18001714c`
- `0x18001ac5c`
- `0x18001c970`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000cba7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000cba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc04`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cc22`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cc22`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000cb85`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000cb85`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000cb92`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000cb92`

## pseudocode

```c
void __fastcall CSession::~CSession(CSession *this)
{
  struct _TP_CLEANUP_GROUP *v2; // rcx
  void *v3; // rcx
  int LastError; // eax
  int v5; // [rsp+20h] [rbp-40h] BYREF
  _QWORD *v6; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v7[2]; // [rsp+30h] [rbp-30h] BYREF
  char v8[24]; // [rsp+40h] [rbp-20h] BYREF

  v5 = 0;
  strcpy(v8, "CSession::~CSession");
  v7[0] = v8;
  v7[1] = &v5;
  lambda_cbdb8ddc6f50a2df8b483c7578a1e01f_::operator()(v7);
  v5 = 1;
  v6 = v7;
  ReaderMonitorStopThread((char *)this + 32);
  v2 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 64);
  if ( v2 )
  {
    CloseThreadpoolCleanupGroupMembers(v2, 1, 0);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 64));
  }
  v3 = (void *)*((_QWORD *)this + 32);
  if ( v3 )
    WaitForSingleObject(v3, 0xFFFFFFFF);
  if ( this != (CSession *)-32LL && *((_QWORD *)this + 18) )
  {
    I_ReaderListFree();
    *((_QWORD *)this + 18) = 0;
  }
  I_ReaderMonitorCleanup((char *)this + 32);
  WppTraceUnwinder__lambda_cbdb8ddc6f50a2df8b483c7578a1e01f____::_WppTraceUnwinder__lambda_cbdb8ddc6f50a2df8b483c7578a1e01f____(&v6);
  std::list<std::unique_ptr<CInformationNode>>::~list<std::unique_ptr<CInformationNode>>((__int64)this + 424);
  *((_QWORD *)this + 2) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( *((_QWORD *)this + 3) )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose((char *)this + 16) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RaiseException(LastError, 1u, 0, 0);
      __debugbreak();
    }
    *((_QWORD *)this + 3) = 0;
  }
  std::unique_ptr<ScopedTaskCounter>::_Delete((char *)this + 8);
}

```

## disassembly

```asm
0x18000cb00  mov     [rsp-8+arg_8], rbx
0x18000cb05  mov     [rsp-8+arg_10], rdi
0x18000cb0a  push    rbp
0x18000cb0b  mov     rbp, rsp
0x18000cb0e  sub     rsp, 60h
0x18000cb12  mov     rax, cs:__security_cookie
0x18000cb19  xor     rax, rsp
0x18000cb1c  mov     [rbp+var_8], rax
0x18000cb20  mov     rbx, rcx
0x18000cb23  mov     [rbp+var_40], 0
0x18000cb2a  movups  xmm0, xmmword ptr cs:aCsessionCsessi; "CSession::~CSession"
0x18000cb31  movups  xmmword ptr [rbp+var_20], xmm0
0x18000cb35  mov     eax, dword ptr cs:aCsessionCsessi+10h; "ion"
0x18000cb3b  mov     dword ptr [rbp+var_20+10h], eax
0x18000cb3e  lea     rax, [rbp+var_20]
0x18000cb42  mov     [rbp+var_30], rax
0x18000cb46  lea     rax, [rbp+var_40]
0x18000cb4a  mov     [rbp+var_28], rax
0x18000cb4e  lea     rcx, [rbp+var_30]
0x18000cb52  call    _lambda_cbdb8ddc6f50a2df8b483c7578a1e01f___operator__
0x18000cb57  mov     [rbp+var_40], 1
0x18000cb5e  lea     rax, [rbp+var_30]
0x18000cb62  mov     [rbp+var_38], rax
0x18000cb66  lea     rdi, [rbx+20h]
0x18000cb6a  mov     rcx, rdi
0x18000cb6d  call    ReaderMonitorStopThread
0x18000cb72  mov     rcx, [rbx+200h]; ptpcg
0x18000cb79  test    rcx, rcx
0x18000cb7c  jz      short loc_18000CB98
0x18000cb7e  xor     r8d, r8d; pvCleanupContext
0x18000cb81  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18000cb85  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18000cb8b  mov     rcx, [rbx+200h]; ptpcg
0x18000cb92  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000cb98  mov     rcx, [rbx+100h]; hHandle
0x18000cb9f  test    rcx, rcx
0x18000cba2  jz      short loc_18000CBAD
0x18000cba4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000cba7  call    cs:__imp_WaitForSingleObject
0x18000cbad  test    rdi, rdi
0x18000cbb0  jz      short loc_18000CBC8
0x18000cbb2  mov     rcx, [rdi+70h]
0x18000cbb6  test    rcx, rcx
0x18000cbb9  jz      short loc_18000CBC8
0x18000cbbb  call    I_ReaderListFree
0x18000cbc0  mov     qword ptr [rdi+70h], 0
0x18000cbc8  mov     rcx, rdi
0x18000cbcb  call    I_ReaderMonitorCleanup
0x18000cbd0  lea     rcx, [rbp+var_38]
0x18000cbd4  call    WppTraceUnwinder__lambda_cbdb8ddc6f50a2df8b483c7578a1e01f_______WppTraceUnwinder__lambda_cbdb8ddc6f50a2df8b483c7578a1e01f____
0x18000cbd9  lea     rcx, [rbx+1A8h]
0x18000cbe0  call    ??1?$list@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@V?$allocator@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::unique_ptr<CInformationNode>>::~list<std::unique_ptr<CInformationNode>>(void)
0x18000cbe5  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18000cbec  mov     [rbx+10h], rax
0x18000cbf0  cmp     qword ptr [rbx+18h], 0
0x18000cbf5  jz      short loc_18000CC31
0x18000cbf7  lea     rcx, [rbx+10h]
0x18000cbfb  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x18000cc00  test    al, al
0x18000cc02  jnz     short loc_18000CC29
0x18000cc04  call    cs:__imp_GetLastError
0x18000cc0a  test    eax, eax
0x18000cc0c  jle     short loc_18000CC16
0x18000cc0e  movzx   eax, ax
0x18000cc11  or      eax, 80070000h
0x18000cc16  xor     r9d, r9d; lpArguments
0x18000cc19  xor     r8d, r8d; nNumberOfArguments
0x18000cc1c  lea     edx, [r9+1]; dwExceptionFlags
0x18000cc20  mov     ecx, eax; dwExceptionCode
0x18000cc22  call    cs:__imp_RaiseException
0x18000cc28  int     3; Trap to Debugger
0x18000cc29  mov     qword ptr [rbx+18h], 0
0x18000cc31  lea     rcx, [rbx+8]
0x18000cc35  call    ?_Delete@?$unique_ptr@VScopedTaskCounter@@U?$default_delete@VScopedTaskCounter@@@std@@@std@@AEAAXXZ; std::unique_ptr<ScopedTaskCounter>::_Delete(void)
0x18000cc3a  nop
0x18000cc3b  mov     rcx, [rbp+var_8]
0x18000cc3f  xor     rcx, rsp; StackCookie
0x18000cc42  call    __security_check_cookie
0x18000cc47  lea     r11, [rsp+60h+var_s0]
0x18000cc4c  mov     rbx, [r11+18h]
0x18000cc50  mov     rdi, [r11+20h]
0x18000cc54  mov     rsp, r11
0x18000cc57  pop     rbp
0x18000cc58  retn
```
