# _std::tr1::shared_ptr_IRegistryKey_::_Resetp_SerializedRegistryKey__::_1_::catch$1

- ea: `0x1800247ee`
- end: `0x18002481f`
- name: `_std::tr1::shared_ptr_IRegistryKey_::_Resetp_SerializedRegistryKey__::_1_::catch$1`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180013294`
- `0x1800247ee`
- `0x180025010`

## pseudocode

```c
void __fastcall __noreturn std::tr1::shared_ptr_IRegistryKey_::_Resetp_SerializedRegistryKey__::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a2 + 72);
  if ( v2 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 96LL))(v2, 1);
  throw;
}

```

## disassembly

```asm
0x1800247ee  mov     [rsp+arg_8], rdx
0x1800247f3  push    rbp
0x1800247f4  sub     rsp, 20h
0x1800247f8  mov     rbp, rdx
0x1800247fb  mov     rcx, [rbp+48h]
0x1800247ff  test    rcx, rcx
0x180024802  jz      short loc_180024815
0x180024804  mov     rax, [rcx]
0x180024807  mov     edx, 1
0x18002480c  mov     rax, [rax+60h]
0x180024810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024815  xor     edx, edx; pThrowInfo
0x180024817  xor     ecx, ecx; pExceptionObject
0x180024819  call    _CxxThrowException_0
```
