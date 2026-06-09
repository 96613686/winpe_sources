# CFlat::ComExportAdapter<IExportDispatcherQueueInterop,Microsoft::CoreUI::IExportDispatcherQueueInterop>::Release(void)

- ea: `0x180007230`
- end: `0x180007547`
- name: `?Release@?$ComExportAdapter@UIExportDispatcherQueueInterop@@V1CoreUI@Microsoft@@@CFlat@@UEAAKXZ`
- size: `791`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180006a30`
- `0x180006a4c`
- `0x180006c50`
- `0x180007198`
- `0x180007230`
- `0x180007d80`
- `0x1800089c0`
- `0x180010ed0`
- `0x18001ffcc`
- `0x180020df8`
- `0x180024980`
- `0x1800333f4`
- `0x18003950c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800072a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800072a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800074fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800074fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800074ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800074ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000731c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000731c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800072b9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800072f3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007308`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800073c7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000740f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007444`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800072b9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800072f3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007308`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800073c7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000740f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007444`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFlat::ComExportAdapter<IExportDispatcherQueueInterop,Microsoft::CoreUI::IExportDispatcherQueueInterop>::Release(
        __int64 a1)
{
  unsigned __int32 v2; // ebp
  struct Cn::Context *v3; // rdi
  struct Cn::Context *Value; // rbx
  char v5; // r14
  __int64 v6; // rsi
  int v7; // ecx
  int v8; // eax
  __int64 v9; // rbx
  char v10; // di
  System::Object *v12; // rcx
  const void *Interface; // rax
  System::Object *v14; // rcx
  void *v15; // rbx
  __int64 v17; // rax
  int v18; // edi
  HANDLE CurrentThread; // rax
  void *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v21; // [rsp+60h] [rbp+8h] BYREF
  __int64 v22; // [rsp+68h] [rbp+10h] BYREF

  v2 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 8));
  if ( !v2 )
  {
    if ( !Cn::Context::s_fTypeIsInitialized )
      CFlat::Abandonment::Fail((const char16_t *)a1, retaddr);
    v3 = *(struct Cn::Context **)(*(_QWORD *)(a1 + 16) + 16LL);
    if ( !v3 || !*((_BYTE *)v3 + 79) || TlsGetValue(Cn::Context::s_tlsStorage) != v3 )
    {
      Value = v3;
      v5 = 0;
      while ( 1 )
      {
        if ( Value )
        {
          v6 = *((_QWORD *)Value + 11);
          if ( v6 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 16));
            v7 = *(_DWORD *)(v6 + 60);
            *(_DWORD *)(v6 + 60) = v7 + 1;
            if ( !v7 )
            {
              *(_QWORD *)(v6 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
              *(_DWORD *)(v6 + 72) = GetCurrentThreadId();
            }
            v5 = 1;
          }
          v8 = *((_DWORD *)Value + 18);
          if ( !v8 )
          {
            if ( v3 && Value != v3 )
              CFlat::Abandonment::FailWithHR(-2018443006, retaddr, -2018443006);
            if ( v6 )
            {
              if ( TlsGetValue(Cn::Context::s_tlsStorage)
                || TlsGetValue(Cn::Context::s_tlsStorage) != Value && !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
              {
                CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode();
              }
              _InterlockedIncrement((volatile signed __int32 *)Value + 2);
            }
            break;
          }
          if ( v8 == 2 )
          {
            v17 = *((_QWORD *)Value + 12);
            if ( v17 )
              v18 = *(_DWORD *)(v17 + 152);
            else
              v18 = 0;
            if ( v18 != GetCurrentThreadId() )
            {
              CurrentThread = GetCurrentThread();
              WaitForSingleObjectEx(CurrentThread, 0x7530u, 0);
            }
            if ( Cn::Process::Host )
              (*(void (__fastcall **)(struct Cn::ICnHost *, void *))(*(_QWORD *)Cn::Process::Host + 56LL))(
                Cn::Process::Host,
                retaddr);
            CFlat::EntryExit::OnEndCallToCFlat(Value);
            break;
          }
          if ( v5 )
          {
            Cn::Engine::Lock::Leave((Cn::Engine::Lock *)v6);
            v5 = 0;
          }
        }
        if ( !v3 )
        {
          Value = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
          if ( !Value )
          {
            Value = Cn::Context::NoContext_GetThreadContextOrNullAndLock();
            if ( !Value )
            {
              LODWORD(v21) = -2018443007;
              if ( !Cn::Process::Host )
                break;
              (*(void (__fastcall **)(struct Cn::ICnHost *, __int64 *, void *))(*(_QWORD *)Cn::Process::Host + 48LL))(
                Cn::Process::Host,
                &v21,
                retaddr);
              if ( (int)v21 < 0 )
                break;
            }
          }
        }
      }
    }
    v22 = 0;
    v9 = *(_QWORD *)(a1 + 16);
    v10 = 0;
    if ( (*(_DWORD *)(v9 + 36))-- == 1 )
    {
      v21 = v9;
      std::_Hash<std::_Uset_traits<CFlat::ComExportAdapterContainer *,std::_Uhash_compare<CFlat::ComExportAdapterContainer *,std::hash<CFlat::ComExportAdapterContainer *>,std::equal_to<CFlat::ComExportAdapterContainer *>>,CFlat::Allocator<CFlat::ComExportAdapterContainer *>,0>>::_Erase<CFlat::ComExportAdapterContainer *>(
        *(_QWORD *)(v9 + 16) + 184LL,
        &v21);
      CFlat::EntryExit::ReleaseHostData(*(void **)(v9 + 16));
      *(_QWORD *)(v9 + 16) = 0;
      v12 = *(System::Object **)(v9 + 24);
      if ( v12 )
      {
        Interface = System::Object::GetInterfaceDispatcher$(
                      v12,
                      (const struct CFlat::InterfaceTypeId *)&CFlat::IComInterfaceHooks::TypeId$);
        if ( Interface )
          v10 = (*(__int64 (__fastcall **)(const void *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)Interface + 8LL))(
                  Interface,
                  *(_QWORD *)(v9 + 24),
                  0,
                  &v22);
        v14 = *(System::Object **)(v9 + 24);
        *(_QWORD *)(v9 + 24) = 0;
        if ( v14 )
          System::Object::Release$(v14);
      }
      else if ( !*(_DWORD *)(v9 + 32) )
      {
        CFlat::ComExportAdapterContainer::Delete((CFlat::ComExportAdapterContainer *)v9);
      }
    }
    v15 = TlsGetValue(Cn::Context::s_tlsStorage);
    CFlat::EntryExit::OnEndCallToCFlat(v15);
    if ( v10 )
      Cn::Context::UninitializeContext((struct Cn::Context *)v15);
  }
  return v2;
}

```

## disassembly

```asm
0x180007230  mov     [rsp+arg_10], rbx
0x180007235  mov     [rsp+arg_18], rbp
0x18000723a  push    rsi
0x18000723b  push    rdi
0x18000723c  push    r13
0x18000723e  push    r14
0x180007240  push    r15
0x180007242  sub     rsp, 30h
0x180007246  mov     r13, rcx
0x180007249  or      ebp, 0FFFFFFFFh
0x18000724c  lock xadd [rcx+8], ebp
0x180007251  sub     ebp, 1
0x180007254  jnz     loc_1800073E6
0x18000725a  mov     r15, [rsp+58h]
0x18000725f  cmp     cs:?s_fTypeIsInitialized@Context@Cn@@0_NA, bpl; bool Cn::Context::s_fTypeIsInitialized
0x180007266  jz      loc_1800074A2
0x18000726c  mov     rax, [rcx+10h]
0x180007270  mov     rdi, [rax+10h]
0x180007274  test    rdi, rdi
0x180007277  jnz     loc_1800073FF
0x18000727d  mov     rbx, rdi
0x180007280  xor     esi, esi
0x180007282  xor     r14b, r14b
0x180007285  test    rbx, rbx
0x180007288  jz      loc_180007435
0x18000728e  test    r14b, r14b
0x180007291  jnz     short loc_1800072CF
0x180007293  mov     rsi, [rbx+58h]
0x180007297  test    rsi, rsi
0x18000729a  jz      short loc_1800072CF
0x18000729c  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800072a0  call    cs:__imp_EnterCriticalSection
0x1800072a6  mov     ecx, [rsi+3Ch]
0x1800072a9  lea     eax, [rcx+1]
0x1800072ac  mov     [rsi+3Ch], eax
0x1800072af  test    ecx, ecx
0x1800072b1  jnz     short loc_1800072CC
0x1800072b3  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800072b9  call    cs:__imp_TlsGetValue
0x1800072bf  mov     [rsi+40h], rax
0x1800072c3  call    cs:__imp_GetCurrentThreadId
0x1800072c9  mov     [rsi+48h], eax
0x1800072cc  mov     r14b, 1
0x1800072cf  mov     eax, [rbx+48h]
0x1800072d2  test    eax, eax
0x1800072d4  jnz     loc_1800074C2
0x1800072da  test    rdi, rdi
0x1800072dd  jz      short loc_1800072E8
0x1800072df  cmp     rbx, rdi
0x1800072e2  jnz     loc_1800074AB
0x1800072e8  test    rsi, rsi
0x1800072eb  jz      short loc_18000732E
0x1800072ed  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800072f3  call    cs:__imp_TlsGetValue
0x1800072f9  test    rax, rax
0x1800072fc  jnz     loc_1800074BC
0x180007302  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007308  call    cs:__imp_TlsGetValue
0x18000730e  cmp     rax, rbx
0x180007311  jz      short loc_18000732A
0x180007313  mov     rdx, rbx; lpTlsValue
0x180007316  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000731c  call    cs:__imp_TlsSetValue
0x180007322  test    eax, eax
0x180007324  jz      loc_1800074BC
0x18000732a  lock inc dword ptr [rbx+8]
0x18000732e  mov     [rsp+58h+arg_8], 0
0x180007337  mov     rbx, [r13+10h]
0x18000733b  xor     dil, dil
0x18000733e  sub     dword ptr [rbx+24h], 1
0x180007342  jnz     short loc_1800073C1
0x180007344  mov     [rsp+58h+arg_0], rbx
0x180007349  mov     rcx, [rbx+10h]
0x18000734d  add     rcx, 0B8h
0x180007354  lea     rdx, [rsp+58h+arg_0]
0x180007359  call    ??$_Erase@PEAVComExportAdapterContainer@CFlat@@@?$_Hash@V?$_Uset_traits@PEAVComExportAdapterContainer@CFlat@@V?$_Uhash_compare@PEAVComExportAdapterContainer@CFlat@@U?$hash@PEAVComExportAdapterContainer@CFlat@@@std@@U?$equal_to@PEAVComExportAdapterContainer@CFlat@@@4@@std@@V?$Allocator@PEAVComExportAdapterContainer@CFlat@@@2@$0A@@std@@@std@@AEAA_KAEBQEAVComExportAdapterContainer@CFlat@@@Z; std::_Hash<std::_Uset_traits<CFlat::ComExportAdapterContainer *,std::_Uhash_compare<CFlat::ComExportAdapterContainer *,std::hash<CFlat::ComExportAdapterContainer *>,std::equal_to<CFlat::ComExportAdapterContainer *>>,CFlat::Allocator<CFlat::ComExportAdapterContainer *>,0>>::_Erase<CFlat::ComExportAdapterContainer *>(CFlat::ComExportAdapterContainer * const &)
0x18000735e  mov     rcx, [rbx+10h]; void *
0x180007362  call    ?ReleaseHostData@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::ReleaseHostData(void *)
0x180007367  mov     qword ptr [rbx+10h], 0
0x18000736f  mov     rcx, [rbx+18h]; this
0x180007373  test    rcx, rcx
0x180007376  jz      loc_180007530
0x18000737c  lea     rdx, ?TypeId$@IComInterfaceHooks@CFlat@@2U?$InterfaceTypeIdField@VIComInterfaceHooks@CFlat@@$0A@$0A@@2@B; struct CFlat::InterfaceTypeId *
0x180007383  call    ?GetInterfaceDispatcher$@Object@System@@QEBAPEBXPEBUInterfaceTypeId@CFlat@@@Z; System::Object::GetInterfaceDispatcher$(CFlat::InterfaceTypeId const *)
0x180007388  mov     rcx, rax
0x18000738b  test    rax, rax
0x18000738e  jz      short loc_1800073AB
0x180007390  mov     rax, [rax]
0x180007393  lea     r9, [rsp+58h+arg_8]
0x180007398  xor     r8d, r8d
0x18000739b  mov     rdx, [rbx+18h]
0x18000739f  mov     rax, [rax+8]
0x1800073a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073a8  mov     dil, al
0x1800073ab  mov     rcx, [rbx+18h]; this
0x1800073af  mov     qword ptr [rbx+18h], 0
0x1800073b7  test    rcx, rcx
0x1800073ba  jz      short loc_1800073C1
0x1800073bc  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x1800073c1  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800073c7  call    cs:__imp_TlsGetValue
0x1800073cd  mov     rbx, rax
0x1800073d0  mov     rcx, rax; void *
0x1800073d3  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x1800073d8  test    dil, dil
0x1800073db  jz      short loc_1800073E6
0x1800073dd  mov     rcx, rbx; struct Cn::Context *
0x1800073e0  call    ?UninitializeContext@Context@Cn@@SAXPEAV12@@Z; Cn::Context::UninitializeContext(Cn::Context *)
0x1800073e5  nop
0x1800073e6  mov     eax, ebp
0x1800073e8  mov     rbx, [rsp+58h+arg_10]
0x1800073ed  mov     rbp, [rsp+58h+arg_18]
0x1800073f2  add     rsp, 30h
0x1800073f6  pop     r15
0x1800073f8  pop     r14
0x1800073fa  pop     r13
0x1800073fc  pop     rdi
0x1800073fd  pop     rsi
0x1800073fe  retn
0x1800073ff  cmp     byte ptr [rdi+4Fh], 0
0x180007403  jz      loc_18000727D
0x180007409  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000740f  call    cs:__imp_TlsGetValue
0x180007415  cmp     rax, rdi
0x180007418  jnz     loc_18000727D
0x18000741e  jmp     loc_18000732E
0x180007423  test    r14b, r14b
0x180007426  jz      short loc_180007435
0x180007428  mov     rcx, rsi; this
0x18000742b  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x180007430  xor     esi, esi
0x180007432  xor     r14b, r14b
0x180007435  test    rdi, rdi
0x180007438  jnz     loc_180007285
0x18000743e  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007444  call    cs:__imp_TlsGetValue
0x18000744a  mov     rbx, rax
0x18000744d  test    rax, rax
0x180007450  jnz     loc_180007285
0x180007456  call    ?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ; Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
0x18000745b  mov     rbx, rax
0x18000745e  test    rax, rax
0x180007461  jnz     loc_180007285
0x180007467  mov     dword ptr [rsp+58h+arg_0], 87B10101h
0x18000746f  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x180007476  test    rcx, rcx
0x180007479  jz      loc_18000732E
0x18000747f  mov     rax, [rcx]
0x180007482  mov     r8, r15
0x180007485  lea     rdx, [rsp+58h+arg_0]
0x18000748a  mov     rax, [rax+30h]
0x18000748e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007493  cmp     dword ptr [rsp+58h+arg_0], ebx
0x180007497  jl      loc_18000732E
0x18000749d  jmp     loc_180007285
0x1800074a2  mov     rdx, r15; void *
0x1800074a5  call    ?Fail@Abandonment@CFlat@@SAXPEB_SPEAX@Z; CFlat::Abandonment::Fail(char16_t const *,void *)
0x1800074ab  mov     ecx, 87B10102h; int
0x1800074b0  mov     r8d, ecx; int
0x1800074b3  mov     rdx, r15; void *
0x1800074b6  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x1800074bc  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x1800074c2  sub     eax, 1
0x1800074c5  jz      loc_180007423
0x1800074cb  cmp     eax, 1
0x1800074ce  jnz     loc_180007423
0x1800074d4  mov     rax, [rbx+60h]
0x1800074d8  test    rax, rax
0x1800074db  jz      short loc_18000752C
0x1800074dd  mov     edi, [rax+98h]
0x1800074e3  call    cs:__imp_GetCurrentThreadId
0x1800074e9  cmp     edi, eax
0x1800074eb  jz      short loc_180007504
0x1800074ed  call    cs:__imp_GetCurrentThread
0x1800074f3  mov     rcx, rax; hHandle
0x1800074f6  xor     r8d, r8d; bAlertable
0x1800074f9  mov     edx, 7530h; dwMilliseconds
0x1800074fe  call    cs:__imp_WaitForSingleObjectEx
0x180007504  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x18000750b  test    rcx, rcx
0x18000750e  jz      short loc_18000751F
0x180007510  mov     rax, [rcx]
0x180007513  mov     rdx, r15
0x180007516  mov     rax, [rax+38h]
0x18000751a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000751f  mov     rcx, rbx; void *
0x180007522  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x180007527  jmp     loc_18000732E
0x18000752c  xor     edi, edi
0x18000752e  jmp     short loc_1800074E3
0x180007530  cmp     dword ptr [rbx+20h], 0
0x180007534  jnz     loc_1800073C1
0x18000753a  mov     rcx, rbx; this
0x18000753d  call    ?Delete@ComExportAdapterContainer@CFlat@@AEAAXXZ; CFlat::ComExportAdapterContainer::Delete(void)
0x180007542  jmp     loc_1800073C1
```
