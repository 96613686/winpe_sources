# ADM_GUID_MAP::Terminate(void)

- ea: `0x1800043d0`
- end: `0x18000445f`
- name: `?Terminate@ADM_GUID_MAP@@SAXXZ`
- size: `143`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002400`

## callees

- `0x180001124`
- `0x18000313c`
- `0x1800043d0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800043ea`
- `KERNEL32!EnterCriticalSection` at `0x1800043ea`
- `KERNEL32!LeaveCriticalSection` at `0x18000442e`
- `KERNEL32!LeaveCriticalSection` at `0x18000442e`
- `KERNEL32!DeleteCriticalSection` at `0x180004444`
- `KERNEL32!DeleteCriticalSection` at `0x180004444`

## pseudocode

```c
void ADM_GUID_MAP::Terminate(void)
{
  ADM_GUID_MAP *v0; // rbx

  if ( ADM_GUID_MAP::sm_fGuidMapDataLockInitialized )
  {
    EnterCriticalSection(&ADM_GUID_MAP::sm_GuidMapDataLock);
    while ( 1 )
    {
      v0 = ADM_GUID_MAP::sm_GuidMapListHead;
      if ( ADM_GUID_MAP::sm_GuidMapListHead == (ADM_GUID_MAP *)&ADM_GUID_MAP::sm_GuidMapListHead )
        break;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)ADM_GUID_MAP::sm_GuidMapListHead + 6, 0xFFFFFFFF) == 1
        && v0 )
      {
        ADM_GUID_MAP::~ADM_GUID_MAP(v0);
        operator delete(v0);
      }
    }
    LeaveCriticalSection(&ADM_GUID_MAP::sm_GuidMapDataLock);
    if ( ADM_GUID_MAP::sm_fGuidMapDataLockInitialized )
    {
      DeleteCriticalSection(&ADM_GUID_MAP::sm_GuidMapDataLock);
      ADM_GUID_MAP::sm_fGuidMapDataLockInitialized = 0;
    }
  }
}

```

## disassembly

```asm
0x1800043d0  mov     [rsp+arg_8], rbx
0x1800043d5  push    rbp
0x1800043d6  sub     rsp, 20h
0x1800043da  cmp     cs:?sm_fGuidMapDataLockInitialized@ADM_GUID_MAP@@0HA, 0; int ADM_GUID_MAP::sm_fGuidMapDataLockInitialized
0x1800043e1  jz      short loc_180004454
0x1800043e3  lea     rcx, ?sm_GuidMapDataLock@ADM_GUID_MAP@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800043ea  call    cs:__imp_EnterCriticalSection
0x1800043f0  lea     rbp, ?sm_GuidMapListHead@ADM_GUID_MAP@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_GUID_MAP::sm_GuidMapListHead
0x1800043f7  jmp     short loc_18000441B
0x1800043f9  or      eax, 0FFFFFFFFh
0x1800043fc  lock xadd [rbx+18h], eax
0x180004401  cmp     eax, 1
0x180004404  jnz     short loc_18000441B
0x180004406  test    rbx, rbx
0x180004409  jz      short loc_18000441B
0x18000440b  mov     rcx, rbx; this
0x18000440e  call    ??1ADM_GUID_MAP@@QEAA@XZ; ADM_GUID_MAP::~ADM_GUID_MAP(void)
0x180004413  mov     rcx, rbx; Block
0x180004416  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000441b  mov     rbx, cs:?sm_GuidMapListHead@ADM_GUID_MAP@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_GUID_MAP::sm_GuidMapListHead
0x180004422  cmp     rbx, rbp
0x180004425  jnz     short loc_1800043F9
0x180004427  lea     rcx, ?sm_GuidMapDataLock@ADM_GUID_MAP@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000442e  call    cs:__imp_LeaveCriticalSection
0x180004434  cmp     cs:?sm_fGuidMapDataLockInitialized@ADM_GUID_MAP@@0HA, 0; int ADM_GUID_MAP::sm_fGuidMapDataLockInitialized
0x18000443b  jz      short loc_180004454
0x18000443d  lea     rcx, ?sm_GuidMapDataLock@ADM_GUID_MAP@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004444  call    cs:__imp_DeleteCriticalSection
0x18000444a  mov     cs:?sm_fGuidMapDataLockInitialized@ADM_GUID_MAP@@0HA, 0; int ADM_GUID_MAP::sm_fGuidMapDataLockInitialized
0x180004454  mov     rbx, [rsp+28h+arg_8]
0x180004459  add     rsp, 20h
0x18000445d  pop     rbp
0x18000445e  retn
```
