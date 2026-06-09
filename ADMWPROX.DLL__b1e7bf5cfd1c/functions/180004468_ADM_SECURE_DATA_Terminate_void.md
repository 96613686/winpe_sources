# ADM_SECURE_DATA::Terminate(void)

- ea: `0x180004468`
- end: `0x1800045d0`
- name: `?Terminate@ADM_SECURE_DATA@@SAXXZ`
- size: `360`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002400`
- `0x18000422c`

## callees

- `0x180001124`
- `0x1800031f4`
- `0x180004468`
- `0x180004e28`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180004488`
- `KERNEL32!EnterCriticalSection` at `0x1800044e5`
- `KERNEL32!EnterCriticalSection` at `0x180004488`
- `KERNEL32!EnterCriticalSection` at `0x1800044e5`
- `KERNEL32!LeaveCriticalSection` at `0x1800044cc`
- `KERNEL32!LeaveCriticalSection` at `0x180004525`
- `KERNEL32!LeaveCriticalSection` at `0x1800044cc`
- `KERNEL32!LeaveCriticalSection` at `0x180004525`
- `KERNEL32!DeleteCriticalSection` at `0x180004573`
- `KERNEL32!DeleteCriticalSection` at `0x180004593`
- `KERNEL32!DeleteCriticalSection` at `0x1800045af`
- `KERNEL32!DeleteCriticalSection` at `0x180004573`
- `KERNEL32!DeleteCriticalSection` at `0x180004593`
- `KERNEL32!DeleteCriticalSection` at `0x1800045af`

## pseudocode

```c
void ADM_SECURE_DATA::Terminate(void)
{
  ADM_SECURE_DATA *v0; // rbx
  ADM_SECURE_DATA *v1; // rbx

  if ( ADM_SECURE_DATA::sm_fServerSecureDataLockInitialized )
  {
    EnterCriticalSection(&ADM_SECURE_DATA::sm_ServerSecureDataLock);
    while ( 1 )
    {
      v0 = ADM_SECURE_DATA::sm_ServerSecureDataListHead;
      if ( ADM_SECURE_DATA::sm_ServerSecureDataListHead == (ADM_SECURE_DATA *)&ADM_SECURE_DATA::sm_ServerSecureDataListHead )
        break;
      if ( _InterlockedExchangeAdd(
             (volatile signed __int32 *)ADM_SECURE_DATA::sm_ServerSecureDataListHead + 6,
             0xFFFFFFFF) == 1
        && v0 )
      {
        ADM_SECURE_DATA::~ADM_SECURE_DATA(v0);
        operator delete(v0);
      }
    }
    LeaveCriticalSection(&ADM_SECURE_DATA::sm_ServerSecureDataLock);
  }
  if ( ADM_SECURE_DATA::sm_fClientSecureDataLockInitialized )
  {
    EnterCriticalSection(&ADM_SECURE_DATA::sm_ClientSecureDataLock);
    while ( 1 )
    {
      v1 = ADM_SECURE_DATA::sm_ClientSecureDataListHead;
      if ( ADM_SECURE_DATA::sm_ClientSecureDataListHead == (ADM_SECURE_DATA *)&ADM_SECURE_DATA::sm_ClientSecureDataListHead )
        break;
      if ( _InterlockedExchangeAdd(
             (volatile signed __int32 *)ADM_SECURE_DATA::sm_ClientSecureDataListHead + 6,
             0xFFFFFFFF) == 1
        && v1 )
      {
        ADM_SECURE_DATA::~ADM_SECURE_DATA(v1);
        operator delete(v1);
      }
    }
    LeaveCriticalSection(&ADM_SECURE_DATA::sm_ClientSecureDataLock);
  }
  if ( ADM_SECURE_DATA::sm_ServerCryptoProvider )
  {
    IISCryptoCloseContainer();
    ADM_SECURE_DATA::sm_ServerCryptoProvider = 0;
  }
  if ( ADM_SECURE_DATA::sm_ClientCryptoProvider )
  {
    IISCryptoCloseContainer();
    ADM_SECURE_DATA::sm_ClientCryptoProvider = 0;
  }
  if ( dword_18000FC38 )
  {
    DeleteCriticalSection(&IcpGlobals);
    dword_18000FC38 = 0;
  }
  if ( ADM_SECURE_DATA::sm_fServerSecureDataLockInitialized )
  {
    DeleteCriticalSection(&ADM_SECURE_DATA::sm_ServerSecureDataLock);
    ADM_SECURE_DATA::sm_fServerSecureDataLockInitialized = 0;
  }
  if ( ADM_SECURE_DATA::sm_fClientSecureDataLockInitialized )
  {
    DeleteCriticalSection(&ADM_SECURE_DATA::sm_ClientSecureDataLock);
    ADM_SECURE_DATA::sm_fClientSecureDataLockInitialized = 0;
  }
}

```

## disassembly

```asm
0x180004468  mov     [rsp+arg_8], rbx
0x18000446d  mov     [rsp+arg_10], rsi
0x180004472  push    r15
0x180004474  sub     rsp, 20h
0x180004478  cmp     cs:?sm_fServerSecureDataLockInitialized@ADM_SECURE_DATA@@0HA, 0; int ADM_SECURE_DATA::sm_fServerSecureDataLockInitialized
0x18000447f  jz      short loc_1800044D2
0x180004481  lea     rcx, ?sm_ServerSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004488  call    cs:__imp_EnterCriticalSection
0x18000448e  lea     rsi, ?sm_ServerSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_SECURE_DATA::sm_ServerSecureDataListHead
0x180004495  jmp     short loc_1800044B9
0x180004497  or      eax, 0FFFFFFFFh
0x18000449a  lock xadd [rbx+18h], eax
0x18000449f  cmp     eax, 1
0x1800044a2  jnz     short loc_1800044B9
0x1800044a4  test    rbx, rbx
0x1800044a7  jz      short loc_1800044B9
0x1800044a9  mov     rcx, rbx; this
0x1800044ac  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x1800044b1  mov     rcx, rbx; Block
0x1800044b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800044b9  mov     rbx, cs:?sm_ServerSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_SECURE_DATA::sm_ServerSecureDataListHead
0x1800044c0  cmp     rbx, rsi
0x1800044c3  jnz     short loc_180004497
0x1800044c5  lea     rcx, ?sm_ServerSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800044cc  call    cs:__imp_LeaveCriticalSection
0x1800044d2  cmp     cs:?sm_fClientSecureDataLockInitialized@ADM_SECURE_DATA@@0HA, 0; int ADM_SECURE_DATA::sm_fClientSecureDataLockInitialized
0x1800044d9  lea     rsi, ?sm_ClientSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION ADM_SECURE_DATA::sm_ClientSecureDataLock
0x1800044e0  jz      short loc_18000452B
0x1800044e2  mov     rcx, rsi; lpCriticalSection
0x1800044e5  call    cs:__imp_EnterCriticalSection
0x1800044eb  lea     r15, ?sm_ClientSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_SECURE_DATA::sm_ClientSecureDataListHead
0x1800044f2  jmp     short loc_180004516
0x1800044f4  or      eax, 0FFFFFFFFh
0x1800044f7  lock xadd [rbx+18h], eax
0x1800044fc  cmp     eax, 1
0x1800044ff  jnz     short loc_180004516
0x180004501  test    rbx, rbx
0x180004504  jz      short loc_180004516
0x180004506  mov     rcx, rbx; this
0x180004509  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x18000450e  mov     rcx, rbx; Block
0x180004511  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004516  mov     rbx, cs:?sm_ClientSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_SECURE_DATA::sm_ClientSecureDataListHead
0x18000451d  cmp     rbx, r15
0x180004520  jnz     short loc_1800044F4
0x180004522  mov     rcx, rsi; lpCriticalSection
0x180004525  call    cs:__imp_LeaveCriticalSection
0x18000452b  mov     rcx, cs:?sm_ServerCryptoProvider@ADM_SECURE_DATA@@0_KA; unsigned __int64 ADM_SECURE_DATA::sm_ServerCryptoProvider
0x180004532  test    rcx, rcx
0x180004535  jz      short loc_180004547
0x180004537  call    IISCryptoCloseContainer
0x18000453c  mov     cs:?sm_ServerCryptoProvider@ADM_SECURE_DATA@@0_KA, 0; unsigned __int64 ADM_SECURE_DATA::sm_ServerCryptoProvider
0x180004547  mov     rcx, cs:?sm_ClientCryptoProvider@ADM_SECURE_DATA@@0_KA; unsigned __int64 ADM_SECURE_DATA::sm_ClientCryptoProvider
0x18000454e  test    rcx, rcx
0x180004551  jz      short loc_180004563
0x180004553  call    IISCryptoCloseContainer
0x180004558  mov     cs:?sm_ClientCryptoProvider@ADM_SECURE_DATA@@0_KA, 0; unsigned __int64 ADM_SECURE_DATA::sm_ClientCryptoProvider
0x180004563  cmp     cs:dword_18000FC38, 0
0x18000456a  jz      short loc_180004583
0x18000456c  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x180004573  call    cs:__imp_DeleteCriticalSection
0x180004579  mov     cs:dword_18000FC38, 0
0x180004583  cmp     cs:?sm_fServerSecureDataLockInitialized@ADM_SECURE_DATA@@0HA, 0; int ADM_SECURE_DATA::sm_fServerSecureDataLockInitialized
0x18000458a  jz      short loc_1800045A3
0x18000458c  lea     rcx, ?sm_ServerSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004593  call    cs:__imp_DeleteCriticalSection
0x180004599  mov     cs:?sm_fServerSecureDataLockInitialized@ADM_SECURE_DATA@@0HA, 0; int ADM_SECURE_DATA::sm_fServerSecureDataLockInitialized
0x1800045a3  cmp     cs:?sm_fClientSecureDataLockInitialized@ADM_SECURE_DATA@@0HA, 0; int ADM_SECURE_DATA::sm_fClientSecureDataLockInitialized
0x1800045aa  jz      short loc_1800045BF
0x1800045ac  mov     rcx, rsi; lpCriticalSection
0x1800045af  call    cs:__imp_DeleteCriticalSection
0x1800045b5  mov     cs:?sm_fClientSecureDataLockInitialized@ADM_SECURE_DATA@@0HA, 0; int ADM_SECURE_DATA::sm_fClientSecureDataLockInitialized
0x1800045bf  mov     rbx, [rsp+28h+arg_8]
0x1800045c4  mov     rsi, [rsp+28h+arg_10]
0x1800045c9  add     rsp, 20h
0x1800045cd  pop     r15
0x1800045cf  retn
```
