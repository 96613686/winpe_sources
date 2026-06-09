# AppV::Client::Host::UserManagerImpl::~UserManagerImpl(void)

- ea: `0x140048354`
- end: `0x1400484be`
- name: `??1UserManagerImpl@Host@Client@AppV@@UEAA@XZ`
- size: `362`
- prototype: `void __fastcall(AppV::Client::Host::UserManagerImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140048650`

## callees

- `0x140004558`
- `0x14001624c`
- `0x140048354`
- `0x14006a010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400483f9`
- `KERNEL32!DeleteCriticalSection` at `0x140048442`
- `KERNEL32!DeleteCriticalSection` at `0x1400483f9`
- `KERNEL32!DeleteCriticalSection` at `0x140048442`
- `KERNEL32!GetCurrentThreadId` at `0x140048390`
- `KERNEL32!GetCurrentThreadId` at `0x140048390`
- `KERNEL32!LeaveCriticalSection` at `0x1400483c9`
- `KERNEL32!LeaveCriticalSection` at `0x1400483c9`
- `KERNEL32!EnterCriticalSection` at `0x140048377`
- `KERNEL32!EnterCriticalSection` at `0x140048377`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AppV::Client::Host::UserManagerImpl::~UserManagerImpl(AppV::Client::Host::UserManagerImpl *this)
{
  int v2; // eax
  volatile signed __int32 *v3; // rbx
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v5; // rcx

  *(_QWORD *)this = &AppV::Client::Host::UserManagerImpl::`vftable';
  EnterCriticalSection(&AppV::Client::Host::UserManagerImpl::st_lockSingleton);
  v2 = qword_1400B0FA8 + 1;
  LODWORD(qword_1400B0FA8) = v2;
  if ( v2 == 1 )
  {
    HIDWORD(qword_1400B0FA8) = GetCurrentThreadId();
    v2 = qword_1400B0FA8;
  }
  AppV::Client::Host::UserManagerImpl::st_singleton = 0;
  LODWORD(qword_1400B0FA8) = v2 - 1;
  if ( v2 == 1 )
    qword_1400B0FA8 = 0;
  LeaveCriticalSection(&AppV::Client::Host::UserManagerImpl::st_lockSingleton);
  std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>,void *>>>(
    (char *)this + 168,
    (char *)this + 168,
    *(_QWORD *)(*((_QWORD *)this + 21) + 8LL));
  operator delete(*((void **)this + 21));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 3);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 14);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  if ( v5 && _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
  *(_QWORD *)this = &AppV::Client::Host::UserManager::`vftable';
}

```

## disassembly

```asm
0x140048354  mov     [rsp+arg_8], rbx
0x140048359  mov     [rsp+arg_10], rsi
0x14004835e  push    rdi
0x14004835f  sub     rsp, 20h
0x140048363  lea     rax, ??_7UserManagerImpl@Host@Client@AppV@@6B@; const AppV::Client::Host::UserManagerImpl::`vftable'
0x14004836a  mov     rdi, rcx
0x14004836d  mov     [rcx], rax
0x140048370  lea     rcx, ?st_lockSingleton@UserManagerImpl@Host@Client@AppV@@0Vcritical_section@shared@softricity@@A; lpCriticalSection
0x140048377  call    cs:__imp_EnterCriticalSection
0x14004837d  mov     eax, dword ptr cs:qword_1400B0FA8
0x140048383  inc     eax
0x140048385  mov     dword ptr cs:qword_1400B0FA8, eax
0x14004838b  cmp     eax, 1
0x14004838e  jnz     short loc_1400483A2
0x140048390  call    cs:__imp_GetCurrentThreadId
0x140048396  mov     dword ptr cs:qword_1400B0FA8+4, eax
0x14004839c  mov     eax, dword ptr cs:qword_1400B0FA8
0x1400483a2  sub     eax, 1
0x1400483a5  mov     cs:?st_singleton@UserManagerImpl@Host@Client@AppV@@0PEAV1234@EA, 0; AppV::Client::Host::UserManagerImpl * AppV::Client::Host::UserManagerImpl::st_singleton
0x1400483b0  mov     dword ptr cs:qword_1400B0FA8, eax
0x1400483b6  jnz     short loc_1400483C2
0x1400483b8  mov     dword ptr cs:qword_1400B0FA8+4, 0
0x1400483c2  lea     rcx, ?st_lockSingleton@UserManagerImpl@Host@Client@AppV@@0Vcritical_section@shared@softricity@@A; lpCriticalSection
0x1400483c9  call    cs:__imp_LeaveCriticalSection
0x1400483cf  lea     rbx, [rdi+0A8h]
0x1400483d6  mov     r8, [rbx]
0x1400483d9  mov     rdx, rbx
0x1400483dc  mov     rcx, rbx
0x1400483df  mov     r8, [r8+8]
0x1400483e3  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>,void *>> &,std::_Tree_node<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>,void *> *)
0x1400483e8  mov     rcx, [rbx]; Block
0x1400483eb  mov     edx, 38h ; '8'
0x1400483f0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400483f5  lea     rcx, [rdi+78h]; lpCriticalSection
0x1400483f9  call    cs:__imp_DeleteCriticalSection
0x1400483ff  mov     rbx, [rdi+70h]
0x140048403  or      esi, 0FFFFFFFFh
0x140048406  test    rbx, rbx
0x140048409  jz      short loc_14004843E
0x14004840b  mov     eax, esi
0x14004840d  lock xadd [rbx+8], eax
0x140048412  add     eax, esi
0x140048414  jnz     short loc_14004843E
0x140048416  mov     rax, [rbx]
0x140048419  mov     rcx, rbx
0x14004841c  mov     rax, [rax]
0x14004841f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048424  mov     eax, esi
0x140048426  lock xadd [rbx+0Ch], eax
0x14004842b  add     eax, esi
0x14004842d  jnz     short loc_14004843E
0x14004842f  mov     rax, [rbx]
0x140048432  mov     rcx, rbx
0x140048435  mov     rax, [rax+8]
0x140048439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004843e  lea     rcx, [rdi+28h]; lpCriticalSection
0x140048442  call    cs:__imp_DeleteCriticalSection
0x140048448  mov     rbx, [rdi+20h]
0x14004844c  test    rbx, rbx
0x14004844f  jz      short loc_140048484
0x140048451  mov     eax, esi
0x140048453  lock xadd [rbx+8], eax
0x140048458  add     eax, esi
0x14004845a  jnz     short loc_140048484
0x14004845c  mov     rax, [rbx]
0x14004845f  mov     rcx, rbx
0x140048462  mov     rax, [rax]
0x140048465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004846a  mov     eax, esi
0x14004846c  lock xadd [rbx+0Ch], eax
0x140048471  add     eax, esi
0x140048473  jnz     short loc_140048484
0x140048475  mov     rax, [rbx]
0x140048478  mov     rcx, rbx
0x14004847b  mov     rax, [rax+8]
0x14004847f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048484  mov     rcx, [rdi+10h]
0x140048488  test    rcx, rcx
0x14004848b  jz      short loc_1400484A4
0x14004848d  mov     eax, esi
0x14004848f  lock xadd [rcx+0Ch], eax
0x140048494  add     eax, esi
0x140048496  jnz     short loc_1400484A4
0x140048498  mov     rax, [rcx]
0x14004849b  mov     rax, [rax+8]
0x14004849f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400484a4  mov     rbx, [rsp+28h+arg_8]
0x1400484a9  lea     rax, ??_7UserManager@Host@Client@AppV@@6B@; const AppV::Client::Host::UserManager::`vftable'
0x1400484b0  mov     rsi, [rsp+28h+arg_10]
0x1400484b5  mov     [rdi], rax
0x1400484b8  add     rsp, 20h
0x1400484bc  pop     rdi
0x1400484bd  retn
```
