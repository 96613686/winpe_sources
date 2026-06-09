# Container::Manager::Core::Details::PdcClient::Worker(void)

- ea: `0x1800d4d7c`
- end: `0x1800d503c`
- name: `?Worker@PdcClient@Details@Core@Manager@Container@@AEAAXXZ`
- size: `704`
- prototype: `void __fastcall(Container::Manager::Core::Details::PdcClient *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x1800d3d00`

## callees

- `0x180004bd0`
- `0x180007c0c`
- `0x180007e54`
- `0x180009cc0`
- `0x18001063c`
- `0x18002d030`
- `0x180042928`
- `0x1800d36d4`
- `0x1800d376c`
- `0x1800d3804`
- `0x1800d3a10`
- `0x1800d3f98`
- `0x1800d4d7c`

## import_xrefs

- `ntdll!RtlWaitOnAddress` at `0x1800d4f57`
- `ntdll!RtlWaitOnAddress` at `0x1800d4f57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d4db3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d4fc9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d4db3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d4fc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d4dec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d4fec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d4dec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d4fec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d4e5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d4e5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d4e31`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d4e31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d4dbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d4dce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d4fd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d4dbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d4dce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d4fd5`
- `UMPDC!PdcNotificationClientAcknowledge` at `0x1800d4f91`
- `UMPDC!PdcNotificationClientAcknowledge` at `0x1800d4f91`

## pseudocode

```c
void __fastcall Container::Manager::Core::Details::PdcClient::Worker(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  char v3; // r13
  RTL_SRWLOCK *v4; // rsi
  char v5; // r12
  int Ptr; // r14d
  Csl *v7; // rcx
  int UnbiasedInterruptTimeMs64; // eax
  int v9; // r15d
  int v10; // esi
  unsigned int v11; // esi
  char v12; // al
  __int64 v13; // r14
  int v14; // eax
  __int64 v15; // rax
  __int64 *v16; // rsi
  __int64 *v17; // r9
  unsigned int v18; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  char v20[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-CCh]
  char v22; // [rsp+38h] [rbp-C8h]
  unsigned int v23; // [rsp+3Ch] [rbp-C4h]
  PVOID v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v25[42]; // [rsp+50h] [rbp-B0h] BYREF

  v1 = this + 2;
  AcquireSRWLockExclusive(this + 2);
  LODWORD(v1[1].Ptr) = GetCurrentThreadId();
  HIDWORD(this[4].Ptr) = GetCurrentThreadId();
  if ( v1 )
  {
    LODWORD(v1[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v1);
  }
  wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v25,
    "PdcWorker");
  v25[0] = &CmTraceProvider::PdcWorker::`vftable';
  CmTraceProvider::PdcWorker::StartActivity((CmTraceProvider::PdcWorker *)v25);
  v3 = 0;
  v4 = this + 5;
  v5 = 0;
  while ( 1 )
  {
    v24[0] = 0;
    AcquireSRWLockShared(v1);
    Ptr = (int)this[4].Ptr;
    v24[0] = v4->Ptr;
    UnbiasedInterruptTimeMs64 = Csl::QueryUnbiasedInterruptTimeMs64(v7);
    v9 = (int)this[4].Ptr;
    v10 = UnbiasedInterruptTimeMs64;
    if ( v1 )
      ReleaseSRWLockShared(v1);
    if ( !Ptr )
      break;
    v11 = v10 - v9;
    v12 = 0;
    if ( !v3 && v11 >= 0x7530 )
    {
      v12 = 1;
      v3 = 1;
    }
    v20[0] = 1;
    v21 = v11;
    v22 = v12;
    v23 = -1;
    Container::Manager::Core::Details::IterateContainers(
      Container::Manager::Core::Details::TryEnterCsIterateContainersCallback,
      v20,
      3);
    v13 = v23;
    v18 = v23;
    if ( v20[0] )
      break;
    if ( !v5 && v11 >= 0x15F90 )
    {
      CmTraceProvider::ExcessiveCsEntryTime();
      v5 = 1;
    }
    if ( v3 )
    {
      if ( v5 )
        goto LABEL_20;
      v14 = 90000;
    }
    else
    {
      v14 = 30000;
    }
    v15 = v14 - v11;
    if ( (unsigned int)v13 >= (unsigned int)v15 )
    {
      v18 = v15;
      goto LABEL_21;
    }
LABEL_20:
    v15 = v13;
LABEL_21:
    v19 = 0;
    if ( (_DWORD)v15 == -1 )
    {
      v16 = 0;
    }
    else
    {
      v16 = &v19;
      v19 = -10000 * v15;
    }
    CmTraceProvider::PdcWorker::PdcWorkerWait<unsigned long &>(v25, &v18);
    v17 = v16;
    v4 = this + 5;
    v18 = RtlWaitOnAddress(&this[5], v24, 8, v17, v18, v19);
    CmTraceProvider::PdcWorker::PdcWorkerWake<long &>(v25, &v18);
  }
  if ( !BYTE2(this[6].Ptr) )
    __int2c();
  if ( BYTE1(this[6].Ptr) )
  {
    v18 = PdcNotificationClientAcknowledge(this->Ptr, 0);
    CmTraceProvider::PdcWorker::PdcWorkerPdcAck<long &>(v25, &v18);
  }
  if ( BYTE2(this[6].Ptr) )
    BYTE2(this[6].Ptr) = 0;
  wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v25, 0);
  AcquireSRWLockExclusive(v1);
  GetCurrentThreadId();
  HIDWORD(this[4].Ptr) = 0;
  LODWORD(v1[1].Ptr) = 0;
  ReleaseSRWLockExclusive(v1);
  v25[0] = &CmTraceProvider::PdcWorker::`vftable';
  wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v25);
  wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v25);
}

```

## disassembly

```asm
0x1800d4d7c  push    rbp
0x1800d4d7e  push    rbx
0x1800d4d7f  push    rsi
0x1800d4d80  push    rdi
0x1800d4d81  push    r12
0x1800d4d83  push    r13
0x1800d4d85  push    r14
0x1800d4d87  push    r15
0x1800d4d89  lea     rbp, [rsp-0B8h]
0x1800d4d91  sub     rsp, 1B8h
0x1800d4d98  mov     rax, cs:__security_cookie
0x1800d4d9f  xor     rax, rsp
0x1800d4da2  mov     [rbp+0F0h+var_50], rax
0x1800d4da9  lea     rdi, [rcx+10h]
0x1800d4dad  mov     rbx, rcx
0x1800d4db0  mov     rcx, rdi; SRWLock
0x1800d4db3  call    cs:__imp_AcquireSRWLockExclusive
0x1800d4dba  nop     dword ptr [rax+rax+00h]
0x1800d4dbf  call    cs:__imp_GetCurrentThreadId
0x1800d4dc6  nop     dword ptr [rax+rax+00h]
0x1800d4dcb  mov     [rdi+8], eax
0x1800d4dce  call    cs:__imp_GetCurrentThreadId
0x1800d4dd5  nop     dword ptr [rax+rax+00h]
0x1800d4dda  xor     r15d, r15d
0x1800d4ddd  mov     [rbx+24h], eax
0x1800d4de0  test    rdi, rdi
0x1800d4de3  jz      short loc_1800D4DF8
0x1800d4de5  mov     rcx, rdi; SRWLock
0x1800d4de8  mov     [rdi+8], r15d
0x1800d4dec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d4df3  nop     dword ptr [rax+rax+00h]
0x1800d4df8  lea     rdx, aPdcworker; "PdcWorker"
0x1800d4dff  lea     rcx, [rsp+1F0h+var_1A0]
0x1800d4e04  call    ??0?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800d4e09  lea     rax, ??_7PdcWorker@CmTraceProvider@@6B@; const CmTraceProvider::PdcWorker::`vftable'
0x1800d4e10  lea     rcx, [rsp+1F0h+var_1A0]; this
0x1800d4e15  mov     [rsp+1F0h+var_1A0], rax
0x1800d4e1a  call    ?StartActivity@PdcWorker@CmTraceProvider@@QEAAXXZ; CmTraceProvider::PdcWorker::StartActivity(void)
0x1800d4e1f  mov     r13b, r15b
0x1800d4e22  lea     rsi, [rbx+28h]
0x1800d4e26  mov     r12b, r15b
0x1800d4e29  mov     rcx, rdi; SRWLock
0x1800d4e2c  mov     [rsp+1F0h+var_1B0], r15
0x1800d4e31  call    cs:__imp_AcquireSRWLockShared
0x1800d4e38  nop     dword ptr [rax+rax+00h]
0x1800d4e3d  mov     rax, [rsi]
0x1800d4e40  mov     r14d, [rbx+20h]
0x1800d4e44  mov     [rsp+1F0h+var_1B0], rax
0x1800d4e49  call    ?QueryUnbiasedInterruptTimeMs64@Csl@@YA_KXZ; Csl::QueryUnbiasedInterruptTimeMs64(void)
0x1800d4e4e  mov     r15d, [rbx+20h]
0x1800d4e52  mov     rsi, rax
0x1800d4e55  test    rdi, rdi
0x1800d4e58  jz      short loc_1800D4E69
0x1800d4e5a  mov     rcx, rdi; SRWLock
0x1800d4e5d  call    cs:__imp_ReleaseSRWLockShared
0x1800d4e64  nop     dword ptr [rax+rax+00h]
0x1800d4e69  test    r14d, r14d
0x1800d4e6c  jz      loc_1800D4F7B
0x1800d4e72  sub     esi, r15d
0x1800d4e75  xor     r15d, r15d
0x1800d4e78  mov     al, r15b
0x1800d4e7b  test    r13b, r13b
0x1800d4e7e  jnz     short loc_1800D4E8D
0x1800d4e80  cmp     esi, 7530h
0x1800d4e86  jb      short loc_1800D4E8D
0x1800d4e88  mov     al, 1
0x1800d4e8a  mov     r13b, al
0x1800d4e8d  mov     r8d, 3
0x1800d4e93  mov     [rsp+1F0h+var_1C0], 1
0x1800d4e98  lea     rdx, [rsp+1F0h+var_1C0]
0x1800d4e9d  mov     [rsp+1F0h+var_1BC], esi
0x1800d4ea1  lea     rcx, ?TryEnterCsIterateContainersCallback@Details@Core@Manager@Container@@YAXAEAVContainerObject@1234@PEAX@Z; Container::Manager::Core::Details::TryEnterCsIterateContainersCallback(Container::Manager::Core::Details::ContainerObject &,void *)
0x1800d4ea8  mov     [rsp+1F0h+var_1B8], al
0x1800d4eac  mov     [rsp+1F0h+var_1B4], 0FFFFFFFFh
0x1800d4eb4  call    ?IterateContainers@Details@Core@Manager@Container@@YAXP6AXAEAVContainerObject@1234@PEAX@Z1W4ContainerIterationFlags@1234@@Z; Container::Manager::Core::Details::IterateContainers(void (*)(Container::Manager::Core::Details::ContainerObject &,void *),void *,Container::Manager::Core::Details::ContainerIterationFlags)
0x1800d4eb9  mov     r14d, [rsp+1F0h+var_1B4]
0x1800d4ebe  mov     [rsp+1F0h+var_1D0], r14d
0x1800d4ec3  cmp     [rsp+1F0h+var_1C0], r15b
0x1800d4ec8  jnz     loc_1800D4F7E
0x1800d4ece  test    r12b, r12b
0x1800d4ed1  jnz     short loc_1800D4EE3
0x1800d4ed3  cmp     esi, 15F90h
0x1800d4ed9  jb      short loc_1800D4EE3
0x1800d4edb  call    ?ExcessiveCsEntryTime@CmTraceProvider@@SAXXZ; CmTraceProvider::ExcessiveCsEntryTime(void)
0x1800d4ee0  mov     r12b, 1
0x1800d4ee3  test    r13b, r13b
0x1800d4ee6  jnz     short loc_1800D4EEF
0x1800d4ee8  mov     eax, 7530h
0x1800d4eed  jmp     short loc_1800D4EF9
0x1800d4eef  test    r12b, r12b
0x1800d4ef2  jnz     short loc_1800D4F06
0x1800d4ef4  mov     eax, 15F90h
0x1800d4ef9  sub     eax, esi
0x1800d4efb  cmp     r14d, eax
0x1800d4efe  jb      short loc_1800D4F06
0x1800d4f00  mov     [rsp+1F0h+var_1D0], eax
0x1800d4f04  jmp     short loc_1800D4F09
0x1800d4f06  mov     rax, r14
0x1800d4f09  mov     [rsp+1F0h+var_1C8], r15
0x1800d4f0e  cmp     eax, 0FFFFFFFFh
0x1800d4f11  jz      short loc_1800D4F30
0x1800d4f13  imul    rax, 0FFFFFFFFFFFFD8F0h
0x1800d4f1a  lea     rsi, [rsp+1F0h+var_1C8]
0x1800d4f1f  mov     rcx, rax
0x1800d4f22  mov     dword ptr [rsp+1F0h+var_1C8], eax
0x1800d4f26  shr     rcx, 20h
0x1800d4f2a  mov     dword ptr [rsp+1F0h+var_1C8+4], ecx
0x1800d4f2e  jmp     short loc_1800D4F33
0x1800d4f30  mov     rsi, r15
0x1800d4f33  lea     rdx, [rsp+1F0h+var_1D0]
0x1800d4f38  lea     rcx, [rsp+1F0h+var_1A0]
0x1800d4f3d  call    ??$PdcWorkerWait@AEAK@PdcWorker@CmTraceProvider@@QEAAXAEAK@Z; CmTraceProvider::PdcWorker::PdcWorkerWait<ulong &>(ulong &)
0x1800d4f42  mov     r9, rsi
0x1800d4f45  lea     rdx, [rsp+1F0h+var_1B0]
0x1800d4f4a  lea     rsi, [rbx+28h]
0x1800d4f4e  mov     r8d, 8
0x1800d4f54  mov     rcx, rsi
0x1800d4f57  call    cs:__imp_RtlWaitOnAddress
0x1800d4f5e  nop     dword ptr [rax+rax+00h]
0x1800d4f63  lea     rdx, [rsp+1F0h+var_1D0]
0x1800d4f68  mov     [rsp+1F0h+var_1D0], eax
0x1800d4f6c  lea     rcx, [rsp+1F0h+var_1A0]
0x1800d4f71  call    ??$PdcWorkerWake@AEAJ@PdcWorker@CmTraceProvider@@QEAAXAEAJ@Z; CmTraceProvider::PdcWorker::PdcWorkerWake<long &>(long &)
0x1800d4f76  jmp     loc_1800D4E29
0x1800d4f7b  xor     r15d, r15d
0x1800d4f7e  cmp     [rbx+32h], r15b
0x1800d4f82  jnz     short loc_1800D4F86
0x1800d4f84  int     2Ch; Windows NT - assertion failure
0x1800d4f86  cmp     [rbx+31h], r15b
0x1800d4f8a  jz      short loc_1800D4FB0
0x1800d4f8c  mov     rcx, [rbx]
0x1800d4f8f  xor     edx, edx
0x1800d4f91  call    cs:__imp_PdcNotificationClientAcknowledge
0x1800d4f98  nop     dword ptr [rax+rax+00h]
0x1800d4f9d  lea     rdx, [rsp+1F0h+var_1D0]
0x1800d4fa2  mov     [rsp+1F0h+var_1D0], eax
0x1800d4fa6  lea     rcx, [rsp+1F0h+var_1A0]
0x1800d4fab  call    ??$PdcWorkerPdcAck@AEAJ@PdcWorker@CmTraceProvider@@QEAAXAEAJ@Z; CmTraceProvider::PdcWorker::PdcWorkerPdcAck<long &>(long &)
0x1800d4fb0  cmp     [rbx+32h], r15b
0x1800d4fb4  jz      short loc_1800D4FBA
0x1800d4fb6  mov     [rbx+32h], r15b
0x1800d4fba  xor     edx, edx
0x1800d4fbc  lea     rcx, [rsp+1F0h+var_1A0]
0x1800d4fc1  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800d4fc6  mov     rcx, rdi; SRWLock
0x1800d4fc9  call    cs:__imp_AcquireSRWLockExclusive
0x1800d4fd0  nop     dword ptr [rax+rax+00h]
0x1800d4fd5  call    cs:__imp_GetCurrentThreadId
0x1800d4fdc  nop     dword ptr [rax+rax+00h]
0x1800d4fe1  mov     [rbx+24h], r15d
0x1800d4fe5  mov     rcx, rdi; SRWLock
0x1800d4fe8  mov     [rdi+8], r15d
0x1800d4fec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d4ff3  nop     dword ptr [rax+rax+00h]
0x1800d4ff8  lea     rax, ??_7PdcWorker@CmTraceProvider@@6B@; const CmTraceProvider::PdcWorker::`vftable'
0x1800d4fff  lea     rcx, [rsp+1F0h+var_1A0]
0x1800d5004  mov     [rsp+1F0h+var_1A0], rax
0x1800d5009  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800d500e  lea     rcx, [rsp+1F0h+var_1A0]
0x1800d5013  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800d5018  mov     rcx, [rbp+0F0h+var_50]
0x1800d501f  xor     rcx, rsp; StackCookie
0x1800d5022  call    __security_check_cookie
0x1800d5027  add     rsp, 1B8h
0x1800d502e  pop     r15
0x1800d5030  pop     r14
0x1800d5032  pop     r13
0x1800d5034  pop     r12
0x1800d5036  pop     rdi
0x1800d5037  pop     rsi
0x1800d5038  pop     rbx
0x1800d5039  pop     rbp
0x1800d503a  retn
```
