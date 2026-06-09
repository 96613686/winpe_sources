# ProcessMonitor::Watch(void *)

- ea: `0x18000c334`
- end: `0x18000c609`
- name: `?Watch@ProcessMonitor@@QEAAKPEAX@Z`
- size: `725`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005ec0`

## callees

- `0x180002a88`
- `0x180002c18`
- `0x180004f20`
- `0x180007468`
- `0x180007484`
- `0x18000bfcc`
- `0x18000c000`
- `0x18000c334`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c56c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c56c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c42e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c437`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c42e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c486`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c499`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c499`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c38b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c38b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c551`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c551`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c4fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c4fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c3c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c3c5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000c459`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000c459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c491`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c580`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c59c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c491`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c580`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c59c`
- `RPCRT4!RpcImpersonateClient` at `0x18000c3e6`
- `RPCRT4!RpcImpersonateClient` at `0x18000c3e6`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000c362`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000c362`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c587`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c587`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000c411`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000c411`

## pseudocode

```c
__int64 __fastcall ProcessMonitor::Watch(RTL_SRWLOCK *this, void *a2)
{
  int v4; // eax
  char v5; // di
  _QWORD *Ptr; // rcx
  _QWORD *i; // rax
  int v8; // eax
  ProcessWatcherDesc *v9; // rdi
  HANDLE CurrentProcess; // rsi
  HANDLE v11; // rax
  const char *v12; // r9
  HANDLE v13; // r12
  HANDLE v14; // r13
  DWORD LastError; // esi
  ProcessWatcherDesc *v16; // rax
  HANDLE v17; // rdx
  ProcessWatcherDesc *v18; // rax
  _QWORD *v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rdx
  char *v22; // rax
  ProcessWatcherDesc *v23; // rbx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-60h]
  ProcessWatcherDesc *v26[3]; // [rsp+40h] [rbp-40h] BYREF
  HANDLE **p_p_hObject; // [rsp+58h] [rbp-28h]
  HANDLE *p_hObject; // [rsp+60h] [rbp-20h] BYREF
  HANDLE TargetHandle; // [rsp+68h] [rbp-18h] BYREF
  char v30; // [rsp+70h] [rbp-10h]
  HANDLE **v31; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  unsigned int Pid; // [rsp+D0h] [rbp+50h] BYREF
  HANDLE hObject; // [rsp+D8h] [rbp+58h] BYREF

  Pid = 0;
  v4 = I_RpcBindingInqLocalClientPID(a2, &Pid);
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\processmonitor.cpp",
      (const char *)(unsigned int)v4,
      dwDesiredAccess);
  AcquireSRWLockShared(this + 5);
  v5 = 0;
  Ptr = this[3].Ptr;
  for ( i = (_QWORD *)*Ptr; i != Ptr; i = (_QWORD *)*i )
  {
    if ( !v5 )
    {
      v5 = 0;
      if ( *(_DWORD *)(i[2] + 48LL) != Pid )
        continue;
    }
    v5 = 1;
  }
  if ( this != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockShared(this + 5);
  if ( !v5 )
  {
    hObject = 0;
    v26[1] = (ProcessWatcherDesc *)&RpcAutoImpersonate::`vftable';
    v8 = RpcImpersonateClient(a2);
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\SpatialSoundDataManager.h",
        (const char *)(unsigned int)v8,
        dwDesiredAccess);
    v9 = (ProcessWatcherDesc *)OpenProcess(0x101040u, 0, Pid);
    v26[2] = v9;
    p_hObject = &hObject;
    TargetHandle = 0;
    v30 = 1;
    CurrentProcess = GetCurrentProcess();
    v11 = GetCurrentProcess();
    if ( !DuplicateHandle(v11, v9, CurrentProcess, &TargetHandle, 0x101040u, 0, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x29,
        (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\processmonitor.cpp",
        v12);
    if ( v30 )
    {
      v13 = TargetHandle;
      v14 = *p_hObject;
      if ( (char *)*p_hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v14);
        SetLastError(LastError);
      }
      *p_hObject = v13;
    }
    v16 = (ProcessWatcherDesc *)operator new(0x38u);
    v26[0] = v16;
    if ( v16 )
    {
      p_p_hObject = &p_hObject;
      p_hObject = &std::_Func_impl<std::_Callable_obj<_lambda_312e65f4f93bbe839a71a78ad9276a5e_,0>,std::allocator<std::_Func_class<void,unsigned long,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,unsigned long,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
      TargetHandle = this;
      v31 = &p_hObject;
      v17 = hObject;
      hObject = 0;
      v18 = (ProcessWatcherDesc *)ProcessWatcherDesc::ProcessWatcherDesc(v16, v17);
    }
    else
    {
      v18 = 0;
    }
    v26[0] = v18;
    AcquireSRWLockExclusive(this + 5);
    p_p_hObject = (HANDLE **)&this[5];
    v19 = this[3].Ptr;
    v21 = std::_List_buy<std::unique_ptr<ProcessWatcherDesc>>::_Buynode<std::unique_ptr<ProcessWatcherDesc>>(
            v20,
            v19,
            v19[1],
            v26);
    v22 = (char *)this[4].Ptr;
    if ( v22 == (char *)0xAAAAAAAAAAAAAA9LL )
      std::_Xlength_error("list<T> too long");
    this[4].Ptr = v22 + 1;
    v19[1] = v21;
    **(_QWORD **)(v21 + 8) = v21;
    if ( this != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(this + 5);
    v23 = v26[0];
    if ( v26[0] )
    {
      ProcessWatcherDesc::~ProcessWatcherDesc(v26[0]);
      operator delete(v23);
    }
    if ( (unsigned __int64)v9 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v9);
    RevertToSelf();
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
  }
  return Pid;
}

```

## disassembly

```asm
0x18000c334  mov     [rsp-38h+arg_0], rbx
0x18000c339  push    rbp
0x18000c33a  push    rsi
0x18000c33b  push    rdi
0x18000c33c  push    r12
0x18000c33e  push    r13
0x18000c340  push    r14
0x18000c342  push    r15
0x18000c344  mov     rbp, rsp
0x18000c347  sub     rsp, 80h
0x18000c34e  mov     rsi, rdx
0x18000c351  mov     r14, rcx
0x18000c354  xor     r12d, r12d
0x18000c357  mov     [rbp+Pid], r12d
0x18000c35b  lea     rdx, [rbp+Pid]; Pid
0x18000c35f  mov     rcx, rsi; Binding
0x18000c362  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000c368  mov     r15d, 80070000h
0x18000c36e  test    eax, eax
0x18000c370  jle     short loc_18000C378
0x18000c372  movzx   eax, ax
0x18000c375  or      eax, r15d
0x18000c378  mov     rcx, [rbp+38h]; this
0x18000c37c  test    eax, eax
0x18000c37e  js      loc_18000C5CD
0x18000c384  lea     rbx, [r14+28h]
0x18000c388  mov     rcx, rbx; SRWLock
0x18000c38b  call    cs:__imp_AcquireSRWLockShared
0x18000c391  mov     dil, r12b
0x18000c394  mov     rcx, [r14+18h]
0x18000c398  mov     rax, [rcx]
0x18000c39b  cmp     rax, rcx
0x18000c39e  jz      short loc_18000C3BD
0x18000c3a0  test    dil, dil
0x18000c3a3  jnz     short loc_18000C3B5
0x18000c3a5  mov     r8, [rax+10h]
0x18000c3a9  mov     edx, [rbp+Pid]
0x18000c3ac  cmp     [r8+30h], edx
0x18000c3b0  mov     dil, r12b
0x18000c3b3  jnz     short loc_18000C3B8
0x18000c3b5  mov     dil, 1
0x18000c3b8  mov     rax, [rax]
0x18000c3bb  jmp     short loc_18000C39B
0x18000c3bd  test    rbx, rbx
0x18000c3c0  jz      short loc_18000C3CB
0x18000c3c2  mov     rcx, rbx; SRWLock
0x18000c3c5  call    cs:__imp_ReleaseSRWLockShared
0x18000c3cb  test    dil, dil
0x18000c3ce  jnz     loc_18000C5A2
0x18000c3d4  mov     [rbp+hObject], r12
0x18000c3d8  lea     rax, ??_7RpcAutoImpersonate@@6B@; const RpcAutoImpersonate::`vftable'
0x18000c3df  mov     [rbp+var_38], rax
0x18000c3e3  mov     rcx, rsi; BindingHandle
0x18000c3e6  call    cs:__imp_RpcImpersonateClient
0x18000c3ec  test    eax, eax
0x18000c3ee  jle     short loc_18000C3F6
0x18000c3f0  movzx   eax, ax
0x18000c3f3  or      eax, r15d
0x18000c3f6  mov     rcx, [rbp+38h]; this
0x18000c3fa  test    eax, eax
0x18000c3fc  js      loc_18000C5E2
0x18000c402  mov     r8d, [rbp+Pid]; dwProcessId
0x18000c406  xor     edx, edx; bInheritHandle
0x18000c408  mov     r15d, 101040h
0x18000c40e  mov     ecx, r15d; dwDesiredAccess
0x18000c411  call    cs:__imp_OpenProcess
0x18000c417  mov     rdi, rax
0x18000c41a  mov     [rbp+var_30], rax
0x18000c41e  lea     rax, [rbp+hObject]
0x18000c422  mov     [rbp+var_20], rax
0x18000c426  mov     [rbp+TargetHandle], r12
0x18000c42a  mov     [rbp+var_10], 1
0x18000c42e  call    cs:__imp_GetCurrentProcess
0x18000c434  mov     rsi, rax
0x18000c437  call    cs:__imp_GetCurrentProcess
0x18000c43d  mov     [rsp+80h+dwOptions], r12d; dwOptions
0x18000c442  mov     [rsp+80h+bInheritHandle], r12d; bInheritHandle
0x18000c447  mov     [rsp+80h+dwDesiredAccess], r15d; dwDesiredAccess
0x18000c44c  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18000c450  mov     r8, rsi; hTargetProcessHandle
0x18000c453  mov     rdx, rdi; hSourceHandle
0x18000c456  mov     rcx, rax; hSourceProcessHandle
0x18000c459  call    cs:__imp_DuplicateHandle
0x18000c45f  mov     rcx, [rbp+38h]; this
0x18000c463  test    eax, eax
0x18000c465  jz      loc_18000C5F7
0x18000c46b  cmp     [rbp+var_10], r12b
0x18000c46f  jz      short loc_18000C4A5
0x18000c471  mov     r12, [rbp+TargetHandle]
0x18000c475  mov     r15, [rbp+var_20]
0x18000c479  mov     r13, [r15]
0x18000c47c  lea     rax, [r13-1]
0x18000c480  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c484  ja      short loc_18000C49F
0x18000c486  call    cs:__imp_GetLastError
0x18000c48c  mov     esi, eax
0x18000c48e  mov     rcx, r13; hObject
0x18000c491  call    cs:__imp_CloseHandle
0x18000c497  mov     ecx, esi; dwErrCode
0x18000c499  call    cs:__imp_SetLastError
0x18000c49f  mov     [r15], r12
0x18000c4a2  xor     r12d, r12d
0x18000c4a5  mov     ecx, 38h ; '8'; Size
0x18000c4aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c4af  mov     [rbp+var_40], rax
0x18000c4b3  test    rax, rax
0x18000c4b6  jz      short loc_18000C4F1
0x18000c4b8  lea     rcx, [rbp+var_20]
0x18000c4bc  mov     [rbp+var_28], rcx
0x18000c4c0  lea     rcx, ??_7?$_Func_impl@U?$_Callable_obj@V_lambda_312e65f4f93bbe839a71a78ad9276a5e_@@$0A@@std@@V?$allocator@V?$_Func_class@XKU_Nil@std@@U12@U12@U12@U12@U12@@std@@@2@XKU_Nil@2@U42@U42@U42@U42@U42@@std@@6B@; const std::_Func_impl<std::_Callable_obj<_lambda_312e65f4f93bbe839a71a78ad9276a5e_,0>,std::allocator<std::_Func_class<void,ulong,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,ulong,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x18000c4c7  mov     [rbp+var_20], rcx
0x18000c4cb  mov     [rbp+TargetHandle], r14
0x18000c4cf  lea     rcx, [rbp+var_20]
0x18000c4d3  mov     [rbp+var_8], rcx
0x18000c4d7  mov     rdx, [rbp+hObject]; h
0x18000c4db  mov     [rbp+hObject], r12
0x18000c4df  lea     r9, [rbp+var_20]
0x18000c4e3  mov     r8d, [rbp+Pid]
0x18000c4e7  mov     rcx, rax; pv
0x18000c4ea  call    ??0ProcessWatcherDesc@@QEAA@PEAXKV?$function@$$A6AXK@Z@std@@@Z; ProcessWatcherDesc::ProcessWatcherDesc(void *,ulong,std::function<void (ulong)>)
0x18000c4ef  jmp     short loc_18000C4F4
0x18000c4f1  mov     rax, r12
0x18000c4f4  mov     [rbp+var_40], rax
0x18000c4f8  mov     rcx, rbx; SRWLock
0x18000c4fb  call    cs:__imp_AcquireSRWLockExclusive
0x18000c501  mov     [rbp+var_28], rbx
0x18000c505  mov     rsi, [r14+18h]
0x18000c509  lea     r9, [rbp+var_40]
0x18000c50d  mov     r8, [rsi+8]
0x18000c511  mov     rdx, rsi
0x18000c514  call    ??$_Buynode@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@@?$_List_buy@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@V?$allocator@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@PEAX@1@PEAU21@0$$QEAV?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@1@@Z; std::_List_buy<std::unique_ptr<ProcessWatcherDesc>>::_Buynode<std::unique_ptr<ProcessWatcherDesc>>(std::_List_node<std::unique_ptr<ProcessWatcherDesc>,void *> *,std::_List_node<std::unique_ptr<ProcessWatcherDesc>,void *> *,std::unique_ptr<ProcessWatcherDesc> &&)
0x18000c519  mov     rdx, rax
0x18000c51c  mov     rax, [r14+20h]
0x18000c520  mov     rcx, 0AAAAAAAAAAAAAA9h
0x18000c52a  sub     rcx, rax
0x18000c52d  cmp     rcx, 1
0x18000c531  jb      loc_18000C5C0
0x18000c537  inc     rax
0x18000c53a  mov     [r14+20h], rax
0x18000c53e  mov     [rsi+8], rdx
0x18000c542  mov     rax, [rdx+8]
0x18000c546  mov     [rax], rdx
0x18000c549  test    rbx, rbx
0x18000c54c  jz      short loc_18000C558
0x18000c54e  mov     rcx, rbx; SRWLock
0x18000c551  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c557  nop
0x18000c558  mov     rbx, [rbp+var_40]
0x18000c55c  test    rbx, rbx
0x18000c55f  jz      short loc_18000C573
0x18000c561  mov     rcx, rbx; this
0x18000c564  call    ??1ProcessWatcherDesc@@QEAA@XZ; ProcessWatcherDesc::~ProcessWatcherDesc(void)
0x18000c569  mov     rcx, rbx
0x18000c56c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c572  nop
0x18000c573  lea     rax, [rdi-1]
0x18000c577  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c57b  ja      short loc_18000C587
0x18000c57d  mov     rcx, rdi; hObject
0x18000c580  call    cs:__imp_CloseHandle
0x18000c586  nop
0x18000c587  call    cs:__imp_RevertToSelf
0x18000c58d  nop
0x18000c58e  mov     rcx, [rbp+hObject]; hObject
0x18000c592  lea     rax, [rcx-1]
0x18000c596  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c59a  ja      short loc_18000C5A2
0x18000c59c  call    cs:__imp_CloseHandle
0x18000c5a2  mov     eax, [rbp+Pid]
0x18000c5a5  mov     rbx, [rsp+80h+arg_0]
0x18000c5ad  add     rsp, 80h
0x18000c5b4  pop     r15
0x18000c5b6  pop     r14
0x18000c5b8  pop     r13
0x18000c5ba  pop     r12
0x18000c5bc  pop     rdi
0x18000c5bd  pop     rsi
0x18000c5be  pop     rbp
0x18000c5bf  retn
0x18000c5c0  lea     rcx, aListTTooLong; "list<T> too long"
0x18000c5c7  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000c5cd  mov     r9d, eax; char *
0x18000c5d0  lea     r8, aAvcoreXaudioHr_0; "avcore\\xaudio\\hrtf\\ssdm\\lib\\proces"...
0x18000c5d7  mov     edx, 18h; void *
0x18000c5dc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c5e2  mov     r9d, eax; char *
0x18000c5e5  lea     r8, aAvcoreXaudioHr_4; "avcore\\xaudio\\hrtf\\ssdm\\lib\\Spatia"...
0x18000c5ec  mov     edx, 10h; void *
0x18000c5f1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c5f7  lea     r8, aAvcoreXaudioHr_0; "avcore\\xaudio\\hrtf\\ssdm\\lib\\proces"...
0x18000c5fe  mov     edx, 29h ; ')'; void *
0x18000c603  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
