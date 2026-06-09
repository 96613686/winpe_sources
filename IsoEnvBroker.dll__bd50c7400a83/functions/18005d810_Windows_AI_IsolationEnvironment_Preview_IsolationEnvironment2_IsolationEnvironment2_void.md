# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::~IsolationEnvironment2(void)

- ea: `0x18005d810`
- end: `0x18005d98c`
- name: `??1IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@UEAA@XZ`
- size: `380`
- prototype: `void __fastcall(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180055f80`

## callees

- `0x18001045c`
- `0x180012ad0`
- `0x18005d810`
- `0x18005efe0`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d893`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d893`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d870`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d870`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d85a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d85a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d921`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d939`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d921`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d939`

## pseudocode

```c
void __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::~IsolationEnvironment2(
        Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *this)
{
  RTL_SRWLOCK *v2; // rbx
  int v3; // edi
  DWORD CurrentThreadId; // ebp
  volatile signed __int32 *v5; // rbx
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rcx

  *(_QWORD *)this = &Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::`vftable';
  *((_QWORD *)this + 1) = &Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp2_ConfigId,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp3,Windows::Foundation::IClosable>'};
  *((_QWORD *)this + 3) = &Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp3'};
  *((_QWORD *)this + 4) = &Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
  v2 = 0;
  v3 = dword_1800B9160;
  CurrentThreadId = GetCurrentThreadId();
  if ( v3 != CurrentThreadId )
  {
    v2 = &g_lock;
    AcquireSRWLockExclusive(&g_lock);
    dword_1800B9160 = CurrentThreadId;
  }
  Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::_Cleanup_DropsLock(this);
  if ( v2 )
  {
    LODWORD(v2[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v2);
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 28);
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 26);
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  WindowsDeleteString(*((HSTRING *)this + 24));
  *((_QWORD *)this + 24) = 0;
  WindowsDeleteString(*((HSTRING *)this + 23));
  *((_QWORD *)this + 23) = 0;
  std::wstring::~wstring((char **)this + 19);
  std::wstring::~wstring((char **)this + 15);
  std::wstring::~wstring((char **)this + 11);
  std::wstring::~wstring((char **)this + 7);
  v7 = *((_QWORD *)this + 6);
  if ( v7 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(2 * v7);
}

```

## disassembly

```asm
0x18005d810  push    rbx
0x18005d812  push    rbp
0x18005d813  push    rsi
0x18005d814  push    rdi
0x18005d815  sub     rsp, 28h
0x18005d819  mov     rsi, rcx
0x18005d81c  lea     rax, ??_7IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@6B@; const Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::`vftable'
0x18005d823  mov     [rcx], rax
0x18005d826  lea     rax, ??_7IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@6BIWeakReferenceSource@@@; const Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::`vftable'{for `IWeakReferenceSource'}
0x18005d82d  mov     [rcx+8], rax
0x18005d831  lea     rax, ??_7IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIIsolationEnvironment_Exp2_ConfigId@Preview@IsolationEnvironment@AI@Windows@@UIIsolationEnvironment_Exp3@5678@UIClosable@Foundation@8@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp2_ConfigId,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp3,Windows::Foundation::IClosable>'}
0x18005d838  mov     [rcx+10h], rax
0x18005d83c  lea     rax, ??_7IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@6BIIsolationEnvironment_Exp3@1234@@; const Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp3'}
0x18005d843  mov     [rcx+18h], rax
0x18005d847  lea     rax, ??_7IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x18005d84e  mov     [rcx+20h], rax
0x18005d852  xor     ebx, ebx
0x18005d854  mov     edi, cs:dword_1800B9160
0x18005d85a  call    cs:__imp_GetCurrentThreadId
0x18005d860  mov     ebp, eax
0x18005d862  cmp     edi, eax
0x18005d864  jz      short loc_18005D87C
0x18005d866  lea     rbx, ?g_lock@@3Vchecked_srwlock@@A; checked_srwlock g_lock
0x18005d86d  mov     rcx, rbx; SRWLock
0x18005d870  call    cs:__imp_AcquireSRWLockExclusive
0x18005d876  mov     cs:dword_1800B9160, ebp
0x18005d87c  mov     rcx, rsi; this
0x18005d87f  call    ?_Cleanup_DropsLock@IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@AEAAJXZ; Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::_Cleanup_DropsLock(void)
0x18005d884  test    rbx, rbx
0x18005d887  jz      short loc_18005D899
0x18005d889  mov     dword ptr [rbx+8], 0
0x18005d890  mov     rcx, rbx; SRWLock
0x18005d893  call    cs:__imp_ReleaseSRWLockExclusive
0x18005d899  mov     rbx, [rsi+0E0h]
0x18005d8a0  or      edi, 0FFFFFFFFh
0x18005d8a3  test    rbx, rbx
0x18005d8a6  jz      short loc_18005D8DB
0x18005d8a8  mov     eax, edi
0x18005d8aa  lock xadd [rbx+8], eax
0x18005d8af  add     eax, edi
0x18005d8b1  jnz     short loc_18005D8DB
0x18005d8b3  mov     rax, [rbx]
0x18005d8b6  mov     rcx, rbx
0x18005d8b9  mov     rax, [rax]
0x18005d8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d8c1  mov     eax, edi
0x18005d8c3  lock xadd [rbx+0Ch], eax
0x18005d8c8  add     eax, edi
0x18005d8ca  jnz     short loc_18005D8DB
0x18005d8cc  mov     rax, [rbx]
0x18005d8cf  mov     rcx, rbx
0x18005d8d2  mov     rax, [rax+8]
0x18005d8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d8db  mov     rbx, [rsi+0D0h]
0x18005d8e2  test    rbx, rbx
0x18005d8e5  jz      short loc_18005D91A
0x18005d8e7  mov     eax, edi
0x18005d8e9  lock xadd [rbx+8], eax
0x18005d8ee  add     eax, edi
0x18005d8f0  jnz     short loc_18005D91A
0x18005d8f2  mov     rax, [rbx]
0x18005d8f5  mov     rcx, rbx
0x18005d8f8  mov     rax, [rax]
0x18005d8fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d900  mov     eax, edi
0x18005d902  lock xadd [rbx+0Ch], eax
0x18005d907  add     eax, edi
0x18005d909  jnz     short loc_18005D91A
0x18005d90b  mov     rax, [rbx]
0x18005d90e  mov     rcx, rbx
0x18005d911  mov     rax, [rax+8]
0x18005d915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d91a  mov     rcx, [rsi+0C0h]; string
0x18005d921  call    cs:__imp_WindowsDeleteString
0x18005d927  mov     qword ptr [rsi+0C0h], 0
0x18005d932  mov     rcx, [rsi+0B8h]; string
0x18005d939  call    cs:__imp_WindowsDeleteString
0x18005d93f  mov     qword ptr [rsi+0B8h], 0
0x18005d94a  lea     rcx, [rsi+98h]
0x18005d951  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d956  lea     rcx, [rsi+78h]
0x18005d95a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d95f  lea     rcx, [rsi+58h]
0x18005d963  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d968  lea     rcx, [rsi+38h]
0x18005d96c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d971  mov     rcx, [rsi+30h]
0x18005d975  test    rcx, rcx
0x18005d978  jns     short loc_18005D983
0x18005d97a  add     rcx, rcx
0x18005d97d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18005d982  nop
0x18005d983  add     rsp, 28h
0x18005d987  pop     rdi
0x18005d988  pop     rsi
0x18005d989  pop     rbp
0x18005d98a  pop     rbx
0x18005d98b  retn
```
