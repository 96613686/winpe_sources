# _dynamic_initializer_for__g_rwWildcardLock__

- ea: `0x1800010d0`
- end: `0x180001126`
- name: `_dynamic_initializer_for__g_rwWildcardLock__`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001c30`

## import_xrefs

- `KERNEL32!CreateMutexA` at `0x1800010f4`
- `KERNEL32!CreateMutexA` at `0x1800010f4`
- `KERNEL32!CreateEventA` at `0x1800010e0`
- `KERNEL32!CreateEventA` at `0x1800010e0`

## pseudocode

```c
int dynamic_initializer_for__g_rwWildcardLock__()
{
  HANDLE MutexA; // rax

  hEvent = CreateEventA(0, 1, 1, 0);
  MutexA = CreateMutexA(0, 0, 0);
  Handles = hEvent;
  hMutex = MutexA;
  qword_1800129A0 = (__int64)MutexA;
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_rwWildcardLock__);
}

```

## disassembly

```asm
0x1800010d0  sub     rsp, 28h
0x1800010d4  xor     r9d, r9d; lpName
0x1800010d7  xor     ecx, ecx; lpEventAttributes
0x1800010d9  lea     edx, [r9+1]; bManualReset
0x1800010dd  mov     r8d, edx; bInitialState
0x1800010e0  call    cs:__imp_CreateEventA
0x1800010e6  xor     r8d, r8d; lpName
0x1800010e9  xor     edx, edx; bInitialOwner
0x1800010eb  xor     ecx, ecx; lpMutexAttributes
0x1800010ed  mov     cs:hEvent, rax
0x1800010f4  call    cs:__imp_CreateMutexA
0x1800010fa  mov     rcx, cs:hEvent
0x180001101  mov     cs:Handles, rcx
0x180001108  lea     rcx, _dynamic_atexit_destructor_for__g_rwWildcardLock__
0x18000110f  mov     cs:hMutex, rax
0x180001116  mov     cs:qword_1800129A0, rax
0x18000111d  add     rsp, 28h
0x180001121  jmp     atexit
```
