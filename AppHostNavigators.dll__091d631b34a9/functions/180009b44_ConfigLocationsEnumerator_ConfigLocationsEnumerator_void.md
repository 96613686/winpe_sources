# ConfigLocationsEnumerator::~ConfigLocationsEnumerator(void)

- ea: `0x180009b44`
- end: `0x180009b6d`
- name: `??1ConfigLocationsEnumerator@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(ConfigLocationsEnumerator *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a104`
- `0x18000cb10`
- `0x18001393d`
- `0x180013a93`

## callees

- `0x1800021a4`
- `0x1800021e0`

## pseudocode

```c
void __fastcall ConfigLocationsEnumerator::~ConfigLocationsEnumerator(ConfigLocationsEnumerator *this)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 6);
  BUFFER::~BUFFER((ConfigLocationsEnumerator *)((char *)this + 24));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 1);
}

```

## disassembly

```asm
0x180009b44  push    rbx
0x180009b46  sub     rsp, 20h
0x180009b4a  mov     rbx, rcx
0x180009b4d  add     rcx, 30h ; '0'
0x180009b51  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009b56  lea     rcx, [rbx+18h]; this
0x180009b5a  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180009b5f  lea     rcx, [rbx+8]
0x180009b63  add     rsp, 20h
0x180009b67  pop     rbx
0x180009b68  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
