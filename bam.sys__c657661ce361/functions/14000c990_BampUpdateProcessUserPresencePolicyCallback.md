# BampUpdateProcessUserPresencePolicyCallback

- ea: `0x14000c990`
- end: `0x14000c9eb`
- name: `BampUpdateProcessUserPresencePolicyCallback`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x14000c990`
- `0x140010760`
- `0x1400107a0`
- `0x140011090`
- `0x140011160`
- `0x1400113a0`
- `0x1400113f0`

## pseudocode

```c
char __fastcall BampUpdateProcessUserPresencePolicyCallback(__int64 a1)
{
  __int64 v2; // rcx
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h]

  v4 = 0;
  v5 = 0;
  BampAcquireThrottledProcessLock(a1);
  BampThrottledProcessGetEffectiveState(a1, &v4);
  BampReleaseThrottledProcessLock(v2);
  if ( (v4 & 2) != 0 )
  {
    BampAcquireThrottlingWorkerLock();
    BampQueueThrottledProcessActionItem(a1, 1, 0, 0);
    BampReleaseThrottlingWorkerLock();
  }
  return 1;
}

```

## disassembly

```asm
0x14000c990  push    rbx
0x14000c992  sub     rsp, 40h
0x14000c996  xorps   xmm0, xmm0
0x14000c999  xor     eax, eax
0x14000c99b  movups  [rsp+48h+var_28], xmm0
0x14000c9a0  mov     [rsp+48h+var_18], rax
0x14000c9a5  mov     rbx, rcx
0x14000c9a8  call    BampAcquireThrottledProcessLock
0x14000c9ad  lea     rdx, [rsp+48h+var_28]
0x14000c9b2  mov     rcx, rbx
0x14000c9b5  call    BampThrottledProcessGetEffectiveState
0x14000c9ba  call    BampReleaseThrottledProcessLock
0x14000c9bf  test    byte ptr [rsp+48h+var_28], 2
0x14000c9c4  jz      short loc_14000C9E2
0x14000c9c6  call    BampAcquireThrottlingWorkerLock
0x14000c9cb  xor     r9d, r9d
0x14000c9ce  xor     r8d, r8d
0x14000c9d1  mov     rcx, rbx
0x14000c9d4  lea     edx, [r9+1]
0x14000c9d8  call    BampQueueThrottledProcessActionItem
0x14000c9dd  call    BampReleaseThrottlingWorkerLock
0x14000c9e2  mov     al, 1
0x14000c9e4  add     rsp, 40h
0x14000c9e8  pop     rbx
0x14000c9e9  retn
```
