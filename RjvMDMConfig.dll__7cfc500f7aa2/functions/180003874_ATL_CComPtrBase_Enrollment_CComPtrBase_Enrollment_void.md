# ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>(void)

- ea: `0x180003874`
- end: `0x180003893`
- name: `??1?$CComPtrBase@VEnrollment@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003868`
- `0x180004168`
- `0x1800049f8`
- `0x180017ed8`
- `0x1800183d0`
- `0x1800184a0`
- `0x180018570`
- `0x180018634`
- `0x180018710`
- `0x180018820`
- `0x180019670`
- `0x1800198f0`
- `0x180019a90`
- `0x180019dd0`
- `0x18001ac70`
- `0x18001b474`

## callees

- `0x180003874`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180003874  sub     rsp, 28h
0x180003878  mov     rcx, [rcx]
0x18000387b  test    rcx, rcx
0x18000387e  jz      short loc_18000388D
0x180003880  mov     rax, [rcx]
0x180003883  mov     rax, [rax+10h]
0x180003887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000388c  nop
0x18000388d  add     rsp, 28h
0x180003891  retn
```
