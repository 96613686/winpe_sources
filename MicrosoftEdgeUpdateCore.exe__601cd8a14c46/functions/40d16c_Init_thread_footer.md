# __Init_thread_footer

- ea: `0x40d16c`
- end: `0x40d1b6`
- name: `__Init_thread_footer`
- size: `74`
- prototype: `int __cdecl(_DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x4015fb`
- `0x4046bf`

## callees

- `0x402330`
- `0x40d16c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x40d176`
- `KERNEL32!EnterCriticalSection` at `0x40d176`
- `KERNEL32!LeaveCriticalSection` at `0x40d1a9`
- `KERNEL32!LeaveCriticalSection` at `0x40d1a9`
- `KERNEL32!SetEvent` at `0x40d22a`
- `KERNEL32!SetEvent` at `0x40d22a`
- `KERNEL32!ResetEvent` at `0x40d236`
- `KERNEL32!ResetEvent` at `0x40d236`

## pseudocode

```c
int __cdecl _Init_thread_footer(_DWORD *a1)
{
  int v2; // [esp+0h] [ebp-4h]
  int savedregs; // [esp+4h] [ebp+0h]

  EnterCriticalSection(&stru_43DCA4);
  *a1 = ++dword_43D000;
  *(_DWORD *)(*((_DWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + TlsIndex) + 4) = dword_43D000;
  LeaveCriticalSection(&stru_43DCA4);
  savedregs = v2;
  if ( dword_43DCC0 )
    return ((int (__thiscall *)(int (__thiscall *)(_DWORD, _DWORD, _DWORD), int *))dword_43DCC0)(
             dword_43DCC0,
             &dword_43DC9C);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x40d16c  push    ebp
0x40d16d  mov     ebp, esp
0x40d16f  push    esi
0x40d170  mov     esi, offset stru_43DCA4
0x40d175  push    esi; lpCriticalSection
0x40d176  call    ds:EnterCriticalSection
0x40d17c  mov     ecx, dword_43D000
0x40d182  mov     eax, [ebp+arg_0]
0x40d185  inc     ecx
0x40d186  mov     dword_43D000, ecx
0x40d18c  push    esi; lpCriticalSection
0x40d18d  mov     [eax], ecx
0x40d18f  mov     eax, large fs:2Ch
0x40d195  mov     ecx, TlsIndex
0x40d19b  mov     ecx, [eax+ecx*4]
0x40d19e  mov     eax, dword_43D000
0x40d1a3  mov     [ecx+4], eax
0x40d1a9  call    ds:LeaveCriticalSection
0x40d1af  pop     esi
0x40d1b0  pop     ebp
0x40d1b1  jmp     __Init_thread_notify
0x40d208  push    esi
0x40d209  mov     esi, dword_43DCC0
0x40d20f  test    esi, esi
0x40d211  jz      short loc_40D224
0x40d213  push    offset dword_43DC9C
0x40d218  mov     ecx, esi
0x40d21a  call    ds:___guard_check_icall_fptr
0x40d220  call    esi ; dword_43DCC0
0x40d222  pop     esi
0x40d223  retn
0x40d224  push    hHandle; hEvent
0x40d22a  call    ds:SetEvent
0x40d230  push    hHandle; hEvent
0x40d236  call    ds:ResetEvent
0x40d23c  pop     esi
0x40d23d  retn
```
