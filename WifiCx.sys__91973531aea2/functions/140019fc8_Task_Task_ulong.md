# Task::Task(ulong)

- ea: `0x140019fc8`
- end: `0x14001a1da`
- name: `??0Task@@QEAA@K@Z`
- size: `530`
- prototype: `Task *__fastcall(Task *__hidden this, unsigned int)`
- caller_count: `16`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400072a0`
- `0x140026010`
- `0x14002b16c`
- `0x14004c7d4`
- `0x14004c9e4`
- `0x14005fd78`
- `0x14005fdfc`
- `0x1400686e0`
- `0x14006f4c8`
- `0x14006f708`
- `0x14006fb84`
- `0x14007692c`
- `0x14007fe98`
- `0x14008fa54`
- `0x14009c77c`
- `0x1400a0c7c`

## callees

- `0x140019fc8`
- `0x14001a1e0`

## pseudocode

```c
Task *__fastcall Task::Task(Task *this, unsigned int a2)
{
  unsigned int v2; // r10d
  __int64 v3; // r11
  Task *v4; // rdx
  unsigned int NextActivityId; // eax
  char *v6; // r8
  unsigned int v7; // eax
  char *v8; // r9
  unsigned int v9; // eax
  char *v10; // r8
  unsigned int v11; // eax
  char *v12; // r8
  Task *result; // rax

  v2 = a2;
  *(_QWORD *)this = &WxNdisProtocolOffload::`vftable';
  v3 = 0;
  v4 = this;
  *((_QWORD *)this + 1) = &WxNdisProtocolOffload::`vftable';
  *((_QWORD *)this + 2) = &WxNdisProtocolOffload::`vftable';
  if ( v2 )
    NextActivityId = v2;
  else
    NextActivityId = IActivityId::get_NextActivityId();
  *((_DWORD *)v4 + 8) = NextActivityId;
  *(_QWORD *)v4 = &Task::`vftable'{for `IOperationCompletionCallback'};
  *((_QWORD *)v4 + 1) = &Task::`vftable'{for `IEventQueueCallback'};
  *((_QWORD *)v4 + 2) = &Task::`vftable'{for `INotifyDeviceIndicationCallback'};
  *((_QWORD *)v4 + 3) = &Task::`vftable'{for `ITimerCallback'};
  v6 = (char *)v4 + 56;
  *((_QWORD *)v4 + 5) = v3;
  *((_DWORD *)v4 + 12) = v3;
  *((_BYTE *)v4 + 52) = v3;
  if ( v2 )
    v7 = v2;
  else
    v7 = IActivityId::get_NextActivityId();
  *((_DWORD *)v6 + 2) = v7;
  *(_QWORD *)v6 = &CancelDeviceCommand::`vftable';
  v8 = v6 + 16;
  if ( v2 )
    v9 = v2;
  else
    v9 = IActivityId::get_NextActivityId();
  *(_DWORD *)v8 = v9;
  *((_QWORD *)v8 + 1) = v3;
  *((_DWORD *)v8 + 4) = v3;
  *((_QWORD *)v8 + 4) = v3;
  *((_DWORD *)v8 + 10) = v3;
  *((_DWORD *)v8 + 11) = 1;
  if ( v8 != (char *)-48LL )
  {
    *((_QWORD *)v8 + 7) = v8 + 48;
    *((_QWORD *)v8 + 6) = v8 + 48;
    *((_QWORD *)v8 + 8) = v8;
  }
  *((_QWORD *)v6 + 11) = v3;
  *((_DWORD *)v6 + 24) = v3;
  *((_DWORD *)v6 + 32) = v3;
  *((_QWORD *)v6 + 17) = v3;
  *((_DWORD *)v6 + 36) = v3;
  *((_QWORD *)v6 + 19) = v3;
  *((_DWORD *)v6 + 40) = v3;
  *((_DWORD *)v6 + 41) = 0xFFFF;
  *((_QWORD *)v6 + 21) = v3;
  if ( v6 != (char *)-104LL )
  {
    *((_QWORD *)v6 + 14) = v6 + 104;
    *((_QWORD *)v6 + 13) = v6 + 104;
    *((_QWORD *)v6 + 15) = v6;
  }
  *((_QWORD *)v4 + 30) = v3;
  v10 = (char *)v4 + 280;
  *((_QWORD *)v4 + 31) = v3;
  *((_QWORD *)v4 + 32) = v3;
  *((_DWORD *)v4 + 66) = v3;
  *((_QWORD *)v4 + 34) = v3;
  if ( v2 )
    v11 = v2;
  else
    v11 = IActivityId::get_NextActivityId();
  *(_DWORD *)v10 = v11;
  *((_QWORD *)v10 + 1) = v3;
  *((_DWORD *)v10 + 4) = v3;
  *((_QWORD *)v10 + 4) = v3;
  *((_DWORD *)v10 + 10) = v3;
  *((_DWORD *)v10 + 11) = 1;
  if ( v10 != (char *)-48LL )
  {
    *((_QWORD *)v10 + 7) = v10 + 48;
    *((_QWORD *)v10 + 6) = v10 + 48;
    *((_QWORD *)v10 + 8) = v10;
  }
  v12 = (char *)v4 + 352;
  if ( !v2 )
    v2 = IActivityId::get_NextActivityId();
  *(_DWORD *)v12 = v2;
  *((_QWORD *)v12 + 1) = v3;
  *((_DWORD *)v12 + 4) = v3;
  *((_QWORD *)v12 + 4) = v3;
  *((_DWORD *)v12 + 10) = v3;
  *((_DWORD *)v12 + 11) = 1;
  if ( v12 != (char *)-48LL )
  {
    *((_QWORD *)v12 + 7) = v12 + 48;
    *((_QWORD *)v12 + 6) = v12 + 48;
    *((_QWORD *)v12 + 8) = v12;
  }
  *((_BYTE *)v4 + 424) = v3;
  result = v4;
  *((_DWORD *)v4 + 107) = v3;
  *((_QWORD *)v4 + 54) = v3;
  *((_DWORD *)v4 + 110) = -1073741823;
  *((_DWORD *)v4 + 111) = v3;
  *((_BYTE *)v4 + 456) = v3;
  *((_QWORD *)v4 + 58) = v3;
  return result;
}

```

## disassembly

```asm
0x140019fc8  sub     rsp, 28h
0x140019fcc  lea     rax, ??_7WxNdisProtocolOffload@@6B@; const WxNdisProtocolOffload::`vftable'
0x140019fd3  mov     r10d, edx
0x140019fd6  mov     [rcx], rax
0x140019fd9  xor     r11d, r11d
0x140019fdc  lea     rax, ??_7WxNdisProtocolOffload@@6B@; const WxNdisProtocolOffload::`vftable'
0x140019fe3  mov     rdx, rcx
0x140019fe6  mov     [rcx+8], rax
0x140019fea  lea     rax, ??_7WxNdisProtocolOffload@@6B@; const WxNdisProtocolOffload::`vftable'
0x140019ff1  mov     [rcx+10h], rax
0x140019ff5  test    r10d, r10d
0x140019ff8  jnz     short loc_14001A001
0x140019ffa  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x140019fff  jmp     short loc_14001A004
0x14001a001  mov     eax, r10d
0x14001a004  mov     [rdx+20h], eax
0x14001a007  lea     rax, ??_7Task@@6BIOperationCompletionCallback@@@; const Task::`vftable'{for `IOperationCompletionCallback'}
0x14001a00e  mov     [rdx], rax
0x14001a011  lea     rax, ??_7Task@@6BIEventQueueCallback@@@; const Task::`vftable'{for `IEventQueueCallback'}
0x14001a018  mov     [rdx+8], rax
0x14001a01c  lea     rax, ??_7Task@@6BINotifyDeviceIndicationCallback@@@; const Task::`vftable'{for `INotifyDeviceIndicationCallback'}
0x14001a023  mov     [rdx+10h], rax
0x14001a027  lea     rax, ??_7Task@@6BITimerCallback@@@; const Task::`vftable'{for `ITimerCallback'}
0x14001a02e  mov     [rdx+18h], rax
0x14001a032  lea     r8, [rdx+38h]
0x14001a036  mov     [rdx+28h], r11
0x14001a03a  mov     [rdx+30h], r11d
0x14001a03e  mov     [rdx+34h], r11b
0x14001a042  test    r10d, r10d
0x14001a045  jnz     short loc_14001A04E
0x14001a047  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x14001a04c  jmp     short loc_14001A051
0x14001a04e  mov     eax, r10d
0x14001a051  mov     [r8+8], eax
0x14001a055  lea     rax, ??_7CancelDeviceCommand@@6B@; const CancelDeviceCommand::`vftable'
0x14001a05c  mov     [r8], rax
0x14001a05f  lea     r9, [r8+10h]
0x14001a063  test    r10d, r10d
0x14001a066  jnz     short loc_14001A06F
0x14001a068  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x14001a06d  jmp     short loc_14001A072
0x14001a06f  mov     eax, r10d
0x14001a072  mov     [r9], eax
0x14001a075  lea     rax, [r9+30h]
0x14001a079  mov     [r9+8], r11
0x14001a07d  mov     [r9+10h], r11d
0x14001a081  mov     [r9+20h], r11
0x14001a085  mov     [r9+28h], r11d
0x14001a089  mov     dword ptr [r9+2Ch], 1
0x14001a091  test    rax, rax
0x14001a094  jz      short loc_14001A0A1
0x14001a096  mov     [rax+8], rax
0x14001a09a  mov     [rax], rax
0x14001a09d  mov     [rax+10h], r9
0x14001a0a1  lea     rax, [r8+68h]
0x14001a0a5  mov     [r8+58h], r11
0x14001a0a9  mov     [r8+60h], r11d
0x14001a0ad  mov     [r8+80h], r11d
0x14001a0b4  mov     [r8+88h], r11
0x14001a0bb  mov     [r8+90h], r11d
0x14001a0c2  mov     [r8+98h], r11
0x14001a0c9  mov     [r8+0A0h], r11d
0x14001a0d0  mov     dword ptr [r8+0A4h], 0FFFFh
0x14001a0db  mov     [r8+0A8h], r11
0x14001a0e2  test    rax, rax
0x14001a0e5  jz      short loc_14001A0F2
0x14001a0e7  mov     [rax+8], rax
0x14001a0eb  mov     [rax], rax
0x14001a0ee  mov     [rax+10h], r8
0x14001a0f2  mov     [rdx+0F0h], r11
0x14001a0f9  lea     r8, [rdx+118h]
0x14001a100  mov     [rdx+0F8h], r11
0x14001a107  mov     [rdx+100h], r11
0x14001a10e  mov     [rdx+108h], r11d
0x14001a115  mov     [rdx+110h], r11
0x14001a11c  test    r10d, r10d
0x14001a11f  jnz     short loc_14001A128
0x14001a121  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x14001a126  jmp     short loc_14001A12B
0x14001a128  mov     eax, r10d
0x14001a12b  mov     [r8], eax
0x14001a12e  lea     rax, [r8+30h]
0x14001a132  mov     [r8+8], r11
0x14001a136  mov     [r8+10h], r11d
0x14001a13a  mov     [r8+20h], r11
0x14001a13e  mov     [r8+28h], r11d
0x14001a142  mov     dword ptr [r8+2Ch], 1
0x14001a14a  test    rax, rax
0x14001a14d  jz      short loc_14001A15A
0x14001a14f  mov     [rax+8], rax
0x14001a153  mov     [rax], rax
0x14001a156  mov     [rax+10h], r8
0x14001a15a  lea     r8, [rdx+160h]
0x14001a161  test    r10d, r10d
0x14001a164  jnz     short loc_14001A16E
0x14001a166  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x14001a16b  mov     r10d, eax
0x14001a16e  lea     rax, [r8+30h]
0x14001a172  mov     [r8], r10d
0x14001a175  mov     [r8+8], r11
0x14001a179  mov     [r8+10h], r11d
0x14001a17d  mov     [r8+20h], r11
0x14001a181  mov     [r8+28h], r11d
0x14001a185  mov     dword ptr [r8+2Ch], 1
0x14001a18d  test    rax, rax
0x14001a190  jz      short loc_14001A19D
0x14001a192  mov     [rax+8], rax
0x14001a196  mov     [rax], rax
0x14001a199  mov     [rax+10h], r8
0x14001a19d  mov     [rdx+1A8h], r11b
0x14001a1a4  mov     rax, rdx
0x14001a1a7  mov     [rdx+1ACh], r11d
0x14001a1ae  mov     [rdx+1B0h], r11
0x14001a1b5  mov     dword ptr [rdx+1B8h], 0C0000001h
0x14001a1bf  mov     [rdx+1BCh], r11d
0x14001a1c6  mov     [rdx+1C8h], r11b
0x14001a1cd  mov     [rdx+1D0h], r11
0x14001a1d4  add     rsp, 28h
0x14001a1d8  retn
```
