# BampThrottlingInitializeModule

- ea: `0x14000c474`
- end: `0x14000c5aa`
- name: `BampThrottlingInitializeModule`
- size: `310`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140016078`

## callees

- `0x140001814`
- `0x14000c474`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000c486`
- `ntoskrnl!KeInitializeEvent` at `0x14000c4a0`
- `ntoskrnl!KeInitializeEvent` at `0x14000c486`
- `ntoskrnl!KeInitializeEvent` at `0x14000c4a0`
- `ntoskrnl!ExUuidCreate` at `0x14000c598`
- `ntoskrnl!ExUuidCreate` at `0x14000c598`

## pseudocode

```c
NTSTATUS BampThrottlingInitializeModule()
{
  KeInitializeEvent(&BampThrottlingWorkerState, SynchronizationEvent, 0);
  KeInitializeEvent(&Object, SynchronizationEvent, 0);
  xmmword_140007520 = 0;
  *((_QWORD *)&xmmword_140007520 + 1) = 0x100000000LL;
  xmmword_140007560 = 0;
  xmmword_140007500 = 0;
  *((_QWORD *)&xmmword_140007500 + 1) = 0;
  *((_QWORD *)&xmmword_140007560 + 1) = 0x200000000LL;
  xmmword_1400074F0 = 0;
  xmmword_140007510 = 0;
  xmmword_140007550 = 0;
  if ( (unsigned int)Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline() )
  {
    xmmword_140007540 = 0;
    *((_QWORD *)&xmmword_140007540 + 1) = 0x200000002LL;
    xmmword_140007530 = 0;
  }
  BampThrottlingLock = 0;
  qword_1400075A0 = (__int64)&qword_140007598;
  qword_140007598 = (__int64)&qword_140007598;
  BampTempBoosts = 0;
  qword_140007588 = 0;
  qword_140007630 = 0;
  BampThrottledProcessTable = 0;
  P = 0;
  return ExUuidCreate(&BampSessionGuid);
}

```

## disassembly

```asm
0x14000c474  sub     rsp, 28h
0x14000c478  xor     r8d, r8d; State
0x14000c47b  lea     rcx, BampThrottlingWorkerState; Event
0x14000c482  lea     edx, [r8+1]; Type
0x14000c486  call    cs:__imp_KeInitializeEvent
0x14000c48d  nop     dword ptr [rax+rax+00h]
0x14000c492  xor     r8d, r8d; State
0x14000c495  lea     rcx, Object; Event
0x14000c49c  lea     edx, [r8+1]; Type
0x14000c4a0  call    cs:__imp_KeInitializeEvent
0x14000c4a7  nop     dword ptr [rax+rax+00h]
0x14000c4ac  xorps   xmm0, xmm0
0x14000c4af  movups  cs:xmmword_140007520, xmm0
0x14000c4b6  mov     dword ptr cs:xmmword_140007520+8, 0
0x14000c4c0  movups  cs:xmmword_140007560, xmm0
0x14000c4c7  mov     dword ptr cs:xmmword_140007520+0Ch, 1
0x14000c4d1  movups  cs:xmmword_140007500, xmm0
0x14000c4d8  mov     qword ptr cs:xmmword_140007500+8, 0
0x14000c4e3  mov     dword ptr cs:xmmword_140007560+8, 0
0x14000c4ed  mov     dword ptr cs:xmmword_140007560+0Ch, 2
0x14000c4f7  movups  cs:xmmword_1400074F0, xmm0
0x14000c4fe  movups  cs:xmmword_140007510, xmm0
0x14000c505  movups  cs:xmmword_140007550, xmm0
0x14000c50c  call    Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline
0x14000c511  test    eax, eax
0x14000c513  jz      short loc_14000C53A
0x14000c515  xorps   xmm0, xmm0
0x14000c518  movups  cs:xmmword_140007540, xmm0
0x14000c51f  mov     dword ptr cs:xmmword_140007540+8, 2
0x14000c529  mov     dword ptr cs:xmmword_140007540+0Ch, 2
0x14000c533  movups  cs:xmmword_140007530, xmm0
0x14000c53a  lea     rax, qword_140007598
0x14000c541  mov     cs:BampThrottlingLock, 0
0x14000c54c  xorps   xmm0, xmm0
0x14000c54f  mov     cs:qword_1400075A0, rax
0x14000c556  lea     rcx, BampSessionGuid; Uuid
0x14000c55d  mov     cs:qword_140007598, rax
0x14000c564  movdqu  cs:BampTempBoosts, xmm0
0x14000c56c  mov     cs:qword_140007588, 0
0x14000c577  mov     cs:qword_140007630, 0
0x14000c582  mov     cs:BampThrottledProcessTable, 0
0x14000c58d  mov     cs:P, 0
0x14000c598  call    cs:__imp_ExUuidCreate
0x14000c59f  nop     dword ptr [rax+rax+00h]
0x14000c5a4  add     rsp, 28h
0x14000c5a8  retn
```
