# Concurrency::details::SchedulerProxy::DeleteThis(void)

- ea: `0x1800230e0`
- end: `0x180023100`
- name: `?DeleteThis@SchedulerProxy@details@Concurrency@@MEAAXXZ`
- size: `32`
- prototype: `void __fastcall(PVOID lpFlsData)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800230e0`
- `0x180023100`
- `0x180023610`

## pseudocode

```c
void __fastcall Concurrency::details::SchedulerProxy::DeleteThis(PVOID lpFlsData)
{
  if ( lpFlsData )
  {
    sub_180023100();
    sub_180023610(lpFlsData);
  }
}

```

## disassembly

```asm
0x1800230e0  test    rcx, rcx
0x1800230e3  jz      short locret_1800230FF
0x1800230e5  push    rbx
0x1800230e6  sub     rsp, 20h
0x1800230ea  mov     rbx, rcx
0x1800230ed  call    sub_180023100
0x1800230f2  mov     rcx, rbx; lpMem
0x1800230f5  call    sub_180023610
0x1800230fa  add     rsp, 20h
0x1800230fe  pop     rbx
0x1800230ff  retn
```
