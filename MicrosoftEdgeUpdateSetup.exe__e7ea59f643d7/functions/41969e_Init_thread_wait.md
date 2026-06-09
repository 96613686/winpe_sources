# __Init_thread_wait

- ea: `0x41969e`
- end: `0x4196ec`
- name: `__Init_thread_wait`
- size: `78`
- prototype: `void __cdecl(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x419616`

## callees

- `0x405810`
- `0x41969e`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x4196cb`
- `KERNEL32!LeaveCriticalSection` at `0x4196cb`
- `KERNEL32!EnterCriticalSection` at `0x4196e3`
- `KERNEL32!EnterCriticalSection` at `0x4196e3`
- `KERNEL32!WaitForSingleObjectEx` at `0x4196dc`
- `KERNEL32!WaitForSingleObjectEx` at `0x4196dc`

## pseudocode

```c
void __cdecl _Init_thread_wait(DWORD dwMilliseconds)
{
  if ( dword_4273A0 )
  {
    dword_4273A0(dword_4273A0, &dword_427380, &CriticalSection, dwMilliseconds);
  }
  else
  {
    LeaveCriticalSection(&CriticalSection);
    WaitForSingleObjectEx(hHandle, dwMilliseconds, 0);
    EnterCriticalSection(&CriticalSection);
  }
}

```

## disassembly

```asm
0x41969e  push    ebp
0x41969f  mov     ebp, esp
0x4196a1  push    esi
0x4196a2  mov     esi, dword_4273A0
0x4196a8  test    esi, esi
0x4196aa  jz      short loc_4196C5
0x4196ac  push    [ebp+dwMilliseconds]
0x4196af  mov     ecx, esi
0x4196b1  push    offset CriticalSection
0x4196b6  push    offset dword_427380
0x4196bb  call    ds:___guard_check_icall_fptr
0x4196c1  call    esi ; dword_4273A0
0x4196c3  jmp     short loc_4196E9
0x4196c5  mov     esi, offset CriticalSection
0x4196ca  push    esi; lpCriticalSection
0x4196cb  call    ds:LeaveCriticalSection
0x4196d1  push    0; bAlertable
0x4196d3  push    [ebp+dwMilliseconds]; dwMilliseconds
0x4196d6  push    hHandle; hHandle
0x4196dc  call    ds:WaitForSingleObjectEx
0x4196e2  push    esi; lpCriticalSection
0x4196e3  call    ds:EnterCriticalSection
0x4196e9  pop     esi
0x4196ea  pop     ebp
0x4196eb  retn
```
