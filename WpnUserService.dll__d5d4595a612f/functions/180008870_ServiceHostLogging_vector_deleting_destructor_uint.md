# ServiceHostLogging::`vector deleting destructor'(uint)

- ea: `0x180008870`
- end: `0x1800088c5`
- name: `??_EServiceHostLogging@@UEAAPEAXI@Z`
- size: `85`
- prototype: `ServiceHostLogging *__fastcall(ServiceHostLogging *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x180002f90`
- `0x180008870`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000889e`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000889e`

## pseudocode

```c
ServiceHostLogging *__fastcall ServiceHostLogging::`vector deleting destructor'(ServiceHostLogging *this, char a2)
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
0x180008870  mov     [rsp+arg_0], rbx
0x180008875  push    rdi
0x180008876  sub     rsp, 20h
0x18000887a  mov     edi, edx
0x18000887c  lea     rax, ??_7ServiceHostTelemetry@@6B@; const ServiceHostTelemetry::`vftable'
0x180008883  xor     edx, edx
0x180008885  mov     [rcx], rax
0x180008888  mov     rbx, rcx
0x18000888b  cmp     [rcx+10h], dl
0x18000888e  jz      short loc_1800088A4
0x180008890  mov     rax, [rcx+8]
0x180008894  mov     rcx, [rax+20h]; RegHandle
0x180008898  mov     [rax], edx
0x18000889a  mov     [rax+20h], rdx
0x18000889e  call    cs:__imp_EventUnregister
0x1800088a4  test    dil, 1
0x1800088a8  jz      short loc_1800088B7
0x1800088aa  mov     edx, 20h ; ' '; unsigned __int64
0x1800088af  mov     rcx, rbx; void *
0x1800088b2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800088b7  mov     rax, rbx
0x1800088ba  mov     rbx, [rsp+28h+arg_0]
0x1800088bf  add     rsp, 20h
0x1800088c3  pop     rdi
0x1800088c4  retn
```
