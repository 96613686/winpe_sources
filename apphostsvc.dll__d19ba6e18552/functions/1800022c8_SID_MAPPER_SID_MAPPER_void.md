# SID_MAPPER::~SID_MAPPER(void)

- ea: `0x1800022c8`
- end: `0x180002308`
- name: `??1SID_MAPPER@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(SID_MAPPER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180002780`
- `0x180005448`

## callees

- `0x180007848`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800022f4`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800022f4`

## pseudocode

```c
void __fastcall SID_MAPPER::~SID_MAPPER(SID_MAPPER *this)
{
  *((_DWORD *)this + 4) = 1482975603;
  *(_QWORD *)this = &SID_MAPPER::`vftable'{for `INativeChangeListener'};
  *((_QWORD *)this + 1) = &SID_MAPPER::`vftable'{for `MULTI_WORK_DISPATCH'};
  CReaderWriterLock3::~CReaderWriterLock3((SID_MAPPER *)((char *)this + 184));
  APP_POOL_HASH_MAPPER::~APP_POOL_HASH_MAPPER((SID_MAPPER *)((char *)this + 32));
}

```

## disassembly

```asm
0x1800022c8  push    rbx
0x1800022ca  sub     rsp, 20h
0x1800022ce  lea     rax, ??_7SID_MAPPER@@6BINativeChangeListener@@@; const SID_MAPPER::`vftable'{for `INativeChangeListener'}
0x1800022d5  mov     dword ptr [rcx+10h], 58646973h
0x1800022dc  mov     [rcx], rax
0x1800022df  mov     rbx, rcx
0x1800022e2  lea     rax, ??_7SID_MAPPER@@6BMULTI_WORK_DISPATCH@@@; const SID_MAPPER::`vftable'{for `MULTI_WORK_DISPATCH'}
0x1800022e9  mov     [rcx+8], rax
0x1800022ed  add     rcx, 0B8h
0x1800022f4  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x1800022fa  lea     rcx, [rbx+20h]; this
0x1800022fe  add     rsp, 20h
0x180002302  pop     rbx
0x180002303  jmp     ??1APP_POOL_HASH_MAPPER@@QEAA@XZ; APP_POOL_HASH_MAPPER::~APP_POOL_HASH_MAPPER(void)
```
