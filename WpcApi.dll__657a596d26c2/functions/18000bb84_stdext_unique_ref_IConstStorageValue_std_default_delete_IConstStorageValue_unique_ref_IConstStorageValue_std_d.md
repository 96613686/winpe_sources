# stdext::unique_ref<IConstStorageValue,std::default_delete<IConstStorageValue>>::~unique_ref<IConstStorageValue,std::default_delete<IConstStorageValue>>(void)

- ea: `0x18000bb84`
- end: `0x18000bba5`
- name: `??1?$unique_ref@UIConstStorageValue@@U?$default_delete@UIConstStorageValue@@@std@@@stdext@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x1800184e8`
- `0x1800296fc`
- `0x18002970e`
- `0x180029732`
- `0x180029c29`
- `0x180029c3b`
- `0x180029dec`
- `0x180029e58`
- `0x180029e7c`
- `0x180029ed6`
- `0x180029efa`
- `0x180029f0c`
- `0x180029fd2`
- `0x18002a1e1`
- `0x18002ab78`
- `0x18002abd4`

## callees

- `0x18000bb84`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall stdext::unique_ref<IConstStorageValue,std::default_delete<IConstStorageValue>>::~unique_ref<IConstStorageValue,std::default_delete<IConstStorageValue>>(
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
0x18000bb84  sub     rsp, 28h
0x18000bb88  mov     rcx, [rcx]
0x18000bb8b  test    rcx, rcx
0x18000bb8e  jz      short loc_18000BBA0
0x18000bb90  mov     rax, [rcx]
0x18000bb93  mov     edx, 1
0x18000bb98  mov     rax, [rax]
0x18000bb9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bba0  add     rsp, 28h
0x18000bba4  retn
```
