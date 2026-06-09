# _Cnd_wait

- ea: `0x1801d2e50`
- end: `0x1801d2e96`
- name: `_Cnd_wait`
- size: `70`
- prototype: `int __cdecl(_Cnd_t, _Mtx_t)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x1800377c0`
- `0x180037900`
- `0x18005e080`
- `0x18005e1d0`
- `0x1800a05f0`
- `0x1800a08c0`
- `0x18017f890`
- `0x180181320`
- `0x180196220`
- `0x180199770`
- `0x180199e40`
- `0x18019beb0`
- `0x180229900`
- `0x180240850`
- `0x180241780`

## callees

- `0x1801d2e50`
- `0x180206a58`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1801d2e7c`
- `KERNEL32!GetCurrentThreadId` at `0x1801d2e7c`
- `KERNEL32!SleepConditionVariableSRW` at `0x1801d2e72`
- `KERNEL32!SleepConditionVariableSRW` at `0x1801d2e72`

## pseudocode

```c
int __cdecl Cnd_wait(_Cnd_t a1, _Mtx_t a2)
{
  DWORD CurrentThreadId; // eax

  --*((_DWORD *)a2 + 19);
  *((_DWORD *)a2 + 18) = -1;
  if ( !SleepConditionVariableSRW((PCONDITION_VARIABLE)a1 + 1, (PSRWLOCK)a2 + 2, 0xFFFFFFFF, 0) )
    abort();
  CurrentThreadId = GetCurrentThreadId();
  ++*((_DWORD *)a2 + 19);
  *((_DWORD *)a2 + 18) = CurrentThreadId;
  return 0;
}

```

## disassembly

```asm
0x1801d2e50  push    rbx
0x1801d2e52  sub     rsp, 20h
0x1801d2e56  dec     dword ptr [rdx+4Ch]
0x1801d2e59  mov     rbx, rdx
0x1801d2e5c  mov     dword ptr [rdx+48h], 0FFFFFFFFh
0x1801d2e63  add     rcx, 8; ConditionVariable
0x1801d2e67  add     rdx, 10h; SRWLock
0x1801d2e6b  xor     r9d, r9d; Flags
0x1801d2e6e  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1801d2e72  call    cs:__imp_SleepConditionVariableSRW
0x1801d2e78  test    eax, eax
0x1801d2e7a  jz      short loc_1801D2E90
0x1801d2e7c  call    cs:__imp_GetCurrentThreadId
0x1801d2e82  inc     dword ptr [rbx+4Ch]
0x1801d2e85  mov     [rbx+48h], eax
0x1801d2e88  xor     eax, eax
0x1801d2e8a  add     rsp, 20h
0x1801d2e8e  pop     rbx
0x1801d2e8f  retn
0x1801d2e90  call    abort
```
