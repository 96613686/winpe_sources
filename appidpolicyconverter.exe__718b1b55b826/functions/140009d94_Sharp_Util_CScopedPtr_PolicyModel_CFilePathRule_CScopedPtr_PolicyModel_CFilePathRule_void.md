# Sharp::Util::CScopedPtr<PolicyModel::CFilePathRule>::~CScopedPtr<PolicyModel::CFilePathRule>(void)

- ea: `0x140009d94`
- end: `0x140009db5`
- name: `??1?$CScopedPtr@VCFilePathRule@PolicyModel@@@Util@Sharp@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400091f4`
- `0x1400092a8`
- `0x14000935c`
- `0x1400141ab`

## callees

- `0x140009d94`
- `0x140016010`

## pseudocode

```c
__int64 __fastcall Sharp::Util::CScopedPtr<PolicyModel::CFilePathRule>::~CScopedPtr<PolicyModel::CFilePathRule>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x140009d94  sub     rsp, 28h
0x140009d98  mov     rcx, [rcx]
0x140009d9b  test    rcx, rcx
0x140009d9e  jz      short loc_140009DB0
0x140009da0  mov     rax, [rcx]
0x140009da3  mov     edx, 1
0x140009da8  mov     rax, [rax]
0x140009dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009db0  add     rsp, 28h
0x140009db4  retn
```
