# ServerCacheContext::GetElementData(IElementKey const &,CachedElementData *)

- ea: `0x1800028c0`
- end: `0x180002b42`
- name: `?GetElementData@ServerCacheContext@@UEAAXAEBVIElementKey@@PEAUCachedElementData@@@Z`
- size: `642`
- prototype: `void __fastcall(ServerCacheContext *__hidden this, const struct IElementKey *, struct CachedElementData *)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000219c`
- `0x1800026c0`
- `0x1800028c0`
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

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002a5a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002a5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000295f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000295f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ServerCacheContext::GetElementData(
        ServerCacheContext *this,
        const struct IElementKey *a2,
        struct CachedElementData *a3)
{
  __int64 v6; // rsi
  int v7; // eax
  const struct LockHolder *v8; // rdx
  struct IElementConstructionTask *Task; // rax
  const struct LockHolder *v10; // rdx
  struct IElementConstructionTask *v11; // rsi
  struct IElementConstructionTask *v12; // rax
  struct IElementConstructionTask *v13; // rdi
  __int64 v14; // rcx
  int v15; // eax
  HANDLE EventW; // rax
  void *v17; // rax
  bool v18; // r8
  int v19; // edi
  int v20; // edi
  struct IElementConstructionTask *pExceptionObject; // [rsp+60h] [rbp+30h] BYREF
  char *v22; // [rsp+78h] [rbp+48h]

  v6 = *((_QWORD *)this + 44);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v6 + 88LL))(v6) )
  {
    v17 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 96LL))(v6);
    if ( !Event::Wait(v17, 0xFFFFFFFF, v18) )
    {
      Exception::Exception((Exception *)&pExceptionObject, -2003283959, 0);
      v19 = (int)pExceptionObject;
      EventLogger::LogEvent<long,EventTag,unsigned int>(
        (_DWORD)this + 16,
        1751343427,
        1869771365,
        (_DWORD)pExceptionObject,
        0x746567727673LL,
        55);
      LODWORD(pExceptionObject) = v19;
      throw (NotSupportedException *)&pExceptionObject;
    }
    _mm_lfence();
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 44) + 104LL))(*((_QWORD *)this + 44));
  if ( v7 < 0 )
  {
    Exception::Exception((Exception *)&pExceptionObject, v7, 0);
    v20 = (int)pExceptionObject;
    EventLogger::LogEvent<long,EventTag,unsigned int>(
      (_DWORD)this + 16,
      1751343427,
      1869771365,
      (_DWORD)pExceptionObject,
      0x746567727673LL,
      58);
    LODWORD(pExceptionObject) = v20;
    throw (OSException *)&pExceptionObject;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(ServerCacheContext *, const struct IElementKey *, struct CachedElementData *))(*(_QWORD *)this + 56LL))(
          this,
          a2,
          a3) )
  {
    pExceptionObject = 0;
    v22 = (char *)this + 288;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
    if ( (*(unsigned __int8 (__fastcall **)(ServerCacheContext *, const struct IElementKey *, struct CachedElementData *))(*(_QWORD *)this + 56LL))(
           this,
           a2,
           a3) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
      v14 = 0;
    }
    else
    {
      Task = ElementTaskList::FindTask((ServerCacheContext *)((char *)this + 288), v8, a2);
      v11 = Task;
      if ( Task )
      {
        v13 = Task;
        pExceptionObject = Task;
        _InterlockedIncrement((volatile signed __int32 *)Task + 2);
        ReleaseReference<IElementConstructionTask>(0);
        if ( !*((_QWORD *)v11 + 3) && *((_DWORD *)v11 + 8) == 1 )
        {
          EventW = CreateEventW(0, 1, 0, 0);
          *((_QWORD *)v11 + 3) = EventW;
          if ( !EventW )
            OSException::ThrowLastError();
        }
      }
      else
      {
        v12 = ElementTaskList::AddTask((ServerCacheContext *)((char *)this + 288), v10, this, a2);
        v13 = v12;
        pExceptionObject = v12;
        if ( v12 )
          _InterlockedIncrement((volatile signed __int32 *)v12 + 2);
        ReleaseReference<IElementConstructionTask>(0);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
      if ( v11 )
      {
        v15 = IElementConstructionTask::WaitForCompletion(v11);
        LogAndThrowIfFailed<OSException>(v15);
      }
      else
      {
        ElementTaskList::ExecuteTask((ServerCacheContext *)((char *)this + 288), this, v13, 1);
      }
      CachedElementData::operator=(a3, (char *)v13 + 40);
      v14 = (__int64)v13;
    }
    ReleaseReference<IElementConstructionTask>(v14);
  }
}

```

## disassembly

```asm
0x1800028c0  mov     [rsp-28h+arg_8], rbx
0x1800028c5  push    rbp
0x1800028c6  push    rsi
0x1800028c7  push    rdi
0x1800028c8  push    r14
0x1800028ca  push    r15
0x1800028cc  mov     rbp, rsp
0x1800028cf  sub     rsp, 30h
0x1800028d3  mov     r15, r8
0x1800028d6  mov     rdi, rdx
0x1800028d9  mov     r14, rcx
0x1800028dc  mov     rbx, 746567727673h
0x1800028e6  mov     rsi, [rcx+160h]
0x1800028ed  mov     rax, [rsi]
0x1800028f0  mov     rcx, rsi
0x1800028f3  mov     rax, [rax+58h]
0x1800028f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028fc  test    al, al
0x1800028fe  jz      loc_180002A73
0x180002904  mov     rcx, [r14+160h]
0x18000290b  mov     rax, [rcx]
0x18000290e  mov     rax, [rax+68h]
0x180002912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002917  test    eax, eax
0x180002919  js      loc_180002AF0
0x18000291f  mov     rax, [r14]
0x180002922  mov     r8, r15
0x180002925  mov     rdx, rdi
0x180002928  mov     rcx, r14
0x18000292b  mov     rax, [rax+38h]
0x18000292f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002934  test    al, al
0x180002936  jz      short loc_180002949
0x180002938  mov     rbx, [rsp+30h+arg_8]
0x18000293d  add     rsp, 30h
0x180002941  pop     r15
0x180002943  pop     r14
0x180002945  pop     rdi
0x180002946  pop     rsi
0x180002947  pop     rbp
0x180002948  retn
0x180002949  lea     rbx, [r14+120h]
0x180002950  mov     [rbp+pExceptionObject], 0
0x180002958  mov     [rbp+arg_18], rbx
0x18000295c  mov     rcx, rbx; lpCriticalSection
0x18000295f  call    cs:__imp_EnterCriticalSection
0x180002965  nop
0x180002966  mov     rax, [r14]
0x180002969  mov     r8, r15
0x18000296c  mov     rdx, rdi
0x18000296f  mov     rcx, r14
0x180002972  mov     rax, [rax+38h]
0x180002976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000297b  test    al, al
0x18000297d  jnz     short loc_1800029F5
0x18000297f  mov     r8, rdi; struct IElementKey *
0x180002982  mov     rcx, rbx; this
0x180002985  call    ?FindTask@ElementTaskList@@AEAAPEAVIElementConstructionTask@@AEBVLockHolder@@AEBVIElementKey@@@Z; ElementTaskList::FindTask(LockHolder const &,IElementKey const &)
0x18000298a  mov     rsi, rax
0x18000298d  test    rax, rax
0x180002990  jnz     loc_180002A27
0x180002996  mov     r9, rdi; struct IElementKey *
0x180002999  mov     r8, r14; struct IBaseCacheContext *
0x18000299c  mov     rcx, rbx; this
0x18000299f  call    ?AddTask@ElementTaskList@@AEAAPEAVIElementConstructionTask@@AEBVLockHolder@@PEAUIBaseCacheContext@@AEBVIElementKey@@@Z; ElementTaskList::AddTask(LockHolder const &,IBaseCacheContext *,IElementKey const &)
0x1800029a4  mov     rdi, rax
0x1800029a7  mov     [rbp+pExceptionObject], rax
0x1800029ab  test    rax, rax
0x1800029ae  jz      short loc_1800029B4
0x1800029b0  lock inc dword ptr [rax+8]
0x1800029b4  xor     ecx, ecx
0x1800029b6  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x1800029bb  nop
0x1800029bc  mov     rcx, rbx; lpCriticalSection
0x1800029bf  call    cs:__imp_LeaveCriticalSection
0x1800029c5  test    rsi, rsi
0x1800029c8  jnz     short loc_180002A03
0x1800029ca  mov     r9b, 1; bool
0x1800029cd  mov     r8, rdi; struct IElementConstructionTask *
0x1800029d0  mov     rdx, r14; struct IBaseCacheContext *
0x1800029d3  mov     rcx, rbx; this
0x1800029d6  call    ?ExecuteTask@ElementTaskList@@QEAAJPEAUIBaseCacheContext@@PEAVIElementConstructionTask@@_N@Z; ElementTaskList::ExecuteTask(IBaseCacheContext *,IElementConstructionTask *,bool)
0x1800029db  lea     rdx, [rdi+28h]
0x1800029df  mov     rcx, r15
0x1800029e2  call    ??4CachedElementData@@QEAAAEAU0@AEBU0@@Z; CachedElementData::operator=(CachedElementData const &)
0x1800029e7  nop
0x1800029e8  mov     rcx, rdi
0x1800029eb  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x1800029f0  jmp     loc_180002938
0x1800029f5  mov     rcx, rbx; lpCriticalSection
0x1800029f8  call    cs:__imp_LeaveCriticalSection
0x1800029fe  nop
0x1800029ff  xor     ecx, ecx
0x180002a01  jmp     short loc_1800029EB
0x180002a03  mov     rbx, 4445746567h
0x180002a0d  mov     rcx, rsi; this
0x180002a10  call    ?WaitForCompletion@IElementConstructionTask@@AEAAJXZ; IElementConstructionTask::WaitForCompletion(void)
0x180002a15  mov     ecx, eax; int
0x180002a17  mov     r8d, 0AAh
0x180002a1d  mov     rdx, rbx
0x180002a20  call    ??$LogAndThrowIfFailed@VOSException@@@@YAXJVEventTag@@I@Z; LogAndThrowIfFailed<OSException>(long,EventTag,uint)
0x180002a25  jmp     short loc_1800029DB
0x180002a27  mov     rdi, rsi
0x180002a2a  mov     [rbp+pExceptionObject], rsi
0x180002a2e  lock inc dword ptr [rax+8]
0x180002a32  xor     ecx, ecx
0x180002a34  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x180002a39  cmp     qword ptr [rsi+18h], 0
0x180002a3e  jnz     loc_1800029BC
0x180002a44  cmp     dword ptr [rsi+20h], 1
0x180002a48  jnz     loc_1800029BC
0x180002a4e  xor     r9d, r9d; lpName
0x180002a51  xor     r8d, r8d; bInitialState
0x180002a54  lea     edx, [r9+1]; bManualReset
0x180002a58  xor     ecx, ecx; lpEventAttributes
0x180002a5a  call    cs:__imp_CreateEventW
0x180002a60  mov     [rsi+18h], rax
0x180002a64  test    rax, rax
0x180002a67  jnz     loc_1800029BC
0x180002a6d  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x180002a73  mov     rax, [rsi]
0x180002a76  mov     rcx, rsi
0x180002a79  mov     rax, [rax+60h]
0x180002a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a82  mov     rcx, rax; hHandle
0x180002a85  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002a88  call    ?Wait@Event@@SA_NPEAXI_N@Z; Event::Wait(void *,uint,bool)
0x180002a8d  test    al, al
0x180002a8f  jz      short loc_180002A9B
0x180002a91  nop
0x180002a92  lfence
0x180002a95  nop
0x180002a96  jmp     loc_180002904
0x180002a9b  xor     r8d, r8d; unsigned int
0x180002a9e  mov     edx, 88985009h; int
0x180002aa3  lea     rcx, [rbp+pExceptionObject]; this
0x180002aa7  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x180002aac  mov     rdx, 7874436568636143h
0x180002ab6  mov     r8, 726F727265h
0x180002ac0  mov     edi, dword ptr [rbp+pExceptionObject]
0x180002ac3  lea     rcx, [r14+10h]
0x180002ac7  mov     [rsp+30h+var_8], 37h ; '7'
0x180002acf  mov     [rsp+30h+var_10], rbx
0x180002ad4  mov     r9d, edi
0x180002ad7  call    ??$LogEvent@JVEventTag@@I@EventLogger@@QEBAXVEventTag@@0J0I@Z; EventLogger::LogEvent<long,EventTag,uint>(EventTag,EventTag,long,EventTag,uint)
0x180002adc  mov     dword ptr [rbp+pExceptionObject], edi
0x180002adf  lea     rdx, _TI2?AVNotSupportedException@@; pThrowInfo
0x180002ae6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180002aea  call    _CxxThrowException_0
0x180002af0  xor     r8d, r8d; unsigned int
0x180002af3  mov     edx, eax; int
0x180002af5  lea     rcx, [rbp+pExceptionObject]; this
0x180002af9  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x180002afe  mov     rdx, 7874436568636143h
0x180002b08  mov     r8, 726F727265h
0x180002b12  mov     edi, dword ptr [rbp+pExceptionObject]
0x180002b15  lea     rcx, [r14+10h]
0x180002b19  mov     [rsp+30h+var_8], 3Ah ; ':'
0x180002b21  mov     [rsp+30h+var_10], rbx
0x180002b26  mov     r9d, edi
0x180002b29  call    ??$LogEvent@JVEventTag@@I@EventLogger@@QEBAXVEventTag@@0J0I@Z; EventLogger::LogEvent<long,EventTag,uint>(EventTag,EventTag,long,EventTag,uint)
0x180002b2e  mov     dword ptr [rbp+pExceptionObject], edi
0x180002b31  lea     rdx, _TI2?AVOSException@@; pThrowInfo
0x180002b38  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180002b3c  call    _CxxThrowException_0
```
