# CMidi2UmpProtocolDownscalerMidiTransform::`scalar deleting destructor'(uint)

- ea: `0x18000d900`
- end: `0x18000d934`
- name: `??_GCMidi2UmpProtocolDownscalerMidiTransform@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CMidi2UmpProtocolDownscalerMidiTransform *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002e94`
- `0x18000d36c`
- `0x18000d900`

## pseudocode

```c
CMidi2UmpProtocolDownscalerMidiTransform *__fastcall CMidi2UmpProtocolDownscalerMidiTransform::`scalar deleting destructor'(
        CMidi2UmpProtocolDownscalerMidiTransform *this,
        char a2)
{
  CMidi2UmpProtocolDownscalerMidiTransform::~CMidi2UmpProtocolDownscalerMidiTransform(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000d900  mov     [rsp+arg_0], rbx
0x18000d905  push    rdi
0x18000d906  sub     rsp, 20h
0x18000d90a  mov     ebx, edx
0x18000d90c  mov     rdi, rcx
0x18000d90f  call    ??1CMidi2UmpProtocolDownscalerMidiTransform@@UEAA@XZ; CMidi2UmpProtocolDownscalerMidiTransform::~CMidi2UmpProtocolDownscalerMidiTransform(void)
0x18000d914  test    bl, 1
0x18000d917  jz      short loc_18000D926
0x18000d919  mov     edx, 0D0h
0x18000d91e  mov     rcx, rdi; Block
0x18000d921  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d926  mov     rbx, [rsp+28h+arg_0]
0x18000d92b  mov     rax, rdi
0x18000d92e  add     rsp, 20h
0x18000d932  pop     rdi
0x18000d933  retn
```
