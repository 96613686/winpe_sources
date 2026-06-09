# std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>::~shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>(void)

- ea: `0x18000c52c`
- end: `0x18000c578`
- name: `??1?$shared_ptr@VMidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@@std@@QEAA@XZ`
- size: `76`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001b7a0`
- `0x18002af94`
- `0x18003f350`
- `0x18003f362`
- `0x18003f3ce`
- `0x18003f3e0`
- `0x18003f8b3`
- `0x18003f963`
- `0x18003f975`
- `0x18003f987`
- `0x18003f9cf`
- `0x18003fdf1`
- `0x18003fe03`
- `0x18003fe15`
- `0x18003fe39`
- `0x18003ff54`
- `0x18004023c`

## callees

- `0x18000c52c`
- `0x180041010`

## pseudocode

```c
__int64 __fastcall std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>::~shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>(
        __int64 a1)
{
  volatile signed __int32 *v1; // rbx
  __int64 result; // rax

  v1 = *(volatile signed __int32 **)(a1 + 8);
  if ( v1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v1)(v1);
      result = (unsigned int)_InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c52c  push    rbx
0x18000c52e  sub     rsp, 20h
0x18000c532  mov     rbx, [rcx+8]
0x18000c536  test    rbx, rbx
0x18000c539  jz      short loc_18000C572
0x18000c53b  or      eax, 0FFFFFFFFh
0x18000c53e  lock xadd [rbx+8], eax
0x18000c543  cmp     eax, 1
0x18000c546  jnz     short loc_18000C572
0x18000c548  mov     rax, [rbx]
0x18000c54b  mov     rcx, rbx
0x18000c54e  mov     rax, [rax]
0x18000c551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c556  or      eax, 0FFFFFFFFh
0x18000c559  lock xadd [rbx+0Ch], eax
0x18000c55e  cmp     eax, 1
0x18000c561  jnz     short loc_18000C572
0x18000c563  mov     rax, [rbx]
0x18000c566  mov     rcx, rbx
0x18000c569  mov     rax, [rax+8]
0x18000c56d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c572  add     rsp, 20h
0x18000c576  pop     rbx
0x18000c577  retn
```
