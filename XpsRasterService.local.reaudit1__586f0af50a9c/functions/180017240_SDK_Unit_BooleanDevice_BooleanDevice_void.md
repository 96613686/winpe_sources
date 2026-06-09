# SDK::Unit::BooleanDevice::BooleanDevice(void)

- ea: `0x180017240`
- end: `0x180017286`
- name: `??0BooleanDevice@Unit@SDK@@QEAA@XZ`
- size: `70`
- prototype: `__int64 __fastcall(SDK::Unit::BooleanDevice *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b210`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017277`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017277`

## pseudocode

```c
SDK::Unit::BooleanDevice *__fastcall SDK::Unit::BooleanDevice::BooleanDevice(SDK::Unit::BooleanDevice *this)
{
  *(_QWORD *)this = &SDK::Unit::BooleanDevice::`vftable';
  *((_QWORD *)this + 1) = 0;
  CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, (LPVOID *)this + 1);
  return this;
}

```

## disassembly

```asm
0x180017240  push    rbx
0x180017242  sub     rsp, 30h
0x180017246  xor     edx, edx; pUnkOuter
0x180017248  lea     rax, ??_7BooleanDevice@Unit@SDK@@6B@
0x18001724f  mov     [rcx], rax
0x180017252  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180017259  lea     rax, [rcx+8]
0x18001725d  mov     rbx, rcx
0x180017260  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180017267  mov     qword ptr [rax], 0
0x18001726e  lea     r8d, [rdx+1]; dwClsContext
0x180017272  mov     [rsp+38h+ppv], rax; ppv
0x180017277  call    cs:__imp_CoCreateInstance
0x18001727d  mov     rax, rbx
0x180017280  add     rsp, 30h
0x180017284  pop     rbx
0x180017285  retn
```
