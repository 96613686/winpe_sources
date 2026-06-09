# _NetSetup2::NetworkInterface::get_ConfigurationPath_::_1_::dtor$0

- ea: `0x1800141f2`
- end: `0x180014218`
- name: `_NetSetup2::NetworkInterface::get_ConfigurationPath_::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x18000d79c`
- `0x1800141f2`

## pseudocode

```c
void __fastcall NetSetup2::NetworkInterface::get_ConfigurationPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    NetSetup2::Aggregate::ConfigurationPath_Value::~ConfigurationPath_Value(
      *(NetSetup2::Aggregate::ConfigurationPath_Value **)(a2 + 120),
      a2);
  }
}

```

## disassembly

```asm
0x1800141f2  push    rbp
0x1800141f4  sub     rsp, 20h
0x1800141f8  mov     rbp, rdx
0x1800141fb  mov     eax, [rbp+20h]
0x1800141fe  and     eax, 1
0x180014201  test    eax, eax
0x180014203  jz      short loc_180014212
0x180014205  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x180014209  mov     rcx, [rbp+78h]; this
0x18001420d  call    ??1ConfigurationPath_Value@Aggregate@NetSetup2@@QEAA@XZ; NetSetup2::Aggregate::ConfigurationPath_Value::~ConfigurationPath_Value(void)
0x180014212  add     rsp, 20h
0x180014216  pop     rbp
0x180014217  retn
```
