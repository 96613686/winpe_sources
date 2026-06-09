# BampUpdateThrottledProcessSiufState

- ea: `0x1400100b0`
- end: `0x140010209`
- name: `BampUpdateThrottledProcessSiufState`
- size: `345`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140013d40`
- `0x140015100`

## callees

- `0x1400100b0`
- `0x140011160`
- `0x1400113a0`
- `0x140013c7c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010164`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400101f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010164`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400101f8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010158`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400101ec`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010158`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400101ec`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001010c`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001010c`

## pseudocode

```c
void __fastcall BampUpdateThrottledProcessSiufState(_DWORD *P)
{
  int v1; // ebx

  v1 = P[91];
  switch ( v1 )
  {
    case 0:
      v1 = (P[76] & 2) != 0;
      goto LABEL_3;
    case 1:
      if ( (P[76] & 2) != 0 || (P[88] & 2) == 0 )
        goto LABEL_3;
      *((_QWORD *)P + 46) = KeQueryUnbiasedInterruptTime();
      P[91] = 2;
      break;
    case 2:
      if ( (P[76] & 2) != 0 )
      {
        v1 = 3;
        BampAcquireThrottlingWorkerLock();
        BampQueueThrottledProcessActionItem((__int64)P, 2, 0x3A98u, 0);
        qword_140007590 = 0;
        ExReleasePushLockExclusiveEx(&qword_140007588, 0);
        KeLeaveCriticalRegion();
      }
      goto LABEL_3;
    default:
      if ( v1 != 3 || (P[76] & 2) != 0 )
      {
LABEL_3:
        P[91] = v1;
        return;
      }
      BampAcquireThrottlingWorkerLock();
      if ( (P[62] & 1) != 0 )
        BampCancelThrottledProcessActionItem(P);
      qword_140007590 = 0;
      ExReleasePushLockExclusiveEx(&qword_140007588, 0);
      KeLeaveCriticalRegion();
      P[91] = 2;
      break;
  }
}

```

## disassembly

```asm
0x1400100b0  mov     [rsp+arg_0], rbx
0x1400100b5  push    rdi
0x1400100b6  sub     rsp, 20h
0x1400100ba  mov     ebx, [rcx+16Ch]
0x1400100c0  mov     rdi, rcx
0x1400100c3  test    ebx, ebx
0x1400100c5  jnz     short loc_1400100E8
0x1400100c7  test    byte ptr [rcx+130h], 2
0x1400100ce  mov     eax, 1
0x1400100d3  cmovnz  ebx, eax
0x1400100d6  mov     [rdi+16Ch], ebx
0x1400100dc  mov     rbx, [rsp+28h+arg_0]
0x1400100e1  add     rsp, 20h
0x1400100e5  pop     rdi
0x1400100e6  retn
0x1400100e8  mov     ecx, ebx
0x1400100ea  sub     ecx, 1
0x1400100ed  jnz     loc_140010182
0x1400100f3  mov     eax, [rdi+130h]
0x1400100f9  test    al, 2
0x1400100fb  jnz     short loc_1400100D6
0x1400100fd  mov     eax, [rdi+160h]
0x140010103  test    al, 2
0x140010105  jz      short loc_1400100D6
0x140010107  mov     ebx, 2
0x14001010c  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140010113  nop     dword ptr [rax+rax+00h]
0x140010118  mov     [rdi+170h], rax
0x14001011f  mov     [rdi+16Ch], ebx
0x140010125  mov     rbx, [rsp+28h+arg_0]
0x14001012a  add     rsp, 20h
0x14001012e  pop     rdi
0x14001012f  retn
0x140010131  mov     ebx, 2
0x140010136  call    BampAcquireThrottlingWorkerLock
0x14001013b  test    byte ptr [rdi+0F8h], 1
0x140010142  jnz     short loc_1400101A0
0x140010144  xor     edx, edx
0x140010146  mov     cs:qword_140007590, 0
0x140010151  lea     rcx, qword_140007588
0x140010158  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001015f  nop     dword ptr [rax+rax+00h]
0x140010164  call    cs:__imp_KeLeaveCriticalRegion
0x14001016b  nop     dword ptr [rax+rax+00h]
0x140010170  mov     [rdi+16Ch], ebx
0x140010176  mov     rbx, [rsp+28h+arg_0]
0x14001017b  add     rsp, 20h
0x14001017f  pop     rdi
0x140010180  retn
0x140010182  sub     ecx, 1
0x140010185  jz      short loc_1400101AA
0x140010187  cmp     ecx, 1
0x14001018a  jnz     loc_1400100D6
0x140010190  mov     eax, [rdi+130h]
0x140010196  test    al, 2
0x140010198  jnz     loc_1400100D6
0x14001019e  jmp     short loc_140010131
0x1400101a0  mov     rcx, rdi; P
0x1400101a3  call    BampCancelThrottledProcessActionItem
0x1400101a8  jmp     short loc_140010144
0x1400101aa  mov     eax, [rdi+130h]
0x1400101b0  test    al, 2
0x1400101b2  jz      loc_1400100D6
0x1400101b8  mov     ebx, 3
0x1400101bd  call    BampAcquireThrottlingWorkerLock
0x1400101c2  xor     r9d, r9d
0x1400101c5  mov     edx, 2
0x1400101ca  mov     r8d, 3A98h
0x1400101d0  mov     rcx, rdi
0x1400101d3  call    BampQueueThrottledProcessActionItem
0x1400101d8  xor     edx, edx
0x1400101da  mov     cs:qword_140007590, 0
0x1400101e5  lea     rcx, qword_140007588
0x1400101ec  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400101f3  nop     dword ptr [rax+rax+00h]
0x1400101f8  call    cs:__imp_KeLeaveCriticalRegion
0x1400101ff  nop     dword ptr [rax+rax+00h]
0x140010204  jmp     loc_1400100D6
```
