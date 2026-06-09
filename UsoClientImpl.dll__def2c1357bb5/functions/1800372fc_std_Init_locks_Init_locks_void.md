# std::_Init_locks::~_Init_locks(void)

- ea: `0x1800372fc`
- end: `0x180037338`
- name: `??1_Init_locks@std@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(std::_Init_locks *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180062ca0`
- `0x180062ce0`
- `0x180062d20`
- `0x180062fa0`
- `0x180063030`

## callees

- `0x1800372fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003731c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003731c`

## pseudocode

```c
void __fastcall std::_Init_locks::~_Init_locks(std::_Init_locks *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  if ( _InterlockedDecrement(&dword_18009D210) < 0 )
  {
    v1 = &CriticalSection;
    do
      DeleteCriticalSection(v1++);
    while ( v1 != (struct _RTL_CRITICAL_SECTION *)qword_1800A0060 );
  }
}

```

## disassembly

```asm
0x1800372fc  push    rbx
0x1800372fe  sub     rsp, 20h
0x180037302  or      eax, 0FFFFFFFFh
0x180037305  lock xadd cs:dword_18009D210, eax
0x18003730d  cmp     eax, 1
0x180037310  jns     short loc_180037332
0x180037312  lea     rbx, CriticalSection
0x180037319  mov     rcx, rbx; lpCriticalSection
0x18003731c  call    cs:__imp_DeleteCriticalSection
0x180037322  lea     rax, qword_1800A0060
0x180037329  add     rbx, 28h ; '('
0x18003732d  cmp     rbx, rax
0x180037330  jnz     short loc_180037319
0x180037332  add     rsp, 20h
0x180037336  pop     rbx
0x180037337  retn
```
