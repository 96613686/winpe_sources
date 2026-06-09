# ServiceBase::~ServiceBase(void)

- ea: `0x180005d18`
- end: `0x180005d52`
- name: `??1ServiceBase@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ServiceBase *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180002fd0`
- `0x180005d60`
- `0x18000b040`

## callees

- `0x180005d18`
- `0x180006734`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005d37`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005d37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d46`

## pseudocode

```c
void __fastcall ServiceBase::~ServiceBase(ServiceBase *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &ServiceBase::`vftable';
  McGenEventUnregister_EventUnregister();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v2 = (void *)*((_QWORD *)this + 10);
  if ( v2 )
    CloseHandle(v2);
}

```

## disassembly

```asm
0x180005d18  push    rbx
0x180005d1a  sub     rsp, 20h
0x180005d1e  lea     rax, ??_7ServiceBase@@6B@; const ServiceBase::`vftable'
0x180005d25  mov     rbx, rcx
0x180005d28  mov     [rcx], rax
0x180005d2b  call    McGenEventUnregister_EventUnregister
0x180005d30  lea     rcx, [rbx+88h]; lpCriticalSection
0x180005d37  call    cs:__imp_DeleteCriticalSection
0x180005d3d  mov     rcx, [rbx+50h]; hObject
0x180005d41  test    rcx, rcx
0x180005d44  jz      short loc_180005D4C
0x180005d46  call    cs:__imp_CloseHandle
0x180005d4c  add     rsp, 20h
0x180005d50  pop     rbx
0x180005d51  retn
```
