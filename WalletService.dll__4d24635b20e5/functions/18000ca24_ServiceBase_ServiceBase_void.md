# ServiceBase::~ServiceBase(void)

- ea: `0x18000ca24`
- end: `0x18000ca5e`
- name: `??1ServiceBase@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ServiceBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005994`
- `0x18000ca70`

## callees

- `0x18000cd2c`
- `0x18000d3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ca4a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ca4a`

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
0x18000ca24  push    rbx
0x18000ca26  sub     rsp, 20h
0x18000ca2a  lea     rax, ??_7ServiceBase@@6B@; const ServiceBase::`vftable'
0x18000ca31  mov     rbx, rcx
0x18000ca34  mov     [rcx], rax
0x18000ca37  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context
0x18000ca3e  call    McGenEventUnregister_EventUnregister
0x18000ca43  lea     rcx, [rbx+88h]; lpCriticalSection
0x18000ca4a  call    cs:__imp_DeleteCriticalSection
0x18000ca50  lea     rcx, [rbx+50h]
0x18000ca54  add     rsp, 20h
0x18000ca58  pop     rbx
0x18000ca59  jmp     ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
```
