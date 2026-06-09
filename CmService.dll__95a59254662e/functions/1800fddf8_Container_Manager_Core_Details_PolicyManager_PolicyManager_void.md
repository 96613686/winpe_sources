# Container::Manager::Core::Details::PolicyManager::~PolicyManager(void)

- ea: `0x1800fddf8`
- end: `0x1800fe086`
- name: `??1PolicyManager@Details@Core@Manager@Container@@QEAA@XZ`
- size: `654`
- prototype: `void __fastcall(Container::Manager::Core::Details::PolicyManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180076500`

## callees

- `0x180004fc4`
- `0x180016658`
- `0x18003e190`
- `0x1800493c8`
- `0x1800fddf8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800fde6a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800fde6a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800fde55`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800fde55`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800fde90`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800fe011`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800fde90`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800fe011`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fde19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fde19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fde40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fde40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fde7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fde7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fde9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fde9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fde25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fde25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fe026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fe026`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe045`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe059`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe045`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe059`

## pseudocode

```c
void __fastcall Container::Manager::Core::Details::PolicyManager::~PolicyManager(
        Container::Manager::Core::Details::PolicyManager *this)
{
  struct _TP_WAIT *v2; // rsi
  DWORD LastError; // ebx
  void *v4; // rcx
  void *v5; // rcx
  char *v6; // rcx
  char *v7; // rcx
  char *v8; // rcx
  char *v9; // rcx
  char *v10; // rcx
  char *v11; // rcx
  char *v12; // rcx
  char *v13; // rcx
  char *v14; // rcx
  struct _TP_WAIT *v15; // rcx
  void *v16; // rcx
  unsigned int v17; // r8d
  const char *v18; // r9
  HKEY v19; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_QWORD *)this + 3) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 5);
    GetCurrentThreadId();
    *((_BYTE *)this + 56) = 1;
    *((_DWORD *)this + 12) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 5);
    SetThreadpoolWait(*((PTP_WAIT *)this + 4), 0, 0);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 4), 1);
    v2 = (struct _TP_WAIT *)*((_QWORD *)this + 4);
    if ( v2 )
    {
      LastError = GetLastError();
      CloseThreadpoolWait(v2);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 4) = 0;
  }
  if ( *((_BYTE *)this + 824) )
  {
    v4 = (void *)*((_QWORD *)this + 100);
    if ( v4 != (void *)-1LL )
    {
      *((_QWORD *)this + 101) = v4;
      operator delete(v4, (const struct std::nothrow_t *)&std::nothrow);
    }
    v5 = (void *)*((_QWORD *)this + 97);
    if ( v5 != (void *)-1LL )
    {
      *((_QWORD *)this + 98) = v5;
      operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
    }
    utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>((char *)this + 712);
  }
  if ( *((_BYTE *)this + 664) )
    Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration((Container::Manager::Core::Details::PolicyManager *)((char *)this + 448));
  v6 = (char *)*((_QWORD *)this + 51);
  if ( v6 != (char *)this + 424 )
    operator delete(v6, (const struct std::nothrow_t *)&std::nothrow);
  v7 = (char *)*((_QWORD *)this + 47);
  if ( v7 != (char *)this + 392 )
    operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
  v8 = (char *)*((_QWORD *)this + 43);
  if ( v8 != (char *)this + 360 )
    operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
  v9 = (char *)*((_QWORD *)this + 37);
  if ( v9 != (char *)this + 312 )
    operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
  v10 = (char *)*((_QWORD *)this + 33);
  if ( v10 != (char *)this + 280 )
    operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
  v11 = (char *)*((_QWORD *)this + 29);
  if ( v11 != (char *)this + 248 )
    operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
  v12 = (char *)*((_QWORD *)this + 25);
  if ( v12 != (char *)this + 216 )
    operator delete(v12, (const struct std::nothrow_t *)&std::nothrow);
  v13 = (char *)*((_QWORD *)this + 21);
  if ( v13 != (char *)this + 184 )
    operator delete(v13, (const struct std::nothrow_t *)&std::nothrow);
  v14 = (char *)*((_QWORD *)this + 8);
  if ( v14 != (char *)this + 80 )
    operator delete(v14, (const struct std::nothrow_t *)&std::nothrow);
  v15 = (struct _TP_WAIT *)*((_QWORD *)this + 4);
  if ( v15 )
    CloseThreadpoolWait(v15);
  v16 = (void *)*((_QWORD *)this + 3);
  if ( v16 && !CloseHandle(v16) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
  if ( *((_BYTE *)this + 16) )
  {
    v19 = (HKEY)*((_QWORD *)this + 1);
    if ( v19 )
      RegCloseKey(v19);
  }
  if ( *(_QWORD *)this )
    RegCloseKey(*(HKEY *)this);
}

```

## disassembly

```asm
0x1800fddf8  mov     [rsp+arg_8], rbx
0x1800fddfd  mov     [rsp+arg_10], rsi
0x1800fde02  push    rdi
0x1800fde03  sub     rsp, 20h
0x1800fde07  cmp     qword ptr [rcx+18h], 0
0x1800fde0c  mov     rdi, rcx
0x1800fde0f  jz      loc_1800FDEB2
0x1800fde15  add     rcx, 28h ; '('; SRWLock
0x1800fde19  call    cs:__imp_AcquireSRWLockExclusive
0x1800fde20  nop     dword ptr [rax+rax+00h]
0x1800fde25  call    cs:__imp_GetCurrentThreadId
0x1800fde2c  nop     dword ptr [rax+rax+00h]
0x1800fde31  mov     byte ptr [rdi+38h], 1
0x1800fde35  lea     rcx, [rdi+28h]; SRWLock
0x1800fde39  mov     dword ptr [rdi+30h], 0
0x1800fde40  call    cs:__imp_ReleaseSRWLockExclusive
0x1800fde47  nop     dword ptr [rax+rax+00h]
0x1800fde4c  mov     rcx, [rdi+20h]; pwa
0x1800fde50  xor     r8d, r8d; pftTimeout
0x1800fde53  xor     edx, edx; h
0x1800fde55  call    cs:__imp_SetThreadpoolWait
0x1800fde5c  nop     dword ptr [rax+rax+00h]
0x1800fde61  mov     rcx, [rdi+20h]; pwa
0x1800fde65  mov     edx, 1; fCancelPendingCallbacks
0x1800fde6a  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800fde71  nop     dword ptr [rax+rax+00h]
0x1800fde76  mov     rsi, [rdi+20h]
0x1800fde7a  test    rsi, rsi
0x1800fde7d  jz      short loc_1800FDEAA
0x1800fde7f  call    cs:__imp_GetLastError
0x1800fde86  nop     dword ptr [rax+rax+00h]
0x1800fde8b  mov     rcx, rsi; pwa
0x1800fde8e  mov     ebx, eax
0x1800fde90  call    cs:__imp_CloseThreadpoolWait
0x1800fde97  nop     dword ptr [rax+rax+00h]
0x1800fde9c  mov     ecx, ebx; dwErrCode
0x1800fde9e  call    cs:__imp_SetLastError
0x1800fdea5  nop     dword ptr [rax+rax+00h]
0x1800fdeaa  mov     qword ptr [rdi+20h], 0
0x1800fdeb2  cmp     byte ptr [rdi+338h], 0
0x1800fdeb9  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800fdec0  jz      short loc_1800FDF06
0x1800fdec2  mov     rcx, [rdi+320h]; void *
0x1800fdec9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800fdecd  jz      short loc_1800FDEDE
0x1800fdecf  mov     rdx, rbx; struct std::nothrow_t *
0x1800fded2  mov     [rdi+328h], rcx
0x1800fded9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fdede  mov     rcx, [rdi+308h]; void *
0x1800fdee5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800fdee9  jz      short loc_1800FDEFA
0x1800fdeeb  mov     rdx, rbx; struct std::nothrow_t *
0x1800fdeee  mov     [rdi+310h], rcx
0x1800fdef5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fdefa  lea     rcx, [rdi+2C8h]
0x1800fdf01  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x1800fdf06  lea     rcx, [rdi+1C0h]; this
0x1800fdf0d  cmp     byte ptr [rcx+0D8h], 0
0x1800fdf14  jz      short loc_1800FDF1B
0x1800fdf16  call    ??1DebugConfiguration@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(void)
0x1800fdf1b  mov     rcx, [rdi+198h]; void *
0x1800fdf22  lea     rax, [rdi+1A8h]
0x1800fdf29  cmp     rcx, rax
0x1800fdf2c  jz      short loc_1800FDF36
0x1800fdf2e  mov     rdx, rbx; struct std::nothrow_t *
0x1800fdf31  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fdf36  mov     rcx, [rdi+178h]; void *
0x1800fdf3d  lea     rax, [rdi+188h]
0x1800fdf44  cmp     rcx, rax
0x1800fdf47  jz      short loc_1800FDF51
0x1800fdf49  mov     rdx, rbx; struct std::nothrow_t *
0x1800fdf4c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fdf51  mov     rcx, [rdi+158h]; void *
0x1800fdf58  lea     rax, [rdi+168h]
0x1800fdf5f  cmp     rcx, rax
0x1800fdf62  jz      short loc_1800FDF6C
0x1800fdf64  mov     rdx, rbx; struct std::nothrow_t *
0x1800fdf67  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fdf6c  mov     rcx, [rdi+128h]; void *
0x1800fdf73  lea     rax, [rdi+138h]
0x1800fdf7a  cmp     rcx, rax
0x1800fdf7d  jz      short loc_1800FDF87
0x1800fdf7f  mov     rdx, rbx; struct std::nothrow_t *
0x1800fdf82  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fdf87  mov     rcx, [rdi+108h]; void *
0x1800fdf8e  lea     rax, [rdi+118h]
0x1800fdf95  cmp     rcx, rax
0x1800fdf98  jz      short loc_1800FDFA2
0x1800fdf9a  mov     rdx, rbx; struct std::nothrow_t *
0x1800fdf9d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fdfa2  mov     rcx, [rdi+0E8h]; void *
0x1800fdfa9  lea     rax, [rdi+0F8h]
0x1800fdfb0  cmp     rcx, rax
0x1800fdfb3  jz      short loc_1800FDFBD
0x1800fdfb5  mov     rdx, rbx; struct std::nothrow_t *
0x1800fdfb8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fdfbd  mov     rcx, [rdi+0C8h]; void *
0x1800fdfc4  lea     rax, [rdi+0D8h]
0x1800fdfcb  cmp     rcx, rax
0x1800fdfce  jz      short loc_1800FDFD8
0x1800fdfd0  mov     rdx, rbx; struct std::nothrow_t *
0x1800fdfd3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fdfd8  mov     rcx, [rdi+0A8h]; void *
0x1800fdfdf  lea     rax, [rdi+0B8h]
0x1800fdfe6  cmp     rcx, rax
0x1800fdfe9  jz      short loc_1800FDFF3
0x1800fdfeb  mov     rdx, rbx; struct std::nothrow_t *
0x1800fdfee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fdff3  mov     rcx, [rdi+40h]; void *
0x1800fdff7  lea     rax, [rdi+50h]
0x1800fdffb  cmp     rcx, rax
0x1800fdffe  jz      short loc_1800FE008
0x1800fe000  mov     rdx, rbx; struct std::nothrow_t *
0x1800fe003  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fe008  mov     rcx, [rdi+20h]; pwa
0x1800fe00c  test    rcx, rcx
0x1800fe00f  jz      short loc_1800FE01D
0x1800fe011  call    cs:__imp_CloseThreadpoolWait
0x1800fe018  nop     dword ptr [rax+rax+00h]
0x1800fe01d  mov     rcx, [rdi+18h]; hObject
0x1800fe021  test    rcx, rcx
0x1800fe024  jz      short loc_1800FE036
0x1800fe026  call    cs:__imp_CloseHandle
0x1800fe02d  nop     dword ptr [rax+rax+00h]
0x1800fe032  test    eax, eax
0x1800fe034  jz      short loc_1800FE076
0x1800fe036  cmp     byte ptr [rdi+10h], 0
0x1800fe03a  jz      short loc_1800FE051
0x1800fe03c  mov     rcx, [rdi+8]; hKey
0x1800fe040  test    rcx, rcx
0x1800fe043  jz      short loc_1800FE051
0x1800fe045  call    cs:__imp_RegCloseKey
0x1800fe04c  nop     dword ptr [rax+rax+00h]
0x1800fe051  mov     rcx, [rdi]; hKey
0x1800fe054  test    rcx, rcx
0x1800fe057  jz      short loc_1800FE065
0x1800fe059  call    cs:__imp_RegCloseKey
0x1800fe060  nop     dword ptr [rax+rax+00h]
0x1800fe065  mov     rbx, [rsp+28h+arg_8]
0x1800fe06a  mov     rsi, [rsp+28h+arg_10]
0x1800fe06f  add     rsp, 20h
0x1800fe073  pop     rdi
0x1800fe074  retn
0x1800fe076  mov     rcx, [rsp+28h]; this
0x1800fe07b  mov     edx, 0A0Bh; void *
0x1800fe080  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
