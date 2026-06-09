# ServiceBase::~ServiceBase(void)

- ea: `0x180020568`
- end: `0x1800205a2`
- name: `??1ServiceBase@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ServiceBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004880`
- `0x1800205b0`

## callees

- `0x180002c2c`
- `0x18000b654`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002058e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002058e`

## pseudocode

```c
void __fastcall ServiceBase::~ServiceBase(ServiceBase *this)
{
  *(_QWORD *)this = &ServiceBase::`vftable';
  McGenEventUnregister_EventUnregister(&MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((char *)this + 80);
}

```

## disassembly

```asm
0x180020568  push    rbx
0x18002056a  sub     rsp, 20h
0x18002056e  lea     rax, ??_7ServiceBase@@6B@; const ServiceBase::`vftable'
0x180020575  mov     rbx, rcx
0x180020578  mov     [rcx], rax
0x18002057b  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context
0x180020582  call    McGenEventUnregister_EventUnregister
0x180020587  lea     rcx, [rbx+88h]; lpCriticalSection
0x18002058e  call    cs:__imp_DeleteCriticalSection
0x180020594  lea     rcx, [rbx+50h]
0x180020598  add     rsp, 20h
0x18002059c  pop     rbx
0x18002059d  jmp     ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
```
