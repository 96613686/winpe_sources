# EnsureInProcServiceInitialized(void)

- ea: `0x180002d20`
- end: `0x180002d9f`
- name: `?EnsureInProcServiceInitialized@@YAJXZ`
- size: `127`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x1800032f0`

## callees

- `0x180002d20`
- `0x180002da8`
- `0x180008da0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d91`

## string_xrefs

- `0x180002d5d`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\rpcsetup.cpp`

## pseudocode

```c
__int64 EnsureInProcServiceInitialized(void)
{
  int v0; // eax
  unsigned int v1; // ebx

  if ( !g_inprocServiceInitialized )
  {
    EnterCriticalSection(&g_inprocServiceInitLock);
    if ( !g_inprocServiceInitialized )
    {
      v0 = PimIMService::OnStarted(&myService);
      v1 = v0;
      if ( v0 < 0 )
      {
        Log_HREvent(
          (unsigned int)v0,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\rpcsetup.cpp",
          17);
        LeaveCriticalSection(&g_inprocServiceInitLock);
        return v1;
      }
      g_inprocServiceInitialized = 1;
    }
    LeaveCriticalSection(&g_inprocServiceInitLock);
  }
  return 0;
}

```

## disassembly

```asm
0x180002d20  push    rbx
0x180002d22  sub     rsp, 30h
0x180002d26  cmp     cs:?g_inprocServiceInitialized@@3HA, 0; int g_inprocServiceInitialized
0x180002d2d  jnz     short loc_180002D97
0x180002d2f  lea     rcx, ?g_inprocServiceInitLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180002d36  call    cs:__imp_EnterCriticalSection
0x180002d3c  cmp     cs:?g_inprocServiceInitialized@@3HA, 0; int g_inprocServiceInitialized
0x180002d43  jnz     short loc_180002D8A
0x180002d45  lea     rcx, ?myService@@3VPimIMService@@A; pv
0x180002d4c  call    ?OnStarted@PimIMService@@UEAAJXZ; PimIMService::OnStarted(void)
0x180002d51  mov     ebx, eax
0x180002d53  test    eax, eax
0x180002d55  jns     short loc_180002D80
0x180002d57  mov     r9d, 11h
0x180002d5d  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180002d64  mov     ecx, eax
0x180002d66  lea     edx, [r9-10h]
0x180002d6a  call    Log_HREvent
0x180002d6f  lea     rcx, ?g_inprocServiceInitLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180002d76  call    cs:__imp_LeaveCriticalSection
0x180002d7c  mov     eax, ebx
0x180002d7e  jmp     short loc_180002D99
0x180002d80  mov     cs:?g_inprocServiceInitialized@@3HA, 1; int g_inprocServiceInitialized
0x180002d8a  lea     rcx, ?g_inprocServiceInitLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180002d91  call    cs:__imp_LeaveCriticalSection
0x180002d97  xor     eax, eax
0x180002d99  add     rsp, 30h
0x180002d9d  pop     rbx
0x180002d9e  retn
```
