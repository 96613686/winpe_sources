# TraceSession::~TraceSession(void)

- ea: `0x180026e58`
- end: `0x180026e7c`
- name: `??1TraceSession@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(TraceSession *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180031860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026e65`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026e65`

## pseudocode

```c
void __fastcall TraceSession::~TraceSession(TraceSession *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_QWORD *)this + 1) = &IRegistryFunctions::`vftable';
}

```

## disassembly

```asm
0x180026e58  push    rbx
0x180026e5a  sub     rsp, 20h
0x180026e5e  mov     rbx, rcx
0x180026e61  add     rcx, 18h; lpCriticalSection
0x180026e65  call    cs:__imp_DeleteCriticalSection
0x180026e6b  lea     rax, ??_7IRegistryFunctions@@6B@; const IRegistryFunctions::`vftable'
0x180026e72  mov     [rbx+8], rax
0x180026e76  add     rsp, 20h
0x180026e7a  pop     rbx
0x180026e7b  retn
```
