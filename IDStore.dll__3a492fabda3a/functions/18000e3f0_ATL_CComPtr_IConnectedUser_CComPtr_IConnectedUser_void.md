# ATL::CComPtr<IConnectedUser>::~CComPtr<IConnectedUser>(void)

- ea: `0x18000e3f0`
- end: `0x18000e40e`
- name: `??1?$CComPtr@UIConnectedUser@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019890`
- `0x1800198a2`
- `0x1800198e4`
- `0x1800198f6`
- `0x180019ae2`
- `0x180019af4`

## callees

- `0x18000e3f0`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IConnectedUser>::~CComPtr<IConnectedUser>(__int64 *a1)
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
0x18000e3f0  sub     rsp, 28h
0x18000e3f4  mov     rcx, [rcx]
0x18000e3f7  test    rcx, rcx
0x18000e3fa  jz      short loc_18000E409
0x18000e3fc  mov     rax, [rcx]
0x18000e3ff  mov     rax, [rax+10h]
0x18000e403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e408  nop
0x18000e409  add     rsp, 28h
0x18000e40d  retn
```
