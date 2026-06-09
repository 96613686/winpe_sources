# CommonUtil::AutoRef<IManagementShield3>::~AutoRef<IManagementShield3>(void)

- ea: `0x140002720`
- end: `0x14000273d`
- name: `??1?$AutoRef@UIManagementShield3@@@CommonUtil@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000fbc6`
- `0x14000fc30`

## callees

- `0x140002720`
- `0x140011010`

## pseudocode

```c
__int64 __fastcall CommonUtil::AutoRef<IManagementShield3>::~AutoRef<IManagementShield3>(__int64 *a1)
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
0x140002720  sub     rsp, 28h
0x140002724  mov     rcx, [rcx]
0x140002727  test    rcx, rcx
0x14000272a  jz      short loc_140002738
0x14000272c  mov     rax, [rcx]
0x14000272f  mov     rax, [rax+10h]
0x140002733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002738  add     rsp, 28h
0x14000273c  retn
```
