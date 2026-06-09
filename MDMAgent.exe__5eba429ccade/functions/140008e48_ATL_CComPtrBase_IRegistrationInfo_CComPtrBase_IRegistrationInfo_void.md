# ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)

- ea: `0x140008e48`
- end: `0x140008e65`
- name: `??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400095cc`
- `0x1400096dc`
- `0x14000a0b8`
- `0x14000bdc4`
- `0x14000d0fc`
- `0x14000d70c`
- `0x14000dca0`
- `0x14000e200`
- `0x14000e530`
- `0x14000e6e8`
- `0x14000eaa8`
- `0x14000ef04`
- `0x14000f56c`

## callees

- `0x140008e48`
- `0x140019010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(__int64 *a1)
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
0x140008e48  sub     rsp, 28h
0x140008e4c  mov     rcx, [rcx]
0x140008e4f  test    rcx, rcx
0x140008e52  jz      short loc_140008E60
0x140008e54  mov     rax, [rcx]
0x140008e57  mov     rax, [rax+10h]
0x140008e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e60  add     rsp, 28h
0x140008e64  retn
```
