# CDShowTransPin::StartStream(void)

- ea: `0x18002e66c`
- end: `0x18002e894`
- name: `?StartStream@CDShowTransPin@@QEAAJXZ`
- size: `552`
- prototype: `__int64 __fastcall(CDShowTransPin *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18002e454`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x18002d514`
- `0x18002e66c`
- `0x18002e8a0`
- `0x180032a50`
- `0x18003eb58`
- `0x180051ce4`
- `0x180053dc0`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002e86c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002e86c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e84e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e84e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e777`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e777`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDShowTransPin::StartStream(CDShowTransPin *this)
{
  struct CDShowTransRoot *RootObj; // rax
  struct CDShowTransRoot *v3; // rdi
  _DWORD *v4; // rax
  CallStackTracing *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rbx
  DWORD CurrentThreadId; // eax
  CMFSRWLock *v10; // rcx
  unsigned int v11; // ebx
  char v13; // [rsp+58h] [rbp+10h] BYREF
  int v14; // [rsp+60h] [rbp+18h]

  v14 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v13, "CDShowTransPin::StartStream", 1002);
  RootObj = CDShowTransPin::GetRootObj(this, 0);
  v3 = RootObj;
  if ( RootObj && *(_DWORD *)(*((_QWORD *)RootObj + 3) + 272LL) == 1 )
  {
    if ( *((_DWORD *)this + 2) )
    {
      if ( *((_DWORD *)this + 2) != 1
        || (v4 = (_DWORD *)((char *)this + 16), (*((_DWORD *)this + 4) & 0xFFFFFFFD) == 0) && !*((_DWORD *)this + 3) )
      {
        if ( (unsigned __int8)byte_1800EACCB >= 8u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 27, &WPP_e67ca36682193615575df34b6326caef_Traceguids, this);
        goto LABEL_24;
      }
    }
    else
    {
      if ( *((_DWORD *)this + 20) == 1 )
        CDShowTransPin::GoActive(this, RootObj);
      *((_DWORD *)this + 2) = 1;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
      v4 = (_DWORD *)((char *)this + 16);
    }
    *v4 = 0;
    *((_DWORD *)this + 3) = 0;
    goto LABEL_24;
  }
  v14 = -1072873854;
  v5 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
    CallStackTracing::s_wpInstance = v6;
    if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
    {
      v5 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v5 = (CallStackTracing *)&qword_1800EB130;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
    }
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
    if ( v14 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v14 )
      CallStackContext::TraceFailure(ThreadRelativeContext, "CDShowTransPin::StartStream", 1031, v14);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_e67ca36682193615575df34b6326caef_Traceguids, this, v14);
LABEL_24:
  if ( v14 < 0 && *((_DWORD *)this + 2) == 1 )
  {
    *((_DWORD *)this + 2) = 0;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 16LL))(*((_QWORD *)this + 6));
  }
  if ( v3 )
  {
    v8 = *((_QWORD *)this + 6);
    CurrentThreadId = GetCurrentThreadId();
    v10 = (CMFSRWLock *)(v8 + 80);
    if ( *(_DWORD *)(v8 + 88) == CurrentThreadId )
      CMFSRWLock::UnlockExclusive(v10);
    else
      ReleaseSRWLockShared((PSRWLOCK)v10);
  }
  v11 = v14;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v13);
  return v11;
}

```

## disassembly

```asm
0x18002e66c  mov     [rsp+arg_0], rbx
0x18002e671  push    rdi
0x18002e672  sub     rsp, 40h
0x18002e676  mov     rbx, rcx
0x18002e679  mov     [rsp+48h+arg_10], 0
0x18002e681  mov     r8d, 3EAh; int
0x18002e687  lea     rdx, aCdshowtranspin_9; "CDShowTransPin::StartStream"
0x18002e68e  lea     rcx, [rsp+48h+arg_8]; this
0x18002e693  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002e698  nop
0x18002e699  mov     [rsp+48h+var_18], 0
0x18002e6a2  lea     rax, [rsp+48h+arg_10]
0x18002e6a7  mov     [rsp+48h+var_10], rax
0x18002e6ac  xor     edx, edx; int
0x18002e6ae  mov     rcx, rbx; this
0x18002e6b1  call    ?GetRootObj@CDShowTransPin@@QEAAPEAVCDShowTransRoot@@H@Z; CDShowTransPin::GetRootObj(int)
0x18002e6b6  mov     rdi, rax
0x18002e6b9  test    rax, rax
0x18002e6bc  jz      loc_18002E763
0x18002e6c2  mov     rcx, [rax+18h]
0x18002e6c6  cmp     dword ptr [rcx+110h], 1
0x18002e6cd  jnz     loc_18002E763
0x18002e6d3  cmp     dword ptr [rbx+8], 0
0x18002e6d7  jz      short loc_18002E725
0x18002e6d9  cmp     dword ptr [rbx+8], 1
0x18002e6dd  jnz     short loc_18002E6F1
0x18002e6df  lea     rax, [rbx+10h]
0x18002e6e3  test    dword ptr [rax], 0FFFFFFFDh
0x18002e6e9  jnz     short loc_18002E751
0x18002e6eb  cmp     dword ptr [rbx+0Ch], 0
0x18002e6ef  jnz     short loc_18002E751
0x18002e6f1  cmp     cs:byte_1800EACCB, 8
0x18002e6f8  jb      loc_18002E821
0x18002e6fe  mov     edx, 1Bh
0x18002e703  mov     r9, rbx
0x18002e706  lea     r8, WPP_e67ca36682193615575df34b6326caef_Traceguids
0x18002e70d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e714  mov     rcx, [rcx+88h]
0x18002e71b  call    WPP_SF_q
0x18002e720  jmp     loc_18002E821
0x18002e725  cmp     dword ptr [rbx+50h], 1
0x18002e729  jnz     short loc_18002E736
0x18002e72b  mov     rdx, rdi; struct CDShowTransRoot *
0x18002e72e  mov     rcx, rbx; this
0x18002e731  call    ?GoActive@CDShowTransPin@@QEAAJPEAVCDShowTransRoot@@@Z; CDShowTransPin::GoActive(CDShowTransRoot *)
0x18002e736  mov     dword ptr [rbx+8], 1
0x18002e73d  mov     rcx, [rbx+30h]
0x18002e741  mov     rax, [rcx]
0x18002e744  mov     rax, [rax+8]
0x18002e748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e74d  lea     rax, [rbx+10h]
0x18002e751  mov     dword ptr [rax], 0
0x18002e757  mov     dword ptr [rbx+0Ch], 0
0x18002e75e  jmp     loc_18002E821
0x18002e763  mov     [rsp+48h+arg_10], 0C00D3E82h
0x18002e76b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e772  test    rcx, rcx
0x18002e775  jnz     short loc_18002E7BE
0x18002e777  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002e77e  nop     dword ptr [rax+rax+00h]
0x18002e783  mov     rcx, rax
0x18002e786  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e78d  test    rax, rax
0x18002e790  jz      short loc_18002E7B0
0x18002e792  mov     rax, [rax]
0x18002e795  mov     edx, 7F0h
0x18002e79a  mov     rax, [rax+8]
0x18002e79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7a3  test    eax, eax
0x18002e7a5  jz      short loc_18002E7B0
0x18002e7a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e7ae  jmp     short loc_18002E7BE
0x18002e7b0  lea     rcx, qword_1800EB130; this
0x18002e7b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e7be  cmp     byte ptr [rcx+8], 0
0x18002e7c2  jz      short loc_18002E7F1
0x18002e7c4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e7c9  mov     r9d, [rsp+48h+arg_10]; int
0x18002e7ce  test    r9d, r9d
0x18002e7d1  jns     short loc_18002E7F1
0x18002e7d3  cmp     [rax+7CCh], r9d
0x18002e7da  jz      short loc_18002E7F1
0x18002e7dc  mov     r8d, 407h; int
0x18002e7e2  lea     rdx, aCdshowtranspin_9; "CDShowTransPin::StartStream"
0x18002e7e9  mov     rcx, rax; this
0x18002e7ec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e7f1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e7f8  jb      short loc_18002E821
0x18002e7fa  mov     edx, 1Ch
0x18002e7ff  mov     eax, [rsp+48h+arg_10]
0x18002e803  mov     [rsp+48h+var_28], eax
0x18002e807  mov     r9, rbx
0x18002e80a  lea     r8, WPP_e67ca36682193615575df34b6326caef_Traceguids
0x18002e811  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e818  mov     rcx, [rcx+10h]
0x18002e81c  call    WPP_SF_qD
0x18002e821  cmp     [rsp+48h+arg_10], 0
0x18002e826  jge     short loc_18002E845
0x18002e828  cmp     dword ptr [rbx+8], 1
0x18002e82c  jnz     short loc_18002E845
0x18002e82e  mov     dword ptr [rbx+8], 0
0x18002e835  mov     rcx, [rbx+30h]
0x18002e839  mov     rax, [rcx]
0x18002e83c  mov     rax, [rax+10h]
0x18002e840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e845  test    rdi, rdi
0x18002e848  jz      short loc_18002E878
0x18002e84a  mov     rbx, [rbx+30h]
0x18002e84e  call    cs:__imp_GetCurrentThreadId
0x18002e855  nop     dword ptr [rax+rax+00h]
0x18002e85a  mov     edx, [rbx+58h]
0x18002e85d  lea     rcx, [rbx+50h]; this
0x18002e861  cmp     edx, eax
0x18002e863  jnz     short loc_18002E86C
0x18002e865  call    ?UnlockExclusive@CMFSRWLock@@QEAAXXZ; CMFSRWLock::UnlockExclusive(void)
0x18002e86a  jmp     short loc_18002E878
0x18002e86c  call    cs:__imp_ReleaseSRWLockShared
0x18002e873  nop     dword ptr [rax+rax+00h]
0x18002e878  mov     ebx, [rsp+48h+arg_10]
0x18002e87c  lea     rcx, [rsp+48h+arg_8]; this
0x18002e881  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002e886  mov     eax, ebx
0x18002e888  mov     rbx, [rsp+48h+arg_0]
0x18002e88d  add     rsp, 40h
0x18002e891  pop     rdi
0x18002e892  retn
```
