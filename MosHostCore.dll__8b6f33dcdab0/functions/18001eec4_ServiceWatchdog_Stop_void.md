# ServiceWatchdog::Stop(void)

- ea: `0x18001eec4`
- end: `0x18001ef0e`
- name: `?Stop@ServiceWatchdog@@QEAAXXZ`
- size: `74`
- prototype: `void __fastcall(ServiceWatchdog *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001405c`
- `0x1800142c4`
- `0x180014744`
- `0x180016d3c`
- `0x18001cc50`
- `0x18001d224`
- `0x18001d870`

## callees

- `0x180022884`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001eecd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001eecd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ef07`

## pseudocode

```c
void __fastcall ServiceWatchdog::Stop(struct _RTL_CRITICAL_SECTION *this)
{
  EnterCriticalSection(this);
  TimerQueue::Uninitialize((TimerQueue *)&this[1]);
  LODWORD(this[3].SpinCount) = 0;
  this[3].OwningThread = 0;
  this[3].LockSemaphore = 0;
  this[4].DebugInfo = 0;
  BYTE4(this[3].SpinCount) = 0;
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x18001eec4  push    rbx
0x18001eec6  sub     rsp, 20h
0x18001eeca  mov     rbx, rcx
0x18001eecd  call    cs:__imp_EnterCriticalSection
0x18001eed3  lea     rcx, [rbx+28h]; this
0x18001eed7  call    ?Uninitialize@TimerQueue@@QEAAXXZ; TimerQueue::Uninitialize(void)
0x18001eedc  xor     eax, eax
0x18001eede  mov     rcx, rbx
0x18001eee1  mov     [rbx+98h], eax
0x18001eee7  mov     [rbx+88h], rax
0x18001eeee  mov     [rbx+90h], rax
0x18001eef5  mov     [rbx+0A0h], rax
0x18001eefc  mov     [rbx+9Ch], al
0x18001ef02  add     rsp, 20h
0x18001ef06  pop     rbx
0x18001ef07  jmp     cs:__imp_LeaveCriticalSection
```
