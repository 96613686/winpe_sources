# uus::UndockedStubDllTelemetry::`scalar deleting destructor'(uint)

- ea: `0x1800099f0`
- end: `0x180009a45`
- name: `??_GUndockedStubDllTelemetry@uus@@UEAAPEAXI@Z`
- size: `85`
- prototype: `uus::UndockedStubDllTelemetry *__fastcall(uus::UndockedStubDllTelemetry *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x1800025d0`
- `0x1800099f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180009a1e`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180009a1e`

## pseudocode

```c
uus::UndockedStubDllTelemetry *__fastcall uus::UndockedStubDllTelemetry::`scalar deleting destructor'(
        uus::UndockedStubDllTelemetry *this,
        char a2)
{
  __int64 v4; // rax
  REGHANDLE v5; // rcx

  *(_QWORD *)this = &wil::TraceLoggingProvider::`vftable';
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
0x1800099f0  mov     [rsp+arg_0], rbx
0x1800099f5  push    rdi
0x1800099f6  sub     rsp, 20h
0x1800099fa  mov     edi, edx
0x1800099fc  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180009a03  xor     edx, edx
0x180009a05  mov     [rcx], rax
0x180009a08  mov     rbx, rcx
0x180009a0b  cmp     [rcx+10h], dl
0x180009a0e  jz      short loc_180009A24
0x180009a10  mov     rax, [rcx+8]
0x180009a14  mov     rcx, [rax+20h]; RegHandle
0x180009a18  mov     [rax], edx
0x180009a1a  mov     [rax+20h], rdx
0x180009a1e  call    cs:__imp_EventUnregister
0x180009a24  test    dil, 1
0x180009a28  jz      short loc_180009A37
0x180009a2a  mov     edx, 20h ; ' '; unsigned __int64
0x180009a2f  mov     rcx, rbx; void *
0x180009a32  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009a37  mov     rax, rbx
0x180009a3a  mov     rbx, [rsp+28h+arg_0]
0x180009a3f  add     rsp, 20h
0x180009a43  pop     rdi
0x180009a44  retn
```
