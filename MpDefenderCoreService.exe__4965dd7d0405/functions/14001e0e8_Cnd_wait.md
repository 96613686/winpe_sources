# _Cnd_wait

- ea: `0x14001e0e8`
- end: `0x14001e12e`
- name: `_Cnd_wait`
- size: `70`
- prototype: `int __cdecl(_Cnd_t, _Mtx_t)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x14001dda0`
- `0x14008b920`
- `0x14008bc70`
- `0x14008c940`
- `0x14008ca40`
- `0x140096ee0`
- `0x140101bd0`
- `0x140101fd0`
- `0x140116370`
- `0x14011e990`
- `0x14012b49c`
- `0x140137138`

## callees

- `0x14001e0e8`
- `0x14004f9a8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14001e114`
- `KERNEL32!GetCurrentThreadId` at `0x14001e114`
- `KERNEL32!SleepConditionVariableSRW` at `0x14001e10a`
- `KERNEL32!SleepConditionVariableSRW` at `0x14001e10a`

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
0x14001e0e8  push    rbx
0x14001e0ea  sub     rsp, 20h
0x14001e0ee  dec     dword ptr [rdx+4Ch]
0x14001e0f1  mov     rbx, rdx
0x14001e0f4  mov     dword ptr [rdx+48h], 0FFFFFFFFh
0x14001e0fb  add     rcx, 8; ConditionVariable
0x14001e0ff  add     rdx, 10h; SRWLock
0x14001e103  xor     r9d, r9d; Flags
0x14001e106  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x14001e10a  call    cs:__imp_SleepConditionVariableSRW
0x14001e110  test    eax, eax
0x14001e112  jz      short loc_14001E128
0x14001e114  call    cs:__imp_GetCurrentThreadId
0x14001e11a  inc     dword ptr [rbx+4Ch]
0x14001e11d  mov     [rbx+48h], eax
0x14001e120  xor     eax, eax
0x14001e122  add     rsp, 20h
0x14001e126  pop     rbx
0x14001e127  retn
0x14001e128  call    abort
```
