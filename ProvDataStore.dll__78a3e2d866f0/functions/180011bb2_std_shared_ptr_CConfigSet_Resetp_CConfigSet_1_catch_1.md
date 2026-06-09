# _std::shared_ptr_CConfigSet_::_Resetp_CConfigSet__::_1_::catch$1

- ea: `0x180011bb2`
- end: `0x180011bd7`
- name: `_std::shared_ptr_CConfigSet_::_Resetp_CConfigSet__::_1_::catch$1`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000ccdc`
- `0x180010e2c`
- `0x180011bb2`

## pseudocode

```c
void __fastcall __noreturn std::shared_ptr_CConfigSet_::_Resetp_CConfigSet__::_1_::catch_1(__int64 a1, __int64 a2)
{
  CConfigSet *v2; // rcx

  v2 = *(CConfigSet **)(a2 + 72);
  if ( v2 )
    CConfigSet::`scalar deleting destructor'(v2);
  throw;
}

```

## disassembly

```asm
0x180011bb2  mov     [rsp+arg_8], rdx
0x180011bb7  push    rbp
0x180011bb8  sub     rsp, 20h
0x180011bbc  mov     rbp, rdx
0x180011bbf  mov     rcx, [rbp+48h]; this
0x180011bc3  test    rcx, rcx
0x180011bc6  jz      short loc_180011BCD
0x180011bc8  call    ??_GCConfigSet@@QEAAPEAXI@Z; CConfigSet::`scalar deleting destructor'(uint)
0x180011bcd  xor     edx, edx; pThrowInfo
0x180011bcf  xor     ecx, ecx; pExceptionObject
0x180011bd1  call    _CxxThrowException_0
```
