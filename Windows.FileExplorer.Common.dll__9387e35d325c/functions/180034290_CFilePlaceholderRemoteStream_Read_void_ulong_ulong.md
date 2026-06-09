# CFilePlaceholderRemoteStream::Read(void *,ulong,ulong *)

- ea: `0x180034290`
- end: `0x1800344f1`
- name: `?Read@CFilePlaceholderRemoteStream@@UEAAJPEAXKPEAK@Z`
- size: `609`
- prototype: `__int64 __fastcall(CFilePlaceholderRemoteStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800478a0`

## callees

- `0x180004a54`
- `0x1800235fc`
- `0x180034290`
- `0x1800344f8`
- `0x18004595c`
- `0x180046f4c`
- `0x180047ccc`
- `0x180089010`

## import_xrefs

- `SHCORE!__imp_CreateWritableSharedMemoryStream` at `0x180034324`
- `SHCORE!__imp_CreateWritableSharedMemoryStream` at `0x180034324`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800343cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800344b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800343cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800344b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800342c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800342c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFilePlaceholderRemoteStream::Read(
        struct _RTL_CRITICAL_SECTION *this,
        void *a2,
        unsigned int a3,
        unsigned int *a4)
{
  unsigned __int64 v5; // r15
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  unsigned __int64 v9; // rcx
  int SpinCount; // ebx
  PSRWLOCK *v11; // rsi
  RTL_SRWLOCK *v12; // rbx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-10h] BYREF
  struct _RTL_CRITICAL_SECTION *v15; // [rsp+38h] [rbp-8h] BYREF
  PSRWLOCK v16; // [rsp+70h] [rbp+30h] BYREF
  struct _RTL_CRITICAL_SECTION_DEBUG *v17; // [rsp+88h] [rbp+48h] BYREF

  v5 = a3;
  if ( a4 )
    *a4 = 0;
  v8 = this + 2;
  EnterCriticalSection(this + 2);
  v15 = v8;
  v9 = v5;
  if ( v5 >= (char *)this[3].LockSemaphore - (char *)this[3].OwningThread )
    v9 = (char *)this[3].LockSemaphore - (char *)this[3].OwningThread;
  if ( v9 > 0xFFFFFFFF )
  {
    LODWORD(this[4].OwningThread) = -1;
    SpinCount = -2147024362;
  }
  else
  {
    LODWORD(this[4].OwningThread) = v9;
    v17 = 0;
    if ( !(_DWORD)v9
      || (Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v17),
          SpinCount = CreateWritableSharedMemoryStream(
                        LODWORD(this[4].OwningThread),
                        &GUID_0000000c_0000_0000_c000_000000000046,
                        &v17),
          SpinCount >= 0) )
    {
      SpinCount = (*(__int64 (__fastcall **)(ULONG_PTR *))(this->SpinCount + 24))(&this->SpinCount);
      if ( SpinCount >= 0 )
      {
        BYTE4(this[4].SpinCount) = LODWORD(this[4].OwningThread) < (unsigned int)v5;
        CFilePlaceholderRemoteStream::_SetIsTimeout((CFilePlaceholderRemoteStream *)this, 0);
        Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &this[5].LockCount);
        *(_QWORD *)&this[4].LockCount = a2;
        this[4].LockSemaphore = a4;
        v11 = (PSRWLOCK *)&this[5];
        v12 = (RTL_SRWLOCK *)v17;
        if ( this[5].DebugInfo != v17 )
        {
          if ( v17 )
            (*(void (__fastcall **)(struct _RTL_CRITICAL_SECTION_DEBUG *))(*(_QWORD *)&v17->Type + 8LL))(v17);
          v16 = *v11;
          *v11 = v12;
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v16);
        }
        if ( SRWLock )
          ReleaseSRWLockExclusive(SRWLock);
        if ( LODWORD(this[4].OwningThread) )
        {
          v16 = 0;
          SRWLock = (PSRWLOCK)this;
          SpinCount = Microsoft::WRL::Details::MakeAndInitialize<CFilePlaceholderCallbackCrashDetector,CFilePlaceholderCallbackCrashDetector,CFilePlaceholderRemoteStream *>(
                        &v16,
                        &SRWLock);
          if ( SpinCount >= 0 )
          {
            SpinCount = (*(__int64 (__fastcall **)(_QWORD, HANDLE, _QWORD, PSRWLOCK, PSRWLOCK))(**(_QWORD **)&this[3].LockCount
                                                                                              + 40LL))(
                          *(_QWORD *)&this[3].LockCount,
                          this[3].OwningThread,
                          LODWORD(this[4].OwningThread),
                          *v11,
                          v16);
            if ( SpinCount >= 0 )
            {
              Microsoft::WRL::ComPtr<CFilePlaceholderCallbackCrashDetector>::InternalRelease(&v16);
              SpinCount = (*(__int64 (__fastcall **)(ULONG_PTR *, __int64))(this->SpinCount + 32))(
                            &this->SpinCount,
                            1800000);
              if ( SpinCount >= 0 )
                SpinCount = this[4].SpinCount;
            }
          }
          Microsoft::WRL::ComPtr<CFilePlaceholderCallbackCrashDetector>::InternalRelease(&v16);
        }
        else
        {
          SpinCount = (*((__int64 (__fastcall **)(HANDLE *, _QWORD, PSRWLOCK))this->LockSemaphore + 6))(
                        &this->LockSemaphore,
                        0,
                        *v11);
        }
        Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v16, &this[5].LockCount);
        *(_QWORD *)&this[4].LockCount = 0;
        this[4].LockSemaphore = 0;
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&this[5]);
        if ( v16 )
          ReleaseSRWLockExclusive(v16);
      }
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v17);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v15);
  return (unsigned int)SpinCount;
}

```

## disassembly

```asm
0x180034290  mov     [rsp-28h+arg_8], rbx
0x180034295  mov     [rsp-28h+arg_10], rsi
0x18003429a  push    rbp
0x18003429b  push    rdi
0x18003429c  push    r12
0x18003429e  push    r14
0x1800342a0  push    r15
0x1800342a2  mov     rbp, rsp
0x1800342a5  sub     rsp, 40h
0x1800342a9  mov     rsi, r9
0x1800342ac  mov     r15d, r8d
0x1800342af  mov     r12, rdx
0x1800342b2  mov     rdi, rcx
0x1800342b5  test    r9, r9
0x1800342b8  jz      short loc_1800342C1
0x1800342ba  mov     dword ptr [r9], 0
0x1800342c1  lea     rbx, [rcx+50h]
0x1800342c5  mov     rcx, rbx; lpCriticalSection
0x1800342c8  call    cs:__imp_EnterCriticalSection
0x1800342ce  mov     [rbp+var_8], rbx
0x1800342d2  mov     rax, [rdi+90h]
0x1800342d9  sub     rax, [rdi+88h]
0x1800342e0  mov     rcx, r15
0x1800342e3  cmp     r15, rax
0x1800342e6  cmovnb  rcx, rax
0x1800342ea  mov     eax, 0FFFFFFFFh
0x1800342ef  cmp     rcx, rax
0x1800342f2  ja      loc_1800344C2
0x1800342f8  mov     [rdi+0B0h], ecx
0x1800342fe  mov     [rbp+arg_18], 0
0x180034306  test    ecx, ecx
0x180034308  jz      short loc_180034334
0x18003430a  lea     rcx, [rbp+arg_18]
0x18003430e  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180034313  lea     r8, [rbp+arg_18]
0x180034317  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18003431e  mov     ecx, [rdi+0B0h]
0x180034324  call    cs:__imp_CreateWritableSharedMemoryStream
0x18003432a  mov     ebx, eax
0x18003432c  test    eax, eax
0x18003432e  js      loc_1800344B7
0x180034334  lea     r14, [rdi+20h]
0x180034338  mov     rax, [r14]
0x18003433b  mov     rcx, r14
0x18003433e  mov     rax, [rax+18h]
0x180034342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034347  mov     ebx, eax
0x180034349  test    eax, eax
0x18003434b  js      loc_1800344B7
0x180034351  cmp     [rdi+0B0h], r15d
0x180034358  setb    al
0x18003435b  mov     [rdi+0C4h], al
0x180034361  xor     edx, edx; bool
0x180034363  mov     rcx, rdi; this
0x180034366  call    ?_SetIsTimeout@CFilePlaceholderRemoteStream@@AEAAX_N@Z; CFilePlaceholderRemoteStream::_SetIsTimeout(bool)
0x18003436b  lea     r15, [rdi+0D0h]
0x180034372  mov     rdx, r15
0x180034375  lea     rcx, [rbp+SRWLock]
0x180034379  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18003437e  mov     [rdi+0A8h], r12
0x180034385  mov     [rdi+0B8h], rsi
0x18003438c  lea     rsi, [rdi+0C8h]
0x180034393  mov     rbx, [rbp+arg_18]
0x180034397  cmp     [rsi], rbx
0x18003439a  jz      short loc_1800343C4
0x18003439c  test    rbx, rbx
0x18003439f  jz      short loc_1800343B1
0x1800343a1  mov     rax, [rbx]
0x1800343a4  mov     rcx, rbx
0x1800343a7  mov     rax, [rax+8]
0x1800343ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343b0  nop
0x1800343b1  mov     rax, [rsi]
0x1800343b4  mov     [rbp+arg_0], rax
0x1800343b8  mov     [rsi], rbx
0x1800343bb  lea     rcx, [rbp+arg_0]
0x1800343bf  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800343c4  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800343c8  test    rcx, rcx
0x1800343cb  jz      short loc_1800343D3
0x1800343cd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800343d3  cmp     dword ptr [rdi+0B0h], 0
0x1800343da  jbe     loc_180034466
0x1800343e0  mov     [rbp+arg_0], 0
0x1800343e8  mov     [rbp+SRWLock], rdi
0x1800343ec  lea     rdx, [rbp+SRWLock]
0x1800343f0  lea     rcx, [rbp+arg_0]
0x1800343f4  call    ??$MakeAndInitialize@VCFilePlaceholderCallbackCrashDetector@@V1@PEAVCFilePlaceholderRemoteStream@@@Details@WRL@Microsoft@@YAJPEAPEAVCFilePlaceholderCallbackCrashDetector@@$$QEAPEAVCFilePlaceholderRemoteStream@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CFilePlaceholderCallbackCrashDetector,CFilePlaceholderCallbackCrashDetector,CFilePlaceholderRemoteStream *>(CFilePlaceholderCallbackCrashDetector * *,CFilePlaceholderRemoteStream * &&)
0x1800343f9  mov     ebx, eax
0x1800343fb  test    eax, eax
0x1800343fd  js      short loc_18003445B
0x1800343ff  mov     rcx, [rdi+80h]
0x180034406  mov     rax, [rcx]
0x180034409  mov     r8d, [rdi+0B0h]
0x180034410  mov     rdx, [rbp+arg_0]
0x180034414  mov     [rsp+40h+var_20], rdx
0x180034419  mov     r9, [rsi]
0x18003441c  mov     rdx, [rdi+88h]
0x180034423  mov     rax, [rax+28h]
0x180034427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003442c  mov     ebx, eax
0x18003442e  test    eax, eax
0x180034430  js      short loc_18003445B
0x180034432  lea     rcx, [rbp+arg_0]
0x180034436  call    ?InternalRelease@?$ComPtr@VCFilePlaceholderCallbackCrashDetector@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CFilePlaceholderCallbackCrashDetector>::InternalRelease(void)
0x18003443b  mov     rax, [r14]
0x18003443e  mov     edx, 1B7740h
0x180034443  mov     rcx, r14
0x180034446  mov     rax, [rax+20h]
0x18003444a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003444f  mov     ebx, eax
0x180034451  test    eax, eax
0x180034453  js      short loc_18003445B
0x180034455  mov     ebx, [rdi+0C0h]
0x18003445b  lea     rcx, [rbp+arg_0]
0x18003445f  call    ?InternalRelease@?$ComPtr@VCFilePlaceholderCallbackCrashDetector@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CFilePlaceholderCallbackCrashDetector>::InternalRelease(void)
0x180034464  jmp     short loc_18003447D
0x180034466  lea     rcx, [rdi+18h]
0x18003446a  mov     rax, [rcx]
0x18003446d  mov     r8, [rsi]
0x180034470  xor     edx, edx
0x180034472  mov     rax, [rax+30h]
0x180034476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003447b  mov     ebx, eax
0x18003447d  mov     rdx, r15
0x180034480  lea     rcx, [rbp+arg_0]
0x180034484  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180034489  mov     qword ptr [rdi+0A8h], 0
0x180034494  mov     qword ptr [rdi+0B8h], 0
0x18003449f  mov     rcx, rsi
0x1800344a2  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800344a7  mov     rcx, [rbp+arg_0]; SRWLock
0x1800344ab  test    rcx, rcx
0x1800344ae  jz      short loc_1800344B7
0x1800344b0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800344b6  nop
0x1800344b7  lea     rcx, [rbp+arg_18]
0x1800344bb  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800344c0  jmp     short loc_1800344CD
0x1800344c2  mov     [rdi+0B0h], eax
0x1800344c8  mov     ebx, 80070216h
0x1800344cd  lea     rcx, [rbp+var_8]; this
0x1800344d1  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800344d6  mov     eax, ebx
0x1800344d8  lea     r11, [rsp+40h+var_s0]
0x1800344dd  mov     rbx, [r11+38h]
0x1800344e1  mov     rsi, [r11+40h]
0x1800344e5  mov     rsp, r11
0x1800344e8  pop     r15
0x1800344ea  pop     r14
0x1800344ec  pop     r12
0x1800344ee  pop     rdi
0x1800344ef  pop     rbp
0x1800344f0  retn
```
