# CallAudioRouting::_PauseRecordingWithHresult(uint)

- ea: `0x180068d60`
- end: `0x1800690ac`
- name: `?_PauseRecordingWithHresult@CallAudioRouting@@AEAAJI@Z`
- size: `844`
- prototype: `__int64 __fastcall(CallAudioRouting *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180068cc0`

## callees

- `0x180006e94`
- `0x180010664`
- `0x1800107d8`
- `0x180057ce8`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x180064dac`
- `0x180068d60`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068dd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068dd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068e19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068e48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068e19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068e48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068d8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068daf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068d8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068daf`

## string_xrefs

- `0x180068da3`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180068e06`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180068e82`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180068f18`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180068fd9`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_PauseRecordingWithHresult(CallAudioRouting *this, unsigned int a2)
{
  __int64 v4; // rcx
  BackTraceCollection *v5; // rcx
  unsigned int v6; // esi
  __int64 v7; // rbx
  __int64 v8; // rdi
  int v9; // eax
  BackTraceCollection *v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 v12; // rdi
  int v13; // eax
  BackTraceCollection *v14; // rcx
  __int64 v15; // rcx
  struct CallAudioRouting::CellularAudioState *v16; // r14
  int v17; // eax
  BackTraceCollection *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  struct CallAudioRouting::CellularAudioState *v22; // [rsp+30h] [rbp-40h] BYREF
  volatile __int32 *v23; // [rsp+38h] [rbp-38h] BYREF
  CallAudioRouting *v24; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v25; // [rsp+48h] [rbp-28h]
  unsigned int v26; // [rsp+50h] [rbp-20h]
  __int64 v27; // [rsp+58h] [rbp-18h] BYREF
  __int64 v28; // [rsp+60h] [rbp-10h] BYREF

  if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2276);
    if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(&v23, (__int64)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v22 = 0;
  if ( !(unsigned int)CallAudioRouting::_FindCellularState(this, a2, &v22) )
  {
    v6 = -2147023728;
    BackTraceCollection::Capture(v5, -2147023728);
    Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2286);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    goto LABEL_37;
  }
  v7 = 0;
  v8 = *((_QWORD *)v22 + 8);
  if ( v8 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(*((_QWORD *)v22 + 8));
    v7 = v8;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v27 = 0;
  v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v7)(
         v7,
         &GUID_6369c758_5644_41e2_97af_8ef56a25e225,
         &v27);
  v6 = v9;
  if ( v9 < 0 )
  {
    BackTraceCollection::Capture(v10, v9);
    Log_HREvent_17(v6, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2294);
LABEL_10:
    v11 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    goto LABEL_37;
  }
  v12 = ((unsigned __int64)this + 8) & -(__int64)(this != 0);
  if ( v12 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v12 + 8LL))(((unsigned __int64)this + 8) & -(__int64)(this != 0));
  v28 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v27 + 48LL))(v27, 0, &v28);
  v6 = v13;
  if ( v13 < 0 )
  {
    BackTraceCollection::Capture(v14, v13);
    Log_HREvent_17(v6, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2300);
LABEL_17:
    v15 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    if ( v12 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_10;
  }
  v22 = 0;
  v24 = this;
  v25 = ((unsigned __int64)this + 8) & -(__int64)(this != 0);
  if ( v12 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v12 + 8LL))(((unsigned __int64)this + 8) & -(__int64)(this != 0));
  v26 = a2;
  Microsoft::WRL::Callback_Windows::Foundation::IAsyncActionCompletedHandler__lambda_419b406f431aa9e6bf396ae83283819c___(
    &v22,
    &v24);
  if ( v25 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v25 + 16LL))(v25);
  v16 = v22;
  v17 = (*(__int64 (__fastcall **)(__int64, struct CallAudioRouting::CellularAudioState *))(*(_QWORD *)v28 + 48LL))(
          v28,
          v22);
  v6 = v17;
  if ( v17 < 0 )
  {
    BackTraceCollection::Capture(v18, v17);
    Log_HREvent_17(v6, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2317);
    if ( v16 )
      (*(void (__fastcall **)(struct CallAudioRouting::CellularAudioState *))(*(_QWORD *)v16 + 16LL))(v16);
    goto LABEL_17;
  }
  if ( v16 )
    (*(void (__fastcall **)(struct CallAudioRouting::CellularAudioState *))(*(_QWORD *)v16 + 16LL))(v16);
  v19 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  if ( v12 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v12 + 16LL))(v12);
  v20 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v6 = 0;
LABEL_37:
  utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>(&v23);
  return v6;
}

```

## disassembly

```asm
0x180068d60  mov     [rsp-28h+arg_8], rbx
0x180068d65  mov     [rsp-28h+arg_10], rsi
0x180068d6a  push    rbp
0x180068d6b  push    rdi
0x180068d6c  push    r12
0x180068d6e  push    r14
0x180068d70  push    r15
0x180068d72  mov     rbp, rsp
0x180068d75  sub     rsp, 70h
0x180068d79  mov     rax, cs:__security_cookie
0x180068d80  xor     rax, rsp
0x180068d83  mov     [rbp+var_8], rax
0x180068d87  mov     r12d, edx
0x180068d8a  mov     r14, rcx
0x180068d8d  call    cs:__imp_GetCurrentThreadId
0x180068d93  lea     r15, [r14+58h]
0x180068d97  cmp     [r15+10h], eax
0x180068d9b  jnz     short loc_180068DC0
0x180068d9d  mov     r8d, 8E4h
0x180068da3  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180068daa  call    Log_AssertionEvent_9
0x180068daf  call    cs:__imp_GetCurrentThreadId
0x180068db5  cmp     [r14+68h], eax
0x180068db9  jnz     short loc_180068DC0
0x180068dbb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180068dc0  lea     rdx, [r14+80h]
0x180068dc7  lea     rcx, [rbp+var_38]
0x180068dcb  call    ??0?$lock_guard@VThreadCheck@@@utl@@QEAA@AEAVThreadCheck@@@Z; utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(ThreadCheck &)
0x180068dd0  mov     rcx, r15; lpCriticalSection
0x180068dd3  call    cs:__imp_EnterCriticalSection
0x180068dd9  lea     r8, [rbp+var_40]; struct CallAudioRouting::CellularAudioState **
0x180068ddd  mov     [rbp+var_40], 0
0x180068de5  mov     edx, r12d; unsigned int
0x180068de8  mov     rcx, r14; this
0x180068deb  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x180068df0  test    eax, eax
0x180068df2  jnz     short loc_180068E24
0x180068df4  mov     esi, 80070490h
0x180068df9  mov     edx, esi; int
0x180068dfb  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180068e00  mov     r9d, 8EEh
0x180068e06  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180068e0d  xor     edx, edx
0x180068e0f  mov     ecx, esi
0x180068e11  call    Log_HREvent_17
0x180068e16  mov     rcx, r15; lpCriticalSection
0x180068e19  call    cs:__imp_LeaveCriticalSection
0x180068e1f  jmp     loc_18006907C
0x180068e24  mov     rax, [rbp+var_40]
0x180068e28  xor     ebx, ebx
0x180068e2a  mov     rdi, [rax+40h]
0x180068e2e  test    rdi, rdi
0x180068e31  jz      short loc_180068E45
0x180068e33  mov     rax, [rdi]
0x180068e36  mov     rcx, rdi
0x180068e39  mov     rax, [rax+8]
0x180068e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068e42  mov     rbx, rdi
0x180068e45  mov     rcx, r15; lpCriticalSection
0x180068e48  call    cs:__imp_LeaveCriticalSection
0x180068e4e  mov     [rbp+var_18], 0
0x180068e56  lea     r8, [rbp+var_18]
0x180068e5a  mov     rax, [rbx]
0x180068e5d  lea     rdx, _GUID_6369c758_5644_41e2_97af_8ef56a25e225
0x180068e64  mov     rcx, rbx
0x180068e67  mov     rax, [rax]
0x180068e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068e6f  mov     esi, eax
0x180068e71  test    eax, eax
0x180068e73  jns     short loc_180068EC6
0x180068e75  mov     edx, eax; int
0x180068e77  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180068e7c  mov     r9d, 8F6h
0x180068e82  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180068e89  mov     edx, 1
0x180068e8e  mov     ecx, esi
0x180068e90  call    Log_HREvent_17
0x180068e95  mov     rcx, [rbp+var_18]
0x180068e99  test    rcx, rcx
0x180068e9c  jz      short loc_180068EB2
0x180068e9e  mov     [rbp+var_18], 0
0x180068ea6  mov     rax, [rcx]
0x180068ea9  mov     rax, [rax+10h]
0x180068ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068eb2  mov     rax, [rbx]
0x180068eb5  mov     rcx, rbx
0x180068eb8  mov     rax, [rax+10h]
0x180068ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ec1  jmp     loc_18006907C
0x180068ec6  mov     rax, r14
0x180068ec9  lea     rcx, [r14+8]
0x180068ecd  neg     rax
0x180068ed0  sbb     rdi, rdi
0x180068ed3  and     rdi, rcx
0x180068ed6  jz      short loc_180068EE7
0x180068ed8  mov     rax, [rdi]
0x180068edb  mov     rcx, rdi
0x180068ede  mov     rax, [rax+8]
0x180068ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ee7  mov     rcx, [rbp+var_18]
0x180068eeb  lea     r8, [rbp+var_10]
0x180068eef  mov     [rbp+var_10], 0
0x180068ef7  xor     edx, edx
0x180068ef9  mov     rax, [rcx]
0x180068efc  mov     rax, [rax+30h]
0x180068f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f05  mov     esi, eax
0x180068f07  test    eax, eax
0x180068f09  jns     short loc_180068F65
0x180068f0b  mov     edx, eax; int
0x180068f0d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180068f12  mov     r9d, 8FCh
0x180068f18  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180068f1f  mov     edx, 1
0x180068f24  mov     ecx, esi
0x180068f26  call    Log_HREvent_17
0x180068f2b  mov     rcx, [rbp+var_10]
0x180068f2f  test    rcx, rcx
0x180068f32  jz      short loc_180068F48
0x180068f34  mov     [rbp+var_10], 0
0x180068f3c  mov     rax, [rcx]
0x180068f3f  mov     rax, [rax+10h]
0x180068f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f48  test    rdi, rdi
0x180068f4b  jz      loc_180068E95
0x180068f51  mov     rax, [rdi]
0x180068f54  mov     rcx, rdi
0x180068f57  mov     rax, [rax+10h]
0x180068f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f60  jmp     loc_180068E95
0x180068f65  mov     [rbp+var_40], 0
0x180068f6d  mov     [rbp+var_30], r14
0x180068f71  mov     [rbp+var_28], rdi
0x180068f75  test    rdi, rdi
0x180068f78  jz      short loc_180068F89
0x180068f7a  mov     rax, [rdi]
0x180068f7d  mov     rcx, rdi
0x180068f80  mov     rax, [rax+8]
0x180068f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f89  lea     rdx, [rbp+var_30]
0x180068f8d  mov     [rbp+var_20], r12d
0x180068f91  lea     rcx, [rbp+var_40]
0x180068f95  call    Microsoft__WRL__Callback_Windows__Foundation__IAsyncActionCompletedHandler__lambda_419b406f431aa9e6bf396ae83283819c___
0x180068f9a  mov     rcx, [rbp+var_28]
0x180068f9e  test    rcx, rcx
0x180068fa1  jz      short loc_180068FAF
0x180068fa3  mov     rax, [rcx]
0x180068fa6  mov     rax, [rax+10h]
0x180068faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068faf  mov     rcx, [rbp+var_10]
0x180068fb3  mov     r14, [rbp+var_40]
0x180068fb7  mov     rdx, r14
0x180068fba  mov     rax, [rcx]
0x180068fbd  mov     rax, [rax+30h]
0x180068fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068fc6  mov     esi, eax
0x180068fc8  test    eax, eax
0x180068fca  jns     short loc_180069009
0x180068fcc  mov     edx, eax; int
0x180068fce  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180068fd3  mov     r9d, 90Dh
0x180068fd9  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180068fe0  mov     edx, 1
0x180068fe5  mov     ecx, esi
0x180068fe7  call    Log_HREvent_17
0x180068fec  test    r14, r14
0x180068fef  jz      loc_180068F2B
0x180068ff5  mov     rax, [r14]
0x180068ff8  mov     rcx, r14
0x180068ffb  mov     rax, [rax+10h]
0x180068fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069004  jmp     loc_180068F2B
0x180069009  test    r14, r14
0x18006900c  jz      short loc_18006901D
0x18006900e  mov     rax, [r14]
0x180069011  mov     rcx, r14
0x180069014  mov     rax, [rax+10h]
0x180069018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006901d  mov     rcx, [rbp+var_10]
0x180069021  test    rcx, rcx
0x180069024  jz      short loc_18006903A
0x180069026  mov     [rbp+var_10], 0
0x18006902e  mov     rax, [rcx]
0x180069031  mov     rax, [rax+10h]
0x180069035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006903a  test    rdi, rdi
0x18006903d  jz      short loc_18006904E
0x18006903f  mov     rax, [rdi]
0x180069042  mov     rcx, rdi
0x180069045  mov     rax, [rax+10h]
0x180069049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006904e  mov     rcx, [rbp+var_18]
0x180069052  test    rcx, rcx
0x180069055  jz      short loc_18006906B
0x180069057  mov     [rbp+var_18], 0
0x18006905f  mov     rax, [rcx]
0x180069062  mov     rax, [rax+10h]
0x180069066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006906b  mov     rax, [rbx]
0x18006906e  mov     rcx, rbx
0x180069071  mov     rax, [rax+10h]
0x180069075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006907a  xor     esi, esi
0x18006907c  lea     rcx, [rbp+var_38]
0x180069080  call    ??1?$lock_guard@VThreadCheck@@@utl@@QEAA@XZ; utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>(void)
0x180069085  mov     eax, esi
0x180069087  mov     rcx, [rbp+var_8]
0x18006908b  xor     rcx, rsp; StackCookie
0x18006908e  call    __security_check_cookie
0x180069093  lea     r11, [rsp+70h+var_s0]
0x180069098  mov     rbx, [r11+38h]
0x18006909c  mov     rsi, [r11+40h]
0x1800690a0  mov     rsp, r11
0x1800690a3  pop     r15
0x1800690a5  pop     r14
0x1800690a7  pop     r12
0x1800690a9  pop     rdi
0x1800690aa  pop     rbp
0x1800690ab  retn
```
