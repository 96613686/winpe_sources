# BampQueuePolicyActionItemAfterStateChange

- ea: `0x140010990`
- end: `0x140010a1c`
- name: `BampQueuePolicyActionItemAfterStateChange`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011660`
- `0x140013d40`

## callees

- `0x140010990`
- `0x140010a30`
- `0x140011160`
- `0x1400113a0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010a09`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010a09`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400109fd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400109fd`

## pseudocode

```c
void __fastcall BampQueuePolicyActionItemAfterStateChange(__int64 a1)
{
  unsigned __int64 v2; // rax
  __int64 v3; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v4; // [rsp+28h] [rbp-10h]

  v3 = 0;
  v4 = 0;
  BampComputeThrottledProcessPolicy(a1, (__int64)&v3);
  v2 = *(_QWORD *)(a1 + 352) - v3;
  if ( !v2 )
    v2 = *(unsigned int *)(a1 + 360) - (unsigned __int64)v4;
  if ( v2 )
  {
    BampAcquireThrottlingWorkerLock();
    BampQueueThrottledProcessActionItem(a1, 1, 0, 2);
    qword_140007590 = 0;
    ExReleasePushLockExclusiveEx(&qword_140007588, 0);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x140010990  push    rbx
0x140010992  sub     rsp, 30h
0x140010996  xor     eax, eax
0x140010998  lea     rdx, [rsp+38h+var_18]
0x14001099d  mov     [rsp+38h+var_18], rax
0x1400109a2  mov     rbx, rcx
0x1400109a5  mov     [rsp+38h+var_10], eax
0x1400109a9  call    BampComputeThrottledProcessPolicy
0x1400109ae  mov     rax, [rbx+160h]
0x1400109b5  sub     rax, [rsp+38h+var_18]
0x1400109ba  jnz     short loc_1400109C9
0x1400109bc  mov     eax, [rbx+168h]
0x1400109c2  mov     ecx, [rsp+38h+var_10]
0x1400109c6  sub     rax, rcx
0x1400109c9  test    rax, rax
0x1400109cc  jz      short loc_140010A15
0x1400109ce  call    BampAcquireThrottlingWorkerLock
0x1400109d3  mov     r9d, 2
0x1400109d9  xor     r8d, r8d
0x1400109dc  mov     edx, 1
0x1400109e1  mov     rcx, rbx
0x1400109e4  call    BampQueueThrottledProcessActionItem
0x1400109e9  xor     edx, edx
0x1400109eb  mov     cs:qword_140007590, 0
0x1400109f6  lea     rcx, qword_140007588
0x1400109fd  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140010a04  nop     dword ptr [rax+rax+00h]
0x140010a09  call    cs:__imp_KeLeaveCriticalRegion
0x140010a10  nop     dword ptr [rax+rax+00h]
0x140010a15  add     rsp, 30h
0x140010a19  pop     rbx
0x140010a1a  retn
```
