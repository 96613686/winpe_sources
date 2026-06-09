# PimIMService::_LoadAggregateCacheFromFile(void)

- ea: `0x18000ba6c`
- end: `0x18000bb17`
- name: `?_LoadAggregateCacheFromFile@PimIMService@@AEAAJXZ`
- size: `171`
- prototype: `__int64 __fastcall(PimIMService *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800082c4`
- `0x18000cb30`

## callees

- `0x180002da8`
- `0x18000ba6c`
- `0x18000bf5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bab1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bab1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000baf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bb04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000baf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bb04`
- `PIMSTORE!GetAggregateCache` at `0x18000bacf`
- `PIMSTORE!GetAggregateCache` at `0x18000bacf`

## string_xrefs

- `0x18000ba8d`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000bae1`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::_LoadAggregateCacheFromFile(PimIMService *this)
{
  int v2; // eax
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  int AggregateCache; // eax
  unsigned int v5; // ebx

  v2 = PimIMService::_ScheduleAggregateCacheBackup(this, 0, 0);
  if ( v2 < 0 )
    Log_HREvent(
      (unsigned int)v2,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      3511);
  if ( !*((_QWORD *)this + 46) )
  {
    v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 376);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 376));
    if ( !*((_QWORD *)this + 46) )
    {
      AggregateCache = GetAggregateCache(3, *((_QWORD *)this + 27));
      v5 = AggregateCache;
      if ( AggregateCache < 0 )
      {
        Log_HREvent(
          (unsigned int)AggregateCache,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
          3519);
        LeaveCriticalSection(v3);
        return v5;
      }
    }
    LeaveCriticalSection(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ba6c  mov     [rsp+arg_0], rbx
0x18000ba71  push    rdi
0x18000ba72  sub     rsp, 30h
0x18000ba76  xor     r8d, r8d; int
0x18000ba79  xor     edx, edx; int
0x18000ba7b  mov     rbx, rcx
0x18000ba7e  call    ?_ScheduleAggregateCacheBackup@PimIMService@@AEAAJHH@Z; PimIMService::_ScheduleAggregateCacheBackup(int,int)
0x18000ba83  test    eax, eax
0x18000ba85  jns     short loc_18000BA9D
0x18000ba87  mov     r9d, 0DB7h
0x18000ba8d  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ba94  xor     edx, edx
0x18000ba96  mov     ecx, eax
0x18000ba98  call    Log_HREvent
0x18000ba9d  cmp     qword ptr [rbx+170h], 0
0x18000baa5  jnz     short loc_18000BB0A
0x18000baa7  lea     rdi, [rbx+178h]
0x18000baae  mov     rcx, rdi; lpCriticalSection
0x18000bab1  call    cs:__imp_EnterCriticalSection
0x18000bab7  cmp     qword ptr [rbx+170h], 0
0x18000babf  jnz     short loc_18000BB01
0x18000bac1  mov     rdx, [rbx+0D8h]
0x18000bac8  xor     r8d, r8d
0x18000bacb  lea     ecx, [r8+3]
0x18000bacf  call    cs:__imp_GetAggregateCache
0x18000bad5  mov     ebx, eax
0x18000bad7  test    eax, eax
0x18000bad9  jns     short loc_18000BB01
0x18000badb  mov     r9d, 0DBFh
0x18000bae1  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bae8  mov     edx, 1
0x18000baed  mov     ecx, eax
0x18000baef  call    Log_HREvent
0x18000baf4  mov     rcx, rdi; lpCriticalSection
0x18000baf7  call    cs:__imp_LeaveCriticalSection
0x18000bafd  mov     eax, ebx
0x18000baff  jmp     short loc_18000BB0C
0x18000bb01  mov     rcx, rdi; lpCriticalSection
0x18000bb04  call    cs:__imp_LeaveCriticalSection
0x18000bb0a  xor     eax, eax
0x18000bb0c  mov     rbx, [rsp+38h+arg_0]
0x18000bb11  add     rsp, 30h
0x18000bb15  pop     rdi
0x18000bb16  retn
```
