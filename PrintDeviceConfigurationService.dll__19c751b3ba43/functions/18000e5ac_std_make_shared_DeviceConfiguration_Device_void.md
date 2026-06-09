# std::make_shared<DeviceConfiguration::Device,>(void)

- ea: `0x18000e5ac`
- end: `0x18000e621`
- name: `??$make_shared@VDevice@DeviceConfiguration@@$$V@std@@YA?AV?$shared_ptr@VDevice@DeviceConfiguration@@@0@XZ`
- size: `117`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000fbe0`

## callees

- `0x1800024cc`
- `0x180002b28`
- `0x18000e854`

## pseudocode

```c
_QWORD *__fastcall std::make_shared<DeviceConfiguration::Device,>(_QWORD *a1)
{
  _QWORD *result; // rax
  _DWORD *v3; // [rsp+40h] [rbp+8h]

  v3 = operator new(0x120u);
  *(_OWORD *)v3 = 0;
  v3[2] = 1;
  v3[3] = 1;
  *(_QWORD *)v3 = &std::_Ref_count_obj2<DeviceConfiguration::Device>::`vftable';
  memset_0(v3 + 4, 0, 0x110u);
  DeviceConfiguration::Device::Device((DeviceConfiguration::Device *)(v3 + 4));
  *a1 = v3 + 4;
  result = a1;
  a1[1] = v3;
  return result;
}

```

## disassembly

```asm
0x18000e5ac  mov     [rsp+arg_8], rbx
0x18000e5b1  mov     [rsp+arg_10], rsi
0x18000e5b6  push    rdi
0x18000e5b7  sub     rsp, 30h
0x18000e5bb  mov     rsi, rcx
0x18000e5be  mov     ecx, 120h; Size
0x18000e5c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e5c8  mov     rdi, rax
0x18000e5cb  mov     [rsp+38h+arg_0], rax
0x18000e5d0  xorps   xmm0, xmm0
0x18000e5d3  xor     edx, edx; Val
0x18000e5d5  mov     r8d, 110h; Size
0x18000e5db  movups  xmmword ptr [rax], xmm0
0x18000e5de  mov     eax, 1
0x18000e5e3  lea     rbx, [rdi+10h]
0x18000e5e7  mov     [rdi+8], eax
0x18000e5ea  mov     rcx, rbx; void *
0x18000e5ed  mov     [rdi+0Ch], eax
0x18000e5f0  lea     rax, ??_7?$_Ref_count_obj2@VDevice@DeviceConfiguration@@@std@@6B@; const std::_Ref_count_obj2<DeviceConfiguration::Device>::`vftable'
0x18000e5f7  mov     [rdi], rax
0x18000e5fa  call    memset_0
0x18000e5ff  mov     rcx, rbx; this
0x18000e602  call    ??0Device@DeviceConfiguration@@QEAA@XZ; DeviceConfiguration::Device::Device(void)
0x18000e607  mov     [rsi], rbx
0x18000e60a  mov     rax, rsi
0x18000e60d  mov     rbx, [rsp+38h+arg_8]
0x18000e612  mov     [rsi+8], rdi
0x18000e616  mov     rsi, [rsp+38h+arg_10]
0x18000e61b  add     rsp, 30h
0x18000e61f  pop     rdi
0x18000e620  retn
```
