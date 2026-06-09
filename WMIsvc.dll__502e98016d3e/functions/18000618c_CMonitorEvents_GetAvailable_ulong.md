# CMonitorEvents::GetAvailable(ulong)

- ea: `0x18000618c`
- end: `0x1800061f6`
- name: `?GetAvailable@CMonitorEvents@@QEAAPEAVResyncPerfTask@@K@Z`
- size: `106`
- prototype: `struct ResyncPerfTask *__fastcall(CMonitorEvents *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004900`
- `0x180005fdc`

## callees

- `0x180004fd0`
- `0x18000618c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct ResyncPerfTask *__fastcall CMonitorEvents::GetAvailable(CMonitorEvents *this, unsigned int a2)
{
  char *v4; // rdi
  unsigned __int64 v5; // rax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 24));
  v5 = (unsigned __int64)a2 << 6;
  if ( *(_DWORD *)((char *)this + v5 + 300) )
  {
    *(_DWORD *)((char *)this + v5 + 300) = 0;
    *(_DWORD *)((char *)this + v5 + 304) = a2;
    v4 = (char *)this + v5 + 296;
  }
  LeaveCriticalSection(lpCriticalSection);
  return (struct ResyncPerfTask *)v4;
}

```

## disassembly

```asm
0x18000618c  mov     [rsp+arg_8], rbx
0x180006191  mov     [rsp+arg_10], rsi
0x180006196  push    rdi
0x180006197  sub     rsp, 20h
0x18000619b  mov     esi, edx
0x18000619d  mov     rbx, rcx
0x1800061a0  xor     edi, edi
0x1800061a2  lea     rdx, [rcx+18h]; struct _RTL_CRITICAL_SECTION *
0x1800061a6  lea     rcx, [rsp+28h+lpCriticalSection]; this
0x1800061ab  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x1800061b0  nop
0x1800061b1  mov     eax, esi
0x1800061b3  shl     rax, 6
0x1800061b7  cmp     [rax+rbx+12Ch], edi
0x1800061be  jz      short loc_1800061D8
0x1800061c0  mov     [rax+rbx+12Ch], edi
0x1800061c7  mov     [rax+rbx+130h], esi
0x1800061ce  lea     rdi, [rbx+128h]
0x1800061d5  add     rdi, rax
0x1800061d8  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x1800061dd  call    cs:__imp_LeaveCriticalSection
0x1800061e3  mov     rax, rdi
0x1800061e6  mov     rbx, [rsp+28h+arg_8]
0x1800061eb  mov     rsi, [rsp+28h+arg_10]
0x1800061f0  add     rsp, 20h
0x1800061f4  pop     rdi
0x1800061f5  retn
```
