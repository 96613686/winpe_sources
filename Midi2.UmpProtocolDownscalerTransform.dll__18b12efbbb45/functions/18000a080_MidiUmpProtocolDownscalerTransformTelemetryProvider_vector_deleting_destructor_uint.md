# MidiUmpProtocolDownscalerTransformTelemetryProvider::`vector deleting destructor'(uint)

- ea: `0x18000a080`
- end: `0x18000a0d5`
- name: `??_EMidiUmpProtocolDownscalerTransformTelemetryProvider@@UEAAPEAXI@Z`
- size: `85`
- prototype: `void *__fastcall(MidiUmpProtocolDownscalerTransformTelemetryProvider *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002e94`
- `0x18000a080`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000a0ae`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000a0ae`

## pseudocode

```c
MidiUmpProtocolDownscalerTransformTelemetryProvider *__fastcall MidiUmpProtocolDownscalerTransformTelemetryProvider::`vector deleting destructor'(
        MidiUmpProtocolDownscalerTransformTelemetryProvider *this,
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
0x18000a080  mov     [rsp+arg_0], rbx
0x18000a085  push    rdi
0x18000a086  sub     rsp, 20h
0x18000a08a  mov     edi, edx
0x18000a08c  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x18000a093  xor     edx, edx
0x18000a095  mov     [rcx], rax
0x18000a098  mov     rbx, rcx
0x18000a09b  cmp     [rcx+10h], dl
0x18000a09e  jz      short loc_18000A0B4
0x18000a0a0  mov     rax, [rcx+8]
0x18000a0a4  mov     rcx, [rax+20h]; RegHandle
0x18000a0a8  mov     [rax], edx
0x18000a0aa  mov     [rax+20h], rdx
0x18000a0ae  call    cs:__imp_EventUnregister
0x18000a0b4  test    dil, 1
0x18000a0b8  jz      short loc_18000A0C7
0x18000a0ba  mov     edx, 20h ; ' '
0x18000a0bf  mov     rcx, rbx; Block
0x18000a0c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a0c7  mov     rax, rbx
0x18000a0ca  mov     rbx, [rsp+28h+arg_0]
0x18000a0cf  add     rsp, 20h
0x18000a0d3  pop     rdi
0x18000a0d4  retn
```
