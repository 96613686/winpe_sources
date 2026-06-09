# ServiceHostTelemetry::`scalar deleting destructor'(uint)

- ea: `0x1800088d0`
- end: `0x180008925`
- name: `??_GServiceHostTelemetry@@UEAAPEAXI@Z`
- size: `85`
- prototype: `ServiceHostTelemetry *__fastcall(ServiceHostTelemetry *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x180002f90`
- `0x1800088d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800088fe`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800088fe`

## pseudocode

```c
ServiceHostTelemetry *__fastcall ServiceHostTelemetry::`scalar deleting destructor'(
        ServiceHostTelemetry *this,
        char a2)
{
  __int64 v4; // rax
  REGHANDLE v5; // rcx

  *(_QWORD *)this = &ServiceHostTelemetry::`vftable';
  if ( *((_BYTE *)this + 16) )
  {
    v4 = *((_QWORD *)this + 1);
    v5 = *(_QWORD *)(v4 + 32);
    *(_DWORD *)v4 = 0;
    *(_QWORD *)(v4 + 32) = 0;
    EventUnregister(v5);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800088d0  mov     [rsp+arg_0], rbx
0x1800088d5  push    rdi
0x1800088d6  sub     rsp, 20h
0x1800088da  mov     edi, edx
0x1800088dc  lea     rax, ??_7ServiceHostTelemetry@@6B@; const ServiceHostTelemetry::`vftable'
0x1800088e3  xor     edx, edx
0x1800088e5  mov     [rcx], rax
0x1800088e8  mov     rbx, rcx
0x1800088eb  cmp     [rcx+10h], dl
0x1800088ee  jz      short loc_180008904
0x1800088f0  mov     rax, [rcx+8]
0x1800088f4  mov     rcx, [rax+20h]; RegHandle
0x1800088f8  mov     [rax], edx
0x1800088fa  mov     [rax+20h], rdx
0x1800088fe  call    cs:__imp_EventUnregister
0x180008904  test    dil, 1
0x180008908  jz      short loc_180008917
0x18000890a  mov     edx, 18h; unsigned __int64
0x18000890f  mov     rcx, rbx; void *
0x180008912  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008917  mov     rax, rbx
0x18000891a  mov     rbx, [rsp+28h+arg_0]
0x18000891f  add     rsp, 20h
0x180008923  pop     rdi
0x180008924  retn
```
