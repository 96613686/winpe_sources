# BampThrottlingShutdownModule

- ea: `0x14000c83c`
- end: `0x14000c985`
- name: `BampThrottlingShutdownModule`
- size: `329`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000b260`
- `0x140016078`

## callees

- `0x14000c83c`
- `0x140010308`
- `0x1400113a0`
- `0x1400113f0`
- `0x140012c1c`
- `0x140012c50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c90f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c90f`
- `ntoskrnl!KeSetEvent` at `0x14000c947`
- `ntoskrnl!KeSetEvent` at `0x14000c947`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14000c95f`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14000c95f`
- `ntoskrnl!ZwClose` at `0x14000c972`
- `ntoskrnl!ZwClose` at `0x14000c972`

## pseudocode

```c
NTSTATUS BampThrottlingShutdownModule()
{
  _WORD *v0; // rax
  _WORD **j; // rdx
  _WORD **i; // rdx
  NTSTATUS result; // eax

  BampAcquireThrottlingLockExclusive();
  if ( P && (v0 = *(_WORD **)P, (*(_QWORD *)P & 1) == 0) )
  {
LABEL_13:
    while ( v0 )
    {
      BampRemoveThrottledProcessFromTable(v0);
      if ( P )
      {
        v0 = *(_WORD **)P;
        if ( (*(_QWORD *)P & 1) == 0 )
          continue;
      }
      for ( i = (_WORD **)((char *)P + 8);
            i < (_WORD **)((char *)P + 8 * ((unsigned __int64)HIDWORD(BampThrottledProcessTable) >> 5));
            ++i )
      {
        v0 = *i;
        if ( ((unsigned __int8)*i & 1) == 0 )
          goto LABEL_13;
      }
      break;
    }
  }
  else
  {
    for ( j = (_WORD **)((char *)P + 8);
          j < (_WORD **)((char *)P + 8 * ((unsigned __int64)HIDWORD(BampThrottledProcessTable) >> 5));
          ++j )
    {
      v0 = *j;
      if ( ((unsigned __int8)*j & 1) == 0 )
        goto LABEL_13;
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0x4B6D6142u);
  result = BampReleaseThrottlingLockExclusive();
  if ( Handle )
  {
    BampAcquireThrottlingWorkerLock();
    byte_1400075A8 |= 1u;
    BampReleaseThrottlingWorkerLock();
    KeSetEvent(&BampThrottlingWorkerState, 0, 0);
    ZwWaitForSingleObject(Handle, 0, 0);
    return ZwClose(Handle);
  }
  return result;
}

```

## disassembly

```asm
0x14000c83c  push    rdi
0x14000c83e  sub     rsp, 20h
0x14000c842  call    BampAcquireThrottlingLockExclusive
0x14000c847  mov     rdx, cs:P
0x14000c84e  mov     rdi, 8000000000000002h
0x14000c858  test    rdx, rdx
0x14000c85b  jz      short loc_14000C878
0x14000c85d  mov     rax, [rdx]
0x14000c860  and     rax, rdi
0x14000c863  cmp     rax, rdi
0x14000c866  jnz     short loc_14000C86D
0x14000c868  xor     eax, eax
0x14000c86a  mov     rcx, [rax]
0x14000c86d  mov     rax, [rdx]
0x14000c870  test    al, 1
0x14000c872  jz      loc_14000C8F9
0x14000c878  mov     ecx, dword ptr cs:BampThrottledProcessTable+4
0x14000c87e  add     rdx, 8
0x14000c882  mov     rax, cs:P
0x14000c889  shr     rcx, 5
0x14000c88d  lea     r8, [rax+rcx*8]
0x14000c891  cmp     rdx, r8
0x14000c894  jnb     short loc_14000C8FE
0x14000c896  mov     rax, [rdx]
0x14000c899  test    al, 1
0x14000c89b  jz      short loc_14000C8F9
0x14000c89d  add     rdx, 8
0x14000c8a1  jmp     short loc_14000C891
0x14000c8a3  mov     rcx, rax; P
0x14000c8a6  call    BampRemoveThrottledProcessFromTable
0x14000c8ab  mov     rdx, cs:P
0x14000c8b2  test    rdx, rdx
0x14000c8b5  jz      short loc_14000C8CE
0x14000c8b7  mov     rax, [rdx]
0x14000c8ba  and     rax, rdi
0x14000c8bd  cmp     rax, rdi
0x14000c8c0  jnz     short loc_14000C8C7
0x14000c8c2  xor     eax, eax
0x14000c8c4  mov     rcx, [rax]
0x14000c8c7  mov     rax, [rdx]
0x14000c8ca  test    al, 1
0x14000c8cc  jz      short loc_14000C8F9
0x14000c8ce  mov     ecx, dword ptr cs:BampThrottledProcessTable+4
0x14000c8d4  add     rdx, 8
0x14000c8d8  mov     rax, cs:P
0x14000c8df  shr     rcx, 5
0x14000c8e3  lea     r8, [rax+rcx*8]
0x14000c8e7  cmp     rdx, r8
0x14000c8ea  jnb     short loc_14000C8FE
0x14000c8ec  mov     rax, [rdx]
0x14000c8ef  test    al, 1
0x14000c8f1  jz      short loc_14000C8F9
0x14000c8f3  add     rdx, 8
0x14000c8f7  jmp     short loc_14000C8E7
0x14000c8f9  test    rax, rax
0x14000c8fc  jnz     short loc_14000C8A3
0x14000c8fe  mov     rcx, cs:P; P
0x14000c905  test    rcx, rcx
0x14000c908  jz      short loc_14000C91B
0x14000c90a  mov     edx, 4B6D6142h; Tag
0x14000c90f  call    cs:__imp_ExFreePoolWithTag
0x14000c916  nop     dword ptr [rax+rax+00h]
0x14000c91b  call    BampReleaseThrottlingLockExclusive
0x14000c920  cmp     cs:Handle, 0
0x14000c928  jz      short loc_14000C97E
0x14000c92a  call    BampAcquireThrottlingWorkerLock
0x14000c92f  or      cs:byte_1400075A8, 1
0x14000c936  call    BampReleaseThrottlingWorkerLock
0x14000c93b  xor     r8d, r8d; Wait
0x14000c93e  lea     rcx, BampThrottlingWorkerState; Event
0x14000c945  xor     edx, edx; Increment
0x14000c947  call    cs:__imp_KeSetEvent
0x14000c94e  nop     dword ptr [rax+rax+00h]
0x14000c953  mov     rcx, cs:Handle; Handle
0x14000c95a  xor     r8d, r8d; Timeout
0x14000c95d  xor     edx, edx; Alertable
0x14000c95f  call    cs:__imp_ZwWaitForSingleObject
0x14000c966  nop     dword ptr [rax+rax+00h]
0x14000c96b  mov     rcx, cs:Handle; Handle
0x14000c972  call    cs:__imp_ZwClose
0x14000c979  nop     dword ptr [rax+rax+00h]
0x14000c97e  add     rsp, 20h
0x14000c982  pop     rdi
0x14000c983  retn
```
