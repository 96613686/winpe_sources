# ConnectedStorage::Service::Destroy(void)

- ea: `0x180014850`
- end: `0x180014901`
- name: `?Destroy@Service@ConnectedStorage@@SAJXZ`
- size: `177`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x18000c41c`

## callees

- `0x180003c70`
- `0x180003c94`
- `0x18000cb9c`
- `0x1800127f8`
- `0x180014850`
- `0x1800154cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800148d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800148d7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180014892`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180014892`

## pseudocode

```c
__int64 __fastcall ConnectedStorage::Service::Destroy(__int64 a1, __int64 a2, char *a3)
{
  struct ConnectedStorage::Mutex *v3; // rbx
  LPCRITICAL_SECTION lpCriticalSection[11]; // [rsp+28h] [rbp-70h] BYREF

  ConnectedStorage::Mutex::Lock::Lock((ConnectedStorage::Mutex::Lock *)lpCriticalSection, &stru_1800C0938, a3);
  if ( pwk )
    WaitForThreadpoolWorkCallbacks(pwk, 0);
  v3 = qword_1800C0858;
  if ( qword_1800C0858 )
  {
    ConnectedStorage::Service::~Service(qword_1800C0858);
    operator delete(v3, 0x198u);
  }
  qword_1800C0858 = 0;
  if ( !ConnectedStorage::gShutdown )
    ConnectedStorage::Service::InitiateShutdownW();
  LeaveCriticalSection(lpCriticalSection[0]);
  return 0;
}

```

## disassembly

```asm
0x180014850  push    rbx
0x180014852  sub     rsp, 90h
0x180014859  mov     rax, cs:__security_cookie
0x180014860  xor     rax, rsp
0x180014863  mov     [rsp+98h+var_18], rax
0x18001486b  mov     [rsp+98h+var_78], 0
0x180014873  lea     rdx, stru_1800C0938; struct ConnectedStorage::Mutex *
0x18001487a  lea     rcx, [rsp+98h+lpCriticalSection]; this
0x18001487f  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180014884  mov     rcx, cs:pwk; pwk
0x18001488b  test    rcx, rcx
0x18001488e  jz      short loc_180014898
0x180014890  xor     edx, edx; fCancelPendingCallbacks
0x180014892  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180014898  mov     rbx, cs:qword_1800C0858
0x18001489f  test    rbx, rbx
0x1800148a2  jz      short loc_1800148B9
0x1800148a4  mov     rcx, rbx; this
0x1800148a7  call    ??1Service@ConnectedStorage@@AEAA@XZ; ConnectedStorage::Service::~Service(void)
0x1800148ac  mov     edx, 198h; unsigned __int64
0x1800148b1  mov     rcx, rbx; void *
0x1800148b4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800148b9  mov     cs:qword_1800C0858, 0
0x1800148c4  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, 0; bool ConnectedStorage::gShutdown
0x1800148cb  jnz     short loc_1800148D2
0x1800148cd  call    ?InitiateShutdownW@Service@ConnectedStorage@@SAXXZ; ConnectedStorage::Service::InitiateShutdownW(void)
0x1800148d2  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x1800148d7  call    cs:__imp_LeaveCriticalSection
0x1800148dd  nop
0x1800148de  jmp     short loc_1800148E4
0x1800148e0  jmp     short loc_1800148E4
0x1800148e2  jmp     short $+2
0x1800148e4  mov     eax, [rsp+98h+var_78]
0x1800148e8  mov     rcx, [rsp+98h+var_18]
0x1800148f0  xor     rcx, rsp; StackCookie
0x1800148f3  call    __security_check_cookie
0x1800148f8  add     rsp, 90h
0x1800148ff  pop     rbx
0x180014900  retn
```
