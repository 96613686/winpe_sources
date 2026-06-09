# std::_Ref_count_obj2<DiagHubCommon::EtlLogWriter>::`scalar deleting destructor'(uint)

- ea: `0x14000d7a0`
- end: `0x14000d7cb`
- name: `??_G?$_Ref_count_obj2@VEtlLogWriter@DiagHubCommon@@@std@@UEAAPEAXI@Z`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000d7a0`
- `0x14001382c`

## pseudocode

```c
_QWORD *__fastcall std::_Ref_count_obj2<DiagHubCommon::EtlLogWriter>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &std::_Ref_count_obj2<DiagHubCommon::EtlLogWriter>::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x14000d7a0  push    rbx
0x14000d7a2  sub     rsp, 20h
0x14000d7a6  lea     rax, ??_7?$_Ref_count_obj2@VEtlLogWriter@DiagHubCommon@@@std@@6B@
0x14000d7ad  mov     rbx, rcx
0x14000d7b0  mov     [rcx], rax
0x14000d7b3  test    dl, 1
0x14000d7b6  jz      short loc_14000D7C2
0x14000d7b8  mov     edx, 20h ; ' '
0x14000d7bd  call    ??3@YAXPEAX_K@Z
0x14000d7c2  mov     rax, rbx
0x14000d7c5  add     rsp, 20h
0x14000d7c9  pop     rbx
0x14000d7ca  retn
```
