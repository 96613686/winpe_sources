# wmi::AutoRef<ChannelConfigObject>::~AutoRef<ChannelConfigObject>(void)

- ea: `0x1800063e0`
- end: `0x180006403`
- name: `??1?$AutoRef@VChannelConfigObject@@@wmi@@QEAA@XZ`
- size: `35`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180039250`
- `0x180039270`
- `0x1800398e7`
- `0x1800398f9`
- `0x180039939`
- `0x180039a35`
- `0x180039afe`
- `0x180039b41`
- `0x18003a5b9`

## callees

- `0x1800063e0`
- `0x180006870`

## pseudocode

```c
unsigned int __fastcall wmi::AutoRef<ChannelConfigObject>::~AutoRef<ChannelConfigObject>(wmi::RefBase **a1)
{
  wmi::RefBase *v2; // rcx
  unsigned int result; // eax

  v2 = *a1;
  if ( v2 )
    result = wmi::RefBase::Release(v2);
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800063e0  push    rbx
0x1800063e2  sub     rsp, 20h
0x1800063e6  mov     rbx, rcx
0x1800063e9  mov     rcx, [rcx]; this
0x1800063ec  test    rcx, rcx
0x1800063ef  jz      short loc_1800063F6
0x1800063f1  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x1800063f6  mov     qword ptr [rbx], 0
0x1800063fd  add     rsp, 20h
0x180006401  pop     rbx
0x180006402  retn
```
