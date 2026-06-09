# MakeSureStartupProcessingComplete(bool)

- ea: `0x140007edc`
- end: `0x140007f34`
- name: `?MakeSureStartupProcessingComplete@@YA_N_N@Z`
- size: `88`
- prototype: `bool __fastcall(char)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400122d4`
- `0x1400127c8`
- `0x140014334`
- `0x140014d60`
- `0x14001503c`

## callees

- `0x140006344`
- `0x14000695c`
- `0x140007edc`
- `0x14001c680`

## pseudocode

```c
bool __fastcall MakeSureStartupProcessingComplete(char a1)
{
  bool v1; // bl
  _QWORD v3[2]; // [rsp+20h] [rbp-28h] BYREF
  char v4; // [rsp+30h] [rbp-18h]

  if ( a1 )
  {
    v1 = 1;
    MonitoredCritSecLocker::MonitoredCritSecLocker(
      (MonitoredCritSecLocker *)v3,
      (struct MonitoredCritSec *)&vTiStartupProcessingLock,
      1);
  }
  else
  {
    v4 = 0;
    v3[1] = &vTiStartupProcessingLock;
    v3[0] = &TiCoreLocker::`vftable';
    v1 = MonitoredCritSecLocker::TryLock((MonitoredCritSecLocker *)v3);
  }
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v3);
  return v1;
}

```

## disassembly

```asm
0x140007edc  push    rbx
0x140007ede  sub     rsp, 40h
0x140007ee2  test    cl, cl
0x140007ee4  lea     rcx, [rsp+48h+var_28]; this
0x140007ee9  jz      short loc_140007EFE
0x140007eeb  mov     bl, 1
0x140007eed  lea     rdx, ?vTiStartupProcessingLock@@3UMonitoredCritSec@@A; struct MonitoredCritSec *
0x140007ef4  mov     r8b, bl; bool
0x140007ef7  call    ??0MonitoredCritSecLocker@@QEAA@AEAUMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(MonitoredCritSec &,bool)
0x140007efc  jmp     short loc_140007F22
0x140007efe  lea     rax, ?vTiStartupProcessingLock@@3UMonitoredCritSec@@A; MonitoredCritSec vTiStartupProcessingLock
0x140007f05  mov     [rsp+48h+var_18], 0
0x140007f0a  mov     [rsp+48h+var_20], rax
0x140007f0f  lea     rax, ??_7TiCoreLocker@@6B@; const TiCoreLocker::`vftable'
0x140007f16  mov     [rsp+48h+var_28], rax
0x140007f1b  call    ?TryLock@MonitoredCritSecLocker@@UEAA_NXZ; MonitoredCritSecLocker::TryLock(void)
0x140007f20  mov     bl, al
0x140007f22  lea     rcx, [rsp+48h+var_28]; this
0x140007f27  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x140007f2c  mov     al, bl
0x140007f2e  add     rsp, 40h
0x140007f32  pop     rbx
0x140007f33  retn
```
