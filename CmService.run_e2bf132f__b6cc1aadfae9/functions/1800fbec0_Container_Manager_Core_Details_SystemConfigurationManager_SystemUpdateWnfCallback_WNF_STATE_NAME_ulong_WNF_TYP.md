# Container::Manager::Core::Details::SystemConfigurationManager::SystemUpdateWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x1800fbec0`
- end: `0x1800fc023`
- name: `?SystemUpdateWnfCallback@SystemConfigurationManager@Details@Core@Manager@Container@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `355`
- prototype: `static int(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x18000da88`
- `0x180016718`
- `0x1800f993c`
- `0x1800fbec0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800fbfa6`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800fbfa6`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800fbf12`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800fbf12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fbed1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fbf82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fbed1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fbf82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fbf68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fbfd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fc009`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fbf68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fbfd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fc009`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fbee1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fbf1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fbf8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fbee1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fbf1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fbf8e`

## string_xrefs

- `0x1800fbfbc`: `onecore\base\gendrv\silos\clem\core\lib\systemconfigurationmanager.cpp`
- `0x1800fbfea`: `onecore\base\gendrv\silos\clem\core\lib\systemconfigurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::SystemConfigurationManager::SystemUpdateWnfCallback(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        char *a4)
{
  DWORD *v5; // rsi
  _DWORD *v6; // rdi
  int v7; // r14d
  int v9; // [rsp+20h] [rbp-28h]
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  AcquireSRWLockExclusive((PSRWLOCK)a4);
  v5 = (DWORD *)(a4 + 8);
  *((_DWORD *)a4 + 2) = GetCurrentThreadId();
  if ( a4[136] )
  {
    do
    {
      *v5 = 0;
      SleepConditionVariableSRW((PCONDITION_VARIABLE)a4 + 18, (PSRWLOCK)a4, 0xFFFFFFFF, 0);
      *v5 = GetCurrentThreadId();
    }
    while ( a4[136] );
    v6 = a4 + 8;
  }
  else
  {
    v6 = a4 + 8;
  }
  if ( !a4[153] )
    goto LABEL_9;
  if ( !a4[152] )
    goto LABEL_9;
  a4[136] = 1;
  *v5 = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)a4);
  v7 = Container::Manager::Core::Details::SystemConfigurationManager::CheckHotPatchesAndNotifyIfNecessary((PSRWLOCK)a4);
  AcquireSRWLockExclusive((PSRWLOCK)a4);
  *v5 = GetCurrentThreadId();
  a4[136] = 0;
  WakeAllConditionVariable((PCONDITION_VARIABLE)a4 + 18);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x433,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
      (const char *)(unsigned int)v7,
      v9);
    *v6 = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)a4);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x446,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
      (const char *)(unsigned int)v7,
      v10);
  }
  else
  {
LABEL_9:
    *v6 = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)a4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800fbec0  push    rbx
0x1800fbec2  push    rbp
0x1800fbec3  push    rsi
0x1800fbec4  push    rdi
0x1800fbec5  push    r14; int
0x1800fbec7  sub     rsp, 20h
0x1800fbecb  mov     rcx, r9; SRWLock
0x1800fbece  mov     rbx, r9
0x1800fbed1  call    cs:__imp_AcquireSRWLockExclusive
0x1800fbed8  nop     dword ptr [rax+rax+00h]
0x1800fbedd  lea     rsi, [rbx+8]
0x1800fbee1  call    cs:__imp_GetCurrentThreadId
0x1800fbee8  nop     dword ptr [rax+rax+00h]
0x1800fbeed  mov     [rsi], eax
0x1800fbeef  lea     rbp, [rbx+90h]
0x1800fbef6  cmp     byte ptr [rbx+88h], 0
0x1800fbefd  jz      short loc_1800FBF3B
0x1800fbeff  xor     r9d, r9d; Flags
0x1800fbf02  mov     dword ptr [rsi], 0
0x1800fbf08  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800fbf0c  mov     rdx, rbx; SRWLock
0x1800fbf0f  mov     rcx, rbp; ConditionVariable
0x1800fbf12  call    cs:__imp_SleepConditionVariableSRW
0x1800fbf19  nop     dword ptr [rax+rax+00h]
0x1800fbf1e  call    cs:__imp_GetCurrentThreadId
0x1800fbf25  nop     dword ptr [rax+rax+00h]
0x1800fbf2a  mov     [rsi], eax
0x1800fbf2c  cmp     byte ptr [rbx+88h], 0
0x1800fbf33  jnz     short loc_1800FBEFF
0x1800fbf35  lea     rdi, [rbx+8]
0x1800fbf39  jmp     short loc_1800FBF3E
0x1800fbf3b  mov     rdi, rsi
0x1800fbf3e  cmp     byte ptr [rbx+99h], 0
0x1800fbf45  jz      loc_1800FC000
0x1800fbf4b  cmp     byte ptr [rbx+98h], 0
0x1800fbf52  jz      loc_1800FC000
0x1800fbf58  mov     byte ptr [rbx+88h], 1
0x1800fbf5f  mov     rcx, rbx; SRWLock
0x1800fbf62  mov     dword ptr [rsi], 0
0x1800fbf68  call    cs:__imp_ReleaseSRWLockExclusive
0x1800fbf6f  nop     dword ptr [rax+rax+00h]
0x1800fbf74  mov     rcx, rbx; SRWLock
0x1800fbf77  call    ?CheckHotPatchesAndNotifyIfNecessary@SystemConfigurationManager@Details@Core@Manager@Container@@AEAAJXZ; Container::Manager::Core::Details::SystemConfigurationManager::CheckHotPatchesAndNotifyIfNecessary(void)
0x1800fbf7c  mov     rcx, rbx; SRWLock
0x1800fbf7f  mov     r14d, eax
0x1800fbf82  call    cs:__imp_AcquireSRWLockExclusive
0x1800fbf89  nop     dword ptr [rax+rax+00h]
0x1800fbf8e  call    cs:__imp_GetCurrentThreadId
0x1800fbf95  nop     dword ptr [rax+rax+00h]
0x1800fbf9a  mov     [rsi], eax
0x1800fbf9c  mov     rcx, rbp; ConditionVariable
0x1800fbf9f  mov     byte ptr [rbx+88h], 0
0x1800fbfa6  call    cs:__imp_WakeAllConditionVariable
0x1800fbfad  nop     dword ptr [rax+rax+00h]
0x1800fbfb2  test    r14d, r14d
0x1800fbfb5  jns     short loc_1800FC000
0x1800fbfb7  mov     rcx, [rsp+48h]; this
0x1800fbfbc  lea     r8, aOnecoreBaseGen_59; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800fbfc3  mov     r9d, r14d; char *
0x1800fbfc6  mov     edx, 433h; void *
0x1800fbfcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fbfd0  mov     rcx, rbx; SRWLock
0x1800fbfd3  mov     dword ptr [rdi], 0
0x1800fbfd9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800fbfe0  nop     dword ptr [rax+rax+00h]
0x1800fbfe5  mov     rcx, [rsp+48h]; this
0x1800fbfea  lea     r8, aOnecoreBaseGen_59; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800fbff1  mov     r9d, r14d; char *
0x1800fbff4  mov     edx, 446h; void *
0x1800fbff9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fbffe  jmp     short loc_1800FC015
0x1800fc000  mov     rcx, rbx; SRWLock
0x1800fc003  mov     dword ptr [rdi], 0
0x1800fc009  call    cs:__imp_ReleaseSRWLockExclusive
0x1800fc010  nop     dword ptr [rax+rax+00h]
0x1800fc015  xor     eax, eax
0x1800fc017  add     rsp, 20h
0x1800fc01b  pop     r14
0x1800fc01d  pop     rdi
0x1800fc01e  pop     rsi
0x1800fc01f  pop     rbp
0x1800fc020  pop     rbx
0x1800fc021  retn
```
