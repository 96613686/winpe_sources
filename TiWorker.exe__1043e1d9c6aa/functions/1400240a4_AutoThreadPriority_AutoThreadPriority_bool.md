# AutoThreadPriority::AutoThreadPriority(bool)

- ea: `0x1400240a4`
- end: `0x1400240e9`
- name: `??0AutoThreadPriority@@QEAA@_N@Z`
- size: `69`
- prototype: `AutoThreadPriority *__fastcall(AutoThreadPriority *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e550`
- `0x14001344c`

## callees

- `0x14002472c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1400240ad`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1400240ad`

## pseudocode

```c
AutoThreadPriority *__fastcall AutoThreadPriority::AutoThreadPriority(AutoThreadPriority *this)
{
  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_BYTE *)this + 68) = 0;
  *((_DWORD *)this + 15) = 2;
  *((_DWORD *)this + 16) = 5;
  *(_DWORD *)((char *)this + 69) = 0;
  *((_BYTE *)this + 73) = 0;
  AutoThreadPriority::Initialize(this);
  return this;
}

```

## disassembly

```asm
0x1400240a4  push    rbx
0x1400240a6  sub     rsp, 20h
0x1400240aa  mov     rbx, rcx
0x1400240ad  call    cs:__imp_InitializeCriticalSection
0x1400240b3  xor     ecx, ecx
0x1400240b5  xor     eax, eax
0x1400240b7  mov     [rbx+28h], ecx
0x1400240ba  mov     [rbx+30h], rcx
0x1400240be  mov     [rbx+38h], ecx
0x1400240c1  mov     [rbx+44h], cl
0x1400240c4  mov     dword ptr [rbx+3Ch], 2
0x1400240cb  mov     dword ptr [rbx+40h], 5
0x1400240d2  mov     [rbx+45h], eax
0x1400240d5  mov     [rbx+49h], cl
0x1400240d8  mov     rcx, rbx; this
0x1400240db  call    ?Initialize@AutoThreadPriority@@AEAAXXZ; AutoThreadPriority::Initialize(void)
0x1400240e0  mov     rax, rbx
0x1400240e3  add     rsp, 20h
0x1400240e7  pop     rbx
0x1400240e8  retn
```
