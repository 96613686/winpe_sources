# ATL::CComPtr<IApplicationActivationManager>::~CComPtr<IApplicationActivationManager>(void)

- ea: `0x14000ea30`
- end: `0x14000ea4e`
- name: `??1?$CComPtr@UIApplicationActivationManager@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011123`
- `0x140011135`
- `0x1400111a1`
- `0x1400111b3`
- `0x1400111c5`
- `0x1400111d7`
- `0x1400111e9`
- `0x1400111fb`
- `0x14001120d`
- `0x14001121f`
- `0x140011231`
- `0x140011277`
- `0x140011289`
- `0x14001129b`

## callees

- `0x14000ea30`
- `0x140012010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IApplicationActivationManager>::~CComPtr<IApplicationActivationManager>(__int64 *a1)
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
0x14000ea30  sub     rsp, 28h
0x14000ea34  mov     rcx, [rcx]
0x14000ea37  test    rcx, rcx
0x14000ea3a  jz      short loc_14000EA49
0x14000ea3c  mov     rax, [rcx]
0x14000ea3f  mov     rax, [rax+10h]
0x14000ea43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ea48  nop
0x14000ea49  add     rsp, 28h
0x14000ea4d  retn
```
