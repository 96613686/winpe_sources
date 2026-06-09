# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Platform::Object]::__abi_AddRef

- ea: `0x14001d470`
- end: `0x14001d4a5`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Platform::Object]::__abi_AddRef`
- size: `53`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14001d4b0`
- `0x14001d4c0`
- `0x14001d4d0`
- `0x14001d4e0`
- `0x14001d4f0`
- `0x14001d500`
- `0x14001d510`
- `0x14001d520`
- `0x14001d530`
- `0x14001d550`
- `0x14001d570`
- `0x14001d590`

## callees

- `0x14001d470`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::_Platform::Object_::__abi_AddRef(
        __int64 a1)
{
  if ( *(_QWORD *)(a1 + 176) && *(int *)(*(_QWORD *)(a1 + 176) + 12LL) >= 0 )
    return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 176) + 12LL));
  else
    return (unsigned int)-1;
}

```

## disassembly

```asm
0x14001d470  mov     rax, [rcx+0B0h]
0x14001d477  test    rax, rax
0x14001d47a  jz      short loc_14001D49F
0x14001d47c  mov     rax, [rcx+0B0h]
0x14001d483  mov     edx, [rax+0Ch]
0x14001d486  test    edx, edx
0x14001d488  js      short loc_14001D49F
0x14001d48a  mov     rax, [rcx+0B0h]
0x14001d491  mov     ecx, 1
0x14001d496  lock xadd [rax+0Ch], ecx
0x14001d49b  inc     ecx
0x14001d49d  jmp     short loc_14001D4A2
0x14001d49f  or      ecx, 0FFFFFFFFh
0x14001d4a2  mov     eax, ecx
0x14001d4a4  retn
```
