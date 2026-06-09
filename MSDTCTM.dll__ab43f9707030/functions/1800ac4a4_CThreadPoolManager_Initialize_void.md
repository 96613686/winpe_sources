# CThreadPoolManager::Initialize(void)

- ea: `0x1800ac4a4`
- end: `0x1800ac6fa`
- name: `?Initialize@CThreadPoolManager@@QEAAJXZ`
- size: `598`
- prototype: `__int64 __fastcall(CThreadPoolManager *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008a6a8`
- `0x1800b510c`

## callees

- `0x1800063b0`
- `0x18001f598`
- `0x1800240f0`
- `0x1800240fc`
- `0x1800ac4a4`
- `0x1800b83ee`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800ac530`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800ac530`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ac66f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ac66f`

## string_xrefs

- `0x1800ac4c0`: `com\complus\dtc\dtc\tipgw\commgr\src\threadpoolmanager.cpp`
- `0x1800ac6bc`: `com\complus\dtc\dtc\tipgw\commgr\src\threadpoolmanager.cpp`
- `0x1800ac4b4`: `Initializing TIP thread pool`
- `0x1800ac4d6`: `CThreadPoolManager::Initialize`
- `0x1800ac6c3`: `CThreadPoolManager::Initialize`
- `0x1800ac6a6`: `TIP thread pool successfully created`

## pseudocode

```c
__int64 __fastcall CThreadPoolManager::Initialize(CThreadPoolManager *this)
{
  CThreadPoolManager *v1; // rcx
  __int64 result; // rax
  unsigned int v3; // ebp
  void **v4; // rax
  void **v5; // r15
  int v6; // esi
  int v7; // edi
  void *v8; // r14
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rbx
  __int64 v12; // rax
  int i; // edi
  HANDLE Thread; // rax
  _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-68h] BYREF

  memset(&SystemInfo, 0, sizeof(SystemInfo));
  TraceStringInline(
    10,
    4,
    L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\threadpoolmanager.cpp",
    49,
    L"CThreadPoolManager::Initialize",
    0,
    L"Initializing TIP thread pool");
  if ( CThreadPoolManager::m_fThreadPoolReady )
    return 0;
  if ( !CThreadPoolManager::m_fThreadPoolCreatable )
    return 2147500037LL;
  result = CThreadPoolManager::CreateCompletionPort(v1);
  v3 = result;
  if ( (int)result < 0 )
    return result;
  GetSystemInfo(&SystemInfo);
  CThreadPoolManager::m_nThreadPoolCount = 2 * SystemInfo.dwNumberOfProcessors;
  CThreadPoolManager::m_rgThreadPool = operator new[](saturated_mul(2 * SystemInfo.dwNumberOfProcessors, 4u));
  if ( !CThreadPoolManager::m_rgThreadPool )
    return 2147942414LL;
  v4 = (void **)operator new[](saturated_mul(CThreadPoolManager::m_nThreadPoolCount, 8u));
  CThreadPoolManager::m_rgThreadHandleArray = v4;
  v5 = v4;
  if ( !v4 )
  {
    operator delete(CThreadPoolManager::m_rgThreadPool);
    CThreadPoolManager::m_rgThreadPool = 0;
    return 2147942414LL;
  }
  v6 = CThreadPoolManager::m_nThreadPoolCount;
  v7 = 0;
  v8 = CThreadPoolManager::m_rgThreadPool;
  if ( CThreadPoolManager::m_nThreadPoolCount >= 2 )
  {
    v9 = CThreadPoolManager::m_nThreadPoolCount - 1;
    if ( CThreadPoolManager::m_rgThreadPool > &v4[v9]
      || (char *)CThreadPoolManager::m_rgThreadPool + 4 * v9 < (char *)v4 )
    {
      v10 = CThreadPoolManager::m_nThreadPoolCount - CThreadPoolManager::m_nThreadPoolCount % 2;
      do
        v7 += 2;
      while ( v7 < v10 );
      v11 = (v10 + 1) / 2;
      memset_0(v5, 0, 16 * v11);
      memset_0(v8, 0, 8 * v11);
    }
  }
  while ( v7 < v6 )
  {
    v12 = v7++;
    v5[v12] = 0;
    *((_DWORD *)v8 + v12) = 0;
  }
  for ( i = 0; i < v6; ++i )
  {
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CThreadPoolManager::ThreadRoutine, 0, 1u, (LPDWORD)v8 + i);
    CThreadPoolManager::m_rgThreadHandleArray[i] = Thread;
    if ( !Thread )
      return 2147500037LL;
    v6 = CThreadPoolManager::m_nThreadPoolCount;
    v8 = CThreadPoolManager::m_rgThreadPool;
  }
  CThreadPoolManager::m_fThreadPoolReady = 1;
  CThreadPoolManager::m_fThreadPoolCreatable = 0;
  TraceStringInline(
    10,
    4,
    L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\threadpoolmanager.cpp",
    128,
    L"CThreadPoolManager::Initialize",
    0,
    L"TIP thread pool successfully created");
  return v3;
}

```

## disassembly

```asm
0x1800ac4a4  push    rbx
0x1800ac4a6  push    rbp
0x1800ac4a7  push    rsi
0x1800ac4a8  push    rdi
0x1800ac4a9  push    r14
0x1800ac4ab  push    r15
0x1800ac4ad  sub     rsp, 78h
0x1800ac4b1  xorps   xmm0, xmm0
0x1800ac4b4  lea     rax, aInitializingTi; "Initializing TIP thread pool"
0x1800ac4bb  mov     [rsp+0A8h+var_78], rax
0x1800ac4c0  lea     r8, aComComplusDtcD_70; "com\\complus\\dtc\\dtc\\tipgw\\commgr\\"...
0x1800ac4c7  mov     r9d, 31h ; '1'
0x1800ac4cd  mov     [rsp+0A8h+lpThreadId], 0
0x1800ac4d6  lea     rax, aCthreadpoolman_3; "CThreadPoolManager::Initialize"
0x1800ac4dd  movups  xmmword ptr [rsp+0A8h+SystemInfo], xmm0
0x1800ac4e2  mov     qword ptr [rsp+0A8h+dwCreationFlags], rax
0x1800ac4e7  lea     ebx, [r9-2Dh]
0x1800ac4eb  mov     edx, ebx
0x1800ac4ed  lea     ecx, [rbx+6]
0x1800ac4f0  movups  xmmword ptr [rsp+0A8h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800ac4f5  movups  xmmword ptr [rsp+0A8h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800ac4fa  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800ac4ff  cmp     cs:?m_fThreadPoolReady@CThreadPoolManager@@0HA, 0; int CThreadPoolManager::m_fThreadPoolReady
0x1800ac506  jz      short loc_1800AC50F
0x1800ac508  xor     eax, eax
0x1800ac50a  jmp     loc_1800AC6ED
0x1800ac50f  cmp     cs:?m_fThreadPoolCreatable@CThreadPoolManager@@0HA, 0; int CThreadPoolManager::m_fThreadPoolCreatable
0x1800ac516  jz      loc_1800AC6E8
0x1800ac51c  call    ?CreateCompletionPort@CThreadPoolManager@@AEAAJXZ; CThreadPoolManager::CreateCompletionPort(void)
0x1800ac521  mov     ebp, eax
0x1800ac523  test    eax, eax
0x1800ac525  js      loc_1800AC6ED
0x1800ac52b  lea     rcx, [rsp+0A8h+SystemInfo]; lpSystemInfo
0x1800ac530  call    cs:__imp_GetSystemInfo
0x1800ac536  mov     eax, [rsp+0A8h+SystemInfo.dwNumberOfProcessors]
0x1800ac53a  add     eax, eax
0x1800ac53c  movsxd  rcx, eax
0x1800ac53f  mov     cs:?m_nThreadPoolCount@CThreadPoolManager@@0HA, eax; int CThreadPoolManager::m_nThreadPoolCount
0x1800ac545  mov     rax, rbx
0x1800ac548  mul     rcx
0x1800ac54b  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800ac552  cmovb   rax, rbx
0x1800ac556  mov     rcx, rax; unsigned __int64
0x1800ac559  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ac55e  mov     cs:?m_rgThreadPool@CThreadPoolManager@@0PEAIEA, rax; uint * CThreadPoolManager::m_rgThreadPool
0x1800ac565  test    rax, rax
0x1800ac568  jnz     short loc_1800AC574
0x1800ac56a  mov     eax, 8007000Eh
0x1800ac56f  jmp     loc_1800AC6ED
0x1800ac574  movsxd  rcx, cs:?m_nThreadPoolCount@CThreadPoolManager@@0HA; int CThreadPoolManager::m_nThreadPoolCount
0x1800ac57b  mov     eax, 8
0x1800ac580  mul     rcx
0x1800ac583  cmovb   rax, rbx
0x1800ac587  mov     rcx, rax; unsigned __int64
0x1800ac58a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ac58f  mov     cs:?m_rgThreadHandleArray@CThreadPoolManager@@0PEAPEAXEA, rax; void * * CThreadPoolManager::m_rgThreadHandleArray
0x1800ac596  mov     r15, rax
0x1800ac599  test    rax, rax
0x1800ac59c  jnz     short loc_1800AC5B3
0x1800ac59e  mov     rcx, cs:?m_rgThreadPool@CThreadPoolManager@@0PEAIEA; Block
0x1800ac5a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ac5aa  mov     cs:?m_rgThreadPool@CThreadPoolManager@@0PEAIEA, r15; uint * CThreadPoolManager::m_rgThreadPool
0x1800ac5b1  jmp     short loc_1800AC56A
0x1800ac5b3  mov     esi, cs:?m_nThreadPoolCount@CThreadPoolManager@@0HA; int CThreadPoolManager::m_nThreadPoolCount
0x1800ac5b9  xor     edi, edi
0x1800ac5bb  mov     r14, cs:?m_rgThreadPool@CThreadPoolManager@@0PEAIEA; uint * CThreadPoolManager::m_rgThreadPool
0x1800ac5c2  test    esi, esi
0x1800ac5c4  jle     short loc_1800AC643
0x1800ac5c6  lea     r8d, [rdi+2]
0x1800ac5ca  cmp     esi, r8d
0x1800ac5cd  jb      short loc_1800AC643
0x1800ac5cf  lea     eax, [rsi-1]
0x1800ac5d2  movsxd  rcx, eax
0x1800ac5d5  lea     rax, [r15+rcx*8]
0x1800ac5d9  cmp     r14, rax
0x1800ac5dc  ja      short loc_1800AC5E7
0x1800ac5de  lea     rax, [r14+rcx*4]
0x1800ac5e2  cmp     rax, r15
0x1800ac5e5  jnb     short loc_1800AC643
0x1800ac5e7  mov     eax, esi
0x1800ac5e9  cdq
0x1800ac5ea  idiv    r8d
0x1800ac5ed  mov     eax, esi
0x1800ac5ef  sub     eax, edx
0x1800ac5f1  add     edi, r8d
0x1800ac5f4  cmp     edi, eax
0x1800ac5f6  jl      short loc_1800AC5F1
0x1800ac5f8  inc     eax
0x1800ac5fa  mov     rcx, r15; void *
0x1800ac5fd  cdq
0x1800ac5fe  idiv    r8d
0x1800ac601  xor     edx, edx; Val
0x1800ac603  movsxd  rbx, eax
0x1800ac606  mov     r8, rbx
0x1800ac609  shl     r8, 4
0x1800ac60d  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x1800ac611  call    memset_0
0x1800ac616  lea     r8, ds:0[rbx*8]
0x1800ac61e  xor     edx, edx; Val
0x1800ac620  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x1800ac624  mov     rcx, r14; void *
0x1800ac627  call    memset_0
0x1800ac62c  jmp     short loc_1800AC643
0x1800ac62e  movsxd  rax, edi
0x1800ac631  inc     edi
0x1800ac633  mov     qword ptr [r15+rax*8], 0
0x1800ac63b  mov     dword ptr [r14+rax*4], 0
0x1800ac643  cmp     edi, esi
0x1800ac645  jl      short loc_1800AC62E
0x1800ac647  xor     edi, edi
0x1800ac649  cmp     edi, esi
0x1800ac64b  jge     short loc_1800AC696
0x1800ac64d  movsxd  rbx, edi
0x1800ac650  lea     r8, ?ThreadRoutine@CThreadPoolManager@@CAKPEAX@Z; lpStartAddress
0x1800ac657  xor     r9d, r9d; lpParameter
0x1800ac65a  xor     edx, edx; dwStackSize
0x1800ac65c  xor     ecx, ecx; lpThreadAttributes
0x1800ac65e  lea     rax, [r14+rbx*4]
0x1800ac662  mov     [rsp+0A8h+lpThreadId], rax; lpThreadId
0x1800ac667  mov     [rsp+0A8h+dwCreationFlags], 1; dwCreationFlags
0x1800ac66f  call    cs:__imp_CreateThread
0x1800ac675  mov     rcx, cs:?m_rgThreadHandleArray@CThreadPoolManager@@0PEAPEAXEA; void * * CThreadPoolManager::m_rgThreadHandleArray
0x1800ac67c  mov     [rcx+rbx*8], rax
0x1800ac680  test    rax, rax
0x1800ac683  jz      short loc_1800AC6E8
0x1800ac685  mov     esi, cs:?m_nThreadPoolCount@CThreadPoolManager@@0HA; int CThreadPoolManager::m_nThreadPoolCount
0x1800ac68b  inc     edi
0x1800ac68d  mov     r14, cs:?m_rgThreadPool@CThreadPoolManager@@0PEAIEA; uint * CThreadPoolManager::m_rgThreadPool
0x1800ac694  jmp     short loc_1800AC649
0x1800ac696  mov     r9d, 80h
0x1800ac69c  mov     cs:?m_fThreadPoolReady@CThreadPoolManager@@0HA, 1; int CThreadPoolManager::m_fThreadPoolReady
0x1800ac6a6  lea     rax, aTipThreadPoolS; "TIP thread pool successfully created"
0x1800ac6ad  mov     cs:?m_fThreadPoolCreatable@CThreadPoolManager@@0HA, 0; int CThreadPoolManager::m_fThreadPoolCreatable
0x1800ac6b7  mov     [rsp+0A8h+var_78], rax
0x1800ac6bc  lea     r8, aComComplusDtcD_70; "com\\complus\\dtc\\dtc\\tipgw\\commgr\\"...
0x1800ac6c3  lea     rax, aCthreadpoolman_3; "CThreadPoolManager::Initialize"
0x1800ac6ca  mov     [rsp+0A8h+lpThreadId], 0
0x1800ac6d3  lea     edx, [r9-7Ch]
0x1800ac6d7  mov     qword ptr [rsp+0A8h+dwCreationFlags], rax
0x1800ac6dc  lea     ecx, [rdx+6]
0x1800ac6df  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800ac6e4  mov     eax, ebp
0x1800ac6e6  jmp     short loc_1800AC6ED
0x1800ac6e8  mov     eax, 80004005h
0x1800ac6ed  add     rsp, 78h
0x1800ac6f1  pop     r15
0x1800ac6f3  pop     r14
0x1800ac6f5  pop     rdi
0x1800ac6f6  pop     rsi
0x1800ac6f7  pop     rbp
0x1800ac6f8  pop     rbx
0x1800ac6f9  retn
```
