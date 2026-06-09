# ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)

- ea: `0x14000904c`
- end: `0x14000906a`
- name: `??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140009040`
- `0x140009f78`
- `0x14000a034`
- `0x14000a14c`
- `0x14000cb14`
- `0x14001050c`
- `0x1400105bc`
- `0x140010698`
- `0x140010a2c`
- `0x1400162cc`
- `0x140018878`
- `0x14001b370`

## callees

- `0x14000904c`
- `0x14001c010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(__int64 *a1)
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
0x14000904c  sub     rsp, 28h
0x140009050  mov     rcx, [rcx]
0x140009053  test    rcx, rcx
0x140009056  jz      short loc_140009065
0x140009058  mov     rax, [rcx]
0x14000905b  mov     rax, [rax+10h]
0x14000905f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009064  nop
0x140009065  add     rsp, 28h
0x140009069  retn
```
