# __Init_thread_footer

- ea: `0x4195cc`
- end: `0x419616`
- name: `__Init_thread_footer`
- size: `74`
- prototype: `int __cdecl(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x40132b`

## callees

- `0x405810`
- `0x4195cc`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x419609`
- `KERNEL32!LeaveCriticalSection` at `0x419609`
- `KERNEL32!EnterCriticalSection` at `0x4195d6`
- `KERNEL32!EnterCriticalSection` at `0x4195d6`
- `KERNEL32!SetEvent` at `0x41968a`
- `KERNEL32!SetEvent` at `0x41968a`
- `KERNEL32!ResetEvent` at `0x419696`
- `KERNEL32!ResetEvent` at `0x419696`

## pseudocode

```c
int __cdecl _Init_thread_footer(_DWORD *a1)
{
  int v2; // [esp+0h] [ebp-4h]
  int savedregs; // [esp+4h] [ebp+0h]

  EnterCriticalSection(&CriticalSection);
  *a1 = ++dword_426880;
  *(_DWORD *)(*((_DWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + TlsIndex) + 4) = dword_426880;
  LeaveCriticalSection(&CriticalSection);
  savedregs = v2;
  if ( dword_4273A4 )
    return ((int (__thiscall *)(int (__thiscall *)(_DWORD, _DWORD, _DWORD), int *))dword_4273A4)(
             dword_4273A4,
             &dword_427380);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x4195cc  push    ebp
0x4195cd  mov     ebp, esp
0x4195cf  push    esi
0x4195d0  mov     esi, offset CriticalSection
0x4195d5  push    esi; lpCriticalSection
0x4195d6  call    ds:EnterCriticalSection
0x4195dc  mov     ecx, dword_426880
0x4195e2  mov     eax, [ebp+arg_0]
0x4195e5  inc     ecx
0x4195e6  mov     dword_426880, ecx
0x4195ec  push    esi; lpCriticalSection
0x4195ed  mov     [eax], ecx
0x4195ef  mov     eax, large fs:2Ch
0x4195f5  mov     ecx, TlsIndex
0x4195fb  mov     ecx, [eax+ecx*4]
0x4195fe  mov     eax, dword_426880
0x419603  mov     [ecx+4], eax
0x419609  call    ds:LeaveCriticalSection
0x41960f  pop     esi
0x419610  pop     ebp
0x419611  jmp     __Init_thread_notify
0x419668  push    esi
0x419669  mov     esi, dword_4273A4
0x41966f  test    esi, esi
0x419671  jz      short loc_419684
0x419673  push    offset dword_427380
0x419678  mov     ecx, esi
0x41967a  call    ds:___guard_check_icall_fptr
0x419680  call    esi ; dword_4273A4
0x419682  pop     esi
0x419683  retn
0x419684  push    hHandle; hEvent
0x41968a  call    ds:SetEvent
0x419690  push    hHandle; hEvent
0x419696  call    ds:ResetEvent
0x41969c  pop     esi
0x41969d  retn
```
