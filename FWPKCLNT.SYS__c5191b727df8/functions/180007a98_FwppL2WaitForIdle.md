# FwppL2WaitForIdle

- ea: `0x180007a98`
- end: `0x180007af0`
- name: `FwppL2WaitForIdle`
- size: `88`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007910`
- `0x18001c2f0`
- `0x18001c5a0`

## callees

- `0x180007a98`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x180007ad0`
- `ntoskrnl!KeDelayExecutionThread` at `0x180007ad0`

## pseudocode

```c
__int64 __fastcall FwppL2WaitForIdle(volatile signed __int32 *a1)
{
  __int64 result; // rax
  union _LARGE_INTEGER Interval; // [rsp+38h] [rbp+10h] BYREF

  Interval.QuadPart = 0;
  _InterlockedAdd(a1, 0xC0000001);
  Interval.QuadPart = -10000;
  for ( result = (unsigned int)_InterlockedCompareExchange(a1, -1073741823, -1073741823);
        (_DWORD)result != -1073741823;
        result = (unsigned int)_InterlockedCompareExchange(a1, -1073741823, -1073741823) )
  {
    KeDelayExecutionThread(0, 0, &Interval);
  }
  return result;
}

```

## disassembly

```asm
0x180007a98  mov     [rsp+arg_0], rbx
0x180007a9d  push    rdi
0x180007a9e  sub     rsp, 20h
0x180007aa2  mov     rbx, rcx
0x180007aa5  mov     qword ptr [rsp+28h+Interval], 0
0x180007aae  mov     edi, 0C0000001h
0x180007ab3  lock add [rcx], edi
0x180007ab6  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFFFD8F0h
0x180007abf  mov     eax, edi
0x180007ac1  lock cmpxchg [rcx], edi
0x180007ac5  jz      short loc_180007AE4
0x180007ac7  lea     r8, [rsp+28h+Interval]; Interval
0x180007acc  xor     edx, edx; Alertable
0x180007ace  xor     ecx, ecx; WaitMode
0x180007ad0  call    cs:__imp_KeDelayExecutionThread
0x180007ad7  nop     dword ptr [rax+rax+00h]
0x180007adc  mov     eax, edi
0x180007ade  lock cmpxchg [rbx], edi
0x180007ae2  jnz     short loc_180007AC7
0x180007ae4  mov     rbx, [rsp+28h+arg_0]
0x180007ae9  add     rsp, 20h
0x180007aed  pop     rdi
0x180007aee  retn
```
