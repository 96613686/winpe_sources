# std::unique_ptr<IHierarchicalStorage,std::default_delete<IHierarchicalStorage>>::~unique_ptr<IHierarchicalStorage,std::default_delete<IHierarchicalStorage>>(void)

- ea: `0x180016290`
- end: `0x1800162c0`
- name: `??1?$unique_ptr@UIHierarchicalStorage@@U?$default_delete@UIHierarchicalStorage@@@std@@@std@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180029c71`
- `0x180029c83`
- `0x180029c95`
- `0x180029ca7`
- `0x180029ff6`
- `0x18002a008`
- `0x18002a01a`
- `0x18002a02c`
- `0x18002a074`
- `0x18002ab66`
- `0x18002abe6`
- `0x18002ac66`
- `0x18002acc0`

## callees

- `0x180016290`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<IHierarchicalStorage>::~unique_ptr<IHierarchicalStorage>(__int64 a1)
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  if ( *(_QWORD *)a1 )
  {
    v1 = (__int64 (__fastcall ***)(_QWORD, __int64))(*(_QWORD *)a1
                                                   + *(int *)(*(_QWORD *)(*(_QWORD *)a1 + 8LL) + 4LL)
                                                   + 8LL);
    return (**v1)(v1, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180016290  sub     rsp, 28h
0x180016294  mov     rdx, [rcx]
0x180016297  test    rdx, rdx
0x18001629a  jz      short loc_1800162BB
0x18001629c  mov     rax, [rdx+8]
0x1800162a0  movsxd  rcx, dword ptr [rax+4]
0x1800162a4  add     rcx, 8
0x1800162a8  add     rcx, rdx
0x1800162ab  mov     edx, 1
0x1800162b0  mov     rax, [rcx]
0x1800162b3  mov     rax, [rax]
0x1800162b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162bb  add     rsp, 28h
0x1800162bf  retn
```
