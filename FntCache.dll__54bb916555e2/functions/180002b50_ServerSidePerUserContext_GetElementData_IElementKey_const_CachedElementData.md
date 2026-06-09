# ServerSidePerUserContext::GetElementData(IElementKey const &,CachedElementData *)

- ea: `0x180002b50`
- end: `0x180002dfc`
- name: `?GetElementData@ServerSidePerUserContext@@UEAAXAEBVIElementKey@@PEAUCachedElementData@@@Z`
- size: `684`
- prototype: `void __fastcall(ServerSidePerUserContext *__hidden this, const struct IElementKey *, struct CachedElementData *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000219c`
- `0x1800026c0`
- `0x180002b50`
- `0x1800031e8`
- `0x1800033c8`
- `0x18000344c`
- `0x1800034bc`
- `0x18000f7bc`
- `0x1800103f0`
- `0x1800217ac`
- `0x1800983d8`
- `0x1800a1558`
- `0x1800ab1b0`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002d14`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002d14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002cb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002cb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c19`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ServerSidePerUserContext::GetElementData(
        ServerSidePerUserContext *this,
        const struct IElementKey *a2,
        struct CachedElementData *a3)
{
  int v6; // ecx
  __int64 v7; // rsi
  int v8; // eax
  __int64 v9; // rcx
  const struct LockHolder *v10; // rdx
  struct IElementConstructionTask *Task; // rax
  const struct LockHolder *v12; // rdx
  struct IElementConstructionTask *v13; // rsi
  struct IElementConstructionTask *v14; // rax
  struct IElementConstructionTask *v15; // rdi
  __int64 v16; // rcx
  int v17; // eax
  HANDLE EventW; // rax
  void *v19; // rax
  bool v20; // r8
  int v21; // edi
  int v22; // edi
  struct IElementConstructionTask *pExceptionObject; // [rsp+68h] [rbp+38h] BYREF
  char *v24; // [rsp+78h] [rbp+48h]

  v6 = *((_DWORD *)a2 + 3);
  if ( ((unsigned int)(v6 - 2) <= 1 || v6 == 9) && (v9 = *((_QWORD *)this + 74)) != 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
  }
  else
  {
    v7 = *((_QWORD *)this + 44);
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v7 + 88LL))(v7) )
    {
      v19 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 96LL))(v7);
      if ( !Event::Wait(v19, 0xFFFFFFFF, v20) )
      {
        Exception::Exception((Exception *)&pExceptionObject, -2003283959, 0);
        v21 = (int)pExceptionObject;
        EventLogger::LogEvent<long,EventTag,unsigned int>(
          (_DWORD)this + 16,
          1751343427,
          1869771365,
          (_DWORD)pExceptionObject,
          0x746567727673LL,
          55);
        LODWORD(pExceptionObject) = v21;
        throw (NotSupportedException *)&pExceptionObject;
      }
      _mm_lfence();
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 44) + 104LL))(*((_QWORD *)this + 44));
    if ( v8 < 0 )
    {
      Exception::Exception((Exception *)&pExceptionObject, v8, 0);
      v22 = (int)pExceptionObject;
      EventLogger::LogEvent<long,EventTag,unsigned int>(
        (_DWORD)this + 16,
        1751343427,
        1869771365,
        (_DWORD)pExceptionObject,
        0x746567727673LL,
        58);
      LODWORD(pExceptionObject) = v22;
      throw (OSException *)&pExceptionObject;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(ServerSidePerUserContext *, const struct IElementKey *, struct CachedElementData *))(*(_QWORD *)this + 56LL))(
            this,
            a2,
            a3) )
    {
      pExceptionObject = 0;
      v24 = (char *)this + 288;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
      if ( (*(unsigned __int8 (__fastcall **)(ServerSidePerUserContext *, const struct IElementKey *, struct CachedElementData *))(*(_QWORD *)this + 56LL))(
             this,
             a2,
             a3) )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
        v16 = 0;
      }
      else
      {
        Task = ElementTaskList::FindTask((ServerSidePerUserContext *)((char *)this + 288), v10, a2);
        v13 = Task;
        if ( Task )
        {
          v15 = Task;
          pExceptionObject = Task;
          _InterlockedIncrement((volatile signed __int32 *)Task + 2);
          ReleaseReference<IElementConstructionTask>(0);
          if ( !*((_QWORD *)v13 + 3) && *((_DWORD *)v13 + 8) == 1 )
          {
            EventW = CreateEventW(0, 1, 0, 0);
            *((_QWORD *)v13 + 3) = EventW;
            if ( !EventW )
              OSException::ThrowLastError();
          }
        }
        else
        {
          v14 = ElementTaskList::AddTask((ServerSidePerUserContext *)((char *)this + 288), v12, this, a2);
          v15 = v14;
          pExceptionObject = v14;
          if ( v14 )
            _InterlockedIncrement((volatile signed __int32 *)v14 + 2);
          ReleaseReference<IElementConstructionTask>(0);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
        if ( v13 )
        {
          v17 = IElementConstructionTask::WaitForCompletion(v13);
          LogAndThrowIfFailed<OSException>(v17);
        }
        else
        {
          ElementTaskList::ExecuteTask((ServerSidePerUserContext *)((char *)this + 288), this, v15, 1);
        }
        CachedElementData::operator=(a3, (char *)v15 + 40);
        v16 = (__int64)v15;
      }
      ReleaseReference<IElementConstructionTask>(v16);
    }
  }
}

```

## disassembly

```asm
0x180002b50  mov     [rsp-28h+arg_0], rbx
0x180002b55  push    rbp
0x180002b56  push    rsi
0x180002b57  push    rdi
0x180002b58  push    r14
0x180002b5a  push    r15
0x180002b5c  mov     rbp, rsp
0x180002b5f  sub     rsp, 30h
0x180002b63  mov     r15, r8
0x180002b66  mov     rdi, rdx
0x180002b69  mov     r14, rcx
0x180002b6c  mov     ecx, [rdx+0Ch]
0x180002b6f  lea     eax, [rcx-2]
0x180002b72  cmp     eax, 1
0x180002b75  jbe     short loc_180002BE9
0x180002b77  cmp     ecx, 9
0x180002b7a  jz      short loc_180002BE9
0x180002b7c  mov     rbx, 746567727673h
0x180002b86  mov     rsi, [r14+160h]
0x180002b8d  mov     rax, [rsi]
0x180002b90  mov     rcx, rsi
0x180002b93  mov     rax, [rax+58h]
0x180002b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b9c  test    al, al
0x180002b9e  jz      loc_180002D2D
0x180002ba4  mov     rcx, [r14+160h]
0x180002bab  mov     rax, [rcx]
0x180002bae  mov     rax, [rax+68h]
0x180002bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bb7  test    eax, eax
0x180002bb9  js      loc_180002DAA
0x180002bbf  mov     rax, [r14]
0x180002bc2  mov     r8, r15
0x180002bc5  mov     rdx, rdi
0x180002bc8  mov     rcx, r14
0x180002bcb  mov     rax, [rax+38h]
0x180002bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bd4  test    al, al
0x180002bd6  jz      short loc_180002C03
0x180002bd8  mov     rbx, [rsp+30h+arg_0]
0x180002bdd  add     rsp, 30h
0x180002be1  pop     r15
0x180002be3  pop     r14
0x180002be5  pop     rdi
0x180002be6  pop     rsi
0x180002be7  pop     rbp
0x180002be8  retn
0x180002be9  mov     rcx, [r14+250h]
0x180002bf0  test    rcx, rcx
0x180002bf3  jz      short loc_180002B7C
0x180002bf5  mov     rax, [rcx]
0x180002bf8  mov     rax, [rax+18h]
0x180002bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c01  jmp     short loc_180002BD8
0x180002c03  lea     rbx, [r14+120h]
0x180002c0a  mov     [rbp+pExceptionObject], 0
0x180002c12  mov     [rbp+arg_18], rbx
0x180002c16  mov     rcx, rbx; lpCriticalSection
0x180002c19  call    cs:__imp_EnterCriticalSection
0x180002c1f  nop
0x180002c20  mov     rax, [r14]
0x180002c23  mov     r8, r15
0x180002c26  mov     rdx, rdi
0x180002c29  mov     rcx, r14
0x180002c2c  mov     rax, [rax+38h]
0x180002c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c35  test    al, al
0x180002c37  jnz     short loc_180002CAF
0x180002c39  mov     r8, rdi; struct IElementKey *
0x180002c3c  mov     rcx, rbx; this
0x180002c3f  call    ?FindTask@ElementTaskList@@AEAAPEAVIElementConstructionTask@@AEBVLockHolder@@AEBVIElementKey@@@Z; ElementTaskList::FindTask(LockHolder const &,IElementKey const &)
0x180002c44  mov     rsi, rax
0x180002c47  test    rax, rax
0x180002c4a  jnz     loc_180002CE1
0x180002c50  mov     r9, rdi; struct IElementKey *
0x180002c53  mov     r8, r14; struct IBaseCacheContext *
0x180002c56  mov     rcx, rbx; this
0x180002c59  call    ?AddTask@ElementTaskList@@AEAAPEAVIElementConstructionTask@@AEBVLockHolder@@PEAUIBaseCacheContext@@AEBVIElementKey@@@Z; ElementTaskList::AddTask(LockHolder const &,IBaseCacheContext *,IElementKey const &)
0x180002c5e  mov     rdi, rax
0x180002c61  mov     [rbp+pExceptionObject], rax
0x180002c65  test    rax, rax
0x180002c68  jz      short loc_180002C6E
0x180002c6a  lock inc dword ptr [rax+8]
0x180002c6e  xor     ecx, ecx
0x180002c70  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x180002c75  nop
0x180002c76  mov     rcx, rbx; lpCriticalSection
0x180002c79  call    cs:__imp_LeaveCriticalSection
0x180002c7f  test    rsi, rsi
0x180002c82  jnz     short loc_180002CBD
0x180002c84  mov     r9b, 1; bool
0x180002c87  mov     r8, rdi; struct IElementConstructionTask *
0x180002c8a  mov     rdx, r14; struct IBaseCacheContext *
0x180002c8d  mov     rcx, rbx; this
0x180002c90  call    ?ExecuteTask@ElementTaskList@@QEAAJPEAUIBaseCacheContext@@PEAVIElementConstructionTask@@_N@Z; ElementTaskList::ExecuteTask(IBaseCacheContext *,IElementConstructionTask *,bool)
0x180002c95  lea     rdx, [rdi+28h]
0x180002c99  mov     rcx, r15
0x180002c9c  call    ??4CachedElementData@@QEAAAEAU0@AEBU0@@Z; CachedElementData::operator=(CachedElementData const &)
0x180002ca1  nop
0x180002ca2  mov     rcx, rdi
0x180002ca5  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x180002caa  jmp     loc_180002BD8
0x180002caf  mov     rcx, rbx; lpCriticalSection
0x180002cb2  call    cs:__imp_LeaveCriticalSection
0x180002cb8  nop
0x180002cb9  xor     ecx, ecx
0x180002cbb  jmp     short loc_180002CA5
0x180002cbd  mov     rbx, 4445746567h
0x180002cc7  mov     rcx, rsi; this
0x180002cca  call    ?WaitForCompletion@IElementConstructionTask@@AEAAJXZ; IElementConstructionTask::WaitForCompletion(void)
0x180002ccf  mov     ecx, eax; int
0x180002cd1  mov     r8d, 0AAh
0x180002cd7  mov     rdx, rbx
0x180002cda  call    ??$LogAndThrowIfFailed@VOSException@@@@YAXJVEventTag@@I@Z; LogAndThrowIfFailed<OSException>(long,EventTag,uint)
0x180002cdf  jmp     short loc_180002C95
0x180002ce1  mov     rdi, rsi
0x180002ce4  mov     [rbp+pExceptionObject], rsi
0x180002ce8  lock inc dword ptr [rax+8]
0x180002cec  xor     ecx, ecx
0x180002cee  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x180002cf3  cmp     qword ptr [rsi+18h], 0
0x180002cf8  jnz     loc_180002C76
0x180002cfe  cmp     dword ptr [rsi+20h], 1
0x180002d02  jnz     loc_180002C76
0x180002d08  xor     r9d, r9d; lpName
0x180002d0b  xor     r8d, r8d; bInitialState
0x180002d0e  lea     edx, [r9+1]; bManualReset
0x180002d12  xor     ecx, ecx; lpEventAttributes
0x180002d14  call    cs:__imp_CreateEventW
0x180002d1a  mov     [rsi+18h], rax
0x180002d1e  test    rax, rax
0x180002d21  jnz     loc_180002C76
0x180002d27  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x180002d2d  mov     rax, [rsi]
0x180002d30  mov     rcx, rsi
0x180002d33  mov     rax, [rax+60h]
0x180002d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d3c  mov     rcx, rax; hHandle
0x180002d3f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002d42  call    ?Wait@Event@@SA_NPEAXI_N@Z; Event::Wait(void *,uint,bool)
0x180002d47  test    al, al
0x180002d49  jz      short loc_180002D55
0x180002d4b  nop
0x180002d4c  lfence
0x180002d4f  nop
0x180002d50  jmp     loc_180002BA4
0x180002d55  xor     r8d, r8d; unsigned int
0x180002d58  mov     edx, 88985009h; int
0x180002d5d  lea     rcx, [rbp+pExceptionObject]; this
0x180002d61  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x180002d66  mov     rdx, 7874436568636143h
0x180002d70  mov     r8, 726F727265h
0x180002d7a  mov     edi, dword ptr [rbp+pExceptionObject]
0x180002d7d  lea     rcx, [r14+10h]
0x180002d81  mov     [rsp+30h+var_8], 37h ; '7'
0x180002d89  mov     [rsp+30h+var_10], rbx
0x180002d8e  mov     r9d, edi
0x180002d91  call    ??$LogEvent@JVEventTag@@I@EventLogger@@QEBAXVEventTag@@0J0I@Z; EventLogger::LogEvent<long,EventTag,uint>(EventTag,EventTag,long,EventTag,uint)
0x180002d96  mov     dword ptr [rbp+pExceptionObject], edi
0x180002d99  lea     rdx, _TI2?AVNotSupportedException@@; pThrowInfo
0x180002da0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180002da4  call    _CxxThrowException_0
0x180002daa  xor     r8d, r8d; unsigned int
0x180002dad  mov     edx, eax; int
0x180002daf  lea     rcx, [rbp+pExceptionObject]; this
0x180002db3  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x180002db8  mov     rdx, 7874436568636143h
0x180002dc2  mov     r8, 726F727265h
0x180002dcc  mov     edi, dword ptr [rbp+pExceptionObject]
0x180002dcf  lea     rcx, [r14+10h]
0x180002dd3  mov     [rsp+30h+var_8], 3Ah ; ':'
0x180002ddb  mov     [rsp+30h+var_10], rbx
0x180002de0  mov     r9d, edi
0x180002de3  call    ??$LogEvent@JVEventTag@@I@EventLogger@@QEBAXVEventTag@@0J0I@Z; EventLogger::LogEvent<long,EventTag,uint>(EventTag,EventTag,long,EventTag,uint)
0x180002de8  mov     dword ptr [rbp+pExceptionObject], edi
0x180002deb  lea     rdx, _TI2?AVOSException@@; pThrowInfo
0x180002df2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180002df6  call    _CxxThrowException_0
```
