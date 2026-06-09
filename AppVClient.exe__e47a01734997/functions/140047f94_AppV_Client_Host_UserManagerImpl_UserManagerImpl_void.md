# AppV::Client::Host::UserManagerImpl::UserManagerImpl(void)

- ea: `0x140047f94`
- end: `0x140048126`
- name: `??0UserManagerImpl@Host@Client@AppV@@AEAA@XZ`
- size: `402`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140049250`

## callees

- `0x1400042a4`
- `0x140047f94`
- `0x140052f64`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400480d9`
- `KERNEL32!GetCurrentThreadId` at `0x1400480d9`
- `KERNEL32!InitializeCriticalSection` at `0x140047fcd`
- `KERNEL32!InitializeCriticalSection` at `0x140047feb`
- `KERNEL32!InitializeCriticalSection` at `0x140047fcd`
- `KERNEL32!InitializeCriticalSection` at `0x140047feb`
- `KERNEL32!LeaveCriticalSection` at `0x14004810b`
- `KERNEL32!LeaveCriticalSection` at `0x14004810b`
- `KERNEL32!EnterCriticalSection` at `0x1400480c0`
- `KERNEL32!EnterCriticalSection` at `0x1400480c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _RTL_CRITICAL_SECTION *__fastcall AppV::Client::Host::UserManagerImpl::UserManagerImpl(
        struct _RTL_CRITICAL_SECTION *this)
{
  _QWORD *v2; // rax
  AppV::Client::Host::SessionQueueImpl *v3; // rax
  volatile signed __int32 *SpinCount; // rbx
  int v5; // eax
  _DWORD *v7; // [rsp+30h] [rbp+8h]
  __int64 v8; // [rsp+38h] [rbp+10h]

  *(_QWORD *)&this->LockCount = 0;
  this->OwningThread = 0;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&AppV::Client::Host::UserManagerImpl::`vftable';
  this->LockSemaphore = 0;
  this->SpinCount = 0;
  InitializeCriticalSection(this + 1);
  this[2].DebugInfo = 0;
  this[2].LockCount = 0;
  this[2].OwningThread = 0;
  this[2].LockSemaphore = 0;
  this[2].SpinCount = 0;
  InitializeCriticalSection(this + 3);
  this[4].DebugInfo = 0;
  *(_QWORD *)&this[4].LockCount = 0;
  this[4].OwningThread = 0;
  v2 = operator new(0x38u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *(_QWORD *)&this[4].LockCount = v2;
  v3 = (AppV::Client::Host::SessionQueueImpl *)operator new(0x60u);
  v8 = AppV::Client::Host::SessionQueueImpl::SessionQueueImpl(v3);
  v7 = operator new(0x18u);
  *(_OWORD *)v7 = 0;
  v7[2] = 1;
  v7[3] = 1;
  *(_QWORD *)v7 = &std::_Ref_count<AppV::Client::Host::SessionQueueImpl>::`vftable';
  *((_QWORD *)v7 + 2) = v8;
  this->LockSemaphore = (HANDLE)v8;
  SpinCount = (volatile signed __int32 *)this->SpinCount;
  this->SpinCount = (ULONG_PTR)v7;
  if ( SpinCount )
  {
    if ( _InterlockedExchangeAdd(SpinCount + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))SpinCount)(SpinCount);
      if ( _InterlockedExchangeAdd(SpinCount + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)SpinCount + 8LL))(SpinCount);
    }
  }
  EnterCriticalSection(&AppV::Client::Host::UserManagerImpl::st_lockSingleton);
  v5 = qword_1400B0FA8 + 1;
  LODWORD(qword_1400B0FA8) = v5;
  if ( v5 == 1 )
  {
    HIDWORD(qword_1400B0FA8) = GetCurrentThreadId();
    v5 = qword_1400B0FA8;
  }
  AppV::Client::Host::UserManagerImpl::st_singleton = (struct AppV::Client::Host::UserManagerImpl *)this;
  LODWORD(qword_1400B0FA8) = v5 - 1;
  if ( v5 == 1 )
    qword_1400B0FA8 = 0;
  LeaveCriticalSection(&AppV::Client::Host::UserManagerImpl::st_lockSingleton);
  return this;
}

```

## disassembly

```asm
0x140047f94  mov     [rsp+arg_10], rbx
0x140047f99  mov     [rsp+arg_18], rdi
0x140047f9e  mov     [rsp+arg_0], rcx
0x140047fa3  push    r14
0x140047fa5  sub     rsp, 20h
0x140047fa9  mov     rdi, rcx
0x140047fac  xor     r14d, r14d
0x140047faf  mov     [rcx+8], r14
0x140047fb3  mov     [rcx+10h], r14
0x140047fb7  lea     rax, ??_7UserManagerImpl@Host@Client@AppV@@6B@; const AppV::Client::Host::UserManagerImpl::`vftable'
0x140047fbe  mov     [rcx], rax
0x140047fc1  mov     [rcx+18h], r14
0x140047fc5  mov     [rcx+20h], r14
0x140047fc9  add     rcx, 28h ; '('; lpCriticalSection
0x140047fcd  call    cs:__imp_InitializeCriticalSection
0x140047fd3  mov     [rdi+50h], r14
0x140047fd7  mov     [rdi+58h], r14d
0x140047fdb  mov     [rdi+60h], r14
0x140047fdf  mov     [rdi+68h], r14
0x140047fe3  mov     [rdi+70h], r14
0x140047fe7  lea     rcx, [rdi+78h]; lpCriticalSection
0x140047feb  call    cs:__imp_InitializeCriticalSection
0x140047ff1  mov     [rdi+0A0h], r14
0x140047ff8  lea     rbx, [rdi+0A8h]
0x140047fff  mov     [rbx], r14
0x140048002  mov     [rbx+8], r14
0x140048006  lea     ecx, [r14+38h]; Size
0x14004800a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004800f  mov     [rax], rax
0x140048012  mov     [rax+8], rax
0x140048016  mov     [rax+10h], rax
0x14004801a  mov     word ptr [rax+18h], 101h
0x140048020  mov     [rbx], rax
0x140048023  lea     ecx, [r14+60h]; Size
0x140048027  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004802c  mov     [rsp+28h+arg_8], rax
0x140048031  mov     rcx, rax; this
0x140048034  call    ??0SessionQueueImpl@Host@Client@AppV@@AEAA@XZ; AppV::Client::Host::SessionQueueImpl::SessionQueueImpl(void)
0x140048039  mov     rbx, rax
0x14004803c  mov     [rsp+28h+arg_8], rax
0x140048041  lea     ecx, [r14+18h]; Size
0x140048045  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004804a  mov     [rsp+28h+arg_0], rax
0x14004804f  xorps   xmm0, xmm0
0x140048052  movups  xmmword ptr [rax], xmm0
0x140048055  mov     dword ptr [rax+8], 1
0x14004805c  mov     dword ptr [rax+0Ch], 1
0x140048063  lea     rcx, ??_7?$_Ref_count@VSessionQueueImpl@Host@Client@AppV@@@std@@6B@; const std::_Ref_count<AppV::Client::Host::SessionQueueImpl>::`vftable'
0x14004806a  mov     [rax], rcx
0x14004806d  mov     [rax+10h], rbx
0x140048071  mov     [rdi+18h], rbx
0x140048075  mov     rbx, [rdi+20h]
0x140048079  mov     [rdi+20h], rax
0x14004807d  test    rbx, rbx
0x140048080  jz      short loc_1400480B9
0x140048082  or      eax, 0FFFFFFFFh
0x140048085  lock xadd [rbx+8], eax
0x14004808a  cmp     eax, 1
0x14004808d  jnz     short loc_1400480B9
0x14004808f  mov     rax, [rbx]
0x140048092  mov     rcx, rbx
0x140048095  mov     rax, [rax]
0x140048098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004809d  or      eax, 0FFFFFFFFh
0x1400480a0  lock xadd [rbx+0Ch], eax
0x1400480a5  cmp     eax, 1
0x1400480a8  jnz     short loc_1400480B9
0x1400480aa  mov     rax, [rbx]
0x1400480ad  mov     rcx, rbx
0x1400480b0  mov     rax, [rax+8]
0x1400480b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400480b9  lea     rcx, ?st_lockSingleton@UserManagerImpl@Host@Client@AppV@@0Vcritical_section@shared@softricity@@A; lpCriticalSection
0x1400480c0  call    cs:__imp_EnterCriticalSection
0x1400480c6  mov     eax, dword ptr cs:qword_1400B0FA8
0x1400480cc  inc     eax
0x1400480ce  mov     dword ptr cs:qword_1400B0FA8, eax
0x1400480d4  cmp     eax, 1
0x1400480d7  jnz     short loc_1400480EB
0x1400480d9  call    cs:__imp_GetCurrentThreadId
0x1400480df  mov     dword ptr cs:qword_1400B0FA8+4, eax
0x1400480e5  mov     eax, dword ptr cs:qword_1400B0FA8
0x1400480eb  mov     cs:?st_singleton@UserManagerImpl@Host@Client@AppV@@0PEAV1234@EA, rdi; AppV::Client::Host::UserManagerImpl * AppV::Client::Host::UserManagerImpl::st_singleton
0x1400480f2  sub     eax, 1
0x1400480f5  mov     dword ptr cs:qword_1400B0FA8, eax
0x1400480fb  jnz     short loc_140048104
0x1400480fd  mov     dword ptr cs:qword_1400B0FA8+4, r14d
0x140048104  lea     rcx, ?st_lockSingleton@UserManagerImpl@Host@Client@AppV@@0Vcritical_section@shared@softricity@@A; lpCriticalSection
0x14004810b  call    cs:__imp_LeaveCriticalSection
0x140048111  nop
0x140048112  mov     rax, rdi
0x140048115  mov     rbx, [rsp+28h+arg_10]
0x14004811a  mov     rdi, [rsp+28h+arg_18]
0x14004811f  add     rsp, 20h
0x140048123  pop     r14
0x140048125  retn
```
