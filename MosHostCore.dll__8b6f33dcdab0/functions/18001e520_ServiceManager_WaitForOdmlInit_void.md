# ServiceManager::WaitForOdmlInit(void)

- ea: `0x18001e520`
- end: `0x18001e5d7`
- name: `?WaitForOdmlInit@ServiceManager@@AEAAJXZ`
- size: `183`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800128d0`
- `0x180015de0`

## callees

- `0x1800043e4`
- `0x18001e520`
- `0x180022914`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e54a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e54a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e582`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e582`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e577`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e5c8`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e577`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e5c8`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001e5ae`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001e5ae`

## string_xrefs

- `0x18001e59c`: `ServiceManager::WaitForOdmlInit`
- `0x18001e5b9`: `ServiceManager::WaitForOdmlInit`

## pseudocode

```c
int __fastcall ServiceManager::WaitForOdmlInit(ServiceManager *this)
{
  __int64 v2; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  int v5; // ebp
  unsigned int v6; // edx
  int v7; // eax
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v9, (__int64)this);
  v2 = v9;
  v4 = v3 + 85;
  v5 = 0;
  EnterCriticalSection(v3 + 85);
  while ( *(_DWORD *)(v2 + 3528) == 3 )
  {
    v7 = CriticalSectionWithConditionVariable::WaitForCondition(v4, v6);
    if ( v7 < 0 )
    {
      v5 = ZTraceReportPropagation(v7, "CriticalSectionWithConditionVariable::WaitWhile", 54, v4);
      break;
    }
  }
  LeaveCriticalSection(v4);
  if ( v5 < 0 )
    return ZTraceReportPropagation(v5, "ServiceManager::WaitForOdmlInit", 1805, this);
  if ( *((_DWORD *)this + 882) == 5 )
    return 0;
  return ZTraceReportOrigination(-2080374756, "ServiceManager::WaitForOdmlInit", 1807, this);
}

```

## disassembly

```asm
0x18001e520  push    rbx
0x18001e522  push    rbp
0x18001e523  push    rsi
0x18001e524  push    rdi
0x18001e525  sub     rsp, 28h
0x18001e529  mov     rdx, rcx
0x18001e52c  mov     rdi, rcx
0x18001e52f  lea     rcx, [rsp+48h+arg_0]
0x18001e534  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001e539  mov     rbx, [rsp+48h+arg_0]
0x18001e53e  lea     rsi, [rdx+0D48h]
0x18001e545  mov     rcx, rsi; lpCriticalSection
0x18001e548  xor     ebp, ebp
0x18001e54a  call    cs:__imp_EnterCriticalSection
0x18001e550  cmp     dword ptr [rbx+0DC8h], 3
0x18001e557  jnz     short loc_18001E57F
0x18001e559  mov     rcx, rsi; lpCriticalSection
0x18001e55c  call    ?WaitForCondition@CriticalSectionWithConditionVariable@@AEAAJK@Z; CriticalSectionWithConditionVariable::WaitForCondition(ulong)
0x18001e561  test    eax, eax
0x18001e563  jns     short loc_18001E550
0x18001e565  mov     r9, rsi
0x18001e568  lea     rdx, aCriticalsectio_0; "CriticalSectionWithConditionVariable::W"...
0x18001e56f  mov     r8d, 36h ; '6'
0x18001e575  mov     ecx, eax
0x18001e577  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001e57d  mov     ebp, eax
0x18001e57f  mov     rcx, rsi; lpCriticalSection
0x18001e582  call    cs:__imp_LeaveCriticalSection
0x18001e588  test    ebp, ebp
0x18001e58a  js      short loc_18001E5B6
0x18001e58c  cmp     dword ptr [rdi+0DC8h], 5
0x18001e593  jnz     short loc_18001E599
0x18001e595  xor     eax, eax
0x18001e597  jmp     short loc_18001E5CE
0x18001e599  mov     r9, rdi
0x18001e59c  lea     rdx, aServicemanager_78; "ServiceManager::WaitForOdmlInit"
0x18001e5a3  mov     r8d, 70Fh
0x18001e5a9  mov     ecx, 8400001Ch
0x18001e5ae  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001e5b4  jmp     short loc_18001E5CE
0x18001e5b6  mov     r9, rdi
0x18001e5b9  lea     rdx, aServicemanager_78; "ServiceManager::WaitForOdmlInit"
0x18001e5c0  mov     r8d, 70Dh
0x18001e5c6  mov     ecx, ebp
0x18001e5c8  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001e5ce  add     rsp, 28h
0x18001e5d2  pop     rdi
0x18001e5d3  pop     rsi
0x18001e5d4  pop     rbp
0x18001e5d5  pop     rbx
0x18001e5d6  retn
```
