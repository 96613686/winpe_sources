# CPimcContext::PostUpdate(ulong)

- ea: `0x180006f08`
- end: `0x180006f5a`
- name: `?PostUpdate@CPimcContext@@QEAAJK@Z`
- size: `82`
- prototype: `__int64 __fastcall(CPimcContext *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x18000b6b8`
- `0x18000b8bc`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006f26`
- `KERNEL32!EnterCriticalSection` at `0x180006f26`
- `KERNEL32!LeaveCriticalSection` at `0x180006f35`
- `KERNEL32!LeaveCriticalSection` at `0x180006f35`
- `KERNEL32!SetEvent` at `0x180006f42`
- `KERNEL32!SetEvent` at `0x180006f42`

## pseudocode

```c
__int64 __fastcall CPimcContext::PostUpdate(struct _RTL_CRITICAL_SECTION *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx

  v2 = this + 5;
  EnterCriticalSection(this + 5);
  LODWORD(this[4].SpinCount) |= a2;
  LeaveCriticalSection(v2);
  SetEvent(this[4].LockSemaphore);
  return 0;
}

```

## disassembly

```asm
0x180006f08  mov     [rsp+arg_0], rbx
0x180006f0d  mov     [rsp+arg_8], rsi
0x180006f12  push    rdi
0x180006f13  sub     rsp, 20h
0x180006f17  lea     rbx, [rcx+0C8h]
0x180006f1e  mov     rsi, rcx
0x180006f21  mov     rcx, rbx; lpCriticalSection
0x180006f24  mov     edi, edx
0x180006f26  call    cs:__imp_EnterCriticalSection
0x180006f2c  or      [rsi+0C0h], edi
0x180006f32  mov     rcx, rbx; lpCriticalSection
0x180006f35  call    cs:__imp_LeaveCriticalSection
0x180006f3b  mov     rcx, [rsi+0B8h]; hEvent
0x180006f42  call    cs:__imp_SetEvent
0x180006f48  mov     rbx, [rsp+28h+arg_0]
0x180006f4d  xor     eax, eax
0x180006f4f  mov     rsi, [rsp+28h+arg_8]
0x180006f54  add     rsp, 20h
0x180006f58  pop     rdi
0x180006f59  retn
```
