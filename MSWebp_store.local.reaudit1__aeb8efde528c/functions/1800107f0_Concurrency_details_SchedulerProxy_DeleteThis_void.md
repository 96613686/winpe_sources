# Concurrency::details::SchedulerProxy::DeleteThis(void)

- ea: `0x1800107f0`
- end: `0x180010810`
- name: `?DeleteThis@SchedulerProxy@details@Concurrency@@MEAAXXZ`
- size: `32`
- prototype: `void __fastcall(Concurrency::details::SchedulerProxy *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180008440`
- `0x1800085a0`
- `0x180014070`
- `0x180014500`

## callees

- `0x180001310`
- `0x18000fe60`
- `0x1800107f0`

## pseudocode

```c
void __fastcall Concurrency::details::SchedulerProxy::DeleteThis(Concurrency::details::SchedulerProxy *this)
{
  if ( this )
  {
    sub_18000FE60();
    j_free(this);
  }
}

```

## disassembly

```asm
0x1800107f0  test    rcx, rcx
0x1800107f3  jz      short locret_18001080F
0x1800107f5  push    rbx
0x1800107f6  sub     rsp, 20h
0x1800107fa  mov     rbx, rcx
0x1800107fd  call    sub_18000FE60
0x180010802  mov     rcx, rbx; Block
0x180010805  call    j_free
0x18001080a  add     rsp, 20h
0x18001080e  pop     rbx
0x18001080f  retn
```
