# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x180008b54`
- end: `0x180008b73`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007af0`
- `0x18000d274`
- `0x18000d430`
- `0x18000eebc`
- `0x18000f578`
- `0x180010d40`
- `0x180011050`
- `0x180014640`
- `0x180014830`
- `0x1800160e0`
- `0x180018d78`
- `0x18001b2f8`
- `0x18001ba1c`
- `0x18001bacc`
- `0x18001c2bc`
- `0x18001c560`
- `0x18001c63c`
- `0x18001c990`
- `0x18001cc90`
- `0x18001d3e0`
- `0x18001e068`
- `0x18001e150`
- `0x18001e230`
- `0x18001e448`
- `0x18001e620`
- `0x18001e840`
- `0x18001ea64`
- `0x18001f284`
- `0x180020674`
- `0x180021fac`

## callees

- `0x180008b54`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(__int64 *a1)
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
0x180008b54  sub     rsp, 28h
0x180008b58  mov     rcx, [rcx]
0x180008b5b  test    rcx, rcx
0x180008b5e  jz      short loc_180008B6D
0x180008b60  mov     rax, [rcx]
0x180008b63  mov     rax, [rax+10h]
0x180008b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b6c  nop
0x180008b6d  add     rsp, 28h
0x180008b71  retn
```
