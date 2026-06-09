# __Init_thread_wait

- ea: `0x40d23e`
- end: `0x40d28c`
- name: `__Init_thread_wait`
- size: `78`
- prototype: `void __cdecl(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x40d1b6`

## callees

- `0x402330`
- `0x40d23e`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x40d283`
- `KERNEL32!EnterCriticalSection` at `0x40d283`
- `KERNEL32!LeaveCriticalSection` at `0x40d26b`
- `KERNEL32!LeaveCriticalSection` at `0x40d26b`
- `KERNEL32!WaitForSingleObjectEx` at `0x40d27c`
- `KERNEL32!WaitForSingleObjectEx` at `0x40d27c`

## pseudocode

```c
void __cdecl _Init_thread_wait(DWORD dwMilliseconds)
{
  if ( dword_43DCBC )
  {
    dword_43DCBC(dword_43DCBC, &dword_43DC9C, &stru_43DCA4, dwMilliseconds);
  }
  else
  {
    LeaveCriticalSection(&stru_43DCA4);
    WaitForSingleObjectEx(hHandle, dwMilliseconds, 0);
    EnterCriticalSection(&stru_43DCA4);
  }
}

```

## disassembly

```asm
0x40d23e  push    ebp
0x40d23f  mov     ebp, esp
0x40d241  push    esi
0x40d242  mov     esi, dword_43DCBC
0x40d248  test    esi, esi
0x40d24a  jz      short loc_40D265
0x40d24c  push    [ebp+dwMilliseconds]
0x40d24f  mov     ecx, esi
0x40d251  push    offset stru_43DCA4
0x40d256  push    offset dword_43DC9C
0x40d25b  call    ds:___guard_check_icall_fptr
0x40d261  call    esi ; dword_43DCBC
0x40d263  jmp     short loc_40D289
0x40d265  mov     esi, offset stru_43DCA4
0x40d26a  push    esi; lpCriticalSection
0x40d26b  call    ds:LeaveCriticalSection
0x40d271  push    0; bAlertable
0x40d273  push    [ebp+dwMilliseconds]; dwMilliseconds
0x40d276  push    hHandle; hHandle
0x40d27c  call    ds:WaitForSingleObjectEx
0x40d282  push    esi; lpCriticalSection
0x40d283  call    ds:EnterCriticalSection
0x40d289  pop     esi
0x40d28a  pop     ebp
0x40d28b  retn
```
