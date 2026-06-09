# std::unique_ptr<RegistryT<256>,std::default_delete<RegistryT<256>>>::~unique_ptr<RegistryT<256>,std::default_delete<RegistryT<256>>>(void)

- ea: `0x1800255b0`
- end: `0x1800255e0`
- name: `??1?$unique_ptr@V?$RegistryT@$0BAA@@@U?$default_delete@V?$RegistryT@$0BAA@@@@std@@@std@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002ac42`
- `0x18002ac54`

## callees

- `0x1800255b0`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<RegistryT<256>>::~unique_ptr<RegistryT<256>>(__int64 a1)
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  if ( *(_QWORD *)a1 )
  {
    v1 = (__int64 (__fastcall ***)(_QWORD, __int64))(*(_QWORD *)a1
                                                   + *(int *)(*(_QWORD *)(*(_QWORD *)a1 + 32LL) + 4LL)
                                                   + 32LL);
    return (**v1)(v1, 1);
  }
  return result;
}

```

## disassembly

```asm
0x1800255b0  sub     rsp, 28h
0x1800255b4  mov     rdx, [rcx]
0x1800255b7  test    rdx, rdx
0x1800255ba  jz      short loc_1800255DB
0x1800255bc  mov     rax, [rdx+20h]
0x1800255c0  movsxd  rcx, dword ptr [rax+4]
0x1800255c4  add     rcx, 20h ; ' '
0x1800255c8  add     rcx, rdx
0x1800255cb  mov     edx, 1
0x1800255d0  mov     rax, [rcx]
0x1800255d3  mov     rax, [rax]
0x1800255d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255db  add     rsp, 28h
0x1800255df  retn
```
