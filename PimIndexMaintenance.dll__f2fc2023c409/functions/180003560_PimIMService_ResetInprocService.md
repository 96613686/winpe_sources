# PimIMService_ResetInprocService

- ea: `0x180003560`
- end: `0x1800035ce`
- name: `PimIMService_ResetInprocService`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x180002da8`
- `0x180003560`
- `0x180008fe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000356d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000356d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035c0`

## string_xrefs

- `0x180003599`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\rpcsetup.cpp`

## pseudocode

```c
__int64 PimIMService_ResetInprocService()
{
  int v0; // eax
  unsigned int v1; // ebx

  EnterCriticalSection(&g_inprocServiceInitLock);
  if ( !g_inprocServiceInitialized )
    goto LABEL_5;
  v0 = PimIMService::OnStopping((PimIMService *)&myService);
  v1 = v0;
  if ( v0 >= 0 )
  {
    g_inprocServiceInitialized = 0;
LABEL_5:
    v1 = 0;
    goto LABEL_6;
  }
  Log_HREvent(
    (unsigned int)v0,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\rpcsetup.cpp",
    56);
LABEL_6:
  LeaveCriticalSection(&g_inprocServiceInitLock);
  return v1;
}

```

## disassembly

```asm
0x180003560  push    rbx
0x180003562  sub     rsp, 30h
0x180003566  lea     rcx, ?g_inprocServiceInitLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18000356d  call    cs:__imp_EnterCriticalSection
0x180003573  cmp     cs:?g_inprocServiceInitialized@@3HA, 0; int g_inprocServiceInitialized
0x18000357a  jz      short loc_1800035B7
0x18000357c  mov     edx, 1; int
0x180003581  lea     rcx, ?myService@@3VPimIMService@@A; this
0x180003588  call    ?OnStopping@PimIMService@@UEAAJH@Z; PimIMService::OnStopping(int)
0x18000358d  mov     ebx, eax
0x18000358f  test    eax, eax
0x180003591  jns     short loc_1800035AD
0x180003593  mov     r9d, 38h ; '8'
0x180003599  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800035a0  mov     ecx, eax
0x1800035a2  lea     edx, [r9-37h]
0x1800035a6  call    Log_HREvent
0x1800035ab  jmp     short loc_1800035B9
0x1800035ad  mov     cs:?g_inprocServiceInitialized@@3HA, 0; int g_inprocServiceInitialized
0x1800035b7  xor     ebx, ebx
0x1800035b9  lea     rcx, ?g_inprocServiceInitLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800035c0  call    cs:__imp_LeaveCriticalSection
0x1800035c6  mov     eax, ebx
0x1800035c8  add     rsp, 30h
0x1800035cc  pop     rbx
0x1800035cd  retn
```
