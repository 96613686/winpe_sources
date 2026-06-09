# _Init_thread_header

- ea: `0x18003e85c`
- end: `0x18003e8d7`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x18003b080`
- `0x18004bf10`
- `0x180080710`
- `0x1800807ac`
- `0x18008083c`
- `0x1800808cc`
- `0x180080968`
- `0x1800809f8`
- `0x18008a5b0`
- `0x18008a628`
- `0x18008a6a0`
- `0x18008a718`
- `0x18008a790`
- `0x18008a808`
- `0x18008a880`
- `0x18008a8f8`
- `0x18008a970`
- `0x18008a9e8`
- `0x18008aa60`

## callees

- `0x18003e85c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e8d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e86c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e86c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18003e894`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18003e894`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  AcquireSRWLockExclusive(&SRWLock);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    SleepConditionVariableSRW(&ConditionVariable, &SRWLock, 0xFFFFFFFF, 0);
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x18003e85c  push    rbx
0x18003e85e  sub     rsp, 20h
0x18003e862  mov     rbx, rcx
0x18003e865  lea     rcx, SRWLock; SRWLock
0x18003e86c  call    cs:__imp_AcquireSRWLockExclusive
0x18003e872  cmp     dword ptr [rbx], 0
0x18003e875  jnz     short loc_18003E89C
0x18003e877  mov     dword ptr [rbx], 0FFFFFFFFh
0x18003e87d  jmp     short loc_18003E8C4
0x18003e87f  xor     r9d, r9d; Flags
0x18003e882  lea     rdx, SRWLock; SRWLock
0x18003e889  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18003e88d  lea     rcx, ConditionVariable; ConditionVariable
0x18003e894  call    cs:__imp_SleepConditionVariableSRW
0x18003e89a  jmp     short loc_18003E872
0x18003e89c  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18003e89f  jz      short loc_18003E87F
0x18003e8a1  mov     rax, gs:58h
0x18003e8aa  mov     ecx, cs:_tls_index
0x18003e8b0  mov     r8d, 4
0x18003e8b6  mov     rdx, [rax+rcx*8]
0x18003e8ba  mov     eax, cs:_Init_global_epoch
0x18003e8c0  mov     [r8+rdx], eax
0x18003e8c4  lea     rcx, SRWLock
0x18003e8cb  add     rsp, 20h
0x18003e8cf  pop     rbx
0x18003e8d0  jmp     cs:__imp_ReleaseSRWLockExclusive
```
