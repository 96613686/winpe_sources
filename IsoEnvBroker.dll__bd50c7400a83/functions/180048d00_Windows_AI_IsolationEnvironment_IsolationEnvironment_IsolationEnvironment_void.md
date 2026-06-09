# Windows::AI::IsolationEnvironment::IsolationEnvironment::~IsolationEnvironment(void)

- ea: `0x180048d00`
- end: `0x180048e1b`
- name: `??1IsolationEnvironment@0AI@Windows@@UEAA@XZ`
- size: `283`
- prototype: `void __fastcall(Windows::AI::IsolationEnvironment::IsolationEnvironment *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022ad0`

## callees

- `0x180012ad0`
- `0x180048d00`
- `0x18004b440`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048d7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048d7f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048d55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048d55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048d3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048d3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironment::~IsolationEnvironment(
        Windows::AI::IsolationEnvironment::IsolationEnvironment *this)
{
  RTL_SRWLOCK *v2; // rbx
  int v3; // edi
  DWORD CurrentThreadId; // ebp
  volatile signed __int32 *v5; // rbx
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rcx

  *(_QWORD *)this = &Windows::AI::IsolationEnvironment::IsolationEnvironment::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationEnvironment'};
  *((_QWORD *)this + 1) = &Windows::AI::IsolationEnvironment::IsolationEnvironment::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationEnvironment2,Windows::Foundation::IClosable>'};
  *((_QWORD *)this + 2) = &Windows::AI::IsolationEnvironment::IsolationEnvironment::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationEnvironment2'};
  *((_QWORD *)this + 3) = &Windows::AI::IsolationEnvironment::IsolationEnvironment::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
  v2 = 0;
  v3 = dword_1800B9160;
  CurrentThreadId = GetCurrentThreadId();
  if ( v3 != CurrentThreadId )
  {
    v2 = &g_lock;
    AcquireSRWLockExclusive(&g_lock);
    dword_1800B9160 = CurrentThreadId;
  }
  if ( *((_QWORD *)this + 6) )
    Windows::AI::IsolationEnvironment::IsolationEnvironment::_Cleanup_DropsLock(this);
  if ( v2 )
  {
    LODWORD(v2[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v2);
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 9);
  if ( v5 )
  {
    if ( !_InterlockedDecrement(v5 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( !_InterlockedDecrement(v5 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 7);
  if ( v6 )
  {
    if ( !_InterlockedDecrement(v6 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( !_InterlockedDecrement(v6 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v7 = *((_QWORD *)this + 5);
  if ( v7 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(2 * v7);
}

```

## disassembly

```asm
0x180048d00  push    rbx
0x180048d02  push    rbp
0x180048d03  push    rsi
0x180048d04  push    rdi
0x180048d05  sub     rsp, 28h
0x180048d09  mov     rsi, rcx
0x180048d0c  lea     rax, ??_7IsolationEnvironment@0AI@Windows@@6BIIsolationEnvironment@012@@; const Windows::AI::IsolationEnvironment::IsolationEnvironment::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationEnvironment'}
0x180048d13  mov     [rcx], rax
0x180048d16  lea     rax, ??_7IsolationEnvironment@0AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIIsolationEnvironment2@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@8@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::IsolationEnvironment::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationEnvironment2,Windows::Foundation::IClosable>'}
0x180048d1d  mov     [rcx+8], rax
0x180048d21  lea     rax, ??_7IsolationEnvironment@0AI@Windows@@6BIIsolationEnvironment2@012@@; const Windows::AI::IsolationEnvironment::IsolationEnvironment::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationEnvironment2'}
0x180048d28  mov     [rcx+10h], rax
0x180048d2c  lea     rax, ??_7IsolationEnvironment@0AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::IsolationEnvironment::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x180048d33  mov     [rcx+18h], rax
0x180048d37  xor     ebx, ebx
0x180048d39  mov     edi, cs:dword_1800B9160
0x180048d3f  call    cs:__imp_GetCurrentThreadId
0x180048d45  mov     ebp, eax
0x180048d47  cmp     edi, eax
0x180048d49  jz      short loc_180048D61
0x180048d4b  lea     rbx, ?g_lock@@3Vchecked_srwlock@@A; checked_srwlock g_lock
0x180048d52  mov     rcx, rbx; SRWLock
0x180048d55  call    cs:__imp_AcquireSRWLockExclusive
0x180048d5b  mov     cs:dword_1800B9160, ebp
0x180048d61  cmp     qword ptr [rsi+30h], 0
0x180048d66  jz      short loc_180048D70
0x180048d68  mov     rcx, rsi; this
0x180048d6b  call    ?_Cleanup_DropsLock@IsolationEnvironment@1AI@Windows@@AEAAXXZ; Windows::AI::IsolationEnvironment::IsolationEnvironment::_Cleanup_DropsLock(void)
0x180048d70  test    rbx, rbx
0x180048d73  jz      short loc_180048D85
0x180048d75  mov     dword ptr [rbx+8], 0
0x180048d7c  mov     rcx, rbx; SRWLock
0x180048d7f  call    cs:__imp_ReleaseSRWLockExclusive
0x180048d85  mov     rbx, [rsi+48h]
0x180048d89  or      edi, 0FFFFFFFFh
0x180048d8c  test    rbx, rbx
0x180048d8f  jz      short loc_180048DC4
0x180048d91  mov     eax, edi
0x180048d93  lock xadd [rbx+8], eax
0x180048d98  add     eax, edi
0x180048d9a  jnz     short loc_180048DC4
0x180048d9c  mov     rax, [rbx]
0x180048d9f  mov     rcx, rbx
0x180048da2  mov     rax, [rax]
0x180048da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048daa  mov     eax, edi
0x180048dac  lock xadd [rbx+0Ch], eax
0x180048db1  add     eax, edi
0x180048db3  jnz     short loc_180048DC4
0x180048db5  mov     rax, [rbx]
0x180048db8  mov     rcx, rbx
0x180048dbb  mov     rax, [rax+8]
0x180048dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048dc4  mov     rbx, [rsi+38h]
0x180048dc8  test    rbx, rbx
0x180048dcb  jz      short loc_180048E00
0x180048dcd  mov     eax, edi
0x180048dcf  lock xadd [rbx+8], eax
0x180048dd4  add     eax, edi
0x180048dd6  jnz     short loc_180048E00
0x180048dd8  mov     rax, [rbx]
0x180048ddb  mov     rcx, rbx
0x180048dde  mov     rax, [rax]
0x180048de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048de6  mov     eax, edi
0x180048de8  lock xadd [rbx+0Ch], eax
0x180048ded  add     eax, edi
0x180048def  jnz     short loc_180048E00
0x180048df1  mov     rax, [rbx]
0x180048df4  mov     rcx, rbx
0x180048df7  mov     rax, [rax+8]
0x180048dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e00  mov     rcx, [rsi+28h]
0x180048e04  test    rcx, rcx
0x180048e07  jns     short loc_180048E12
0x180048e09  add     rcx, rcx
0x180048e0c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180048e11  nop
0x180048e12  add     rsp, 28h
0x180048e16  pop     rdi
0x180048e17  pop     rsi
0x180048e18  pop     rbp
0x180048e19  pop     rbx
0x180048e1a  retn
```
