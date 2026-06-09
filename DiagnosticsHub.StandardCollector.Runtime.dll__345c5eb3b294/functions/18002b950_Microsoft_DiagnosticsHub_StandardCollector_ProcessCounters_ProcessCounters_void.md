# Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::~ProcessCounters(void)

- ea: `0x18002b950`
- end: `0x18002ba5b`
- name: `??1ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ`
- size: `267`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180013908`
- `0x180013d1c`
- `0x180015048`
- `0x180015110`
- `0x180015920`
- `0x180016298`

## callees

- `0x180008408`
- `0x18002b950`
- `0x18004a078`
- `0x18004a0f8`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18002b96d`
- `KERNEL32!WaitForSingleObject` at `0x18002b9a3`
- `KERNEL32!WaitForSingleObject` at `0x18002b96d`
- `KERNEL32!WaitForSingleObject` at `0x18002b9a3`
- `KERNEL32!SetEvent` at `0x18002b98f`
- `KERNEL32!SetEvent` at `0x18002b98f`
- `KERNEL32!CloseHandle` at `0x18002ba3d`
- `KERNEL32!CloseHandle` at `0x18002ba3d`
- `KERNEL32!DeleteCriticalSection` at `0x18002b9fa`
- `KERNEL32!DeleteCriticalSection` at `0x18002ba25`
- `KERNEL32!DeleteCriticalSection` at `0x18002b9fa`
- `KERNEL32!DeleteCriticalSection` at `0x18002ba25`
- `KERNEL32!GetLastError` at `0x18002b9ad`
- `KERNEL32!GetLastError` at `0x18002b9ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::~ProcessCounters(
        Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters *this)
{
  void *v2; // rcx
  void *v3; // rcx
  _QWORD **v4; // rcx
  _QWORD *v5; // rcx
  _QWORD *v6; // rbx
  void *v7; // rcx

  v2 = (void *)*((_QWORD *)this + 5);
  if ( v2 && WaitForSingleObject(v2, 0) )
  {
    if ( *((_QWORD *)this + 5) && *((int *)this + 32) >= 0 )
      SetEvent(*((HANDLE *)this + 15));
    v3 = (void *)*((_QWORD *)this + 5);
    if ( v3 && WaitForSingleObject(v3, 0xFFFFFFFF) == -1 )
      GetLastError();
  }
  v4 = (_QWORD **)*((_QWORD *)this + 64);
  *v4[1] = 0;
  v5 = *v4;
  if ( v5 )
  {
    do
    {
      v6 = (_QWORD *)*v5;
      operator delete(v5);
      v5 = v6;
    }
    while ( v6 );
  }
  operator delete(*((void **)this + 64));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 472));
  `eh vector destructor iterator'(
    (char *)this + 184,
    0x48u,
    4u,
    (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::~CounterData);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  DiagHubCommon::HubTask<long,0>::~HubTask<long,0>((char *)this + 32);
  v7 = (void *)*((_QWORD *)this + 2);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x18002b950  mov     [rsp+arg_8], rbx
0x18002b955  mov     [rsp+arg_10], rsi
0x18002b95a  push    rdi
0x18002b95b  sub     rsp, 20h
0x18002b95f  mov     rdi, rcx
0x18002b962  mov     rcx, [rcx+28h]; hHandle
0x18002b966  test    rcx, rcx
0x18002b969  jz      short loc_18002B9B3
0x18002b96b  xor     edx, edx; dwMilliseconds
0x18002b96d  call    cs:__imp_WaitForSingleObject
0x18002b973  test    eax, eax
0x18002b975  jz      short loc_18002B9B3
0x18002b977  cmp     qword ptr [rdi+28h], 0
0x18002b97c  jz      short loc_18002B995
0x18002b97e  mov     eax, [rdi+80h]
0x18002b984  shr     eax, 1Fh
0x18002b987  test    al, al
0x18002b989  jnz     short loc_18002B995
0x18002b98b  mov     rcx, [rdi+78h]; hEvent
0x18002b98f  call    cs:__imp_SetEvent
0x18002b995  mov     rcx, [rdi+28h]; hHandle
0x18002b999  test    rcx, rcx
0x18002b99c  jz      short loc_18002B9B3
0x18002b99e  or      ebx, 0FFFFFFFFh
0x18002b9a1  mov     edx, ebx; dwMilliseconds
0x18002b9a3  call    cs:__imp_WaitForSingleObject
0x18002b9a9  cmp     eax, ebx
0x18002b9ab  jnz     short loc_18002B9B3
0x18002b9ad  call    cs:__imp_GetLastError
0x18002b9b3  mov     rcx, [rdi+200h]
0x18002b9ba  mov     rax, [rcx+8]
0x18002b9be  mov     qword ptr [rax], 0
0x18002b9c5  mov     rcx, [rcx]; Block
0x18002b9c8  test    rcx, rcx
0x18002b9cb  jz      short loc_18002B9E2
0x18002b9cd  mov     rbx, [rcx]
0x18002b9d0  mov     edx, 20h ; ' '
0x18002b9d5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b9da  mov     rcx, rbx
0x18002b9dd  test    rbx, rbx
0x18002b9e0  jnz     short loc_18002B9CD
0x18002b9e2  mov     edx, 20h ; ' '
0x18002b9e7  mov     rcx, [rdi+200h]; Block
0x18002b9ee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b9f3  lea     rcx, [rdi+1D8h]; lpCriticalSection
0x18002b9fa  call    cs:__imp_DeleteCriticalSection
0x18002ba00  nop
0x18002ba01  lea     rcx, [rdi+0B8h]; void *
0x18002ba08  lea     r9, ??1CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; void (*)(void *)
0x18002ba0f  mov     edx, 48h ; 'H'; unsigned __int64
0x18002ba14  lea     r8d, [rdx-44h]; unsigned __int64
0x18002ba18  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002ba1d  nop
0x18002ba1e  lea     rcx, [rdi+90h]; lpCriticalSection
0x18002ba25  call    cs:__imp_DeleteCriticalSection
0x18002ba2b  lea     rcx, [rdi+20h]
0x18002ba2f  call    ??1?$HubTask@J$0A@@DiagHubCommon@@UEAA@XZ; DiagHubCommon::HubTask<long,0>::~HubTask<long,0>(void)
0x18002ba34  mov     rcx, [rdi+10h]; hObject
0x18002ba38  test    rcx, rcx
0x18002ba3b  jz      short loc_18002BA4B
0x18002ba3d  call    cs:__imp_CloseHandle
0x18002ba43  mov     qword ptr [rdi+10h], 0
0x18002ba4b  mov     rbx, [rsp+28h+arg_8]
0x18002ba50  mov     rsi, [rsp+28h+arg_10]
0x18002ba55  add     rsp, 20h
0x18002ba59  pop     rdi
0x18002ba5a  retn
```
