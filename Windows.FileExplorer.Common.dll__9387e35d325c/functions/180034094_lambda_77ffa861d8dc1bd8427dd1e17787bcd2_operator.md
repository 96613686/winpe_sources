# _lambda_77ffa861d8dc1bd8427dd1e17787bcd2_::operator()

- ea: `0x180034094`
- end: `0x180034282`
- name: `_lambda_77ffa861d8dc1bd8427dd1e17787bcd2_::operator()`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043390`

## callees

- `0x180004a54`
- `0x1800077c8`
- `0x180013200`
- `0x180031c78`
- `0x180034094`
- `0x1800344f8`
- `0x18003ce28`
- `0x18003d008`
- `0x18003d2d0`
- `0x180089010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800341b2`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800341b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800340af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800340af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034194`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034194`

## string_xrefs

- `0x1800341f8`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`
- `0x18003425a`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_77ffa861d8dc1bd8427dd1e17787bcd2_::operator()(struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int DebugInfo; // r8d
  int LockSemaphore_high; // edx
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  __int64 v6; // rax
  __int64 *v7; // rax
  __int64 v8; // r14
  DWORD CurrentThreadId; // eax
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-30h]
  _BYTE v13[32]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  __int64 v15; // [rsp+80h] [rbp+30h] BYREF
  PRTL_CRITICAL_SECTION_DEBUG v16; // [rsp+88h] [rbp+38h] BYREF
  struct _RTL_CRITICAL_SECTION *v17; // [rsp+90h] [rbp+40h] BYREF
  struct _RTL_CRITICAL_SECTION *v18; // [rsp+98h] [rbp+48h] BYREF

  v2 = *a1 + 2;
  EnterCriticalSection(v2);
  v18 = v2;
  if ( ((*a1)[4].SpinCount & 0x1000000000LL) != 0 || (DebugInfo = (int)a1[1]->DebugInfo, (DebugInfo & 2) == 0) )
  {
    v10 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27E,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
      (const char *)0x80070057LL,
      v12);
    goto LABEL_17;
  }
  LockSemaphore_high = HIDWORD((*a1)[3].LockSemaphore);
  LODWORD(v15) = LockSemaphore_high & ~DebugInfo | DebugInfo & (__int64)a1[2]->DebugInfo;
  if ( LockSemaphore_high == (_DWORD)v15 )
  {
    (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD))(*(_QWORD *)a1[3]->DebugInfo + 40LL))(
      a1[3]->DebugInfo,
      0);
LABEL_15:
    v10 = 0;
    goto LABEL_17;
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v18);
  v5 = *a1;
  v17 = *a1;
  Microsoft::WRL::ComPtr<CFilePlaceholder>::InternalAddRef(&v17);
  v16 = a1[3]->DebugInfo;
  Microsoft::WRL::ComPtr<CFilePlaceholder>::InternalAddRef(&v16);
  v6 = lambda_5d56487974500167389e3f00b1ae9cd4_::_lambda_5d56487974500167389e3f00b1ae9cd4_(
         (unsigned int)v13,
         (unsigned int)*a1,
         (unsigned int)&v17,
         (unsigned int)&v15,
         (__int64)a1[1],
         (__int64)&v16);
  v7 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_5d56487974500167389e3f00b1ae9cd4_____lambda_5d56487974500167389e3f00b1ae9cd4___(
                    &v15,
                    v6);
  v8 = *v7;
  *v7 = 0;
  if ( v15 )
  {
    v15 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v10 = SHTaskPoolQueueTask(0, 0, CurrentThreadId, 0);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  lambda_5d56487974500167389e3f00b1ae9cd4_::__lambda_5d56487974500167389e3f00b1ae9cd4_(v13);
  if ( (v10 & 0x80000000) == 0 )
  {
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v16);
    if ( v5 )
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v5->DebugInfo->ProcessLocksList.Flink)(v5);
    goto LABEL_15;
  }
  (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD))(*(_QWORD *)a1[3]->DebugInfo + 40LL))(
    a1[3]->DebugInfo,
    v10);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2D4,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
    (const char *)v10,
    v8);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v16);
  if ( v5 )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v5->DebugInfo->ProcessLocksList.Flink)(v5);
LABEL_17:
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v18);
  return v10;
}

```

## disassembly

```asm
0x180034094  push    rbp
0x180034096  push    rbx
0x180034097  push    rsi
0x180034098  push    rdi
0x180034099  push    r14
0x18003409b  mov     rbp, rsp
0x18003409e  sub     rsp, 50h
0x1800340a2  mov     rdi, rcx
0x1800340a5  mov     rbx, [rcx]
0x1800340a8  add     rbx, 50h ; 'P'
0x1800340ac  mov     rcx, rbx; lpCriticalSection
0x1800340af  call    cs:__imp_EnterCriticalSection
0x1800340b5  mov     [rbp+arg_18], rbx
0x1800340b9  mov     rdx, [rdi]
0x1800340bc  test    byte ptr [rdx+0C4h], 10h
0x1800340c3  jnz     loc_18003424E
0x1800340c9  mov     rax, [rdi+8]
0x1800340cd  mov     r8d, [rax]
0x1800340d0  test    r8b, 2
0x1800340d4  jz      loc_18003424E
0x1800340da  mov     edx, [rdx+94h]
0x1800340e0  mov     rax, [rdi+10h]
0x1800340e4  mov     ecx, [rax]
0x1800340e6  and     ecx, r8d
0x1800340e9  not     r8d
0x1800340ec  and     r8d, edx
0x1800340ef  or      ecx, r8d
0x1800340f2  mov     dword ptr [rbp+arg_0], ecx
0x1800340f5  cmp     edx, ecx
0x1800340f7  jnz     short loc_180034113
0x1800340f9  mov     rax, [rdi+18h]
0x1800340fd  mov     rcx, [rax]
0x180034100  mov     rax, [rcx]
0x180034103  xor     edx, edx
0x180034105  mov     rax, [rax+28h]
0x180034109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003410e  jmp     loc_18003424A
0x180034113  lea     rcx, [rbp+arg_18]; this
0x180034117  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003411c  mov     rsi, [rdi]
0x18003411f  mov     [rbp+arg_10], rsi
0x180034123  lea     rcx, [rbp+arg_10]
0x180034127  call    ?InternalAddRef@?$ComPtr@VCFilePlaceholder@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CFilePlaceholder>::InternalAddRef(void)
0x18003412c  nop
0x18003412d  mov     rax, [rdi+18h]
0x180034131  mov     rcx, [rax]
0x180034134  mov     [rbp+arg_8], rcx
0x180034138  lea     rcx, [rbp+arg_8]
0x18003413c  call    ?InternalAddRef@?$ComPtr@VCFilePlaceholder@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CFilePlaceholder>::InternalAddRef(void)
0x180034141  nop
0x180034142  lea     rax, [rbp+arg_8]
0x180034146  mov     [rsp+50h+var_28], rax
0x18003414b  mov     rax, [rdi+8]
0x18003414f  mov     qword ptr [rsp+50h+var_30], rax
0x180034154  lea     r9, [rbp+arg_0]
0x180034158  lea     r8, [rbp+arg_10]
0x18003415c  mov     rdx, [rdi]
0x18003415f  lea     rcx, [rbp+var_20]
0x180034163  call    _lambda_5d56487974500167389e3f00b1ae9cd4____lambda_5d56487974500167389e3f00b1ae9cd4_
0x180034168  mov     rdx, rax
0x18003416b  lea     rcx, [rbp+arg_0]
0x18003416f  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_5d56487974500167389e3f00b1ae9cd4_____lambda_5d56487974500167389e3f00b1ae9cd4___
0x180034174  mov     r14, [rax]
0x180034177  mov     qword ptr [rax], 0
0x18003417e  mov     rcx, [rbp+arg_0]
0x180034182  test    rcx, rcx
0x180034185  jz      short loc_180034194
0x180034187  mov     [rbp+arg_0], 0
0x18003418f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180034194  call    cs:__imp_GetCurrentThreadId
0x18003419a  mov     [rsp+50h+var_28], 0
0x1800341a3  mov     qword ptr [rsp+50h+var_30], r14; int
0x1800341a8  xor     r9d, r9d
0x1800341ab  mov     r8d, eax
0x1800341ae  xor     edx, edx
0x1800341b0  xor     ecx, ecx
0x1800341b2  call    cs:__imp_SHTaskPoolQueueTask
0x1800341b8  mov     ebx, eax
0x1800341ba  test    r14, r14
0x1800341bd  jz      short loc_1800341CF
0x1800341bf  mov     rdx, [r14]
0x1800341c2  mov     rcx, r14
0x1800341c5  mov     rax, [rdx+10h]
0x1800341c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341ce  nop
0x1800341cf  lea     rcx, [rbp+var_20]
0x1800341d3  call    _lambda_5d56487974500167389e3f00b1ae9cd4_____lambda_5d56487974500167389e3f00b1ae9cd4_
0x1800341d8  test    ebx, ebx
0x1800341da  jns     short loc_18003422B
0x1800341dc  mov     rax, [rdi+18h]
0x1800341e0  mov     rcx, [rax]
0x1800341e3  mov     rax, [rcx]
0x1800341e6  mov     edx, ebx
0x1800341e8  mov     rax, [rax+28h]
0x1800341ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341f1  mov     rcx, [rbp+28h]; this
0x1800341f5  mov     r9d, ebx; char *
0x1800341f8  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800341ff  mov     edx, 2D4h; void *
0x180034204  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034209  nop
0x18003420a  lea     rcx, [rbp+arg_8]
0x18003420e  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180034213  nop
0x180034214  test    rsi, rsi
0x180034217  jz      short loc_180034229
0x180034219  mov     rax, [rsi]
0x18003421c  mov     rcx, rsi
0x18003421f  mov     rax, [rax+10h]
0x180034223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034228  nop
0x180034229  jmp     short loc_18003426C
0x18003422b  lea     rcx, [rbp+arg_8]
0x18003422f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180034234  nop
0x180034235  test    rsi, rsi
0x180034238  jz      short loc_18003424A
0x18003423a  mov     rax, [rsi]
0x18003423d  mov     rcx, rsi
0x180034240  mov     rax, [rax+10h]
0x180034244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034249  nop
0x18003424a  xor     ebx, ebx
0x18003424c  jmp     short loc_18003426C
0x18003424e  mov     rcx, [rbp+28h]; this
0x180034252  mov     ebx, 80070057h
0x180034257  mov     r9d, ebx; char *
0x18003425a  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x180034261  mov     edx, 27Eh; void *
0x180034266  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003426b  nop
0x18003426c  lea     rcx, [rbp+arg_18]; this
0x180034270  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180034275  mov     eax, ebx
0x180034277  add     rsp, 50h
0x18003427b  pop     r14
0x18003427d  pop     rdi
0x18003427e  pop     rsi
0x18003427f  pop     rbx
0x180034280  pop     rbp
0x180034281  retn
```
