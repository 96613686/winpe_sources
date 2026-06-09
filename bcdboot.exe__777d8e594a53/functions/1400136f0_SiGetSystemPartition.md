# SiGetSystemPartition

- ea: `0x1400136f0`
- end: `0x140013731`
- name: `SiGetSystemPartition`
- size: `65`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140013484`
- `0x1400136f0`
- `0x14001cb14`

## pseudocode

```c
__int64 __fastcall SiGetSystemPartition(unsigned int a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rdx
  __int64 v6; // r8

  result = SiGetBootDeviceName(a1, 2, 0, 0, 0, a2);
  if ( (int)result < 0 )
    return SiGetFirmwareSystemDevice(a1, v5, v6, a2);
  return result;
}

```

## disassembly

```asm
0x1400136f0  mov     [rsp+arg_0], rbx
0x1400136f5  push    rdi
0x1400136f6  sub     rsp, 30h
0x1400136fa  mov     [rsp+38h+var_10], rdx
0x1400136ff  xor     r9d, r9d
0x140013702  mov     rbx, rdx
0x140013705  mov     [rsp+38h+var_18], 0
0x14001370a  xor     r8d, r8d
0x14001370d  mov     edi, ecx
0x14001370f  lea     edx, [r9+2]
0x140013713  call    SiGetBootDeviceName
0x140013718  test    eax, eax
0x14001371a  jns     short loc_140013726
0x14001371c  mov     r9, rbx
0x14001371f  mov     ecx, edi
0x140013721  call    SiGetFirmwareSystemDevice
0x140013726  mov     rbx, [rsp+38h+arg_0]
0x14001372b  add     rsp, 30h
0x14001372f  pop     rdi
0x140013730  retn
```
