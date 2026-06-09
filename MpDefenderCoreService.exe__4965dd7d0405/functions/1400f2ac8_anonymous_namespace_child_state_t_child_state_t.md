# _anonymous_namespace_::child_state_t::_child_state_t

- ea: `0x1400f2ac8`
- end: `0x1400f2b2b`
- name: `_anonymous_namespace_::child_state_t::_child_state_t`
- size: `99`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400f2894`
- `0x1400f2a14`
- `0x1400f2a9c`
- `0x1400f2e40`
- `0x1400f3370`
- `0x1400f34b0`

## callees

- `0x1400f2ac8`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x1400f2ae6`
- `KERNEL32!SetThreadpoolWait` at `0x1400f2ae6`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1400f2af4`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1400f2af4`
- `KERNEL32!CloseThreadpoolWait` at `0x1400f2afd`
- `KERNEL32!CloseThreadpoolWait` at `0x1400f2afd`
- `KERNEL32!CloseHandle` at `0x1400f2b0c`
- `KERNEL32!CloseHandle` at `0x1400f2b1a`
- `KERNEL32!CloseHandle` at `0x1400f2b0c`
- `KERNEL32!CloseHandle` at `0x1400f2b1a`

## pseudocode

```c
void __fastcall anonymous_namespace_::child_state_t::_child_state_t(__int64 a1)
{
  struct _TP_WAIT *v1; // rdi
  void *v3; // rcx

  v1 = *(struct _TP_WAIT **)(a1 + 16);
  if ( v1 )
  {
    SetThreadpoolWait(*(PTP_WAIT *)(a1 + 16), 0, 0);
    WaitForThreadpoolWaitCallbacks(v1, 1);
    CloseThreadpoolWait(v1);
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    CloseHandle(v3);
  if ( *(_QWORD *)a1 )
    CloseHandle(*(HANDLE *)a1);
}

```

## disassembly

```asm
0x1400f2ac8  mov     [rsp+arg_0], rbx
0x1400f2acd  push    rdi
0x1400f2ace  sub     rsp, 20h
0x1400f2ad2  mov     rdi, [rcx+10h]
0x1400f2ad6  mov     rbx, rcx
0x1400f2ad9  test    rdi, rdi
0x1400f2adc  jz      short loc_1400F2B03
0x1400f2ade  xor     r8d, r8d; pftTimeout
0x1400f2ae1  xor     edx, edx; h
0x1400f2ae3  mov     rcx, rdi; pwa
0x1400f2ae6  call    cs:__imp_SetThreadpoolWait
0x1400f2aec  mov     edx, 1; fCancelPendingCallbacks
0x1400f2af1  mov     rcx, rdi; pwa
0x1400f2af4  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1400f2afa  mov     rcx, rdi; pwa
0x1400f2afd  call    cs:__imp_CloseThreadpoolWait
0x1400f2b03  mov     rcx, [rbx+8]; hObject
0x1400f2b07  test    rcx, rcx
0x1400f2b0a  jz      short loc_1400F2B12
0x1400f2b0c  call    cs:__imp_CloseHandle
0x1400f2b12  mov     rcx, [rbx]; hObject
0x1400f2b15  test    rcx, rcx
0x1400f2b18  jz      short loc_1400F2B20
0x1400f2b1a  call    cs:__imp_CloseHandle
0x1400f2b20  mov     rbx, [rsp+28h+arg_0]
0x1400f2b25  add     rsp, 20h
0x1400f2b29  pop     rdi
0x1400f2b2a  retn
```
