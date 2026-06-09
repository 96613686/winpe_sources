# ServiceManager::WaitForMOSAndBingInit(void)

- ea: `0x18001e454`
- end: `0x18001e517`
- name: `?WaitForMOSAndBingInit@ServiceManager@@AEAAJXZ`
- size: `195`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180014a90`
- `0x180015898`
- `0x180015ad0`
- `0x180016490`
- `0x180018330`
- `0x18001d7ec`

## callees

- `0x1800043e4`
- `0x18001e454`
- `0x180022914`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e47e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e47e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e4b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e4b6`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e4ab`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e508`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e4ab`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e508`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001e4ea`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001e4ea`

## string_xrefs

- `0x18001e4dd`: `ServiceManager::WaitForMOSAndBingInit`
- `0x18001e4f9`: `ServiceManager::WaitForMOSAndBingInit`

## pseudocode

```c
int __fastcall ServiceManager::WaitForMOSAndBingInit(ServiceManager *this)
{
  __int64 v2; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  int v5; // ebp
  unsigned int v6; // edx
  int v7; // eax
  int v8; // ecx
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v10, (__int64)this);
  v2 = v10;
  v4 = v3 + 85;
  v5 = 0;
  EnterCriticalSection(v3 + 85);
  while ( *(_DWORD *)(v2 + 3528) == 1 )
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
    return ZTraceReportPropagation(v5, "ServiceManager::WaitForMOSAndBingInit", 1776, this);
  if ( (unsigned int)(*((_DWORD *)this + 882) - 2) <= 3 )
    return 0;
  v8 = *((_DWORD *)this + 862);
  if ( v8 >= 0 )
    __int2c();
  return ZTraceReportOrigination(v8, "ServiceManager::WaitForMOSAndBingInit", 1785, this);
}

```

## disassembly

```asm
0x18001e454  push    rbx
0x18001e456  push    rbp
0x18001e457  push    rsi
0x18001e458  push    rdi
0x18001e459  sub     rsp, 28h
0x18001e45d  mov     rdx, rcx
0x18001e460  mov     rdi, rcx
0x18001e463  lea     rcx, [rsp+48h+arg_0]
0x18001e468  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001e46d  mov     rbx, [rsp+48h+arg_0]
0x18001e472  lea     rsi, [rdx+0D48h]
0x18001e479  mov     rcx, rsi; lpCriticalSection
0x18001e47c  xor     ebp, ebp
0x18001e47e  call    cs:__imp_EnterCriticalSection
0x18001e484  cmp     dword ptr [rbx+0DC8h], 1
0x18001e48b  jnz     short loc_18001E4B3
0x18001e48d  mov     rcx, rsi; lpCriticalSection
0x18001e490  call    ?WaitForCondition@CriticalSectionWithConditionVariable@@AEAAJK@Z; CriticalSectionWithConditionVariable::WaitForCondition(ulong)
0x18001e495  test    eax, eax
0x18001e497  jns     short loc_18001E484
0x18001e499  mov     r9, rsi
0x18001e49c  lea     rdx, aCriticalsectio_0; "CriticalSectionWithConditionVariable::W"...
0x18001e4a3  mov     r8d, 36h ; '6'
0x18001e4a9  mov     ecx, eax
0x18001e4ab  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001e4b1  mov     ebp, eax
0x18001e4b3  mov     rcx, rsi; lpCriticalSection
0x18001e4b6  call    cs:__imp_LeaveCriticalSection
0x18001e4bc  test    ebp, ebp
0x18001e4be  js      short loc_18001E4F6
0x18001e4c0  mov     eax, [rdi+0DC8h]
0x18001e4c6  sub     eax, 2
0x18001e4c9  cmp     eax, 3
0x18001e4cc  jbe     short loc_18001E4F2
0x18001e4ce  mov     ecx, [rdi+0D78h]
0x18001e4d4  test    ecx, ecx
0x18001e4d6  js      short loc_18001E4DA
0x18001e4d8  int     2Ch; Windows NT - assertion failure
0x18001e4da  mov     r9, rdi
0x18001e4dd  lea     rdx, aServicemanager_5; "ServiceManager::WaitForMOSAndBingInit"
0x18001e4e4  mov     r8d, 6F9h
0x18001e4ea  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001e4f0  jmp     short loc_18001E50E
0x18001e4f2  xor     eax, eax
0x18001e4f4  jmp     short loc_18001E50E
0x18001e4f6  mov     r9, rdi
0x18001e4f9  lea     rdx, aServicemanager_5; "ServiceManager::WaitForMOSAndBingInit"
0x18001e500  mov     r8d, 6F0h
0x18001e506  mov     ecx, ebp
0x18001e508  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001e50e  add     rsp, 28h
0x18001e512  pop     rdi
0x18001e513  pop     rsi
0x18001e514  pop     rbp
0x18001e515  pop     rbx
0x18001e516  retn
```
