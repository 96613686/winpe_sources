# WinSAT::TimeGate::~TimeGate(void)

- ea: `0x140060614`
- end: `0x140060642`
- name: `??1TimeGate@WinSAT@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(WinSAT::TimeGate *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140061b44`
- `0x140116745`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x14006062b`
- `KERNEL32!GetCurrentThread` at `0x14006062b`
- `KERNEL32!SetThreadPriority` at `0x14006063b`
- `WINMM!timeEndPeriod` at `0x140060622`
- `WINMM!timeEndPeriod` at `0x140060622`

## pseudocode

```c
void __fastcall WinSAT::TimeGate::~TimeGate(WinSAT::TimeGate *this)
{
  HANDLE CurrentThread; // rax

  timeEndPeriod(1u);
  LODWORD(this) = *((_DWORD *)this + 4);
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, (int)this);
}

```

## disassembly

```asm
0x140060614  push    rbx
0x140060616  sub     rsp, 20h
0x14006061a  mov     rbx, rcx
0x14006061d  mov     ecx, 1; uPeriod
0x140060622  call    cs:__imp_timeEndPeriod
0x140060628  mov     ebx, [rbx+10h]
0x14006062b  call    cs:__imp_GetCurrentThread
0x140060631  mov     rcx, rax
0x140060634  mov     edx, ebx
0x140060636  add     rsp, 20h
0x14006063a  pop     rbx
0x14006063b  jmp     cs:__imp_SetThreadPriority
```
