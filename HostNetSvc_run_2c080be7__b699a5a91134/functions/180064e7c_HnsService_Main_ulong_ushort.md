# HnsService::Main(ulong,ushort * *)

- ea: `0x180064e7c`
- end: `0x1800650b7`
- name: `?Main@HnsService@@IEAAXKPEAPEAG@Z`
- size: `571`
- prototype: `void __fastcall(HnsService *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180066770`

## callees

- `0x180001b68`
- `0x18005f0c0`
- `0x18005f560`
- `0x18005f59c`
- `0x18005ffc4`
- `0x180064e7c`
- `0x18006531c`
- `0x1800657b8`
- `0x180066534`
- `0x18006a1c0`
- `0x18006d588`
- `0x1802b7010`

## import_xrefs

- `WS2_32!__imp_WSAGetLastError` at `0x180064ef6`
- `WS2_32!__imp_WSAGetLastError` at `0x180064ef6`
- `WS2_32!__imp_WSAStartup` at `0x180064eda`
- `WS2_32!__imp_WSAStartup` at `0x180064eda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180065091`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180065091`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180064f9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180064f9a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006502d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006502d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064fd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064fd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fc1`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180064eb8`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180064eb8`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180064f5d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180064f5d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180064fcc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180064fcc`
- `NetMgmtIF!NetMgmtRemoveHyperVVirtualNetworks` at `0x180065084`
- `NetMgmtIF!NetMgmtRemoveHyperVVirtualNetworks` at `0x180065084`

## pseudocode

```c
void __fastcall HnsService::Main(HnsService *this, __int64 a2, unsigned __int16 **a3)
{
  __int64 v3; // rbx
  DWORD Error; // eax
  __int16 *v5; // rdx
  void (__fastcall *v6)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(HnsService *, unsigned __int8), void *, int); // r14
  HANDLE v7; // rsi
  HANDLE v8; // rdi
  DWORD LastError; // ebx
  HnsService *v10; // rcx
  unsigned int v11; // r8d
  HnsService *v12; // rcx
  bool v13; // di
  HNSCore *v14; // rax
  HNSCore *v15; // rax
  HnsService *v16; // rcx
  HNSCore *v17; // rbx
  HnsService *v18; // rcx
  unsigned int v19; // r8d
  DWORD v20; // [rsp+40h] [rbp-C0h] BYREF
  WSAData WSAData; // [rsp+50h] [rbp-B0h] BYREF
  char v22[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  DWORD *v23; // [rsp+210h] [rbp+110h]
  __int64 v24; // [rsp+218h] [rbp+118h]

  EventRegister(&MSHNS, 0, 0, &g_HnsLogging);
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( WSAStartup(0x202u, &WSAData) )
  {
    v3 = qword_180397C20;
    if ( *(_DWORD *)qword_180397C20 <= 1u )
      return;
    Error = WSAGetLastError();
    v5 = word_1803332A2;
    goto LABEL_4;
  }
  HnsService::Instance = RegisterServiceCtrlHandlerExW(L"hns", HnsService::Handler, &HnsService::Instance);
  if ( HnsService::Instance )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v6 = *(void (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(HnsService *, unsigned __int8), void *, int))(qword_180397C48 + 192);
    v7 = hObject;
    v8 = WaitHandle;
    if ( WaitHandle )
    {
      LastError = GetLastError();
      UnregisterWait(v8);
      SetLastError(LastError);
    }
    WaitHandle = 0;
    v6(&WaitHandle, L"hns", v7, HnsService::StopCallback, &HnsService::Instance, 24);
    HnsService::SetStatus(v10, 2u, v11);
    v13 = HnsService::WaitForVmSwitch(v12);
    if ( WaitForSingleObject(hObject, 0) )
    {
      v14 = (HNSCore *)operator new(0x2B0u);
      v15 = HNSCore::HNSCore(v14);
      v17 = qword_180397C50;
      qword_180397C50 = v15;
      if ( v17 )
      {
        HNSCore::~HNSCore(v17);
        operator delete(v17, (const struct std::nothrow_t *)0x2B0);
      }
      HnsService::OnStart(v16);
      HnsService::SetStatus(v18, 4u, v19);
      if ( v13 )
        NetMgmtRemoveHyperVVirtualNetworks();
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  else
  {
    v3 = qword_180397C20;
    if ( *(_DWORD *)qword_180397C20 > 1u )
    {
      Error = GetLastError();
      v5 = &word_180333276;
LABEL_4:
      v20 = Error;
      v23 = &v20;
      v24 = 4;
      tlgWriteTransfer_EventWriteTransfer(v3, v5, 0, 0, 3, v22);
    }
  }
}

```

## disassembly

```asm
0x180064e7c  push    rbp
0x180064e7e  push    rbx
0x180064e7f  push    rsi
0x180064e80  push    rdi
0x180064e81  push    r12
0x180064e83  push    r14
0x180064e85  lea     rbp, [rsp-138h]
0x180064e8d  sub     rsp, 238h
0x180064e94  mov     rax, cs:__security_cookie
0x180064e9b  xor     rax, rsp
0x180064e9e  mov     [rbp+160h+var_40], rax
0x180064ea5  lea     r9, ?g_HnsLogging@@3_KA; RegHandle
0x180064eac  xor     r8d, r8d; CallbackContext
0x180064eaf  xor     edx, edx; EnableCallback
0x180064eb1  lea     rcx, MSHNS; ProviderId
0x180064eb8  call    cs:__imp_EventRegister
0x180064ebe  xor     edx, edx; Val
0x180064ec0  mov     r8d, 198h; Size
0x180064ec6  lea     rcx, [rsp+260h+WSAData]; void *
0x180064ecb  call    memset_0
0x180064ed0  mov     ecx, 202h; wVersionRequested
0x180064ed5  lea     rdx, [rsp+260h+WSAData]; lpWSAData
0x180064eda  call    cs:__imp_WSAStartup
0x180064ee0  test    eax, eax
0x180064ee2  jz      short loc_180064F45
0x180064ee4  mov     rbx, cs:qword_180397C20
0x180064eeb  mov     eax, [rbx]
0x180064eed  cmp     eax, 1
0x180064ef0  jbe     loc_180065098
0x180064ef6  call    cs:__imp_WSAGetLastError
0x180064efc  lea     rdx, word_1803332A2
0x180064f03  mov     [rsp+260h+var_220], eax
0x180064f07  lea     rax, [rsp+260h+var_220]
0x180064f0c  mov     [rbp+160h+var_50], rax
0x180064f13  lea     rax, [rbp+160h+var_70]
0x180064f1a  xor     r9d, r9d
0x180064f1d  mov     [rsp+260h+var_238], rax
0x180064f22  xor     r8d, r8d
0x180064f25  mov     dword ptr [rsp+260h+var_240], 3
0x180064f2d  mov     [rbp+160h+var_48], 4
0x180064f38  mov     rcx, rbx
0x180064f3b  call    _tlgWriteTransfer_EventWriteTransfer
0x180064f40  jmp     loc_180065098
0x180064f45  lea     r12, ?Instance@HnsService@@2V1@A; HnsService HnsService::Instance
0x180064f4c  mov     r8, r12; lpContext
0x180064f4f  lea     rdx, ?Handler@HnsService@@KAKKKPEAX0@Z; lpHandlerProc
0x180064f56  lea     rcx, ServiceName; "hns"
0x180064f5d  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180064f63  mov     cs:?Instance@HnsService@@2V1@A, rax; HnsService HnsService::Instance
0x180064f6a  test    rax, rax
0x180064f6d  jnz     short loc_180064F93
0x180064f6f  mov     rbx, cs:qword_180397C20
0x180064f76  mov     eax, [rbx]
0x180064f78  cmp     eax, 1
0x180064f7b  jbe     loc_180065098
0x180064f81  call    cs:__imp_GetLastError
0x180064f87  lea     rdx, word_180333276
0x180064f8e  jmp     loc_180064F03
0x180064f93  lea     rcx, SRWLock; SRWLock
0x180064f9a  call    cs:__imp_AcquireSRWLockExclusive
0x180064fa0  mov     rax, cs:qword_180397C48
0x180064fa7  mov     r14, [rax+0C0h]
0x180064fae  mov     rsi, cs:hObject
0x180064fb5  mov     rdi, cs:WaitHandle
0x180064fbc  test    rdi, rdi
0x180064fbf  jz      short loc_180064FDA
0x180064fc1  call    cs:__imp_GetLastError
0x180064fc7  mov     ebx, eax
0x180064fc9  mov     rcx, rdi; WaitHandle
0x180064fcc  call    cs:__imp_UnregisterWait
0x180064fd2  mov     ecx, ebx; dwErrCode
0x180064fd4  call    cs:__imp_SetLastError
0x180064fda  mov     cs:WaitHandle, 0
0x180064fe5  mov     dword ptr [rsp+260h+var_238], 18h
0x180064fed  mov     [rsp+260h+var_240], r12
0x180064ff2  lea     r9, ?StopCallback@HnsService@@CAXPEAXE@Z; HnsService::StopCallback(void *,uchar)
0x180064ff9  mov     r8, rsi
0x180064ffc  lea     rdx, ServiceName; "hns"
0x180065003  lea     rcx, WaitHandle
0x18006500a  mov     rax, r14
0x18006500d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065012  mov     edx, 2; unsigned int
0x180065017  call    ?SetStatus@HnsService@@IEAAXKK@Z; HnsService::SetStatus(ulong,ulong)
0x18006501c  call    ?WaitForVmSwitch@HnsService@@AEAA_NXZ; HnsService::WaitForVmSwitch(void)
0x180065021  mov     dil, al
0x180065024  xor     edx, edx; dwMilliseconds
0x180065026  mov     rcx, cs:hObject; hHandle
0x18006502d  call    cs:__imp_WaitForSingleObject
0x180065033  test    eax, eax
0x180065035  jz      short loc_18006508A
0x180065037  mov     esi, 2B0h
0x18006503c  mov     ecx, esi; Size
0x18006503e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180065043  mov     rcx, rax; this
0x180065046  call    ??0HNSCore@@QEAA@XZ; HNSCore::HNSCore(void)
0x18006504b  mov     rbx, cs:qword_180397C50
0x180065052  mov     cs:qword_180397C50, rax
0x180065059  test    rbx, rbx
0x18006505c  jz      short loc_180065070
0x18006505e  mov     rcx, rbx; this
0x180065061  call    ??1HNSCore@@UEAA@XZ; HNSCore::~HNSCore(void)
0x180065066  mov     edx, esi; struct std::nothrow_t *
0x180065068  mov     rcx, rbx; void *
0x18006506b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180065070  call    ?OnStart@HnsService@@IEAAXXZ; HnsService::OnStart(void)
0x180065075  mov     edx, 4; unsigned int
0x18006507a  call    ?SetStatus@HnsService@@IEAAXKK@Z; HnsService::SetStatus(ulong,ulong)
0x18006507f  test    dil, dil
0x180065082  jz      short loc_18006508A
0x180065084  call    cs:__imp_NetMgmtRemoveHyperVVirtualNetworks
0x18006508a  lea     rcx, SRWLock; SRWLock
0x180065091  call    cs:__imp_ReleaseSRWLockExclusive
0x180065097  nop
0x180065098  mov     rcx, [rbp+160h+var_40]
0x18006509f  xor     rcx, rsp; StackCookie
0x1800650a2  call    __security_check_cookie
0x1800650a7  add     rsp, 238h
0x1800650ae  pop     r14
0x1800650b0  pop     r12
0x1800650b2  pop     rdi
0x1800650b3  pop     rsi
0x1800650b4  pop     rbx
0x1800650b5  pop     rbp
0x1800650b6  retn
```
