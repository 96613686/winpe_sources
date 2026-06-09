# TileSession::RaiseAppChangedCallback(ushort const *)

- ea: `0x180066ec8`
- end: `0x180067210`
- name: `?RaiseAppChangedCallback@TileSession@@QEAAJPEBG@Z`
- size: `840`
- prototype: `__int64 __fastcall(TileSession *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180066eb0`

## callees

- `0x180004e38`
- `0x180011618`
- `0x18002ee38`
- `0x180066ec8`
- `0x180067d58`
- `0x180067de0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066ef3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066ef3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066fd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006718e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006719c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066fd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006718e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006719c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066f11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066fe0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066f11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066fe0`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180066fb0`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180067070`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180067148`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180066fb0`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180067070`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180067148`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180066f2e`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180066ff7`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180066f2e`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180066ff7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180066f61`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18006702a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180066f61`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18006702a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180066fc4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180067084`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18006715d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180066fc4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180067084`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18006715d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall TileSession::RaiseAppChangedCallback(TileSession *this, const unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v7; // eax
  int v8; // ebx
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v11; // rcx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rcx
  int v16; // eax
  DWORD DueTime; // [rsp+20h] [rbp-40h]
  DWORD Parameter; // [rsp+40h] [rbp-20h] BYREF
  char v19; // [rsp+44h] [rbp-1Ch]
  HRESULT v20; // [rsp+48h] [rbp-18h]
  void *phNewTimer[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+A0h] [rbp+40h] BYREF
  __int64 v24; // [rsp+B0h] [rbp+50h] BYREF
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+B8h] [rbp+58h]

  v23 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v25 = v4;
  if ( *((_DWORD *)this + 16) && *((_QWORD *)this + 10) )
  {
    Parameter = GetCurrentThreadId();
    v19 = 0;
    phNewTimer[0] = 0;
    v20 = CoEnableCallCancellation(0);
    if ( v20 >= 0 )
      CreateTimerQueueTimer(phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x2710u, 0x3E8u, 0);
    v5 = *((_QWORD *)this + 10);
    v6 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v5 + 40LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    v7 = v6(v5, *((unsigned int *)this + 16), &GUID_e716b283_6be7_4e6f_a88f_1cde47d5e355, &v23);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\tilesession.cpp",
        (const char *)(unsigned int)v7,
        DueTime);
      if ( v20 >= 0 )
      {
        v20 = -2147467259;
        CoDisableCallCancellation(0);
        if ( phNewTimer[0] )
        {
          DeleteTimerQueueTimer(0, phNewTimer[0], (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          phNewTimer[0] = 0;
        }
      }
      if ( v4 )
        LeaveCriticalSection(v4);
      v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
      if ( v23 )
      {
        v23 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v15)[2])(v15);
      }
      return (unsigned int)v8;
    }
    if ( v20 >= 0 )
    {
      v20 = -2147467259;
      CoDisableCallCancellation(0);
      if ( phNewTimer[0] )
      {
        DeleteTimerQueueTimer(0, phNewTimer[0], (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        phNewTimer[0] = 0;
      }
    }
    if ( v4 )
      LeaveCriticalSection(v4);
    v24 = 0;
    Parameter = GetCurrentThreadId();
    v19 = 0;
    v20 = -2147467259;
    phNewTimer[0] = 0;
    v20 = CoEnableCallCancellation(0);
    if ( v20 >= 0 )
      CreateTimerQueueTimer(phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x2710u, 0x3E8u, 0);
    v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
    v10 = **v23;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v8 = v10(v9, &GUID_78d3e6f2_0c4f_45a5_bca6_59ec8a03e08f, &v24);
    if ( v8 < 0 )
    {
      if ( v20 >= 0 )
      {
        v20 = -2147467259;
        CoDisableCallCancellation(0);
        if ( phNewTimer[0] )
        {
          DeleteTimerQueueTimer(0, phNewTimer[0], (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          phNewTimer[0] = 0;
        }
      }
      v11 = v24;
      if ( v24 )
      {
        v24 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
      if ( v23 )
      {
        v23 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v12)[2])(v12);
      }
      return (unsigned int)v8;
    }
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
    CRPCTimeout::CRPCTimeout((CRPCTimeout *)&Parameter, 0x2710u);
    v16 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v24 + 24LL))(v24, a2);
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xFE,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\tilesession.cpp",
        (const char *)(unsigned int)v16,
        DueTime);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\tilesession.cpp",
      (const char *)0x80004005LL,
      DueTime);
    if ( v4 )
      LeaveCriticalSection(v4);
    v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
    if ( v23 )
    {
      v23 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v14)[2])(v14);
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180066ec8  mov     [rsp-38h+arg_8], rbx
0x180066ecd  push    rbp
0x180066ece  push    rsi
0x180066ecf  push    rdi
0x180066ed0  push    r12
0x180066ed2  push    r13
0x180066ed4  push    r14
0x180066ed6  push    r15
0x180066ed8  mov     rbp, rsp
0x180066edb  sub     rsp, 60h
0x180066edf  mov     r12, rdx
0x180066ee2  mov     r15, rcx
0x180066ee5  xor     r13d, r13d
0x180066ee8  mov     [rbp+arg_0], r13
0x180066eec  lea     rsi, [rcx+18h]
0x180066ef0  mov     rcx, rsi; lpCriticalSection
0x180066ef3  call    cs:__imp_EnterCriticalSection
0x180066ef9  mov     [rbp+arg_18], rsi
0x180066efd  cmp     [r15+40h], r13d
0x180066f01  jz      loc_1800670DC
0x180066f07  cmp     [r15+50h], r13
0x180066f0b  jz      loc_1800670DC
0x180066f11  call    cs:__imp_GetCurrentThreadId
0x180066f17  mov     [rbp+Parameter], eax
0x180066f1a  mov     [rbp+var_1C], r13b
0x180066f1e  mov     r14d, 80004005h
0x180066f24  mov     [rbp+var_18], r14d
0x180066f28  mov     [rbp+phNewTimer], r13
0x180066f2c  xor     ecx, ecx; pReserved
0x180066f2e  call    cs:__imp_CoEnableCallCancellation
0x180066f34  mov     [rbp+var_18], eax
0x180066f37  test    eax, eax
0x180066f39  js      short loc_180066F68
0x180066f3b  mov     [rsp+60h+Flags], r13d; Flags
0x180066f40  mov     [rsp+60h+Period], 3E8h; Period
0x180066f48  mov     [rsp+60h+DueTime], 2710h; int
0x180066f50  lea     r9, [rbp+Parameter]; Parameter
0x180066f54  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x180066f5b  xor     edx, edx; TimerQueue
0x180066f5d  lea     rcx, [rbp+phNewTimer]; phNewTimer
0x180066f61  call    cs:__imp_CreateTimerQueueTimer
0x180066f67  nop
0x180066f68  mov     rdi, [r15+50h]
0x180066f6c  mov     rax, [rdi]
0x180066f6f  mov     rbx, [rax+28h]
0x180066f73  lea     rcx, [rbp+arg_0]
0x180066f77  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180066f7c  lea     r9, [rbp+arg_0]
0x180066f80  lea     r8, _GUID_e716b283_6be7_4e6f_a88f_1cde47d5e355
0x180066f87  mov     edx, [r15+40h]
0x180066f8b  mov     rcx, rdi
0x180066f8e  mov     rax, rbx
0x180066f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f96  mov     ebx, eax
0x180066f98  test    eax, eax
0x180066f9a  js      loc_180067123
0x180066fa0  or      r15, 0FFFFFFFFFFFFFFFFh
0x180066fa4  cmp     [rbp+var_18], r13d
0x180066fa8  jl      short loc_180066FCE
0x180066faa  mov     [rbp+var_18], r14d
0x180066fae  xor     ecx, ecx; pReserved
0x180066fb0  call    cs:__imp_CoDisableCallCancellation
0x180066fb6  mov     rdx, [rbp+phNewTimer]; Timer
0x180066fba  test    rdx, rdx
0x180066fbd  jz      short loc_180066FCE
0x180066fbf  mov     r8, r15; CompletionEvent
0x180066fc2  xor     ecx, ecx; TimerQueue
0x180066fc4  call    cs:__imp_DeleteTimerQueueTimer
0x180066fca  mov     [rbp+phNewTimer], r13
0x180066fce  test    rsi, rsi
0x180066fd1  jz      short loc_180066FDC
0x180066fd3  mov     rcx, rsi; lpCriticalSection
0x180066fd6  call    cs:__imp_LeaveCriticalSection
0x180066fdc  mov     [rbp+arg_10], r13
0x180066fe0  call    cs:__imp_GetCurrentThreadId
0x180066fe6  mov     [rbp+Parameter], eax
0x180066fe9  mov     [rbp+var_1C], r13b
0x180066fed  mov     [rbp+var_18], r14d
0x180066ff1  mov     [rbp+phNewTimer], r13
0x180066ff5  xor     ecx, ecx; pReserved
0x180066ff7  call    cs:__imp_CoEnableCallCancellation
0x180066ffd  mov     [rbp+var_18], eax
0x180067000  test    eax, eax
0x180067002  js      short loc_180067031
0x180067004  mov     [rsp+60h+Flags], r13d; Flags
0x180067009  mov     [rsp+60h+Period], 3E8h; Period
0x180067011  mov     [rsp+60h+DueTime], 2710h; int
0x180067019  lea     r9, [rbp+Parameter]; Parameter
0x18006701d  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x180067024  xor     edx, edx; TimerQueue
0x180067026  lea     rcx, [rbp+phNewTimer]; phNewTimer
0x18006702a  call    cs:__imp_CreateTimerQueueTimer
0x180067030  nop
0x180067031  mov     rbx, [rbp+arg_0]
0x180067035  mov     rax, [rbx]
0x180067038  mov     rdi, [rax]
0x18006703b  lea     rcx, [rbp+arg_10]
0x18006703f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067044  lea     r8, [rbp+arg_10]
0x180067048  lea     rdx, _GUID_78d3e6f2_0c4f_45a5_bca6_59ec8a03e08f
0x18006704f  mov     rcx, rbx
0x180067052  mov     rax, rdi
0x180067055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006705a  mov     ebx, eax
0x18006705c  test    eax, eax
0x18006705e  jns     loc_1800671A4
0x180067064  cmp     [rbp+var_18], r13d
0x180067068  jl      short loc_18006708E
0x18006706a  mov     [rbp+var_18], r14d
0x18006706e  xor     ecx, ecx; pReserved
0x180067070  call    cs:__imp_CoDisableCallCancellation
0x180067076  mov     rdx, [rbp+phNewTimer]; Timer
0x18006707a  test    rdx, rdx
0x18006707d  jz      short loc_18006708E
0x18006707f  mov     r8, r15; CompletionEvent
0x180067082  xor     ecx, ecx; TimerQueue
0x180067084  call    cs:__imp_DeleteTimerQueueTimer
0x18006708a  mov     [rbp+phNewTimer], r13
0x18006708e  mov     rcx, [rbp+arg_10]
0x180067092  test    rcx, rcx
0x180067095  jz      short loc_1800670A8
0x180067097  mov     [rbp+arg_10], r13
0x18006709b  mov     rax, [rcx]
0x18006709e  mov     rax, [rax+10h]
0x1800670a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670a7  nop
0x1800670a8  mov     rcx, [rbp+arg_0]
0x1800670ac  test    rcx, rcx
0x1800670af  jz      short loc_1800670C2
0x1800670b1  mov     [rbp+arg_0], r13
0x1800670b5  mov     rax, [rcx]
0x1800670b8  mov     rax, [rax+10h]
0x1800670bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670c1  nop
0x1800670c2  mov     eax, ebx
0x1800670c4  mov     rbx, [rsp+60h+arg_8]
0x1800670cc  add     rsp, 60h
0x1800670d0  pop     r15
0x1800670d2  pop     r14
0x1800670d4  pop     r13
0x1800670d6  pop     r12
0x1800670d8  pop     rdi
0x1800670d9  pop     rsi
0x1800670da  pop     rbp
0x1800670db  retn
0x1800670dc  mov     rcx, [rbp+38h]; this
0x1800670e0  mov     r14d, 80004005h
0x1800670e6  mov     r9d, r14d; char *
0x1800670e9  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800670f0  mov     edx, 0EDh; void *
0x1800670f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800670fa  nop
0x1800670fb  test    rsi, rsi
0x1800670fe  jnz     loc_18006718B
0x180067104  mov     rcx, [rbp+arg_0]
0x180067108  test    rcx, rcx
0x18006710b  jz      short loc_18006711E
0x18006710d  mov     [rbp+arg_0], r13
0x180067111  mov     rdx, [rcx]
0x180067114  mov     rax, [rdx+10h]
0x180067118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006711d  nop
0x18006711e  mov     eax, r14d
0x180067121  jmp     short loc_1800670C4
0x180067123  mov     rcx, [rbp+38h]; this
0x180067127  mov     r9d, ebx; char *
0x18006712a  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180067131  mov     edx, 0F2h; void *
0x180067136  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006713b  nop
0x18006713c  cmp     [rbp+var_18], r13d
0x180067140  jl      short loc_180067167
0x180067142  mov     [rbp+var_18], r14d
0x180067146  xor     ecx, ecx; pReserved
0x180067148  call    cs:__imp_CoDisableCallCancellation
0x18006714e  mov     rdx, [rbp+phNewTimer]; Timer
0x180067152  test    rdx, rdx
0x180067155  jz      short loc_180067167
0x180067157  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18006715b  xor     ecx, ecx; TimerQueue
0x18006715d  call    cs:__imp_DeleteTimerQueueTimer
0x180067163  mov     [rbp+phNewTimer], r13
0x180067167  test    rsi, rsi
0x18006716a  jnz     short loc_180067199
0x18006716c  mov     rcx, [rbp+arg_0]
0x180067170  test    rcx, rcx
0x180067173  jz      short loc_180067186
0x180067175  mov     [rbp+arg_0], r13
0x180067179  mov     rax, [rcx]
0x18006717c  mov     rax, [rax+10h]
0x180067180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067185  nop
0x180067186  jmp     loc_1800670C2
0x18006718b  mov     rcx, rsi; lpCriticalSection
0x18006718e  call    cs:__imp_LeaveCriticalSection
0x180067194  jmp     loc_180067104
0x180067199  mov     rcx, rsi; lpCriticalSection
0x18006719c  call    cs:__imp_LeaveCriticalSection
0x1800671a2  jmp     short loc_18006716C
0x1800671a4  lea     rcx, [rbp+Parameter]; this
0x1800671a8  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x1800671ad  mov     edx, 2710h; DueTime
0x1800671b2  lea     rcx, [rbp+Parameter]; this
0x1800671b6  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x1800671bb  nop
0x1800671bc  mov     rcx, [rbp+arg_10]
0x1800671c0  mov     rax, [rcx]
0x1800671c3  mov     rdx, r12
0x1800671c6  mov     rax, [rax+18h]
0x1800671ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800671cf  mov     rcx, [rbp+38h]; this
0x1800671d3  test    eax, eax
0x1800671d5  jns     short loc_1800671EC
0x1800671d7  mov     r9d, eax; char *
0x1800671da  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800671e1  mov     edx, 0FEh; void *
0x1800671e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800671eb  nop
0x1800671ec  lea     rcx, [rbp+Parameter]; this
0x1800671f0  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x1800671f5  nop
0x1800671f6  lea     rcx, [rbp+arg_10]
0x1800671fa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800671ff  nop
0x180067200  lea     rcx, [rbp+arg_0]
0x180067204  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067209  xor     eax, eax
0x18006720b  jmp     loc_1800670C4
```
