# BampTempBoostCheck

- ea: `0x14000c0c8`
- end: `0x14000c185`
- name: `BampTempBoostCheck`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001474c`

## callees

- `0x14000c0c8`
- `0x14000c464`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c0d6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c0d6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c0eb`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c0eb`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c15b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c15b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c167`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c167`

## pseudocode

```c
bool __fastcall BampTempBoostCheck(int a1)
{
  unsigned __int64 v1; // rbx
  int v2; // edi
  int v3; // eax
  unsigned __int64 v4; // rax
  int v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = a1;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&qword_140007630, 0);
  v1 = BampTempBoosts;
  if ( (BYTE8(BampTempBoosts) & 1) != 0 && (_QWORD)BampTempBoosts )
    v1 = (unsigned __int64)&BampTempBoosts ^ BampTempBoosts;
  v2 = BYTE8(BampTempBoosts) & 1;
  while ( v1 )
  {
    v3 = BampTempBoostsTreeCompareRoutine(&v6, v1);
    if ( v3 >= 0 )
    {
      if ( v3 <= 0 )
        break;
      v4 = *(_QWORD *)(v1 + 8);
    }
    else
    {
      v4 = *(_QWORD *)v1;
    }
    if ( v2 && v4 )
      v1 ^= v4;
    else
      v1 = v4;
  }
  ExReleasePushLockSharedEx(&qword_140007630, 0);
  KeLeaveCriticalRegion();
  return v1 != 0;
}

```

## disassembly

```asm
0x14000c0c8  mov     [rsp+arg_8], rbx
0x14000c0cd  mov     [rsp+arg_0], ecx
0x14000c0d1  push    rdi
0x14000c0d2  sub     rsp, 20h
0x14000c0d6  call    cs:__imp_KeEnterCriticalRegion
0x14000c0dd  nop     dword ptr [rax+rax+00h]
0x14000c0e2  xor     edx, edx
0x14000c0e4  lea     rcx, qword_140007630
0x14000c0eb  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000c0f2  nop     dword ptr [rax+rax+00h]
0x14000c0f7  mov     rax, qword ptr cs:BampTempBoosts+8
0x14000c0fe  mov     rbx, qword ptr cs:BampTempBoosts
0x14000c105  test    al, 1
0x14000c107  jz      short loc_14000C118
0x14000c109  test    rbx, rbx
0x14000c10c  jz      short loc_14000C118
0x14000c10e  lea     rcx, BampTempBoosts
0x14000c115  xor     rbx, rcx
0x14000c118  movzx   edi, al
0x14000c11b  and     edi, 1
0x14000c11e  jmp     short loc_14000C14D
0x14000c120  mov     rdx, rbx
0x14000c123  lea     rcx, [rsp+28h+arg_0]
0x14000c128  call    BampTempBoostsTreeCompareRoutine
0x14000c12d  test    eax, eax
0x14000c12f  jns     short loc_14000C136
0x14000c131  mov     rax, [rbx]
0x14000c134  jmp     short loc_14000C13C
0x14000c136  jle     short loc_14000C152
0x14000c138  mov     rax, [rbx+8]
0x14000c13c  test    edi, edi
0x14000c13e  jz      short loc_14000C14A
0x14000c140  test    rax, rax
0x14000c143  jz      short loc_14000C14A
0x14000c145  xor     rbx, rax
0x14000c148  jmp     short loc_14000C14D
0x14000c14a  mov     rbx, rax
0x14000c14d  test    rbx, rbx
0x14000c150  jnz     short loc_14000C120
0x14000c152  xor     edx, edx
0x14000c154  lea     rcx, qword_140007630
0x14000c15b  call    cs:__imp_ExReleasePushLockSharedEx
0x14000c162  nop     dword ptr [rax+rax+00h]
0x14000c167  call    cs:__imp_KeLeaveCriticalRegion
0x14000c16e  nop     dword ptr [rax+rax+00h]
0x14000c173  test    rbx, rbx
0x14000c176  mov     rbx, [rsp+28h+arg_8]
0x14000c17b  setnz   al
0x14000c17e  add     rsp, 20h
0x14000c182  pop     rdi
0x14000c183  retn
```
